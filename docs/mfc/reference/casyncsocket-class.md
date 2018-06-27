---
title: CAsyncSocket クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c98703cbe68efc0ca7e40d3b25d0178d826855a
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952607"
---
# <a name="casyncsocket-class"></a>CAsyncSocket クラス
Windows ソケットを表します:、ネットワーク通信エンドポイントです。  
  
## <a name="syntax"></a>構文  
  
```  
class CAsyncSocket : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|`CAsyncSocket` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::Accept](#accept)|ソケットの接続を受け入れます。|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|ソケットのイベント通知を要求します。|  
|[CAsyncSocket::Attach](#attach)|ソケットのハンドルをアタッチ、`CAsyncSocket`オブジェクト。|  
|[CAsyncSocket::Bind](#bind)|ソケット、ローカル アドレスに関連付けます。|  
|[CAsyncSocket::Close](#close)|ソケットを閉じます。|  
|[不要なため](#connect)|ピア ソケットへの接続を確立します。|  
|[CAsyncSocket::Create](#create)|ソケットを作成します。|  
|[CAsyncSocket::Detach](#detach)|ソケットのハンドルからのデタッチ、`CAsyncSocket`オブジェクト。|  
|[CAsyncSocket::FromHandle](#fromhandle)|ポインターを返します、`CAsyncSocket`オブジェクト、ソケット ハンドルを指定します。|  
|[CAsyncSocket::GetLastError](#getlasterror)|失敗した最後の操作のエラー状態を取得します。|  
|[で](#getpeername)|ソケットが接続されているピア ソケットのアドレスを取得します。|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|ソケットが接続されている (ハンドルの IPv6 アドレス) のピア ソケットのアドレスを取得します。|  
|[で](#getsockname)|ソケットのローカル名を取得します。|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|ソケット (IPv6 アドレスを処理) のローカル名を取得します。|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|ソケット オプションを取得します。|  
|[CAsyncSocket::IOCtl](#ioctl)|ソケットのモードを制御します。|  
|[CAsyncSocket::Listen](#listen)|接続要求をリッスンするソケットを確立します。|  
|[CAsyncSocket::Receive](#receive)|ソケットからデータを受信します。|  
|[で](#receivefrom)|データグラムを受信し、送信元アドレスを格納します。|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|データグラムを受信し、送信元アドレス (IPv6 アドレスを処理する) を格納します。|  
|[CAsyncSocket::Send](#send)|接続されたソケットにデータを送信します。|  
|[で](#sendto)|特定の宛先にデータを送信します。|  
|[CAsyncSocket::SendToEx](#sendtoex)|特定の宛先 (IPv6 アドレスを処理する) にデータを送信します。|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|ソケット オプションを設定します。|  
|[CAsyncSocket::ShutDown](#shutdown)|無効に`Send`や`Receive`ソケットで呼び出します。|  
|[CASyncSocket::Socket](#socket)|ソケット ハンドルを割り当てます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|呼び出すことによって保留中の接続要求を受け付けられるを待機中のソケットに通知`Accept`です。|  
|[CAsyncSocket::OnClose](#onclose)|ソケットが接続されているソケットが閉じに通知します。|  
|[CAsyncSocket::OnConnect](#onconnect)|接続の試行が完了したこと、かどうかが正常にまたはエラーで接続のソケットに通知します。|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|緊急のメッセージでは通常、ソケットに読み込まれる帯域外のデータが受信ソケットに通知します。|  
|[CAsyncSocket::OnReceive](#onreceive)|呼び出すことによって取得するデータがあることを待機中のソケットに通知`Receive`です。|  
|[CAsyncSocket::OnSend](#onsend)|ソケットを呼び出してデータを送信できることを通知`Send`です。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|新しい値を割り当てます、`CAsyncSocket`オブジェクト。|  
|[CAsyncSocket::operator ソケット](#operator_socket)|この演算子を使用して、取得、**ソケット**のハンドル、`CAsyncSocket`オブジェクト。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|示します、**ソケット**ハンドルは、これに接続されている`CAsyncSocket`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 クラス`CAsyncSocket`と共に MFC Windows ソケットを使用するプログラマのオブジェクト指向の抽象化を提供する、Windows ソケット関数 API をカプセル化します。  
  
 このクラスは、ネットワーク通信を理解していることを前提に基づいています。 ブロック、バイト順序の違いを処理する、Unicode とマルチバイト文字の間の変換セット (MBCS) 文字列。 これらの問題を管理する方が便利なインターフェイスを実行する場合に、クラスを参照してください。 [CSocket](../../mfc/reference/csocket-class.md)です。  
  
 使用する、`CAsyncSocket`オブジェクト、そのコンス トラクターの呼び出しを呼び出す、[作成](#create)を基になるソケット ハンドルを作成する関数 (型`SOCKET`)、受け入れられたソケット上を除きます。 サーバー ソケットの呼び出しの[リッスン](#listen)メンバー関数の場合、クライアント ソケットの呼び出し、[接続](#connect)メンバー関数。 サーバー ソケットを呼び出す必要があります、 [Accept](#accept)接続要求を受け取った関数。 残りの使用`CAsyncSocket`ソケットの間の通信を実行する関数。 完了すると、破棄、`CAsyncSocket`ヒープで作成した場合のオブジェクト以外の場合は、デストラクターを自動的に呼び出します、[閉じる](#close)関数。 **ソケット**データ型は、資料に記載されて[Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)です。  
  
> [!NOTE]
>  静的にリンクされた MFC アプリケーションのセカンダリ スレッドで MFC ソケットを使用して、呼び出す必要があります`AfxSocketInit`ソケット ライブラリを初期化するためにソケットを使用する各スレッドにします。 既定では、`AfxSocketInit`プライマリ スレッドでのみ呼び出すことができます。  
  
 詳細については、次を参照してください。 [Windows ソケット: を使用してクラス CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) 、関連する記事、だけでなく[Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxsock.h  
  
##  <a name="accept"></a>  CAsyncSocket::Accept  
 ソケットへの接続を受け入れるようにこのメンバー関数を呼び出します。  
  
```  
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,  
    SOCKADDR* lpSockAddr = NULL,  
    int* lpSockAddrLen = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *rConnectedSocket*  
 接続に使用される新しいソケットを識別する参照。  
  
 *lpSockAddr*  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)接続のアドレスを受け取るソケット、ネットワーク上で認知されています。 正確な形式、 *lpSockAddr*引数は、アドレス ファミリがソケットの作成時に設定によって決まります。 場合*lpSockAddr*や*lpSockAddrLen*と等しい**NULL**、受け入れられたソケットのリモート アドレスに関する情報も返されません。  
  
 *lpSockAddrLen*  
 指定されたアドレスの長さへのポインター *lpSockAddr* (バイト単位)。 *LpSockAddrLen*値結果パラメーターです: 指す領域の量を最初に含んでいなければなりません*lpSockAddr*; 返された場合はバイト単位で返されたアドレスの実際の長さが含まれます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEFAULT** 、 *lpSockAddrLen*引数が小さすぎます (のサイズよりも小さいか、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体)。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **WSAEINVAL** `Listen`に同意する前に呼び出されたでした。  
  
- **WSAEMFILE**キューが入ったを受け入れるように空と使用可能な記述子がありません。  
  
- **WSAENOBUFS**バッファー領域が不足しています。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP**参照先のソケットが接続指向のサービスをサポートする型ではありません。  
  
- **WSAEWOULDBLOCK**ソケットがマークされている非ブロッキング接続が許容されるために存在しません。  
  
### <a name="remarks"></a>Remarks  
 このルーチンは、接続待ちのキューの最初の接続を抽出し、このソケットと同じプロパティを持つ新しいソケットを作成しにアタッチ*rConnectedSocket*です。 保留中の接続が、キューに存在しない場合`Accept`は 0 を返しますと`GetLastError`はエラーを返します。 受け入れられたソケット ( *rConnectedSocket)* をより多くの接続を受け入れるように使用することはできません。 元のソケット開いたままで、リッスンしています。  
  
 引数*lpSockAddr* 、ソケット接続のアドレスを使用して読み込まれた結果パラメーターは、認識されているため、通信レイヤー。 `Accept` ソケットの接続に基づく種類でなど使用**SOCK_STREAM**です。  
  
##  <a name="asyncselect"></a>  CAsyncSocket::AsyncSelect  
 ソケットのイベント通知を要求するには、このメンバー関数を呼び出します。  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *lEvent*  
 アプリケーションが必要とするネットワーク イベントの組み合わせを指定するビットマスク。  
  
- **FD_READ**を読み取るのための準備完了の通知を受信します。  
  
- **FD_WRITE**データが読み取り可能な場合に通知を受信します。  
  
- **FD_OOB**の帯域外のデータの到着の通知を受信します。  
  
- **FD_ACCEPT**着信接続の通知を受信します。  
  
- **FD_CONNECT**接続の結果の通知を受信します。  
  
- **FD_CLOSE**ピアによってソケットが閉じられたときに通知を受信します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEINVAL**有効な指定されたパラメーターのいずれかがないことを示します。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
### <a name="remarks"></a>Remarks  
 この関数を指定するソケットの MFC のコールバック通知関数が呼び出されます使用されます。 `AsyncSelect` 非ブロッキング モード ソケットが自動的に設定します。 詳細については、記事を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)です。  
  
