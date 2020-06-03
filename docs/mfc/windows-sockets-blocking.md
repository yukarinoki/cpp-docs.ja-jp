---
title: 'Windows ソケット : ブロッキング'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
ms.openlocfilehash: 87d4f0eb57f9e26dbf73da06b5d7ca6d61d6c174
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359993"
---
# <a name="windows-sockets-blocking"></a>Windows ソケット : ブロッキング

この資料と 2 つの関連資料では、Windows ソケットプログラミングのいくつかの問題について説明します。 この記事では、ブロッキングについて説明します。 その他の問題については[、「Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)と[Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)」の記事で説明します。

クラス[CAsyncSocket](../mfc/reference/casyncsocket-class.md)を使用するか、クラスから派生する場合は、これらの問題を自分で管理する必要があります。 CSocket クラスを使用するか[CSocket](../mfc/reference/csocket-class.md)、クラスから派生する場合、MFC によってそれらのクラスが管理されます。

## <a name="blocking"></a>ブロッキング

ソケットは「ブロッキングモード」または「非ブロッキングモード」にすることができます。 ブロッキング (または同期) モードのソケットの関数は、アクションを完了するまで戻りません。 これは、関数が呼び出されたソケットが呼び出しを戻すまでブロックされないため、ブロッキングと呼ばれます。 たとえば、メンバー関数`Receive`の呼び出しは、送信側アプリケーションの送信を待機する間、任意に長い時間を要することがあります (これは、を使用している場合、`CSocket`またはブロッキングを`CAsyncSocket`使用している場合です)。 `CAsyncSocket`オブジェクトが (非同期に動作する) 非ブロック モードの場合、呼び出しはすぐに返され、現在のエラー コードは[、GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror)メンバー関数で取得可能な**WSAEWOULDBLOCK**です。 (`CSocket` **WSAEWOULDBLOCK を**返すことはありません 。 クラスは、ブロッキングを管理します。

ソケットの動作は、32 ビットおよび 64 ビット オペレーティング システム (Windows 95 や Windows 98 など) では、16 ビット オペレーティング システム (Windows 3.1 など) の場合とは異なります。 16 ビットのオペレーティング システムとは異なり、32 ビットおよび 64 ビットオペレーティング システムではプリエンプティブ マルチタスキングが使用され、マルチスレッドが提供されます。 32 ビットおよび 64 ビットのオペレーティング システムでは、ソケットを別々のワーカー スレッドに配置できます。 スレッド内のソケットは、アプリケーション内の他のアクティビティーに干渉することなく、ブロックにコンピューティング時間を費やすことなくブロックできます。 マルチスレッド プログラミングの詳細については、[マルチスレッド](../parallel/multithreading-support-for-older-code-visual-cpp.md)の記事を参照してください。

> [!NOTE]
> マルチスレッド アプリケーションでは、ブロックの性質`CSocket`を使用して、ユーザー インターフェイスの応答性に影響を与えることなく、プログラムの設計を簡略化できます。 メイン スレッドでのユーザー操作を処理し、`CSocket`代替スレッドで処理することで、これらの論理操作を分離できます。 マルチスレッドではないアプリケーションでは、これらの 2 つのアクティビティーを単一スレッド`CAsyncSocket``CSocket::OnMessagePending`として組み合わせて処理する必要があります。

この説明の残りの部分は、16 ビット オペレーティング システムを対象とするプログラマ向けです。

通常、 を使用`CAsyncSocket`している場合は、ブロッキング操作を使用せずに、代わりに非同期に操作する必要があります。 非同期操作では、呼び出し`Receive`後に**WSAEWOULDBLOCK**エラー・コードを受け取る時点から、例`OnReceive`えば、メンバー関数が呼び出されるまで待って、再び読み取ることができることを通知します。 非同期呼び出しは、ソケットの適切なコールバック通知関数[(OnReceive](../mfc/reference/casyncsocket-class.md#onreceive)など) を呼び戻すことによって行われます。

Windows では、ブロッキング呼び出しは不適切な方法と見なされます。 既定では[、CAsyncSocket](../mfc/reference/casyncsocket-class.md)は非同期呼び出しをサポートしており、コールバック通知を使用してブロッキングを自分で管理する必要があります。 一方、クラス[CSocket](../mfc/reference/csocket-class.md)は同期です。 Windows メッセージを送り込み、ブロックを管理します。

ブロックの詳細については、Windows ソケットの仕様を参照してください。 "オン" 関数の詳細については、「 [Windows ソケット : ソケット通知](../mfc/windows-sockets-socket-notifications.md)と[Windows ソケット : ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)」を参照してください。

詳細については、次を参照してください。

- [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows ソケット : 予備知識](../mfc/windows-sockets-background.md)

- [Windows ソケット : ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット : データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[同期ソケット::オンセンド](../mfc/reference/casyncsocket-class.md#onsend)
