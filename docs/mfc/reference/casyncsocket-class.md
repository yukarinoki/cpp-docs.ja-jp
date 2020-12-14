---
description: '詳細情報: CAsyncSocket クラス'
title: CAsyncSocket クラス
ms.date: 06/25/2020
f1_keywords:
- CAsyncSocket
- AFXSOCK/CAsyncSocket
- AFXSOCK/CAsyncSocket::CAsyncSocket
- AFXSOCK/CAsyncSocket::Accept
- AFXSOCK/CAsyncSocket::AsyncSelect
- AFXSOCK/CAsyncSocket::Attach
- AFXSOCK/CAsyncSocket::Bind
- AFXSOCK/CAsyncSocket::Close
- AFXSOCK/CAsyncSocket::Connect
- AFXSOCK/CAsyncSocket::Create
- AFXSOCK/CAsyncSocket::Detach
- AFXSOCK/CAsyncSocket::FromHandle
- AFXSOCK/CAsyncSocket::GetLastError
- AFXSOCK/CAsyncSocket::GetPeerName
- AFXSOCK/CAsyncSocket::GetPeerNameEx
- AFXSOCK/CAsyncSocket::GetSockName
- AFXSOCK/CAsyncSocket::GetSockNameEx
- AFXSOCK/CAsyncSocket::GetSockOpt
- AFXSOCK/CAsyncSocket::IOCtl
- AFXSOCK/CAsyncSocket::Listen
- AFXSOCK/CAsyncSocket::Receive
- AFXSOCK/CAsyncSocket::ReceiveFrom
- AFXSOCK/CAsyncSocket::ReceiveFromEx
- AFXSOCK/CAsyncSocket::Send
- AFXSOCK/CAsyncSocket::SendTo
- AFXSOCK/CAsyncSocket::SendToEx
- AFXSOCK/CAsyncSocket::SetSockOpt
- AFXSOCK/CAsyncSocket::ShutDown
- AFXSOCK/CASyncSocket::Socket
- AFXSOCK/CAsyncSocket::OnAccept
- AFXSOCK/CAsyncSocket::OnClose
- AFXSOCK/CAsyncSocket::OnConnect
- AFXSOCK/CAsyncSocket::OnOutOfBandData
- AFXSOCK/CAsyncSocket::OnReceive
- AFXSOCK/CAsyncSocket::OnSend
- AFXSOCK/CAsyncSocket::m_hSocket
helpviewer_keywords:
- CAsyncSocket [MFC], CAsyncSocket
- CAsyncSocket [MFC], Accept
- CAsyncSocket [MFC], AsyncSelect
- CAsyncSocket [MFC], Attach
- CAsyncSocket [MFC], Bind
- CAsyncSocket [MFC], Close
- CAsyncSocket [MFC], Connect
- CAsyncSocket [MFC], Create
- CAsyncSocket [MFC], Detach
- CAsyncSocket [MFC], FromHandle
- CAsyncSocket [MFC], GetLastError
- CAsyncSocket [MFC], GetPeerName
- CAsyncSocket [MFC], GetPeerNameEx
- CAsyncSocket [MFC], GetSockName
- CAsyncSocket [MFC], GetSockNameEx
- CAsyncSocket [MFC], GetSockOpt
- CAsyncSocket [MFC], IOCtl
- CAsyncSocket [MFC], Listen
- CAsyncSocket [MFC], Receive
- CAsyncSocket [MFC], ReceiveFrom
- CAsyncSocket [MFC], ReceiveFromEx
- CAsyncSocket [MFC], Send
- CAsyncSocket [MFC], SendTo
- CAsyncSocket [MFC], SendToEx
- CAsyncSocket [MFC], SetSockOpt
- CAsyncSocket [MFC], ShutDown
- CASyncSocket [MFC], Socket
- CAsyncSocket [MFC], OnAccept
- CAsyncSocket [MFC], OnClose
- CAsyncSocket [MFC], OnConnect
- CAsyncSocket [MFC], OnOutOfBandData
- CAsyncSocket [MFC], OnReceive
- CAsyncSocket [MFC], OnSend
- CAsyncSocket [MFC], m_hSocket
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
ms.openlocfilehash: a9b020a93d4d0f279b5b79fa76a9f6b94e4f9f03
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234333"
---
# <a name="casyncsocket-class"></a>CAsyncSocket クラス

Windows ソケット (ネットワーク通信のエンドポイント) を表します。

