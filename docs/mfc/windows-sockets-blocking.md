---
title: 'Windows ソケット: ブロッキング |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 400114e557632c9a1dd11cc2f9ec5b3101eb8c37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385951"
---
# <a name="windows-sockets-blocking"></a>Windows ソケット : ブロッキング
この記事の内容と 2 部構成の記事は、Windows ソケット プログラミングのいくつかの問題を説明します。 この記事では、ブロックについて説明します。 その他の問題については、技術情報: [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)と[Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)です。  
  
 使用するか、またはクラスから派生させる場合[CAsyncSocket](../mfc/reference/casyncsocket-class.md)、これらの問題を管理する必要があります。 使用するか、またはクラスから派生させる場合[CSocket](../mfc/reference/csocket-class.md)MFC では、それらを管理します。  
  
## <a name="blocking"></a>ブロック  
 ソケットが「ブロック モード」または「非ブロッキング モードです」であることができます。 ブロックしている (または同期) モードで、ソケットの関数では、そのアクションを完了するまでは返されません。 これは、関数が呼び出されたソケットは何もできないためにのブロックと呼びます — がブロックされている — 呼び出しが戻るまでです。 呼び出し、**受信**メンバー関数は、たとえば、時間がかかること、任意の長さ、送信元のアプリケーションを送信するまで待機するように完了した (使用するかどうかは、この`CSocket`、またはを使用して`CAsyncSocket`ブロックと)。 場合、`CAsyncSocket`オブジェクトは非ブロッキング動作モードが (非同期的に)、呼び出しを直ちに返しますおよび取得することで、現在エラー コード、 [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror)メンバー関数は、 **WSAEWOULDBLOCK**、モードのためすぐに返されませんが、呼び出しがブロックされていることを示す必要があります。 (`CSocket`返さない**WSAEWOULDBLOCK**です。 クラスは、管理するためにブロックされます。)  
  
 ソケットの動作は 32 ビットおよび 64 ビット オペレーティング システム (Windows 95 や Windows 98) よりも 16 ビット オペレーティング システム (Windows 3.1) などで異なります。 16 ビットのオペレーティング システムとは異なり、32 ビットおよび 64 ビット オペレーティング システムはプリエンプティブ マルチタスクを使用およびマルチ スレッド処理を提供します。 32 ビットおよび 64 ビットのオペレーティング システムでは、個別のワーカー スレッドで、ソケットを収容できます。 ブロックにコンピューティング時間を費やすことがなく、アプリケーションの他のアクティビティを妨げることがなく、スレッドのソケットをブロックできます。 マルチ スレッド プログラミング方法については、記事を参照してください。[マルチ スレッド](../parallel/multithreading-support-for-older-code-visual-cpp.md)です。  
  
> [!NOTE]
>  ブロッキング特性を使用するマルチ スレッド アプリケーションで、`CSocket`をユーザー インターフェイスの応答性に影響を与えずに、プログラムのデザインを簡素化します。 メイン スレッドでのユーザーの操作を処理することによって、`CSocket`代替スレッドで処理、これらの各論理操作を分離することができます。 アプリケーションはマルチ スレッドでは、これら 2 つのアクティビティを結合し、つまり通常を使用して 1 つのスレッドとして処理する必要があります`CAsyncSocket`要求時、またはオーバーライドする通信要求を処理できるように`CSocket::OnMessagePending`ユーザー アクションを処理するにはスレッドでします。  
  
 このディスカッションの残りの部分は、16 ビットのオペレーティング システムを対象とするプログラマにとっては。  
  
 通常、使用している場合`CAsyncSocket`、ブロッキング操作を使用しないでくださいして代わりに非同期的に動作する必要があります。 受信するポイントからの非同期操作で、 **WSAEWOULDBLOCK**呼び出した後のエラー コード**受信**、まで待機するなど、`OnReceive`に通知するメンバー関数が呼び出されますもう一度読み取ることができるします。 非同期呼び出しがソケットの適切なコールバックの通知関数をなど、呼び出すことで行われる[OnReceive](../mfc/reference/casyncsocket-class.md#onreceive)です。  
  
 Windows の場合、ブロッキング呼び出しが良くないと見なされます。 既定では、 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)サポートする非同期呼び出し、およびするコールバック通知を使用して自分でブロッキングを管理する必要があります。 クラス[CSocket](../mfc/reference/csocket-class.md)、その一方は同期型です。 Windows メッセージをポンプし、管理するためにブロックします。  
  
 ブロックの詳細については、Windows ソケット仕様を参照してください。 "On"機能に関する詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../mfc/windows-sockets-socket-notifications.md)と[Windows ソケット: ソケット クラスから派生する](../mfc/windows-sockets-deriving-from-socket-classes.md)です。  
  
 詳細については次を参照してください:  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: 予備知識](../mfc/windows-sockets-background.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)

