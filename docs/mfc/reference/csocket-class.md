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
ms.openlocfilehash: a861e557b7368d13d615aaf796faded93c72b040
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426553"
---
# <a name="csocket-class"></a>CSocket クラス

は `CAsyncSocket`から派生し、Windows ソケット API のカプセル化を継承し、`CAsyncSocket` オブジェクトよりも高いレベルの抽象化を表します。

## <a name="syntax"></a>構文

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CSocket:: CSocket](#csocket)|`CSocket` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CSocket:: Attach](#attach)|ソケットハンドルを `CSocket` オブジェクトにアタッチします。|
|[CSocket:: CancelBlockingCall](#cancelblockingcall)|現在実行中のブロッキング呼び出しをキャンセルします。|
|[CSocket:: Create](#create)|ソケットを作成します。|
|[CSocket:: FromHandle](#fromhandle)|ソケットハンドルが指定されている場合、`CSocket` オブジェクトへのポインターを返します。|
|[CSocket:: IsBlocking](#isblocking)|ブロック呼び出しが進行中かどうかを判断します。|

### <a name="protected-methods"></a>プロテクト メソッド

|Name|Description|
|----------|-----------------|
|[CSocket:: OnMessagePending](#onmessagepending)|ブロック呼び出しの完了を待機している間、保留中のメッセージを処理するために呼び出されます。|

## <a name="remarks"></a>解説

`CSocket` は、データの送受信を管理するために `CSocketFile` および `CArchive` のクラスと連携します。

`CSocket` オブジェクトは、`CArchive`の同期操作に不可欠なブロッキングも提供します。 `Receive`、`Send`、`ReceiveFrom`、`SendTo`、`Accept` (すべて `CAsyncSocket`から継承) などのブロック関数は `WSAEWOULDBLOCK` で `CSocket`エラーを返しません。 代わりに、これらの関数は、操作が完了するまで待機します。 また、これらの関数のいずれかがブロックされている間に `CancelBlockingCall` が呼び出された場合、元の呼び出しはエラー WSAEINTR で終了します。

`CSocket` オブジェクトを使用するには、コンストラクターを呼び出し、次に `Create` を呼び出して、基になるソケットハンドル (型ソケット) を作成します。 ストリームソケットを作成 `Create` の既定のパラメーターですが、`CArchive` オブジェクトでソケットを使用していない場合は、代わりに、パラメーターを指定してデータグラムソケットを作成するか、特定のポートにバインドしてサーバーソケットを作成することができます。 クライアント側で `Connect` を使用してクライアントソケットに接続し、サーバー側で `Accept` します。 次に、`CSocketFile` オブジェクトを作成し、`CSocketFile` コンストラクターの `CSocket` オブジェクトに関連付けます。 次に、送信用の `CArchive` オブジェクトを作成し、必要に応じてデータを受信するためのオブジェクトを作成し、`CArchive` コンストラクターの `CSocketFile` オブジェクトと関連付けます。 通信が完了したら、`CArchive`、`CSocketFile`、および `CSocket` オブジェクトを破棄します。 ソケットデータ型については、「 [Windows Sockets: Background](../../mfc/windows-sockets-background.md)」を参照してください。

`CSocketFile` と `CSocket`で `CArchive` を使用する場合、要求されたバイト数を待機し `PumpMessages(FD_READ)`て `CSocket::Receive` がループに入る状況が発生する可能性があります。 これは、Windows sockets では FD_READ 通知ごとに1つの recv 呼び出しのみが許可されるのに対し、`CSocketFile` と `CSocket` では FD_READ ごとに複数の recv 呼び出しが許可されるためです。 読み取るデータが存在しない場合に FD_READ を取得すると、アプリケーションがハングします。 別の FD_READ が得られない場合、アプリケーションはソケット経由の通信を停止します。

この問題は、次のように解決できます。 ソケットクラスの `OnReceive` メソッドで、ソケットから読み取られると予想されるデータが1つの TCP パケット (ネットワークメディアの最大転送単位 (通常は1096バイト以上)) のサイズを超えたときに、メッセージクラスの `Serialize` メソッドを呼び出す前に `CAsyncSocket::IOCtl(FIONREAD, ...)` を呼び出します。 使用可能なデータのサイズが必要以上に満たない場合は、すべてのデータが受信されるのを待ってから、読み取り操作を開始します。

次の例では、`m_dwExpected` は、ユーザーが受け取ると予想されるおおよそのバイト数です。 コード内の他の場所で宣言することを前提としています。

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
>  静的にリンクされた MFC アプリケーションでセカンダリスレッドで MFC ソケットを使用する場合は、ソケットを使用してソケットライブラリを初期化する各スレッドで `AfxSocketInit` を呼び出す必要があります。 既定では、`AfxSocketInit` はプライマリスレッドでのみ呼び出されます。

詳細については、「 [MFC の Windows sockets](../../mfc/windows-sockets-in-mfc.md)」、「 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」、「windows ソケット: アーカイブを使用するソケットの[しくみ](../../mfc/windows-sockets-how-sockets-with-archives-work.md)」、「windows ソケット:[操作のシーケンス](../../mfc/windows-sockets-sequence-of-operations.md)」、「 [Windows ソケット: アーカイブを使用するソケットの例](../../mfc/windows-sockets-example-of-sockets-using-archives.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxsock

##  <a name="attach"></a>CSocket:: Attach

このメンバー関数を呼び出して、`CSocket` オブジェクトに `hSocket` ハンドルをアタッチします。

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>パラメーター

*hSocket*<br/>
ソケットを表すハンドルを格納します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。

### <a name="remarks"></a>解説

ソケットハンドルは、オブジェクトの[m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket)データメンバーに格納されます。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

##  <a name="cancelblockingcall"></a>CSocket:: CancelBlockingCall

現在実行中のブロック呼び出しを取り消すには、このメンバー関数を呼び出します。

```
void CancelBlockingCall();
```

### <a name="remarks"></a>解説

この関数は、このソケットの未処理のブロッキング操作を取り消します。 元のブロック呼び出しは、エラー WSAEINTR でできるだけ早く終了します。

`Connect` のブロッキング操作の場合は、Windows ソケットの実装によってブロック呼び出しができるだけ早く終了しますが、接続が完了してからリセットされるか、またはタイムアウトになるまでソケットリソースが解放されない可能性があります。これは、アプリケーションが (ソケットが使用できない場合) 新しいソケットをすぐに開くか、同じピアに接続する場合にのみ、顕著になる可能性があります。

`Accept` 以外の操作を取り消すと、ソケットが中間状態のままになる可能性があります。 アプリケーションがソケットでのブロック操作をキャンセルした場合、そのアプリケーションがソケット上で実行できる操作は `Close`への呼び出しに依存しますが、一部の Windows ソケット実装では他の操作が機能することがあります。 アプリケーションの移植性を最大にする場合は、キャンセル後の操作の実行に依存しないように注意する必要があります。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

##  <a name="create"></a>CSocket:: Create

Socket オブジェクトを構築した後に**create** member 関数を呼び出して、Windows ソケットを作成し、それをアタッチします。

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>パラメーター

*nSocketPort*<br/>
ソケットで使用される特定のポート。 MFC でポートを選択する場合は0。

*nSocketType*<br/>
SOCK_STREAM または SOCK_DGRAM。

*lpszSocketAddress*<br/>
接続されたソケットのネットワークアドレスを格納している文字列へのポインター ("128.56.22.8" など)。 このパラメーターに NULL 文字列を渡すことは、`CSocket` インスタンスがすべてのネットワークインターフェイスでクライアントアクティビティをリッスンする必要があることを示します。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、`GetLastError`を呼び出すことによって特定のエラーコードを取得できます。

### <a name="remarks"></a>解説

次に、`Bind` を呼び出して、ソケットを指定されたアドレスにバインドします。 `Create` 次のソケットの種類がサポートされています。

- SOCK_STREAM は、シーケンス、信頼性、双方向の、接続ベースのバイトストリームを提供します。 は、インターネットアドレスファミリに伝送制御プロトコル (TCP) を使用します。

- SOCK_DGRAM は、固定された (通常は小さい) 最大長の、コネクションレスで信頼性の低いバッファーであるデータグラムをサポートします。 は、インターネットアドレスファミリにユーザーデータグラムプロトコル (UDP) を使用します。 このオプションを使用するには、`CArchive` オブジェクトでソケットを使用しないようにする必要があります。

    > [!NOTE]
    >  `Accept` メンバー関数は、新しい空の `CSocket` オブジェクトへの参照をそのパラメーターとして受け取ります。 `Accept`を呼び出す前に、このオブジェクトを作成する必要があります。 このソケットオブジェクトがスコープ外に出ると、接続が閉じられることに注意してください。 この新しいソケットオブジェクトに対して `Create` を呼び出さないでください。

ストリームソケットとデータグラムソケットの詳細については、「 [Windows ソケット: バックグラウンド](../../mfc/windows-sockets-background.md)」、「 [Windows ソケット: ポートとソケットアドレス](../../mfc/windows-sockets-ports-and-socket-addresses.md)」、および「 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

##  <a name="csocket"></a>CSocket:: CSocket

`CSocket` オブジェクトを構築します。

```
CSocket();
```

### <a name="remarks"></a>解説

構築後、`Create` メンバー関数を呼び出す必要があります。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

##  <a name="fromhandle"></a>CSocket:: FromHandle

`CSocket` オブジェクトへのポインターを返します。

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>パラメーター

*hSocket*<br/>
ソケットを表すハンドルを格納します。

### <a name="return-value"></a>戻り値

`CSocket` オブジェクトへのポインター。 *Hsocket*に `CSocket` オブジェクトがアタッチされていない場合は NULL。

### <a name="remarks"></a>解説

ソケットハンドルが指定されている場合、`CSocket` オブジェクトがハンドルにアタッチされていない場合、メンバー関数は NULL を返し、一時オブジェクトを作成しません。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

##  <a name="isblocking"></a>CSocket:: IsBlocking

ブロック呼び出しが進行中かどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsBlocking();
```

### <a name="return-value"></a>戻り値

ソケットがブロックしている場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

##  <a name="onmessagepending"></a>CSocket:: OnMessagePending

このメンバー関数をオーバーライドして、Windows から特定のメッセージを検索し、ソケット内の特定のメッセージに応答します。

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>戻り値

メッセージが処理された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

これは高度なオーバーライド可能です。

このフレームワークは、ソケットが Windows メッセージをポンプしている間に `OnMessagePending` を呼び出し、アプリケーションにとって関心のあるメッセージを処理する機会を提供します。 `OnMessagePending`を使用する方法の例については、「 [Windows ソケット: ソケットクラスからの派生](../../mfc/windows-sockets-deriving-from-socket-classes.md)」を参照してください。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="see-also"></a>参照

[CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
