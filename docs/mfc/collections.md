---
description: '詳細情報: コレクション'
title: コレクション
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, collections
- arrays [MFC], classes
- MFC collection classes
- shapes, collection
- collection classes [MFC], MFC
- collections, about collections
- array templates [MFC]
- collection classes [MFC], template-based
- collection classes [MFC], about collection classes
- collection classes [MFC], maps
- collection classes [MFC], arrays
- shapes
- collection classes [MFC], lists
- collection classes [MFC], shapes
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
ms.openlocfilehash: 63bc61b73a9ba654fd22ecf3a238f8ef89734221
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283473"
---
# <a name="collections"></a>コレクション

Microsoft Foundation Class ライブラリには、オブジェクトのグループを管理するためのコレクションクラスが用意されています。 これらのクラスには、次の2種類があります。

- [C++ テンプレートから作成されたコレクションクラス](#_core_the_template_based_collection_classes)

- [テンプレートから作成されていないコレクションクラス](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
> コードで既に非テンプレートコレクションクラスが使用されている場合は、引き続き使用できます。 独自のデータ型に対して新しいタイプセーフなコレクションクラスを作成する場合は、新しいテンプレートベースのクラスを使用することをお勧めします。

## <a name="collection-shapes"></a><a name="_core_collection_shapes"></a> コレクション図形

コレクションクラスの特性は、"shape" とその要素の型によって特徴付けられます。 図形は、オブジェクトがコレクションによってどのように編成および格納されるかを示します。 MFC には、リスト、配列、およびマップ (ディクショナリとも呼ばれます) という3つの基本的なコレクション図形が用意されています。 特定のプログラミングの問題に最も適したコレクション図形を選択できます。

指定された3つのコレクションの各図形については、このトピックの後半で簡単に説明します。 図形の機能を比較して、プログラムに最適なものを判断するには、「 [コレクションクラスの選択に関する推奨事項](recommendations-for-choosing-a-collection-class.md)」を参照してください。

- List

   リストクラスは、二重リンクリストとして実装されている要素の順序付けられたインデックスなしのリストを提供します。 リストには "head" と "tail" があり、ヘッドまたはテールの要素を追加または削除したり、中央に要素を挿入または削除したりすると非常に高速になります。

- Array

   Array クラスは、動的にサイズが設定され、順序付けられた、整数で始まるオブジェクトの配列を提供します。

- Map (辞書とも呼ばれます)

   マップとは、キーオブジェクトを値オブジェクトに関連付けるコレクションです。

## <a name="the-template-based-collection-classes"></a><a name="_core_the_template_based_collection_classes"></a> Template-Based コレクションクラス

任意の型のオブジェクトを含むタイプセーフなコレクションを実装する最も簡単な方法は、MFC テンプレートベースのクラスの1つを使用することです。 これらのクラスの例については、「MFC のサンプルの [収集](../overview/visual-cpp-samples.md)」を参照してください。

次の表は、MFC テンプレートベースのコレクションクラスを示しています。

### <a name="collection-template-classes"></a>コレクションテンプレートクラス

|コレクションの内容|配列|リスト|マップ|
|-------------------------|------------|-----------|----------|
|任意の型のオブジェクトのコレクション|`CArray`|`CList`|`CMap`|
|任意の型のオブジェクトへのポインターのコレクション|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

## <a name="the-collection-classes-not-based-on-templates"></a><a name="_core_the_collection_classes_not_based_on_templates"></a> テンプレートに基づいていないコレクションクラス

アプリケーションが既に MFC の非テンプレートクラスを使用している場合は、引き続き使用できます。 ただし、新しいコレクションの場合は、テンプレートベースのクラスを使用することをお勧めします。 次の表は、テンプレートに基づいていない MFC コレクションクラスの一覧です。

### <a name="nontemplate-collection-classes"></a>非テンプレートコレクションクラス

|配列|リスト|マップ|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

[「コレクションクラスの選択に関する推奨事項](recommendations-for-choosing-a-collection-class.md)」の「mfc コレクションクラスの特性」では、これらの特性 (形状以外) に関して mfc コレクションクラスについて説明しています。

- クラスで C++ テンプレートを使用しているかどうか

- コレクションに格納されている要素をシリアル化できるかどうか

- コレクションに格納されている要素を診断用にダンプできるかどうか

- タイプ セーフなコレクションかどうか

### <a name="what-do-you-want-to-do"></a>どうしたいんですか

#### <a name="general-collection-class-tasks"></a>一般的な Collection-Class タスク

- [コレクションクラスの選択に関する推奨事項](recommendations-for-choosing-a-collection-class.md)

- [方法: Type-Safe コレクションを作成する](how-to-make-a-type-safe-collection.md)

- [スタックコレクションとキューコレクションの作成](creating-stack-and-queue-collections.md)

- [CArray:: Add](reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>Template-Based Collection-Class タスク

- [テンプレートベースのクラス](template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>コレクションのメンバーへのアクセス (テンプレートベースまたは Not)

- [コレクションのすべてのメンバーへのアクセス](accessing-all-members-of-a-collection.md)

- [CObject コレクション内のすべてのオブジェクトの削除](deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>関連項目

[概念](mfc-concepts.md)<br/>
[MFC の一般的なトピック](general-mfc-topics.md)
