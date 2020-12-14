---
description: '詳細については、「メモリ管理: サイズ変更可能なメモリブロック」を参照してください。'
title: 'メモリ管理 : サイズ変更可能なメモリ ブロック'
ms.date: 11/04/2016
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
ms.openlocfilehash: bcca5617a0d59a7dd5c6a1f9c9f82cb5876f1ef5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248880"
---
# <a name="memory-management-resizable-memory-blocks"></a>メモリ管理 : サイズ変更可能なメモリ ブロック

**`new`** **`delete`** 「[メモリ管理: 例](memory-management-examples.md)」で説明されているおよび演算子は、固定サイズのメモリブロックおよびオブジェクトの割り当てと割り当て解除に適しています。 場合によっては、アプリケーションでサイズ変更可能なメモリブロックが必要になることがあります。 ヒープ上のサイズ変更可能なメモリブロックを管理するには、標準の C ランタイムライブラリ関数 [malloc](../c-runtime-library/reference/malloc.md)、 [realloc](../c-runtime-library/reference/realloc.md)、および [free](../c-runtime-library/reference/free.md) を使用する必要があります。

> [!IMPORTANT]
> **`new`** および演算子と、 **`delete`** サイズ変更可能なメモリ割り当て関数を同じメモリブロックに混在させると、MFC のデバッグバージョンではメモリが破損します。 で割り当てられたメモリブロックで **realloc** を使用しないでください **`new`** 。 同様に、演算子にメモリブロックを割り当てて、 **`new`** それを **free** で削除したり、 **`delete`** **malloc** で割り当てられたメモリのブロックに対して演算子を使用したりしないでください。

## <a name="see-also"></a>関連項目

[メモリ管理: ヒープ割り当て](memory-management-heap-allocation.md)