##  <a name="attach"></a>  CAsyncSocket::Attach  
 アタッチするには、このメンバー関数を呼び出す、 *hSocket*へのハンドル、`CAsyncSocket`オブジェクト。  
  
```  
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *hSocket*  
 ソケットへのハンドルが含まれています。  
  
 *lEvent*  
 アプリケーションが必要とするネットワーク イベントの組み合わせを指定するビットマスク。  
  
- **FD_READ**を読み取るのための準備完了の通知を受信します。  
  
- **FD_WRITE**データが読み取り可能な場合に通知を受信します。  
  
- **FD_OOB**の帯域外のデータの到着の通知を受信します。  
  
- **FD_ACCEPT**着信接続の通知を受信します。  
  
- **FD_CONNECT**接続の結果の通知を受信します。  
  
- **FD_CLOSE**ピアによってソケットが閉じられたときに通知を受信します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。  
  
### <a name="remarks"></a>Remarks  
 **ソケット**ハンドルが、オブジェクトに格納されている[m_hSocket](#m_hsocket)データ メンバーです。  
  
##  <a name="bind"></a>  CAsyncSocket::Bind  
 ソケットにローカル アドレスを関連付けるには、このメンバー関数を呼び出します。  
  
```  
BOOL Bind(
    UINT nSocketPort,  
    LPCTSTR lpszSocketAddress = NULL);

 
