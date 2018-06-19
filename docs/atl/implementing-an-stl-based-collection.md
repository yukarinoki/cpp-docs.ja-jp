---
title: C++ 標準ライブラリに基づくコレクションを実装する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14a09f54598b525346a65b56a335711f114878cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359676"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>C++ 標準ライブラリに基づくコレクションを実装します。
ATL には、`ICollectionOnSTLImpl`に迅速に、オブジェクトに C++ 標準ライブラリに基づくコレクション インターフェイスを実装するインターフェイスです。 このクラスのしくみを理解するのには、簡単な例 (下記) はこのクラスを使用して、オートメーション クライアントを目的と読み取り専用のコレクションを実装する機能します。  
  
 サンプルのコードは、 [ATLCollections サンプル](../visual-cpp-samples.md)です。  
  
 この手順を完了するには。  
  
-   [新しいシンプル オブジェクトを生成する](#vccongenerating_an_object)です。  
  
-   [IDL ファイルを編集](#vcconedit_the_idl)生成されたインターフェイスです。  
  
-   [5 つの typedef を作成する](#vcconstorage_and_exposure_typedefs)コレクション アイテムの格納方法と、COM インターフェイスによるクライアントへの公開方法を説明します。  
  
-   [ポリシー クラスのコピー用の 2 つの typedef を作成](#vcconcopy_classes)です。  
  
-   [列挙子とコレクションの実装のための typedef を作成](#vcconenumeration_and_collection)です。  
  
-   [コレクションの typedef を使用するウィザードで生成された C++ コードを編集](#vcconedit_the_generated_code)です。  
  
-   [コレクションを設定するコードを追加](#vcconpopulate_the_collection)です。  
  
##  <a name="vccongenerating_an_object"></a> 新しいシンプル オブジェクトを生成します。  
 アプリケーション設定 属性 ボックスがオフになっていることを確認、新しいプロジェクトを作成します。 クラスの追加 ダイアログ ボックスを使用して、単純なオブジェクトを生成するシンプル オブジェクト ウィザードの追加と呼ばれる`Words`です。 デュアル インターフェイスが呼び出されることを確認してください`IWords`が生成されます。 生成されたクラスのオブジェクトは、語 (つまり、文字列) のコレクションを表すため使用されます。  
  
##  <a name="vcconedit_the_idl"></a> IDL ファイルを編集します。  
 ここで、IDL ファイルを開き、有効にするために必要な 3 つのプロパティを追加`IWords`が読み取り専用コレクション インターフェイスは、次に示すようにします。  
  
 [!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]  
  
 これは、注意のオートメーション クライアントに設計された読み取り専用コレクション インターフェイスの標準のフォームです。 このインターフェイスの定義では番号付きコメントは、次のコメントに対応しています。  
  
1.  オートメーション クライアントがアクセスするため、コレクション インターフェイスがデュアル通常、`_NewEnum`を介してプロパティ**idispatch::invoke**です。 ただし、オートメーション クライアントは、デュアル インターフェイスは、ディスパッチ インターフェイスにも適していますので、vtable を使用して残りのメソッドをアクセスできます。  
  
2.  実行時にインターフェイスをデュアルまたはディスパッチ インターフェイスを拡張するがいない場合 (つまり、追加のメソッドまたはプロパティ経由で提供されません**idispatch::invoke**) を適用する必要があります、 **nonextensible**属性を定義します。 この属性は、コンパイル時に完全なコードの検証を実行するオートメーション クライアントを使用できます。 この例では、インターフェイスを拡張しません。  
  
3.  DISPID を正しくは、オートメーション クライアントがこのプロパティを使用できるようにする場合に重要です。 (1 つだけではアンダー スコアがあることに注意してください**DISPID_NEWENUM**)。  
  
4.  DISPID として任意の値を指定することができます、**項目**プロパティです。 ただし、**項目**通常使用**DISPID_VALUE**コレクションの既定のプロパティを作成します。 これにより、オートメーション クライアントが明示的に名前を指定せず、プロパティを参照してください。  
  
5.  戻り値のデータ型、**項目**プロパティは、COM クライアントにとってはできる限り、コレクションに格納されている項目の種類。 インターフェイスには、文字列を返すため、標準の COM 文字列型を使用する必要があります`BSTR`です。 データを格納できます、別の形式で内部的にすぐにわかります。  
  
6.  DISPID で使用される値、**カウント**プロパティが完全に任意です。 このプロパティの標準 DISPID はありません。  
  
##  <a name="vcconstorage_and_exposure_typedefs"></a> 記憶域と露出の Typedef を作成します。  
 コレクション インターフェイスを定義すると、データの格納方法、および列挙子を使用してデータを公開する方法を決定する必要があります。  
  
 これらの質問に対する回答は、新しく作成されたクラスのヘッダー ファイルの先頭付近にある追加することができますの typedef の数値の形式で指定することができます。  
  
 [!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]  
  
 この場合、としてデータを格納する、 **std::vector**の**std::string**s。 **std::vector**マネージ配列のように動作する C++ 標準ライブラリのコンテナー クラスです。 **std::string** C++ 標準ライブラリの文字列のクラスです。 これらのクラスしやすいように文字列のコレクションを使用します。  
  
 列挙子がによって返される Visual Basic のサポートは、このインターフェイスの成功に不可欠であるため、`_NewEnum`プロパティをサポートする必要があります、 **IEnumVARIANT**インターフェイスです。 これは、Visual Basic で認識される唯一の列挙子インターフェイスです。  
  
##  <a name="vcconcopy_classes"></a> コピー ポリシー クラスの Typedef を作成します。  
 これまでに作成した typedef は、さらに、列挙子とコレクションで使用されるコピー クラスの typedef を作成する必要があります。 すべての情報を提供します。  
  
 [!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]  
  
 この例では、ユーザー設定を行うこともできます`GenericCopy`VCUE_Copy.h およびから VCUE_CopyString.h で定義されたクラス、 [ATLCollections](../visual-cpp-samples.md)サンプルです。 このクラスは、他のコードで使用できますが、さらに特殊化を定義する必要があります`GenericCopy`独自のコレクションで使用されるデータ型をサポートするためにします。 詳細については、次を参照してください。 [ATL コピー ポリシー クラス](../atl/atl-copy-policy-classes.md)です。  
  
##  <a name="vcconenumeration_and_collection"></a> 列挙型とコレクションの Typedef を作成します。  
 これですべてのテンプレート パラメーターを特化するために必要な`CComEnumOnSTL`と`ICollectionOnSTLImpl`typedef の形式でこのような状況のためのクラスが用意されています。 特化された型の使用を簡略化するには、次のように 2 つの typedef を作成します。  
  
 [!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]  
  
 今すぐ`CollectionType`特化したテンプレートのシノニムは、`ICollectionOnSTLImpl`を実装する、`IWords`インターフェイスは、以前に定義されているしをサポートする列挙子を提供**IEnumVARIANT**です。  
  
##  <a name="vcconedit_the_generated_code"></a> ウィザードで生成されたコードの編集  
 これで、派生する必要があります`CWords`によって表されるインターフェイスの実装から、 `CollectionType` typedef なく`IWords`次のように、します。  
  
 [!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]  
  
##  <a name="vcconpopulate_the_collection"></a> コレクションを設定するコードを追加します。  
 残っている唯一の機能は、データを持つベクトルを入力します。 この簡単な例では、クラスのコンス トラクターでコレクションにいくつかの単語を追加できます。  
  
 [!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]  
  
 ここで、任意のクライアントで、コードをテストできます。  
  
## <a name="see-also"></a>関連項目  
 [コレクションと列挙子](../atl/atl-collections-and-enumerators.md)   
 [ATLCollections サンプル](../visual-cpp-samples.md)   
 [ATL コピー ポリシー クラス](../atl/atl-copy-policy-classes.md)

