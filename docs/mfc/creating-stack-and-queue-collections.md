---
title: スタック コレクションとキュー コレクションの作成
ms.date: 11/04/2016
helpviewer_keywords:
- MFC collection classes [MFC], stack collections
- collections, stack
- stack
- collection classes [MFC], creating
- queue collections
- MFC collection classes [MFC], queue collections
- stack collections
- collections, queue
ms.assetid: 3c7bc198-35f0-4fc3-aaed-6005a0f22638
ms.openlocfilehash: 5b3427f7bb2e46435ddf2768bcbb816f9d7e5c1a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371603"
---
# <a name="creating-stack-and-queue-collections"></a>スタック コレクションとキュー コレクションの作成

この資料では[、MFC](#_core_stacks)リスト クラスからスタックやキューなどの他のデータ構造[を作成する](#_core_queues)方法について説明します。 この例では、 から`CList`派生したクラスを使用`CList`しますが、機能を追加する必要がない限り、直接使用できます。

## <a name="stacks"></a><a name="_core_stacks"></a>スタック

標準のリスト コレクションには頭と尾部の両方があるため、先入れ先出しスタックの動作を模倣した派生リスト コレクションを簡単に作成できます。 スタックはカフェテリアのトレイの積み重ねのようなものです。 トレイがスタックに追加されると、それらはスタックの上に移動します。 最後に追加されたトレイが最初に取り外されます。 リスト コレクションのメンバー`AddHead`関数`RemoveHead`を使用して、リストの先頭に対して要素を追加および削除できます。したがって、最後に追加された要素は、最初に削除されます。

#### <a name="to-create-a-stack-collection"></a>スタック コレクションを作成するには

1. 既存の MFC リスト クラスの 1 つから新しいリスト クラスを派生させ、スタック操作の機能をサポートするメンバー関数を追加します。

   次の例では、スタックに要素をプッシュするメンバー関数を追加し、スタックの一番上の要素を覗いて、スタックから最上位の要素をポップする方法を示します。

   [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]

この方法では、基になる`CObList`クラスが公開されることに注意してください。 ユーザーは、スタックに`CObList`対して意味を持つかどうかにかかわらず、任意のメンバー関数を呼び出すことができます。

## <a name="queues"></a><a name="_core_queues"></a> キュー

標準リスト コレクションには先頭と末尾の両方があるため、先入れ先出しキューの動作を模倣した派生リスト コレクションを簡単に作成できます。 行列は食堂の人々の列のようなものです。 最初に並ぶ人が最初に奉仕されます。 より多くの人々が来るにつれて、彼らは順番を待つために行の終わりに行きます。 リスト コレクションのメンバー`AddTail`関数`RemoveHead`を使用して、リストの先頭または末尾に対して要素を追加および削除できます。したがって、最後に追加された要素は、常に最後に削除されます。

#### <a name="to-create-a-queue-collection"></a>キュー コレクションを作成するには

1. Microsoft Foundation クラス ライブラリに用意されている定義済みのリスト クラスの 1 つから新しいリスト クラスを派生し、キュー操作のセマンティクスをサポートするメンバー関数を追加します。

   次の例は、メンバー関数を追加して、要素をキューの末尾に追加し、キューの先頭から要素を取得する方法を示しています。

   [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]

## <a name="see-also"></a>関連項目

[コレクション](../mfc/collections.md)
