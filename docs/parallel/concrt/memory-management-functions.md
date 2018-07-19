---
title: メモリ管理関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0a298c7fb9e50bb17d37224b69ce342c54115d7
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687297"
---
# <a name="memory-management-functions"></a>メモリ管理関数
このドキュメントでは、割り当ておよび同時実行方式でメモリを解放するため、同時実行ランタイムを提供する、メモリ管理関数について説明します。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 始めることをお勧めタスク スケジューラを使用してアプリケーションのパフォーマンスを微調整できますが、ため、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)場合同時実行ランタイムに新しいです。  
  
 同時実行ランタイムでは、割り当ておよび同時実行方式でメモリのブロックを解放するために最適化された 2 つのメモリ管理関数を提供します。 [Concurrency::alloc](reference/concurrency-namespace-functions.md#alloc)関数は、指定したサイズを使用して、メモリ ブロックを割り当てます。 [Concurrency::free](reference/concurrency-namespace-functions.md#free)関数によって割り当てられたメモリを解放する`Alloc`です。  
  
> [!NOTE]
>  `Alloc`と`Free`関数は互いに依存します。 使用して、`Free`を使用して割り当てるメモリを解放するためのもの、`Alloc`関数。 また、使用、`Alloc`メモリを割り当て、のみを使用する関数、`Free`そのメモリを解放します。  
  
 使用して、`Alloc`と`Free`割り当ておよび割り当てサイズ別のスレッドまたはタスクからの固定セットを解放するときに機能します。 同時実行ランタイムでは、メモリを割り当てた C ランタイムのヒープからメモリをキャッシュします。 同時実行ランタイムは、各実行中のスレッドの個別のメモリ キャッシュを保持しています。そのため、ランタイムは、ロックまたはメモリ バリアを使用せずにメモリを管理します。 アプリケーションの利点から、`Alloc`と`Free`メモリ キャッシュをより頻繁にアクセスする場合に機能します。 両方を頻繁に呼び出す、スレッドなど、`Alloc`と`Free`を主に呼び出すスレッドよりも多くの利点があります`Alloc`または`Free`です。  
  
> [!NOTE]
>  これらのメモリ管理関数を使用すると、アプリケーションの使用して大量のメモリ、アプリケーションは入力メモリ不足の状態早くするよりも期待します。 1 つのスレッドによってキャッシュされたメモリ ブロックが 1 つのスレッドは、大量のメモリを保持している場合、他のスレッドを使用できないため、メモリは使用できません。  
  
## <a name="example"></a>例  
 使用する例については、`Alloc`と`Free`メモリ パフォーマンスを向上させるために関数を参照してください[する方法: 使用 Alloc と Free メモリ パフォーマンスを向上させる](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)です。  
  
## <a name="see-also"></a>関連項目  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [方法: Alloc および Free を使用してメモリ パフォーマンスを改善する](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)

