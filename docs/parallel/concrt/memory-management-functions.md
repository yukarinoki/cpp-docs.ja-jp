---
description: 詳細については、「メモリ管理関数」を参照してください。
title: メモリ管理関数
ms.date: 11/04/2016
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
ms.openlocfilehash: d75778f99294c1a177ac204bb0fb96c3ee84422c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205539"
---
# <a name="memory-management-functions"></a>メモリ管理関数

このドキュメントでは、同時実行方式でメモリの割り当てと解放を支援するために同時実行ランタイムに用意されているメモリ管理関数について説明します。

> [!TIP]
> コンカレンシー ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 タスクスケジューラはアプリケーションのパフォーマンスを微調整するのに役立ちます。そのため、同時実行ランタイムを初めて使用する場合は、 [並列パターンライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) または [非同期エージェントライブラリ](../../parallel/concrt/asynchronous-agents-library.md) から始めることをお勧めします。

同時実行ランタイムには、同時にメモリブロックの割り当てと解放を行うために最適化された、2つのメモリ管理関数が用意されています。 [Concurrency:: Alloc](reference/concurrency-namespace-functions.md#alloc)関数は、指定されたサイズを使用してメモリのブロックを割り当てます。 [Concurrency:: Free](reference/concurrency-namespace-functions.md#free)関数は、によって割り当てられたメモリを解放 `Alloc` します。

> [!NOTE]
> `Alloc`関数と `Free` 関数は相互に依存しています。 関数は、 `Free` 関数を使用して割り当てたメモリを解放するためにのみ使用し `Alloc` ます。 また、関数を使用してメモリを割り当てるときは、 `Alloc` 関数のみを使用し `Free` てそのメモリを解放します。

さまざまな `Alloc` `Free` スレッドまたはタスクから固定された割り当てサイズのセットを割り当てて解放するときに、関数と関数を使用します。 同時実行ランタイムは、C ランタイムヒープから割り当てられたメモリをキャッシュします。 同時実行ランタイムは、実行中のスレッドごとに個別のメモリキャッシュを保持します。このため、ランタイムは、ロックやメモリバリアを使用せずにメモリを管理します。 アプリケーションでは、 `Alloc` `Free` メモリキャッシュがより頻繁にアクセスされるときに、および関数の方が優れています。 たとえば、との両方を頻繁に呼び出すスレッドは、 `Alloc` `Free` 主にまたはを呼び出すスレッドよりも多くの利点を持ち `Alloc` `Free` ます。

> [!NOTE]
> これらのメモリ管理機能を使用し、アプリケーションで大量のメモリを使用すると、アプリケーションは、予想よりも早くメモリ不足の状態になる可能性があります。 1つのスレッドによってキャッシュされたメモリブロックは、他のスレッドでは使用できないため、1つのスレッドが大量のメモリを保持している場合、そのメモリは使用できません。

## <a name="example"></a>例

および関数を使用してメモリパフォーマンスを向上させる例につい `Alloc` `Free` ては、「 [方法: Alloc と Free を使用してメモリパフォーマンスを向上](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)させる」を参照してください。

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[方法: Alloc と Free を使用してメモリパフォーマンスを向上させる](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)