BOOL Bind (
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSocketPort*  
 ソケット アプリケーションを識別するポートです。  
  
 *lpszSocketAddress*  
 ネットワーク アドレスでは、「128.56.22.8」などのピリオドで区切られた数字。 渡す、 **NULL**このパラメーターを文字列、`CAsyncSocket`インスタンスがすべてのネットワーク インターフェイス上のクライアント アクティビティを待機する必要があります。  
  
 *lpSockAddr*  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)このソケットに割り当てるアドレスを格納する構造体。  
  
 *nSockAddrLen*  
 指定されたアドレスの長さ*lpSockAddr* (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEADDRINUSE**指定されたアドレスは既に使用されています。 (を参照してください、 **SO_REUSEADDR**ソケットの下にあるオプション[SetSockOpt](#setsockopt))。  
  
- **WSAEFAULT** 、 *nSockAddrLen*引数が小さすぎます (のサイズよりも小さいか、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体)。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **WSAEAFNOSUPPORT**このポートで指定したアドレス ファミリがサポートされていません。  
  
- **WSAEINVAL**ソケットは既にアドレスにバインドされています。  
  
- **WSAENOBUFS**のに十分なバッファーの使用可能な接続が多すぎます。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 このルーチンは前に接続されていないデータグラムまたはストリーム ソケットで使用後続`Connect`または`Listen`呼び出しです。 その接続要求を受け入れることができます、前にサーバー ソケットをリッスンしている必要があります、ポート番号を選択となる Windows ソケットを呼び出すことによって`Bind`です。 `Bind` 名前のないソケットにローカル名を割り当てることで、ソケットのローカルの関連付け (ホスト アドレスとポート番号) を確立します。  
  
##  <a name="casyncsocket"></a>  CAsyncSocket::CAsyncSocket  
 空のソケット オブジェクトを構築します。  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>Remarks  
 オブジェクトを構築するには、後に呼び出す必要があります、`Create`メンバー関数を作成する、**ソケット**データ構造体し、そのアドレスをバインドします。 (待機中のソケットで使用するソケットを作成する場合は、Windows ソケット通信のサーバー側で、`Accept`呼び出し、呼び出すことはありません`Create`ソケット用です)。  
  
##  <a name="close"></a>  CAsyncSocket::Close  
 ソケットを閉じます。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarks  
 参照は、エラーで失敗するさらにできるように、この関数は、ソケット記述子を解放**切り離します**です。 これは、基になるソケットに対する最後の参照である場合、関連付けられた名前情報とキューに置かれたデータは破棄されます。 ソケット オブジェクトのデストラクターの呼び出し`Close`します。  
  
 `CAsyncSocket`のではなく`CSocket`のセマンティクス`Close`ソケット オプションの影響を受ける**SO_LINGER**と**SO_DONTLINGER**です。 詳細については、メンバー関数を参照してください。`GetSockOpt`です。  
  
##  <a name="connect"></a>  不要なため  
 独立したストリームまたはデータグラム ソケットへの接続を確立するためにこのメンバー関数を呼び出します。  
  
```  
BOOL Connect(
    LPCTSTR lpszHostAddress,  
    UINT nHostPort);

 
BOOL Connect(
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszHostAddress*  
 このオブジェクトが接続されたソケットのネットワーク アドレス:「専用」や「128.56.22.8」などのピリオドで区切られた番号などのコンピューター名。  
  
 *nHostPort*  
 ソケット アプリケーションを識別するポートです。  
  
 *lpSockAddr*  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)接続されたソケットのアドレスを格納する構造体。  
  
 *nSockAddrLen*  
 指定されたアドレスの長さ*lpSockAddr* (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 場合のエラー コードを示します**WSAEWOULDBLOCK**、およびアプリケーションは、オーバーライド可能なコールバックを使用して、アプリケーションが表示されます、`OnConnect`メッセージの接続操作が完了するとします。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEADDRINUSE**指定されたアドレスは既に使用されています。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **WSAEADDRNOTAVAIL**指定されたアドレスは、ローカル コンピューターから使用できません。  
  
- **WSAEAFNOSUPPORT**このソケットで指定されたファミリ内のアドレスは使用できません。  
  
- **使います**接続の試行は拒否されました。  
  
- **WSAEDESTADDRREQ**送信先アドレスが必要です。  
  
- **WSAEFAULT** 、 *nSockAddrLen*引数が正しくありません。  
  
- **WSAEINVAL**無効なホスト アドレス。  
  
- **WSAEISCONN**ソケットは既に接続されています。  
  
- **WSAEMFILE**ファイル記述子をこれ以上を利用できます。  
  
- **WSAENETUNREACH**ネットワークは、この時点でこのホストから到達できません。  
  
- **WSAENOBUFS**バッファー領域が不足しています。 ソケットを接続することはできません。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAETIMEDOUT**がタイムアウトしました。 接続を確立せずに接続しようとしています。  
  
- **WSAEWOULDBLOCK**ソケットがマークされている非ブロッキング接続は直ちに完了したことはできません。  
  
### <a name="remarks"></a>Remarks  
 ソケットにバインドがない場合は、一意の値が、システムによって、ローカルの関連付けを割り当てられているソケットとしてマークされている次のようにバインドされます。 されている場合、アドレスのフィールド名の構造がすべて 0 (ゼロ)`Connect`は 0 を返します。 拡張エラー情報を取得する呼び出し、`GetLastError`メンバー関数。  
  
 ストリーム ソケット (型**SOCK_STREAM**)、外部ホストへのアクティブな接続を開始します。 ソケットの呼び出しが正常に完了すると、ソケットはデータの送信/受信準備ができてです。  
  
 データグラム ソケットに関して (型**SOCK_DGRAM**)、既定の出力先を設定すると、その後で使用される`Send`と`Receive`呼び出しです。  
  
##  <a name="create"></a>  CAsyncSocket::Create  
 呼び出す、`Create`メンバー関数は、Windows ソケットを作成し、アタッチするソケット オブジェクトを構築した後です。  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSocketPort*  
 Windows ソケット ポートを選択する場合、または 0 で使用する既知のポートです。  
  
 *nSocketType*  
 **SOCK_STREAM**または**SOCK_DGRAM**です。  
  
 *lEvent*  
 アプリケーションが必要とするネットワーク イベントの組み合わせを指定するビットマスク。  
  
- **FD_READ**を読み取るのための準備完了の通知を受信します。  
  
- **FD_WRITE**書き込みのための準備完了の通知を受信します。  
  
- **FD_OOB**の帯域外のデータの到着の通知を受信します。  
  
- **FD_ACCEPT**着信接続の通知を受信します。  
  
- **FD_CONNECT**完成した接続の通知を受信します。  
  
- **FD_CLOSE**ソケットの終了の通知を受信します。  
  
 *lpszSockAddress*  
 接続のソケットでは、「128.56.22.8」などのピリオドで区切られた数のネットワーク アドレスを含む文字列へのポインター。渡す、 **NULL**このパラメーターを文字列、 **CAsyncSocket**インスタンスがすべてのネットワーク インターフェイス上のクライアント アクティビティを待機する必要があります。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEAFNOSUPPORT**指定されたアドレス ファミリがサポートされていません。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **WSAEMFILE**ファイル記述子をこれ以上を利用できます。  
  
- **WSAENOBUFS**バッファー領域が不足しています。 ソケットを作成することはできません。  
  
- **WSAEPROTONOSUPPORT**指定されたポートはサポートされていません。  
  
- **WSAEPROTOTYPE**指定したポートがこのソケットに対して無効な型です。  
  
- **WSAESOCKTNOSUPPORT**このアドレス ファミリでは、指定したソケットの種類はサポートされていません。  
  
### <a name="remarks"></a>Remarks  
 `Create` 呼び出し[ソケット](#socket)成功した場合、それを呼び出すと[バインド](#bind)指定されたアドレスにソケットをバインドします。 次のソケットの種類がサポートされています。  
  
- **SOCK_STREAM** sequenced、信頼性の高い、全二重、接続に基づくバイト ストリームを提供します。 インターネット アドレス ファミリ用には、伝送制御プロトコル (TCP) を使用します。  
  
- **SOCK_DGRAM**固定 (通常はわずか) の最大長のパケットのコネクションレス、信頼性の低いデータグラムをサポートしています。 インターネット アドレス ファミリ用には、ユーザー データグラム プロトコル (UDP) を使用します。  
  
    > [!NOTE]
    >  `Accept`メンバー関数は、新しい空への参照を受け取ります`CSocket`オブジェクトをパラメーターとして。 呼び出す前に、このオブジェクトを構築する必要があります`Accept`です。 ただし、このソケット オブジェクトがスコープ接続は閉じられますなくなる場合。 呼び出す必要はありません`Create`この新しいソケット オブジェクト。  
  
> [!IMPORTANT]
> `Create` **いない**スレッド セーフであります。  呼び出す場合、マルチ スレッド環境でそれが呼び出すことが同時に別のスレッドで、必ず、ミュー テックスまたはその他の同期ロックでは、各呼び出しを保護してください。  
  
 ストリームとデータグラム ソケットの詳細については、記事を参照してください[Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)と[Windows ソケット: ポートとソケット アドレス](../../mfc/windows-sockets-ports-and-socket-addresses.md)と[Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)。  
  
##  <a name="detach"></a>  CAsyncSocket::Detach  
 デタッチするには、このメンバー関数を呼び出す、**ソケット**中の処理、 *m_hSocket*からそのデータ メンバー、`CAsyncSocket`オブジェクトおよび設定*m_hSocket*に**NULL**.  
  
```  
SOCKET Detach();
```  
  
##  <a name="fromhandle"></a>  CAsyncSocket::FromHandle  
 ポインターを返します、`CAsyncSocket`オブジェクト。  
  
```  
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>パラメーター  
 *hSocket*  
 ソケットへのハンドルが含まれています。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CAsyncSocket`オブジェクト、または**NULL**がある場合ありません`CAsyncSocket`オブジェクトにアタッチ*hSocket*です。  
  
### <a name="remarks"></a>Remarks  
 指定した場合、**ソケット**を処理する場合、`CAsyncSocket`オブジェクトがハンドルに関連付けられていない、メンバー関数を返します**NULL**です。  
  
##  <a name="getlasterror"></a>  CAsyncSocket::GetLastError  
 失敗した最後の操作のエラー状態を取得するには、このメンバー関数を呼び出します。  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値は、このスレッドによって実行される最後の Windows ソケット API ルーチンのエラー コードを示します。  
  
### <a name="remarks"></a>Remarks  
 特定のメンバー関数は、エラーが発生したことを示すとき`GetLastError`該当するエラー コードを取得するために呼び出す必要があります。 該当するエラー コードの一覧については、個々 のメンバー関数の説明を参照してください。  
  
 エラー コードの詳細については、次を参照してください。 [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673)です。  
  
##  <a name="getpeername"></a>  で  
 このソケットが接続されているピア ソケットのアドレスを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetPeerName(
    CString& rPeerAddress,  
    UINT& rPeerPort);

 
BOOL GetPeerName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>パラメーター  
 *rPeerAddress*  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rPeerPort*  
 参照、 **UINT**ポートを格納します。  
  
 *lpSockAddr*  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)ピア ソケットの名前を受け取る。  
  
 *lpSockAddrLen*  
 指定されたアドレスの長さへのポインター *lpSockAddr* (バイト単位)。 戻り時に、 *lpSockAddrLen*引数の実際のサイズに含まれる*lpSockAddr* (バイト単位) が返されます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEFAULT** 、 *lpSockAddrLen*引数のサイズが不十分です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **接続保持**ソケットが接続されていません。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 IPv6 アドレスを処理する[CAsyncSocket::GetPeerNameEx](#getpeernameex)です。  
  
##  <a name="getpeernameex"></a>  CAsyncSocket::GetPeerNameEx  
 このソケットが接続されている (ハンドルの IPv6 アドレス) のピア ソケットのアドレスを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>パラメーター  
 *rPeerAddress*  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rPeerPort*  
 参照、 **UINT**ポートを格納します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEFAULT** 、 *lpSockAddrLen*引数のサイズが不十分です。  
  
- **WSAEINPROGRESS** Windows ソケットのブロッキング呼び出しが進行中です。  
  
- **接続保持**ソケットが接続されていません。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 この関数は、同じ[で](#getpeername)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
##  <a name="getsockname"></a>  で  
 ソケットのローカル名を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetSockName(
    CString& rSocketAddress,  
    UINT& rSocketPort);

 
BOOL GetSockName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>パラメーター  
 *rSocketAddress*  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rSocketPort*  
 参照、 **UINT**ポートを格納します。  
  
 *lpSockAddr*  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)ソケットのアドレスを受け取る。  
  
 *lpSockAddrLen*  
 指定されたアドレスの長さへのポインター *lpSockAddr* (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEFAULT** 、 *lpSockAddrLen*引数のサイズが不十分です。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEINVAL**ソケットが使用するアドレスにバインドされていない`Bind`です。  
  
### <a name="remarks"></a>Remarks  
 この呼び出しは特に便利だときに、`Connect`ことがなく呼び出しが行われた、`Bind`先にこの呼び出しのシステムによって設定されているローカルの関連付けを判断できますのみ手段を提供します。  
  
 IPv6 アドレスを処理する[CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>  CAsyncSocket::GetSockNameEx  
 ソケット (IPv6 アドレスを処理) のローカル名を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>パラメーター  
 *rSocketAddress*  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rSocketPort*  
 参照、 **UINT**ポートを格納します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEFAULT** 、 *lpSockAddrLen*引数のサイズが不十分です。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEINVAL**ソケットが使用するアドレスにバインドされていない`Bind`です。  
  
### <a name="remarks"></a>Remarks  
 この呼び出しは同じ[で](#getsockname)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
 この呼び出しは特に便利だときに、`Connect`ことがなく呼び出しが行われた、`Bind`先にこの呼び出しのシステムによって設定されているローカルの関連付けを判断できますのみ手段を提供します。  
  
##  <a name="getsockopt"></a>  CAsyncSocket::GetSockOpt  
 ソケット オプションを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetSockOpt(
    int nOptionName,  
    void* lpOptionValue,  
    int* lpOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>パラメーター  
 *nOptionName*  
 値を取得するソケット オプション。  
  
 *関連付け*  
 要求されたオプションの値が返されるバッファーへのポインター。 選択したオプションに関連付けられている値がバッファーに返されます*は*します。 整数を指す*lpOptionLen* (バイト単位) には、このバッファーのサイズを含める必要があります最初およびその、制御が戻るとき、返される値のサイズに設定されます。 **SO_LINGER**のサイズになります、`LINGER`構造体以外の他のすべてのオプションのサイズであることが、 **BOOL**または**int**オプションに応じて、します。 オプションと、「解説」セクションでは、そのサイズ一覧を参照してください。  
  
 *lpOptionLen*  
 サイズへのポインター、*は*バッファーのバイト単位です。  
  
 *nLevel*  
 オプションが定義されているレベル唯一サポートされているレベルは、**取得**と**取得できる**です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 オプションが設定されていない場合`SetSockOpt`、し`GetSockOpt`オプションの既定値を返します。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEFAULT** 、 *lpOptionLen*引数が無効です。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **WSAENOPROTOOPT**不明、またはサポートされていないオプションです。 具体的には、 **:so_broadcast**型のソケットでサポートされていない**SOCK_STREAM**、中に**SO_ACCEPTCONN**、 **SO_DONTLINGER**、 **接続**、 **SO_LINGER**、および**SO_OOBINLINE**型のソケットでサポートされていない**SOCK_DGRAM**です。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 `GetSockOpt` 任意の状態で、任意の型のソケットに関連付けられているソケット オプションの現在の値を取得しで結果を格納*は*します。 オプションでは、パケット、帯域外のデータ転送のルーティングなどのソケット操作に影響します。  
  
 次のオプションはサポートされて`GetSockOpt`です。 型によってアドレス指定されるデータの種類を識別する*は*します。 **低下**オプションは、レベルを使用して**取得できる**; 他のすべてのオプションの使用レベル**取得**です。  
  
|[値]|型|説明|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|ソケットはリッスンしています。|  
|**:SO_BROADCAST**|**BOOL**|ソケットは、ブロードキャスト メッセージの送信用に構成されています。|  
|**SO_DEBUG**|**BOOL**|デバッグを有効にするとします。|  
|**SO_DONTLINGER**|**BOOL**|True の場合、 **SO_LINGER**オプションが無効になります。|  
|**SO_DONTROUTE**|**BOOL**|ルーティングが無効です。|  
|**SO_ERROR**|**int**|エラー状態を取得し、オフにします。|  
|**接続**|**BOOL**|Keep-alive が送信されます。|  
|**SO_LINGER**|**LINGER 構造体**|現在の待機オプションを返します。|  
|**SO_OOBINLINE**|**BOOL**|帯域外のデータは、通常のデータ ストリームで受信しています。|  
|**SO_RCVBUF**|**int**|バッファー サイズを受け取ります。|  
|**SO_REUSEADDR**|**BOOL**|ソケットは、既に使用されているアドレスにバインドできます。|  
|**SO_SNDBUF**|**int**|バッファー サイズを送信します。|  
|**SO_TYPE**|**int**|ソケットの種類 (たとえば、 **SOCK_STREAM**)。|  
|**低下**|**BOOL**|送信結合用の Nagle アルゴリズムを無効にします。|  
  
 Berkeley ソフトウェア配布 (BSD) オプションはサポートされていません`GetSockOpt`は。  
  
|[値]|型|説明|  
|-----------|----------|-------------|  
|**SO_RCVLOWAT**|**int**|低水位マークが表示されます。|  
|**SO_RCVTIMEO**|**int**|受信タイムアウト。|  
|**SO_SNDLOWAT**|**int**|低水位マークを送信します。|  
|**SO_SNDTIMEO**|**int**|送信タイムアウト。|  
|**なる**||IP ヘッダーでオプションを取得します。|  
|**TCP_MAXSEG**|**int**|TCP セグメントの最大サイズを取得します。|  
  
 呼び出す`GetSockOpt`サポートされていないオプションを使用してが、エラー コードは**WSAENOPROTOOPT**から返される`GetLastError`です。  
  
##  <a name="ioctl"></a>  CAsyncSocket::IOCtl  
 ソケットのモードを制御するには、このメンバー関数を呼び出します。  
  
```  
BOOL IOCtl(
    long lCommand,  
    DWORD* lpArgument);
```  
  
### <a name="parameters"></a>パラメーター  
 *lCommand*  
 ソケットで実行するコマンドです。  
  
 *lpArgument*  
 パラメーターへのポインター *lCommand*です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEINVAL** *lCommand*は有効なコマンドではありませんか*lpArgument*がの許容可能なパラメーターでない*lCommand*、または、コマンドには適用できません、指定したソケットの種類です。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 このルーチンは、いずれかの州の任意のソケットで使用できます。 取得またはプロトコルとの通信サブシステムの独立した、ソケットに関連付けられた操作パラメーターを取得するために使用します。 次のコマンドがサポートされています。  
  
- **FIONBIO**を有効にするまたは非ブロッキング モード ソケットを無効にします。 *LpArgument*パラメーターが指す、`DWORD`する場合は 0 以外を有効にするのには、非ブロッキング モード、および無効にするが場合は 0 です。 場合`AsyncSelect`しようとするを使用して、ソケットで発行されている`IOCtl`ソケットをブロックしているモードに設定するには失敗**WSAEINVAL**です。 ソケットをブロックしているモードに設定したり防止したり、 **WSAEINVAL**エラー、アプリケーションする必要があります最初に無効に`AsyncSelect`を呼び出して`AsyncSelect`で、 *lEvent*パラメーターを 0 を呼び出す`IOCtl`.  
  
- **FIONREAD**最大で 1 つの読み取り可能バイト数を決定`Receive`このソケットから呼び出します。 *LpArgument*パラメーターが指す、`DWORD`を`IOCtl`結果を格納します。 型の場合はこのソケット**SOCK_STREAM**、 **FIONREAD** 、1 つで読み取ることができるデータ量の合計を返します`Receive`です。 これは通常と同じになるソケット キューに置かれたデータの総量。 型の場合はこのソケット**SOCK_DGRAM**、 **FIONREAD**になるソケット キューに置かれた最初のデータグラムのサイズを返します。  
  
- **SIOCATMARK**すべて帯域外のデータが読み取られたかどうかを判断します。 型のソケットにのみ適用**SOCK_STREAM**帯域外のデータの行で受信用に構成されている ( **SO_OOBINLINE**)。 読み取られる帯域外のデータが待機していない場合、操作は 0 以外を返します。 それ以外の場合、0 が返され、次へ`Receive`または`ReceiveFrom`で実行「マーク」の前のデータの一部または全部にソケットが取得されますアプリケーションを使用する必要があります、 **SIOCATMARK**操作かどうかを判断するには。データのままです。 「緊急」(帯域外) データの前に通常のデータがある場合は、順序で受信されます。 (なお、`Receive`または`ReceiveFrom`は、同じ呼び出しで帯域外の通常のデータを混在させることはありません)。*LpArgument*パラメーターが指す、`DWORD`を`IOCtl`結果を格納します。  
  
 この関数のサブセットである`ioctl()`Berkeley ソケットで使用されています。 具体的には、コマンドと同じですがない**FIOASYNC**、中に**SIOCATMARK**はサポートされているソケット レベルのみコマンドです。  
  
##  <a name="listen"></a>  CAsyncSocket::Listen  
 接続要求をリッスンするには、このメンバー関数を呼び出します。  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>パラメーター  
 *nConnectionBacklog*  
 接続待ちのキューを拡張できる最大長。 有効な範囲は 1 から 5 には。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEADDRINUSE**使用のアドレスでリッスンしようとしました。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **WSAEINVAL**にソケットがバインドされていない`Bind`が既に接続されているか。  
  
- **WSAEISCONN**ソケットは既に接続されています。  
  
- **WSAEMFILE**ファイル記述子をこれ以上を利用できます。  
  
- **WSAENOBUFS**バッファー領域が不足しています。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP**をサポートする型の参照先のソケットではありません、`Listen`操作します。  
  
### <a name="remarks"></a>Remarks  
 接続を受け入れるように、ソケットが最初に作成で`Create`、着信接続用のバックログがで指定された`Listen`で、接続が受け入れられます、`Accept`です。 `Listen` 型は、接続をサポートするソケットにのみ適用されます**SOCK_STREAM**です。 このソケットは、「パッシブ」モードの着信接続が確認され、プロセスによって保留中の承認キューに配置された場所に配置されます。  
  
 この関数は通常、サーバー (または接続を許可する必要があるすべてのアプリケーション) によって使用、一度に 1 つ以上の接続要求がある可能性があります場合は、キューがいっぱいで、接続要求が到着すると、クライアントは、を示す値を持つエラー。**使います**です。  
  
 `Listen` 使用可能なポート (記述子) がない場合に、合理的に続行しようとしています。 キューが空にするまで接続を受け入れることです。 ポートが利用可能になった場合に以降の呼び出し`Listen`または`Accept`は、現在または最新の「バックログ」にキューを可能であれば、補充し、着信接続のリッスンを再開します。  
  
##  <a name="m_hsocket"></a>  CAsyncSocket::m_hSocket  
 含まれています、**ソケット**これによってカプセル化されたソケットのハンドル`CAsyncSocket`オブジェクト。  
  
```  
SOCKET m_hSocket;  
```  
  
##  <a name="onaccept"></a>  CAsyncSocket::OnAccept  
 呼び出すことによって保留中の接続要求を受け付けられるを待機中のソケットに通知するためにフレームワークによって呼び出される、 [Accept](#accept)メンバー関数。  
  
```  
virtual void OnAccept(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードが適用されます、`OnAccept`メンバー関数。  
  
- **0**関数が正常に実行します。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)です。  
  
##  <a name="onclose"></a>  CAsyncSocket::OnClose  
 そのプロセスによって接続されたソケットが閉じているソケットに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnClose`メンバー関数。  
  
- **0**関数が正常に実行します。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAECONNRESET**リモート側によって接続がリセットされました。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害のため、接続が中止されました。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)です。  
  
##  <a name="onconnect"></a>  CAsyncSocket::OnConnect  
 その接続の試行が完了したこと、正常にまたはエラーであるかどうかを接続しているソケットに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnConnect`メンバー関数。  
  
- **0**関数が正常に実行します。  
  
- **WSAEADDRINUSE**指定されたアドレスは既に使用されています。  
  
- **WSAEADDRNOTAVAIL**指定されたアドレスは、ローカル コンピューターから使用できません。  
  
- **WSAEAFNOSUPPORT**このソケットで指定されたファミリ内のアドレスは使用できません。  
  
- **使います**接続の試行が強制的に拒否されました。  
  
- **WSAEDESTADDRREQ**送信先アドレスが必要です。  
  
- **WSAEFAULT** 、 *lpSockAddrLen*引数が正しくありません。  
  
- **WSAEINVAL**ソケットは既にアドレスにバインドされています。  
  
- **WSAEISCONN**ソケットは既に接続されています。  
  
- **WSAEMFILE**ファイル記述子をこれ以上を利用できます。  
  
- **WSAENETUNREACH**ネットワークは、この時点でこのホストから到達できません。  
  
- **WSAENOBUFS**バッファー領域が不足しています。 ソケットを接続することはできません。  
  
- **接続保持**ソケットが接続されていません。  
  
- **切り離します**記述子が、ファイル、ソケットではありません。  
  
- **WSAETIMEDOUT**接続を確立することがなく、接続の試行がタイムアウトします。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  [CSocket](../../mfc/reference/csocket-class.md)、`OnConnect`通知関数が呼び出されることはありません。 接続は、単に呼び出す`Connect`、(正常またはエラー)、接続が完了したときにこれが返されます。 MFC 実装の詳細は、接続の通知の処理方法。  
  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>  CAsyncSocket::OnOutOfBandData  
 送信側のソケットが帯域外のデータを送信する受信側のソケットに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnOutOfBandData`メンバー関数。  
  
- **0**関数が正常に実行します。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
### <a name="remarks"></a>Remarks  
 帯域外のデータが論理的に独立したチャネルの種類の接続されたソケットの各ペアに関連付けられている**SOCK_STREAM**です。 チャネルは通常、緊急データの送信に使用されます。  
  
 MFC クラスのユーザーが、帯域外のデータをサポートしている`CAsyncSocket`使用することから推奨されていません。 簡単な方法では、このようなデータを渡すための 2 番目のソケットを作成します。 帯域外のデータの詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)です。  
  
##  <a name="onreceive"></a>  CAsyncSocket::OnReceive  
 このソケットに呼び出すことによって取得できるバッファーのデータがあることを通知するためにフレームワークによって呼び出される、`Receive`メンバー関数。  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnReceive`メンバー関数。  
  
- **0**関数が正常に実行します。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>  CAsyncSocket::OnSend  
 呼び出してデータを送信できるようになりましたことソケットに通知するためにフレームワークによって呼び出される、**送信**メンバー関数。  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用、`OnSend`メンバー関数。  
  
- **0**関数が正常に実行します。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]  
  
##  <a name="operator_eq"></a>  CAsyncSocket::operator =  
 新しい値を割り当てます、`CAsyncSocket`オブジェクト。  
  
```  
void operator=(const CAsyncSocket& rSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *rSrc*  
 既存への参照を`CAsyncSocket`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この関数を呼び出して、既存のコピー`CAsyncSocket`を別のオブジェクト`CAsyncSocket`オブジェクト。  
  
##  <a name="operator_socket"></a>  CAsyncSocket::operator ソケット  
 この演算子を使用して、取得、**ソケット**のハンドル、`CAsyncSocket`オブジェクト。  
  
```  
operator SOCKET() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合のハンドル、**ソケット**オブジェクト。 それ以外の場合、 **NULL**です。  
  
### <a name="remarks"></a>Remarks  
 Windows Api を直接呼び出すために、ハンドルを使用することができます。  
  
##  <a name="receive"></a>  CAsyncSocket::Receive  
 ソケットからデータを受信するには、このメンバー関数を呼び出します。  
  
```  
virtual int Receive(
    void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuf*  
 着信データのバッファーです。  
  
 *nBufLen*  
 長さ*lpBuf* (バイト単位)。  
  
 *nFlags*  
 呼び出しが行われた方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- **MSG_PEEK**受信データをピークします。 データは、バッファーにコピーされますが、入力キューからは削除されません。  
  
- **MSG_OOB**帯域外のデータを処理します。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`Receive`受信したバイト数を返します。 接続が閉じられた場合は、0 を返します。 それ以外の場合、値は**あふれた**返されると特定のエラー コードを呼び出すことによって取得できます[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **接続保持**ソケットが接続されていません。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されているソケットの種類ではありませんが、 **SOCK_STREAM**です。  
  
- **WSAESHUTDOWN**ソケットはシャット ダウンされました。 を呼び出すことはできません`Receive`後ソケットで`ShutDown`して呼び出されています*nHow* 0 または 2 に設定します。  
  
- **WSAEWOULDBLOCK**ソケットがマークされている非ブロッキングと`Receive`操作はブロックされます。  
  
- **WSAEMSGSIZE**データグラムが大きすぎて指定されたバッファーに収まるよう、切り捨てられました。  
  
- **WSAEINVAL**にソケットがバインドされていない`Bind`です。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>Remarks  
 この関数は、接続されているストリームとデータグラム ソケットが使用し、受信データの読み取りに使用します。  
  
 型のソケット**SOCK_STREAM**は現在、指定されたバッファーのサイズの最大使用可能な多くの情報が返されます。 帯域外のデータの行で受信ソケットが構成されている場合 (ソケット オプション**SO_OOBINLINE**) と帯域外のデータは、読み取り、のみの帯域外のデータが返されます。 アプリケーションを使用して、 **IOCtlSIOCATMARK**オプションまたは[OnOutOfBandData](#onoutofbanddata)を任意の帯域外の複数のデータが読み取られるままかどうかを判断します。  
  
 データグラム ソケットでは、データは、指定されたバッファーのサイズの最大のエンキューされたデータグラムの最初から抽出されます。 バッファーは、データグラムの最初の部分で塗りつぶさ、余分なデータが失われたデータグラムが、指定されたバッファーよりも大きい場合と`Receive`の値を返します**あふれた**に設定すると、エラー コード**WSAEMSGSIZE**です。 受信データがないかどうか、値は、ソケットに**あふれた**がエラー コードに設定して返される**WSAEWOULDBLOCK**です。 [OnReceive](#onreceive)より多くのデータが到着したときを決定するコールバック関数を使用できます。  
  
 型の場合は、ソケット**SOCK_STREAM**リモート側が、接続を正常にシャット ダウンし、`Receive`は 0 バイトを受信して直ちに完了します。 接続がリセットされた場合、`Receive`は、エラーで失敗**WSAECONNRESET**です。  
  
 `Receive` 時間ごとに 1 回だけ呼び出す必要があります[CAsyncSocket::OnReceive](#onreceive)と呼びます。  
  
### <a name="example"></a>例  
  例を参照して[CAsyncSocket::OnReceive](#onreceive)です。  
  
##  <a name="receivefrom"></a>  で  
 データグラムを受信およびの送信元アドレスを格納するには、このメンバー関数を呼び出す、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造または*rSocketAddress*です。  
  
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
 *lpBuf*  
 着信データのバッファーです。  
  
 *nBufLen*  
 長さ*lpBuf* (バイト単位)。  
  
 *rSocketAddress*  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rSocketPort*  
 参照、 **UINT**ポートを格納します。  
  
 *lpSockAddr*  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)関数が戻るとき、送信元アドレスを保持する構造。  
  
 *lpSockAddrLen*  
 送信元アドレスの長さへのポインター *lpSockAddr* (バイト単位)。  
  
 *nFlags*  
 呼び出しが行われた方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- **MSG_PEEK**受信データをピークします。 データは、バッファーにコピーされますが、入力キューからは削除されません。  
  
- **MSG_OOB**帯域外のデータを処理します。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`ReceiveFrom`受信したバイト数を返します。 接続が閉じられた場合は、0 を返します。 それ以外の場合、値は**あふれた**返されると特定のエラー コードを呼び出すことによって取得できます`GetLastError`です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEFAULT** 、 *lpSockAddrLen*引数が無効でした: *lpSockAddr*バッファーが小さすぎて、ピアのアドレスを格納します。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **WSAEINVAL**にソケットがバインドされていない`Bind`です。  
  
- **接続保持**ソケットが接続されていない ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されているソケットの種類ではありませんが、 **SOCK_STREAM**です。  
  
- **WSAESHUTDOWN**ソケットはシャット ダウンされました。 を呼び出すことはできません`ReceiveFrom`後ソケットで`ShutDown`して呼び出されています*nHow* 0 または 2 に設定します。  
  
- **WSAEWOULDBLOCK**ソケットがマークされている非ブロッキングと`ReceiveFrom`操作はブロックされます。  
  
- **WSAEMSGSIZE**データグラムが大きすぎて指定されたバッファーに収まるよう、切り捨てられました。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>Remarks  
 この関数は、(接続されている可能性があります) のソケットの受信データの読み取りし、データの送信元アドレスのキャプチャに使用されます。  
  
 IPv6 アドレスを処理する[CAsyncSocket::ReceiveFromEx](#receivefromex)です。  
  
 型のソケット**SOCK_STREAM**は現在、指定されたバッファーのサイズの最大使用可能な多くの情報が返されます。 帯域外のデータの行で受信ソケットが構成されている場合 (ソケット オプション**SO_OOBINLINE**) と帯域外のデータは、読み取り、のみの帯域外のデータが返されます。 アプリケーションを使用して、 **IOCtlSIOCATMARK**オプションまたは`OnOutOfBandData`を任意の帯域外の複数のデータが読み取られるままかどうかを判断します。 *LpSockAddr*と*lpSockAddrLen*のパラメーターは無視**SOCK_STREAM** sockets です。  
  
 データグラム ソケットでは、データは、指定されたバッファーのサイズの最大のエンキューされたデータグラムの最初から抽出されます。 バッファーは、メッセージの前半で塗りつぶさ、余分なデータが失われたデータグラムが、指定されたバッファーよりも大きい場合と`ReceiveFrom`の値を返します**あふれた**に設定すると、エラー コード**WSAEMSGSIZE**です。  
  
 場合*lpSockAddr* 0 以外の場合は、種類がソケット**SOCK_DGRAM**、対応する、データを送信したソケットのネットワーク アドレスをコピー [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体。 値を指す*lpSockAddrLen*この構造体のサイズに初期化され、格納されたアドレスの実際のサイズを示す戻り値に変更されています。 受信データが使用できない場合に、ソケット、`ReceiveFrom`ソケットでない限り、到着するデータの呼び出しが待機する非ブロッキングです。 この場合の値で**あふれた**がエラー コードに設定して返される**WSAEWOULDBLOCK**です。 `OnReceive`より多くのデータが到着したときを決定するコールバックを使用できます。  
  
 型の場合は、ソケット**SOCK_STREAM**リモート側が、接続を正常にシャット ダウンし、`ReceiveFrom`は 0 バイトを受信して直ちに完了します。  
  
##  <a name="receivefromex"></a>  CAsyncSocket::ReceiveFromEx  
 データグラムを受信およびの送信元アドレスを格納するには、このメンバー関数を呼び出す、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造または*rSocketAddress* (IPv6 アドレスのハンドル)。  
  
```  
int ReceiveFromEx(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuf*  
 着信データのバッファーです。  
  
 *nBufLen*  
 長さ*lpBuf* (バイト単位)。  
  
 *rSocketAddress*  
 参照、`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rSocketPort*  
 参照、 **UINT**ポートを格納します。  
  
 *nFlags*  
 呼び出しが行われた方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- **MSG_PEEK**受信データをピークします。 データは、バッファーにコピーされますが、入力キューからは削除されません。  
  
- **MSG_OOB**帯域外のデータを処理します。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`ReceiveFromEx`受信したバイト数を返します。 接続が閉じられた場合は、0 を返します。 それ以外の場合、値は**あふれた**返されると特定のエラー コードを呼び出すことによって取得できます`GetLastError`です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEFAULT** 、 *lpSockAddrLen*引数が無効でした: *lpSockAddr*バッファーが小さすぎて、ピアのアドレスを格納します。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **WSAEINVAL**にソケットがバインドされていない`Bind`です。  
  
- **接続保持**ソケットが接続されていない ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されているソケットの種類ではありませんが、 **SOCK_STREAM**です。  
  
- **WSAESHUTDOWN**ソケットはシャット ダウンされました。 を呼び出すことはできません`ReceiveFromEx`後ソケットで`ShutDown`して呼び出されています*nHow* 0 または 2 に設定します。  
  
- **WSAEWOULDBLOCK**ソケットがマークされている非ブロッキングと`ReceiveFromEx`操作はブロックされます。  
  
- **WSAEMSGSIZE**データグラムが大きすぎて指定されたバッファーに収まるよう、切り捨てられました。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>Remarks  
 この関数は、(接続されている可能性があります) のソケットの受信データの読み取りし、データの送信元アドレスのキャプチャに使用されます。  
  
 この関数は、同じ[で](#receivefrom)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
 型のソケット**SOCK_STREAM**は現在、指定されたバッファーのサイズの最大使用可能な多くの情報が返されます。 帯域外のデータの行で受信ソケットが構成されている場合 (ソケット オプション**SO_OOBINLINE**) と帯域外のデータは、読み取り、のみの帯域外のデータが返されます。 アプリケーションを使用して、 **IOCtlSIOCATMARK**オプションまたは`OnOutOfBandData`を任意の帯域外の複数のデータが読み取られるままかどうかを判断します。 *LpSockAddr*と*lpSockAddrLen*のパラメーターは無視**SOCK_STREAM** sockets です。  
  
 データグラム ソケットでは、データは、指定されたバッファーのサイズの最大のエンキューされたデータグラムの最初から抽出されます。 バッファーは、メッセージの前半で塗りつぶさ、余分なデータが失われたデータグラムが、指定されたバッファーよりも大きい場合と`ReceiveFromEx`の値を返します**あふれた**に設定すると、エラー コード**WSAEMSGSIZE**です。  
  
 場合*lpSockAddr* 0 以外の場合は、種類がソケット**SOCK_DGRAM**、対応する、データを送信したソケットのネットワーク アドレスをコピー [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体。 値を指す*lpSockAddrLen*この構造体のサイズに初期化され、格納されたアドレスの実際のサイズを示す戻り値に変更されています。 受信データが使用できない場合に、ソケット、`ReceiveFromEx`ソケットでない限り、到着するデータの呼び出しが待機する非ブロッキングです。 この場合の値で**あふれた**がエラー コードに設定して返される**WSAEWOULDBLOCK**です。 `OnReceive`より多くのデータが到着したときを決定するコールバックを使用できます。  
  
 型の場合は、ソケット**SOCK_STREAM**リモート側が、接続を正常にシャット ダウンし、`ReceiveFromEx`は 0 バイトを受信して直ちに完了します。  
  
##  <a name="send"></a>  CAsyncSocket::Send  
 接続されたソケット上にデータを送信するには、このメンバー関数を呼び出します。  
  
```  
virtual int Send(
    const void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuf*  
 転送するデータを格納しているバッファー。  
  
 *nBufLen*  
 内のデータの長さ*lpBuf* (バイト単位)。  
  
 *nFlags*  
 呼び出しが行われた方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- **MSG_DONTROUTE**データは、ルーティングされる可能性がありますすべきを指定します。 Windows ソケットのサプライヤーは、このフラグを無視を選択できます。  
  
- **MSG_OOB**帯域外のデータを送信 ( **SOCK_STREAM**のみ)。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`Send`送信されたバイト数の合計を返します。 (これを指定できますで示される数よりも少ない*nBufLen*)。それ以外の場合、値は**あふれた**返されると特定のエラー コードを呼び出すことによって取得できます[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEACCES**要求されたアドレスは、ブロードキャスト アドレスですが、適切なフラグが設定されませんでした。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **WSAEFAULT** 、 *lpBuf*引数は、ユーザー アドレス空間の有効な部分に含まれない。  
  
- **いるとき**Windows Sockets 実装で削除されたため、接続をリセットする必要があります。  
  
- **WSAENOBUFS** 「Windows Sockets 実装、バッファー、デッドロックが報告されます。  
  
- **接続保持**ソケットが接続されていません。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されているソケットの種類ではありませんが、 **SOCK_STREAM**です。  
  
- **WSAESHUTDOWN**ソケットはシャット ダウンされました。 を呼び出すことはできません`Send`後ソケットで`ShutDown`して呼び出されています*nHow* 1 または 2 に設定します。  
  
- **WSAEWOULDBLOCK**ソケットがマークされている非ブロッキングされ、要求された操作を停止します。  
  
- **WSAEMSGSIZE** 、ソケットの型が**SOCK_DGRAM**データグラムが Windows ソケットの実装でサポートされている最大値よりも大きいとします。  
  
- **WSAEINVAL**にソケットがバインドされていない`Bind`です。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>Remarks  
 `Send` 接続されているストリームまたはデータグラム ソケットで送信したデータの書き込みに使用します。 データグラム ソケットの場合は注意が必要で、指定した基になるサブネットの IP パケットの最大サイズを超えることはできません、**とき**内の要素、 [WSADATA](../../mfc/reference/wsadata-structure.md)によって返される構造体`AfxSocketInit`です。 データが長すぎて、基になるプロトコル エラー場合**WSAEMSGSIZE**を介して返されます`GetLastError`データは送信されません。  
  
 なお、データグラムのソケットが正常に完了、`Send`データが正常に送信されたことを示していません。  
  
 `CAsyncSocket`型のオブジェクト**SOCK_STREAM**、書き込まれたバイト数は 1 ~ ローカルおよび外部の両方のホスト上のバッファーの可用性に応じて、要求された長さにすることができます。  
  
### <a name="example"></a>例  
  例を参照して[CAsyncSocket::OnSend](#onsend)です。  
  
##  <a name="sendto"></a>  で  
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
 *lpBuf*  
 転送するデータを格納しているバッファー。  
  
 *nBufLen*  
 内のデータの長さ*lpBuf* (バイト単位)。  
  
 *nHostPort*  
 ソケット アプリケーションを識別するポートです。  
  
 *lpszHostAddress*  
 このオブジェクトが接続されたソケットのネットワーク アドレス:「専用、」や「128.56.22.8」などのピリオドで区切られた番号などのコンピューター名。  
  
 *nFlags*  
 呼び出しが行われた方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- **MSG_DONTROUTE**データは、ルーティングされる可能性がありますすべきを指定します。 Windows ソケットのサプライヤーは、このフラグを無視を選択できます。  
  
- **MSG_OOB**帯域外のデータを送信 ( **SOCK_STREAM**のみ)。  
  
 *lpSockAddr*  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)ターゲット ソケットのアドレスを格納する構造体。  
  
 *nSockAddrLen*  
 指定されたアドレスの長さ*lpSockAddr* (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`SendTo`送信されたバイト数の合計を返します。 (これを指定できますで示される数よりも少ない*nBufLen*)。それ以外の場合、値は**あふれた**返されると特定のエラー コードを呼び出すことによって取得できます[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEACCES**要求されたアドレスは、ブロードキャスト アドレスですが、適切なフラグが設定されませんでした。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **WSAEFAULT** 、 *lpBuf*または*lpSockAddr*パラメーターは、ユーザー アドレス空間の一部ではない、または*lpSockAddr*引数が (小さいサイズよりも小さすぎます。[SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体)。  
  
- **WSAEINVAL**ホスト名が無効です。  
  
- **いるとき**Windows Sockets 実装で削除されたため、接続をリセットする必要があります。  
  
- **WSAENOBUFS** 「Windows Sockets 実装、バッファー、デッドロックが報告されます。  
  
- **接続保持**ソケットが接続されていない ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されているソケットの種類ではありませんが、 **SOCK_STREAM**です。  
  
- **WSAESHUTDOWN**ソケットはシャット ダウンされました。 を呼び出すことはできません`SendTo`後ソケットで`ShutDown`して呼び出されています*nHow* 1 または 2 に設定します。  
  
- **WSAEWOULDBLOCK**ソケットがマークされている非ブロッキングされ、要求された操作を停止します。  
  
- **WSAEMSGSIZE** 、ソケットの型が**SOCK_DGRAM**データグラムが Windows ソケットの実装でサポートされている最大値よりも大きいとします。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
- **WSAEADDRNOTAVAIL**指定されたアドレスは、ローカル コンピューターから使用できません。  
  
- **WSAEAFNOSUPPORT**このソケットで指定されたファミリ内のアドレスは使用できません。  
  
- **WSAEDESTADDRREQ**送信先アドレスが必要です。  
  
- **WSAENETUNREACH**ネットワークは、この時点でこのホストから到達できません。  
  
### <a name="remarks"></a>Remarks  
 `SendTo` データグラム ソケットまたはストリーム ソケットで使用され、ソケットで送信したデータを書き込むために使用します。 データグラム ソケットの場合は注意が必要で、指定した基になるサブネットの IP パケットの最大サイズを超えることはできません、**とき**内の要素、 [WSADATA](../../mfc/reference/wsadata-structure.md)構造記入[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)です。 場合は、データが長すぎて、基になるプロトコル エラー **WSAEMSGSIZE**が返されたデータは送信されません。  
  
 なおが正常に完了、`SendTo`データが正常に送信されたことを示していません。  
  
 `SendTo` のみ使用されて、 **SOCK_DGRAM**ソケットで識別される特定のソケットにデータグラムを送信する、 *lpSockAddr*パラメーター。  
  
 ブロードキャストを送信する (上、 **SOCK_DGRAM**のみ)、内のアドレス、 *lpSockAddr*パラメーターは、特別な IP アドレスを使用して作成する必要があります**INADDR_BROADCAST** (定義されています。Windows ソケットのヘッダーの WINSOCK をファイルです。H) と共に目的のポート番号。 またはの場合、 *lpszHostAddress*パラメーターが**NULL**ソケットはブロードキャスト用に構成されています。 ブロードキャスト データグラムを断片化が発生することが、サイズを超えたことをお勧めはできません (ヘッダーを除く)、データグラムのデータ部分が 512 バイトを超えていないことを意味します。  
  
 IPv6 アドレスを処理する[CAsyncSocket::SendToEx](#sendtoex)です。  
  
##  <a name="sendtoex"></a>  CAsyncSocket::SendToEx  
 特定の宛先 (IPv6 アドレスを処理する) にデータを送信するには、このメンバー関数を呼び出します。  
  
```  
int SendToEx(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuf*  
 転送するデータを格納しているバッファー。  
  
 *nBufLen*  
 内のデータの長さ*lpBuf* (バイト単位)。  
  
 *nHostPort*  
 ソケット アプリケーションを識別するポートです。  
  
 *lpszHostAddress*  
 このオブジェクトが接続されたソケットのネットワーク アドレス:「専用、」や「128.56.22.8」などのピリオドで区切られた番号などのコンピューター名。  
  
 *nFlags*  
 呼び出しが行われた方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- **MSG_DONTROUTE**データは、ルーティングされる可能性がありますすべきを指定します。 Windows ソケットのサプライヤーは、このフラグを無視を選択できます。  
  
- **MSG_OOB**帯域外のデータを送信 ( **SOCK_STREAM**のみ)。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しなかった場合`SendToEx`送信されたバイト数の合計を返します。 (これを指定できますで示される数よりも少ない*nBufLen*)。それ以外の場合、値は**あふれた**返されると特定のエラー コードを呼び出すことによって取得できます[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEACCES**要求されたアドレスは、ブロードキャスト アドレスですが、適切なフラグが設定されませんでした。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **WSAEFAULT** 、 *lpBuf*または*lpSockAddr*パラメーターは、ユーザー アドレス空間の一部ではない、または*lpSockAddr*引数が (小さいサイズよりも小さすぎます。[SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体)。  
  
- **WSAEINVAL**ホスト名が無効です。  
  
- **いるとき**Windows Sockets 実装で削除されたため、接続をリセットする必要があります。  
  
- **WSAENOBUFS** 「Windows Sockets 実装、バッファー、デッドロックが報告されます。  
  
- **接続保持**ソケットが接続されていない ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
- **WSAEOPNOTSUPP MSG_OOB**が指定されているソケットの種類ではありませんが、 **SOCK_STREAM**です。  
  
- **WSAESHUTDOWN**ソケットはシャット ダウンされました。 を呼び出すことはできません`SendToEx`後ソケットで`ShutDown`して呼び出されています*nHow* 1 または 2 に設定します。  
  
- **WSAEWOULDBLOCK**ソケットがマークされている非ブロッキングされ、要求された操作を停止します。  
  
- **WSAEMSGSIZE** 、ソケットの型が**SOCK_DGRAM**データグラムが Windows ソケットの実装でサポートされている最大値よりも大きいとします。  
  
- **WSAECONNABORTED**タイムアウトまたはその他の障害によって仮想回線が中止されました。  
  
- **WSAECONNRESET**リモート側によって仮想回線がリセットされました。  
  
- **WSAEADDRNOTAVAIL**指定されたアドレスは、ローカル コンピューターから使用できません。  
  
- **WSAEAFNOSUPPORT**このソケットで指定されたファミリ内のアドレスは使用できません。  
  
- **WSAEDESTADDRREQ**送信先アドレスが必要です。  
  
- **WSAENETUNREACH**ネットワークは、この時点でこのホストから到達できません。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、同じ[で](#sendto)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
 `SendToEx` データグラム ソケットまたはストリーム ソケットで使用され、ソケットで送信したデータを書き込むために使用します。 データグラム ソケットの場合は注意が必要で、指定した基になるサブネットの IP パケットの最大サイズを超えることはできません、**とき**内の要素、 [WSADATA](../../mfc/reference/wsadata-structure.md)構造記入[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)です。 場合は、データが長すぎて、基になるプロトコル エラー **WSAEMSGSIZE**が返されたデータは送信されません。  
  
 なおが正常に完了、`SendToEx`データが正常に送信されたことを示していません。  
  
 `SendToEx` のみ使用されて、 **SOCK_DGRAM**ソケットで識別される特定のソケットにデータグラムを送信する、 *lpSockAddr*パラメーター。  
  
 ブロードキャストを送信する (上、 **SOCK_DGRAM**のみ)、内のアドレス、 *lpSockAddr*パラメーターは、特別な IP アドレスを使用して作成する必要があります**INADDR_BROADCAST** (定義されています。Windows ソケットのヘッダーの WINSOCK をファイルです。H) と共に目的のポート番号。 またはの場合、 *lpszHostAddress*パラメーターが**NULL**ソケットはブロードキャスト用に構成されています。 ブロードキャスト データグラムを断片化が発生することが、サイズを超えたことをお勧めはできません (ヘッダーを除く)、データグラムのデータ部分が 512 バイトを超えていないことを意味します。  
  
##  <a name="setsockopt"></a>  CAsyncSocket::SetSockOpt  
 ソケット オプションを設定するには、このメンバー関数を呼び出します。  
  
```  
BOOL SetSockOpt(
    int nOptionName,  
    const void* lpOptionValue,  
    int nOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>パラメーター  
 *nOptionName*  
 値を設定するソケット オプション。  
  
 *関連付け*  
 要求されたオプションの値を指定するバッファーへのポインター。  
  
 *nOptionLen*  
 サイズ、*は*バッファーのバイト単位です。  
  
 *nLevel*  
 オプションが定義されているレベル唯一サポートされているレベルは、**取得**と**取得できる**です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEFAULT** *は*プロセスのアドレス空間の有効な部分ではありません。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **WSAEINVAL** *nLevel*が有効でないかの情報は、*は*が無効です。  
  
- **いるとき**接続がタイムアウト時に**接続**が設定されています。  
  
- **WSAENOPROTOOPT**不明、またはサポートされていないオプションです。 具体的には、 **:so_broadcast**型のソケットでサポートされていない**SOCK_STREAM**、中に**SO_DONTLINGER**、**接続**、 **SO_LINGER**、および**SO_OOBINLINE**型のソケットでサポートされていない**SOCK_DGRAM**です。  
  
- **接続保持**接続されたときにリセット**接続**設定されています。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 `SetSockOpt` いずれかの状態で、任意の型のソケットに関連付けられているソケット オプションの現在の値を設定します。 オプションは、複数のプロトコル レベルに存在できる、この仕様には最上位の「ソケット」レベルに存在するためのオプションのみを定義します。 オプションでは、ブロードキャスト メッセージがソケットに送信することができます、かどうかにして、通常のデータ ストリームで優先データが受信したかどうかなどのソケット操作に影響します。  
  
 2 つの種類のソケット オプションがあります: ブール型のオプションを有効にするか、機能や動作を無効にして、整数値または構造体を必要とするオプションです。 ブール型のオプションを有効にする*は*0 以外の整数を指します。 オプションを無効に*は*0 に等しい整数を指します。 *nOptionLen*を等しく必要のある**sizeof(BOOL)** のブール型のオプションです。 その他のオプション*は*整数または、オプションの目的の値を格納する構造体を指すおよび*nOptionLen*整数または構造体の長さです。  
  
 **SO_LINGER**ときに実行されるアクション未送信のデータがキューに置かれたソケットでのコントロールと`Close`関数は、ソケットを閉じるために呼び出されます。  
  
 既定では、ソケットをバインドすることはできません (を参照してください[バインド](#bind)) は既に使用されているローカル アドレスにします。 場合によっては、ただし、ある可能性がありますをこの方法でアドレスを「再利用」することをお勧めします。 すべての接続には、ローカルおよびリモート アドレスの組み合わせによって一意に識別、ために、2 つのソケットがリモートのアドレスが異なる限り、同じローカル アドレスにバインドされていることに問題はありません。  
  
 Windows ソケットの実装に通知すること、 `Bind` 、必要なアドレスが既に別のソケットが使用されているために、ソケットに対する呼び出しは禁止されませんが、アプリケーションを設定する必要があります、 **SO_REUSEADDR**ソケット オプション発行する前にソケットに関して、`Bind`呼び出します。 ときにのみ、オプションが解釈されることに注意してください、`Bind`を呼び出す: 必要はありませんので (ただし、影響を与えません) には、既存のアドレスにバインドされているソケット オプションを設定して、設定または後にオプションをリセットして、`Bind`呼び出しではこのまたはその他のソケットに対する影響はありません。  
  
 アプリケーションが Windows ソケットの実装がオンでの伝送制御プロトコル (TCP) 接続の"keep alive"パケットの使用を有効にすることを要求することができます、**接続**ソケット オプション。 Windows Sockets 実装はキープア ライブの使用をサポートする必要がありません: 場合は、正確なセマンティクスの実装に固有がならなければのセクション 4.2.3.6 に準拠している必要があります:"Requirements for Internet Hosts-通信レイヤー"。 接続がエラー コード「キープア」の結果として削除された場合**いるとき**、ソケットで進行中のすべての呼び出しに返される、後続の呼び出しは失敗し、**接続保持**です。  
  
 **低下**オプション Nagle アルゴリズムを無効にします。 Nagle アルゴリズムを使用して、フルサイズのパケットを送信するまで、未確認の送信データをバッファー処理して、ホストによって送信された小さなパケットの数が削減されます。 ただし、一部のアプリケーションのこのアルゴリズム、パフォーマンスが低下、および**低下**を無効にするために使用できます。 アプリケーションの作成者が設定されていない**低下**そうの影響はよく理解されていると、必要なされてからの設定しない限り、**低下**ネットワーク パフォーマンスに重大な悪影響を持つことができます. **低下**は、唯一サポート レベルを使用するソケット オプション**取得できる**; レベルを使用するその他のすべてのオプション**取得**です。  
  
 Windows ソケット装置の実装によっては、場合にデバッグ情報を出力、 **SO_DEBUG**オプションは、アプリケーションによって設定します。  
  
 次のオプションはサポートされて`SetSockOpt`です。 型によってアドレス指定されるデータの種類を識別する*は*します。  
  
|[値]|型|説明|  
|-----------|----------|-------------|  
|**:SO_BROADCAST**|**BOOL**|ソケットのブロードキャスト メッセージの送信を許可します。|  
|**SO_DEBUG**|**BOOL**|デバッグ情報を記録します。|  
|**SO_DONTLINGER**|**BOOL**|ブロックしない**閉じる**未送信のデータを送信するを待っています。 設定は、このオプションを設定**SO_LINGER**で**こと**を 0 に設定します。|  
|**SO_DONTROUTE**|**BOOL**|ルーティングありません: インターフェイスに直接送信します。|  
|**接続**|**BOOL**|Keep-alive を送信します。|  
|**SO_LINGER**|**LINGER 構造体**|Linger**閉じる**未送信のデータが存在する場合。|  
|**SO_OOBINLINE**|**BOOL**|通常のデータ ストリームでは、帯域外のデータを受信します。|  
|**SO_RCVBUF**|**int**|受信用のバッファー サイズを指定します。|  
|**SO_REUSEADDR**|**BOOL**|既に使用されているアドレスにバインドするソケットを使用できます。 (を参照してください[バインド](#bind))。|  
|**SO_SNDBUF**|**int**|送信用のバッファー サイズを指定します。|  
|**低下**|**BOOL**|送信結合用の Nagle アルゴリズムを無効にします。|  
  
 Berkeley ソフトウェア配布 (BSD) オプションはサポートされていません`SetSockOpt`は。  
  
|[値]|型|説明|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|ソケットをリッスンします。|  
|**SO_ERROR**|**int**|エラー状態を取得し、オフにします。|  
|**SO_RCVLOWAT**|**int**|低水位マークが表示されます。|  
|**SO_RCVTIMEO**|**int**|受信タイムアウト|  
|**SO_SNDLOWAT**|**int**|低水位マークを送信します。|  
|**SO_SNDTIMEO**|**int**|送信タイムアウト。|  
|**SO_TYPE**|**int**|ソケットの種類です。|  
|**なる**||IP ヘッダーには、オプションのフィールドを設定します。|  
  
##  <a name="shutdown"></a>  CAsyncSocket::ShutDown  
 呼び出しを無効にするには、このメンバー関数は、次の送信、受信すると、またはその両方、ソケットにします。  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>パラメーター  
 *nHow*  
 操作の種類を示すフラグが不要になったできる、次の列挙値を使用します。  
  
- **受信 = 0**  
  
- **送信 1 を =**  
  
- **両方 = 2**  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合[GetLastError](#getlasterror)です。 次のエラーは、このメンバー関数に適用されます。  
  
- **成功**成功[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- **WSAENETDOWN** 「Windows Sockets 実装は、ネットワーク サブシステムが失敗したことが検出されました。  
  
- **WSAEINVAL** *nHow*が無効です。  
  
- **WSAEINPROGRESS**ブロックしている Windows ソケット操作が進行中です。  
  
- **接続保持**ソケットが接続されていない ( **SOCK_STREAM**のみ)。  
  
- **切り離します**記述子がソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 `ShutDown` 受信と送信、またはその両方を無効にするすべての種類のソケットで使用されます。 場合*nHow*が 0 の場合での受信ソケットは使用できません。 下位のプロトコル層への影響はありません。  
  
 伝送制御プロトコル (TCP) では、TCP ウィンドウが変更されていないと、受信データになります (ただし、応答ではありません) ウィンドウがなくなるまでに受け入れられます。 ユーザー データグラム プロトコル (UDP) では、受信したデータグラムが受け入れてし、キューに置かれました。 いかなる場合で、ICMP のエラー パケットが生成されます。 場合*nHow* 1 の場合は、その後送信は許可されません。 TCP ソケットの場合、FIN は送信されます。 設定*nHow* 2 に両方の送信が無効になり、前述のように受信します。  
  
 注意してください`ShutDown`はいない閉じるソケット、およびソケットにアタッチされているリソースは解放されませんまで`Close`と呼びます。 アプリケーションはシャット ダウン後に、ソケットを再利用することに依存する必要があります。 具体的には、Windows Sockets 実装は、の使用をサポートする必要はありません`Connect`このようなソケットでします。  
  
### <a name="example"></a>例  
  例を参照して[CAsyncSocket::OnReceive](#onreceive)です。  
  
##  <a name="socket"></a>  CASyncSocket::Socket  
 ソケット ハンドルを割り当てます。  
  
```  
BOOL Socket(
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    int nProtocolType = 0,  
    int nAddressFormat = PF_INET);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSocketType*  
 指定`SOCK_STREAM`または`SOCK_DGRAM`です。  
  
 *lEvent*  
 アプリケーションが必要とするネットワーク イベントの組み合わせを指定するビットマスク。  
  
- `FD_READ`: 読み取り用の準備完了の通知を受信するとしてください。  
  
- `FD_WRITE`: 書き込みのための準備完了の通知を受信するとしてください。  
  
- `FD_OOB`: の帯域外のデータの到着の通知を受信するとしてください。  
  
- `FD_ACCEPT`: 着信接続の通知を受信するとしてください。  
  
- `FD_CONNECT`: 完全な接続の通知を受信するとしてください。  
  
- `FD_CLOSE`: ソケットの終了の通知を受信するとしてください。  
  
 *nProtocolType*  
 指定されたアドレス ファミリに特有のソケットで使用するプロトコルです。  
  
 *nAddressFormat*  
 アドレス ファミリの指定。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は、`TRUE` を返します。それ以外の場合は、`FALSE` を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ソケット ハンドルを割り当てます。 呼び出しません[CAsyncSocket::Bind](#bind)呼び出す必要があるために、指定したアドレスにソケットをバインドする`Bind`以降を指定したアドレスにソケットをバインドします。 使用することができます[CAsyncSocket::SetSockOpt](#setsockopt)バインドされている前に、ソケット オプションを設定します。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSocket クラス](../../mfc/reference/csocket-class.md)   
 [CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
