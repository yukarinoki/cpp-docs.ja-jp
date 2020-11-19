---
title: メモリの割り当て
ms.date: 11/18/2020
description: メモリの割り当て、解放、および再割り当てに使用される Microsoft C ランタイム関数の一覧。
f1_keywords:
- c.memory
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.openlocfilehash: 39be48a4ebdf8ee917395d7b743846196200878d
ms.sourcegitcommit: e82e13b80150fcb27a1387018aafb00d99a3827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94920743"
---
# <a name="memory-allocation"></a>メモリ割り当て

これらのルーチンは、メモリの割り当て、解放、および再割り当てを行います。

## <a name="memory-allocation-routines"></a>メモリ割り当てルーチン

|ルーチンによって返される値|用途|
|-------------|---------|
|[`_alloca`](../c-runtime-library/reference/alloca.md), [`_malloca`](../c-runtime-library/reference/malloca.md)|スタックからのメモリの割り当て|
|[`calloc`](../c-runtime-library/reference/calloc.md)|配列を割り当て、その要素を 0 (ゼロ) に初期化します。|
|[`_calloc_dbg`](../c-runtime-library/reference/calloc-dbg.md)|のデバッグバージョン **`calloc`** 。 ランタイムライブラリのデバッグバージョンでのみ使用できます|
|[`operator delete`, `operator delete[]`](../c-runtime-library/delete-operator-crt.md)|ヒープに割り当てられた空きメモリ |
|[`_expand`](../c-runtime-library/reference/expand.md)|メモリブロックを移動せずに拡大または縮小する|
|[`_expand_dbg`](../c-runtime-library/reference/expand-dbg.md)|のデバッグバージョン **`_expand`** 。 ランタイムライブラリのデバッグバージョンでのみ使用できます|
|[`free`](../c-runtime-library/reference/free.md)|ヒープに割り当てられた空きメモリ|
|[`_free_dbg`](../c-runtime-library/reference/free-dbg.md)|のデバッグバージョン **`free`** 。 ランタイムライブラリのデバッグバージョンでのみ使用できます|
|[`_freea`](../c-runtime-library/reference/freea.md)|スタックに割り当てられた空きメモリ|
|[`_get_heap_handle`](../c-runtime-library/reference/get-heap-handle.md)|Win32 `HANDLE` を C ランタイム (CRT) ヒープに取得します。|
|[`_heapadd`](../c-runtime-library/heapadd.md)|ヒープにメモリを追加する|
|[`_heapchk`](../c-runtime-library/reference/heapchk.md)|ヒープの整合性をチェックする|
|[`_heapmin`](../c-runtime-library/reference/heapmin.md)|ヒープ内の未使用のメモリを解放する|
|[`_heapset`](../c-runtime-library/heapset.md)|空きヒープエントリに値を格納する|
|[`_heapwalk`](../c-runtime-library/reference/heapwalk.md)|ヒープ内の各エントリに関する情報を取得します。|
|[`malloc`](../c-runtime-library/reference/malloc.md)|ヒープからのメモリの割り当て|
|[`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md)|のデバッグバージョン **`malloc`** 。ランタイムライブラリのデバッグバージョンでのみ使用できます。|
|[`_msize`](../c-runtime-library/reference/msize.md)|割り当てられたメモリブロックのサイズを返す|
|[`_msize_dbg`](../c-runtime-library/reference/msize-dbg.md)|のデバッグバージョン **`_msize`** 。ランタイムライブラリのデバッグバージョンでのみ使用できます。|
|[`new`, `new[]`](../c-runtime-library/new-operator-crt.md)|ヒープからメモリブロックを割り当てます。|
|[`_query_new_handler`](../c-runtime-library/reference/query-new-handler.md)|によって設定された現在の新しいハンドラールーチンのアドレスを取得します。 **`_set_new_handler`**|
|[`_query_new_mode`](../c-runtime-library/reference/query-new-mode.md)|によって設定された新しいハンドラーモードを取得します。 **`_set_new_mode`****`malloc`**|
|[`realloc`](../c-runtime-library/reference/realloc.md)|ブロックを新しいサイズに再割り当てします。|
|[`_realloc_dbg`](../c-runtime-library/reference/realloc-dbg.md)|のデバッグバージョン **`realloc`** 。ランタイムライブラリのデバッグバージョンでのみ使用できます。|
|[`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md)|演算子がメモリの割り当てに失敗したときにエラー処理機構を有効に **`new`** し、C++ 標準ライブラリのコンパイルを有効にします。|
|[`_set_new_mode`](../c-runtime-library/reference/set-new-mode.md)|の新しいハンドラーモードを設定します。 **`malloc`**|

## <a name="see-also"></a>関連項目

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)