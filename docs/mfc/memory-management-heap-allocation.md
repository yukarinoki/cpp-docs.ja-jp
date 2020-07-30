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
ms.openlocfilehash: ecf60fbdd11f540d12c1bfab047bbb80a3cb83e8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228597"
---
# <a name="memory-management-heap-allocation"></a>メモリ管理 : ヒープ割り当て

ヒープは、プログラムのメモリ割り当てのニーズに合わせて予約されています。 プログラムコードとスタックとは別の領域です。 一般的な C プログラムでは、 **malloc**と**free**の関数を使用して、ヒープメモリの割り当てと割り当て解除を行います。 MFC のデバッグバージョンは、C++ 組み込み演算子の変更バージョンを提供 **`new`** し、 **`delete`** ヒープメモリ内のオブジェクトの割り当てと割り当て解除を行います。

**`new`** **`delete`** **Malloc**と**free**の代わりにとを使用すると、クラスライブラリのメモリ管理デバッグの拡張機能を利用できます。これは、メモリリークの検出に役立ちます。 リリースバージョンの MFC を使用してプログラムをビルドする場合、および演算子の標準バージョンでは、 **`new`** **`delete`** メモリの割り当てと割り当て解除を効率的に行うことができます (Mfc のリリースバージョンでは、これらの演算子の変更バージョンは提供されません)。

ヒープに割り当てられたオブジェクトの合計サイズは、システムの使用可能な仮想メモリによってのみ制限されることに注意してください。

## <a name="see-also"></a>関連項目

[メモリ管理](memory-management.md)
