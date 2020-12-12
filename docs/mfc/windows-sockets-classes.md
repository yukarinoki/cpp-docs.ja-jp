---
description: '詳細情報: Windows Sockets クラス'
title: Windows Sockets クラス
ms.date: 11/04/2016
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
ms.openlocfilehash: 03d8ddae0bb511e52b0ea7ed2b3754184ed6ebc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118642"
---
# <a name="windows-sockets-classes"></a>Windows Sockets クラス

Windows ソケットは、ネットワークプロトコルに依存しない2台のコンピューター間の通信方法を提供します。 これらのソケットは同期 (プログラムは通信が完了するまで待機します) または非同期 (通信が行われている間はプログラムが実行を継続します) のいずれかになります。

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)<br/>
Windows Sockets API をシンラッパーでカプセル化します。

[CSocket](../mfc/reference/csocket-class.md)<br/>
から派生した、より高いレベルの抽象化 `CAsyncSocket` 。 同期的に動作します。

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
`CFile`Windows ソケットへのインターフェイスを提供します。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)