## <a name="syntax"></a>構文

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAsyncSocket:: CAsyncSocket](#casyncsocket)|`CAsyncSocket` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAsyncSocket:: Accept](#accept)|ソケットでの接続を受け入れます。|
|[CAsyncSocket:: AsyncSelect](#asyncselect)|ソケットのイベント通知を要求します。|
|[CAsyncSocket:: Attach](#attach)|ソケットハンドルをオブジェクトにアタッチ `CAsyncSocket` します。|
|[CAsyncSocket:: Bind](#bind)|ローカルアドレスをソケットに関連付けます。|
|[CAsyncSocket:: Close](#close)|ソケットを閉じます。|
|[CAsyncSocket:: Connect](#connect)|ピアソケットへの接続を確立します。|
|[CAsyncSocket::Create](#create)|ソケットを作成します。|
|[CAsyncSocket:: CreateEx](#createex)|詳細オプションを使用してソケットを作成します。|
|[CAsyncSocket::D etach](#detach)|オブジェクトからソケットハンドルをデタッチ `CAsyncSocket` します。|
|[CAsyncSocket:: FromHandle](#fromhandle)|`CAsyncSocket`ソケットハンドルを指定して、オブジェクトへのポインターを返します。|
|[CAsyncSocket:: GetLastError](#getlasterror)|失敗した最後の操作のエラー状態を取得します。|
|[CAsyncSocket:: GetPeerName](#getpeername)|ソケットが接続されているピアソケットのアドレスを取得します。|
|[CAsyncSocket:: GetPeerNameEx](#getpeernameex)|ソケットが接続されている (IPv6 アドレスを処理する) ピアソケットのアドレスを取得します。|
|[CAsyncSocket:: GetSockName](#getsockname)|ソケットのローカル名を取得します。|
|[CAsyncSocket:: GetSockNameEx](#getsocknameex)|ソケットのローカル名を取得します (IPv6 アドレスを処理します)。|
|[CAsyncSocket:: GetSockOpt](#getsockopt)|ソケットオプションを取得します。|
|[CAsyncSocket:: IOCtl](#ioctl)|ソケットのモードを制御します。|
|[CAsyncSocket:: Listen](#listen)|着信接続要求をリッスンするソケットを確立します。|
|[CAsyncSocket:: Receive](#receive)|ソケットからデータを受信します。|
|[CAsyncSocket:: ReceiveFrom](#receivefrom)|データグラムを受信し、送信元アドレスを格納します。|
|[CAsyncSocket:: ReceiveFromEx](#receivefromex)|データグラムを受信し、送信元アドレス (IPv6 アドレスを処理) を格納します。|
|[CAsyncSocket:: Send](#send)|接続されたソケットにデータを送信します。|
|[CAsyncSocket:: SendTo](#sendto)|特定の送信先にデータを送信します。|
|[CAsyncSocket:: SendToEx](#sendtoex)|特定の宛先にデータを送信します (IPv6 アドレスを処理します)。|
|[CAsyncSocket:: SetSockOpt](#setsockopt)|ソケットオプションを設定します。|
|[CAsyncSocket:: ShutDown](#shutdown)|`Send`ソケットでのまたはの呼び出しを無効にし `Receive` ます。|
|[CASyncSocket:: Socket](#socket)|ソケットハンドルを割り当てます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAsyncSocket:: OnAccept](#onaccept)|を呼び出すことによって、保留中の接続要求を受け入れることができることを待機中のソケットに通知 `Accept` します。|
|[CAsyncSocket:: OnClose](#onclose)|ソケットに接続されているソケットが閉じられたことをソケットに通知します。|
|[CAsyncSocket:: OnConnect](#onconnect)|接続の試行が成功したか、エラーが発生したかを接続ソケットに通知します。|
|[CAsyncSocket:: OnOutOfBandData](#onoutofbanddata)|受信ソケットに、(通常は緊急メッセージである) ソケットで読み取られる帯域外データがあることを通知します。|
|[CAsyncSocket:: OnReceive](#onreceive)|を呼び出すことによって取得されるデータがあることをリッスンソケットに通知 `Receive` します。|
|[CAsyncSocket:: OnSend](#onsend)|を呼び出すことによってデータを送信できることをソケットに通知 `Send` します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAsyncSocket:: operator =](#operator_eq)|オブジェクトに新しい値を割り当て `CAsyncSocket` ます。|
|[CAsyncSocket:: operator SOCKET](#operator_socket)|オブジェクトのソケットハンドルを取得するには、この演算子を使用し `CAsyncSocket` ます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CAsyncSocket:: m_hSocket](#m_hsocket)|このオブジェクトにアタッチされているソケットハンドルを示し `CAsyncSocket` ます。|

## <a name="remarks"></a>解説

クラス `CAsyncSocket` は、Windows ソケット関数 API をカプセル化して、Windows ソケットを MFC と組み合わせて使用するプログラマにオブジェクト指向の抽象化を提供します。

このクラスは、ネットワーク通信を理解していることを前提としています。 ブロック、バイト順の違い、および Unicode とマルチバイト文字セット (MBCS) の文字列間の変換を処理する責任があります。 これらの問題を管理するためのより便利なインターフェイスが必要な場合は、「クラス [CSocket](../../mfc/reference/csocket-class.md)」を参照してください。

オブジェクトを使用するには `CAsyncSocket` 、コンストラクターを呼び出した後、 [create](#create) 関数を呼び出して、 `SOCKET` 受け入れられたソケットを除き、基になるソケットハンドル (型) を作成します。 サーバーソケットの場合は、 [Listen](#listen) メンバー関数を呼び出し、クライアントソケットの場合は [Connect](#connect) メンバー関数を呼び出します。 サーバーソケットは、接続要求の受信時に [Accept](#accept) 関数を呼び出す必要があります。 残りの関数は、 `CAsyncSocket` ソケット間の通信を実行するために使用します。 完了時に、ヒープで作成されたオブジェクトを破棄します。 `CAsyncSocket` デストラクターは、 [Close](#close) 関数を自動的に呼び出します。 ソケットデータ型については、「 [Windows Sockets: Background](../../mfc/windows-sockets-background.md)」を参照してください。

> [!NOTE]
> 静的にリンクされた MFC アプリケーションでセカンダリスレッドで MFC ソケットを使用する場合は、ソケット `AfxSocketInit` ライブラリを初期化するためにソケットを使用する各スレッドでを呼び出す必要があります。 既定で `AfxSocketInit` は、はプライマリスレッドでのみ呼び出されます。

詳細については、「 [Windows ソケット: クラス CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) と関連記事」、および「 [WINDOWS sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>要件

**ヘッダー:** afxsock

## <a name="casyncsocketaccept"></a><a name="accept"></a> CAsyncSocket:: Accept

ソケット上の接続を受け入れるには、このメンバー関数を呼び出します。

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>パラメーター

*rConnectedSocket*<br/>
接続に使用できる新しいソケットを識別する参照。

*lpSockAddr*<br/>
ネットワーク上で認識されている接続ソケットのアドレスを受け取る [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体へのポインター。 *LpSockAddr* 引数の正確な形式は、ソケットの作成時に確立されたアドレスファミリによって決まります。 *LpSockAddr* または *lpSockAddrLen* が NULL と等しい場合、受け入れられたソケットのリモートアドレスに関する情報は返されません。

*lpSockAddrLen*<br/>
*LpSockAddr* 内のアドレスの長さをバイト単位で示すポインター。 *LpSockAddrLen* は、値の結果のパラメーターです。最初に *lpSockAddr* が指す領域の量を格納する必要があります。返されると、返されるアドレスの実際の長さ (バイト単位) が返されます。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEFAULT *lpSockAddrLen* 引数が小さすぎます ( [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体のサイズ未満)。

- かかわらず WSAEINPROGRESS Windows Sockets の呼び出しが進行中です。

- `Listen`受け入れ前に WSAEINVAL が呼び出されませんでした。

- WSAEMFILE は、受信時にキューが空であり、使用可能な記述子がありません。

- WSAは、バッファー領域を使用できません。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEOPNOTSUPP 参照されているソケットは、接続指向のサービスをサポートする型ではありません。

- WSAEWOULDBLOCK ソケットが非ブロッキングとしてマークされていて、受け入れられる接続が存在しません。

### <a name="remarks"></a>解説

このルーチンは、保留中の接続のキュー内の最初の接続を抽出し、このソケットと同じプロパティを使用して新しいソケットを作成し、 *Rconnectedsocket* にアタッチします。 保留中の接続がキューに存在しない場合、は `Accept` 0 を返し、 `GetLastError` エラーを返します。 受け入れられたソケット ( *Rconnectedsocket)* を使用して、より多くの接続を受け入れることはできません。 元のソケットは開いたままリッスンしています。

引数 *lpSockAddr* は、通信層に知られているように、接続ソケットのアドレスを使用して入力される結果パラメーターです。 `Accept` は、SOCK_STREAM などの接続ベースのソケットの種類で使用されます。

## <a name="casyncsocketasyncselect"></a><a name="asyncselect"></a> CAsyncSocket:: AsyncSelect

ソケットのイベント通知を要求するには、このメンバー関数を呼び出します。

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>パラメーター

*lEvent*<br/>
アプリケーションが関心を持つネットワークイベントの組み合わせを指定するビットマスク。

- 読み取りの準備に関する通知を受信する FD_READ ます。

- データを読み取ることができる場合に通知を受信する FD_WRITE ます。

- 帯域外データの到着通知を受信する FD_OOB ます。

- 着信接続の通知を受信する FD_ACCEPT ます。

- 接続結果の通知を受信する FD_CONNECT ます。

- ソケットがピアによって閉じられたときに通知を受信する FD_CLOSE ます。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEINVAL は、指定されたパラメーターのいずれかが無効であることを示します。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

### <a name="remarks"></a>解説

この関数は、ソケットに対して呼び出される MFC コールバック通知関数を指定するために使用されます。 `AsyncSelect` は、このソケットを非ブロッキングモードに自動的に設定します。 詳細については、「 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

## <a name="casyncsocketattach"></a><a name="attach"></a> CAsyncSocket:: Attach

このメンバー関数を呼び出して、 *Hsocket* ハンドルをオブジェクトにアタッチし `CAsyncSocket` ます。

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>パラメーター

*hSocket*<br/>
ソケットを表すハンドルを格納します。

*lEvent*<br/>
アプリケーションが関心を持つネットワークイベントの組み合わせを指定するビットマスク。

- 読み取りの準備に関する通知を受信する FD_READ ます。

- データを読み取ることができる場合に通知を受信する FD_WRITE ます。

- 帯域外データの到着通知を受信する FD_OOB ます。

- 着信接続の通知を受信する FD_ACCEPT ます。

- 接続結果の通知を受信する FD_CONNECT ます。

- ソケットがピアによって閉じられたときに通知を受信する FD_CLOSE ます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。

### <a name="remarks"></a>解説

ソケットハンドルは、オブジェクトの [m_hSocket](#m_hsocket) データメンバーに格納されます。

## <a name="casyncsocketbind"></a><a name="bind"></a> CAsyncSocket:: Bind

ローカルアドレスをソケットに関連付けるには、このメンバー関数を呼び出します。

```
BOOL Bind(
    UINT nSocketPort,
    LPCTSTR lpszSocketAddress = NULL);

BOOL Bind (
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>パラメーター

*nSocketPort*<br/>
ソケットアプリケーションを識別するポート。

*lpszSocketAddress*<br/>
ネットワークアドレス。 "128.56.22.8" などのドットで区切られた数字です。 このパラメーターに NULL 文字列を渡すと、 `CAsyncSocket` インスタンスはすべてのネットワークインターフェイスでクライアントアクティビティをリッスンする必要があることを示します。

*lpSockAddr*<br/>
このソケットに割り当てるアドレスを格納している [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体へのポインター。

*nSockAddrLen*<br/>
*LpSockAddr* のアドレスの長さ (バイト単位)。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 次の一覧は、返される可能性のあるエラーの一部を示しています。 完全な一覧については、「 [Windows Sockets のエラーコード](/windows/win32/winsock/windows-sockets-error-codes-2)」を参照してください。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEADDRINUSE 指定されたアドレスは既に使用されています。 ( [SetSockOpt](#setsockopt)の下の SO_REUSEADDR socket オプションを参照してください。)

- WSAEFAULT *nSockAddrLen* 引数が小さすぎます ( [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体のサイズ未満)。

- かかわらず WSAEINPROGRESS Windows Sockets の呼び出しが進行中です。

- WSAEAFNOSUPPORT このポートでは、指定されたアドレスファミリがサポートされていません。

- WSAEINVAL ソケットは既にアドレスにバインドされています。

- 使用できるバッファーが不足しています。また、接続が多すぎます。

- WSAENOTSOCK 記述子はソケットではありません。

### <a name="remarks"></a>解説

このルーチンは、後続のまたはを呼び出す前に、未接続のデータグラムまたはストリームソケットで使用され `Connect` `Listen` ます。 接続要求を受け入れるには、リッスンしているサーバーソケットがポート番号を選択し、を呼び出して Windows ソケットに認識させる必要があり `Bind` ます。 `Bind` 名前のないソケットにローカル名を割り当てることにより、ソケットのローカルの関連付け (ホストアドレスとポート番号) を確立します。

## <a name="casyncsocketcasyncsocket"></a><a name="casyncsocket"></a> CAsyncSocket:: CAsyncSocket

空のソケットオブジェクトを構築します。

```
CAsyncSocket();
```

### <a name="remarks"></a>解説

オブジェクトを構築した後、その `Create` メンバー関数を呼び出してソケットデータ構造を作成し、そのアドレスをバインドする必要があります。 (Windows ソケット通信のサーバー側では、リッスンソケットが呼び出しで使用するソケットを作成するときに、 `Accept` そのソケットに対してを呼び出すことはありません `Create` )。

## <a name="casyncsocketclose"></a><a name="close"></a> CAsyncSocket:: Close

ソケットを閉じます。

```
virtual void Close();
```

### <a name="remarks"></a>解説

この関数は、ソケット記述子を解放して、それ以降の参照がエラー WSAENOTSOCK で失敗するようにします。 これが基になるソケットへの最後の参照である場合、関連付けられている名前付け情報とキューに格納されたデータは破棄されます。 ソケットオブジェクトのデストラクターがを呼び出し `Close` ます。

では、では `CAsyncSocket` ありませんが、 `CSocket` のセマンティクスは、 `Close` ソケットオプション SO_LINGER および SO_DONTLINGER によって影響を受けます。 詳細については、「メンバー関数」を参照してください `GetSockOpt` 。

## <a name="casyncsocketconnect"></a><a name="connect"></a> CAsyncSocket:: Connect

このメンバー関数を呼び出して、未接続のストリームまたはデータグラムソケットへの接続を確立します。

```
BOOL Connect(
    LPCTSTR lpszHostAddress,
    UINT nHostPort);

BOOL Connect(
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>パラメーター

*lpszHostAddress*<br/>
このオブジェクトが接続されているソケットのネットワークアドレス。 "ftp.microsoft.com" のようなコンピューター名、または "128.56.22.8" などのドット番号。

*nHostPort*<br/>
ソケットアプリケーションを識別するポート。

*lpSockAddr*<br/>
接続されたソケットのアドレスを格納している [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体へのポインター。

*nSockAddrLen*<br/>
*LpSockAddr* のアドレスの長さ (バイト単位)。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 これが WSAEWOULDBLOCK のエラーコードを示し、アプリケーションがオーバーライド可能なコールバックを使用している場合、 `OnConnect` 接続操作が完了すると、アプリケーションはメッセージを受信します。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEADDRINUSE 指定されたアドレスは既に使用されています。

- かかわらず WSAEINPROGRESS Windows Sockets の呼び出しが進行中です。

- WSAEADDRNOTAVAIL ローカルコンピューターから指定されたアドレスを使用できません。

- 指定されたファミリの WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。

- WSAECONNREFUSED 接続の試行が拒否されました。

- WSAEDESTADDRREQ 宛先アドレスが必要です。

- WSAEFAULT *nSockAddrLen* 引数が正しくありません。

- WSAEINVAL 無効なホストアドレスです。

- WSAEISCONN ソケットは既に接続されています。

- WSAEMFILE ファイル記述子を使用できません。

- この時点では、このホストからネットワークに到達できません。

- WSAは、バッファー領域を使用できません。 ソケットを接続できません。

- WSAENOTSOCK 記述子はソケットではありません。

- 接続を確立せずに、WSAETIMEDOUT の接続試行がタイムアウトしました。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされており、すぐに接続を完了することはできません。

### <a name="remarks"></a>解説

ソケットがバインド解除されている場合は、システムによってローカルの関連付けに一意の値が割り当てられ、ソケットはバインド済みとしてマークされます。 名前構造の address フィールドがすべてゼロの場合、 `Connect` は0を返します。 拡張されたエラー情報を取得するには、 `GetLastError` メンバー関数を呼び出します。

ストリームソケット (型 SOCK_STREAM) の場合、外部ホストへのアクティブな接続が開始されます。 ソケットの呼び出しが正常に完了すると、ソケットはデータを送受信する準備が整います。

データグラムソケット (型 SOCK_DGRAM) の場合、既定の宛先が設定されます。これは後続のおよび呼び出しで使用され `Send` `Receive` ます。

## <a name="casyncsocketcreate"></a><a name="create"></a> CAsyncSocket:: Create

`Create`ソケットオブジェクトを構築した後、メンバー関数を呼び出して、Windows ソケットを作成し、それをアタッチします。

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>パラメーター

*nSocketPort*<br/>
ソケットと共に使用される既知のポート。 Windows ソケットでポートを選択する場合は0。

*nSocketType*<br/>
SOCK_STREAM または SOCK_DGRAM。

*lEvent*<br/>
アプリケーションが関心を持つネットワークイベントの組み合わせを指定するビットマスク。

- 読み取りの準備に関する通知を受信する FD_READ ます。

- 書き込みの準備ができていることを通知する FD_WRITE ます。

- 帯域外データの到着通知を受信する FD_OOB ます。

- 着信接続の通知を受信する FD_ACCEPT ます。

- 完了した接続の通知を受信する FD_CONNECT ます。

- ソケットのクロージャの通知を受信する FD_CLOSE ます。

*lpszSockAddress*<br/>
接続されたソケットのネットワークアドレスを格納している文字列へのポインター ("128.56.22.8" など)。このパラメーターに NULL 文字列を渡すと、 `CAsyncSocket` インスタンスはすべてのネットワークインターフェイスでクライアントアクティビティをリッスンする必要があることを示します。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEAFNOSUPPORT 指定されたアドレスファミリはサポートされていません。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAEMFILE ファイル記述子を使用できません。

- WSAは、バッファー領域を使用できません。 ソケットを作成できません。

- WSAEPROTONOSUPPORT 指定されたポートはサポートされていません。

- WSAEPROTOTYPE 指定されたポートの種類がこのソケットに対して正しくありません。

- WSAESOCKTNOSUPPORT このアドレスファミリでは、指定されたソケットの種類がサポートされていません。

### <a name="remarks"></a>解説

`Create`[ソケット](#socket)を呼び出します。成功した場合は、 [bind](#bind)を呼び出して、ソケットを指定されたアドレスにバインドします。 次のソケットの種類がサポートされています。

- SOCK_STREAM は、シーケンス処理された信頼性の高い、完全な双方向の接続ベースのバイトストリームを提供します。 は、インターネットアドレスファミリに伝送制御プロトコル (TCP) を使用します。

- SOCK_DGRAM は、固定された (通常は小さい) 最大長の、コネクションレスで信頼性の低いパケットであるデータグラムをサポートします。 は、インターネットアドレスファミリのユーザーデータグラムプロトコル (UDP) を使用します。

    > [!NOTE]
    >  この `Accept` メンバー関数は、新しい空のオブジェクトへの参照を `CSocket` そのパラメーターとして受け取ります。 を呼び出す前に、このオブジェクトを作成する必要があり `Accept` ます。 このソケットオブジェクトがスコープ外に出ると、接続が閉じられることに注意してください。 `Create`この新しいソケットオブジェクトに対してを呼び出さないでください。

> [!IMPORTANT]
> `Create` はスレッドセーフでは **ありません** 。  複数のスレッドで同時に呼び出すことができるマルチスレッド環境で呼び出す場合は、ミューテックスまたはその他の同期ロックを使用して各呼び出しを確実に保護してください。

ストリームソケットとデータグラムソケットの詳細については、「 [Windows ソケット: バックグラウンド](../../mfc/windows-sockets-background.md) および [Windows ソケット: ポートとソケットアドレス](../../mfc/windows-sockets-ports-and-socket-addresses.md) 」および「windows [sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)」を参照してください。

## <a name="casyncsocketcreateex"></a><a name="createex"></a> CAsyncSocket:: CreateEx

`CreateEx`ソケットオブジェクトを構築した後、メンバー関数を呼び出して、Windows ソケットを作成し、それをアタッチします。

この関数は、ソケットの種類などの詳細オプションを指定する必要がある場合に使用します。

```
BOOL CreateEx(
    ADDRINFOT* pAI,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>パラメーター

*pAI*<br/>
ファミリやソケットの種類などのソケット情報を保持するための [Addrinfot](/windows/win32/api/ws2def/ns-ws2def-addrinfoa) へのポインター。

*lEvent*<br/>
アプリケーションが関心を持つネットワークイベントの組み合わせを指定するビットマスク。

- 読み取りの準備に関する通知を受信する FD_READ ます。

- 書き込みの準備ができていることを通知する FD_WRITE ます。

- 帯域外データの到着通知を受信する FD_OOB ます。

- 着信接続の通知を受信する FD_ACCEPT ます。

- 完了した接続の通知を受信する FD_CONNECT ます。

- ソケットのクロージャの通知を受信する FD_CLOSE ます。

### <a name="return-value"></a>戻り値

[Create ()](#return-value-5)の戻り値を参照してください。

### <a name="remarks"></a>解説

[Create ()](#remarks-8)については、「解説」を参照してください。

## <a name="casyncsocketdetach"></a><a name="detach"></a> CAsyncSocket::D etach

このメンバー関数を呼び出して、 *m_hSocket* データメンバー内のソケットハンドルをオブジェクトからデタッチ `CAsyncSocket` し、 *m_hSocket* を NULL に設定します。

```
SOCKET Detach();
```

## <a name="casyncsocketfromhandle"></a><a name="fromhandle"></a> CAsyncSocket:: FromHandle

オブジェクトへのポインターを返し `CAsyncSocket` ます。

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>パラメーター

*hSocket*<br/>
ソケットを表すハンドルを格納します。

### <a name="return-value"></a>戻り値

オブジェクトへのポインター `CAsyncSocket` `CAsyncSocket` 。 *hsocket* にアタッチされたオブジェクトがない場合は NULL。

### <a name="remarks"></a>解説

ソケットハンドルが指定されている場合、 `CAsyncSocket` オブジェクトがハンドルにアタッチされていない場合、メンバー関数は NULL を返します。

## <a name="casyncsocketgetlasterror"></a><a name="getlasterror"></a> CAsyncSocket:: GetLastError

このメンバー関数を呼び出して、失敗した最後の操作のエラー状態を取得します。

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>戻り値

戻り値は、このスレッドで最後に実行された Windows Sockets API ルーチンのエラーコードを示します。

### <a name="remarks"></a>解説

特定のメンバー関数がエラーが発生したことを示す場合は、 `GetLastError` 適切なエラーコードを取得するためにを呼び出す必要があります。 該当するエラーコードの一覧については、個々のメンバー関数の説明を参照してください。

エラーコードの詳細については、「 [Windows Sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)」を参照してください。

## <a name="casyncsocketgetpeername"></a><a name="getpeername"></a> CAsyncSocket:: GetPeerName

このメンバー関数を呼び出して、このソケットが接続されているピアソケットのアドレスを取得します。

```
BOOL GetPeerName(
    CString& rPeerAddress,
    UINT& rPeerPort);

BOOL GetPeerName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>パラメーター

*rPeerAddress*<br/>
`CString`ドット形式の IP アドレスを受け取るオブジェクトへの参照。

*rPeerPort*<br/>
ポートを格納する UINT への参照。

*lpSockAddr*<br/>
ピアソケットの名前を受け取る [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体へのポインター。

*lpSockAddrLen*<br/>
*LpSockAddr* 内のアドレスの長さをバイト単位で示すポインター。 返されると、 *lpSockAddrLen* 引数には、返された *lpSockAddr* の実際のサイズがバイト単位で格納されます。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEFAULT *lpSockAddrLen* 引数の大きさが十分ではありません。

- かかわらず WSAEINPROGRESS Windows Sockets の呼び出しが進行中です。

- WSAENOTCONN ソケットが接続されていません。

- WSAENOTSOCK 記述子はソケットではありません。

### <a name="remarks"></a>解説

IPv6 アドレスを処理するには、 [CAsyncSocket:: GetPeerNameEx](#getpeernameex)を使用します。

## <a name="casyncsocketgetpeernameex"></a><a name="getpeernameex"></a> CAsyncSocket:: GetPeerNameEx

このメンバー関数を呼び出して、このソケットが接続されているピアソケットのアドレスを取得します (IPv6 アドレスを処理します)。

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>パラメーター

*rPeerAddress*<br/>
`CString`ドット形式の IP アドレスを受け取るオブジェクトへの参照。

*rPeerPort*<br/>
ポートを格納する UINT への参照。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEFAULT *lpSockAddrLen* 引数の大きさが十分ではありません。

- かかわらず WSAEINPROGRESS Windows Sockets の呼び出しが進行中です。

- WSAENOTCONN ソケットが接続されていません。

- WSAENOTSOCK 記述子はソケットではありません。

### <a name="remarks"></a>解説

この関数は、IPv6 アドレスおよび古いプロトコルを処理することを除いて、 [CAsyncSocket:: GetPeerName](#getpeername) と同じです。

## <a name="casyncsocketgetsockname"></a><a name="getsockname"></a> CAsyncSocket:: GetSockName

このメンバー関数を呼び出して、ソケットのローカル名を取得します。

```
BOOL GetSockName(
    CString& rSocketAddress,
    UINT& rSocketPort);

BOOL GetSockName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>パラメーター

*rSocketAddress*<br/>
`CString`ドット形式の IP アドレスを受け取るオブジェクトへの参照。

*rSocketPort*<br/>
ポートを格納する UINT への参照。

*lpSockAddr*<br/>
ソケットのアドレスを受け取る [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体へのポインター。

*lpSockAddrLen*<br/>
*LpSockAddr* 内のアドレスの長さをバイト単位で示すポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEFAULT *lpSockAddrLen* 引数の大きさが十分ではありません。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEINVAL ソケットは、アドレスにバインドされていません `Bind` 。

### <a name="remarks"></a>解説

この呼び出しは、 `Connect` 最初のを実行せずに呼び出しが行われた場合に特に便利です `Bind` 。この呼び出しでは、システムによって設定されたローカルの関連付けを特定できる唯一の手段が提供されます。

IPv6 アドレスを処理するには、 [CAsyncSocket:: GetSockNameEx](#getsocknameex)を使用します。

## <a name="casyncsocketgetsocknameex"></a><a name="getsocknameex"></a> CAsyncSocket:: GetSockNameEx

このメンバー関数を呼び出して、ソケットのローカル名を取得します (IPv6 アドレスを処理します)。

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>パラメーター

*rSocketAddress*<br/>
`CString`ドット形式の IP アドレスを受け取るオブジェクトへの参照。

*rSocketPort*<br/>
ポートを格納する UINT への参照。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEFAULT *lpSockAddrLen* 引数の大きさが十分ではありません。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEINVAL ソケットは、アドレスにバインドされていません `Bind` 。

### <a name="remarks"></a>解説

この呼び出しは [CAsyncSocket:: GetSockName](#getsockname) と同じですが、IPv6 アドレスおよび古いプロトコルを処理する点が異なります。

この呼び出しは、 `Connect` 最初のを実行せずに呼び出しが行われた場合に特に便利です `Bind` 。この呼び出しでは、システムによって設定されたローカルの関連付けを特定できる唯一の手段が提供されます。

## <a name="casyncsocketgetsockopt"></a><a name="getsockopt"></a> CAsyncSocket:: GetSockOpt

ソケットオプションを取得するには、このメンバー関数を呼び出します。

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>パラメーター

*nOptionName*<br/>
値の取得対象となるソケットオプション。

*lpOptionValue*<br/>
要求されたオプションの値が返されるバッファーへのポインター。 選択したオプションに関連付けられている値は、バッファー *lpOptionValue* で返されます。 *Lpoptionlen* が指す整数には、最初にこのバッファーのサイズをバイト単位で格納する必要があります。返されると、返される値のサイズに設定されます。 SO_LINGER の場合、これは構造体のサイズになります `LINGER` 。他のすべてのオプションについては、 **`int`** オプションに応じて BOOL またはのサイズになります。 オプションとそのサイズの一覧については、「解説」を参照してください。

*lpOptionLen*<br/>
*LpOptionValue* バッファーのサイズ (バイト単位) へのポインター。

*nLevel*<br/>
オプションが定義されているレベル。サポートされているレベルは SOL_SOCKET と IPPROTO_TCP のみです。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 オプションがで設定されていない場合 `SetSockOpt` 、は `GetSockOpt` オプションの既定値を返します。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEFAULT *Lpoptionlen* 引数が無効でした。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAENOPROTOOPT オプションは不明またはサポートされていません。 特に、SO_BROADCAST は SOCK_STREAM 型のソケットではサポートされていませんが、SO_ACCEPTCONN、SO_DONTLINGER、SO_KEEPALIVE、SO_LINGER、SO_OOBINLINE は型のソケットではサポートされていません。

- WSAENOTSOCK 記述子はソケットではありません。

### <a name="remarks"></a>解説

`GetSockOpt` 任意の型のソケットに関連付けられているソケットオプションの現在の値を任意の状態で取得し、その結果を *lpOptionValue* に格納します。 オプションは、パケットのルーティング、帯域外のデータ転送などのソケット操作に影響します。

では、次のオプションがサポートされてい `GetSockOpt` ます。 この型は、 *lpOptionValue* によってアドレス指定されるデータの種類を識別します。 TCP_NODELAY オプションは level IPPROTO_TCP を使用します。その他のすべてのオプションでは、レベル SOL_SOCKET を使用します。

|値|Type|説明|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|ソケットがリッスンしています。|
|SO_BROADCAST|BOOL|ソケットは、ブロードキャストメッセージを転送するように構成されています。|
|SO_DEBUG|BOOL|デバッグが有効になっています。|
|SO_DONTLINGER|BOOL|True の場合、SO_LINGER オプションは無効になります。|
|SO_DONTROUTE|BOOL|ルーティングは無効になっています。|
|SO_ERROR|**`int`**|エラーの状態を取得してクリアします。|
|SO_KEEPALIVE|BOOL|キープアライブが送信されています。|
|SO_LINGER|`struct LINGER`|現在の待機オプションを返します。|
|SO_OOBINLINE|BOOL|通常のデータストリームで帯域外データを受信しています。|
|SO_RCVBUF|INT|受信のバッファーサイズ。|
|SO_REUSEADDR|BOOL|ソケットは、既に使用されているアドレスにバインドできます。|
|SO_SNDBUF|**`int`**|送信のバッファーサイズ。|
|SO_TYPE|**`int`**|ソケットの種類 (SOCK_STREAM など)。|
|TCP_NODELAY|BOOL|送信結合用の Nagle アルゴリズムを無効にします。|

でサポートされていないソフトウェア配布 (BSD) のオプション `GetSockOpt` は次のとおりです。

|値|Type|説明|
|-----------|----------|-------------|
|SO_RCVLOWAT|**`int`**|低いウォーターマークを受け取ります。|
|SO_RCVTIMEO|**`int`**|受信タイムアウト。|
|SO_SNDLOWAT|**`int`**|低いウォーターマークを送信します。|
|SO_SNDTIMEO|**`int`**|送信タイムアウト。|
|IP_OPTIONS||IP ヘッダーのオプションを取得します。|
|TCP_MAXSEG|**`int`**|TCP セグメントの最大サイズを取得します。|

`GetSockOpt`サポートされていないオプションを指定してを呼び出すと、から返される WSAENOPROTOOPT のエラーコードが発生 `GetLastError` します。

## <a name="casyncsocketioctl"></a><a name="ioctl"></a> CAsyncSocket:: IOCtl

ソケットのモードを制御するには、このメンバー関数を呼び出します。

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>パラメーター

*lCommand*<br/>
ソケットに対して実行するコマンドです。

*lpArgument*<br/>
*Lcommand* のパラメーターへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEINVAL *lcommand* が有効なコマンドではないか、 *LpArgument* が *lcommand* に使用できるパラメーターではないか、コマンドが指定されたソケットの種類に適用できません。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAENOTSOCK 記述子はソケットではありません。

### <a name="remarks"></a>解説

このルーチンは、任意の状態の任意のソケットで使用できます。 これは、プロトコルおよび通信サブシステムとは関係なく、ソケットに関連付けられている操作パラメーターを取得または取得するために使用されます。 次のコマンドがサポートされています。

- FIONBIO ソケットで非ブロッキングモードを有効または無効にします。 *LpArgument* パラメーターは、非 `DWORD` ブロッキングモードを有効にする場合は0以外、無効にする場合は0をポイントします。 `AsyncSelect`がソケットで発行されている場合、を使用して `IOCtl` ソケットをブロッキングモードに戻すと、wsaeinval では失敗します。 ソケットをブロックモードに戻して、WSAEINVAL エラーが発生しないようにするには、LEvent パラメーターを0に設定してを呼び出してアプリケーションを最初に無効にし `AsyncSelect` てから、を `AsyncSelect` 呼び出し `IOCtl` ます。

- FIONREAD このソケットからの1回の呼び出しで読み取ることができる最大バイト数を決定 `Receive` します。 *LpArgument* パラメーターは、 `DWORD` 結果を格納するのをポイントし `IOCtl` ます。 このソケットの種類が SOCK_STREAM の場合、FIONREAD は、1つので読み取ることができるデータの合計量を返します `Receive` 。これは通常、ソケットでキューに入れられたデータの合計量と同じです。 このソケットの種類が SOCK_DGRAM の場合、FIONREAD は、ソケットでキューに置かれた最初のデータグラムのサイズを返します。

- SIOCATMARK は、帯域外のすべてのデータが読み取られたかどうかを判断します。 これは、帯域外データ (SO_OOBINLINE) のインライン受信用に構成されている SOCK_STREAM 種類のソケットにのみ適用されます。 帯域外のデータが読み取られるのを待機していない場合、この操作は0以外の値を返します。 それ以外の場合は0を返し、次の `Receive` または `ReceiveFrom` ソケットで実行されるデータの一部またはすべてを "マーク" の前に取得します。アプリケーションは、SIOCATMARK 操作を使用して、データが残っているかどうかを判断する必要があります。 "緊急" (帯域外) データの前に通常のデータがある場合は、順番に受信されます。 ( `Receive` またはは、 `ReceiveFrom` 同じ呼び出しで帯域外データと通常のデータを混在させないことに注意してください)。 *LpArgument* パラメーターは、 `DWORD` 結果を格納するのをポイントし `IOCtl` ます。

この関数は、 `ioctl()` バークレーソケットで使用されるのサブセットです。 特に、FIOASYNC に相当するコマンドはありませんが、SIOCATMARK はサポートされている唯一のソケットレベルのコマンドです。

## <a name="casyncsocketlisten"></a><a name="listen"></a> CAsyncSocket:: Listen

このメンバー関数を呼び出して、着信接続要求をリッスンします。

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>パラメーター

*nConnectionBacklog ログ*<br/>
保留中の接続のキューが拡張できる最大長。 有効な範囲は 1 ~ 5 です。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEADDRINUSE 使用中のアドレスをリッスンしようとしました。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAEINVAL ソケットがにバインドされていないか、既に接続されてい `Bind` ます。

- WSAEISCONN ソケットは既に接続されています。

- WSAEMFILE ファイル記述子を使用できません。

- WSAは、バッファー領域を使用できません。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEOPNOTSUPP 参照されているソケットが、操作をサポートする型ではありません `Listen` 。

### <a name="remarks"></a>解説

接続を受け入れるには、ソケットがで最初に作成され、 `Create` 着信接続のバックログがで指定され `Listen` ます。その後、接続はで受け入れられ `Accept` ます。 `Listen` 接続をサポートするソケット、つまり SOCK_STREAM 型のソケットにのみ適用されます。 このソケットは "パッシブ" モードになります。このモードでは、着信接続が受信確認され、プロセスによって保留されていることが確認されます。

通常、この関数は、一度に複数の接続要求を持つ可能性があるサーバー (または接続を受け入れる任意のアプリケーション) によって使用されます。接続要求がキューいっぱいに到着すると、クライアントは WSAECONNREFUSED を示すエラーを受け取ります。

`Listen` 使用可能なポート (記述子) がない場合に、引き続き合理的の機能を試行します。 キューが空になるまで、接続が受け入れられます。 ポートが使用可能になると、後でまたはを呼び出すと、 `Listen` `Accept` 可能な場合は現在または最新の "バックログ" にキューが補充され、着信接続のリッスンが再開されます。

## <a name="casyncsocketm_hsocket"></a><a name="m_hsocket"></a> CAsyncSocket:: m_hSocket

このオブジェクトによってカプセル化されるソケットのソケットハンドルを格納し `CAsyncSocket` ます。

```
SOCKET m_hSocket;
```

## <a name="casyncsocketonaccept"></a><a name="onaccept"></a> CAsyncSocket:: OnAccept

[Accept](#accept)メンバー関数を呼び出すことによって、保留中の接続要求を受け入れることができることをリッスンするソケットに通知するために、フレームワークによって呼び出されます。

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*nErrorCode*<br/>
ソケットでの最新のエラー。 次のエラーコードは、メンバー関数に適用され `OnAccept` ます。

- **0** 関数は正常に実行されました。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

## <a name="casyncsocketonclose"></a><a name="onclose"></a> CAsyncSocket:: OnClose

接続されたソケットがプロセスによって閉じられたことをこのソケットに通知するために、フレームワークによって呼び出されます。

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*nErrorCode*<br/>
ソケットでの最新のエラー。 次のエラーコードは、メンバー関数に適用され `OnClose` ます。

- **0** 関数は正常に実行されました。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAECONNRESET リモート側によって接続がリセットされました。

- WSAECONNABORTED タイムアウトまたはその他のエラーにより、接続が中止されました。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

## <a name="casyncsocketonconnect"></a><a name="onconnect"></a> CAsyncSocket:: OnConnect

正常に実行されたか、エラーが発生したかにかかわらず、接続試行が完了したことをこの接続ソケットに通知するために、フレームワークによって呼び出されます。

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*nErrorCode*<br/>
ソケットでの最新のエラー。 次のエラーコードは、メンバー関数に適用され `OnConnect` ます。

- **0** 関数は正常に実行されました。

- WSAEADDRINUSE 指定されたアドレスは既に使用されています。

- WSAEADDRNOTAVAIL ローカルコンピューターから指定されたアドレスを使用できません。

- 指定されたファミリの WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。

- WSAECONNREFUSED 接続の試行が強制的に拒否されました。

- WSAEDESTADDRREQ 宛先アドレスが必要です。

- WSAEFAULT *lpSockAddrLen* 引数が正しくありません。

- WSAEINVAL ソケットは既にアドレスにバインドされています。

- WSAEISCONN ソケットは既に接続されています。

- WSAEMFILE ファイル記述子を使用できません。

- この時点では、このホストからネットワークに到達できません。

- WSAは、バッファー領域を使用できません。 ソケットを接続できません。

- WSAENOTCONN ソケットが接続されていません。

- WSAENOTSOCK 記述子は、ソケットではなくファイルです。

- WSAETIMEDOUT 接続を確立せずに接続の試行がタイムアウトしました。

### <a name="remarks"></a>解説

> [!NOTE]
> [CSocket](../../mfc/reference/csocket-class.md)では、 `OnConnect` 通知関数は呼び出されません。 接続の場合は、を呼び出すだけです `Connect` 。接続が完了すると (正常にまたはエラーが発生)、が返されます。 接続通知の処理方法は、MFC 実装の詳細です。

詳細については、「 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

## <a name="casyncsocketonoutofbanddata"></a><a name="onoutofbanddata"></a> CAsyncSocket:: OnOutOfBandData

送信ソケットが帯域外データを送信することを受信ソケットに通知するために、フレームワークによって呼び出されます。

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*nErrorCode*<br/>
ソケットでの最新のエラー。 次のエラーコードは、メンバー関数に適用され `OnOutOfBandData` ます。

- **0** 関数は正常に実行されました。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

### <a name="remarks"></a>解説

帯域外データは、SOCK_STREAM 種類の接続されたソケットの各ペアに関連付けられている論理的に独立したチャネルです。 チャネルは、通常、緊急データを送信するために使用されます。

MFC は帯域外データをサポートしますが、クラスのユーザー `CAsyncSocket` には使用しないことをお勧めします。 より簡単な方法は、このようなデータを渡すための2番目のソケットを作成することです。 帯域外データの詳細については、「 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

## <a name="casyncsocketonreceive"></a><a name="onreceive"></a> CAsyncSocket:: OnReceive

メンバー関数を呼び出すことによって取得できるデータがバッファーに存在することをこのソケットに通知するために、フレームワークによって呼び出され `Receive` ます。

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*nErrorCode*<br/>
ソケットでの最新のエラー。 次のエラーコードは、メンバー関数に適用され `OnReceive` ます。

- **0** 関数は正常に実行されました。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

## <a name="casyncsocketonsend"></a><a name="onsend"></a> CAsyncSocket:: OnSend

メンバー関数を呼び出すことによってデータを送信できるようになったことをソケットに通知するために、フレームワークによって呼び出され `Send` ます。

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*nErrorCode*<br/>
ソケットでの最新のエラー。 次のエラーコードは、メンバー関数に適用され `OnSend` ます。

- **0** 関数は正常に実行されました。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

## <a name="casyncsocketoperator-"></a><a name="operator_eq"></a> CAsyncSocket:: operator =

オブジェクトに新しい値を割り当て `CAsyncSocket` ます。

```cpp
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>パラメーター

*.Rsrc*<br/>
既存のオブジェクトへの参照 `CAsyncSocket` 。

### <a name="remarks"></a>解説

既存の `CAsyncSocket` オブジェクトを別のオブジェクトにコピーするには、この関数を呼び出し `CAsyncSocket` ます。

## <a name="casyncsocketoperator-socket"></a><a name="operator_socket"></a> CAsyncSocket:: operator SOCKET

オブジェクトのソケットハンドルを取得するには、この演算子を使用し `CAsyncSocket` ます。

```
operator SOCKET() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、ソケットオブジェクトのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

ハンドルを使用すると、Windows Api を直接呼び出すことができます。

## <a name="casyncsocketreceive"></a><a name="receive"></a> CAsyncSocket:: Receive

ソケットからデータを受信するには、このメンバー関数を呼び出します。

```
virtual int Receive(
    void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
受信データのバッファー。

*nBufLen*<br/>
*Lpbuf* の長さ (バイト単位)。

*nFlags*<br/>
呼び出しを行う方法を指定します。 この関数のセマンティクスは、socket オプションと *nFlags* パラメーターによって決まります。 後者は、次のいずれかの値を C++ **または** 演算子と組み合わせることによって作成されます。

- 受信データをピーク MSG_PEEK ます。 データはバッファーにコピーされますが、入力キューからは削除されません。

- 帯域外データを処理 MSG_OOB。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は、 `Receive` 受信したバイト数を返します。 接続が閉じられている場合は、0を返します。 それ以外の場合は SOCKET_ERROR の値が返され、 [GetLastError](#getlasterror)を呼び出すことによって特定のエラーコードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAENOTCONN ソケットが接続されていません。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットの種類が SOCK_STREAM ではありません。

- WSAESHUTDOWN ソケットがシャットダウンされました。 `Receive` `ShutDown` *nhow* を0または2に設定してを呼び出した後に、ソケットでを呼び出すことはできません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、操作はブロックされ `Receive` ます。

- WSAEMSGSIZE は、データグラムが大きすぎて指定されたバッファーに収まりませんでしたが、切り捨てられました。

- WSAEINVAL ソケットがにバインドされていません `Bind` 。

- タイムアウトまたはその他のエラーが原因で仮想回線が中止された WSAECONNABORTED。

- WSAECONNRESET リモート側によって仮想回線がリセットされました。

### <a name="remarks"></a>解説

この関数は、接続されているストリームまたはデータグラムソケットに対して使用され、受信データを読み取るために使用されます。

SOCK_STREAM 型のソケットの場合は、指定されたバッファーのサイズまで現在使用できるほど多くの情報が返されます。 ソケットが帯域外データのインライン受信用に構成されていて (ソケットオプション SO_OOBINLINE)、帯域外データが未読の場合は、帯域外データのみが返されます。 アプリケーションで `IOCtlSIOCATMARK` は、オプションまたは [OnOutOfBandData](#onoutofbanddata) を使用して、帯域外のデータが残っていないかどうかを確認できます。

データグラムソケットの場合、データは、指定されたバッファーのサイズまでの最初のエンキューされたデータグラムから抽出されます。 データグラムが指定されたバッファーよりも大きい場合、バッファーにはデータグラムの最初の部分が格納され、余分なデータは失われ、 `Receive` WSAEMSGSIZE に設定されたエラーコードと共に SOCKET_ERROR の値が返されます。 ソケットに受信データが使用できない場合は、WSAEWOULDBLOCK に設定されたエラーコードと共に SOCKET_ERROR の値が返されます。 [OnReceive](#onreceive) callback 関数を使用すると、より多くのデータが到着したかどうかを判断できます。

ソケットの種類が SOCK_STREAM で、リモート側が正常に接続をシャットダウンした場合、は、 `Receive` 受信した0バイトですぐに完了します。 接続がリセットされている場合、は `Receive` エラー WSAECONNRESET で失敗します。

`Receive`[CAsyncSocket:: OnReceive](#onreceive)が呼び出されるたびに1回だけ呼び出す必要があります。

### <a name="example"></a>例

  [CAsyncSocket:: OnReceive](#onreceive)の例を参照してください。

## <a name="casyncsocketreceivefrom"></a><a name="receivefrom"></a> CAsyncSocket:: ReceiveFrom

データグラムを受信し、そのソースアドレスを [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体または *rsocketaddress* に格納するには、このメンバー関数を呼び出します。

```
int ReceiveFrom(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);

int ReceiveFrom(
    void* lpBuf,
    int nBufLen,
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen,
    int nFlags = 0);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
受信データのバッファー。

*nBufLen*<br/>
*Lpbuf* の長さ (バイト単位)。

*rSocketAddress*<br/>
`CString`ドット形式の IP アドレスを受け取るオブジェクトへの参照。

*rSocketPort*<br/>
ポートを格納する UINT への参照。

*lpSockAddr*<br/>
返されたときにソースアドレスを保持する [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体へのポインター。

*lpSockAddrLen*<br/>
*LpSockAddr* の送信元アドレスの長さ (バイト単位) へのポインター。

*nFlags*<br/>
呼び出しを行う方法を指定します。 この関数のセマンティクスは、socket オプションと *nFlags* パラメーターによって決まります。 後者は、次のいずれかの値を C++ **または** 演算子と組み合わせることによって作成されます。

- 受信データをピーク MSG_PEEK ます。 データはバッファーにコピーされますが、入力キューからは削除されません。

- 帯域外データを処理 MSG_OOB。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は、 `ReceiveFrom` 受信したバイト数を返します。 接続が閉じられている場合は、0を返します。 それ以外の場合は SOCKET_ERROR の値が返され、を呼び出すことによって特定のエラーコードを取得でき `GetLastError` ます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEFAULT *lpSockAddrLen* 引数が無効でした: *lpSockAddr* バッファーが小さすぎてピアアドレスを格納できませんでした。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAEINVAL ソケットがにバインドされていません `Bind` 。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAM のみ)。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットの種類が SOCK_STREAM ではありません。

- WSAESHUTDOWN ソケットがシャットダウンされました。 `ReceiveFrom` `ShutDown` *nhow* を0または2に設定してを呼び出した後に、ソケットでを呼び出すことはできません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、操作はブロックされ `ReceiveFrom` ます。

- WSAEMSGSIZE は、データグラムが大きすぎて指定されたバッファーに収まりませんでしたが、切り捨てられました。

- タイムアウトまたはその他のエラーが原因で仮想回線が中止された WSAECONNABORTED。

- WSAECONNRESET リモート側によって仮想回線がリセットされました。

### <a name="remarks"></a>解説

この関数は、(接続されている可能性がある) ソケットで受信データを読み取り、データの送信元のアドレスをキャプチャするために使用されます。

IPv6 アドレスを処理するには、 [CAsyncSocket:: ReceiveFromEx](#receivefromex)を使用します。

SOCK_STREAM 型のソケットの場合は、指定されたバッファーのサイズまで現在使用できるほど多くの情報が返されます。 ソケットが帯域外データのインライン受信用に構成されていて (ソケットオプション SO_OOBINLINE)、帯域外データが未読の場合は、帯域外データのみが返されます。 アプリケーションで `IOCtlSIOCATMARK` は、オプションまたはを使用して、 `OnOutOfBandData` 帯域外のデータが読み取られていないかどうかを判断できます。 SOCK_STREAM ソケットの場合、 *lpSockAddr* パラメーターと *lpSockAddrLen* パラメーターは無視されます。

データグラムソケットの場合、データは、指定されたバッファーのサイズまでの最初のエンキューされたデータグラムから抽出されます。 データグラムが、指定されたバッファーより大きい場合、バッファーにはメッセージの最初の部分が格納され、余分なデータは失われ、 `ReceiveFrom` エラーコードが WSAEMSGSIZE に設定された SOCKET_ERROR の値が返されます。

*LpSockAddr* が0以外の場合、ソケットの種類が SOCK_DGRAM の場合は、データを送信したソケットのネットワークアドレスが対応する [SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体にコピーされます。 *LpSockAddrLen* によってポイントされる値は、この構造体のサイズに初期化され、そこに格納されているアドレスの実際のサイズを示すために返されます。 ソケットで受信データが使用できない場合、 `ReceiveFrom` ソケットが非ブロッキングでない限り、呼び出しはデータの到着を待機します。 この場合、SOCKET_ERROR の値が返され、エラーコードは WSAEWOULDBLOCK に設定されます。 `OnReceive`コールバックを使用すると、より多くのデータが到着したかどうかを判断できます。

ソケットの種類が SOCK_STREAM で、リモート側が正常に接続をシャットダウンした場合、は、 `ReceiveFrom` 受信した0バイトですぐに完了します。

## <a name="casyncsocketreceivefromex"></a><a name="receivefromex"></a> CAsyncSocket:: ReceiveFromEx

このメンバー関数を呼び出して、データグラムを受信し、送信元アドレスを [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体または *rsocketaddress* (IPv6 アドレスを処理) に格納します。

```
int ReceiveFromEx(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
受信データのバッファー。

*nBufLen*<br/>
*Lpbuf* の長さ (バイト単位)。

*rSocketAddress*<br/>
`CString`ドット形式の IP アドレスを受け取るオブジェクトへの参照。

*rSocketPort*<br/>
ポートを格納する UINT への参照。

*nFlags*<br/>
呼び出しを行う方法を指定します。 この関数のセマンティクスは、socket オプションと *nFlags* パラメーターによって決まります。 後者は、次のいずれかの値を C++ **または** 演算子と組み合わせることによって作成されます。

- 受信データをピーク MSG_PEEK ます。 データはバッファーにコピーされますが、入力キューからは削除されません。

- 帯域外データを処理 MSG_OOB。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は、 `ReceiveFromEx` 受信したバイト数を返します。 接続が閉じられている場合は、0を返します。 それ以外の場合は SOCKET_ERROR の値が返され、を呼び出すことによって特定のエラーコードを取得でき `GetLastError` ます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEFAULT *lpSockAddrLen* 引数が無効でした: *lpSockAddr* バッファーが小さすぎてピアアドレスを格納できませんでした。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAEINVAL ソケットがにバインドされていません `Bind` 。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAM のみ)。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットの種類が SOCK_STREAM ではありません。

- WSAESHUTDOWN ソケットがシャットダウンされました。 `ReceiveFromEx` `ShutDown` *nhow* を0または2に設定してを呼び出した後に、ソケットでを呼び出すことはできません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、操作はブロックされ `ReceiveFromEx` ます。

- WSAEMSGSIZE は、データグラムが大きすぎて指定されたバッファーに収まりませんでしたが、切り捨てられました。

- タイムアウトまたはその他のエラーが原因で仮想回線が中止された WSAECONNABORTED。

- WSAECONNRESET リモート側によって仮想回線がリセットされました。

### <a name="remarks"></a>解説

この関数は、(接続されている可能性がある) ソケットで受信データを読み取り、データの送信元のアドレスをキャプチャするために使用されます。

この関数は、IPv6 アドレスおよび古いプロトコルを処理する点を除いて、 [CAsyncSocket:: ReceiveFrom](#receivefrom) と同じです。

SOCK_STREAM 型のソケットの場合は、指定されたバッファーのサイズまで現在使用できるほど多くの情報が返されます。 ソケットが帯域外データのインライン受信用に構成されていて (ソケットオプション SO_OOBINLINE)、帯域外データが未読の場合は、帯域外データのみが返されます。 アプリケーションで `IOCtlSIOCATMARK` は、オプションまたはを使用して、 `OnOutOfBandData` 帯域外のデータが読み取られていないかどうかを判断できます。 SOCK_STREAM ソケットの場合、 *lpSockAddr* パラメーターと *lpSockAddrLen* パラメーターは無視されます。

データグラムソケットの場合、データは、指定されたバッファーのサイズまでの最初のエンキューされたデータグラムから抽出されます。 データグラムが、指定されたバッファーより大きい場合、バッファーにはメッセージの最初の部分が格納され、余分なデータは失われ、 `ReceiveFromEx` エラーコードが WSAEMSGSIZE に設定された SOCKET_ERROR の値が返されます。

*LpSockAddr* が0以外の場合、ソケットの種類が SOCK_DGRAM の場合は、データを送信したソケットのネットワークアドレスが対応する [SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体にコピーされます。 *LpSockAddrLen* によってポイントされる値は、この構造体のサイズに初期化され、そこに格納されているアドレスの実際のサイズを示すために返されます。 ソケットで受信データが使用できない場合、 `ReceiveFromEx` ソケットが非ブロッキングでない限り、呼び出しはデータの到着を待機します。 この場合、SOCKET_ERROR の値が返され、エラーコードは WSAEWOULDBLOCK に設定されます。 `OnReceive`コールバックを使用すると、より多くのデータが到着したかどうかを判断できます。

ソケットの種類が SOCK_STREAM で、リモート側が正常に接続をシャットダウンした場合、は、 `ReceiveFromEx` 受信した0バイトですぐに完了します。

## <a name="casyncsocketsend"></a><a name="send"></a> CAsyncSocket:: Send

接続されたソケットでデータを送信するには、このメンバー関数を呼び出します。

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
転送されるデータを格納しているバッファー。

*nBufLen*<br/>
*Lpbuf* 内のデータの長さ (バイト単位)。

*nFlags*<br/>
呼び出しを行う方法を指定します。 この関数のセマンティクスは、socket オプションと *nFlags* パラメーターによって決まります。 後者は、次のいずれかの値を C++ **または** 演算子と組み合わせることによって作成されます。

- MSG_DONTROUTE は、データをルーティングの対象にしないことを指定します。 Windows ソケットの供給業者は、このフラグを無視することを選択できます。

- 帯域外データの送信 MSG_OOB (SOCK_STREAM のみ)。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は、 `Send` 送信された合計文字数を返します。 (これは、 *Nbuflen* によって示される数値よりも小さくなる可能性があることに注意してください)。それ以外の場合は SOCKET_ERROR の値が返され、 [GetLastError](#getlasterror)を呼び出すことによって特定のエラーコードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEACCES は、要求されたアドレスがブロードキャストアドレスですが、適切なフラグが設定されていませんでした。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAEFAULT *Lpbuf* 引数は、ユーザーアドレス空間の有効な部分に含まれていません。

- Windows ソケットの実装によって接続が削除されたため、接続をリセットする必要があります。

- WSAの Windows ソケット実装では、バッファーのデッドロックが報告されます。

- WSAENOTCONN ソケットが接続されていません。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットの種類が SOCK_STREAM ではありません。

- WSAESHUTDOWN ソケットがシャットダウンされました。 `Send` `ShutDown` *nhow* を1または2に設定してを呼び出した後に、ソケットでを呼び出すことはできません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、要求された操作はブロックされます。

- WSAEMSGSIZE はソケットの種類が SOCK_DGRAM で、データグラムが Windows Sockets 実装でサポートされている最大値を超えています。

- WSAEINVAL ソケットがにバインドされていません `Bind` 。

- タイムアウトまたはその他のエラーが原因で仮想回線が中止された WSAECONNABORTED。

- WSAECONNRESET リモート側によって仮想回線がリセットされました。

### <a name="remarks"></a>解説

`Send` は、接続されているストリームまたはデータグラムソケットで送信データを書き込むために使用されます。 データグラムソケットの場合は、基になるサブネットの最大 IP パケットサイズを超えないように注意する必要があり `iMaxUdpDg` ます。これは、によって返される [WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) 構造体の要素によって指定され `AfxSocketInit` ます。 データが長すぎて、基になるプロトコルを使用してアトミックに渡すことができない場合、エラー WSAEMSGSIZE はによって返され、 `GetLastError` データは送信されません。

データグラムソケットの場合、が正常に完了して `Send` も、データが正常に配信されたことは示されないことに注意してください。

`CAsyncSocket`SOCK_STREAM 型のオブジェクトでは、ローカルホストと外部ホストの両方でのバッファーの可用性に応じて、1から要求された長さまでのバイト数を指定できます。

### <a name="example"></a>例

  [CAsyncSocket:: OnSend](#onsend)の例を参照してください。

## <a name="casyncsocketsendto"></a><a name="sendto"></a> CAsyncSocket:: SendTo

このメンバー関数を呼び出して、特定の宛先にデータを送信します。

```
int SendTo(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);

int SendTo(
    const void* lpBuf,
    int nBufLen,
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen,
    int nFlags = 0);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
転送されるデータを格納しているバッファー。

*nBufLen*<br/>
*Lpbuf* 内のデータの長さ (バイト単位)。

*nHostPort*<br/>
ソケットアプリケーションを識別するポート。

*lpszHostAddress*<br/>
このオブジェクトが接続されているソケットのネットワークアドレス。 "ftp.microsoft.com" などのコンピューター名、または "128.56.22.8" などのドット番号。

*nFlags*<br/>
呼び出しを行う方法を指定します。 この関数のセマンティクスは、socket オプションと *nFlags* パラメーターによって決まります。 後者は、次のいずれかの値を C++ **または** 演算子と組み合わせることによって作成されます。

- MSG_DONTROUTE は、データをルーティングの対象にしないことを指定します。 Windows ソケットの供給業者は、このフラグを無視することを選択できます。

- 帯域外データの送信 MSG_OOB (SOCK_STREAM のみ)。

*lpSockAddr*<br/>
ターゲットソケットのアドレスを格納している [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体へのポインター。

*nSockAddrLen*<br/>
*LpSockAddr* のアドレスの長さ (バイト単位)。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は、 `SendTo` 送信された合計文字数を返します。 (これは、 *Nbuflen* によって示される数値よりも小さくなる可能性があることに注意してください)。それ以外の場合は SOCKET_ERROR の値が返され、 [GetLastError](#getlasterror)を呼び出すことによって特定のエラーコードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEACCES は、要求されたアドレスがブロードキャストアドレスですが、適切なフラグが設定されていませんでした。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAEFAULT は、 *Lpbuf* または *lpSockAddr* パラメーターがユーザーアドレス空間に含まれていないか、 *lpSockAddr* 引数が小さすぎる ( [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体のサイズ未満)。

- WSAEINVAL ホスト名が無効です。

- Windows ソケットの実装によって接続が削除されたため、接続をリセットする必要があります。

- WSAの Windows ソケット実装では、バッファーのデッドロックが報告されます。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAM のみ)。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットの種類が SOCK_STREAM ではありません。

- WSAESHUTDOWN ソケットがシャットダウンされました。 `SendTo` `ShutDown` *nhow* を1または2に設定してを呼び出した後に、ソケットでを呼び出すことはできません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、要求された操作はブロックされます。

- WSAEMSGSIZE はソケットの種類が SOCK_DGRAM で、データグラムが Windows Sockets 実装でサポートされている最大値を超えています。

- タイムアウトまたはその他のエラーが原因で仮想回線が中止された WSAECONNABORTED。

- WSAECONNRESET リモート側によって仮想回線がリセットされました。

- WSAEADDRNOTAVAIL ローカルコンピューターから指定されたアドレスを使用できません。

- 指定されたファミリの WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。

- WSAEDESTADDRREQ 宛先アドレスが必要です。

- この時点では、このホストからネットワークに到達できません。

### <a name="remarks"></a>解説

`SendTo` は、データグラムソケットまたはストリームソケットで使用され、ソケットで送信データを書き込むために使用されます。 データグラムソケットの場合は、基になるサブネットの最大 IP パケットサイズを超えないように注意する必要があります。これは、 `iMaxUdpDg` [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)によって入力される[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata)構造体の要素によって指定されます。 データが長すぎて、基になるプロトコルを使用してアトミックに渡すことができない場合、エラー WSAEMSGSIZE が返され、データは送信されません。

が正常に完了したことは、 `SendTo` データが正常に配信されたことを示していないことに注意してください。

`SendTo` は、 *lpSockAddr* パラメーターによって識別される特定のソケットにデータグラムを送信するために、SOCK_DGRAM ソケットでのみ使用されます。

ブロードキャストを送信するには (SOCK_DGRAM でのみ)、 *lpSockAddr* パラメーターのアドレスは、Windows Sockets ヘッダーファイル WINSOCK で定義されている特別な IP アドレス INADDR_BROADCAST を使用して構築する必要があります。H) を指定します。 または、 *Lpszhostaddress* パラメーターが NULL の場合、ソケットはブロードキャスト用に構成されます。 一般に、ブロードキャストデータグラムは、断片化が発生する可能性があるサイズを超えることが好ましくます。これは、データグラムのデータ部分 (ヘッダーを除く) が512バイトを超えないことを意味します。

IPv6 アドレスを処理するには、 [CAsyncSocket:: SendToEx](#sendtoex)を使用します。

## <a name="casyncsocketsendtoex"></a><a name="sendtoex"></a> CAsyncSocket:: SendToEx

このメンバー関数を呼び出して、特定の宛先にデータを送信します (IPv6 アドレスを処理します)。

```
int SendToEx(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
転送されるデータを格納しているバッファー。

*nBufLen*<br/>
*Lpbuf* 内のデータの長さ (バイト単位)。

*nHostPort*<br/>
ソケットアプリケーションを識別するポート。

*lpszHostAddress*<br/>
このオブジェクトが接続されているソケットのネットワークアドレス。 "ftp.microsoft.com" などのコンピューター名、または "128.56.22.8" などのドット番号。

*nFlags*<br/>
呼び出しを行う方法を指定します。 この関数のセマンティクスは、socket オプションと *nFlags* パラメーターによって決まります。 後者は、次のいずれかの値を C++ **または** 演算子と組み合わせることによって作成されます。

- MSG_DONTROUTE は、データをルーティングの対象にしないことを指定します。 Windows ソケットの供給業者は、このフラグを無視することを選択できます。

- 帯域外データの送信 MSG_OOB (SOCK_STREAM のみ)。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は、 `SendToEx` 送信された合計文字数を返します。 (これは、 *Nbuflen* によって示される数値よりも小さくなる可能性があることに注意してください)。それ以外の場合は SOCKET_ERROR の値が返され、 [GetLastError](#getlasterror)を呼び出すことによって特定のエラーコードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEACCES は、要求されたアドレスがブロードキャストアドレスですが、適切なフラグが設定されていませんでした。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAEFAULT は、 *Lpbuf* または *lpSockAddr* パラメーターがユーザーアドレス空間に含まれていないか、 *lpSockAddr* 引数が小さすぎる ( [SOCKADDR](/windows/win32/winsock/sockaddr-2) 構造体のサイズ未満)。

- WSAEINVAL ホスト名が無効です。

- Windows ソケットの実装によって接続が削除されたため、接続をリセットする必要があります。

- WSAの Windows ソケット実装では、バッファーのデッドロックが報告されます。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAM のみ)。

- WSAENOTSOCK 記述子はソケットではありません。

- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットの種類が SOCK_STREAM ではありません。

- WSAESHUTDOWN ソケットがシャットダウンされました。 `SendToEx` `ShutDown` *nhow* を1または2に設定してを呼び出した後に、ソケットでを呼び出すことはできません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、要求された操作はブロックされます。

- WSAEMSGSIZE はソケットの種類が SOCK_DGRAM で、データグラムが Windows Sockets 実装でサポートされている最大値を超えています。

- タイムアウトまたはその他のエラーが原因で仮想回線が中止された WSAECONNABORTED。

- WSAECONNRESET リモート側によって仮想回線がリセットされました。

- WSAEADDRNOTAVAIL ローカルコンピューターから指定されたアドレスを使用できません。

- 指定されたファミリの WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。

- WSAEDESTADDRREQ 宛先アドレスが必要です。

- この時点では、このホストからネットワークに到達できません。

### <a name="remarks"></a>解説

このメソッドは、IPv6 アドレスおよび古いプロトコルを処理することを除いて、 [CAsyncSocket:: SendTo](#sendto) と同じです。

`SendToEx` は、データグラムソケットまたはストリームソケットで使用され、ソケットで送信データを書き込むために使用されます。 データグラムソケットの場合は、基になるサブネットの最大 IP パケットサイズを超えないように注意する必要があります。これは、 `iMaxUdpDg` [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)によって入力される[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata)構造体の要素によって指定されます。 データが長すぎて、基になるプロトコルを使用してアトミックに渡すことができない場合、エラー WSAEMSGSIZE が返され、データは送信されません。

が正常に完了したことは、 `SendToEx` データが正常に配信されたことを示していないことに注意してください。

`SendToEx` は、 *lpSockAddr* パラメーターによって識別される特定のソケットにデータグラムを送信するために、SOCK_DGRAM ソケットでのみ使用されます。

ブロードキャストを送信するには (SOCK_DGRAM でのみ)、 *lpSockAddr* パラメーターのアドレスは、Windows Sockets ヘッダーファイル WINSOCK で定義されている特別な IP アドレス INADDR_BROADCAST を使用して構築する必要があります。H) を指定します。 または、 *Lpszhostaddress* パラメーターが NULL の場合、ソケットはブロードキャスト用に構成されます。 一般に、ブロードキャストデータグラムは、断片化が発生する可能性があるサイズを超えることが好ましくます。これは、データグラムのデータ部分 (ヘッダーを除く) が512バイトを超えないことを意味します。

## <a name="casyncsocketsetsockopt"></a><a name="setsockopt"></a> CAsyncSocket:: SetSockOpt

ソケットオプションを設定するには、このメンバー関数を呼び出します。

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>パラメーター

*nOptionName*<br/>
値が設定されるソケットオプション。

*lpOptionValue*<br/>
要求されたオプションの値が指定されているバッファーへのポインター。

*nOptionLen*<br/>
*LpOptionValue* バッファーのサイズ (バイト単位)。

*nLevel*<br/>
オプションが定義されているレベル。サポートされているレベルは SOL_SOCKET と IPPROTO_TCP のみです。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEFAULT *lpOptionValue* は、プロセスアドレス空間の有効な部分に含まれていません。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAEINVAL *Nlevel* が無効であるか、 *lpOptionValue* の情報が無効です。

- SO_KEEPALIVE が設定されているときに、WSAENETRESET 接続がタイムアウトしました。

- WSAENOPROTOOPT オプションは不明またはサポートされていません。 特に、SO_BROADCAST は SOCK_STREAM 型のソケットではサポートされていませんが、SO_DONTLINGER、SO_KEEPALIVE、SO_LINGER、および SO_OOBINLINE は、型 SOCK_DGRAM のソケットではサポートされていません。

- SO_KEEPALIVE が設定されると、WSAENOTCONN 接続がリセットされました。

- WSAENOTSOCK 記述子はソケットではありません。

### <a name="remarks"></a>解説

`SetSockOpt` 任意の状態のソケットに関連付けられているソケットオプションの現在の値を設定します。 オプションは複数のプロトコルレベルで存在できますが、この仕様では、最上位の "ソケット" レベルに存在するオプションのみが定義されています。 オプションは、通常のデータストリームで優先データを受信するかどうか、ソケットでブロードキャストメッセージを送信できるかどうかなど、ソケット操作に影響します。

ソケットオプションには、特徴または動作を有効または無効にするブール値オプションと、整数値または構造体を必要とするオプションの2種類があります。 ブール型のオプションを有効にするために、 *lpOptionValue* は0以外の整数を指します。 *LpOptionValue* オプションを無効にするには、0と等しい整数をポイントします。 *Noptionlen* は、ブール値オプションのと同じである必要があり `sizeof(BOOL)` ます。 その他のオプションの場合、 *lpOptionValue* はオプションの目的の値を含む整数または構造体を指し、 *Noptionlen* は整数または構造体の長さです。

SO_LINGER は、ソケットの未送信データがキューに置かれ、その `Close` 関数がソケットを閉じるために呼び出されるときに実行されるアクションを制御します。

既定では、ソケットは、既に使用されているローカルアドレスにバインドすることはできません (「 [Bind](#bind)」を参照してください)。 しかし、場合によっては、この方法でアドレスを再利用することが望ましい場合があります。 すべての接続はローカルアドレスとリモートアドレスの組み合わせによって一意に識別されるため、リモートアドレスが異なる限り、2つのソケットを同じローカルアドレスにバインドすることには問題はありません。

目的のアドレスが別のソケットによって既に使用されているために、ソケットの呼び出しが禁止されていないことを Windows ソケット実装に通知するには、 `Bind` 呼び出しを発行する前に、アプリケーションでソケットの SO_REUSEADDR ソケットオプションを設定する必要があり `Bind` ます。 このオプションは、呼び出し時にのみ解釈されることに注意して `Bind` ください。したがって、既存のアドレスにバインドされていないソケットにオプションを設定したり、呼び出しの後でオプションを設定またはリセットしたりすることはでき `Bind` ません。

アプリケーションでは、Windows ソケットの実装で、SO_KEEPALIVE ソケットオプションをオンにすることで、伝送制御プロトコル (TCP) 接続での "キープアライブ" パケットの使用を有効にするように要求できます。 Windows ソケットの実装では、キープアライブの使用をサポートしている必要はありません。その場合、正確なセマンティクスは実装固有ですが、RFC 1122 の「インターネットホストの要件」と「通信レイヤー」のセクション4.2.3.6 に準拠している必要があります。 "キープアライブ" の結果として接続が削除されると、エラーコード "WSAENETRESET" がソケットで進行中のすべての呼び出しに返され、それ以降の呼び出しは、WSAENOTCONN で失敗します。

TCP_NODELAY オプションを指定すると、Nagle アルゴリズムが無効になります。 Nagle アルゴリズムを使用すると、フルサイズのパケットを送信できるようになるまで、ホストから送信される小さなパケットの数を減らすことができます。 ただし、一部のアプリケーションでは、このアルゴリズムによってパフォーマンスが低下する可能性があるため、TCP_NODELAY を使用して無効にすることができます。 アプリケーションの作成者は、TCP_NODELAY の設定がネットワークパフォーマンスに重大な悪影響を及ぼす可能性があるため、TCP_NODELAY を設定しないようにしてください。 レベル IPPROTO_TCP を使用する唯一のサポートされているソケットオプションは TCP_NODELAY です。その他のすべてのオプションでは、レベル SOL_SOCKET を使用します。

SO_DEBUG オプションがアプリケーションによって設定されている場合、Windows ソケットの実装によってはデバッグ情報が出力されます。

では、次のオプションがサポートされてい `SetSockOpt` ます。 この型は、 *lpOptionValue* によってアドレス指定されるデータの種類を識別します。

|値|Type|説明|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|ソケットでのブロードキャストメッセージの送信を許可します。|
|SO_DEBUG|BOOL|デバッグ情報を記録します。|
|SO_DONTLINGER|BOOL|未送信 `Close` のデータが送信されるのを待ってブロックしないでください。 このオプションを設定することは、を0に設定して SO_LINGER を設定することと同じです `l_onoff` 。|
|SO_DONTROUTE|BOOL|ルーティングしない: インターフェイスに直接送信します。|
|SO_KEEPALIVE|BOOL|キープアライブを送信します。|
|SO_LINGER|`struct LINGER`|`Close`未送信のデータが存在する場合は、を待機します。|
|SO_OOBINLINE|BOOL|通常のデータストリームで帯域外データを受信します。|
|SO_RCVBUF|**`int`**|受信のバッファーサイズを指定します。|
|SO_REUSEADDR|BOOL|既に使用されているアドレスにソケットをバインドできるようにします。 (「 [Bind](#bind)」を参照してください)。|
|SO_SNDBUF|**`int`**|送信のバッファーサイズを指定します。|
|TCP_NODELAY|BOOL|送信結合用の Nagle アルゴリズムを無効にします。|

でサポートされていないソフトウェア配布 (BSD) のオプション `SetSockOpt` は次のとおりです。

|値|Type|説明|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|ソケットがリッスンしています|
|SO_ERROR|**`int`**|エラーの状態を取得してクリアします。|
|SO_RCVLOWAT|**`int`**|低いウォーターマークを受け取ります。|
|SO_RCVTIMEO|**`int`**|[受信タイムアウト]|
|SO_SNDLOWAT|**`int`**|低いウォーターマークを送信します。|
|SO_SNDTIMEO|**`int`**|送信タイムアウト。|
|SO_TYPE|**`int`**|ソケットの種類。|
|IP_OPTIONS||IP ヘッダーのオプションフィールドを設定します。|

## <a name="casyncsocketshutdown"></a><a name="shutdown"></a> CAsyncSocket:: ShutDown

このメンバー関数を呼び出して、ソケットでの送信、受信、またはその両方を無効にします。

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>パラメーター

*nHow*<br/>
次の列挙値を使用して、許可されなくなる操作の種類を説明するフラグ。

- **受信 = 0**

- **送信 = 1**

- **両方 = 2**

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0、および特定のエラーコードは、 [GetLastError](#getlasterror)を呼び出すことによって取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED A 成功した [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) は、この API を使用する前に実行する必要があります。

- Windows ソケット実装の WSAENETDOWN は、ネットワークサブシステムで障害が発生したことを検出しました。

- WSAEINVAL *Nhow* は無効です。

- かかわらず WSAEINPROGRESS Windows ソケットのブロッキング操作が進行中です。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAM のみ)。

- WSAENOTSOCK 記述子はソケットではありません。

### <a name="remarks"></a>解説

`ShutDown` は、受信、転送、またはその両方を無効にするために、すべての種類のソケットで使用されます。 *Nhow* が0の場合、ソケットでの後続の受信は許可されません。 これは、下位のプロトコルレイヤーには影響しません。

伝送制御プロトコル (TCP) の場合、TCP ウィンドウは変更されず、受信したデータはウィンドウが使い果たされるまで受け入れられます (ただし、確認はされません)。 ユーザーデータグラムプロトコル (UDP) の場合は、受信データグラムが受け入れられ、キューに登録されます。 では、ICMP エラーパケットが生成されません。 *N* が1の場合、後続の送信は許可されません。 TCP ソケットの場合、FIN が送信されます。 *Nhow* to 2 を設定すると、前述のように、送信と受信の両方が無効になります。

はソケットを閉じないことに注意して `ShutDown` `Close` ください。が呼び出されるまで、ソケットにアタッチされているリソースは解放されません。 アプリケーションは、シャットダウン後に、ソケットを再利用できないようにする必要があります。 特に、Windows ソケットの実装は、このようなソケットでのの使用をサポートするためには必要ありません `Connect` 。

### <a name="example"></a>例

  [CAsyncSocket:: OnReceive](#onreceive)の例を参照してください。

## <a name="casyncsocketsocket"></a><a name="socket"></a> CASyncSocket:: Socket

ソケットハンドルを割り当てます。

```
BOOL Socket(
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    int nProtocolType = 0,
    int nAddressFormat = PF_INET);
```

### <a name="parameters"></a>パラメーター

*nSocketType*<br/>
またはを指定し `SOCK_STREAM` `SOCK_DGRAM` ます。

*lEvent*<br/>
アプリケーションが関心を持つネットワークイベントの組み合わせを指定するビットマスク。

- `FD_READ`: 読み取りの準備の通知を受信します。

- `FD_WRITE`: 書き込みの準備に関する通知を受信します。

- `FD_OOB`: 帯域外データの到着通知を受信します。

- `FD_ACCEPT`: 着信接続の通知を受信します。

- `FD_CONNECT`: 完了した接続の通知を受信します。

- `FD_CLOSE`: ソケットのクロージャの通知を受信します。

*nProtocolType*<br/>
指定されたアドレスファミリに固有のソケットで使用されるプロトコル。

*nAddressFormat*<br/>
アドレスファミリの仕様。

### <a name="return-value"></a>戻り値

正常に終了した場合は、`TRUE` を返します。それ以外の場合は、`FALSE` を返します。

### <a name="remarks"></a>解説

このメソッドは、ソケットハンドルを割り当てます。 [CAsyncSocket:: Bind](#bind)を呼び出して、指定したアドレスにソケットをバインドすることはありません。そのため、後でを呼び出して `Bind` 、ソケットを指定されたアドレスにバインドする必要があります。 [CAsyncSocket:: SetSockOpt](#setsockopt)を使用すると、ソケットオプションをバインドする前に設定できます。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CSocket クラス](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
