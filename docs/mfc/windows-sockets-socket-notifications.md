---
description: '詳細については、「Windows ソケット: ソケット通知」を参照してください。'
title: 'Windows ソケット : ソケット通知'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
ms.openlocfilehash: 856e954050753545a7ff64d3e111c648dc0284d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207658"
---
# <a name="windows-sockets-socket-notifications"></a>Windows ソケット : ソケット通知

この記事では、ソケットクラスの通知関数について説明します。 これらのメンバー関数は、重要なイベントのソケットオブジェクトを通知するためにフレームワークが呼び出すコールバック関数です。 通知関数は次のとおりです。

- [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive): このソケットに対して、 [Receive](../mfc/reference/casyncsocket-class.md#receive)を呼び出すことによって取得するデータがバッファーに存在することを通知します。

- [Onsend](../mfc/reference/casyncsocket-class.md#onsend): [send](../mfc/reference/casyncsocket-class.md#send)を呼び出すことによってデータを送信できるように、このソケットに通知します。

- [Onaccept](../mfc/reference/casyncsocket-class.md#onaccept): [accept](../mfc/reference/casyncsocket-class.md#accept)を呼び出して、保留中の接続要求を受け入れることができることを、このリッスンソケットに通知します。

- [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect): 接続試行が完了したことをこの接続ソケットに通知します。成功したか、エラーが発生した可能性があります。

- [OnClose](../mfc/reference/casyncsocket-class.md#onclose): 接続されているソケットが閉じていることをこのソケットに通知します。

    > [!NOTE]
    >  追加の通知関数は [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata)です。 この通知は、送信ソケットが送信する "帯域外" データを持っていることを受信ソケットに伝えます。 帯域外データは、接続されたストリームソケットの各ペアに関連付けられた論理的に独立したチャネルです。 帯域外チャネルは、通常、"緊急" データを送信するために使用されます。 MFC では、帯域外データをサポートしています。 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)クラスを操作する上級ユーザーは、帯域外チャネルを使用する必要がある場合がありますが、クラスを使用しない[ことをお](../mfc/reference/csocket-class.md)勧めします。 より簡単な方法は、このようなデータを渡すための2番目のソケットを作成することです。 帯域外データの詳細については、Windows SDK で使用可能な Windows ソケット仕様を参照してください。

クラスから派生する場合は `CAsyncSocket` 、アプリケーションにとって重要なネットワークイベントの通知関数をオーバーライドする必要があります。 クラスからクラスを派生させる場合 `CSocket` は、対象の通知関数をオーバーライドするかどうかを選択します。 また、それ自体を使用することもでき `CSocket` ます。この場合、通知関数は既定で何も実行しません。

これらの関数は、オーバーライド可能なコールバック関数です。 `CAsyncSocket` また、 `CSocket` メッセージを通知に変換しますが、使用する場合は、通知関数の応答方法を実装する必要があります。 通知関数は、読み取られるデータの存在など、目的のイベントがソケットに通知されたときに呼び出されます。

MFC は通知関数を呼び出して、通知時にソケットの動作をカスタマイズできるようにします。 たとえば、通知関数からを呼び出すことができ `Receive` `OnReceive` ます。つまり、データが読み込まれたことが通知されたときに、を呼び出して読み取ることができ `Receive` ます。 この方法は必要ありませんが、有効なシナリオです。 別の方法として、通知関数を使用して、進行状況の追跡、 **トレース** メッセージの出力などを行うこともできます。

これらの通知を利用するには、派生ソケットクラスで通知関数をオーバーライドし、実装を提供します。

データの受信や送信などの操作では、 `CSocket` オブジェクトが同期されます。 同期状態では、他のソケットに対する通知はキューに登録され、現在のソケットは必要な通知を待機しています。 (たとえば、呼び出し中に、 `Receive` ソケットが通知を読み取るように要求します)。ソケットが同期操作を完了し、再び非同期になると、他のソケットがキューに置かれた通知の受信を開始できるようになります。

> [!NOTE]
> で `CSocket` は、 `OnConnect` 通知関数は呼び出されません。 接続の場合、を呼び出すと `Connect` 、接続が完了したとき (正常にまたはエラーが発生した場合) にが返されます。 接続通知の処理方法は、MFC 実装の詳細です。

各通知関数の詳細については、 `CAsyncSocket` *MFC リファレンス* の「クラス」の関数を参照してください。 ソースコードと MFC サンプルに関する情報については、「 [Mfc サンプル](../overview/visual-cpp-samples.md#mfc-samples)」を参照してください。

詳細については、次を参照してください。

- [Windows ソケット: CAsyncSocket クラスの使用](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット: ソケットクラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows ソケット: アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows ソケット:ブロッキング](../mfc/windows-sockets-blocking.md)

- [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)

- [Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)
