---
description: 詳細については、「C++ 標準 Library-Based コレクションの実装」を参照してください。
title: C++ 標準 Library-Based コレクションの実装
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: 4a403885a6fe66bf8e8578deeab05c7fc08e88a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152855"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>C++ 標準 Library-Based コレクションの実装

ATL には、 `ICollectionOnSTLImpl` C++ 標準ライブラリベースのコレクションインターフェイスをオブジェクトにすばやく実装できるようにするためのインターフェイスが用意されています。 このクラスがどのように動作するかを理解するために、このクラスを使用して、オートメーションクライアントを対象とする読み取り専用コレクションを実装する簡単な例 (下記参照) を使用します。

サンプルコードは、 [Atlcollections サンプル](../overview/visual-cpp-samples.md)からのものです。

この手順を完了するには、次の手順を実行します。

- [新しい単純なオブジェクトを生成](#vccongenerating_an_object)します。

- 生成されたインターフェイスの[IDL ファイルを編集](#vcconedit_the_idl)します。

- コレクション項目の格納方法と、COM インターフェイスを介してクライアントに公開される方法を記述する[5 つの typedef を作成](#vcconstorage_and_exposure_typedefs)します。

- [コピーポリシークラス用に2つの typedef を作成](#vcconcopy_classes)します。

- [列挙子とコレクションの実装の typedef を作成](#vcconenumeration_and_collection)します。

- [コレクション typedef を使用するようにウィザードで生成された C++ コードを編集し](#vcconedit_the_generated_code)ます。

- [コレクションを作成するコードを追加](#vcconpopulate_the_collection)します。

## <a name="generating-a-new-simple-object"></a><a name="vccongenerating_an_object"></a> 新しい単純なオブジェクトの生成

新しいプロジェクトを作成し、[アプリケーション設定] の [属性] ボックスがオフになっていることを確認します。 ATL の [クラスの追加] ダイアログボックスと単純なオブジェクトの追加ウィザードを使用して、という単純なオブジェクトを生成し `Words` ます。 というデュアルインターフェイスが生成されていることを確認し `IWords` ます。 生成されたクラスのオブジェクトは、単語のコレクション (つまり、文字列) を表すために使用されます。

## <a name="editing-the-idl-file"></a><a name="vcconedit_the_idl"></a> IDL ファイルの編集

次に示すように、IDL ファイルを開き、読み取り専用のコレクションインターフェイスを有効にするために必要な3つのプロパティを追加し `IWords` ます。

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

これは、オートメーションクライアントを念頭に置いて設計された読み取り専用コレクションインターフェイスの標準形式です。 このインターフェイス定義の番号付きコメントは、以下のコメントに対応しています。

1. コレクションインターフェイスは、通常、オートメーションクライアントがを介してプロパティにアクセスするため、デュアルに `_NewEnum` `IDispatch::Invoke` なります。 ただし、オートメーションクライアントは vtable 経由で残りのメソッドにアクセスできます。そのため、デュアルインターフェイスはディスパッチインターフェイスよりも適しています。

1. デュアルインターフェイスまたはディスパッチインターフェイスが実行時に拡張されない場合 (つまり、で追加のメソッドやプロパティを提供しない場合) は、 `IDispatch::Invoke` **非拡張** 属性を定義に適用する必要があります。 この属性は、コンパイル時にオートメーションクライアントが完全なコードの検証を実行できるようにします。 この場合、インターフェイスを拡張することはできません。

1. オートメーションクライアントでこのプロパティを使用できるようにするには、正しい DISPID が重要です。 (DISPID_NEWENUM にはアンダースコアが1つだけあることに注意してください)。

1. プロパティの DISPID として任意の値を指定でき `Item` ます。 ただし、 `Item` は通常、DISPID_VALUE を使用して、コレクションの既定のプロパティに設定します。 これにより、オートメーションクライアントは、明示的に名前を付けずにプロパティを参照できます。

1. プロパティの戻り値に使用されるデータ型 `Item` は、COM クライアントに関係する限り、コレクションに格納されている項目の型です。 インターフェイスは文字列を返します。したがって、標準の COM 文字列型である BSTR を使用する必要があります。 データは、後で説明するように、内部で異なる形式で格納することができます。

1. プロパティの DISPID に使用される値 `Count` は、まったく任意です。 このプロパティには標準の DISPID がありません。

## <a name="creating-typedefs-for-storage-and-exposure"></a><a name="vcconstorage_and_exposure_typedefs"></a> ストレージと公開のための Typedef の作成

コレクションインターフェイスを定義したら、データを格納する方法と、列挙子を使用してデータを公開する方法を決定する必要があります。

これらの質問に対する答えは、多数の typedef の形式で提供できます。これは、新しく作成されたクラスのヘッダーファイルの先頭付近に追加できます。

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

この場合は、std:: **string** s の **std:: vector** としてデータを格納します。 **std:: vector** は、マネージ配列のように動作する C++ 標準ライブラリコンテナークラスです。 **std:: string** は、C++ 標準ライブラリの string クラスです。 これらのクラスを使用すると、文字列のコレクションを簡単に操作できます。

このインターフェイスを成功させるには Visual Basic サポートが不可欠であるため、プロパティによって返される列挙子は `_NewEnum` インターフェイスをサポートする必要があり `IEnumVARIANT` ます。 これは、Visual Basic によって認識される唯一の列挙子インターフェイスです。

## <a name="creating-typedefs-for-copy-policy-classes"></a><a name="vcconcopy_classes"></a> コピーポリシークラス用の Typedef を作成する

これまでに作成した typedef は、列挙子とコレクションによって使用されるコピークラス用に、さらに typedef を作成するために必要なすべての情報を提供します。

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

この例では、 `GenericCopy` VCUE_Copy で定義されているカスタムクラスと [atlcollections](../overview/visual-cpp-samples.md) サンプルの VCUE_CopyString を使用できます。 このクラスは他のコードでも使用できますが、 `GenericCopy` 独自のコレクションで使用されるデータ型をサポートするために、のさらに特殊化したを定義することが必要になる場合があります。 詳細については、「 [ATL コピーポリシークラス](../atl/atl-copy-policy-classes.md)」を参照してください。

## <a name="creating-typedefs-for-enumeration-and-collection"></a><a name="vcconenumeration_and_collection"></a> 列挙およびコレクション用の Typedef を作成する

これで、この状況でクラスとクラスを特化するために必要なすべてのテンプレートパラメーター `CComEnumOnSTL` `ICollectionOnSTLImpl` が、typedef の形式で提供されています。 特殊化の使用を簡単にするために、次のように2つの typedef を作成します。

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

`CollectionType`は、 `ICollectionOnSTLImpl` 前に定義されたインターフェイスを実装し、を `IWords` サポートする列挙子を提供する、の特殊化のシノニムです `IEnumVARIANT` 。

## <a name="editing-the-wizard-generated-code"></a><a name="vcconedit_the_generated_code"></a> Wizard-Generated コードの編集

`CWords` `CollectionType` 次に示すように、ではなく、typedef によって表されるインターフェイスの実装から派生する必要があり `IWords` ます。

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

## <a name="adding-code-to-populate-the-collection"></a><a name="vcconpopulate_the_collection"></a> コレクションを作成するコードを追加する

残っているのは、ベクターにデータを設定することだけです。 この簡単な例では、クラスのコンストラクターのコレクションにいくつかの単語を追加できます。

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

ここで、任意のクライアントを使用してコードをテストできます。

## <a name="see-also"></a>関連項目

[コレクションと列挙子](../atl/atl-collections-and-enumerators.md)<br/>
[ATLCollections サンプル](../overview/visual-cpp-samples.md)<br/>
[ATL コピーポリシークラス](../atl/atl-copy-policy-classes.md)
