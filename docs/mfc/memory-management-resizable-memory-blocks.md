---
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
ms.openlocfilehash: b048b60a5512ecc54750cb980ca67e2373e2c837
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364773"
---
# <a name="memory-management-resizable-memory-blocks"></a>メモリ管理 : サイズ変更可能なメモリ ブロック

「[メモリ管理: 例](../mfc/memory-management-examples.md)」で説明されている**新しい**演算子と**削除**演算子は、固定サイズのメモリ ブロックとオブジェクトの割り当てと割り当てを解除する場合に適しています。 アプリケーションでサイズ変更可能なメモリ ブロックが必要になる場合があります。 ヒープ上のサイズ変更可能なメモリ ブロックを管理するには、標準の C ランタイム ライブラリ関数[malloc](../c-runtime-library/reference/malloc.md) [、realloc、](../c-runtime-library/reference/realloc.md)[および自由](../c-runtime-library/reference/free.md)なメモリ ブロックを自由に使用する必要があります。

> [!IMPORTANT]
> **新しい**演算子と**削除**演算子を同じメモリ ブロック上でサイズ変更可能なメモリ割り当て関数と混合すると、MFC のデバッグ バージョンでメモリが破損します。 **新しい**. で割り当てられたメモリ ブロックに**realloc**を使用しないでください。 同様に **、new**演算子を使用してメモリ ブロックを割り当てて削除する必要**があります**。 **delete** **malloc**

## <a name="see-also"></a>関連項目

[メモリ管理 : ヒープ割り当て](../mfc/memory-management-heap-allocation.md)
