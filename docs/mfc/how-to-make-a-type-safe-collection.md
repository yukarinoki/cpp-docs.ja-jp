---
title: '方法 : タイプ セーフなコレクションを作成する'
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
ms.openlocfilehash: 1901100996a776244b57efe0951795ceec3c630a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377255"
---
# <a name="how-to-make-a-type-safe-collection"></a>方法 : タイプ セーフなコレクションを作成する

この記事では、独自のデータ型のタイプ セーフなコレクションを作成する方法について説明します。 取り上げるトピックは次のとおりです。

- [タイプ セーフのためのテンプレート ベースのクラスの使用](#_core_using_template.2d.based_classes_for_type_safety)

- [ヘルパー関数の実装](#_core_implementing_helper_functions)

- [非テンプレート コレクション クラスの使用](#_core_using_nontemplate_collection_classes)

Microsoft Foundation クラス ライブラリには、C++ テンプレートに基づく定義済みのタイプ セーフなコレクションが用意されています。 これらのクラスはテンプレートであるため、型のキャストや、この目的のために非テンプレート クラスを使用するその他の追加作業を行わずに、タイプ セーフで使いやすさを実現します。 MFC サンプル[COLLECT](../overview/visual-cpp-samples.md)は、MFC アプリケーションでテンプレート ベースのコレクション クラスを使用する方法を示します。 一般に、これらのクラスは、新しいコレクション コードを記述するときにはいつでも使用します。

## <a name="using-template-based-classes-for-type-safety"></a><a name="_core_using_template.2d.based_classes_for_type_safety"></a>タイプ セーフのためのテンプレート ベースのクラスの使用

#### <a name="to-use-template-based-classes"></a>テンプレート ベースのクラスを使用するには

1. コレクション クラス型の変数を宣言します。 次に例を示します。

   [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]

1. コレクション オブジェクトのメンバー関数を呼び出します。 次に例を示します。

   [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]

1. 必要に応じて、[ヘルパー関数](../mfc/reference/collection-class-helpers.md)と[SerializeElements を](../mfc/reference/collection-class-helpers.md#serializeelements)実装します。 これらの関数の実装については、「 ヘルパー関数の[実装](#_core_implementing_helper_functions)」を参照してください。

この例では、整数のリストの宣言を示します。 手順 1 の最初のパラメーターは、リストの要素として格納されているデータの型です。 2 番目のパラメーターは、コレクション クラスのメンバー関数にデータを渡し、`Add`および コレクション クラスの`GetAt`メンバー関数から返す方法を指定します。

## <a name="implementing-helper-functions"></a><a name="_core_implementing_helper_functions"></a>ヘルパー関数の実装

テンプレート ベースのコレクション`CArray`クラス`CList`、、および`CMap`派生コレクション クラスに合わせてカスタマイズできる 5 つのグローバル ヘルパ関数を使用します。 これらのヘルパー関数の詳細については、「MFC リファレンス」の[「コレクション クラス ヘルパー](../mfc/reference/collection-class-helpers.md) 」を*参照してください。* シリアル化関数の実装は、テンプレート ベースのコレクション クラスのほとんどの用途に必要です。

### <a name="serializing-elements"></a><a name="_core_serializing_elements"></a>要素のシリアル化

、 `CArray` `CList`、および`CMap`クラスは`SerializeElements`、コレクション要素をアーカイブに格納したり、アーカイブから読み取ったりするために呼び出します。

ヘルパー関数の`SerializeElements`既定の実装では、オブジェクトがアーカイブにビット単位で書き込まれるか、またはオブジェクトがアーカイブに格納されているか、アーカイブから取得されているかに応じて、アーカイブからオブジェクトへのビットごとの読み取りが行われます。 この`SerializeElements`アクションが適切でない場合はオーバーライドします。

コレクションが派生したオブジェクトを格納`CObject`し、コレクション要素`IMPLEMENT_SERIAL`クラスの実装でマクロを使用する場合は、 と`CArchive``CObject`に組み込まれているシリアル化機能を利用できます。

[!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]

各`CPerson`オブジェクトの呼び出`CArchive`し`CObject::Serialize`(またはその関数のオーバーライド) に対するオーバーロードされた挿入演算子。

## <a name="using-nontemplate-collection-classes"></a><a name="_core_using_nontemplate_collection_classes"></a>非テンプレート コレクション クラスの使用

MFC では、MFC バージョン 1.0 で導入されたコレクション クラスもサポートしています。 これらのクラスはテンプレートに基づいていません。 サポート`CObject*`されている型 、 、、`UINT``DWORD`および`CString`のデータを格納するために使用できます。 これらの定義済みコレクション ( など`CObList`) を使用して、 から`CObject`派生したオブジェクトのコレクションを保持できます。 MFC には、void ポインター (*)`UINT``void`などのプリミティブ型を保持する他の定義済みコレクションも用意されています。 ただし、一般的には、より特定のクラスとその派生物のオブジェクトを保持するために、独自のタイプ セーフなコレクションを定義すると便利です。 テンプレートに基づくコレクション クラスを使用する方が、テンプレート ベースのクラスを使用するよりも作業が多いことに注意してください。

非テンプレート コレクションを使用してタイプ セーフなコレクションを作成するには、次の 2 つの方法があります。

1. 必要に応じて、型キャストで非テンプレート コレクションを使用します。 これは簡単なアプローチです。

1. 非テンプレート タイプ セーフ なコレクションを派生および拡張します。

#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>型キャストで非テンプレート コレクションを使用するには

1. テンプレート以外のクラス (など`CWordArray`) を直接使用します。

   たとえば、作成`CWordArray`して 32 ビットの値を追加し、それらを取得できます。 これ以上やるべきことは何もない。 定義済みの機能を使用するだけです。

   また、 など`CObList`、定義済みのコレクションを使用して、 から`CObject`派生したオブジェクトを保持することもできます。 コレクション`CObList`は、 へのポインターを保持するように`CObject`定義されています。 リストからオブジェクトを取得する場合、`CObList`関数が ポインタを 返すため、結果を適切な型にキャストする`CObject`必要がある場合があります。 たとえば、コレクションにオブジェクトを`CPerson``CObList`格納する場合、取得した要素を`CPerson`オブジェクトへのポインターにキャストする必要があります。 次の例では、`CObList`コレクションを使用`CPerson`してオブジェクトを保持します。

   [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]

   この方法では、定義済みのコレクション型を使用し、必要に応じてキャストする方法は、コレクションのニーズの多くにとって適切な場合があります。 さらに機能が必要な場合やタイプ セーフを強化する必要がある場合は、テンプレート ベースのクラスを使用するか、次の手順に従います。

#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>非テンプレート タイプ セーフ コレクションを派生および拡張するには

1. 定義済みの非テンプレート クラスの 1 つから独自のコレクション クラスを派生させます。

   クラスを派生させる場合は、タイプ セーフなラッパー関数を追加して、既存の関数にタイプ セーフなインターフェイスを提供できます。

   `CObList`たとえば、オブジェクトを保持`CPerson`するためにリストを派生した場合、次に示すように、ラッパー関数`AddHeadPerson`と`GetHeadPerson`を追加できます。

   [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]

   これらのラッパー関数は、派生リストからオブジェクトを追加および取得`CPerson`するタイプ セーフな方法を提供します。 `GetHeadPerson`関数の場合は、型キャストをカプセル化していることがわかります。

   また、既存の機能をタイプ セーフラッパーにラップするのではなく、コレクションの機能を拡張する新しい関数を定義することで、新しい機能を追加することもできます。 たとえば[、CObject コレクション内のすべてのオブジェクトを削除する](../mfc/deleting-all-objects-in-a-cobject-collection.md)の記事では、リストに含まれるすべてのオブジェクトを削除する関数について説明します。 この関数は、派生クラスにメンバー関数として追加できます。

## <a name="see-also"></a>関連項目

[コレクション](../mfc/collections.md)
