---
title: 'メモリ管理 : ヒープ割り当て'
ms.date: 11/04/2016
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
ms.openlocfilehash: 1f0b07a0a3439faba71078af1e2d7d1559a42b41
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626291"
---
# <a name="memory-management-heap-allocation"></a>メモリ管理 : ヒープ割り当て

ヒープは、プログラムのメモリ割り当てのニーズに合わせて予約されています。 プログラムコードとスタックとは別の領域です。 一般的な C プログラムでは、 **malloc**と**free**の関数を使用して、ヒープメモリの割り当てと割り当て解除を行います。 MFC のデバッグバージョンでは、ヒープメモリ内のオブジェクトの割り当てと割り当て解除を行うために、C++ 組み込み演算子**new**および**delete**の変更バージョンが提供されています。

**Malloc**と**free**の代わりに**new**と**delete**を使用すると、クラスライブラリのメモリ管理デバッグの拡張機能を利用できます。これは、メモリリークの検出に役立ちます。 MFC のリリースバージョンでプログラムをビルドする場合、 **new**および**delete**演算子の標準バージョンによって、メモリの割り当てと割り当て解除を効率的に行うことができます (mfc のリリースバージョンでは、これらの演算子の変更バージョンは提供されません)。

ヒープに割り当てられたオブジェクトの合計サイズは、システムの使用可能な仮想メモリによってのみ制限されることに注意してください。

## <a name="see-also"></a>関連項目

[メモリ管理](memory-management.md)
