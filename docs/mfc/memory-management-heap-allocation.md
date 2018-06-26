---
title: 'メモリ管理: ヒープ割り当て |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7ef166201103b1544d0a36d82452b485af75418
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928610"
---
# <a name="memory-management-heap-allocation"></a>メモリ管理 : ヒープ割り当て
ヒープは、プログラムの必要なメモリ割り当てに予約されています。 これとは別に、プログラム コードおよびスタック領域です。 一般的な C プログラム関数を使用して**malloc**と**空き**割り当てヒープ メモリの割り当てを解除したりします。 MFC のデバッグ バージョンは、C++ の組み込み演算子の改訂版**新しい**と**削除**割り当て、ヒープのメモリ内のオブジェクトを解放します。  
  
 使用すると**新しい**と**削除**の代わりに**malloc**と**空き**、クラス ライブラリの活用するためには、メモリ管理デバッグの強化、メモリ リークを検出するのに便利です。 リリース バージョンの MFC、標準のバージョンを使用してプログラムをビルドすると、**新しい**と**削除**演算子効率的な手段と割り当て解除メモリ (リリース バージョンの MFC提供されませんこれらの演算子の改訂版)。  
  
 ヒープに割り当てられたオブジェクトの合計サイズが、システムの使用可能な仮想メモリによってのみ制限されることに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [メモリ管理](../mfc/memory-management.md)

