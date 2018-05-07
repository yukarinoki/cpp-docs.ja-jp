---
title: スタック コレクションとキュー コレクションの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5545a1803675965cdea716e009ab70d2d72a31f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-stack-and-queue-collections"></a>スタック コレクションとキュー コレクションの作成
この記事などその他のデータ構造を作成する方法を説明します[スタック](#_core_stacks)と[キュー](#_core_queues)、MFC クラスのリストします。 例から派生したクラスを使用して`CList`、使用することができますが、`CList`直接機能を追加する必要がある場合を除き、します。  
  
##  <a name="_core_stacks"></a> スタック  
 標準のリスト コレクションは、先頭と末尾の両方があるため最後先出しスタックの動作を模倣した派生リスト コレクションの作成が容易になります。 スタックは、トレイ カフェテリアでのスタックに似ています。 トレイは、スタックに追加されるため、スタックの先頭に移動します。 追加された最後のトレイは、最初に削除します。 リスト コレクションのメンバー関数は、`AddHead`と`RemoveHead`を追加するために使用して具体的には、リストの先頭から要素を削除; そのため、最も最近追加された要素は、最初に削除されます。  
  
#### <a name="to-create-a-stack-collection"></a>スタック コレクションを作成するには  
  
1.  既存の MFC リスト クラスのいずれかから新しいリストのクラスを派生し、スタック操作の機能をサポートするメンバー関数を追加します。  
  
     次の例では、スタック、スタックの最上位の要素のピークに要素をプッシュして、スタックから先頭の要素をポップするメンバー関数を追加する方法を示します。  
  
     [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]  
  
 このアプローチが基になるを公開する注`CObList`クラスです。 ユーザーは、いずれかを呼び出すことができます`CObList`メンバー関数は、合理的スタックのかどうかどうか。  
  
##  <a name="_core_queues"></a> キュー  
 標準のリスト コレクションは、先頭と末尾の両方があるためにも簡単に最初に先出しキューの動作を模倣した派生リスト コレクションを作成できます。 キューは、カフェテリア内の人の行に似ています。 行の最初の人は、最初に処理します。 多くの人々 が発生、順番を待機する行の末尾に移動します。 リスト コレクションのメンバー関数は、`AddTail`と`RemoveHead`を追加するために使用して、head またはリストの末尾から具体的には要素を削除以外の場合はそのため、最も最近追加された要素が削除される最後では常にします。  
  
#### <a name="to-create-a-queue-collection"></a>キューのコレクションを作成するには  
  
1.  Microsoft Foundation Class ライブラリで提供される定義済みリスト クラスのいずれかから新しいリストのクラスを派生し、キュー操作のセマンティクスをサポートするメンバー関数を追加します。  
  
     次の例では、キューの末尾に要素を追加し、キューの先頭から要素を取得するメンバー関数を追加する方法を示します。  
  
     [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]  
  
## <a name="see-also"></a>関連項目  
 [コレクション](../mfc/collections.md)

