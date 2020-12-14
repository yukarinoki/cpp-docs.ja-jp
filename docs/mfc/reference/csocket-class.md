---
description: '詳細: CSocket クラス'
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
ms.openlocfilehash: e04fc0b453c4d4172fcd286b142d029bda0eb5dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345109"
---
# <a name="csocket-class"></a>CSocket クラス

は、から派生し `CAsyncSocket` 、Windows ソケット API のカプセル化を継承し、オブジェクトよりも高い抽象化レベルを表し `CAsyncSocket` ます。

## <a name="syntax"></a>構文

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSocket:: CSocket](#csocket)|`CSocket` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSocket:: Attach](#attach)|ソケットハンドルをオブジェクトにアタッチ `CSocket` します。|
|[CSocket:: CancelBlockingCall](#cancelblockingcall)|現在実行中のブロッキング呼び出しをキャンセルします。|
|[CSocket:: Create](#create)|ソケットを作成します。|
|[CSocket:: FromHandle](#fromhandle)|`CSocket`ソケットハンドルを指定して、オブジェクトへのポインターを返します。|
|[CSocket:: IsBlocking](#isblocking)|ブロック呼び出しが進行中かどうかを判断します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CSocket:: OnMessagePending](#onmessagepending)|ブロック呼び出しの完了を待機している間、保留中のメッセージを処理するために呼び出されます。|

## <a name="remarks"></a>解説

`CSocket` は、クラス `CSocketFile` と連携し `CArchive` 、データの送受信を管理します。

また、オブジェクトには `CSocket` 、の同期操作に不可欠なブロッキングも用意されて `CArchive` います。 `Receive`、、 `Send` `ReceiveFrom` 、 `SendTo` 、および `Accept` (から継承されたすべての) のブロック関数 `CAsyncSocket` は、ではエラーを返しません `WSAEWOULDBLOCK` `CSocket` 。 代わりに、これらの関数は、操作が完了するまで待機します。 また、 `CancelBlockingCall` これらの関数のいずれかがブロックされているときにが呼び出された場合、元の呼び出しはエラー WSAEINTR で終了します。

オブジェクトを使用するには、 `CSocket` コンストラクターを呼び出した後、 `Create` を呼び出して、基になるソケットハンドル (型ソケット) を作成します。 の既定のパラメーターでは、 `Create` ストリームソケットを作成しますが、オブジェクトでソケットを使用していない場合は、 `CArchive` 代わりに、パラメーターを指定してデータグラムソケットを作成するか、特定のポートにバインドしてサーバーソケットを作成することができます。 クライアント `Connect` 側とサーバー側でを使用して、クライアントソケットに接続し `Accept` ます。 次に、 `CSocketFile` オブジェクトを作成し、 `CSocket` コンストラクター内のオブジェクトに関連付け `CSocketFile` ます。 次に、 `CArchive` 送信用のオブジェクトとデータを受信するためのオブジェクトを作成し (必要に応じて)、 `CSocketFile` コンストラクター内のオブジェクトに関連付け `CArchive` ます。 通信が完了したら、、、の各オブジェクトを破棄 `CArchive` `CSocketFile` `CSocket` します。 ソケットデータ型については、「 [Windows Sockets: Background](../../mfc/windows-sockets-background.md)」を参照してください。

とを一緒に使用すると `CArchive` `CSocketFile` `CSocket` 、 `CSocket::Receive` によって () によって `PumpMessages(FD_READ)` 要求されたバイト数の待機が開始される状況が発生する可能性があります。 これは、Windows sockets では FD_READ 通知ごとに1つの recv 呼び出しのみが許可されていますが、 `CSocketFile` FD_READ ごとに複数の recv 呼び出しが許可されているためです `CSocket` 。 読み取るデータが存在しない場合に FD_READ を取得すると、アプリケーションがハングします。 別の FD_READ が得られない場合、アプリケーションはソケット経由の通信を停止します。

この問題は、次のように解決できます。 `OnReceive`ソケットクラスのメソッドで、 `CAsyncSocket::IOCtl(FIONREAD, ...)` `Serialize` ソケットから読み取られると予想されるデータが1つの TCP パケット (ネットワークメディアの最大転送単位 (通常は1096バイト以上)) のサイズを超えたときに、メッセージクラスのメソッドを呼び出す前に、を呼び出します。 使用可能なデータのサイズが必要以上に満たない場合は、すべてのデータが受信されるのを待ってから、読み取り操作を開始します。

次の例で `m_dwExpected` は、は、ユーザーが受け取ると予想されるおおよそのバイト数です。 コード内の他の場所で宣言することを前提としています。

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
> 静的にリンクされた MFC アプリケーションでセカンダリスレッドで MFC ソケットを使用する場合は、ソケット `AfxSocketInit` ライブラリを初期化するためにソケットを使用する各スレッドでを呼び出す必要があります。 既定で `AfxSocketInit` は、はプライマリスレッドでのみ呼び出されます。

詳細については、「 [MFC の Windows sockets](../../mfc/windows-sockets-in-mfc.md)」、「 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」、「windows ソケット: アーカイブを使用するソケットの [しくみ](../../mfc/windows-sockets-how-sockets-with-archives-work.md)」、「windows ソケット: [操作のシーケンス](../../mfc/windows-sockets-sequence-of-operations.md)」、「 [Windows ソケット: アーカイブを使用するソケットの例](../../mfc/windows-sockets-example-of-sockets-using-archives.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>要件

**ヘッダー:** afxsock

## <a name="csocketattach"></a><a name="attach"></a> CSocket:: Attach

ハンドルをオブジェクトにアタッチするには、このメンバー関数を呼び出し `hSocket` `CSocket` ます。

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>パラメーター

*hSocket*<br/>
ソケットを表すハンドルを格納します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。

### <a name="remarks"></a>解説

ソケットハンドルは、オブジェクトの [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) データメンバーに格納されます。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

## <a name="csocketcancelblockingcall"></a><a name="cancelblockingcall"></a> CSocket:: CancelBlockingCall

現在実行中のブロック呼び出しを取り消すには、このメンバー関数を呼び出します。

```cpp
void CancelBlockingCall();
```

### <a name="remarks"></a>解説

この関数は、このソケットの未処理のブロッキング操作を取り消します。 元のブロック呼び出しは、エラー WSAEINTR でできるだけ早く終了します。

ブロック操作の場合は、 `Connect` Windows ソケットの実装によってブロック呼び出しができるだけ早く終了しますが、接続が完了してからリセットされるか、タイムアウトになるまで、ソケットリソースが解放されない可能性があります。これは、アプリケーションが (ソケットが使用できない場合) 新しいソケットをすぐに開くか、同じピアに接続する場合にのみ、顕著になる可能性があります。

以外の操作を取り消す `Accept` と、ソケットは不確定状態のままになります。 アプリケーションがソケットでのブロック操作をキャンセルした場合、そのアプリケーションがソケットでの実行に依存できる操作は、の呼び出しだけです `Close` 。ただし、Windows ソケットの実装によっては、他の操作が機能する場合があります。 アプリケーションの移植性を最大にする場合は、キャンセル後の操作の実行に依存しないように注意する必要があります。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketcreate"></a><a name="create"></a> CSocket:: Create

Socket オブジェクトを構築した後に **create** member 関数を呼び出して、Windows ソケットを作成し、それをアタッチします。

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
接続されたソケットのネットワークアドレスを格納している文字列へのポインター ("128.56.22.8" など)。 このパラメーターに NULL 文字列を渡すと、 `CSocket` インスタンスはすべてのネットワークインターフェイスでクライアントアクティビティをリッスンする必要があることを示します。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0。を呼び出すと、特定のエラーコードを取得でき `GetLastError` ます。

### <a name="remarks"></a>解説

`Create` 次 `Bind` に、を呼び出して、ソケットを指定されたアドレスにバインドします。 次のソケットの種類がサポートされています。

- SOCK_STREAM は、シーケンス、信頼性、双方向の、接続ベースのバイトストリームを提供します。 は、インターネットアドレスファミリに伝送制御プロトコル (TCP) を使用します。

- SOCK_DGRAM は、固定された (通常は小さい) 最大長の、コネクションレスで信頼性の低いバッファーであるデータグラムをサポートします。 は、インターネットアドレスファミリにユーザーデータグラムプロトコル (UDP) を使用します。 このオプションを使用するには、オブジェクトでソケットを使用しないようにする必要があり `CArchive` ます。

    > [!NOTE]
    >  この `Accept` メンバー関数は、新しい空のオブジェクトへの参照を `CSocket` そのパラメーターとして受け取ります。 を呼び出す前に、このオブジェクトを作成する必要があり `Accept` ます。 このソケットオブジェクトがスコープ外に出ると、接続が閉じられることに注意してください。 `Create`この新しいソケットオブジェクトに対してを呼び出さないでください。

ストリームソケットとデータグラムソケットの詳細については、「 [Windows ソケット: バックグラウンド](../../mfc/windows-sockets-background.md)」、「 [Windows ソケット: ポートとソケットアドレス](../../mfc/windows-sockets-ports-and-socket-addresses.md)」、および「 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketcsocket"></a><a name="csocket"></a> CSocket:: CSocket

`CSocket` オブジェクトを構築します。

```
CSocket();
```

### <a name="remarks"></a>解説

構築後、メンバー関数を呼び出す必要があり `Create` ます。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketfromhandle"></a><a name="fromhandle"></a> CSocket:: FromHandle

オブジェクトへのポインターを返し `CSocket` ます。

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>パラメーター

*hSocket*<br/>
ソケットを表すハンドルを格納します。

### <a name="return-value"></a>戻り値

オブジェクトへのポインター `CSocket` `CSocket` 。 *hsocket* にアタッチされたオブジェクトがない場合は NULL。

### <a name="remarks"></a>解説

ソケットハンドルが指定されている場合、 `CSocket` オブジェクトがハンドルにアタッチされていない場合、メンバー関数は NULL を返し、一時オブジェクトを作成しません。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketisblocking"></a><a name="isblocking"></a> CSocket:: IsBlocking

ブロック呼び出しが進行中かどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsBlocking();
```

### <a name="return-value"></a>戻り値

ソケットがブロックしている場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="csocketonmessagepending"></a><a name="onmessagepending"></a> CSocket:: OnMessagePending

このメンバー関数をオーバーライドして、Windows から特定のメッセージを検索し、ソケット内の特定のメッセージに応答します。

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>戻り値

メッセージが処理された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

これは高度なオーバーライド可能です。

このフレームワークは、 `OnMessagePending` ソケットが Windows メッセージをポンプしている間にを呼び出し、アプリケーションに関連するメッセージを処理する機会を提供します。 の使用方法の例につい `OnMessagePending` ては、「 [Windows ソケット: ソケットクラスからの派生](../../mfc/windows-sockets-deriving-from-socket-classes.md)」を参照してください。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
