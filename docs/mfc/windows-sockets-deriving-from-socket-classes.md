---
title: 'Windows ソケット: ソケット クラスからの派生 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64fb9a3ff1c27aade9f74a8ed95a8016829874ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows ソケット : ソケット クラスからの派生
この記事では、いくつかのいずれかのソケット クラスから独自のクラスを派生させることによって利用できる機能について説明します。  
  
 ソケット クラスは、いずれかから派生できます[CAsyncSocket](../mfc/reference/casyncsocket-class.md)または[CSocket](../mfc/reference/csocket-class.md)独自の機能を追加します。 具体的には、これらのクラスは、オーバーライドできる仮想メンバー関数の数を指定します。 これらの関数を含める[OnReceive](../mfc/reference/casyncsocket-class.md#onreceive)、 [OnSend](../mfc/reference/casyncsocket-class.md#onsend)、 [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept)、 [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect)、および[OnClose](../mfc/reference/casyncsocket-class.md#onclose)です。 関数は、ネットワーク イベントの発生時に提供する通知を活用するために、ソケットの派生クラスでオーバーライドできます。 フレームワークは、通知するようにデータの受信などの重要なソケットのイベントの読み取りを開始することができますのこれらの通知のコールバック関数を呼び出します。 通知の関数の詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../mfc/windows-sockets-socket-notifications.md)です。  
  
 さらに、クラス`CSocket`提供、 [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending)メンバー関数は、(高度なオーバーライド可能)。 MFC は、ソケットは、Windows ベースのメッセージをポンプ中に、この関数を呼び出します。 オーバーライドできます`OnMessagePending`を Windows からの特定のメッセージを確認し、それらに応答します。  
  
 既定のバージョン`OnMessagePending`クラスで提供される`CSocket`用のメッセージ キューを調べて`WM_PAINT`ブロッキング呼び出しが完了の待機中にメッセージ。 表示品質を向上させるために描画メッセージをディスパッチします。 別に便利な操作を行うには、この方法について説明、関数をオーバーライドする可能性があります自分でします。 別の例としては、使用を検討して`OnMessagePending`次のタスクのです。 たとえば、ネットワーク トランザクションの完了を待っている間に、モードレス ダイアログ ボックスを表示します。 ダイアログ ボックスには、ユーザーは、時間がかかりすぎるブロックしているトランザクションのキャンセルに使用できる [キャンセル] ボタンが含まれています。 `OnMessagePending`オーバーライドがこのモードレス ダイアログ ボックスに関連するメッセージをポンプ可能性があります。  
  
 `OnMessagePending`上書き、いずれかを返す**TRUE**またはの基本クラスのバージョンへの呼び出しから返される`OnMessagePending`です。 実行する必要のある作業を実行する場合は、基本クラスのバージョンを呼び出します。  
  
 詳細については次を参照してください:  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md)  
  
-   [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)

