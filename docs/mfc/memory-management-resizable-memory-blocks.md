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
ms.openlocfilehash: 74ae94146b1ec711b586ea1fecbbc89a47b40b5e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626280"
---
# <a name="memory-management-resizable-memory-blocks"></a>メモリ管理 : サイズ変更可能なメモリ ブロック

「[メモリ管理: 例](memory-management-examples.md)」で説明されている**new**および**delete**演算子は、固定サイズのメモリブロックおよびオブジェクトの割り当てと割り当て解除に適しています。 場合によっては、アプリケーションでサイズ変更可能なメモリブロックが必要になることがあります。 ヒープ上のサイズ変更可能なメモリブロックを管理するには、標準の C ランタイムライブラリ関数[malloc](../c-runtime-library/reference/malloc.md)、 [realloc](../c-runtime-library/reference/realloc.md)、および[free](../c-runtime-library/reference/free.md)を使用する必要があります。

> [!IMPORTANT]
> **新しい**演算子と**delete**演算子を同じメモリブロックでサイズ変更可能なメモリ割り当て関数と混在させると、MFC のデバッグバージョンではメモリが破損します。 **New**で割り当てられたメモリブロックで**realloc**を使用しないでください。 同様に、 **new**演算子を使用してメモリブロックを割り当てて**free**を使用して削除したり、 **malloc**で割り当てられたメモリブロックに**delete**演算子を使用したりしないでください。

## <a name="see-also"></a>関連項目

[メモリ管理 : ヒープ割り当て](memory-management-heap-allocation.md)
