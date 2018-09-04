---
title: CAsyncSocket クラス |Microsoft Docs
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
ms.openlocfilehash: c74bc6a134ea31f3184912192ccbcb3908e64cd3
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221526"
---
# <a name="casyncsocket-class"></a>CAsyncSocket クラス
Windows ソケットを表します: ネットワークの通信エンドポイントです。  
  
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
|[CAsyncSocket::Accept](#accept)|ソケット上の接続を受け入れます。|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|ソケットのイベント通知を要求します。|  
|[CAsyncSocket::Attach](#attach)|ソケットのハンドルをアタッチ、`CAsyncSocket`オブジェクト。|  
|[CAsyncSocket::Bind](#bind)|ローカル アドレスをソケットに関連付けます。|  
|[CAsyncSocket::Close](#close)|ソケットを閉じます。|  
|[不要なため](#connect)|ピアのソケットへの接続を確立します。|  
|[CAsyncSocket::Create](#create)|ソケットが作成されます。|  
|[CAsyncSocket::Detach](#detach)|ソケット ハンドルをデタッチする`CAsyncSocket`オブジェクト。|  
|[CAsyncSocket::FromHandle](#fromhandle)|ポインターを返します、`CAsyncSocket`オブジェクト、ソケット ハンドルを指定します。|  
|[CAsyncSocket::GetLastError](#getlasterror)|最後の操作に失敗したは、エラー状態を取得します。|  
|[で](#getpeername)|ソケットが接続されているピア ソケットのアドレスを取得します。|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|ピア ソケット、ソケットが接続されている (ハンドルの IPv6 アドレス) のアドレスを取得します。|  
|[で](#getsockname)|ソケットのローカル名を取得します。|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|ソケット (IPv6 アドレスのハンドル) のローカル名を取得します。|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|ソケット オプションを取得します。|  
|[CAsyncSocket::IOCtl](#ioctl)|ソケットのモードを制御します。|  
|[CAsyncSocket::Listen](#listen)|受信接続要求をリッスンするソケットを確立します。|  
|[CAsyncSocket::Receive](#receive)|ソケットからデータを受信します。|  
|[で](#receivefrom)|データグラムを受信し、送信元アドレスを格納します。|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|データグラムを受信し、送信元アドレス (IPv6 アドレスを処理する) を格納します。|  
|[CAsyncSocket::Send](#send)|接続されたソケットにデータを送信します。|  
|[で](#sendto)|特定の宛先にデータを送信します。|  
|[CAsyncSocket::SendToEx](#sendtoex)|特定の宛先 (IPv6 アドレスを処理する) にデータを送信します。|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|ソケット オプションを設定します。|  
|[CAsyncSocket::ShutDown](#shutdown)|無効にします`Send`や`Receive`ソケットで呼び出します。|  
|[CASyncSocket::Socket](#socket)|ソケットのハンドルを割り当てます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|呼び出すことによって保留中の接続要求を受け付けられるを待機中のソケットに通知`Accept`します。|  
|[CAsyncSocket::OnClose](#onclose)|ソケットが接続されているソケットが閉じられてに通知します。|  
|[CAsyncSocket::OnConnect](#onconnect)|接続の試行が完了した、かどうかが正常にまたはエラーで接続のソケットに通知します。|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|緊急のメッセージでは、通常は、ソケットで読み取られる帯域外のデータが含まれる受信ソケットに通知します。|  
|[CAsyncSocket::OnReceive](#onreceive)|呼び出すことによって取得するデータがあることを待機中のソケットに通知`Receive`します。|  
|[CAsyncSocket::OnSend](#onsend)|ソケットに通知を呼び出してデータを送信できる`Send`します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|新しい値を割り当てます、`CAsyncSocket`オブジェクト。|  
|[CAsyncSocket::operator ソケット](#operator_socket)|この演算子を使用してのソケット ハンドルを取得する、`CAsyncSocket`オブジェクト。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|これに接続されたソケット ハンドル`CAsyncSocket`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 クラス`CAsyncSocket`MFC と組み合わせて Windows ソケットを使用するプログラマのオブジェクト指向の抽象化を提供する、Windows ソケット Functions API をカプセル化します。  
  
 このクラスは、ネットワーク通信を理解していることを前提に基づいています。 ブロック、バイト順序の違いを処理して、Unicode とマルチバイト文字の間の変換セット (MBCS) 文字列。 使いやすいインターフェイスがこれらの問題を管理する場合は、クラスを参照してください。 [CSocket](../../mfc/reference/csocket-class.md)します。  
  
 使用する、 `CAsyncSocket` 、コンス トラクターを呼び出すオブジェクトを呼び出して、[作成](#create)基になるソケット ハンドルを作成する関数 (型`SOCKET`)、ソケットが受け入れられた場合は除きます。 サーバー ソケットの呼び出しの[リッスン](#listen)メンバー関数、およびクライアント ソケットの呼び出しに対して、 [Connect](#connect)メンバー関数。 サーバー ソケットを呼び出す必要があります、 [Accept](#accept)接続要求を受け取った関数。 使用して、残りの`CAsyncSocket`ソケットの間の通信を実行する関数。 完了すると、破棄、`CAsyncSocket`オブジェクト ヒープ上で作成された場合は、デストラクターが自動的に呼び出します、[閉じる](#close)関数。 ソケットのデータ型が、情報の記事で説明されている[Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)します。  
  
> [!NOTE]
>  静的にリンクされた MFC アプリケーションでセカンダリ スレッドで MFC ソケットを使用する場合を呼び出す必要があります`AfxSocketInit`ソケット ライブラリを初期化するためにソケットを使用する各スレッドにします。 既定では、`AfxSocketInit`は、プライマリ スレッドでのみ呼び出されます。  
  
 詳細については、次を参照してください。 [Windows ソケット: を使用してクラス CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md)おり、関連する記事、だけでなく[Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxsock.h  
  
##  <a name="accept"></a>  CAsyncSocket::Accept  
 ソケットで接続を受け入れる場合は、このメンバー関数を呼び出します。  
  
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
 ポインターを[SOCKADDR](../../mfc/reference/sockaddr-structure.md)既知のネットワークの 接続のアドレスを受け取る構造体がソケットします。 正確な形式、 *lpSockAddr*引数は、ソケットが作成されたときに確立されているアドレス ファミリによって決定されます。 場合*lpSockAddr*や*lpSockAddrLen*に NULL 値が受け入れられたソケットのリモート アドレスに関する情報は返されません。  
  
 *lpSockAddrLen*  
 内のアドレスの長さへのポインター *lpSockAddr* (バイト単位)。 *LpSockAddrLen*値結果パラメーター: によって示される領域の量を最初に格納する必要があります*lpSockAddr*; 返された場合は返されたアドレスの実際の長さ (単位: バイト) が含まれます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEFAULT、 *lpSockAddrLen*引数が小さすぎる (のサイズよりも小さいか、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造)。  
  
- Windows ソケットのブロックを呼び出す WSAEINPROGRESS A が進行中です。  
  
- WSAEINVAL`Listen`が呼び出される前にそのまま使用します。  
  
- WSAEMFILE キューが空を受け入れるように入ったときにし、使用可能な記述子はありません。  
  
- WSAENOBUFS いいえバッファー領域は使用できます。  
  
- 切り離します記述子は、ソケットではありません。  
  
- WSAEOPNOTSUPP 参照先のソケットは、接続指向のサービスをサポートする型ではありません。  
  
- ソケットがマークされている WSAEWOULDBLOCK 非ブロッキング許可される接続がないとします。  
  
### <a name="remarks"></a>Remarks  
 このルーチンは、接続待ちのキューの最初の接続を抽出し、このソケットと同じプロパティを持つ新しいソケットを作成にアタッチします*rConnectedSocket*します。 キューに保留中の接続がない場合`Accept`は 0 を返しますと`GetLastError`エラーが返されます。 受け入れられたソケット ( *rConnectedSocket)* より多くの接続を受け入れるには使用できません。 オープンでリッスンしている、元のソケットが残ります。  
  
 引数*lpSockAddr* 、ソケット接続のアドレスが入力されます結果パラメーターは、通信レイヤーに既知として。 `Accept` SOCK_STREAM などのソケットの接続に基づく型と共に使用されます。  
  
##  <a name="asyncselect"></a>  CAsyncSocket::AsyncSelect  
 ソケットでのイベント通知を要求するには、このメンバー関数を呼び出します。  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *lEvent*  
 アプリケーションが必要とするネットワーク イベントの組み合わせを指定するビットマスクです。  
  
- FD_READ は、読み取り用の準備完了の通知を受信します。  
  
- FD_WRITE は、データが読み取り可能な場合に通知を受信します。  
  
- FD_OOB は、帯域外のデータの到着の通知を受信します。  
  
- FD_ACCEPT は着信接続の通知を受信します。  
  
- FD_CONNECT は、接続の結果の通知を受信します。  
  
- FD_CLOSE がピアでソケットが閉じられたときに通知を受信します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEINVAL を示す、指定されたパラメーターの 1 つが無効でした。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
### <a name="remarks"></a>Remarks  
 この関数は、ソケットの MFC コールバック通知関数が呼び出されるかを指定するに使用されます。 `AsyncSelect` このソケットを非ブロッキング モードに自動的に設定します。 詳細については、この記事を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
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
 アプリケーションが必要とするネットワーク イベントの組み合わせを指定するビットマスクです。  
  
- FD_READ は、読み取り用の準備完了の通知を受信します。  
  
- FD_WRITE は、データが読み取り可能な場合に通知を受信します。  
  
- FD_OOB は、帯域外のデータの到着の通知を受信します。  
  
- FD_ACCEPT は着信接続の通知を受信します。  
  
- FD_CONNECT は、接続の結果の通知を受信します。  
  
- FD_CLOSE がピアでソケットが閉じられたときに通知を受信します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。  
  
### <a name="remarks"></a>Remarks  
 ソケットのハンドルがオブジェクトに格納されている[m_hSocket](#m_hsocket)データ メンバー。  
  
##  <a name="bind"></a>  CAsyncSocket::Bind  
 ローカル アドレスにソケットを関連付けるには、このメンバー関数を呼び出します。  
  
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
 ネットワーク アドレスでは、「128.56.22.8」などのピリオドで区切られた数値。 このパラメーターに文字列、NULL が渡される、`CAsyncSocket`インスタンスがすべてのネットワーク インターフェイス上のクライアント アクティビティを待機する必要があります。  
  
 *lpSockAddr*  
 ポインターを[SOCKADDR](../../mfc/reference/sockaddr-structure.md)このソケットに割り当てるアドレスを含む構造体。  
  
 *nSockAddrLen*  
 内のアドレスの長さ*lpSockAddr* (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEADDRINUSE 指定されたアドレスは既に使用します。 (下の SO_REUSEADDR ソケット オプションを参照してください[SetSockOpt](#setsockopt)。)。  
  
- WSAEFAULT、 *nSockAddrLen*引数が小さすぎる (のサイズよりも小さいか、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造)。  
  
- Windows ソケットのブロックを呼び出す WSAEINPROGRESS A が進行中です。  
  
- このポートでは、WSAEAFNOSUPPORT 指定したアドレス ファミリがサポートされていません。  
  
- WSAEINVAL ソケットは、既にアドレスにバインドされています。  
  
- WSAENOBUFS いないのに十分なバッファーの使用可能な接続が多すぎます。  
  
- 切り離します記述子は、ソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 このルーチンはストリーム ソケットまたは未接続データグラムの前に使用される後続`Connect`または`Listen`呼び出し。 接続要求を受け入れることができます、前にサーバー ソケットをリッスンしている必要がありますポート番号を選択し、既知 Windows Sockets を呼び出すことによって`Bind`します。 `Bind` 名前のない、ソケットをローカル名を割り当てることで、ソケットのローカルの関連付け (ホスト アドレスとポート番号) を確立します。  
  
##  <a name="casyncsocket"></a>  CAsyncSocket::CAsyncSocket  
 空のソケット オブジェクトを構築します。  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>Remarks  
 オブジェクトを構築後に呼び出す必要があるその`Create`ソケット データ構造を作成し、そのアドレスをバインドするメンバー関数。 (待機中のソケットで使用するソケットを作成する場合は、Windows ソケット通信のサーバー側で、`Accept`呼び出し、呼び出すことはありません`Create`するソケット)。  
  
##  <a name="close"></a>  CAsyncSocket::Close  
 ソケットを閉じます。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarks  
 この関数を切り離しますへの参照が失敗するさらにするために、ソケット記述子を解放します。 これは、基になるソケットに対する最後の参照である場合、関連付けられている名前付けの情報とキューに置かれたデータは破棄されます。 ソケット オブジェクトのデストラクター呼び出し`Close`できます。  
  
 `CAsyncSocket`ではなく`CSocket`のセマンティクス`Close`SO_LINGER と SO_DONTLINGER ソケット オプションの影響を受けます。 詳細については、メンバー関数を参照してください。`GetSockOpt`します。  
  
##  <a name="connect"></a>  不要なため  
 データグラム ソケットまたは未接続のストリームへの接続を確立するには、このメンバー関数を呼び出します。  
  
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
 このオブジェクトが接続されているソケットのネットワーク アドレス:「専用」や「128.56.22.8」などのピリオドで区切られた番号などのコンピューター名。  
  
 *nHostPort*  
 ソケット アプリケーションを識別するポートです。  
  
 *lpSockAddr*  
 ポインターを[SOCKADDR](../../mfc/reference/sockaddr-structure.md)接続されたソケットのアドレスを格納する構造体。  
  
 *nSockAddrLen*  
 内のアドレスの長さ*lpSockAddr* (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 WSAEWOULDBLOCK、エラー コードを示します、アプリケーションが、オーバーライド可能なコールバックを使用する場合は、アプリケーションは受信、`OnConnect`メッセージの接続操作が完了するとします。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEADDRINUSE 指定されたアドレスは既に使用します。  
  
- Windows ソケットのブロックを呼び出す WSAEINPROGRESS A が進行中です。  
  
- WSAEADDRNOTAVAIL 指定されたアドレスは、ローカル コンピューターからご利用いただけません。  
  
- 指定されたファミリー WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。  
  
- 使います接続の試行が拒否されました。  
  
- WSAEDESTADDRREQ する宛先アドレスが必要です。  
  
- WSAEFAULT、 *nSockAddrLen*引数が正しくありません。  
  
- ホストのアドレスの WSAEINVAL が無効です。  
  
- WSAEISCONN ソケットが既に接続されています。  
  
- WSAEMFILE いいえファイル記述子をこれ以上は使用できます。  
  
- WSAENETUNREACH ネットワーク到達できませんこのホストからこの時点で。  
  
- WSAENOBUFS いいえバッファー領域は使用できます。 ソケットを接続することはできません。  
  
- 切り離します記述子は、ソケットではありません。  
  
- 接続を試行する WSAETIMEDOUT 接続を確立せずタイムアウトが発生しました。  
  
- ソケットがマークされている WSAEWOULDBLOCK 非ブロッキングの接続は直ちに完了したことはできません。  
  
### <a name="remarks"></a>Remarks  
 ソケットがバインドされている、一意の値が、システムでローカルの関連付けに割り当てられているおよびソケットとしてマークされている場合は、次のバインドします。 されている場合、名前の構造体のアドレス フィールドがすべてゼロの場合は、`Connect`は 0 を返します。 拡張エラー情報を取得する、`GetLastError`メンバー関数。  
  
 ストリーム ソケット (型)、外部ホストをアクティブな接続が開始されます。 ソケットの呼び出しが正常に完了すると、ソケットがデータの送信/受信準備ができています。  
  
 データグラム ソケット (型 SOCK_DGRAM) の場合、既定の出力先が設定されてその後で使用される`Send`と`Receive`呼び出し。  
  
##  <a name="create"></a>  CAsyncSocket::Create  
 呼び出す、 `Create` Windows ソケットを作成し、アタッチするソケット オブジェクトを構築した後、メンバー関数。  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSocketPort*  
 Windows ソケットのポートを選択する場合は、ソケット、または 0 で使用される既知のポート。  
  
 *nSocketType*  
 SOCK_STREAM または SOCK_DGRAM します。  
  
 *lEvent*  
 アプリケーションが必要とするネットワーク イベントの組み合わせを指定するビットマスクです。  
  
- FD_READ は、読み取り用の準備完了の通知を受信します。  
  
- FD_WRITE は、書き込みのための準備完了の通知を受信します。  
  
- FD_OOB は、帯域外のデータの到着の通知を受信します。  
  
- FD_ACCEPT は着信接続の通知を受信します。  
  
- FD_CONNECT は、完全な接続の通知を受信します。  
  
- FD_CLOSE は、ソケットのクロージャの通知を受信します。  
  
 *lpszSockAddress*  
 接続のソケットでは、「128.56.22.8」などのピリオドで区切られた数のネットワーク アドレスを含む文字列へのポインター。このパラメーターに文字列、NULL が渡される、`CAsyncSocket`インスタンスがすべてのネットワーク インターフェイス上のクライアント アクティビティを待機する必要があります。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEAFNOSUPPORT 指定したアドレス ファミリがサポートされていません。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- WSAEMFILE いいえファイル記述子をこれ以上は使用できます。  
  
- WSAENOBUFS いいえバッファー領域は使用できます。 ソケットを作成することはできません。  
  
- WSAEPROTONOSUPPORT、指定したポートがサポートされていません。  
  
- WSAEPROTOTYPE、指定したポートは、このソケットに対して無効な型です。  
  
- このアドレス ファミリでは、WSAESOCKTNOSUPPORT 指定したソケット タイプはサポートされていません。  
  
### <a name="remarks"></a>Remarks  
 `Create` 呼び出し[ソケット](#socket)呼び出しが成功した場合と[バインド](#bind)指定のアドレスにソケットをバインドします。 次の種類のソケットがサポートされています。  
  
- SOCK_STREAM に、シーケンス処理、信頼性の高い、全二重、接続ベースのバイト ストリームを提供します。 インターネット アドレス ファミリの伝送制御プロトコル (TCP) を使用します。  
  
- SOCK_DGRAM サポート データグラムには、固定の (通常は短い) 最大長のパケットのコネクションレスで信頼性の低い。 インターネット アドレス ファミリには、ユーザー データグラム プロトコル (UDP) を使用します。  
  
    > [!NOTE]
    >  `Accept`メンバー関数は、新しい空への参照を受け取ります`CSocket`オブジェクトをパラメーターとして。 呼び出す前に、このオブジェクトを構築する必要があります`Accept`します。 注意このソケット オブジェクトがスコープ接続は閉じられますがなくなるとします。 呼び出さない`Create`この新しいソケット オブジェクト。  
  
> [!IMPORTANT]
> `Create` **いない**スレッド セーフです。  呼び出す場合、マルチ スレッド環境でどこに呼び出すことができる同時に別のスレッドで、必ず、ミュー テックスまたはその他の同期ロックでは、各呼び出しを保護してください。  
  
 ストリームとデータグラム ソケットの詳細については、記事をご覧ください[Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)と[Windows ソケット: ポートとソケット アドレス](../../mfc/windows-sockets-ports-and-socket-addresses.md)と[Windows Sockets 2 API。](/windows/desktop/WinSock/windows-sockets-start-page-2).  
  
##  <a name="detach"></a>  CAsyncSocket::Detach  
 ソケットのハンドルをデタッチするには、このメンバー関数を呼び出す、 *m_hSocket*からのデータ メンバー、`CAsyncSocket`オブジェクトし、設定*m_hSocket*を NULL にします。  
  
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
 ポインター、`CAsyncSocket`がある場合は NULL またはありません`CAsyncSocket`オブジェクトにアタッチされて*hSocket*。  
  
### <a name="remarks"></a>Remarks  
 場合、ソケット ハンドルが指定されると、`CAsyncSocket`オブジェクトがハンドルに関連付けられていない、メンバー関数は NULL を返します。  
  
##  <a name="getlasterror"></a>  CAsyncSocket::GetLastError  
 失敗した最後の操作のエラー状態を取得するには、このメンバー関数を呼び出します。  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値では、このスレッドによって実行された最後の Windows ソケット API ルーチンのエラー コードを示します。  
  
### <a name="remarks"></a>Remarks  
 特定のメンバー関数は、エラーが発生したことを示すとき`GetLastError`適切なエラー コードの取得を呼び出す必要があります。 該当するエラー コードの一覧については、個々 のメンバー関数の説明を参照してください。  
  
 エラー コードの詳細については、次を参照してください。 [Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2)します。  
  
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
 参照を`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rPeerPort*  
 ポートを格納する UINT への参照。  
  
 *lpSockAddr*  
 ポインター、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)ピア ソケットの名を受け取る構造体。  
  
 *lpSockAddrLen*  
 内のアドレスの長さへのポインター *lpSockAddr* (バイト単位)。 返された場合、 *lpSockAddrLen*引数の実際のサイズに含まれる*lpSockAddr* (バイト単位) が返されます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEFAULT、 *lpSockAddrLen*引数が十分な大きさではありません。  
  
- Windows ソケットのブロックを呼び出す WSAEINPROGRESS A が進行中です。  
  
- ソケットが接続されていない接続を保持します。  
  
- 切り離します記述子は、ソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 IPv6 アドレスを処理する[CAsyncSocket::GetPeerNameEx](#getpeernameex)します。  
  
##  <a name="getpeernameex"></a>  CAsyncSocket::GetPeerNameEx  
 このソケットが接続されている (ハンドルの IPv6 アドレス) であるピア ソケットのアドレスを取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>パラメーター  
 *rPeerAddress*  
 参照を`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rPeerPort*  
 ポートを格納する UINT への参照。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEFAULT、 *lpSockAddrLen*引数が十分な大きさではありません。  
  
- Windows ソケットのブロックを呼び出す WSAEINPROGRESS A が進行中です。  
  
- ソケットが接続されていない接続を保持します。  
  
- 切り離します記述子は、ソケットではありません。  
  
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
 参照を`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rSocketPort*  
 ポートを格納する UINT への参照。  
  
 *lpSockAddr*  
 ポインターを[SOCKADDR](../../mfc/reference/sockaddr-structure.md)ソケットのアドレスを受け取る構造体。  
  
 *lpSockAddrLen*  
 内のアドレスの長さへのポインター *lpSockAddr* (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEFAULT、 *lpSockAddrLen*引数が十分な大きさではありません。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- 切り離します記述子は、ソケットではありません。  
  
- ソケットが使用するアドレスにバインドされていない WSAEINVAL`Bind`します。  
  
### <a name="remarks"></a>Remarks  
 この呼び出しは特に便利な場合に、`Connect`実行せずに呼び出しが行われた、`Bind`されます。 この呼び出しは、システムによって設定されているローカルの関連付けを判断できますのみ手段を提供します。 します。  
  
 IPv6 アドレスを処理する[CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>  CAsyncSocket::GetSockNameEx  
 ソケット (IPv6 アドレスのハンドル) のローカル名を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>パラメーター  
 *rSocketAddress*  
 参照を`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rSocketPort*  
 ポートを格納する UINT への参照。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEFAULT、 *lpSockAddrLen*引数が十分な大きさではありません。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- 切り離します記述子は、ソケットではありません。  
  
- ソケットが使用するアドレスにバインドされていない WSAEINVAL`Bind`します。  
  
### <a name="remarks"></a>Remarks  
 この呼び出しは同じ[で](#getsockname)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
 この呼び出しは特に便利な場合に、`Connect`実行せずに呼び出しが行われた、`Bind`されます。 この呼び出しは、システムによって設定されているローカルの関連付けを判断できますのみ手段を提供します。 します。  
  
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
 要求されたオプションの値が返されるバッファーへのポインター。 バッファーで選択したオプションに関連付けられている値が返される*は*します。 によって示される整数*lpOptionLen* (バイト単位) には、このバッファーのサイズを含める必要があります最初とに、返された場合は、返される値のサイズに設定されます。 SO_LINGER のサイズの場合は、`LINGER`構造体は他のすべてのオプションのブール値のサイズであること、または**int**オプションに応じて。 オプションと、「解説」には、そのサイズの一覧を参照してください。  
  
 *lpOptionLen*  
 サイズへのポインター、*は*バッファー (バイト単位)。  
  
 *nLevel*  
 位置のオプションが定義されている場合、レベルサポートされているレベルだけ取得、取得できます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 オプションが設定されていない場合`SetSockOpt`、し`GetSockOpt`オプションの既定値を返します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEFAULT、 *lpOptionLen*引数が無効です。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- WSAENOPROTOOPT オプションは、不明なまたはサポートされていないです。 具体的には、:so_broadcast は SOCK_STREAM、SO_ACCEPTCONN、SO_DONTLINGER、接続、SO_LINGER、および SO_OOBINLINE 中には、型 SOCK_DGRAM のソケットでサポートされていない型のソケットではサポートされていません。  
  
- 切り離します記述子は、ソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 `GetSockOpt` の任意の状態で、あらゆる種類のソケットに関連付けられているソケット オプションの現在の値を取得し、に結果を格納*は*します。 オプションでは、パケットや帯域外のデータ転送のルーティングなどのソケット操作に影響します。  
  
 次のオプションはサポートされて`GetSockOpt`します。 型によってアドレス指定されたデータの種類を識別する*は*します。 低下オプションの使用レベルの取得できます。その他のすべてのオプションでは、レベルの取得を使用します。  
  
|[値]|型|説明|  
|-----------|----------|-------------|  
|SO_ACCEPTCONN|BOOL|ソケットはリッスンします。|  
|:SO_BROADCAST|BOOL|ソケットは、ブロードキャスト メッセージを送信するために構成されます。|  
|SO_DEBUG|BOOL|デバッグが有効になっているとします。|  
|SO_DONTLINGER|BOOL|True の場合、このオプションは無効になります。|  
|SO_DONTROUTE|BOOL|ルーティングが無効です。|  
|SO_ERROR|**int**|エラー状態を取得し、オフにします。|  
|接続|BOOL|Keep-alive が送信されます。|  
|SO_LINGER|`struct LINGER`|現在の待機オプションを返します。|  
|SO_OOBINLINE|BOOL|帯域外のデータは、通常のデータ ストリームの受信中です。|  
|SO_RCVBUF|int|バッファー サイズを受け取ります。|  
|SO_REUSEADDR|BOOL|ソケットは、既に使用中のアドレスにバインドできます。|  
|SO_SNDBUF|**int**|バッファー サイズを送信します。|  
|SO_TYPE|**int**|ソケット (SOCK_STREAM など) の型。|  
|低下|BOOL|送信結合用の Nagle アルゴリズムを無効にします。|  
  
 Berkeley Software Distribution (BSD) オプションがサポートされていません`GetSockOpt`は。  
  
|[値]|型|説明|  
|-----------|----------|-------------|  
|SO_RCVLOWAT|**int**|低水位マークが表示されます。|  
|SO_RCVTIMEO|**int**|受信タイムアウト。|  
|SO_SNDLOWAT|**int**|低水位マークを送信します。|  
|SO_SNDTIMEO|**int**|送信タイムアウト。|  
|なる||IP ヘッダーでオプションを取得します。|  
|TCP_MAXSEG|**int**|TCP セグメントの最大サイズを取得します。|  
  
 呼び出す`GetSockOpt`WSAENOPROTOOPT から返されるエラー コードでサポートされていないオプションが発生`GetLastError`します。  
  
##  <a name="ioctl"></a>  CAsyncSocket::IOCtl  
 ソケットのモードを制御するには、このメンバー関数を呼び出します。  
  
```  
BOOL IOCtl(
    long lCommand,  
    DWORD* lpArgument);
```  
  
### <a name="parameters"></a>パラメーター  
 *lCommand*  
 ソケットでを実行するコマンドです。  
  
 *lpArgument*  
 パラメーターへのポインター *lCommand*します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEINVAL *lCommand*が有効なコマンドまたは*lpArgument*がの許容可能なパラメーターでない*lCommand*、または、コマンドは指定したソケットの種類に適用されません.  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- 切り離します記述子は、ソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 このルーチンは、いずれかの状態のすべてのソケットで使用できます。 取得またはプロトコルと通信サブシステムの独立した、ソケットに関連付けられた操作パラメーターを取得するために使用します。 次のコマンドがサポートされています。  
  
- FIONBIO を有効にする、またはソケットで非ブロッキング モードを無効にします。 *LpArgument*パラメーター、`DWORD`非ブロッキング モードが有効にする場合、0 以外の場合を無効にするにはその場合は 0。 場合`AsyncSelect`を使用しようとし、ソケットで発行された`IOCtl`ソケットを設定するブロッキング モードに戻る は WSAEINVAL で失敗します。 ソケットをブロッキング モードに設定し、WSAEINVAL エラーを防ぐため、アプリケーションを無効にあります`AsyncSelect`呼び出して`AsyncSelect`で、 *lEvent*パラメーターを 0 に等しいを呼び出して`IOCtl`します。  
  
- FIONREAD いずれかで読み取ることができるバイトの最大数を決定する`Receive`このソケットから呼び出します。 *LpArgument*パラメーター、`DWORD`を`IOCtl`結果を格納します。 このソケットが型の場合は、FIONREAD が 1 つの読み取り可能なデータ量の合計を返します`Receive`; これは、通常と同じソケットでのキューに置かれたデータの総量。 このソケットが型 SOCK_DGRAM の FIONREAD はソケットでのキューに置かれた最初のデータグラムのサイズを返します。  
  
- SIOCATMARK 決定すべての帯域外のデータが読み取られたかどうか。 これは、型、帯域外のデータ (SO_OOBINLINE) の行で受信用に構成されている SOCK_STREAM のソケットにのみ適用されます。 読み取られる帯域外のデータが待機していない場合、操作は 0 以外の値を返します。 それ以外の場合、0 が返され、[次へ]`Receive`または`ReceiveFrom`に対してソケットは、「マーク」の前のデータの一部またはすべてを取得は、アプリケーションは、SIOCATMARK 操作を使用してデータが残っているかどうかを判断する必要があります。 (帯域外) の「緊急」のデータの前に通常のデータがある場合は、順序で受信されます。 (なお、`Receive`または`ReceiveFrom`は、同じ呼び出しで帯域外の通常のデータを混在させることはありません)。*LpArgument*パラメーター、`DWORD`を`IOCtl`結果を格納します。  
  
 この関数のサブセットである`ioctl()`Berkeley ソケットで使用します。 具体的には、これは、SIOCATMARK はサポートされているソケット レベルでのみコマンド FIOASYNC に相当コマンドではありません。  
  
##  <a name="listen"></a>  CAsyncSocket::Listen  
 受信接続要求をリッスンするには、このメンバー関数を呼び出します。  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>パラメーター  
 *nConnectionBacklog*  
 接続待ちのキューを拡張できる最大長。 有効な範囲は 1 から 5 には。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEADDRINUSE しようとは、使用中で、アドレスをリッスンするようになりました。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- ソケットがバインドされていない WSAEINVAL`Bind`が既に接続されているか。  
  
- WSAEISCONN ソケットが既に接続されています。  
  
- WSAEMFILE いいえファイル記述子をこれ以上は使用できます。  
  
- WSAENOBUFS いいえバッファー領域は使用できます。  
  
- 切り離します記述子は、ソケットではありません。  
  
- 参照先のソケットがサポートする型の WSAEOPNOTSUPP、`Listen`操作。  
  
### <a name="remarks"></a>Remarks  
 接続を受け入れるように、ソケットを最初に作成`Create`、着信接続用のバックログがで指定された`Listen`での接続の承認、および`Accept`します。 `Listen` のみ適用されますソケット接続をサポートする、型のものです。 このソケットは、着信接続が確認され、プロセスによって保留中の承認キューに置かれた場所の「パッシブ」モードに配置されます。  
  
 この関数がサーバー (または接続を受け入れる必要がある任意のアプリケーション) によって使用される通常、一度に 1 つ以上の接続要求がある可能性があります: 場合は、キューがいっぱいで、接続要求が到着した、クライアントは、エラーを示す値を使います。  
  
 `Listen` 使用可能なポート (記述子) がない場合に、合理的に続行を試行します。 キューが空にするまで接続を受け入れることです。 ポートが利用可能になった場合は、後の呼び出し`Listen`または`Accept`は、現在または最近の「バックログ」にキューを可能であれば、補充し、着信接続のリッスンを再開します。  
  
##  <a name="m_hsocket"></a>  CAsyncSocket::m_hSocket  
 これによってカプセル化されたソケットのソケット ハンドルを格納`CAsyncSocket`オブジェクト。  
  
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
  
- **0**が正常に実行する関数。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
##  <a name="onclose"></a>  CAsyncSocket::OnClose  
 ソケットにそのプロセスによって接続されたソケットが閉じられたことを通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用されます、`OnClose`メンバー関数。  
  
- **0**が正常に実行する関数。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAECONNRESET 接続は、リモート側によってリセットされました。  
  
- WSAECONNABORTED 接続がタイムアウトまたは他の障害によって中止されました。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
##  <a name="onconnect"></a>  CAsyncSocket::OnConnect  
 その接続試行が完了したこと、正常にまたはエラーであるかどうかを接続するソケットに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用されます、`OnConnect`メンバー関数。  
  
- **0**が正常に実行する関数。  
  
- WSAEADDRINUSE 指定されたアドレスは既に使用します。  
  
- WSAEADDRNOTAVAIL 指定されたアドレスは、ローカル コンピューターからご利用いただけません。  
  
- 指定されたファミリー WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。  
  
- 接続の試行が拒否されました強制的に使います。  
  
- WSAEDESTADDRREQ する宛先アドレスが必要です。  
  
- WSAEFAULT、 *lpSockAddrLen*引数が正しくありません。  
  
- WSAEINVAL ソケットは、既にアドレスにバインドされています。  
  
- WSAEISCONN ソケットが既に接続されています。  
  
- WSAEMFILE いいえファイル記述子をこれ以上は使用できます。  
  
- WSAENETUNREACH ネットワーク到達できませんこのホストからこの時点で。  
  
- WSAENOBUFS いいえバッファー領域は使用できます。 ソケットを接続することはできません。  
  
- ソケットが接続されていない接続を保持します。  
  
- 切り離します記述子は、ファイル、ソケットではなくです。  
  
- 接続を確立せずに WSAETIMEDOUT 接続の試行がタイムアウトしました。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  [CSocket](../../mfc/reference/csocket-class.md)、`OnConnect`通知関数を呼び出すことはありません。 接続は、単に呼び出す`Connect`、(正常にまたはエラー)、接続が完了したときに返されます。 MFC 実装の詳細は、接続の通知を処理する方法。  
  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>  CAsyncSocket::OnOutOfBandData  
 送信側のソケットが帯域外のデータを送信する受信側のソケットに通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用されます、`OnOutOfBandData`メンバー関数。  
  
- **0**が正常に実行する関数。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
### <a name="remarks"></a>Remarks  
 帯域外のデータは、論理的に独立したチャネル型の接続されたソケットの各ペアに関連付けられているです。 チャネルは通常、緊急データの送信に使用されます。  
  
 MFC クラスのユーザーが、帯域外のデータをサポートしている`CAsyncSocket`これを使用しないでください。 簡単な方法では、このようなデータを渡すための 2 つ目のソケットを作成します。 帯域外のデータの詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
##  <a name="onreceive"></a>  CAsyncSocket::OnReceive  
 ソケットに呼び出すことによって取得できるバッファーのデータがあることを通知するためにフレームワークによって呼び出される、`Receive`メンバー関数。  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用されます、`OnReceive`メンバー関数。  
  
- **0**が正常に実行する関数。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>  CAsyncSocket::OnSend  
 ソケットに呼び出すことによってデータを送信できるようになりましたことを通知するためにフレームワークによって呼び出される、`Send`メンバー関数。  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nErrorCode*  
 ソケットで最新のエラーです。 次のエラー コードに適用されます、`OnSend`メンバー関数。  
  
- **0**が正常に実行する関数。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../../mfc/windows-sockets-socket-notifications.md)します。  
  
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
 既存のコピーするには、この関数を呼び出す`CAsyncSocket`を別のオブジェクト`CAsyncSocket`オブジェクト。  
  
##  <a name="operator_socket"></a>  CAsyncSocket::operator ソケット  
 この演算子を使用してのソケット ハンドルを取得する、`CAsyncSocket`オブジェクト。  
  
```  
operator SOCKET() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、ソケット オブジェクトのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 ハンドルを使用して、Windows Api を直接呼び出すことができます。  
  
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
 受信データのバッファー。  
  
 *nBufLen*  
 長さ*lpBuf* (バイト単位)。  
  
 *nFlags*  
 これで、呼び出しが行われる方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者の場合は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- MSG_PEEK は、受信データをピークします。 データは、バッファーにコピーされますが、入力キューからは削除されません。  
  
- MSG_OOB プロセス帯域外のデータ。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しない場合`Receive`受信したバイト数を返します。 接続が閉じられた場合は、0 を返します。 それ以外の場合、あふれたの値が返され、特定のエラー コードを呼び出すことによって取得できます[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- ソケットが接続されていない接続を保持します。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- 切り離します記述子は、ソケットではありません。  
  
- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットが型はありません。  
  
- WSAESHUTDOWN ソケットがシャット ダウン; されました呼び出すことはできません`Receive`後にソケットで`ShutDown`でが呼び出された*nHow* 0 または 2 に設定します。  
  
- WSAEWOULDBLOCK ソケットがマークされているブロッキング、`Receive`操作がブロックされます。  
  
- WSAEMSGSIZE データグラムが、指定されたバッファーに収まるようには大きすぎるため、切り捨てられました。  
  
- ソケットがバインドされていない WSAEINVAL`Bind`します。  
  
- WSAECONNABORTED 仮想回線はタイムアウトまたは他の障害によって中止されました。  
  
- WSAECONNRESET リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>Remarks  
 この関数は、接続されているストリームとデータグラム ソケットが使用し、着信データの読み取りに使用されます。  
  
 型のソケットは現在、指定されたバッファーのサイズの最大使用可能な限り多くの情報が返されます。 ソケットが帯域外のデータ (ソケット オプション SO_OOBINLINE) の行の受信に構成されている、帯域外のデータは読み取りがない場合は、帯域外のデータのみが返されます。 アプリケーションを使用できます、`IOCtlSIOCATMARK`オプションまたは[OnOutOfBandData](#onoutofbanddata)を任意の帯域外の複数のデータが読み取られるままかどうかを判断します。  
  
 データグラム ソケットの場合は、指定されたバッファーのサイズの最大のエンキューされたデータグラムの最初からデータを抽出します。 データグラムが指定されたバッファーよりも大きい場合は、データグラムの最初の部分でバッファーの読み込みが、余分なデータが失われたと`Receive`WSAEMSGSIZE にあふれたと、エラー コードの値のセットを返します。 ソケットに使用可能な受信データがない場合は、ときに設定エラー コードであふれたが返されます。 [OnReceive](#onreceive)より多くのデータの受信時に決定するコールバック関数を使用できます。  
  
 型のソケットがあり、リモート側が、接続を正常にシャット ダウンする場合、`Receive`は 0 バイトを受信してすぐに完了します。 接続がリセットされた場合、 `Receive` WSAECONNRESET エラーで失敗します。  
  
 `Receive` 時間ごとに 1 回だけ呼び出す必要があります[CAsyncSocket::OnReceive](#onreceive)が呼び出されます。  
  
### <a name="example"></a>例  
  例をご覧ください[CAsyncSocket::OnReceive](#onreceive)します。  
  
##  <a name="receivefrom"></a>  で  
 データグラムを受信およびの送信元アドレスを格納するには、このメンバー関数を呼び出す、 [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造または*rSocketAddress*します。  
  
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
 受信データのバッファー。  
  
 *nBufLen*  
 長さ*lpBuf* (バイト単位)。  
  
 *rSocketAddress*  
 参照を`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rSocketPort*  
 ポートを格納する UINT への参照。  
  
 *lpSockAddr*  
 ポインターを[SOCKADDR](../../mfc/reference/sockaddr-structure.md)戻り時にソース アドレスを保持する構造体。  
  
 *lpSockAddrLen*  
 送信元アドレスの長さへのポインター *lpSockAddr* (バイト単位)。  
  
 *nFlags*  
 これで、呼び出しが行われる方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者の場合は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- MSG_PEEK は、受信データをピークします。 データは、バッファーにコピーされますが、入力キューからは削除されません。  
  
- MSG_OOB プロセス帯域外のデータ。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しない場合`ReceiveFrom`受信したバイト数を返します。 接続が閉じられた場合は、0 を返します。 それ以外の場合、あふれたの値が返され、特定のエラー コードを呼び出すことによって取得できます`GetLastError`します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEFAULT、 *lpSockAddrLen*引数が無効です。 *lpSockAddr*バッファーが小さすぎるため、ピア アドレスに対応します。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- ソケットがバインドされていない WSAEINVAL`Bind`します。  
  
- ソケットが接続には、(SOCK_STREAM のみ) が接続されています。  
  
- 切り離します記述子は、ソケットではありません。  
  
- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットが型はありません。  
  
- WSAESHUTDOWN ソケットがシャット ダウン; されました呼び出すことはできません`ReceiveFrom`後にソケットで`ShutDown`でが呼び出された*nHow* 0 または 2 に設定します。  
  
- WSAEWOULDBLOCK ソケットがマークされているブロッキング、`ReceiveFrom`操作がブロックされます。  
  
- WSAEMSGSIZE データグラムが、指定されたバッファーに収まるようには大きすぎるため、切り捨てられました。  
  
- WSAECONNABORTED 仮想回線はタイムアウトまたは他の障害によって中止されました。  
  
- WSAECONNRESET リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>Remarks  
 この関数は、(接続されている可能性があります) のソケットの受信データを読み取るし、データの送信元アドレスのキャプチャに使用されます。  
  
 IPv6 アドレスを処理する[CAsyncSocket::ReceiveFromEx](#receivefromex)します。  
  
 型のソケットは現在、指定されたバッファーのサイズの最大使用可能な限り多くの情報が返されます。 ソケットが帯域外のデータ (ソケット オプション SO_OOBINLINE) の行の受信に構成されている、帯域外のデータは読み取りがない場合は、帯域外のデータのみが返されます。 アプリケーションを使用できます、`IOCtlSIOCATMARK`オプションまたは`OnOutOfBandData`を任意の帯域外の複数のデータが読み取られるままかどうかを判断します。 *LpSockAddr*と*lpSockAddrLen* SOCK_STREAM ソケットでのパラメーターは無視されます。  
  
 データグラム ソケットの場合は、指定されたバッファーのサイズの最大のエンキューされたデータグラムの最初からデータを抽出します。 データグラムが指定されたバッファーよりも大きい場合は、メッセージの最初の部分でバッファーの読み込みが、余分なデータが失われたと`ReceiveFrom`WSAEMSGSIZE にあふれたと、エラー コードの値のセットを返します。  
  
 場合*lpSockAddr* 、0 以外の場合は、ソケットの SOCK_DGRAM の型が、データを送信するソケットのネットワーク アドレスは、対応するコピー [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体。 によって示される値*lpSockAddrLen*は、この構造体のサイズに初期化されが格納されているアドレスの実際のサイズを示す戻り値に変更します。 ソケットに使用可能な受信データがない場合、`ReceiveFrom`データの到着、ソケットがない限り、呼び出しが待機する非ブロッキングします。 この場合、あふれたが WSAEWOULDBLOCK に設定エラー コードで返されます。 `OnReceive`より多くのデータの受信時に決定するコールバックを使用できます。  
  
 型のソケットがあり、リモート側が、接続を正常にシャット ダウンする場合、`ReceiveFrom`は 0 バイトを受信してすぐに完了します。  
  
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
 受信データのバッファー。  
  
 *nBufLen*  
 長さ*lpBuf* (バイト単位)。  
  
 *rSocketAddress*  
 参照を`CString`をピリオドで区切られた数値 IP アドレスを受け取るオブジェクト。  
  
 *rSocketPort*  
 ポートを格納する UINT への参照。  
  
 *nFlags*  
 これで、呼び出しが行われる方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者の場合は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- MSG_PEEK は、受信データをピークします。 データは、バッファーにコピーされますが、入力キューからは削除されません。  
  
- MSG_OOB プロセス帯域外のデータ。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しない場合`ReceiveFromEx`受信したバイト数を返します。 接続が閉じられた場合は、0 を返します。 それ以外の場合、あふれたの値が返され、特定のエラー コードを呼び出すことによって取得できます`GetLastError`します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEFAULT、 *lpSockAddrLen*引数が無効です。 *lpSockAddr*バッファーが小さすぎるため、ピア アドレスに対応します。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- ソケットがバインドされていない WSAEINVAL`Bind`します。  
  
- ソケットが接続には、(SOCK_STREAM のみ) が接続されています。  
  
- 切り離します記述子は、ソケットではありません。  
  
- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットが型はありません。  
  
- WSAESHUTDOWN ソケットがシャット ダウン; されました呼び出すことはできません`ReceiveFromEx`後にソケットで`ShutDown`でが呼び出された*nHow* 0 または 2 に設定します。  
  
- WSAEWOULDBLOCK ソケットがマークされているブロッキング、`ReceiveFromEx`操作がブロックされます。  
  
- WSAEMSGSIZE データグラムが、指定されたバッファーに収まるようには大きすぎるため、切り捨てられました。  
  
- WSAECONNABORTED 仮想回線はタイムアウトまたは他の障害によって中止されました。  
  
- WSAECONNRESET リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>Remarks  
 この関数は、(接続されている可能性があります) のソケットの受信データを読み取るし、データの送信元アドレスのキャプチャに使用されます。  
  
 この関数は、同じ[で](#receivefrom)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
 型のソケットは現在、指定されたバッファーのサイズの最大使用可能な限り多くの情報が返されます。 ソケットが帯域外のデータ (ソケット オプション SO_OOBINLINE) の行の受信に構成されている、帯域外のデータは読み取りがない場合は、帯域外のデータのみが返されます。 アプリケーションを使用できます、`IOCtlSIOCATMARK`オプションまたは`OnOutOfBandData`を任意の帯域外の複数のデータが読み取られるままかどうかを判断します。 *LpSockAddr*と*lpSockAddrLen* SOCK_STREAM ソケットでのパラメーターは無視されます。  
  
 データグラム ソケットの場合は、指定されたバッファーのサイズの最大のエンキューされたデータグラムの最初からデータを抽出します。 データグラムが指定されたバッファーよりも大きい場合は、メッセージの最初の部分でバッファーの読み込みが、余分なデータが失われたと`ReceiveFromEx`WSAEMSGSIZE にあふれたと、エラー コードの値のセットを返します。  
  
 場合*lpSockAddr* 、0 以外の場合は、ソケットの SOCK_DGRAM の型が、データを送信するソケットのネットワーク アドレスは、対応するコピー [SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造体。 によって示される値*lpSockAddrLen*は、この構造体のサイズに初期化されが格納されているアドレスの実際のサイズを示す戻り値に変更します。 ソケットに使用可能な受信データがない場合、`ReceiveFromEx`データの到着、ソケットがない限り、呼び出しが待機する非ブロッキングします。 この場合、あふれたが WSAEWOULDBLOCK に設定エラー コードで返されます。 `OnReceive`より多くのデータの受信時に決定するコールバックを使用できます。  
  
 型のソケットがあり、リモート側が、接続を正常にシャット ダウンする場合、`ReceiveFromEx`は 0 バイトを受信してすぐに完了します。  
  
##  <a name="send"></a>  CAsyncSocket::Send  
 接続されたソケットにデータを送信するには、このメンバー関数を呼び出します。  
  
```  
virtual int Send(
    const void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuf*  
 転送するデータを格納するバッファー。  
  
 *nBufLen*  
 内のデータの長さ*lpBuf* (バイト単位)。  
  
 *nFlags*  
 これで、呼び出しが行われる方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者の場合は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- MSG_DONTROUTE では、ルーティングの対象はならないデータを指定します。 このフラグを無視する、Windows Sockets 業者を選択できます。  
  
- MSG_OOB 帯域外のデータを送信 (SOCK_STREAM のみ)。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しない場合`Send`送信される文字の合計数を返します。 (これがで示される数より少なくをすることに注意してください*nBufLen*。)。それ以外の場合、あふれたの値が返され、特定のエラー コードを呼び出すことによって取得できます[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEACCES、要求されたアドレスは、ブロードキャスト アドレスですが、適切なフラグが設定されませんでした。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- WSAEFAULT、 *lpBuf*引数が有効なユーザーのアドレス空間の一部ではありません。  
  
- Windows ソケットの実装で削除されるため、いるとき、接続をリセットする必要があります。  
  
- WSAENOBUFS、Windows ソケットの実装では、バッファーのデッドロックをレポートします。  
  
- ソケットが接続されていない接続を保持します。  
  
- 切り離します記述子は、ソケットではありません。  
  
- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットが型はありません。  
  
- WSAESHUTDOWN ソケットがシャット ダウン; されました呼び出すことはできません`Send`後にソケットで`ShutDown`でが呼び出された*nHow* 1 または 2 に設定します。  
  
- WSAEWOULDBLOCK ソケットがマークされている非ブロッキングされ、要求された操作を停止します。  
  
- WSAEMSGSIZE ソケット SOCK_DGRAM、種類、データグラムが Windows ソケットの実装でサポートされている最大値よりも大きい。  
  
- ソケットがバインドされていない WSAEINVAL`Bind`します。  
  
- WSAECONNABORTED 仮想回線はタイムアウトまたは他の障害によって中止されました。  
  
- WSAECONNRESET リモート側によって仮想回線がリセットされました。  
  
### <a name="remarks"></a>Remarks  
 `Send` 接続されているストリームまたはデータグラム ソケットで送信したデータの書き込みに使用します。 データグラム ソケットでは、注意が必要で、指定した、基になるサブネットの IP パケットの最大サイズを超えることはできません、`iMaxUdpDg`内の要素、 [WSADATA](../../mfc/reference/wsadata-structure.md)によって返される構造体`AfxSocketInit`します。 データが長すぎて、基になるプロトコルの場合、エラー WSAEMSGSIZE 経由で返されます`GetLastError`データは送信されません。  
  
 データグラム ソケットを正常に完了ことに注意を`Send`データが正常に配信されたことを示しません。  
  
 `CAsyncSocket`型のオブジェクトは、書き込まれたバイト数は、1 ~ ローカルおよび外部の両方のホスト バッファーの可用性に応じて、要求された長さにできます。  
  
### <a name="example"></a>例  
  例をご覧ください[CAsyncSocket::OnSend](#onsend)します。  
  
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
 転送するデータを格納するバッファー。  
  
 *nBufLen*  
 内のデータの長さ*lpBuf* (バイト単位)。  
  
 *nHostPort*  
 ソケット アプリケーションを識別するポートです。  
  
 *lpszHostAddress*  
 このオブジェクトが接続されているソケットのネットワーク アドレス:「専用、」や「128.56.22.8」などのピリオドで区切られた番号などのコンピューター名。  
  
 *nFlags*  
 これで、呼び出しが行われる方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者の場合は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- MSG_DONTROUTE では、ルーティングの対象はならないデータを指定します。 このフラグを無視する、Windows Sockets 業者を選択できます。  
  
- MSG_OOB 帯域外のデータを送信 (SOCK_STREAM のみ)。  
  
 *lpSockAddr*  
 ポインターを[SOCKADDR](../../mfc/reference/sockaddr-structure.md)ターゲット ソケットのアドレスを含む構造体。  
  
 *nSockAddrLen*  
 内のアドレスの長さ*lpSockAddr* (バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しない場合`SendTo`送信される文字の合計数を返します。 (これがで示される数より少なくをすることに注意してください*nBufLen*。)。それ以外の場合、あふれたの値が返され、特定のエラー コードを呼び出すことによって取得できます[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEACCES、要求されたアドレスは、ブロードキャスト アドレスですが、適切なフラグが設定されませんでした。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- WSAEFAULT、 *lpBuf*または*lpSockAddr*パラメーターは、ユーザーのアドレス空間の一部ではない、または*lpSockAddr*引数が小さすぎる (、のサイズよりも小さい[SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造)。  
  
- WSAEINVAL ホスト名が無効です。  
  
- Windows ソケットの実装で削除されるため、いるとき、接続をリセットする必要があります。  
  
- WSAENOBUFS、Windows ソケットの実装では、バッファーのデッドロックをレポートします。  
  
- ソケットが接続には、(SOCK_STREAM のみ) が接続されています。  
  
- 切り離します記述子は、ソケットではありません。  
  
- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットが型はありません。  
  
- WSAESHUTDOWN ソケットがシャット ダウン; されました呼び出すことはできません`SendTo`後にソケットで`ShutDown`でが呼び出された*nHow* 1 または 2 に設定します。  
  
- WSAEWOULDBLOCK ソケットがマークされている非ブロッキングされ、要求された操作を停止します。  
  
- WSAEMSGSIZE ソケット SOCK_DGRAM、種類、データグラムが Windows ソケットの実装でサポートされている最大値よりも大きい。  
  
- WSAECONNABORTED 仮想回線はタイムアウトまたは他の障害によって中止されました。  
  
- WSAECONNRESET リモート側によって仮想回線がリセットされました。  
  
- WSAEADDRNOTAVAIL 指定されたアドレスは、ローカル コンピューターからご利用いただけません。  
  
- 指定されたファミリー WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。  
  
- WSAEDESTADDRREQ する宛先アドレスが必要です。  
  
- WSAENETUNREACH ネットワーク到達できませんこのホストからこの時点で。  
  
### <a name="remarks"></a>Remarks  
 `SendTo` データグラムまたはストリーム ソケットで使用され、ソケットで送信したデータの書き込みに使用されます。 データグラム ソケットでは、注意が必要で、指定した、基になるサブネットの IP パケットの最大サイズを超えることはできません、`iMaxUdpDg`内の要素、 [WSADATA](../../mfc/reference/wsadata-structure.md)構造をして入力[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). データが長すぎて、基になるプロトコルの場合、エラー WSAEMSGSIZE が返され、データは送信されません。  
  
 なおが正常に完了、`SendTo`データが正常に配信されたことを示しません。  
  
 `SendTo` 識別される特定のソケットにデータグラムを送信する SOCK_DGRAM ソケットでのみ使用される、 *lpSockAddr*パラメーター。  
  
 (上、SOCK_DGRAM のみ)、ブロードキャストを送信するアドレス、 *lpSockAddr* INADDR_BROADCAST (WINSOCK Windows Sockets ヘッダー ファイルで定義特別な IP アドレスを使用してパラメーターを作成する必要があります。H) と共に目的のポート番号。 または、 *lpszHostAddress*パラメーターが NULL でブロードキャストのソケットが構成されています。 一般に、ブロードキャスト データグラムを断片化が発生することができます、サイズを超えたことをお勧めは (ヘッダーを除く) データグラムのデータ部分が 512 バイトを超えていないことを意味します。  
  
 IPv6 アドレスを処理する[CAsyncSocket::SendToEx](#sendtoex)します。  
  
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
 転送するデータを格納するバッファー。  
  
 *nBufLen*  
 内のデータの長さ*lpBuf* (バイト単位)。  
  
 *nHostPort*  
 ソケット アプリケーションを識別するポートです。  
  
 *lpszHostAddress*  
 このオブジェクトが接続されているソケットのネットワーク アドレス:「専用、」や「128.56.22.8」などのピリオドで区切られた番号などのコンピューター名。  
  
 *nFlags*  
 これで、呼び出しが行われる方法を指定します。 この関数のセマンティクスがソケット オプションによって決まりますが、 *nFlags*パラメーター。 後者の場合は、C++ と、次の値のいずれかを組み合わせることによって構築**または**演算子。  
  
- MSG_DONTROUTE では、ルーティングの対象はならないデータを指定します。 このフラグを無視する、Windows Sockets 業者を選択できます。  
  
- MSG_OOB 帯域外のデータを送信 (SOCK_STREAM のみ)。  
  
### <a name="return-value"></a>戻り値  
 エラーが発生しない場合`SendToEx`送信される文字の合計数を返します。 (これがで示される数より少なくをすることに注意してください*nBufLen*。)。それ以外の場合、あふれたの値が返され、特定のエラー コードを呼び出すことによって取得できます[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEACCES、要求されたアドレスは、ブロードキャスト アドレスですが、適切なフラグが設定されませんでした。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- WSAEFAULT、 *lpBuf*または*lpSockAddr*パラメーターは、ユーザーのアドレス空間の一部ではない、または*lpSockAddr*引数が小さすぎる (、のサイズよりも小さい[SOCKADDR](../../mfc/reference/sockaddr-structure.md)構造)。  
  
- WSAEINVAL ホスト名が無効です。  
  
- Windows ソケットの実装で削除されるため、いるとき、接続をリセットする必要があります。  
  
- WSAENOBUFS、Windows ソケットの実装では、バッファーのデッドロックをレポートします。  
  
- ソケットが接続には、(SOCK_STREAM のみ) が接続されています。  
  
- 切り離します記述子は、ソケットではありません。  
  
- WSAEOPNOTSUPP MSG_OOB が指定されましたが、ソケットが型はありません。  
  
- WSAESHUTDOWN ソケットがシャット ダウン; されました呼び出すことはできません`SendToEx`後にソケットで`ShutDown`でが呼び出された*nHow* 1 または 2 に設定します。  
  
- WSAEWOULDBLOCK ソケットがマークされている非ブロッキングされ、要求された操作を停止します。  
  
- WSAEMSGSIZE ソケット SOCK_DGRAM、種類、データグラムが Windows ソケットの実装でサポートされている最大値よりも大きい。  
  
- WSAECONNABORTED 仮想回線はタイムアウトまたは他の障害によって中止されました。  
  
- WSAECONNRESET リモート側によって仮想回線がリセットされました。  
  
- WSAEADDRNOTAVAIL 指定されたアドレスは、ローカル コンピューターからご利用いただけません。  
  
- 指定されたファミリー WSAEAFNOSUPPORT アドレスは、このソケットでは使用できません。  
  
- WSAEDESTADDRREQ する宛先アドレスが必要です。  
  
- WSAENETUNREACH ネットワーク到達できませんこのホストからこの時点で。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、同じ[で](#sendto)IPv6 を処理する点を除いて、従来のプロトコルに対応します。  
  
 `SendToEx` データグラムまたはストリーム ソケットで使用され、ソケットで送信したデータの書き込みに使用されます。 データグラム ソケットでは、注意が必要で、指定した、基になるサブネットの IP パケットの最大サイズを超えることはできません、`iMaxUdpDg`内の要素、 [WSADATA](../../mfc/reference/wsadata-structure.md)構造をして入力[AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). データが長すぎて、基になるプロトコルの場合、エラー WSAEMSGSIZE が返され、データは送信されません。  
  
 なおが正常に完了、`SendToEx`データが正常に配信されたことを示しません。  
  
 `SendToEx` 識別される特定のソケットにデータグラムを送信する SOCK_DGRAM ソケットでのみ使用される、 *lpSockAddr*パラメーター。  
  
 (上、SOCK_DGRAM のみ)、ブロードキャストを送信するアドレス、 *lpSockAddr* INADDR_BROADCAST (WINSOCK Windows Sockets ヘッダー ファイルで定義特別な IP アドレスを使用してパラメーターを作成する必要があります。H) と共に目的のポート番号。 または、 *lpszHostAddress*パラメーターが NULL でブロードキャストのソケットが構成されています。 一般に、ブロードキャスト データグラムを断片化が発生することができます、サイズを超えたことをお勧めは (ヘッダーを除く) データグラムのデータ部分が 512 バイトを超えていないことを意味します。  
  
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
 要求されたオプションの値が指定されているバッファーへのポインター。  
  
 *nOptionLen*  
 サイズ、*は*バッファー (バイト単位)。  
  
 *nLevel*  
 位置のオプションが定義されている場合、レベルサポートされているレベルだけ取得、取得できます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEFAULT*は*プロセスのアドレス空間の有効なパーツ内にないです。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- WSAEINVAL *nLevel*が有効でないかの情報は、*は*が無効です。  
  
- 接続が設定されているときの接続がタイムアウトします。  
  
- WSAENOPROTOOPT オプションは、不明なまたはサポートされていないです。 具体的には、:so_broadcast は SOCK_STREAM、SO_DONTLINGER、接続、SO_LINGER、および SO_OOBINLINE 中には、型 SOCK_DGRAM のソケットでサポートされていない型のソケットではサポートされていません。  
  
- 接続が設定されている場合、接続の接続がリセットされました。  
  
- 切り離します記述子は、ソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 `SetSockOpt` いずれかの状態で、あらゆる種類のソケットに関連付けられているソケット オプションの現在の値を設定します。 オプションが複数のプロトコル レベルで存在することができます、この仕様はのみが最上位の「ソケット」レベルに存在するオプションを定義します。 オプションでは、優先データは、通常のデータ ストリームで受信したブロードキャスト メッセージがソケットに送信できる具合かどうかどうかなどのソケット操作に影響します。  
  
 ソケット オプションの 2 種類があります: ブール型のオプションを有効にするか、機能や動作を無効にして、整数値または構造体を必要とするオプション。 ブール型のオプションを有効に*は*ゼロ以外の整数を指します。 オプションを無効にする*は*0 に等しい整数を指します。 *nOptionLen*必要があります`sizeof(BOOL)`のブール型のオプション。 その他のオプションについて*は*整数またはオプションとして、目的の値を含む構造体を指すと*nOptionLen*整数または構造体の長さです。  
  
 SO_LINGER 未送信のデータがソケットでキューに置かれたときの動作を制御して、`Close`関数は、ソケットを閉じます。  
  
 既定では、ソケットをバインドすることはできません (を参照してください[バインド](#bind)) が既に使用しているローカル アドレスにします。 場合によっては、ただし、ある可能性がありますこの方法でアドレスを「再利用」することが望ましい。 すべての接続は、ローカルおよびリモート アドレスの組み合わせによって一意に識別、ために、2 つのソケットがリモートのアドレスが異なる限り、同じローカル アドレスにバインドされていることに問題はありません。  
  
 Windows ソケットの実装を通知するためにする、`Bind`目的のアドレスが既に別のソケットによって使用されているために、ソケットでの呼び出しが禁止される必要がない、アプリケーションが発行する前に、ソケットの SO_REUSEADDR ソケット オプションを設定する必要があります、`Bind`呼び出します。 時にのみ、オプションが解釈されることに注意してください、`Bind`呼び出す: 必要はありませんので (ただし、害のない) は、既存のアドレスにバインドするソケットでオプションを設定する設定し、または後にオプションをリセットして、`Bind`呼び出しにはこのまたはその他のソケットに影響を与えません。  
  
 アプリケーションでは、Windows ソケットの実装が、接続のソケット オプションをオンにして「キープ アライブ」パケットで伝送制御プロトコル (TCP) 接続の使用を有効にすることを要求できます。 Windows Sockets 実装必要キープア ライブの使用をサポートしていません: 場合は、正確なセマンティクスは実装によって異なりますの RFC 1122 セクション 4.2.3.6 に準拠している必要があります:"Requirements for Internet Hosts-通信レイヤーです"。 結果として、接続が削除された場合「キープア ライブ」のエラー コードいるときが返さ進行中の呼び出しに、ソケットでれ接続保持の後続の呼び出しは失敗します。  
  
 低下オプションには、Nagle アルゴリズムが無効にします。 Nagle アルゴリズムを使用すると、フルサイズのパケットを送信できるまで、未確認の送信データをバッファー処理によって、ホストによって送信された小さなパケットの数を減らします。 ただし、一部のアプリケーションのこのアルゴリズムは、パフォーマンスを妨げる、低下を無効にするために使用できます。 アプリケーションの作成者では、影響のためが十分に理解して、必要なため、ネットワーク パフォーマンスに大きな悪影響を及ぼすことができます低下を設定しない限り、低下は設定しないでください。 低下は、唯一サポートされているレベルの取得できる; を使用するソケット オプションその他のすべてのオプションでは、レベルの取得を使用します。  
  
 Windows Sockets 装置の一部の実装は、アプリケーションによって SO_DEBUG オプションが設定されている場合にデバッグ情報を出力します。  
  
 次のオプションはサポートされて`SetSockOpt`します。 型によってアドレス指定されたデータの種類を識別する*は*します。  
  
|[値]|型|説明|  
|-----------|----------|-------------|  
|:SO_BROADCAST|BOOL|ソケットでブロードキャスト メッセージの送信を許可します。|  
|SO_DEBUG|BOOL|デバッグ情報を記録します。|  
|SO_DONTLINGER|BOOL|ブロックしない`Close`未送信のデータ送信を待機しています。 SO_LINGER の設定と同じには、このオプションを設定`l_onoff`を 0 に設定します。|  
|SO_DONTROUTE|BOOL|ルーティングはありません: インターフェイスに直接送信します。|  
|接続|BOOL|キープア ライブを送信します。|  
|SO_LINGER|`struct LINGER`|待機`Close`未送信のデータが存在する場合。|  
|SO_OOBINLINE|BOOL|通常のデータ ストリームで帯域外のデータが表示されます。|  
|SO_RCVBUF|**int**|受信用のバッファー サイズを指定します。|  
|SO_REUSEADDR|BOOL|既に使用中のアドレスにバインドするソケットを許可します。 (を参照してください[バインド](#bind))。|  
|SO_SNDBUF|**int**|送信バッファー サイズを指定します。|  
|低下|BOOL|送信結合用の Nagle アルゴリズムを無効にします。|  
  
 Berkeley Software Distribution (BSD) オプションがサポートされていません`SetSockOpt`は。  
  
|[値]|型|説明|  
|-----------|----------|-------------|  
|SO_ACCEPTCONN|BOOL|ソケットがリッスンしています。|  
|SO_ERROR|**int**|エラー状態を取得し、オフにします。|  
|SO_RCVLOWAT|**int**|低水位マークが表示されます。|  
|SO_RCVTIMEO|**int**|受信タイムアウト|  
|SO_SNDLOWAT|**int**|低水位マークを送信します。|  
|SO_SNDTIMEO|**int**|送信タイムアウト。|  
|SO_TYPE|**int**|ソケットの種類です。|  
|なる||IP ヘッダーには、オプションのフィールドを設定します。|  
  
##  <a name="shutdown"></a>  CAsyncSocket::ShutDown  
 呼び出しを無効にするには、このメンバー関数は、次の送信、受信すると、またはその両方ソケット。  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>パラメーター  
 *nHow*  
 操作の種類を示すフラグが許可されなく、次の列挙値を使用します。  
  
- **受信 = 0**  
  
- **送信 = 1**  
  
- **両方 = 2**  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、0 以外の場合0、および特定のエラー コードを呼び出すことによって取得されるそれ以外の場合[GetLastError](#getlasterror)します。 次のエラーは、このメンバー関数に適用されます。  
  
- 成功した成功 A [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)この API を使用する前に行う必要があります。  
  
- WSAENETDOWN、Windows ソケットの実装では、ネットワーク サブシステムが失敗したことが検出されました。  
  
- WSAEINVAL *nHow*が無効です。  
  
- WSAEINPROGRESS A が Windows ソケットのブロック操作が進行中です。  
  
- ソケットが接続には、(SOCK_STREAM のみ) が接続されています。  
  
- 切り離します記述子は、ソケットではありません。  
  
### <a name="remarks"></a>Remarks  
 `ShutDown` 受信と送信、またはその両方を無効にするすべての種類のソケットで使用されます。 場合*nHow*での受信が 0 の場合、ソケットは使用できません。 プロトコルの下位レイヤーへの影響はありません。  
  
 伝送制御プロトコル (TCP) では、TCP ウィンドウは変更されず、受信データと、ウィンドウがなくなるまで (応答しない) が受け入れられます。 ユーザー データグラム プロトコル (UDP) では、受信データグラムは受け入れし、キューに登録します。 いかなる場合で、ICMP パケットのエラーが生成されます。 場合*nHow*は 1 です。 その後送信は許可されません。 TCP ソケット、FIN が送信されます。 設定*nHow* 2 には、両方の送信を無効にし、前述のように受信します。  
  
 なお`ShutDown`はいない閉じる、ソケットとに、ソケットに接続されているリソースは解放されませんまで`Close`が呼び出されます。 アプリケーションは、シャット ダウン後にソケットを再利用することに依存する必要があります。 具体的には、Windows Sockets 実装は、の使用をサポートする必要はありません`Connect`このようなソケットでします。  
  
### <a name="example"></a>例  
  例をご覧ください[CAsyncSocket::OnReceive](#onreceive)します。  
  
##  <a name="socket"></a>  CASyncSocket::Socket  
 ソケットのハンドルを割り当てます。  
  
```  
BOOL Socket(
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    int nProtocolType = 0,  
    int nAddressFormat = PF_INET);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSocketType*  
 指定します`SOCK_STREAM`または`SOCK_DGRAM`します。  
  
 *lEvent*  
 アプリケーションが必要とするネットワーク イベントの組み合わせを指定するビットマスク。  
  
- `FD_READ`: 読み取り用の準備完了の通知を受信します。  
  
- `FD_WRITE`: 書き込みのための準備完了の通知を受信します。  
  
- `FD_OOB`: の帯域外のデータの追加の通知を受信するとしてください。  
  
- `FD_ACCEPT`: 着信接続の通知を受信します。  
  
- `FD_CONNECT`: 完全な接続の通知を受信します。  
  
- `FD_CLOSE`: ソケット クロージャの通知を受信します。  
  
 *nProtocolType*  
 指定されたアドレス ファミリに固有のソケットで使用するプロトコル。  
  
 *nAddressFormat*  
 アドレス ファミリの指定。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は、`TRUE` を返します。それ以外の場合は、`FALSE` を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ソケット ハンドルを割り当てます。 呼び出しません[CAsyncSocket::Bind](#bind)を呼び出す必要があるため、指定したアドレスにソケットをバインドする`Bind`以降を指定したアドレスにソケットをバインドします。 使用することができます[CAsyncSocket::SetSockOpt](#setsockopt)バインドされている前に、ソケット オプションを設定します。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSocket クラス](../../mfc/reference/csocket-class.md)   
 [CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
