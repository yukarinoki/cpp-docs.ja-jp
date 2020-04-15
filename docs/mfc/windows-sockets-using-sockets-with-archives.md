---
title: 'Windows ソケット: アーカイブ付きソケットの使用'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
ms.openlocfilehash: 55b4f9a5412c1447fe2b3bde10cb934b91abf008
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359953"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows ソケット: アーカイブ付きソケットの使用

この記事では[、CSocket プログラミング モデルについて](#_core_the_csocket_programming_model)説明します。 クラス[CSocket](../mfc/reference/csocket-class.md)は、クラス[CAsyncSocket](../mfc/reference/casyncsocket-class.md)よりも高い抽象化レベルでソケットサポートを提供します。 `CSocket`は MFC [CArchive](../mfc/reference/carchive-class.md)オブジェクトを介してソケット オブジェクトとの間でデータをやり取りするために、MFC シリアル化プロトコルのバージョンを使用します。 `CSocket`はブロックを提供し (Windows メッセージのバックグラウンド処理を管理している`CArchive`間)、生の API またはクラス`CAsyncSocket`を使用して自分で行う必要のある通信のさまざまな側面を管理する にアクセスできます。

> [!TIP]
> クラス`CSocket`は、より便利なバージョン`CAsyncSocket`として単独で使用できますが、最も簡単なプログラミング モデルは`CSocket``CArchive`オブジェクトで使用することです。

アーカイブ付きソケットの実装のしくみについては、「 [Windows ソケット : アーカイブを持つソケットの動作」](../mfc/windows-sockets-how-sockets-with-archives-work.md)を参照してください。 例のコードについては、「 [Windows ソケット : 操作のシーケンス](../mfc/windows-sockets-sequence-of-operations.md)と Windows ソケット :[アーカイブを使用したソケットの例](../mfc/windows-sockets-example-of-sockets-using-archives.md)」を参照してください。 ソケット クラスから独自のクラスを派生させることによって得られる機能の詳細については、「 Windows ソケット[: ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)」を参照してください。

> [!NOTE]
> 確立された (非 MFC) サーバーと通信する MFC クライアント プログラムを作成する場合は、アーカイブを通じて C++ オブジェクトを送信しないでください。 サーバーが、送信するオブジェクトの種類を理解する MFC アプリケーションでない限り、オブジェクトを受信および逆シリアル化することはできません。 非 MFC アプリケーションとの通信に関する関連事項については[、「Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)」を参照してください。

## <a name="the-csocket-programming-model"></a><a name="_core_the_csocket_programming_model"></a>CSocket プログラミング モデル

オブジェクトを`CSocket`使用するには、複数の MFC クラス オブジェクトを作成し、関連付けます。 以下の一般的な手順では、各ソケットタイプが異なるアクションを必要とするステップ 3 を除き、サーバーソケットとクライアントソケットの両方で各ステップが実行されます。

> [!TIP]
> 実行時に、サーバー アプリケーションは、通常、最初に準備が整い、クライアント アプリケーションが接続を求めるときに "待機" します。 クライアントが接続しようとしたときにサーバーの準備ができていない場合は、通常、ユーザー アプリケーションが後で接続を再試行する必要があります。

#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>サーバー ソケットとクライアント ソケット間の通信をセットアップするには

1. [CSocket](../mfc/reference/csocket-class.md)オブジェクトを構築します。

1. オブジェクトを使用して、基になる**SOCKET**ハンドルを作成します。

   クライアント`CSocket`オブジェクトの場合は、データグラム ソケットが必要な場合を除き、通常は既定のパラメータを[[作成](../mfc/reference/casyncsocket-class.md#create)] に使用する必要があります。 サーバー`CSocket`オブジェクトの場合は、呼び出しで`Create`ポートを指定する必要があります。

    > [!NOTE]
    >  `CArchive`データグラムソケットでは動作しません。 データグラム ソケットに`CSocket`使用する場合は、アーカイブなしで使用するクラスを使用`CAsyncSocket`する必要があります。 データグラムは信頼性が低いため (到着が保証されておらず、繰り返しまたは順序が乱れている可能性があります)、アーカイブによるシリアル化と互換性がありません。 シリアル化操作は、確実かつ順番に完了すると予想されます。 データグラムの`CArchive`オブジェクトで`CSocket`使用しようとすると、MFC アサーションが失敗します。

1. ソケットがクライアントの場合は[、CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect)を呼び出してソケットオブジェクトをサーバーソケットに接続します。

     \- または -

   ソケットがサーバーの場合は[、CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)を呼び出して、クライアントからの接続試行のリッスンを開始します。 接続要求を受信した後、呼び出すことによって受[け入れる::受け入れる](../mfc/reference/casyncsocket-class.md#accept).

    > [!NOTE]
    >  メンバー`Accept`関数は、新しい空`CSocket`のオブジェクトへの参照をパラメーターとして受け取ります。 このオブジェクトは、 を呼び`Accept`出す前に構築する必要があります。 このソケット オブジェクトがスコープ外に出ると、接続は閉じます。 この新しい`Create`ソケット オブジェクトを呼び出しません。

1. [CSocketFile](../mfc/reference/csocketfile-class.md)オブジェクトを作成し、`CSocket`オブジェクトをそれに関連付けます。

1. データの読み込み (受信) または格納 (送信) 用の[CArchive](../mfc/reference/carchive-class.md)オブジェクトを作成します。 アーカイブはオブジェクトに`CSocketFile`関連付けられます。

   データグラムソケットでは`CArchive`動作しません。

1. `CArchive`クライアント ソケットとサーバー ソケット間でデータを渡す場合は、オブジェクトを使用します。

   特定`CArchive`のオブジェクトは、読み込み (受信) または格納 (送信) のいずれかの方向にのみデータを移動することを覚えておいてください。 場合によっては、データの送信用と`CArchive`受信確認用の 2 つのオブジェクトを使用します。

   接続を受け入れてアーカイブを設定した後、パスワードの検証などのタスクを実行できます。

1. アーカイブ、ソケットファイル、およびソケットオブジェクトを破棄します。

    > [!NOTE]
    >  クラス`CArchive`は、`IsBufferEmpty`クラス`CSocket`で使用するために特別にメンバー関数を提供します。 たとえば、バッファーに複数のデータ メッセージが含まれている場合は、すべてのデータ メッセージが読み取られ、バッファがクリアされるまでループする必要があります。 それ以外の場合は、受信するデータがあるという次の通知が無期限に遅延する可能性があります。 すべての`IsBufferEmpty`データを取得する場合に使用します。

「Windows[ソケット: 操作のシーケンス」では](../mfc/windows-sockets-sequence-of-operations.md)、このプロセスの両側にコード例を示します。

詳細については、次を参照してください。

- [Windows ソケット : ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット : データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[Cソケット::作成](../mfc/reference/csocket-class.md#create)
