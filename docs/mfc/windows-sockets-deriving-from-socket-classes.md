---
description: '詳細については、「Windows ソケット: ソケットクラスからの派生」を参照してください。'
title: 'Windows ソケット : ソケット クラスからの派生'
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
ms.openlocfilehash: ba3526ddde4d254ff044fa09588d7764b16fb719
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132965"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows ソケット : ソケット クラスからの派生

この記事では、いずれかのソケットクラスから独自のクラスを派生させることによって得られる機能の一部について説明します。

独自の機能を追加するために、 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) または [CSocket](../mfc/reference/csocket-class.md) から独自のソケットクラスを派生させることができます。 特に、これらのクラスには、オーバーライドできるいくつかの仮想メンバー関数が用意されています。 これらの関数には、 [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive)、 [onsend](../mfc/reference/casyncsocket-class.md#onsend)、 [onsend](../mfc/reference/casyncsocket-class.md#onaccept)、 [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect)、および [OnClose](../mfc/reference/casyncsocket-class.md#onclose)が含まれます。 派生ソケットクラスの関数をオーバーライドすると、ネットワークイベントが発生したときに提供される通知を利用できます。 フレームワークは、これらの通知コールバック関数を呼び出して、読み取りを開始できるデータの受信など、重要なソケットイベントを通知します。 通知関数の詳細については、「 [Windows ソケット: ソケット通知](../mfc/windows-sockets-socket-notifications.md)」を参照してください。

さらに、クラスは、 `CSocket` [Onmessagepending](../mfc/reference/csocket-class.md#onmessagepending) メンバー関数 (高度なオーバーライド可能) を提供します。 MFC は、ソケットが Windows ベースのメッセージをポンプしている間、この関数を呼び出します。 をオーバーライドし `OnMessagePending` て、Windows から特定のメッセージを検索し、それに応答することができます。

クラスに指定されたの既定のバージョンは、 `OnMessagePending` `CSocket` ブロック呼び出しの完了を待機している間に WM_PAINT メッセージのメッセージキューを調べます。 描画メッセージをディスパッチして、表示品質を向上させます。 役に立つこと以外にも、関数を自分でオーバーライドできる1つの方法を示しています。 別の例として、 `OnMessagePending` 次のタスクにを使用することを検討してください。 ネットワークトランザクションの完了を待機している間に、モードレスダイアログボックスを表示したとします。 ダイアログボックスには [キャンセル] ボタンがあり、ユーザーはこのボタンを使用して、時間がかかりすぎるブロックしているトランザクションを取り消すことができます。 上書きによって、 `OnMessagePending` このモードレスダイアログボックスに関連するメッセージがポンプされる場合があります。

オーバーライドで `OnMessagePending` 、 **TRUE** を返すか、またはの基本クラスバージョンの呼び出しからを返し `OnMessagePending` ます。 実行する必要がある作業を実行する場合は、基本クラスのバージョンを呼び出します。

詳細については、次を参照してください。

- [Windows ソケット: アーカイブでのソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows ソケット: CAsyncSocket クラスの使用](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット:ブロッキング](../mfc/windows-sockets-blocking.md)

- [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)

- [Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)
