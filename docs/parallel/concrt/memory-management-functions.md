---
title: メモリ管理関数
ms.date: 11/04/2016
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
ms.openlocfilehash: 9a7810267c3eaa11ad7592774440365620e7e8f4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276937"
---
# <a name="memory-management-functions"></a>メモリ管理関数

このドキュメントでは、割り当てし、同時実行方式でメモリを解放するために、同時実行ランタイムを提供するメモリ管理関数について説明します。

> [!TIP]
>  コンカレンシー ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 開始するので、タスク スケジューラを使用してアプリケーションのパフォーマンスを微調整する、推奨、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)場合新しい同時実行ランタイムにします。

同時実行ランタイムでは、割り当てと、同時実行方式でメモリのブロックを解放するために最適化された 2 つのメモリ管理関数を提供します。 [Concurrency::alloc](reference/concurrency-namespace-functions.md#alloc)関数は、指定したサイズを使用してメモリ ブロックを割り当てます。 [Concurrency::free](reference/concurrency-namespace-functions.md#free)関数で割り当てられたメモリを解放する`Alloc`します。

> [!NOTE]
>  `Alloc`と`Free`関数は互いに依存します。 使用して、`Free`を使用して割り当てたメモリを解放するためのもの、`Alloc`関数。 また、使用、`Alloc`メモリを割り当て、のみを使用する関数、`Free`そのメモリを解放する関数。

使用して、`Alloc`と`Free`割り当ておよび割り当てのサイズ別のスレッドまたはタスクからの固定セットを解放するときに機能します。 同時実行ランタイムでは、C ランタイム ヒープから割り当てるメモリをキャッシュします。 同時実行ランタイムは、各実行中のスレッドの個別のメモリ キャッシュを保持します。そのため、ランタイムは、ロックまたはメモリ バリアを使用せずにメモリを管理します。 アプリケーションでは、その他のメリットがあります、`Alloc`と`Free`メモリ キャッシュをより頻繁にアクセスするときに機能します。 両方を頻繁に呼び出す、スレッドなど`Alloc`と`Free`メリットよりも主を呼び出すスレッド`Alloc`または`Free`します。

> [!NOTE]
>  これらのメモリ管理関数を使用すると、入力できるは、アプリケーションは大量のメモリ、アプリケーション メモリ不足の状態より早くするよりも期待しています。 1 つのスレッドによってキャッシュされたメモリ ブロックが 1 つのスレッドは、大量のメモリを保持している場合、他のスレッドを利用できないため、そのメモリは使用できません。

## <a name="example"></a>例

使用する例については、`Alloc`と`Free`メモリのパフォーマンスを向上させるために関数を参照してください[方法。割り当てを使用して、およびメモリのパフォーマンスを向上させるためにテープを空き](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)します。

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[方法: Alloc および Free を使用してメモリ パフォーマンスを改善する](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)
