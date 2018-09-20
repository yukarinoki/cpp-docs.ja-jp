---
title: 'メモリ管理: ヒープの割り当て |Microsoft Docs'
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
ms.openlocfilehash: cc158ceda21bfb04053bbc490a3333a76e2d7afe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383819"
---
# <a name="memory-management-heap-allocation"></a>メモリ管理 : ヒープ割り当て

ヒープは、プログラムの必要なメモリ割り当てに予約されています。 プログラム コードとスタックとは別の領域になります。 C プログラムの一般的な関数を使用して**malloc**と**無料**を割り当てたり、ヒープ メモリの割り当てを解除します。 MFC のデバッグ バージョンは、C++ 組み込み演算子の変更バージョンを提供します。**新しい**と**削除**を割り当てたり、ヒープのメモリ内のオブジェクトの割り当てを解除します。

使用すると**新しい**と**削除**の代わりに**malloc**と**無料**、クラス ライブラリの活用するためには、メモリ管理デバッグの強化、メモリ リークを検出するのに便利です。 MFC では、標準のバージョンのリリース バージョンでプログラムをビルドするときに、**新しい**と**削除**演算子によって、効率的に割り当てるし、(リリース バージョンの MFC のメモリの割り当てを解除するには提供されませんこれらの演算子の変更のバージョン)。

ヒープに割り当てられたオブジェクトの合計サイズが、システムの使用可能な仮想メモリによってのみ制限されることに注意してください。

## <a name="see-also"></a>関連項目

[メモリ管理](../mfc/memory-management.md)

