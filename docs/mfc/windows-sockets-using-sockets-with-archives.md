---
description: '詳細については、「Windows ソケット: アーカイブでのソケットの使用」を参照してください。'
title: 'Windows ソケット: アーカイブ付きソケットの使用'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
ms.openlocfilehash: bd5f239a0fdcee4bf6c6141994c4ca5002bdc6b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331336"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows ソケット: アーカイブ付きソケットの使用

この記事では、 [CSocket プログラミングモデル](#_core_the_csocket_programming_model)について説明します。 クラスの [CSocket](../mfc/reference/csocket-class.md) は、 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)クラスよりも高いレベルの抽象化でソケットのサポートを提供します。 `CSocket` mfc シリアル化プロトコルのバージョンを使用して、MFC の [CArchive](../mfc/reference/carchive-class.md) オブジェクトを介してソケットオブジェクトとの間でデータをやり取りします。 `CSocket` は、Windows メッセージのバックグラウンド処理を管理すると同時に、にアクセスできるようにし `CArchive` ます。これにより、未加工の API またはクラスを使用して自分で行う必要がある通信の多くの側面が管理され `CAsyncSocket` ます。

> [!TIP]
> クラスは、 `CSocket` の便利なバージョンとして単独で使用でき `CAsyncSocket` ますが、最も単純なプログラミングモデルはオブジェクトで使用することです `CSocket` `CArchive` 。

アーカイブ付きソケットの実装のしくみの詳細については、「 [Windows ソケット: アーカイブ付きソケットの動作方法](../mfc/windows-sockets-how-sockets-with-archives-work.md)」を参照してください。 コード例については、「 [Windows ソケット: 操作のシーケンス](../mfc/windows-sockets-sequence-of-operations.md) 」と「 [Windows ソケット: アーカイブを使用したソケットの例](../mfc/windows-sockets-example-of-sockets-using-archives.md)」を参照してください。 ソケットクラスから独自のクラスを派生させることによって得られる機能の一部については、「 [Windows ソケット: ソケットクラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)」を参照してください。

> [!NOTE]
> 確立された (非 MFC) サーバーと通信するように MFC クライアントプログラムを作成している場合は、アーカイブを通じて C++ オブジェクトを送信しないでください。 サーバーが、送信するオブジェクトの種類を認識する MFC アプリケーションでない限り、オブジェクトを受信したり、逆シリアル化したりすることはできません。 MFC 以外のアプリケーションとの通信に関する関連資料については、「 [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)」を参照してください。

## <a name="the-csocket-programming-model"></a><a name="_core_the_csocket_programming_model"></a> CSocket プログラミングモデル

オブジェクトを使用するには `CSocket` 、複数の MFC クラスオブジェクトを作成して関連付ける必要があります。 以下の一般的な手順では、各手順はサーバーソケットとクライアントソケットの両方で実行されます。ただし、手順3では、各ソケットの種類に異なるアクションが必要です。

> [!TIP]
> サーバーアプリケーションは、実行時に、通常は最初に準備が完了し、クライアントアプリケーションが接続をシークしたときに "待機中" になります。 クライアントが接続しようとしたときにサーバーの準備ができていない場合は、通常、後で接続を再試行するためにユーザーアプリケーションが必要になります。

#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>サーバーソケットとクライアントソケット間の通信を設定するには

1. [CSocket](../mfc/reference/csocket-class.md)オブジェクトを構築します。

1. オブジェクトを使用して、基になる **ソケット** ハンドルを作成します。

   クライアントオブジェクトの場合、 `CSocket` データグラムソケットが必要でない限り、通常は既定のパラメーターを使用してを [作成](../mfc/reference/casyncsocket-class.md#create)する必要があります。 サーバーオブジェクトの場合は `CSocket` 、呼び出しでポートを指定する必要があり `Create` ます。

    > [!NOTE]
    >  `CArchive` は、データグラムソケットでは機能しません。 をデータグラムソケットに対して使用する場合は、アーカイブを使用するのではなく、使用するクラスを使用する `CSocket` 必要があり `CAsyncSocket` ます。 データグラムは信頼できない (到着することは保証されず、繰り返しまたは順序が切れている可能性があります) ため、アーカイブによるシリアル化との互換性がありません。 シリアル化操作が確実かつ順番に完了することを期待しています。 をオブジェクトと共にデータグラムに対して使用しようとすると `CSocket` `CArchive` 、MFC アサーションは失敗します。

1. ソケットがクライアントの場合は、 [CAsyncSocket:: connect](../mfc/reference/casyncsocket-class.md#connect) を呼び出して、ソケットオブジェクトをサーバーソケットに接続します。

     または

   ソケットがサーバーの場合は、 [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen) を呼び出して、クライアントからの接続試行のリッスンを開始します。 接続要求を受信したら、 [CAsyncSocket:: accept](../mfc/reference/casyncsocket-class.md#accept)を呼び出してそれを受け入れます。

    > [!NOTE]
    >  この `Accept` メンバー関数は、新しい空のオブジェクトへの参照を `CSocket` そのパラメーターとして受け取ります。 を呼び出す前に、このオブジェクトを作成する必要があり `Accept` ます。 このソケットオブジェクトがスコープ外に出ると、接続は閉じられます。 `Create`この新しいソケットオブジェクトに対してを呼び出さないでください。

1. [CSocketFile](../mfc/reference/csocketfile-class.md)オブジェクトを作成し、オブジェクトを関連付け `CSocket` ます。

1. データの読み込み (受信) または格納 (送信) のために、 [CArchive](../mfc/reference/carchive-class.md) オブジェクトを作成します。 アーカイブは、オブジェクトに関連付けられてい `CSocketFile` ます。

   `CArchive`はデータグラムソケットでは動作しないことに注意してください。

1. オブジェクトを使用して、 `CArchive` クライアントとサーバーのソケットの間でデータを渡します。

   特定 `CArchive` のオブジェクトがデータを1方向に移動するのは、読み込み (受信) または格納 (送信) のいずれかであることに注意してください。 場合によっては、 `CArchive` データの送信用に1つ、受信確認を受信するための2つのオブジェクトを使用します。

   接続を受け入れ、アーカイブを設定したら、パスワードの検証などのタスクを実行できます。

1. アーカイブ、ソケットファイル、およびソケットオブジェクトを破棄します。

    > [!NOTE]
    >  クラス `CArchive` は、 `IsBufferEmpty` クラスで使用するためのメンバー関数を提供し `CSocket` ます。 たとえば、バッファーに複数のデータメッセージが含まれている場合は、すべてのメッセージが読み取られ、バッファーがクリアされるまでループする必要があります。 それ以外の場合、受信するデータがあることを示す次の通知は、無期限に遅延される可能性があります。 `IsBufferEmpty`すべてのデータを確実に取得するには、を使用します。

「 [Windows ソケット: 一連の操作](../mfc/windows-sockets-sequence-of-operations.md) 」では、このプロセスの両方の側面をコード例と共に示します。

詳細については、次を参照してください。

- [Windows ソケット: ストリームソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット: データグラムソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket:: Create](../mfc/reference/csocket-class.md#create)
