---
title: Windows Sockets クラス
ms.date: 11/04/2016
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
ms.openlocfilehash: 3f1b7b2b6674b4a5f8c8f7bff6c5fa239715f459
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445988"
---
# <a name="windows-sockets-classes"></a>Windows Sockets クラス

Windows ソケットは、ネットワークプロトコルに依存しない2台のコンピューター間の通信方法を提供します。 これらのソケットは同期 (プログラムは通信が完了するまで待機します) または非同期 (通信が行われている間はプログラムが実行を継続します) のいずれかになります。

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)<br/>
Windows Sockets API をシンラッパーでカプセル化します。

[CSocket](../mfc/reference/csocket-class.md)<br/>
`CAsyncSocket`から派生した高いレベルの抽象化。 同期的に動作します。

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
Windows ソケットへの `CFile` インターフェイスを提供します。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
