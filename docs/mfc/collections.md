---
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
ms.openlocfilehash: 3fba3a3c6cd3fecbda7f46575b1d72c450c44019
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361865"
---
# <a name="collections"></a>コレクション

Microsoft Foundation クラス ライブラリには、オブジェクトのグループを管理するためのコレクション クラスが用意されています。 これらのクラスには、次の 2 つのタイプがあります。

- [C++ テンプレートから作成されたコレクション クラス](#_core_the_template_based_collection_classes)

- [テンプレートから作成されないコレクション クラス](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
> コードで既に非テンプレート コレクション クラスを使用している場合は、それらを引き続き使用できます。 独自のデータ型に対して新しいタイプ セーフなコレクション クラスを記述する場合は、新しいテンプレート ベースのクラスを使用することをお勧めします。

## <a name="collection-shapes"></a><a name="_core_collection_shapes"></a>コレクション図形

コレクション クラスは、その "形状" と要素の型によって特徴付けられます。 図形は、コレクションによってオブジェクトが整理され格納される方法を示します。 MFC には、リスト、配列、およびマップ (ディクショナリとも呼ばれます) の 3 つの基本的なコレクション図形が用意されています。 特定のプログラミングの問題に最も適したコレクションの形状を選択できます。

このトピックでは、提供される 3 つのコレクション図形について簡単に説明します。 図形の機能を比較して、プログラムに最適な方法を判断するには、「[コレクション クラスを選択するための推奨事項](../mfc/recommendations-for-choosing-a-collection-class.md)」を参照してください。

- List

   list クラスは、二重リンク リストとして実装された、順序付けられたインデックスなしの要素のリストを提供します。 リストには「頭」と「尾」があり、頭や尾に要素を追加または削除したり、中央に要素を挿入または削除したりするのは非常に高速です。

- Array

   配列クラスは、オブジェクトの動的なサイズ、順序付け、および整数インデックス配列を提供します。

- マップ (ディクショナリとも呼ばれます)

   マップは、キー オブジェクトを値オブジェクトに関連付けるコレクションです。

## <a name="the-template-based-collection-classes"></a><a name="_core_the_template_based_collection_classes"></a>テンプレートベースのコレクション クラス

任意の型のオブジェクトを含むタイプ セーフなコレクションを実装する最も簡単な方法は、MFC テンプレート ベースのクラスのいずれかを使用することです。 これらのクラスの例については、MFC サンプル[COLLECT](../overview/visual-cpp-samples.md)を参照してください。

次の表は、MFC テンプレート ベースのコレクション クラスの一覧です。

### <a name="collection-template-classes"></a>コレクション テンプレート クラス

|コレクションの内容|配列|表示内容|マップ|
|-------------------------|------------|-----------|----------|
|任意の型のオブジェクトのコレクション|`CArray`|`CList`|`CMap`|
|任意の型のオブジェクトへのポインターのコレクション|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

## <a name="the-collection-classes-not-based-on-templates"></a><a name="_core_the_collection_classes_not_based_on_templates"></a>テンプレートに基づくコレクション クラス

アプリケーションで MFC 非テンプレート クラスを既に使用している場合は、引き続き使用できます。 ただし、新しいコレクションの場合は、テンプレート ベースのクラスを使用することをお勧めします。 次の表は、テンプレートに基づく MFC コレクション クラスの一覧です。

### <a name="nontemplate-collection-classes"></a>非テンプレート コレクション クラス

|配列|表示内容|マップ|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

「コレクション クラスを[選択するための推奨事項](../mfc/recommendations-for-choosing-a-collection-class.md)」の MFC コレクション クラスの特性の表では、これらの特性 (形状以外) の MFC コレクション クラスについて説明します。

- クラスで C++ テンプレートを使用しているかどうか

- コレクションに格納されている要素をシリアル化できるかどうか

- コレクションに格納されている要素を診断用にダンプできるかどうか

- タイプ セーフなコレクションかどうか

### <a name="what-do-you-want-to-do"></a>どうしたいんですか

#### <a name="general-collection-class-tasks"></a>一般的なコレクション クラスのタスク

- [コレクション クラスの選択に関する推奨事項](../mfc/recommendations-for-choosing-a-collection-class.md)

- [方法: タイプ セーフなコレクションを作成する](../mfc/how-to-make-a-type-safe-collection.md)

- [スタック コレクションとキュー コレクションの作成](../mfc/creating-stack-and-queue-collections.md)

- [CArray::追加](../mfc/reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>テンプレート ベースのコレクション クラス タスク

- [テンプレートベースのクラス](../mfc/template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>コレクションのメンバーへのアクセス (テンプレートベースまたは非テンプレート)

- [コレクションのすべてのメンバーへのアクセス](../mfc/accessing-all-members-of-a-collection.md)

- [CObject コレクションの全オブジェクトの削除](../mfc/deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)<br/>
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
