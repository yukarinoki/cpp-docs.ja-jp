---
title: '方法: タイプ セーフなコレクションを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcd1fbce9e6dda649da8fe2e53fc7dc70db1da33
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-a-type-safe-collection"></a>方法: タイプ セーフなコレクションを作成する
この記事では、独自のデータ型のタイプ セーフなコレクションを作成する方法について説明します。 ここでは、次の内容について説明します。  
  
-   [テンプレート ベースのクラスを使用して、タイプ セーフ](#_core_using_template.2d.based_classes_for_type_safety)  
  
-   [ヘルパー関数の実装](#_core_implementing_helper_functions)  
  
-   [非テンプレート コレクション クラスを使用します。](#_core_using_nontemplate_collection_classes)  
  
 Microsoft Foundation Class ライブラリでは、C++ テンプレートに基づく定義済みのタイプ セーフなコレクションを提供します。 テンプレートがいるため、これらのクラスはタイプ セーフとせず、型キャストし、この目的の非テンプレート クラスの使用に関連するその他の余分な作業の使いやすさを実現に役立ちます。 MFC サンプル[収集](../visual-cpp-samples.md)MFC アプリケーションのテンプレートに基づくコレクション クラスの使用例を示します。 一般に、新しいコレクションのコードを作成するときのこれらのクラスを使用します。  
  
##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> テンプレート ベースのクラスを使用して、タイプ セーフ  
  
#### <a name="to-use-template-based-classes"></a>テンプレート ベースのクラスを使用するには  
  
1.  コレクション クラス型の変数を宣言します。 例えば:  
  
     [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]  
  
2.  メンバーのコレクション オブジェクトの関数を呼び出します。 例えば:  
  
     [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]  
  
3.  必要に応じて、実装、[ヘルパー関数](../mfc/reference/collection-class-helpers.md)と[SerializeElements](../mfc/reference/collection-class-helpers.md#serializeelements)です。 これらの関数を実装する方法については、次を参照してください。[ヘルパー関数の実装](#_core_implementing_helper_functions)です。  
  
 この例では、整数のリストの宣言を示します。 手順 1 の最初のパラメーターは、リストの要素として格納されたデータの種類です。 2 番目のパラメーター データを指定する方法に渡されるされなどのコレクション クラスのメンバー関数から返される**追加**と`GetAt`です。  
  
##  <a name="_core_implementing_helper_functions"></a> ヘルパー関数の実装  
 テンプレート ベースのコレクション クラス`CArray`、 `CList`、および`CMap`派生コレクション クラスの必要に応じてカスタマイズできる 5 つのグローバルなヘルパー関数を使用します。 これらのヘルパー関数については、次を参照してください。[コレクション クラスのヘルパー](../mfc/reference/collection-class-helpers.md)で、 *『 MFC リファレンス*です。 シリアル化の関数の実装は、テンプレート ベースのコレクション クラスのほとんどの用途の必要があります。  
  
###  <a name="_core_serializing_elements"></a> 要素をシリアル化します。  
 `CArray`、 `CList`、および`CMap`クラス呼び出し`SerializeElements`にコレクション要素を保存またはアーカイブからの読み取りにします。  
  
 既定の実装、`SerializeElements`ヘルパー関数では、オブジェクトのビットごとの書き込みは、アーカイブする、または、ビットごとのアーカイブから、オブジェクトに格納されているかどうかに応じて、オブジェクトへの読み取りまたはアーカイブから取得します。 オーバーライド`SerializeElements`このアクションが適切でない場合。  
  
 コレクションから派生したオブジェクトを格納する場合、`CObject`を使用して、`IMPLEMENT_SERIAL`マクロ コレクション要素クラスの実装に組み込まれたシリアル化機能の利点を行える`CArchive`と`CObject`:  
  
 [!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]  
  
 オーバー ロードされた挿入演算子`CArchive`呼び出す`CObject::Serialize`(またはその関数のオーバーライド) 各**CPerson**オブジェクト。  
  
##  <a name="_core_using_nontemplate_collection_classes"></a> 非テンプレート コレクション クラスを使用します。  
 MFC には、MFC バージョン 1.0 で導入されたコレクション クラスもサポートしています。 これらのクラスは、テンプレートには基づいていません。 サポートされる型のデータを格納する使えます`CObject*`、 **UINT**、 `DWORD`、および`CString`です。 これらの定義済みのコレクションを使用することができます (など`CObList`) から派生した任意のオブジェクトのコレクションを保持するために`CObject`です。 MFC は、その他の定義済みのコレクションなどのプリミティブ型を保持するためにも用意されています。 **UINT**ポインターを無効にすると (`void`*)。 一般に、ただしは多くの場合、固有のクラスとその派生クラスのオブジェクトを保持するために、独自のタイプ セーフなコレクションを定義すると便利です。 テンプレートに基づいていないコレクション クラスでこれをメモは、テンプレート ベースのクラスを使用するよりも多くの作業です。  
  
 これには、非テンプレート コレクションにタイプ セーフなコレクションを作成する 2 つの方法があります。  
  
1.  型キャストは、必要な場合に、非テンプレート コレクションを使用します。 これより簡単な方法です。  
  
2.  派生し、非テンプレート タイプ セーフなコレクションを拡張します。  
  
#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>型キャストを使用したテンプレートのコレクションを使用するには  
  
1.  非テンプレート クラスのいずれかのような使用`CWordArray`、直接です。  
  
     たとえば、作成することができます、`CWordArray`に任意の 32 ビット値を追加し、資格情報を取得します。 行うには詳細はありません。 定義済みの機能を使用するだけです。  
  
     など、定義済みのコレクションを使用することもできます。`CObList`から派生した任意のオブジェクトを保持するために、`CObject`です。 A`CObList`へのポインターを保持するためにコレクションが定義されている`CObject`です。 一覧からオブジェクトを取得する場合は、以降の適切な型に結果をキャストする必要があります、`CObList`関数へのポインターを返す`CObject`です。 格納する場合など、`CPerson`内のオブジェクト、 `CObList` 、コレクションへのポインターを取得した要素をキャストする必要がある、`CPerson`オブジェクト。 次の例では、`CObList`を保持するコレクション`CPerson`オブジェクト。  
  
     [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]  
  
     コレクションの要件の多くの十分な定義済みのコレクション型を使用して、必要に応じてキャストのこの手法もあります。 さらに機能または複数のタイプ セーフを必要がある場合は、テンプレート ベースのクラスを使用してまたは次の手順に従います。  
  
#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>派生および非テンプレート タイプ セーフなコレクションを拡張するには  
  
1.  定義済みの非テンプレート クラスの 1 つから独自のコレクション クラスを派生します。  
  
     クラスを派生させる場合は、既存の機能にタイプ セーフなインターフェイスを提供するタイプ セーフ ラッパー関数を追加できます。  
  
     たとえば、一覧からの派生`CObList`を保持する`CPerson`オブジェクト、ラッパー関数を追加する場合があります`AddHeadPerson`と`GetHeadPerson`次のように、します。  
  
     [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]  
  
     これらのラッパー関数を追加および取得するタイプ セーフな方法を提供する`CPerson`オブジェクト派生しますから。 ことがわかります、`GetHeadPerson`関数、型キャストをカプセル化するだけです。  
  
     タイプ セーフなラッパーで既存の機能をラップするだけではなく、コレクションの機能を拡張する新しい関数の定義によって新しい機能を追加することもできます。 記事など[CObject コレクション内のすべてのオブジェクトを削除する](../mfc/deleting-all-objects-in-a-cobject-collection.md)一覧に含まれるすべてのオブジェクトを削除する関数について説明します。 この関数は、メンバー関数として、派生クラスに追加できませんでした。  
  
## <a name="see-also"></a>関連項目  
 [コレクション](../mfc/collections.md)

