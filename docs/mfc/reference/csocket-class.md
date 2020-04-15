---
title: CSocket クラス
ms.date: 11/04/2016
f1_keywords:
- CSocket
- AFXSOCK/CSocket
- AFXSOCK/CSocket::CSocket
- AFXSOCK/CSocket::Attach
- AFXSOCK/CSocket::CancelBlockingCall
- AFXSOCK/CSocket::Create
- AFXSOCK/CSocket::FromHandle
- AFXSOCK/CSocket::IsBlocking
- AFXSOCK/CSocket::OnMessagePending
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
ms.openlocfilehash: 3f0a7a9a90250ede7b112cfbd9bc1ca14d583356
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318194"
---
# <a name="csocket-class"></a>CSocket クラス

から`CAsyncSocket`派生、 Windows ソケット API のカプセル化を継承し、オブジェクトの抽象化レベルよりも高いレベルを`CAsyncSocket`表します。

## <a name="syntax"></a>構文

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cソケット::Cソケット](#csocket)|`CSocket` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cソケット::アタッチ](#attach)|オブジェクトに SOCKET ハンドルを`CSocket`アタッチします。|
|[呼び出しをキャンセルします。](#cancelblockingcall)|現在進行中のブロッキング呼び出しをキャンセルします。|
|[Cソケット::作成](#create)|ソケットを作成します。|
|[ハンドルを受け取る](#fromhandle)|指定されたソケット ハンドル`CSocket`を指定して、オブジェクトへのポインターを返します。|
|[Cソケット::イズブロッキング](#isblocking)|ブロッキング呼び出しが進行中かどうかを判断します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[メッセージ処理中](#onmessagepending)|ブロッキング呼び出しが完了するのを待っている間に、保留中のメッセージを処理するために呼び出されます。|

## <a name="remarks"></a>解説

`CSocket`クラス`CSocketFile`と連携し`CArchive`、データの送受信を管理します。

オブジェクト`CSocket`は、ブロックも提供します`CArchive`。 `Receive` `Send`、 、 、 、 `ReceiveFrom` `SendTo`、`Accept`など (`CAsyncSocket`継承元 )`WSAEWOULDBLOCK`などのブロック`CSocket`関数は、 でエラーを返しません。 代わりに、これらの関数は操作が完了するまで待機します。 さらに、これらの関数の 1 つがブロックされている間に呼び出された`CancelBlockingCall`場合、元の呼び出しはエラー WSAEINTR で終了します。

オブジェクトを`CSocket`使用するには、コンストラクターを呼び出`Create`してから、基になる SOCKET ハンドル (型 SOCKET) を作成します。 ストリームソケットを作成`Create`するデフォルトのパラメータですが、`CArchive`オブジェクトでソケットを使用していない場合は、代わりにデータグラムソケットを作成するパラメータを指定するか、特定のポートにバインドしてサーバーソケットを作成することができます。 クライアント側と`Accept`サーバー側で`Connect`クライアントソケットに接続します。 次に、`CSocketFile`オブジェクトを作成し、コンストラクター`CSocket`内のオブジェクト`CSocketFile`に関連付けます。 次に`CArchive`、送信するオブジェクトと、必要に応じてデータを受信するためのオブジェクトを作成し、`CSocketFile``CArchive`コンストラクター内のオブジェクトに関連付けます。 通信が完了したら、 `CArchive`、`CSocketFile`および オブジェクト`CSocket`を破棄します。 ソケットデータ型については[、「Windows ソケット: バックグラウンド](../../mfc/windows-sockets-background.md)」の記事で説明されています。

と`CSocket`を`CArchive``CSocketFile`使用すると、要求されたバイト数を待`CSocket::Receive`つループがループ`PumpMessages(FD_READ)`に入る状況が発生する場合があります。 これは、Windows ソケットでは、FD_READ通知ごとに 1 つの recv `CSocketFile` `CSocket`呼び出ししか許可しませんが、FD_READごとに複数の recv 呼び出しを許可するためです。 読み取るデータがないときにFD_READを取得すると、アプリケーションがハングします。 FD_READがもうない場合、アプリケーションはソケット経由で通信を停止します。

この問題は、次のように解決できます。 ソケット`OnReceive`クラスのメソッドでは、ソケットから`CAsyncSocket::IOCtl(FIONREAD, ...)`読み取る`Serialize`データが 1 つの TCP パケットのサイズ (ネットワーク メディアの最大伝送単位、通常は少なくとも 1096 バイト) を超えたときに、メッセージ クラスのメソッドを呼び出す前に呼び出します。 使用可能なデータのサイズが必要以上に小さい場合は、すべてのデータが受信されるのを待ってから、読み取り操作を開始してください。

次の例では、`m_dwExpected`ユーザーが受信する必要があるおよそのバイト数を示します。 コード内の他の場所で宣言することを前提としています。

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
> 静的にリンクされた MFC アプリケーションのセカンダリ スレッドで MFC ソケットを使用する`AfxSocketInit`場合は、ソケット ライブラリを初期化するためにソケットを使用する各スレッドで呼び出す必要があります。 デフォルトでは、`AfxSocketInit`プライマリ スレッドでのみ呼び出されます。

詳細については、「 MFC の[Windows ソケット](../../mfc/windows-sockets-in-mfc.md)、 Windows ソケット[: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md) [、Windows ソケット : アーカイブを含むソケットの動作](../../mfc/windows-sockets-how-sockets-with-archives-work.md) [、Windows ソケット: 操作のシーケンス](../../mfc/windows-sockets-sequence-of-operations.md) [、Windows ソケット : アーカイブを使用したソケットの例](../../mfc/windows-sockets-example-of-sockets-using-archives.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxsock.h

## <a name="csocketattach"></a><a name="attach"></a>Cソケット::アタッチ

`hSocket`オブジェクトにハンドルをアタッチ`CSocket`します。

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>パラメーター

*hソケット*<br/>
ソケットへのハンドルを含みます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。

### <a name="remarks"></a>解説

SOCKET ハンドルは、オブジェクトの[m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket)データ・メンバーに保管されます。

詳細については、「 [Windows ソケット : アーカイブでソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

## <a name="csocketcancelblockingcall"></a><a name="cancelblockingcall"></a>呼び出しをキャンセルします。

現在進行中のブロッキング呼び出しをキャンセルするには、このメンバー関数を呼び出します。

```
void CancelBlockingCall();
```

### <a name="remarks"></a>解説

この関数は、このソケットの未処理のブロック操作を取り消します。 元のブロッキング呼び出しは、エラー WSAEINTR でできるだけ早く終了します。

ブロッキング`Connect`操作の場合、Windows ソケットの実装は、ブロッキング呼び出しをできるだけ早く終了しますが、接続が完了するか (そしてリセットされた)、またはタイムアウトするまで、ソケット リソースを解放できない場合があります。これは、アプリケーションが新しいソケットを直ちに開こうとした場合 (ソケットが利用できない場合)、または同じピアに接続する場合にのみ顕著です。

以外の操作をキャンセル`Accept`すると、ソケットは不確定な状態のままで済みます。 アプリケーションがソケットでのブロック操作を取り消した場合、そのアプリケーションがソケットで実行できる操作は 呼び出し`Close`だけですが、他の操作は Windows ソケットの実装で動作する場合があります。 アプリケーションの移植性を最大限に高める場合は、キャンセル後に操作を実行することに依存しないように注意する必要があります。

詳細については、「 [Windows ソケット : アーカイブでソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketcreate"></a><a name="create"></a>Cソケット::作成

ソケット オブジェクトを作成した後に**Create**メンバー関数を呼び出して、Windows ソケットを作成し、アタッチします。

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ソケットで使用する特定のポート、または MFC でポートを選択する場合は 0。

*を指定します。*<br/>
SOCK_STREAMまたはSOCK_DGRAM。

*ソケットアドレス*<br/>
接続されたソケットのネットワークアドレスを含む文字列へのポインタで、ドット番号(128.56.22.8)など。 このパラメーターに NULL 文字列を渡`CSocket`すと、インスタンスはすべてのネットワーク インターフェイスでクライアント アクティビティをリッスンする必要があります。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し、特定の`GetLastError`エラー コードを呼び出すことによって取得できます。

### <a name="remarks"></a>解説

`Create`その後`Bind`、ソケットを指定したアドレスにバインドする呼び出しを行います。 次のソケット・タイプがサポートされています。

- SOCK_STREAM シーケンス型、信頼性のある、双方向の接続ベースのバイト ストリームを提供します。 インターネット アドレス ファミリに伝送制御プロトコル (TCP) を使用します。

- SOCK_DGRAM固定 (通常は小さい) 最大長のコネクションレスで信頼性の低いバッファであるデータグラムをサポートします。 インターネット アドレス ファミリにユーザー データグラム プロトコル (UDP) を使用します。 このオプションを使用するには、オブジェクトと共にソケットを`CArchive`使用しないでください。

    > [!NOTE]
    >  メンバー`Accept`関数は、新しい空`CSocket`のオブジェクトへの参照をパラメーターとして受け取ります。 このオブジェクトは、 を呼び`Accept`出す前に構築する必要があります。 このソケット オブジェクトがスコープ外に出ると、接続が閉じられます。 この新しい`Create`ソケット オブジェクトを呼び出しません。

ストリーム ソケットとデータグラム ソケットの詳細については[、「Windows ソケット: バックグラウンド](../../mfc/windows-sockets-background.md)[、Windows ソケット: ポートとソケット アドレス](../../mfc/windows-sockets-ports-and-socket-addresses.md)、および Windows ソケット :[アーカイブでソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketcsocket"></a><a name="csocket"></a>Cソケット::Cソケット

`CSocket` オブジェクトを構築します。

```
CSocket();
```

### <a name="remarks"></a>解説

構築後、メンバー関数を呼`Create`び出す必要があります。

詳細については、「 [Windows ソケット : アーカイブでソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketfromhandle"></a><a name="fromhandle"></a>ハンドルを受け取る

オブジェクトへのポインターを`CSocket`返します。

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>パラメーター

*hソケット*<br/>
ソケットへのハンドルを含みます。

### <a name="return-value"></a>戻り値

`CSocket`オブジェクトへのポインター、 *hSocket*にアタッチされているオブジェクト`CSocket`がない場合は NULL。

### <a name="remarks"></a>解説

SOCKET ハンドルが与えられた場合、`CSocket`オブジェクトがハンドルにアタッチされていない場合、メンバー関数は NULL を返し、一時オブジェクトは作成しません。

詳細については、「 [Windows ソケット : アーカイブでソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketisblocking"></a><a name="isblocking"></a>Cソケット::イズブロッキング

ブロッキング呼び出しが進行中かどうかを確認します。

```
BOOL IsBlocking();
```

### <a name="return-value"></a>戻り値

ソケットがブロックしている場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット : アーカイブでソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketonmessagepending"></a><a name="onmessagepending"></a>メッセージ処理中

Windows からの特定のメッセージを検索し、ソケットで応答するには、このメンバー関数をオーバーライドします。

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>戻り値

メッセージが処理された場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

これは、高度なオーバーライド可能です。

ソケットが`OnMessagePending`Windows メッセージを送り込んでいる間にフレームワークが呼び出され、アプリケーションに関心のあるメッセージを処理する機会が与えられます。 の使用例`OnMessagePending`については、「 Windows ソケット :[ソケット クラスからの派生](../../mfc/windows-sockets-deriving-from-socket-classes.md)」を参照してください。

詳細については、「 [Windows ソケット : アーカイブでソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/casyncsocket-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
