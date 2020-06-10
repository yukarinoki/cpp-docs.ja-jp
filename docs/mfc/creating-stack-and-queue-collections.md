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
ms.openlocfilehash: 5db90422f78fc6ca3bc2a182f9569c33db56cad1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623214"
---
# <a name="creating-stack-and-queue-collections"></a>スタック コレクションとキュー コレクションの作成

この記事では、MFC リストクラスから、[スタック](#_core_stacks)や[キュー](#_core_queues)などの他のデータ構造を作成する方法について説明します。 この例では、から派生したクラスを使用し `CList` ますが、機能を追加する必要がない限り、を直接使用することもでき `CList` ます。

## <a name="stacks"></a><a name="_core_stacks"></a>煙

標準リストコレクションには先頭と末尾の両方があるため、後入れ先出しスタックの動作を模倣する派生リストコレクションを簡単に作成できます。 スタックは、カフェテリアのトレイのスタックに似ています。 トレイがスタックに追加されると、スタックの一番上に表示されます。 最後に追加されたトレイが、最初に削除されます。 リストコレクションメンバー関数とは、 `AddHead` `RemoveHead` リストの先頭から要素を追加および削除するために使用できます。したがって、最後に追加された要素が最初に削除されます。

#### <a name="to-create-a-stack-collection"></a>スタックコレクションを作成するには

1. 既存の MFC リストクラスの1つから新しいリストクラスを派生させ、スタック操作の機能をサポートするためにメンバー関数を追加します。

   次の例では、メンバー関数を追加して、スタックに要素をプッシュし、スタックの最上位の要素をピークし、スタックから最上位の要素をポップする方法を示します。

   [!code-cpp[NVC_MFCCollections#20](codesnippet/cpp/creating-stack-and-queue-collections_1.h)]

この方法では、基になるクラスが公開されることに注意 `CObList` してください。 ユーザーは、 `CObList` スタックにとって意味があるかどうかにかかわらず、任意のメンバー関数を呼び出すことができます。

## <a name="queues"></a><a name="_core_queues"></a> キュー

標準リストコレクションには先頭と末尾の両方があるため、先入れ先出しのキューの動作を模倣する派生リストのコレクションを簡単に作成できます。 キューは、カフェテリアの1行のメンバーに似ています。 最初のユーザーが最初に提供されます。 さらに多くのユーザーは、行の終わりにアクセスして、そのターンを待ちます。 リストコレクションメンバー関数とは、 `AddTail` `RemoveHead` リストの先頭または末尾から要素を追加および削除するために使用できます。したがって、最後に追加された要素は常に最後に削除されます。

#### <a name="to-create-a-queue-collection"></a>キューコレクションを作成するには

1. Microsoft Foundation Class ライブラリに用意されている定義済みリストクラスの1つから新しいリストクラスを派生し、キュー操作のセマンティクスをサポートするためにメンバー関数を追加します。

   次の例では、メンバー関数を追加して、キューの末尾に要素を追加し、キューの先頭から要素を取得する方法を示します。

   [!code-cpp[NVC_MFCCollections#21](codesnippet/cpp/creating-stack-and-queue-collections_2.h)]

## <a name="see-also"></a>関連項目

[コレクション](collections.md)
