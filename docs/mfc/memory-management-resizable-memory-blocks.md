---
title: 'メモリ管理: サイズ変更可能なメモリのブロック |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92582e4255c88b9cc78368a635b27772f2e51a30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443905"
---
# <a name="memory-management-resizable-memory-blocks"></a>メモリ管理 : サイズ変更可能なメモリ ブロック

**新しい**と**削除**演算子は、この記事で説明されている[メモリ管理: 例](../mfc/memory-management-examples.md)、割り当てと固定サイズのメモリ ブロックを解放するのに適しているとオブジェクト。 場合によっては、アプリケーションには、サイズ変更可能なメモリ ブロックが必要があります。 標準の C ランタイム ライブラリ関数を使用する必要があります[malloc](../c-runtime-library/reference/malloc.md)、 [realloc](../c-runtime-library/reference/realloc.md)、および[無料](../c-runtime-library/reference/free.md)ヒープ上のサイズ変更可能なメモリ ブロックを管理します。

> [!IMPORTANT]
>  混合、**新しい**と**削除**MFC のデバッグ バージョンで、破損したメモリ内と同じメモリ ブロックのサイズ変更可能なメモリ割り当て関数と演算子になります。 使用しないようにする**realloc**で割り当てられたメモリ ブロックに**新しい**します。 同様に、割り当てる必要がありますいないメモリ ブロックを**新しい**演算子の削除と**無料**を使用して、または、**削除**で割り当てられたメモリブロックの演算子**malloc**します。

## <a name="see-also"></a>関連項目

[メモリ管理: ヒープ割り当て](../mfc/memory-management-heap-allocation.md)

