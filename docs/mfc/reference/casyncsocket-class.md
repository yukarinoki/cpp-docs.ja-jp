---
title: クラス
ms.date: 09/03/2019
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
ms.openlocfilehash: e384be534bdbb355554c28383e9e214e9084f217
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753033"
---
# <a name="casyncsocket-class"></a>クラス

Windows ソケットを表します — ネットワーク通信のエンドポイント。

## <a name="syntax"></a>構文

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[同期ソケット::同期ソケット](#casyncsocket)|`CAsyncSocket` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[同期ソケット::受け入れる](#accept)|ソケット上の接続を受け入れます。|
|[同期ソケット::非同期選択](#asyncselect)|ソケットのイベント通知を要求します。|
|[同期ソケット::アタッチ](#attach)|オブジェクトにソケット ハンドルを`CAsyncSocket`アタッチします。|
|[同期ソケット::バインド](#bind)|ローカル アドレスをソケットに関連付けます。|
|[同期ソケット::閉じる](#close)|ソケットを閉じます。|
|[接続ソケット::接続](#connect)|ピア ソケットへの接続を確立します。|
|[CAsyncSocket::Create](#create)|ソケットを作成します。|
|[同期ソケット::Dエタッハ](#detach)|オブジェクトからソケット ハンドルを`CAsyncSocket`デタッチします。|
|[を使用します。](#fromhandle)|ソケット ハンドルを指定`CAsyncSocket`して、オブジェクトへのポインターを返します。|
|[同期ソケット::ラストエラーを取得します。](#getlasterror)|失敗した最後の操作のエラー状態を取得します。|
|[同期ソケット::取得ピアネーム](#getpeername)|ソケットが接続されているピア ソケットのアドレスを取得します。|
|[同期ソケット::取得ピアナメックス](#getpeernameex)|ソケットが接続されているピア ソケットのアドレスを取得します (IPv6 アドレスを処理します)。|
|[同期ソケット::ゲットソック名](#getsockname)|ソケットのローカル名を取得します。|
|[同期ソケット::ゲットソックナメックス](#getsocknameex)|ソケットのローカル名を取得します (IPv6 アドレスを処理します)。|
|[同期ソケット::ゲットソックオプト](#getsockopt)|ソケット オプションを取得します。|
|[同期ソケット::IOCtl](#ioctl)|ソケットのモードを制御します。|
|[同期ソケット::リッスン](#listen)|着信接続要求をリッスンするソケットを確立します。|
|[同期ソケット::受信](#receive)|ソケットからデータを受信します。|
|[同期ソケット::受信から](#receivefrom)|データグラムを受信し、送信元アドレスを格納します。|
|[同期ソケット::受信FromEx](#receivefromex)|データグラムを受信し、送信元アドレスを格納します (IPv6 アドレスを処理します)。|
|[同期ソケット::送信](#send)|接続されたソケットにデータを送信します。|
|[同期ソケット::送信](#sendto)|特定の宛先にデータを送信します。|
|[同期ソケット::送信ToEx](#sendtoex)|特定の宛先にデータを送信します (IPv6 アドレスを処理します)。|
|[同期ソケット::セットソックオプト](#setsockopt)|ソケットオプションを設定します。|
|[同期ソケット::シャットダウン](#shutdown)|ソケットの`Send``Receive`呼び出しを無効または呼び出します。|
|[ソケットソケット](#socket)|ソケット ハンドルを割り当てます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[同期ソケット::オンアクセ](#onaccept)|を呼び出`Accept`すことによって保留中の接続要求を受け入れることができることを、リッスンしているソケットに通知します。|
|[同期ソケット::オンクローズ](#onclose)|接続されているソケットが閉じられたことをソケットに通知します。|
|[同期ソケット::オンコネクト](#onconnect)|接続の試行が完了したことを接続ソケットに通知します( 正常に行うか、エラーが発生したか)。|
|[同期ソケット::オンアウトオブバンドデータ](#onoutofbanddata)|受信ソケットに、ソケット上で読み取る帯域外データがあることを通知します。|
|[受信時に発生します。](#onreceive)|を呼び出`Receive`して取得するデータがあることをリッスンしているソケットに通知します。|
|[同期ソケット::オンセンド](#onsend)|呼び出し`Send`によってデータを送信できることをソケットに通知します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[同期ソケット::演算子 =](#operator_eq)|オブジェクトに新しい値を`CAsyncSocket`割り当てます。|
|[同期ソケット::オペレーターソケット](#operator_socket)|この演算子は、オブジェクトの SOCKET ハンドル`CAsyncSocket`を取得するために使用します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[同期ソケット::m_hSocket](#m_hsocket)|この`CAsyncSocket`オブジェクトにアタッチされた SOCKET ハンドルを示します。|

## <a name="remarks"></a>解説

クラス`CAsyncSocket`は、MFC と共に Windows ソケットを使用するプログラマにオブジェクト指向の抽象化を提供する、Windows ソケット関数 API をカプセル化します。

このクラスは、ネットワーク通信を理解していることを前提としています。 あなたは、ブロック、バイト順の違い、および Unicode 文字列とマルチバイト文字セット (MBCS) 文字列間の変換を処理する責任があります。 これらの問題を管理する、より便利なインターフェイスが必要な場合は、クラス[CSocket](../../mfc/reference/csocket-class.md)を参照してください。

オブジェクトを`CAsyncSocket`使用するには、そのコンストラクターを呼び出し[、Create](#create)関数を呼び出して、`SOCKET`受け入れられたソケットを除いて、基になるソケット ハンドル (type) を作成します。 サーバー ソケットの場合は[、Listen](#listen)メンバー関数を呼び出し、クライアント ソケットの場合は[Connect](#connect)メンバー関数を呼び出します。 サーバー ソケットは、接続要求を受信したときに[Accept](#accept)関数を呼び出す必要があります。 残りの`CAsyncSocket`関数を使用して、ソケット間の通信を実行します。 完了時に、オブジェクト`CAsyncSocket`がヒープ上に作成された場合は破棄します。デストラクターは自動的に[Close](#close)関数を呼び出します。 ソケットデータ型については[、「Windows ソケット: バックグラウンド](../../mfc/windows-sockets-background.md)」の記事で説明されています。

> [!NOTE]
> 静的にリンクされた MFC アプリケーションのセカンダリ スレッドで MFC ソケットを使用する`AfxSocketInit`場合は、ソケット ライブラリを初期化するためにソケットを使用する各スレッドで呼び出す必要があります。 デフォルトでは、`AfxSocketInit`プライマリ スレッドでのみ呼び出されます。

詳細については、「 [Windows ソケット : クラス CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md)および関連記事の使用」、および Windows ソケット 2 [API](/windows/win32/WinSock/windows-sockets-start-page-2)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxsock.h

## <a name="casyncsocketaccept"></a><a name="accept"></a>同期ソケット::受け入れる

ソケット上の接続を受け入れるには、このメンバー関数を呼び出します。

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>パラメーター

*コネクトソケット*<br/>
接続に使用できる新しいソケットを識別する参照。

*lpSockAddr*<br/>
ネットワーク上で知られている接続ソケットのアドレスを受け取る[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体へのポインター。 *引数 lpSockAddr*の正確な形式は、ソケットの作成時に確立されたアドレス ファミリによって決まります。 *lpSockAddr*または*lpSockAddrLen*が NULL に等しい場合、受け入れられたソケットのリモート アドレスに関する情報は返されません。

*lpSockAddrLen*<br/>
*lpSockAddr*のアドレスの長さ (バイト単位) へのポインター。 *lpSockAddrLen*は値の結果のパラメーターです: 最初は*lpSockAddr*によって指されるスペースの量を含める必要があります。戻り値には、返されるアドレスの実際の長さ (バイト単位) が含まれます。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 引数*が*小さすぎる[(SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体のサイズより小さい) 。

- WINDOWS ソケットの呼び出しをブロックしています。

- 受け入れる前`Listen`に呼び出されませんでした。

- WSAEMFILE キューは受け入れるエントリ時に空であり、使用可能な記述子がありません。

- WSAENOBUFS 使用可能なバッファー・スペースがありません。

- 記述子がソケットではありません。

- 参照されるソケットは、接続指向サービスをサポートする型ではありません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、受け入れられる接続はありません。

### <a name="remarks"></a>解説

このルーチンは、保留中の接続のキュー内の最初の接続を抽出し、このソケットと同じプロパティを持つ新しいソケットを作成し、*それを rConnectedSocket*にアタッチします。 キューに保留中の接続がない場合は、ゼロ`Accept`を返し`GetLastError`、エラーを返します。 受け入れられたソケット *(rConnectedSocket) を*使用して、接続を受け入れることはできません。 元のソケットは開いたままで、リスニング状態です。

引数*lpSockAddr*は、通信層に認識されているように、接続ソケットのアドレスで埋め込まれる結果パラメーターです。 `Accept`は、SOCK_STREAMなどの接続ベースのソケットタイプで使用されます。

## <a name="casyncsocketasyncselect"></a><a name="asyncselect"></a>同期ソケット::非同期選択

ソケットのイベント通知を要求するには、このメンバー関数を呼び出します。

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>パラメーター

*イベント*<br/>
アプリケーションが対象とするネットワーク イベントの組み合わせを指定するビットマスク。

- FD_READ 読み取り準備の通知を受け取りたい。

- FD_WRITE データが読み取り可能になったときに通知を受け取りたい。

- FD_OOB帯域外データの到着通知を受け取りたい。

- FD_ACCEPT着信接続の通知を受け取りたい。

- FD_CONNECT 接続結果の通知を受け取りたい。

- FD_CLOSE ピアによってソケットが閉じられたときに通知を受け取りたい。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 指定されたパラメーターの 1 つが無効であることを示します。

- WINDOWS ソケットのブロック操作が進行中です。

### <a name="remarks"></a>解説

この関数は、ソケットに対して呼び出される MFC コールバック通知関数を指定するために使用されます。 `AsyncSelect`このソケットを自動的に非ブロッキングモードに設定します。 詳細については[、「Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

## <a name="casyncsocketattach"></a><a name="attach"></a>同期ソケット::アタッチ

オブジェクトに*hSocket*ハンドルをアタッチするには、この`CAsyncSocket`メンバー関数を呼び出します。

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>パラメーター

*hソケット*<br/>
ソケットへのハンドルを含みます。

*イベント*<br/>
アプリケーションが対象とするネットワーク イベントの組み合わせを指定するビットマスク。

- FD_READ 読み取り準備の通知を受け取りたい。

- FD_WRITE データが読み取り可能になったときに通知を受け取りたい。

- FD_OOB帯域外データの到着通知を受け取りたい。

- FD_ACCEPT着信接続の通知を受け取りたい。

- FD_CONNECT 接続結果の通知を受け取りたい。

- FD_CLOSE ピアによってソケットが閉じられたときに通知を受け取りたい。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。

### <a name="remarks"></a>解説

SOCKET ハンドルは、オブジェクトの[m_hSocket](#m_hsocket)データ・メンバーに保管されます。

## <a name="casyncsocketbind"></a><a name="bind"></a>同期ソケット::バインド

ローカル アドレスをソケットに関連付けるには、このメンバー関数を呼び出します。

```
BOOL Bind(
    UINT nSocketPort,
    LPCTSTR lpszSocketAddress = NULL);

BOOL Bind (
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ソケット アプリケーションを識別するポート。

*ソケットアドレス*<br/>
ネットワークアドレスは、「128.56.22.8」などのドット番号である。 このパラメーターに NULL 文字列を渡`CAsyncSocket`すと、インスタンスはすべてのネットワーク インターフェイスでクライアント アクティビティをリッスンする必要があります。

*lpSockAddr*<br/>
このソケットに割り当てるアドレスを含む[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体へのポインター。

*nソックアドルレン*<br/>
*lpSockAddr*のアドレスの長さ (バイト単位)。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 次の一覧は、返される可能性のあるエラーの一部を示しています。 完全なリストについては、 [Windows ソケット のエラー コード を参照してください](/windows/win32/winsock/windows-sockets-error-codes-2)。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 指定されたアドレスは既に使用されています。 [(SetSockOpt](#setsockopt)の下のSO_REUSEADDRソケット オプションを参照してください。

- WSAEFAULT*引数が*小さすぎます[(SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体のサイズより小さい)。

- WINDOWS ソケットの呼び出しをブロックしています。

- 指定されたアドレス ファミリは、このポートではサポートされていません。

- WSAEINVAL ソケットは既にアドレスにバインドされています。

- WSAENOBUFS 十分なバッファーが使用できず、接続数が多すぎます。

- 記述子がソケットではありません。

### <a name="remarks"></a>解説

このルーチンは、後続`Connect`の呼び出しまたは`Listen`呼び出しの前に、接続されていないデータグラムまたはストリーム・ソケットで使用されます。 接続要求を受け入れる前に、リッスンしているサーバー ソケットは、ポート番号を選択し、 を呼`Bind`び出して Windows ソケットに通知する必要があります。 `Bind`は、名前のないソケットにローカル名を割り当てることによって、ソケットのローカルアソシエーション (ホストアドレス/ポート番号) を確立します。

## <a name="casyncsocketcasyncsocket"></a><a name="casyncsocket"></a>同期ソケット::同期ソケット

空白のソケット オブジェクトを構築します。

```
CAsyncSocket();
```

### <a name="remarks"></a>解説

オブジェクトを構築した後、その`Create`メンバー関数を呼び出して、SOCKET データ構造を作成し、そのアドレスをバインドする必要があります。 (Windows ソケット通信のサーバー側では、リッスンソケットが`Accept`呼び出しで使用するソケットを作成するときに、そのソケットを呼`Create`び出しません。

## <a name="casyncsocketclose"></a><a name="close"></a>同期ソケット::閉じる

ソケットを閉じます。

```
virtual void Close();
```

### <a name="remarks"></a>解説

この関数はソケット記述子を解放して、それ以降の参照がエラー WSAENOTSOCK で失敗するようにします。 これが基底のソケットへの最後の参照である場合、関連付けられた命名情報とキューに入っているデータは破棄されます。 ソケットオブジェクトのデストラクタが呼`Close`び出します。

の`CAsyncSocket`場合は`CSocket`、ソケット オプションSO_LINGERとSO_DONTLINGER`Close`の影響を受けますが、のセマンティクスは 、 の意味に影響を受けます。 詳細については、メンバー関数`GetSockOpt`を参照してください。

## <a name="casyncsocketconnect"></a><a name="connect"></a>接続ソケット::接続

接続されていないストリームまたはデータグラム ソケットへの接続を確立するには、このメンバー関数を呼び出します。

```
BOOL Connect(
    LPCTSTR lpszHostAddress,
    UINT nHostPort);

BOOL Connect(
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>パラメーター

*アドレスを指定します。*<br/>
このオブジェクトが接続されているソケットのネットワーク アドレス: "ftp.microsoft.com"などのマシン名、または "128.56.22.8" などのドット番号。

*をクリックします。*<br/>
ソケット アプリケーションを識別するポート。

*lpSockAddr*<br/>
接続されたソケットのアドレスを含む[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体へのポインター。

*nソックアドルレン*<br/>
*lpSockAddr*のアドレスの長さ (バイト単位)。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 これが WSAEWOULDBLOCK のエラー・コードを示しており、アプリケーションがオーバーライド可能なコールバックを使用している場合、アプリケーションは`OnConnect`接続操作が完了するとメッセージを受け取ります。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 指定されたアドレスは既に使用されています。

- WINDOWS ソケットの呼び出しをブロックしています。

- 指定されたアドレスはローカル・マシンからは使用できません。

- 指定されたファミリー内の WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。

- 接続の試行が拒否されました。

- 宛先アドレスが必要です。

- WSAEFAULT *nSockAddrLen*引数が正しくありません。

- WSAEINVAL ホスト アドレスが無効です。

- WSAEISCONN ソケットは既に接続されています。

- WSAEMFILE これ以上のファイル記述子を使用できません。

- この時点では、このホストからネットワークにアクセスできません。

- WSAENOBUFS 使用可能なバッファー・スペースがありません。 ソケットを接続できません。

- 記述子がソケットではありません。

- WSAETIMEDOUT 接続を確立せずに接続がタイムアウトになろうと試みます。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、接続をすぐに完了することはできません。

### <a name="remarks"></a>解説

ソケットがバインドされていない場合、固有値はシステムによってローカルの関連付けに割り当てられ、ソケットはバインド済みとしてマークされます。 name 構造体のアドレス フィールドがすべてゼロの場合は、`Connect`ゼロを返します。 拡張エラー情報を取得するには、メンバー`GetLastError`関数を呼び出します。

ストリーム・ソケット (タイプ SOCK_STREAM) の場合、外部ホストへのアクティブ接続が開始されます。 ソケット呼び出しが正常に完了すると、ソケットはデータの送受信の準備が完了します。

データグラムソケット(タイプSOCK_DGRAM)の場合、デフォルトの宛先が設定され、後続`Send`の呼び出`Receive`しで使用されます。

## <a name="casyncsocketcreate"></a><a name="create"></a>同期ソケット::作成

ソケット`Create`オブジェクトを作成した後にメンバー関数を呼び出して、Windows ソケットを作成し、アタッチします。

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ソケットで使用する既知のポート、または Windows ソケットでポートを選択する場合は 0。

*を指定します。*<br/>
SOCK_STREAMまたはSOCK_DGRAM。

*イベント*<br/>
アプリケーションが対象とするネットワーク イベントの組み合わせを指定するビットマスク。

- FD_READ 読み取り準備の通知を受け取りたい。

- FD_WRITE書き込みの準備の通知を受け取りたいです。

- FD_OOB帯域外データの到着通知を受け取りたい。

- FD_ACCEPT着信接続の通知を受け取りたい。

- FD_CONNECT 接続完了の通知を受信する必要があります。

- FD_CLOSE ソケットクロージャの通知を受け取りたい。

*アドレスをクリックします。*<br/>
接続されたソケットのネットワークアドレスを含む文字列へのポインタで、ドット番号(128.56.22.8)など。このパラメーターに NULL 文字列を渡`CAsyncSocket`すと、インスタンスはすべてのネットワーク インターフェイスでクライアント アクティビティをリッスンする必要があります。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 指定されたアドレス・ファミリーはサポートされていません。

- WINDOWS ソケットのブロック操作が進行中です。

- WSAEMFILE これ以上のファイル記述子を使用できません。

- WSAENOBUFS 使用可能なバッファー・スペースがありません。 ソケットを作成できません。

- 指定されたポートはサポートされていません。

- WSAEPROTOTYPE 指定されたポートは、このソケットに対して間違ったタイプです。

- 指定されたソケット・タイプは、このアドレス・ファミリーではサポートされていません。

### <a name="remarks"></a>解説

`Create`[Socket](#socket)を呼び出し、成功した場合は[Bind](#bind)を呼び出して、ソケットを指定したアドレスにバインドします。 次のソケット・タイプがサポートされています。

- SOCK_STREAM シーケンス型、信頼性、全二重、接続ベースのバイト ストリームを提供します。 インターネット アドレス ファミリに伝送制御プロトコル (TCP) を使用します。

- SOCK_DGRAM固定 (通常は小さい) 最大長のコネクションレスで信頼性の低いパケットであるデータグラムをサポートします。 インターネット アドレス ファミリにユーザー データグラム プロトコル (UDP) を使用します。

    > [!NOTE]
    >  メンバー`Accept`関数は、新しい空`CSocket`のオブジェクトへの参照をパラメーターとして受け取ります。 このオブジェクトは、 を呼び`Accept`出す前に構築する必要があります。 このソケット オブジェクトがスコープ外に出ると、接続が閉じられます。 この新しい`Create`ソケット オブジェクトを呼び出しません。

> [!IMPORTANT]
> `Create`はスレッドセーフ**ではありません**。  異なるスレッドによって同時に呼び出すことができるマルチスレッド環境で呼び出す場合は、各呼び出しをミューテックスなどの同期ロックで保護してください。

ストリームソケットとデータグラムソケットの詳細については[、「Windows ソケット: バックグラウンド](../../mfc/windows-sockets-background.md)ソケットと[Windows ソケット: ポートとソケット アドレスと](../../mfc/windows-sockets-ports-and-socket-addresses.md) [Windows ソケット 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)」を参照してください。

## <a name="casyncsocketdetach"></a><a name="detach"></a>同期ソケット::Dエタッハ

*m_hSocket*データ メンバー内の SOCKET ハンドルを`CAsyncSocket`オブジェクトからデタッチし *、m_hSocket* NULL に設定します。

```
SOCKET Detach();
```

## <a name="casyncsocketfromhandle"></a><a name="fromhandle"></a>を使用します。

オブジェクトへのポインターを`CAsyncSocket`返します。

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>パラメーター

*hソケット*<br/>
ソケットへのハンドルを含みます。

### <a name="return-value"></a>戻り値

`CAsyncSocket`オブジェクトへのポインター、 *hSocket*にアタッチされているオブジェクト`CAsyncSocket`がない場合は NULL。

### <a name="remarks"></a>解説

SOCKET ハンドルが与えられた場合、`CAsyncSocket`オブジェクトがハンドルにアタッチされていない場合、メンバー関数は NULL を返します。

## <a name="casyncsocketgetlasterror"></a><a name="getlasterror"></a>同期ソケット::ラストエラーを取得します。

失敗した最後の操作のエラー状態を取得します。

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>戻り値

戻り値は、このスレッドによって実行された最後の Windows ソケット API ルーチンのエラー コードを示します。

### <a name="remarks"></a>解説

特定のメンバー関数がエラーの発生を示した場合は`GetLastError`、適切なエラー コードを取得するために呼び出す必要があります。 該当するエラー・コードのリストについては、個々のメンバー関数の説明を参照してください。

エラー コードの詳細については、「 [Windows ソケット 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)」を参照してください。

## <a name="casyncsocketgetpeername"></a><a name="getpeername"></a>同期ソケット::取得ピアネーム

このメンバー関数を呼び出して、このソケットが接続されているピア ソケットのアドレスを取得します。

```
BOOL GetPeerName(
    CString& rPeerAddress,
    UINT& rPeerPort);

BOOL GetPeerName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ドット番号の`CString`IP アドレスを受け取るオブジェクトへの参照。

*ルピアポート*<br/>
ポートを格納する UINT への参照。

*lpSockAddr*<br/>
ピアソケットの名前を受け取る[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体へのポインタ。

*lpSockAddrLen*<br/>
*lpSockAddr*のアドレスの長さ (バイト単位) へのポインター。 戻り値の場合、*引数 lpSockAddr には*、返される*lpSockAddr*の実際のサイズがバイト単位で格納されます。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 引数*が*十分に大きくない。

- WINDOWS ソケットの呼び出しをブロックしています。

- ソケットが接続されていません。

- 記述子がソケットではありません。

### <a name="remarks"></a>解説

IPv6 アドレスを処理するには[、CAsyncSocket::GetPeerNameEx](#getpeernameex)を使用します。

## <a name="casyncsocketgetpeernameex"></a><a name="getpeernameex"></a>同期ソケット::取得ピアナメックス

このメンバー関数を呼び出して、このソケットが接続されているピア ソケットのアドレスを取得します (IPv6 アドレスを処理します)。

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ドット番号の`CString`IP アドレスを受け取るオブジェクトへの参照。

*ルピアポート*<br/>
ポートを格納する UINT への参照。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 引数*が*十分に大きくない。

- WINDOWS ソケットの呼び出しをブロックしています。

- ソケットが接続されていません。

- 記述子がソケットではありません。

### <a name="remarks"></a>解説

この関数は、古いプロトコルと同様に IPv6 アドレスを処理する点を除いて[、CAsyncSocket::GetPeerName](#getpeername)と同じです。

## <a name="casyncsocketgetsockname"></a><a name="getsockname"></a>同期ソケット::ゲットソック名

ソケットのローカル名を取得します。

```
BOOL GetSockName(
    CString& rSocketAddress,
    UINT& rSocketPort);

BOOL GetSockName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ドット番号の`CString`IP アドレスを受け取るオブジェクトへの参照。

*をクリックします。*<br/>
ポートを格納する UINT への参照。

*lpSockAddr*<br/>
ソケットのアドレスを受け取る[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体へのポインター。

*lpSockAddrLen*<br/>
*lpSockAddr*のアドレスの長さ (バイト単位) へのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 引数*が*十分に大きくない。

- WINDOWS ソケットのブロック操作が進行中です。

- 記述子がソケットではありません。

- WSAEINVAL ソケットが を持つ`Bind`アドレスにバインドされていません。

### <a name="remarks"></a>解説

この呼び出しは、`Connect`最初に行わずに呼び出`Bind`しが行われた場合に特に便利です。この呼び出しは、システムによって設定されたローカル関連付けを判別する唯一の手段となります。

IPv6 アドレスを処理するには[、CAsyncSocket を使用します。](#getsocknameex)

## <a name="casyncsocketgetsocknameex"></a><a name="getsocknameex"></a>同期ソケット::ゲットソックナメックス

ソケットのローカル名を取得します (IPv6 アドレスを処理します)。

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ドット番号の`CString`IP アドレスを受け取るオブジェクトへの参照。

*をクリックします。*<br/>
ポートを格納する UINT への参照。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 引数*が*十分に大きくない。

- WINDOWS ソケットのブロック操作が進行中です。

- 記述子がソケットではありません。

- WSAEINVAL ソケットが を持つ`Bind`アドレスにバインドされていません。

### <a name="remarks"></a>解説

この呼び出しは、IPv6 アドレスと古いプロトコルを処理する点を除いて[、CAsyncSocket::GetSockName](#getsockname)と同じです。

この呼び出しは、`Connect`最初に行わずに呼び出`Bind`しが行われた場合に特に便利です。この呼び出しは、システムによって設定されたローカル関連付けを判別する唯一の手段となります。

## <a name="casyncsocketgetsockopt"></a><a name="getsockopt"></a>同期ソケット::ゲットソックオプト

ソケット オプションを取得するには、このメンバー関数を呼び出します。

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>パラメーター

*オプション名*<br/>
値を取得するソケット オプション。

*オプション値*<br/>
要求されたオプションの値が戻されるバッファーへのポインター。 選択したオプションに関連付けられた値が、バッファー *lpOptionValue に*返されます。 *lpOptionLen*が指す整数は、もともとこのバッファのサイズをバイト単位で格納する必要があります。戻り値は、返される値のサイズに設定されます。 SO_LINGERの場合、これは`LINGER`構造体のサイズになります。その他のオプションの場合は、オプションに応じて BOOL または**int**のサイズになります。 「解説」セクションのオプションとそのサイズのリストを参照してください。

*オプションレン*<br/>
バイト単位で*の lpOptionValue*バッファーのサイズへのポインター。

*nレベル*<br/>
オプションが定義されているレベル。サポートされているレベルはSOL_SOCKETとIPPROTO_TCPだけです。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 オプションが に`SetSockOpt`設定されなかった場合は、`GetSockOpt`オプションの既定値を返します。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- *引数が*無効でした。

- WINDOWS ソケットのブロック操作が進行中です。

- WSAENOPROTOOPT オプションが不明であるか、サポートされていません。 特に、SO_BROADCASTタイプ SOCK_STREAMのソケットではサポートされませんが、SO_ACCEPTCONN、SO_DONTLINGER、SO_KEEPALIVE、SO_LINGER、およびSO_OOBINLINEはタイプ SOCK_DGRAMのソケットではサポートされません。

- 記述子がソケットではありません。

### <a name="remarks"></a>解説

`GetSockOpt`任意のタイプのソケットに関連付けられたソケットオプションの現在の値を任意の状態で取得し、その結果を*lpOptionValue*に格納します。 オプションは、パケットのルーティング、帯域外データ転送などのソケット操作に影響します。

では、次の`GetSockOpt`オプションがサポートされています。 型は *、lpOptionValue*によってアドレス指定されるデータの種類を識別します。 TCP_NODELAYオプションではレベルIPPROTO_TCPを使用します。その他のオプションはすべて、レベルSOL_SOCKETを使用します。

|値|Type|意味|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|ソケットがリッスンしています。|
|SO_BROADCAST|BOOL|ソケットはブロードキャスト メッセージの送信用に設定されます。|
|SO_DEBUG|BOOL|デバッグが有効になっています。|
|SO_DONTLINGER|BOOL|true の場合、SO_LINGER オプションは無効になります。|
|SO_DONTROUTE|BOOL|ルーティングは無効になっています。|
|SO_ERROR|**int**|エラーステータスを取得し、クリアします。|
|SO_KEEPALIVE|BOOL|キープアライブが送信されています。|
|SO_LINGER|`struct LINGER`|現在の残留オプションを返します。|
|SO_OOBINLINE|BOOL|帯域外データは通常のデータ ストリームで受信されています。|
|SO_RCVBUF|INT|受信のバッファー サイズ。|
|SO_REUSEADDR|BOOL|ソケットは、既に使用中のアドレスにバインドできます。|
|SO_SNDBUF|**int**|送信のバッファ サイズ。|
|SO_TYPE|**int**|ソケットの型 (SOCK_STREAMなど)。|
|TCP_NODELAY|BOOL|送信結合用の Nagle アルゴリズムを無効にします。|

サポートされていないバークレー・ソフトウェア・ディストリビューション (BSD) オプション`GetSockOpt`は次のとおりです。

|値|Type|意味|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|低いウォーターマークを受け取ります。|
|SO_RCVTIMEO|**int**|受信タイムアウト。|
|SO_SNDLOWAT|**int**|低いウォーターマークを送信します。|
|SO_SNDTIMEO|**int**|送信タイムアウト。|
|IP_OPTIONS||IP ヘッダーのオプションを取得します。|
|TCP_MAXSEG|**int**|TCP 最大セグメント サイズを取得します。|

サポート`GetSockOpt`されていないオプションを指定して呼び出すと、WSAENOPROTOOPT のエラー・コード`GetLastError`が から戻されます。

## <a name="casyncsocketioctl"></a><a name="ioctl"></a>同期ソケット::IOCtl

ソケットのモードを制御するには、このメンバー関数を呼び出します。

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>パラメーター

*lコマンド*<br/>
ソケットで実行するコマンド。

*引数*<br/>
*lCommand*のパラメーターへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- WSAEINVAL *lCommand*が有効なコマンドではないか *、lCommand*に対して*lCommand*lpArgument が受け入れ可能なパラメーターではないか、コマンドが提供されたソケットのタイプに適用できません。

- WINDOWS ソケットのブロック操作が進行中です。

- 記述子がソケットではありません。

### <a name="remarks"></a>解説

このルーチンは、任意の状態の任意のソケットで使用できます。 この機能は、プロトコルおよび通信サブシステムに関係なく、ソケットに関連付けられた操作パラメーターを取得または取得するために使用されます。 次のコマンドがサポートされています。

- FIONBIO ソケットの非ブロックモードを有効または無効にします。 *lpArgument*パラメーターは`DWORD`、非ブロッキング モードを有効にする場合は 0 以外の値を指し、無効にする場合は 0 以外を指します。 ソケット`AsyncSelect`で発行された場合、ソケットをブロック・モードに戻`IOCtl`すために使用する試みは WSAEINVAL で失敗します。 ソケットをブロック モードに戻して WSAEINVAL エラーを防ぐには、アプリケーションは`AsyncSelect`まず`AsyncSelect`*lEvent*パラメーターを 0 にして呼`IOCtl`び出して無効にしてから、 を呼び出す必要があります。

- FIONREAD このソケットからの 1 回`Receive`の呼び出しで読み取ることができる最大バイト数を決定します。 *lpArgument*パラメーターは、結果`DWORD`を格納`IOCtl`するを指します。 このソケットがタイプSOCK_STREAMの場合、FIONREAD は、単一`Receive`で読み取ることができるデータの合計量を戻します。これは通常、ソケットにキューイングされたデータの合計量と同じです。 このソケットがタイプ SOCK_DGRAM の場合、FIONREAD はソケットにキューイングされた最初のデータグラムのサイズを戻します。

- すべての帯域外データが読み取られたかどうかを判断します。 これは、帯域外データ (SO_OOBINLINE) のインライン受信用に設定されているタイプ SOCK_STREAMのソケットにのみ適用されます。 アウトオブバンド・データが読み取りを待っていない場合、この操作はゼロ以外を戻します。 それ以外の場合は 0`Receive`を`ReceiveFrom`返し、次に実行されたソケットで実行されたデータの一部またはすべてを "mark" の前に取得します。アプリケーションは、SIOCATMARK 操作を使用して、データが残っているかどうかを判別する必要があります。 「緊急」(帯域外)データの前に通常のデータがある場合は、順番に受信されます。 (同じ呼`Receive`び`ReceiveFrom`出しでは、帯域外データと通常データは混在しない、またはは決してありません)。*lpArgument*パラメーターは、結果`DWORD`を格納`IOCtl`するを指します。

この関数は、バークレー・`ioctl()`ソケットで使用されるサブセットです。 特に、FIOASYNC と同等のコマンドはありませんが、SIOCATMARK はサポートされている唯一のソケット・レベル・コマンドです。

## <a name="casyncsocketlisten"></a><a name="listen"></a>同期ソケット::リッスン

着信接続要求をリッスンするには、このメンバー関数を呼び出します。

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>パラメーター

*接続バックログ*<br/>
保留接続のキューが拡張できる最大長。 有効な範囲は 1 から 5 です。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 使用中のアドレスをリッスンする試みが行われました。

- WINDOWS ソケットのブロック操作が進行中です。

- WSAEINVAL ソケットがバインドされていないか、`Bind`既に接続されています。

- WSAEISCONN ソケットは既に接続されています。

- WSAEMFILE これ以上のファイル記述子を使用できません。

- WSAENOBUFS 使用可能なバッファー・スペースがありません。

- 記述子がソケットではありません。

- WSAEOPNOTSUPP 参照されるソケットが`Listen`、操作をサポートする型ではありません。

### <a name="remarks"></a>解説

接続を受け入れるには、ソケットが`Create`を使用して最初に 作成され、`Listen`着信接続のバックログが で`Accept`指定され、次に接続が で受け入れられます。 `Listen`は、接続をサポートするソケット、つまりタイプがSOCK_STREAMソケットにのみ適用されます。 このソケットは、受信接続が承認され、プロセスによる受け入れ待ちのキューに入れられる「パッシブ」モードに設定されます。

この機能は通常、一度に複数の接続要求を持つ可能性のあるサーバー (または接続を受け入れるアプリケーション) によって使用されます。

`Listen`使用可能なポート (記述子) がない場合に、合理的に機能し続けようとします。 キューが空になるまで接続を受け入れます。 ポートが使用可能になった場合、後でキュー`Listen`への`Accept`呼び出しが現在または最新の 「バックログ」に再入力され、可能であれば、着信接続のリッスンが再開されます。

## <a name="casyncsocketm_hsocket"></a><a name="m_hsocket"></a>同期ソケット::m_hSocket

この`CAsyncSocket`オブジェクトによってカプセル化されたソケットの SOCKET ハンドルを格納します。

```
SOCKET m_hSocket;
```

## <a name="casyncsocketonaccept"></a><a name="onaccept"></a>同期ソケット::オンアクセ

[Accept](#accept)メンバー関数を呼び出すことによって、保留中の接続要求を受け入れることができることを待機中のソケットに通知するために、フレームワークによって呼び出されます。

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*エラーコード*<br/>
ソケットの最新のエラー。 次のエラー コードがメンバー`OnAccept`関数に適用されます。

- **0**関数が正常に実行されました。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット : ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

## <a name="casyncsocketonclose"></a><a name="onclose"></a>同期ソケット::オンクローズ

接続されたソケットがそのプロセスによって閉じられたことをこのソケットに通知するために、フレームワークによって呼び出されます。

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*エラーコード*<br/>
ソケットの最新のエラー。 次のエラー コードがメンバー`OnClose`関数に適用されます。

- **0**関数が正常に実行されました。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- 接続がリモート側によってリセットされました。

- タイムアウトまたはその他の障害により、接続が中止されました。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット : ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

## <a name="casyncsocketonconnect"></a><a name="onconnect"></a>同期ソケット::オンコネクト

正常に行われたかエラーであるかに関係なく、この接続ソケットに接続の試行が完了したことを通知するために、フレームワークによって呼び出されます。

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*エラーコード*<br/>
ソケットの最新のエラー。 次のエラー コードがメンバー`OnConnect`関数に適用されます。

- **0**関数が正常に実行されました。

- 指定されたアドレスは既に使用されています。

- 指定されたアドレスはローカル・マシンからは使用できません。

- 指定されたファミリー内の WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。

- 接続の試行は強制的に拒否されました。

- 宛先アドレスが必要です。

- 引数*が*正しくありません。

- WSAEINVAL ソケットは既にアドレスにバインドされています。

- WSAEISCONN ソケットは既に接続されています。

- WSAEMFILE これ以上のファイル記述子を使用できません。

- この時点では、このホストからネットワークにアクセスできません。

- WSAENOBUFS 使用可能なバッファー・スペースがありません。 ソケットを接続できません。

- ソケットが接続されていません。

- WSAENOTSOCK 記述子はソケットではなくファイルです。

- WSAETIMEDOUT 接続を確立せずに接続がタイムアウトしました。

### <a name="remarks"></a>解説

> [!NOTE]
> [CSocket](../../mfc/reference/csocket-class.md)では、`OnConnect`通知関数が呼び出されることはありません。 接続の場合は、`Connect`を呼び出すだけで、接続が完了したときに返されます (正常またはエラー)。 接続通知の処理方法は、MFC 実装の詳細です。

詳細については、「 [Windows ソケット : ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

## <a name="casyncsocketonoutofbanddata"></a><a name="onoutofbanddata"></a>同期ソケット::オンアウトオブバンドデータ

送信ソケットに送信する帯域外データがあることを受信側ソケットに通知するために、フレームワークによって呼び出されます。

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*エラーコード*<br/>
ソケットの最新のエラー。 次のエラー コードがメンバー`OnOutOfBandData`関数に適用されます。

- **0**関数が正常に実行されました。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

### <a name="remarks"></a>解説

アウト・オブ・バンド・データは、タイプ・SOCK_STREAMの接続ソケットの各ペアに関連付けられた、論理的に独立したチャネルです。 チャネルは、一般に緊急データを送信するために使用されます。

MFC は帯域外データをサポートしますが、クラス`CAsyncSocket`のユーザーは使用しないことをお勧めします。 簡単な方法は、このようなデータを渡すための2番目のソケットを作成することです。 帯域外データの詳細については、「 Windows ソケット[: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

## <a name="casyncsocketonreceive"></a><a name="onreceive"></a>受信時に発生します。

このソケットに、メンバー関数を呼び出すことによって取得できるデータがあることをこのソケットに`Receive`通知するために、フレームワークによって呼び出されます。

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*エラーコード*<br/>
ソケットの最新のエラー。 次のエラー コードがメンバー`OnReceive`関数に適用されます。

- **0**関数が正常に実行されました。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット : ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

## <a name="casyncsocketonsend"></a><a name="onsend"></a>同期ソケット::オンセンド

メンバー関数を呼び出してデータを送信できることをソケットに通知するために、フレームワーク`Send`によって呼び出されます。

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>パラメーター

*エラーコード*<br/>
ソケットの最新のエラー。 次のエラー コードがメンバー`OnSend`関数に適用されます。

- **0**関数が正常に実行されました。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

### <a name="remarks"></a>解説

詳細については、「 [Windows ソケット : ソケット通知](../../mfc/windows-sockets-socket-notifications.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

## <a name="casyncsocketoperator-"></a><a name="operator_eq"></a>同期ソケット::演算子 =

オブジェクトに新しい値を`CAsyncSocket`割り当てます。

```cpp
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>パラメーター

*rSrc*<br/>
既存`CAsyncSocket`のオブジェクトへの参照。

### <a name="remarks"></a>解説

既存`CAsyncSocket`のオブジェクトを別`CAsyncSocket`のオブジェクトにコピーします。

## <a name="casyncsocketoperator-socket"></a><a name="operator_socket"></a>同期ソケット::オペレーターソケット

この演算子は、オブジェクトの SOCKET ハンドル`CAsyncSocket`を取得するために使用します。

```
operator SOCKET() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、SOCKET オブジェクトのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

ハンドルを使用して、Windows API を直接呼び出すことができます。

## <a name="casyncsocketreceive"></a><a name="receive"></a>同期ソケット::受信

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

*ヌフレン*<br/>
*lpBuf*の長さ (バイト単位)。

*Nflags*<br/>
呼び出しの方法を指定します。 この関数のセマンティクスは、ソケット オプションと*nFlags*パラメーターによって決定されます。 後者は、次の値のいずれかを C++ **OR**演算子と組み合わせることによって構成されます。

- MSG_PEEK受信データをピークします。 データはバッファーにコピーされますが、入力キューからは削除されません。

- MSG_OOB アウトオブバンド データを処理します。

### <a name="return-value"></a>戻り値

エラーが発生しない場合は`Receive`、受信したバイト数を返します。 接続が閉じられている場合は、0 を返します。 それ以外の場合は、SOCKET_ERRORの値が返され[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- ソケットが接続されていません。

- WINDOWS ソケットのブロック操作が進行中です。

- 記述子がソケットではありません。

- WSAEOPNOTSUPP MSG_OOB指定されましたが、ソケットのタイプがSOCK_STREAMではありません。

- ソケットがシャットダウンされました。*nHow*を 0`Receive`または 2`ShutDown`に設定して呼び出した後で、ソケットを呼び出す方法はありません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、`Receive`操作はブロックされます。

- 指定されたバッファーに収まらないデータグラムが大きすぎて切り捨てられました。

- WSAEINVAL ソケットが に`Bind`バインドされていません。

- タイムアウトなどの障害により、仮想回線が中断されました。

- リモート側で仮想回線がリセットされました。

### <a name="remarks"></a>解説

この関数は、接続されたストリームまたはデータグラム・ソケットに使用され、受信データの読み取りに使用されます。

SOCK_STREAMタイプのソケットの場合、現在使用可能な情報の数が、指定されたバッファーのサイズまで戻されます。 ソケットが帯域外データ (ソケットオプション SO_OOBINLINE) のインライン受信用に設定されており、アウトオブバンド データが未読である場合は、アウトオブバンド データのみが返されます。 アプリケーションは、オプションまたは`IOCtlSIOCATMARK` [OnOutOfBandData](#onoutofbanddata)を使用して、これ以上の帯域外データが読み取られるかどうかを判断できます。

データグラム・ソケットの場合、データは、最初のエンキュー・データグラムから、指定されたバッファーのサイズまで抽出されます。 データグラムが指定されたバッファーより大きい場合、バッファーはデータグラムの最初の部分で埋め、超過データは失われ`Receive`、エラー・コードが WSAEMSGSIZE に設定されたSOCKET_ERRORの値を戻します。 ソケットで受信データが使用可能な場合、エラー・コードが WSAEWOULDBLOCK に設定された SOCKET_ERROR の値が戻されます。 [OnReceive](#onreceive)コールバック関数を使用して、いつより多くのデータが到着するかを判断できます。

ソケットがタイプ SOCK_STREAMで、リモート側が接続を正常にシャットダウンした場合、a`Receive`は 0 バイト受信して直ちに完了します。 接続がリセットされた場合、エラー `Receive` WSAECONNRESET で失敗します。

`Receive`[は、CAsyncSocket::OnReceive](#onreceive)が呼び出されるたびに 1 回だけ呼び出す必要があります。

### <a name="example"></a>例

  [「CAsyncSocket::受信時](#onreceive)」の例を参照してください。

## <a name="casyncsocketreceivefrom"></a><a name="receivefrom"></a>同期ソケット::受信から

このメンバー関数を呼び出して、データグラムを受信し、ソース アドレスを[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体または*rSocketAddress*に格納します。

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

*ヌフレン*<br/>
*lpBuf*の長さ (バイト単位)。

*をクリックします。*<br/>
ドット番号の`CString`IP アドレスを受け取るオブジェクトへの参照。

*をクリックします。*<br/>
ポートを格納する UINT への参照。

*lpSockAddr*<br/>
戻り値の送信元アドレスを保持する[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体へのポインター。

*lpSockAddrLen*<br/>
*lpSockAddr*のソース アドレスの長さ (バイト単位) へのポインター。

*Nflags*<br/>
呼び出しの方法を指定します。 この関数のセマンティクスは、ソケット オプションと*nFlags*パラメーターによって決定されます。 後者は、次の値のいずれかを C++ **OR**演算子と組み合わせることによって構成されます。

- MSG_PEEK受信データをピークします。 データはバッファーにコピーされますが、入力キューからは削除されません。

- MSG_OOB アウトオブバンド データを処理します。

### <a name="return-value"></a>戻り値

エラーが発生しない場合は`ReceiveFrom`、受信したバイト数を返します。 接続が閉じられている場合は、0 を返します。 それ以外の場合は、SOCKET_ERROR の値が返され、呼び出すことによって`GetLastError`特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- *引数 lpSockAddrLen*が無効でした: *lpSockAddr*バッファーが小さすぎてピア アドレスを収容できませんでした。

- WINDOWS ソケットのブロック操作が進行中です。

- WSAEINVAL ソケットが に`Bind`バインドされていません。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAMのみ)。

- 記述子がソケットではありません。

- WSAEOPNOTSUPP MSG_OOB指定されましたが、ソケットのタイプがSOCK_STREAMではありません。

- ソケットがシャットダウンされました。*nHow*を 0`ReceiveFrom`または 2`ShutDown`に設定して呼び出した後で、ソケットを呼び出す方法はありません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、`ReceiveFrom`操作はブロックされます。

- 指定されたバッファーに収まらないデータグラムが大きすぎて切り捨てられました。

- タイムアウトなどの障害により、仮想回線が中断されました。

- リモート側で仮想回線がリセットされました。

### <a name="remarks"></a>解説

この関数は、(接続されている可能性のある) ソケット上の受信データを読み取り、データの送信元のアドレスをキャプチャするために使用されます。

IPv6 アドレスを処理するには[、CAsyncSocket::ReceiveFromEx](#receivefromex)を使用します。

SOCK_STREAMタイプのソケットの場合、現在使用可能な情報の数が、指定されたバッファーのサイズまで戻されます。 ソケットが帯域外データ (ソケットオプション SO_OOBINLINE) のインライン受信用に設定されており、アウトオブバンド データが未読である場合は、アウトオブバンド データのみが返されます。 アプリケーションは、このオプション`IOCtlSIOCATMARK`を使用`OnOutOfBandData`するか、またはこれ以上帯域外データを読み取る必要があるかどうかを判断できます。 *SOCK_STREAMソケットの場合、lpSockAddr*および*lpSockAddrLen*パラメーターは無視されます。

データグラム・ソケットの場合、データは、最初のエンキュー・データグラムから、指定されたバッファーのサイズまで抽出されます。 データグラムが指定されたバッファーより大きい場合、バッファーはメッセージの最初の部分で埋め込まれ、超過データは失われ`ReceiveFrom`、エラー・コードが WSAEMSGSIZE に設定された SOCKET_ERROR の値を戻します。

*lpSockAddr*が 0 以外で、ソケットがタイプ SOCK_DGRAM場合、データを送信したソケットのネットワーク・アドレスが対応する[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体にコピーされます。 *lpSockAddrLen*によって指す値はこの構造体のサイズに初期化され、そこに格納されているアドレスの実際のサイズを示すために戻り値に変更されます。 ソケットで受信データが利用できない場合、ソケットが`ReceiveFrom`非ブロッキングでない限り、呼び出しはデータの到着を待機します。 この場合、エラー・コードが WSAEWOULDBLOCK に設定された SOCKET_ERROR の値が戻されます。 コールバック`OnReceive`を使用して、いつより多くのデータが到着するかを判断できます。

ソケットがタイプ SOCK_STREAMで、リモート側が接続を正常にシャットダウンした場合、a`ReceiveFrom`は 0 バイト受信して直ちに完了します。

## <a name="casyncsocketreceivefromex"></a><a name="receivefromex"></a>同期ソケット::受信FromEx

データグラムを受信し、ソース アドレスを[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体または*rSocketAddress* (IPv6 アドレスを処理する) に格納するには、このメンバー関数を呼び出します。

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

*ヌフレン*<br/>
*lpBuf*の長さ (バイト単位)。

*をクリックします。*<br/>
ドット番号の`CString`IP アドレスを受け取るオブジェクトへの参照。

*をクリックします。*<br/>
ポートを格納する UINT への参照。

*Nflags*<br/>
呼び出しの方法を指定します。 この関数のセマンティクスは、ソケット オプションと*nFlags*パラメーターによって決定されます。 後者は、次の値のいずれかを C++ **OR**演算子と組み合わせることによって構成されます。

- MSG_PEEK受信データをピークします。 データはバッファーにコピーされますが、入力キューからは削除されません。

- MSG_OOB アウトオブバンド データを処理します。

### <a name="return-value"></a>戻り値

エラーが発生しない場合は`ReceiveFromEx`、受信したバイト数を返します。 接続が閉じられている場合は、0 を返します。 それ以外の場合は、SOCKET_ERROR の値が返され、呼び出すことによって`GetLastError`特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- *引数 lpSockAddrLen*が無効でした: *lpSockAddr*バッファーが小さすぎてピア アドレスを収容できませんでした。

- WINDOWS ソケットのブロック操作が進行中です。

- WSAEINVAL ソケットが に`Bind`バインドされていません。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAMのみ)。

- 記述子がソケットではありません。

- WSAEOPNOTSUPP MSG_OOB指定されましたが、ソケットのタイプがSOCK_STREAMではありません。

- ソケットがシャットダウンされました。*nHow*を 0`ReceiveFromEx`または 2`ShutDown`に設定して呼び出した後で、ソケットを呼び出す方法はありません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、`ReceiveFromEx`操作はブロックされます。

- 指定されたバッファーに収まらないデータグラムが大きすぎて切り捨てられました。

- タイムアウトなどの障害により、仮想回線が中断されました。

- リモート側で仮想回線がリセットされました。

### <a name="remarks"></a>解説

この関数は、(接続されている可能性のある) ソケット上の受信データを読み取り、データの送信元のアドレスをキャプチャするために使用されます。

この関数は、古いプロトコルと同様に IPv6 アドレスを処理する点を除いて[、CAsyncSocket::ReceiveFrom](#receivefrom)と同じです。

SOCK_STREAMタイプのソケットの場合、現在使用可能な情報の数が、指定されたバッファーのサイズまで戻されます。 ソケットが帯域外データ (ソケットオプション SO_OOBINLINE) のインライン受信用に設定されており、アウトオブバンド データが未読である場合は、アウトオブバンド データのみが返されます。 アプリケーションは、このオプション`IOCtlSIOCATMARK`を使用`OnOutOfBandData`するか、またはこれ以上帯域外データを読み取る必要があるかどうかを判断できます。 *SOCK_STREAMソケットの場合、lpSockAddr*および*lpSockAddrLen*パラメーターは無視されます。

データグラム・ソケットの場合、データは、最初のエンキュー・データグラムから、指定されたバッファーのサイズまで抽出されます。 データグラムが指定されたバッファーより大きい場合、バッファーはメッセージの最初の部分で埋め込まれ、超過データは失われ`ReceiveFromEx`、エラー・コードが WSAEMSGSIZE に設定された SOCKET_ERROR の値を戻します。

*lpSockAddr*が 0 以外で、ソケットがタイプ SOCK_DGRAM場合、データを送信したソケットのネットワーク・アドレスが対応する[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体にコピーされます。 *lpSockAddrLen*によって指す値はこの構造体のサイズに初期化され、そこに格納されているアドレスの実際のサイズを示すために戻り値に変更されます。 ソケットで受信データが利用できない場合、ソケットが`ReceiveFromEx`非ブロッキングでない限り、呼び出しはデータの到着を待機します。 この場合、エラー・コードが WSAEWOULDBLOCK に設定された SOCKET_ERROR の値が戻されます。 コールバック`OnReceive`を使用して、いつより多くのデータが到着するかを判断できます。

ソケットがタイプ SOCK_STREAMで、リモート側が接続を正常にシャットダウンした場合、a`ReceiveFromEx`は 0 バイト受信して直ちに完了します。

## <a name="casyncsocketsend"></a><a name="send"></a>同期ソケット::送信

接続されているソケットでデータを送信するには、このメンバー関数を呼び出します。

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
送信するデータを格納しているバッファー。

*ヌフレン*<br/>
*lpBuf*単位のデータの長さ (バイト単位)。

*Nflags*<br/>
呼び出しの方法を指定します。 この関数のセマンティクスは、ソケット オプションと*nFlags*パラメーターによって決定されます。 後者は、次の値のいずれかを C++ **OR**演算子と組み合わせることによって構成されます。

- MSG_DONTROUTE データがルーティングの対象でないことを指定します。 Windows ソケットの供給業者は、このフラグを無視することができます。

- MSG_OOB 帯域外データを送信します (SOCK_STREAMのみ)。

### <a name="return-value"></a>戻り値

エラーが発生しない場合は`Send`、送信された文字の総数を返します。 (これは*nBufLen*で示される数より小さい場合があることに注意してください。それ以外の場合は、SOCKET_ERRORの値が返され[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- WSAEACCES 要求されたアドレスはブロードキャスト・アドレスですが、適切なフラグが設定されていません。

- WINDOWS ソケットのブロック操作が進行中です。

- WSAEFAULT*引数 lpBuf*がユーザー・アドレス・スペースの有効な部分にありません。

- WSAENETRESET Windows ソケットの実装によって接続が削除されたため、接続をリセットする必要があります。

- WSAENOBUFS Windows ソケットの実装は、バッファーのデッドロックを報告します。

- ソケットが接続されていません。

- 記述子がソケットではありません。

- WSAEOPNOTSUPP MSG_OOB指定されましたが、ソケットのタイプがSOCK_STREAMではありません。

- ソケットがシャットダウンされました。*nHow*を 1`Send`または 2`ShutDown`に設定して呼び出した後で、ソケットを呼び出す方法はありません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、要求された操作はブロックされます。

- WSAEMSGSIZE ソケットはSOCK_DGRAM型であり、データグラムは Windows ソケット実装でサポートされている最大値より大きくなっています。

- WSAEINVAL ソケットが に`Bind`バインドされていません。

- タイムアウトなどの障害により、仮想回線が中断されました。

- リモート側で仮想回線がリセットされました。

### <a name="remarks"></a>解説

`Send`は、接続されたストリームまたはデータグラム ソケットに送信データを書き込むために使用されます。 データグラム ソケットの場合、基になるサブネット`iMaxUdpDg`の最大 IP パケット サイズを超えないように注意する必要があります。 [WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) `AfxSocketInit` データが長すぎて基底のプロトコルを介してアトミックに渡されない場合、エラー WSAEMSGSIZE`GetLastError`は を介して返され、データは送信されません。

データグラム・ソケットの場合、a`Send`が正常に完了しても、データが正常に配信されたことを示すわけではありません。

SOCK_STREAM`CAsyncSocket`タイプのオブジェクトでは、書き込まれるバイト数は、ローカル・ホストと外部ホストの両方でバッファーが使用可能に応じて、1 から要求された長さの間にすることができます。

### <a name="example"></a>例

  [の](#onsend)例を参照してください。

## <a name="casyncsocketsendto"></a><a name="sendto"></a>同期ソケット::送信

特定の宛先にデータを送信するには、このメンバー関数を呼び出します。

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
送信するデータを格納しているバッファー。

*ヌフレン*<br/>
*lpBuf*単位のデータの長さ (バイト単位)。

*をクリックします。*<br/>
ソケット アプリケーションを識別するポート。

*アドレスを指定します。*<br/>
このオブジェクトが接続されているソケットのネットワーク アドレス:"ftp.microsoft.com"などのコンピュータ名、または "128.56.22.8" などのドット番号。

*Nflags*<br/>
呼び出しの方法を指定します。 この関数のセマンティクスは、ソケット オプションと*nFlags*パラメーターによって決定されます。 後者は、次の値のいずれかを C++ **OR**演算子と組み合わせることによって構成されます。

- MSG_DONTROUTE データがルーティングの対象でないことを指定します。 Windows ソケットの供給業者は、このフラグを無視することができます。

- MSG_OOB 帯域外データを送信します (SOCK_STREAMのみ)。

*lpSockAddr*<br/>
ターゲット・ソケットのアドレスを含む[SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体へのポインター。

*nソックアドルレン*<br/>
*lpSockAddr*のアドレスの長さ (バイト単位)。

### <a name="return-value"></a>戻り値

エラーが発生しない場合は`SendTo`、送信された文字の総数を返します。 (これは*nBufLen*で示される数より小さい場合があることに注意してください。それ以外の場合は、SOCKET_ERRORの値が返され[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- WSAEACCES 要求されたアドレスはブロードキャスト・アドレスですが、適切なフラグが設定されていません。

- WINDOWS ソケットのブロック操作が進行中です。

- WSAEFAULT *lpBuf*または*lpSockAddr*パラメーターがユーザー・アドレス・スペースの一部ではないか、*または引数 lpSockAddr*が小さすぎる[(SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体のサイズより小さい) 。

- WSAEINVAL ホスト名が無効です。

- WSAENETRESET Windows ソケットの実装によって接続が削除されたため、接続をリセットする必要があります。

- WSAENOBUFS Windows ソケットの実装は、バッファーのデッドロックを報告します。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAMのみ)。

- 記述子がソケットではありません。

- WSAEOPNOTSUPP MSG_OOB指定されましたが、ソケットのタイプがSOCK_STREAMではありません。

- ソケットがシャットダウンされました。*nHow*を 1`SendTo`または 2`ShutDown`に設定して呼び出した後で、ソケットを呼び出す方法はありません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、要求された操作はブロックされます。

- WSAEMSGSIZE ソケットはSOCK_DGRAM型であり、データグラムは Windows ソケット実装でサポートされている最大値より大きくなっています。

- タイムアウトなどの障害により、仮想回線が中断されました。

- リモート側で仮想回線がリセットされました。

- 指定されたアドレスはローカル・マシンからは使用できません。

- 指定されたファミリー内の WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。

- 宛先アドレスが必要です。

- この時点では、このホストからネットワークにアクセスできません。

### <a name="remarks"></a>解説

`SendTo`は、データグラムソケットまたはストリームソケットで使用され、ソケットに送信データを書き込むために使用されます。 データグラム ソケットの場合は`iMaxUdpDg`[、AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)によって入力された[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata)構造体の要素によって指定される、基になるサブネットの最大 IP パケット サイズを超えないように注意する必要があります。 データが長すぎて基底のプロトコルを介してアトミックに渡されない場合、エラー WSAEMSGSIZE が返され、データは送信されません。

a`SendTo`が正常に完了しても、データが正常に配信されたことを示すわけではありません。

`SendTo`は *、SOCK_DGRAMソケットで、lpSockAddr*パラメーターで指定された特定のソケットにデータグラムを送信するためにのみ使用されます。

ブロードキャストを送信するには (SOCK_DGRAMのみ *)、lpSockAddr*パラメーターのアドレスは、Windows ソケット ヘッダー ファイル WINSOCK で定義されている特別な IP アドレス INADDR_BROADCASTを使用して構築する必要があります。H) と目的のポート番号。 または *、lpszHostAddress*パラメーターが NULL の場合、ソケットはブロードキャスト用に構成されます。 ブロードキャスト データグラムが断片化が発生する可能性のあるサイズを超えることは一般的に、データグラムのデータ部分 (ヘッダーを除く) が 512 バイトを超えてはならないことを意味します。

IPv6 アドレスを処理するには[、CAsyncSocket::SendToEx を](#sendtoex)使用します。

## <a name="casyncsocketsendtoex"></a><a name="sendtoex"></a>同期ソケット::送信ToEx

特定の宛先にデータを送信する (IPv6 アドレスを処理する) 場合は、このメンバー関数を呼び出します。

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
送信するデータを格納しているバッファー。

*ヌフレン*<br/>
*lpBuf*単位のデータの長さ (バイト単位)。

*をクリックします。*<br/>
ソケット アプリケーションを識別するポート。

*アドレスを指定します。*<br/>
このオブジェクトが接続されているソケットのネットワーク アドレス:"ftp.microsoft.com"などのコンピュータ名、または "128.56.22.8" などのドット番号。

*Nflags*<br/>
呼び出しの方法を指定します。 この関数のセマンティクスは、ソケット オプションと*nFlags*パラメーターによって決定されます。 後者は、次の値のいずれかを C++ **OR**演算子と組み合わせることによって構成されます。

- MSG_DONTROUTE データがルーティングの対象でないことを指定します。 Windows ソケットの供給業者は、このフラグを無視することができます。

- MSG_OOB 帯域外データを送信します (SOCK_STREAMのみ)。

### <a name="return-value"></a>戻り値

エラーが発生しない場合は`SendToEx`、送信された文字の総数を返します。 (これは*nBufLen*で示される数より小さい場合があることに注意してください。それ以外の場合は、SOCKET_ERRORの値が返され[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- WSAEACCES 要求されたアドレスはブロードキャスト・アドレスですが、適切なフラグが設定されていません。

- WINDOWS ソケットのブロック操作が進行中です。

- WSAEFAULT *lpBuf*または*lpSockAddr*パラメーターがユーザー・アドレス・スペースの一部ではないか、*または引数 lpSockAddr*が小さすぎる[(SOCKADDR](/windows/win32/winsock/sockaddr-2)構造体のサイズより小さい) 。

- WSAEINVAL ホスト名が無効です。

- WSAENETRESET Windows ソケットの実装によって接続が削除されたため、接続をリセットする必要があります。

- WSAENOBUFS Windows ソケットの実装は、バッファーのデッドロックを報告します。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAMのみ)。

- 記述子がソケットではありません。

- WSAEOPNOTSUPP MSG_OOB指定されましたが、ソケットのタイプがSOCK_STREAMではありません。

- ソケットがシャットダウンされました。*nHow*を 1`SendToEx`または 2`ShutDown`に設定して呼び出した後で、ソケットを呼び出す方法はありません。

- WSAEWOULDBLOCK ソケットは非ブロッキングとしてマークされ、要求された操作はブロックされます。

- WSAEMSGSIZE ソケットはSOCK_DGRAM型であり、データグラムは Windows ソケット実装でサポートされている最大値より大きくなっています。

- タイムアウトなどの障害により、仮想回線が中断されました。

- リモート側で仮想回線がリセットされました。

- 指定されたアドレスはローカル・マシンからは使用できません。

- 指定されたファミリー内の WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。

- 宛先アドレスが必要です。

- この時点では、このホストからネットワークにアクセスできません。

### <a name="remarks"></a>解説

このメソッドは、古いプロトコルと同様に IPv6 アドレスを処理する点を除いて[、CAsyncSocket::SendTo](#sendto)と同じです。

`SendToEx`は、データグラムソケットまたはストリームソケットで使用され、ソケットに送信データを書き込むために使用されます。 データグラム ソケットの場合は`iMaxUdpDg`[、AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)によって入力された[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata)構造体の要素によって指定される、基になるサブネットの最大 IP パケット サイズを超えないように注意する必要があります。 データが長すぎて基底のプロトコルを介してアトミックに渡されない場合、エラー WSAEMSGSIZE が返され、データは送信されません。

a`SendToEx`が正常に完了しても、データが正常に配信されたことを示すわけではありません。

`SendToEx`は *、SOCK_DGRAMソケットで、lpSockAddr*パラメーターで指定された特定のソケットにデータグラムを送信するためにのみ使用されます。

ブロードキャストを送信するには (SOCK_DGRAMのみ *)、lpSockAddr*パラメーターのアドレスは、Windows ソケット ヘッダー ファイル WINSOCK で定義されている特別な IP アドレス INADDR_BROADCASTを使用して構築する必要があります。H) と目的のポート番号。 または *、lpszHostAddress*パラメーターが NULL の場合、ソケットはブロードキャスト用に構成されます。 ブロードキャスト データグラムが断片化が発生する可能性のあるサイズを超えることは一般的に、データグラムのデータ部分 (ヘッダーを除く) が 512 バイトを超えてはならないことを意味します。

## <a name="casyncsocketsetsockopt"></a><a name="setsockopt"></a>同期ソケット::セットソックオプト

ソケット オプションを設定するには、このメンバー関数を呼び出します。

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>パラメーター

*オプション名*<br/>
値を設定するソケット オプション。

*オプション値*<br/>
要求されたオプションの値が指定されているバッファーへのポインター。

*nオプションレン*<br/>
バイト単位の*lpOptionValue*バッファーのサイズ。

*nレベル*<br/>
オプションが定義されているレベル。サポートされているレベルはSOL_SOCKETとIPPROTO_TCPだけです。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- プロセス アドレス 空間の有効な部分に*ありません*。

- WINDOWS ソケットのブロック操作が進行中です。

- n*レベル*が無効であるか、*または情報が無効*です。

- SO_KEEPALIVEが設定されている場合、接続がタイムアウトしました。

- WSAENOPROTOOPT オプションが不明であるか、サポートされていません。 特に、SO_BROADCASTタイプ SOCK_STREAMのソケットではサポートされませんが、SO_DONTLINGER、SO_KEEPALIVE、SO_LINGER、およびSO_OOBINLINEは、タイプ SOCK_DGRAM のソケットではサポートされません。

- SO_KEEPALIVEが設定されている場合、WSAENOTCONN 接続はリセットされました。

- 記述子がソケットではありません。

### <a name="remarks"></a>解説

`SetSockOpt`任意のタイプのソケットに関連付けられたソケットオプションの現在の値を任意の状態に設定します。 オプションは複数のプロトコルレベルで存在することができますが、この仕様では、最上部の「ソケット」レベルに存在するオプションのみを定義します。 オプションは、通常のデータ・ストリームで急送データを受信するかどうか、ブロードキャスト・メッセージをソケットで送信できるかどうかなどのソケット操作に影響を与えます。

ソケット オプションには、機能または動作を有効または無効にするブール型オプションと、整数値または構造体を必要とするオプションの 2 種類があります。 ブール値オプションを有効にするには *、0*以外の整数を指定します。 オプション*lpOptionValue*を無効にするには、0 に等しい整数を指します。 *nOptionLen*はブール値`sizeof(BOOL)`オプションと等しくする必要があります。 その他のオプションの場合 *、lpOptionValue*はオプションの目的の値を含む整数または構造体を指し *、nOptionLen*は整数または構造体の長さです。

SO_LINGERは、未送信データがソケットにキューに入れられ、ソケットを`Close`クローズするために関数が呼び出されたときに実行されるアクションを制御します。

デフォルトでは、ソケットは既に使用されているローカルアドレスにバインドできません[(Bind](#bind)を参照)。 しかし、この方法でアドレスを「再利用」することが望ましい場合もあります。 すべての接続はローカルアドレスとリモートアドレスの組み合わせによって一意に識別されるため、リモートアドレスが異なる限り、2つのソケットを同じローカルアドレスにバインドしても問題はありません。

目的のアドレスが別のソケットによって既`Bind`に使用されているためにソケットの呼び出しを許可しないことを Windows ソケットの実装に通知するには、アプリケーションは、呼び出しを発行する前にソケット`Bind`のSO_REUSEADDRソケット オプションを設定する必要があります。 このオプションは`Bind`呼び出し時にのみ解釈されることに注意してください:既存のアドレスにバインドされないソケットにオプションを設定することは不要です(ただし無害です)、`Bind`呼び出し後のオプションの設定やリセットは、このソケットやその他のソケットには影響しません。

アプリケーションは、Windows ソケットの実装で、SO_KEEPALIVE ソケット オプションをオンにすることで、伝送制御プロトコル (TCP) 接続で "キープアライブ" パケットの使用を有効にすることを要求できます。 Windows ソケットの実装では、キープアライブの使用をサポートする必要はありません: その場合、正確なセマンティクスは実装固有ですが、RFC 1122 のセクション 4.2.3.6 に準拠する必要があります: "インターネット ホストの要件 - 通信層。 「キープ・アライブ」の結果として接続がドロップされると、エラー・コード WSAENETRESET はソケット上で進行中の呼び出しに戻され、それ以降の呼び出しは WSAENOTCONN で失敗します。

TCP_NODELAYオプションは Nagle アルゴリズムを無効にします。 Nagle アルゴリズムは、フルサイズのパケットが送信されるまで未確認の送信データをバッファリングすることによって、ホストが送信する小さなパケットの数を減らすために使用されます。 ただし、アプリケーションによっては、このアルゴリズムによってパフォーマンスが低下し、TCP_NODELAYを使用してオフにできます。 アプリケーション作成者は、設定がネットワークのパフォーマンスに大きな悪影響を及ぼす可能性 TCP_NODELAYがあるため、その影響が十分に理解され、望ましい場合を除き、TCP_NODELAYを設定しないでください。 TCP_NODELAYレベルIPPROTO_TCPを使用する唯一のサポートされているソケットオプションです。その他のオプションはすべて、レベルSOL_SOCKETを使用します。

Windows ソケットの一部の実装では、SO_DEBUG オプションがアプリケーションによって設定されている場合に、出力デバッグ情報を提供します。

では、次の`SetSockOpt`オプションがサポートされています。 型は *、lpOptionValue*によってアドレス指定されるデータの種類を識別します。

|値|Type|意味|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|ソケットでブロードキャスト メッセージの送信を許可します。|
|SO_DEBUG|BOOL|デバッグ情報を記録します。|
|SO_DONTLINGER|BOOL|未送信のデータ`Close`が送信されるのを待つブロックしないでください。 このオプションを設定することは、SO_LINGERをゼロ`l_onoff`に設定することと同じです。|
|SO_DONTROUTE|BOOL|ルーティングしない: インターフェイスに直接送信します。|
|SO_KEEPALIVE|BOOL|キープアライブを送信します。|
|SO_LINGER|`struct LINGER`|未送信`Close`のデータが存在する場合は、オンにします。|
|SO_OOBINLINE|BOOL|通常のデータ ストリームで帯域外データを受信します。|
|SO_RCVBUF|**int**|受信のバッファー サイズを指定します。|
|SO_REUSEADDR|BOOL|ソケットを既に使用されているアドレスにバインドできるようにします。 ([バインドを](#bind)参照してください。|
|SO_SNDBUF|**int**|送信のバッファ サイズを指定します。|
|TCP_NODELAY|BOOL|送信結合用の Nagle アルゴリズムを無効にします。|

サポートされていないバークレー・ソフトウェア・ディストリビューション (BSD) オプション`SetSockOpt`は次のとおりです。

|値|Type|意味|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|ソケットがリッスンしています|
|SO_ERROR|**int**|エラーステータスを取得し、クリアします。|
|SO_RCVLOWAT|**int**|低いウォーターマークを受け取ります。|
|SO_RCVTIMEO|**int**|[受信タイムアウト]|
|SO_SNDLOWAT|**int**|低いウォーターマークを送信します。|
|SO_SNDTIMEO|**int**|送信タイムアウト。|
|SO_TYPE|**int**|ソケットの型。|
|IP_OPTIONS||IP ヘッダーのオプション フィールドを設定します。|

## <a name="casyncsocketshutdown"></a><a name="shutdown"></a>同期ソケット::シャットダウン

ソケットの送信、受信、またはその両方を無効にします。

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>パラメーター

*Nhow*<br/>
次の列挙値を使用して、許可されなくなる操作の種類を示すフラグ。

- **受信 = 0**

- **送信 = 1**

- **両方とも = 2**

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 を指定し[、GetLastError](#getlasterror)を呼び出すことによって特定のエラー コードを取得できます。 このメンバー関数には、次のエラーが適用されます。

- WSANOTINITIALISED 成功した[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)は、この API を使用する前に発生する必要があります。

- WSAENETDOWN Windows ソケットの実装で、ネットワーク サブシステムに障害が発生したことを検出しました。

- WSAEINVAL *nどのように*無効です。

- WINDOWS ソケットのブロック操作が進行中です。

- WSAENOTCONN ソケットが接続されていません (SOCK_STREAMのみ)。

- 記述子がソケットではありません。

### <a name="remarks"></a>解説

`ShutDown`は、受信、送信、またはその両方を無効にするために、すべてのタイプのソケットで使用されます。 *nHow が*0 の場合、ソケットでの後続の受信は許可されません。 これは下位のプロトコル層には影響しません。

伝送制御プロトコル (TCP) の場合、TCP ウィンドウは変更されず、ウィンドウが使い果たされるまで受信データは受け入れられます (ただし確認はされません)。 ユーザー データグラム プロトコル (UDP) では、受信データグラムが受け入れられ、キューに入れられます。 いずれの場合も、ICMP エラー パケットは生成されません。 *nHow が*1 の場合、後続の送信は許可されません。 TCP ソケットの場合、FIN が送信されます。 *n「How」* を 2 に設定すると、上記のとおり、送信と受信の両方が無効になります。

ソケットを`ShutDown`閉じず、ソケットに接続されたリソースは呼び出されるまで`Close`解放されないことに注意してください。 アプリケーションは、ソケットがシャットダウンされた後にソケットを再利用できることに頼るべきではありません。 特に、このようなソケットでの使用をサポートするために、Windows ソケットの`Connect`実装は必要ありません。

### <a name="example"></a>例

  [「CAsyncSocket::受信時](#onreceive)」の例を参照してください。

## <a name="casyncsocketsocket"></a><a name="socket"></a>ソケットソケット

ソケット ハンドルを割り当てます。

```
BOOL Socket(
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    int nProtocolType = 0,
    int nAddressFormat = PF_INET);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
または`SOCK_STREAM``SOCK_DGRAM`を指定します。

*イベント*<br/>
アプリケーションが対象とするネットワーク イベントの組み合わせを指定するビットマスク。

- `FD_READ`: 読み取り準備の通知を受け取りたい。

- `FD_WRITE`: 書き込みの準備が整っている旨の通知を受け取りたい。

- `FD_OOB`: 帯域外データの到着通知を受け取りたい。

- `FD_ACCEPT`: 着信接続の通知を受信する。

- `FD_CONNECT`: 接続完了の通知を受信する。

- `FD_CLOSE`: ソケットクロージャの通知を受け取りたい。

*プロトコルタイプ*<br/>
指定されたアドレス・ファミリーに固有のソケットで使用されるプロトコル。

*アドレスフォーマット*<br/>
アドレス ファミリの仕様。

### <a name="return-value"></a>戻り値

正常に終了した場合は、`TRUE` を返します。それ以外の場合は、`FALSE` を返します。

### <a name="remarks"></a>解説

このメソッドは、ソケット ハンドルを割り当てます。 指定されたアドレスにソケットをバインドする[CAsyncSocket::Bind](#bind)を呼び出さないので、`Bind`指定されたアドレスにソケットをバインドするために後で呼び出す必要があります。 [CAsyncSocket::SetSockOpt](#setsockopt)を使用して、ソケットオプションをバインドする前に設定できます。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CSocket クラス](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
