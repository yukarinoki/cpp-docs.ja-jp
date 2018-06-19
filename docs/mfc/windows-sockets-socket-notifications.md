---
title: 'Windows ソケット: ソケット通知 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b51bf2b562f0d4eff5b9cfef557e62f996d53470
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385581"
---
# <a name="windows-sockets-socket-notifications"></a>Windows ソケット : ソケット通知
この記事では、ソケット クラス内の通知関数について説明します。 これらのメンバー関数は、重要なイベントのソケット オブジェクトに通知するフレームワークから呼び出されるコールバック関数です。 通知機能は次のとおりです。  
  
-   [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive): このソケットを呼び出して取得するためのバッファーにデータがあることを通知[受信](../mfc/reference/casyncsocket-class.md#receive)です。  
  
-   [OnSend](../mfc/reference/casyncsocket-class.md#onsend): このソケット呼び出してデータを送信できるようになりましたことを通知[送信](../mfc/reference/casyncsocket-class.md#send)です。  
  
-   [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept): に受け入れることができる保留中の接続要求を呼び出してこのリッスン ソケットに通知[Accept](../mfc/reference/casyncsocket-class.md#accept)です。  
  
-   [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect): その接続の試行が完了しているソケットに通知: おそらく正常完了またはエラーが発生します。  
  
-   [OnClose](../mfc/reference/casyncsocket-class.md#onclose): に接続されているソケットが閉じられてこのソケットに通知します。  
  
    > [!NOTE]
    >  その他の通知機能は、 [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata)です。 この通知は、送信側のソケットに送信する「帯域外」データを受信側のソケットに指示します。 帯域外のデータは、論理的に独立した接続されているストリーム ソケットの各ペアに関連付けられているチャネルです。 帯域外のチャネルは通常、「緊急」データの送信に使用されます。 MFC では、帯域外のデータをサポートします。 上級ユーザーのクラスで操作して[CAsyncSocket](../mfc/reference/casyncsocket-class.md)クラスのユーザーが帯域外のチャネルを使用する必要があります[CSocket](../mfc/reference/csocket-class.md)使用することから推奨されていません。 簡単な方法では、このようなデータを渡すための 2 番目のソケットを作成します。 帯域外のデータの詳細については、Windows SDK で使用できる Windows ソケット仕様を参照してください。  
  
 クラスから派生した場合`CAsyncSocket`、ネットワーク、アプリケーションに関心のあるイベントの通知関数をオーバーライドする必要があります。 クラスからクラスを派生する場合`CSocket`には、選択対象の通知関数をオーバーライドするかどうか。 使用することも`CSocket`自体、後者通知機能は何の既定値は。  
  
 これらの関数は、オーバーライド可能なコールバック関数です。 `CAsyncSocket` および`CSocket`に通知をメッセージの変換が、それらを使用する場合に、応答に対して、通知で実行される関数を実装する必要があります。 通知機能は、ソケットが読み取られるデータが存在するなど、目的のイベントの通知時に呼び出されます。  
  
 MFC が通知される時に、ソケットの動作をカスタマイズするために通知関数を呼び出します。 たとえば、呼び出すことができます**受信**から、`OnReceive`通知関数が通知を受け取ることを読み取るデータが、呼び出す**受信**を読むことです。 この方法は、必要ではありませんが、有効なシナリオです。 代わりにの進行状況を追跡するために、通知関数を使用する場合があります印刷**トレース**メッセージ、およびなどです。  
  
 ソケットの派生クラスでの通知関数をオーバーライドして、実装を提供することによってこれらの通知の利点がかかります。  
  
 受信データの送信などの操作中に、`CSocket`オブジェクトが同期状態になります。 同期の状態では、他のソケットのことを意図した任意の通知は、現在のソケットが必要がある通知を待っている間にキューイングされます。 (たとえば中、**受信**呼び出し、ソケットは、通知を読み取る)。ソケットが、同期操作を完了し、非同期状態に戻ると、他のソケットはキューに置かれた通知の受信を開始できます。  
  
> [!NOTE]
>  `CSocket`、`OnConnect`通知関数が呼び出されることはありません。 接続を呼び出す**接続**、(正常またはエラー)、接続が完了したときにこれが返されます。 MFC 実装の詳細は、接続の通知の処理方法。  
  
 詳細については、通知の各関数は、クラスの関数を参照してください。`CAsyncSocket`で、 *『 MFC リファレンス*です。 ソース コードと MFC のサンプルについては、「 [MFC サンプル](../visual-cpp-samples.md)です。  
  
 詳細については次を参照してください:  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md)  
  
-   [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)

