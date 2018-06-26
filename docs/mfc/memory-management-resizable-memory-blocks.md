---
title: 'メモリ管理: サイズ変更可能なメモリ ブロック |Microsoft ドキュメント'
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
ms.openlocfilehash: ba66fb3d85d716b18486ef08f7f2025e78d6cc57
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929331"
---
# <a name="memory-management-resizable-memory-blocks"></a>メモリ管理 : サイズ変更可能なメモリ ブロック
**新しい**と**削除**演算子、資料に記載[メモリ管理: 例](../mfc/memory-management-examples.md)、割り当てと固定サイズのメモリ ブロックを解放するのに適しているとオブジェクト。 場合によっては、アプリケーションには、サイズ変更可能なメモリ ブロックが必要があります。 標準の C ランタイム ライブラリ関数を使用する必要があります[malloc](../c-runtime-library/reference/malloc.md)、 [realloc](../c-runtime-library/reference/realloc.md)、および[空き](../c-runtime-library/reference/free.md)ヒープのサイズ変更可能なメモリ ブロックを管理します。  
  
> [!IMPORTANT]
>  混合、**新しい**と**削除**同じメモリ ブロックのサイズ変更可能なメモリを割り当てる関数と演算子は、MFC のデバッグ バージョンでメモリの破損になります。 使用しないで**realloc**で割り当てられたメモリ ブロックに**新しい**です。 同様に、割り当てる必要がありますいないメモリ ブロックを**新しい**演算子で、削除して**空き**を使用して、または、**削除**で割り当てられたメモリブロックの演算子**malloc**です。  
  
## <a name="see-also"></a>関連項目  
 [メモリ管理: ヒープ割り当て](../mfc/memory-management-heap-allocation.md)

