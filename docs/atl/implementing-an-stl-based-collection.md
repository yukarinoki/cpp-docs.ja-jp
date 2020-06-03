---
title: C++ 標準ライブラリ ベースのコレクションの実装
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: e80ce5e7bbc6b9c6be1615dad1ea43c18e03eb55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319437"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>C++ 標準ライブラリ ベースのコレクションの実装

ATL は`ICollectionOnSTLImpl`、オブジェクトに C++ 標準ライブラリ ベースのコレクション インターフェイスを迅速に実装できるようにするインターフェイスを提供します。 このクラスの動作を理解するために、このクラスを使用してオートメーション クライアントを対象とした読み取り専用コレクションを実装する簡単な例 (以下) を使用します。

サンプル コードは[、ATLCollections サンプルから取得されています](../overview/visual-cpp-samples.md)。

この手順を完了するには、次の手順を実行します。

- [新しい簡易オブジェクトを生成します](#vccongenerating_an_object)。

- 生成[されたインターフェイスの IDL ファイルを編集](#vcconedit_the_idl)します。

- コレクション項目の格納方法と、COM インターフェイスを介してコレクション項目をクライアントに公開する方法を説明する[5 つの typedef](#vcconstorage_and_exposure_typedefs)を作成します。

- [コピー ポリシー クラス用に 2 つの typedef を作成](#vcconcopy_classes)する :

- [列挙子およびコレクションの実装の typedef を作成する](#vcconenumeration_and_collection)。

- [ウィザードで生成された C++ コードを編集して、コレクション typedef を使用](#vcconedit_the_generated_code)します。

- [コレクションにデータを追加するコードを追加](#vcconpopulate_the_collection)します。

## <a name="generating-a-new-simple-object"></a><a name="vccongenerating_an_object"></a>新しいシンプルオブジェクトの生成

新しいプロジェクトを作成し、[アプリケーション設定] の [属性] ボックスがクリアされていることを確認します。 ATL の [クラスの追加] ダイアログ ボックスと [シンプル`Words`オブジェクトの追加ウィザード] を使用して、 という単純オブジェクトを生成します。 呼び出される`IWords`デュアル インターフェイスが生成されていることを確認します。 生成されたクラスのオブジェクトは、単語のコレクション (文字列) を表すために使用されます。

## <a name="editing-the-idl-file"></a><a name="vcconedit_the_idl"></a>IDL ファイルの編集

次に、IDL ファイルを開き、次に示すように`IWords`、読み取り専用のコレクション インターフェイスに変換するために必要な 3 つのプロパティを追加します。

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

これは、オートメーション クライアントを念頭に置いて設計された読み取り専用コレクション インターフェイスの標準形式です。 このインターフェイス定義の番号付きコメントは、以下のコメントに対応しています。

1. オートメーション クライアントは を介して`_NewEnum``IDispatch::Invoke`プロパティにアクセスするため、コレクション インターフェイスは通常デュアルです。 ただし、オートメーション クライアントは vtable を介して残りのメソッドにアクセスできるため、インターフェイスを isp する場合はデュアル インターフェイスが推奨されます。

1. デュアル インターフェイスまたは disp インターフェイスが実行時に拡張されない場合 (つまり、追加のメソッドやプロパティを提供`IDispatch::Invoke`しない場合は、定義に**nonextenensible 属性**を適用する必要があります)。 この属性により、オートメーション クライアントはコンパイル時にコードの完全な検証を実行できます。 この場合、インターフェイスを拡張しないでください。

1. オートメーション クライアントがこのプロパティを使用できるようにする場合は、正しい DISPID が重要です。 (DISPID_NEWENUMにはアンダースコアが1つしか存在しません。

1. プロパティの DISPID として任意の値を`Item`指定できます。 ただし、`Item`通常はDISPID_VALUEを使用してコレクションの既定のプロパティにします。 これにより、オートメーション クライアントは、明示的に名前を付けずにプロパティを参照できます。

1. プロパティの戻り値に使用される`Item`データ型は、COM クライアントに関する限り、コレクションに格納されている項目の型です。 インターフェイスは文字列を返すため、標準の COM 文字列型 BSTR を使用する必要があります。 すぐにわかるように、データを内部で別の形式で保存できます。

1. プロパティの DISPID に使用される`Count`値は、完全に任意です。 このプロパティに対する標準の DISPID はありません。

## <a name="creating-typedefs-for-storage-and-exposure"></a><a name="vcconstorage_and_exposure_typedefs"></a>ストレージと露出用のタイプ定義の作成

コレクション インターフェイスを定義したら、データの格納方法と、列挙子を介してデータを公開する方法を決定する必要があります。

これらの質問に対する回答は、いくつかの typedefs の形式で提供できます。

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

この場合、データを**std::string** s の**std::vector**として格納します。 **std::vector**は、C++ 標準ライブラリのコンテナー クラスで、マネージ配列のように動作します。 **std::文字列**は C++ 標準ライブラリの文字列クラスです。 これらのクラスを使用すると、文字列のコレクションを簡単に操作できます。

Visual Basic のサポートは、このインターフェイスの成功に不可欠であるため、プロパティによって`_NewEnum`返される列挙子`IEnumVARIANT`は、インターフェイスをサポートする必要があります。 これは、Visual Basic で理解されている唯一の列挙子インターフェイスです。

## <a name="creating-typedefs-for-copy-policy-classes"></a><a name="vcconcopy_classes"></a>コピー ポリシー クラスの Typedef の作成

これまでに作成した typedef は、列挙子とコレクションで使用されるコピー クラスの追加の typedef を作成するために必要なすべての情報を提供します。

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

この例では[、atLCollections](../overview/visual-cpp-samples.md) `GenericCopy`サンプルから VCUE_Copy.h および VCUE_CopyString.h で定義されたカスタム クラスを使用できます。 このクラスは他のコードでも使用できますが、独自の`GenericCopy`コレクションで使用されるデータ型をサポートするために、さらに特殊化を定義する必要があります。 詳細については、「 [ATL コピー ポリシー クラス](../atl/atl-copy-policy-classes.md)」を参照してください。

## <a name="creating-typedefs-for-enumeration-and-collection"></a><a name="vcconenumeration_and_collection"></a>列挙とコレクションの Typedef の作成

これで、`CComEnumOnSTL`と`ICollectionOnSTLImpl`クラスを特化するために必要なすべてのテンプレート パラメーターが typedef の形式で提供されました。 特殊化の使用を簡略化するには、次に示すように、2 つの typedef を作成します。

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

ここでは`CollectionType`、前に定義`ICollectionOnSTLImpl`した`IWords`インターフェイスを実装し、 をサポート`IEnumVARIANT`する列挙子を提供する特殊化のシノニムです。

## <a name="editing-the-wizard-generated-code"></a><a name="vcconedit_the_generated_code"></a>ウィザードによって生成されたコードの編集

ここで、次に`CWords`示すように、typedef ではなく`CollectionType``IWords`typedef で表されるインターフェイス実装から派生する必要があります。

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

## <a name="adding-code-to-populate-the-collection"></a><a name="vcconpopulate_the_collection"></a>コレクションにデータを設定するコードの追加

残っている唯一のことは、ベクトルにデータを入力することです。 この簡単な例では、クラスのコンストラクターでコレクションにいくつかの単語を追加できます。

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

これで、選択したクライアントでコードをテストできます。

## <a name="see-also"></a>関連項目

[コレクションと列挙子](../atl/atl-collections-and-enumerators.md)<br/>
[ATL コレクションのサンプル](../overview/visual-cpp-samples.md)<br/>
[ATL コピー ポリシー クラス](../atl/atl-copy-policy-classes.md)
