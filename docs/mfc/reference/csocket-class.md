---
title: CSocket クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0bfaf418ec78a750f6030683801d00a1450364d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375604"
---
# <a name="csocket-class"></a>CSocket クラス
派生した`CAsyncSocket`、Windows ソケット API のをカプセル化を継承しよりも高い抽象化レベルを表す、`CAsyncSocket`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSocket::CSocket](#csocket)|`CSocket` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Csocket::attach](#attach)|アタッチ、**ソケット**へのハンドル、`CSocket`オブジェクト。|  
|[CSocket::CancelBlockingCall](#cancelblockingcall)|現在進行中のブロッキング呼び出しをキャンセルします。|  
|[CSocket::Create](#create)|ソケットを作成します。|  
|[CSocket::FromHandle](#fromhandle)|ポインターを返します、`CSocket`指定されたオブジェクト、**ソケット**を処理します。|  
|[CSocket::IsBlocking](#isblocking)|ブロッキング呼び出しが進行中かどうかを判断します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[種類](#onmessagepending)|ブロッキング呼び出しが完了の待機中にメッセージを保留中の処理に呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 `CSocket` クラスと連携`CSocketFile`と`CArchive`データの送受信を管理します。  
  
 A`CSocket`オブジェクトも用意されています、ブロックの同期の動作に不可欠である`CArchive`です。 など、機能をブロックして`Receive`、 `Send`、 `ReceiveFrom`、 `SendTo`、および`Accept`(から継承されたすべて`CAsyncSocket`)、戻ることはありません、`WSAEWOULDBLOCK`でエラー`CSocket`です。 代わりに、これらの関数は、操作が完了するまで待機します。 元の呼び出しが中止され、エラー、さらに、`WSAEINTR`場合`CancelBlockingCall`これらの関数の 1 つのブロックは中に呼び出されます。  
  
 使用する、`CSocket`オブジェクト、コンス トラクターを呼び出してを呼び出す`Create`を基になるを作成する`SOCKET`処理 (型`SOCKET`)。 既定のパラメーターの`Create`ストリーム ソケットを作成、ソケットを使用していない場合は、`CArchive`オブジェクト、データグラム ソケットを作成する代わりに、またはサーバー ソケットを作成する特定のポートにバインドするパラメーターを指定することができます。 使用して、クライアント ソケット接続`Connect`クライアント側と`Accept`サーバー側でします。 作成し、`CSocketFile`オブジェクトし、それに関連付ける、`CSocket`内のオブジェクト、`CSocketFile`コンス トラクターです。 次に、作成、`CArchive`を送信するためのオブジェクトと (必要に応じて)、データを受信するための 1 つ関連付けるし、これらを`CSocketFile`内のオブジェクト、`CArchive`コンス トラクターです。 通信の完了後に、破棄、 `CArchive`、 `CSocketFile`、および`CSocket`オブジェクト。 `SOCKET`データ型は、資料に記載されて[Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)です。  
  
 使用する場合`CArchive`で`CSocketFile`と`CSocket`、状況が発生する可能性があります、`CSocket::Receive`ループに入る (によって`PumpMessages(FD_READ)`) 要求されたバイト数を待機しています。 これは、Windows ソケット FD_READ 通知ごとに 1 つだけの受信呼び出しを許可するため、`CSocketFile`と`CSocket`FD_READ ごとの複数の受信呼び出しができるようにします。 表示された場合、FD_READ 読み取るデータがない場合に、アプリケーションがハングします。 別の FD_READ を取得しない場合、アプリケーションは、ソケット上で通信を停止します。  
  
 次のようにこの問題を解決できます。 `OnReceive`ソケット クラス、呼び出しのメソッド`CAsyncSocket::IOCtl(FIONREAD, ...)`を呼び出す前に、`Serialize`ソケットから読み取る必要なデータが 1 つの TCP パケット ネットワーク メディアの (最大転送単位のサイズを超える場合、メッセージ クラスのメソッド、通常 1096 バイト以上)。 使用可能なデータのサイズが必要なよりも小さい場合は、すべてのデータを受信して、読み取り操作を開始して待機します。  
  
 次の例では、`m_dwExpected`ユーザーが受信されるバイトのおおよその数です。 宣言している他の場所で、コード内と見なされます。  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]  
  
> [!NOTE]
>  静的にリンクされた MFC アプリケーションのセカンダリ スレッドで MFC ソケットを使用して、呼び出す必要があります`AfxSocketInit`ソケット ライブラリを初期化するためにソケットを使用する各スレッドにします。 既定では、`AfxSocketInit`プライマリ スレッドでのみ呼び出すことができます。  
  
 詳細については、次を参照してください[MFC における Windows ソケット](../../mfc/windows-sockets-in-mfc.md)、 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)、 [Windows ソケット: アーカイブ作業付きソケット](../../mfc/windows-sockets-how-sockets-with-archives-work.md)、 [。Windows ソケット: 動作シーケンス](../../mfc/windows-sockets-sequence-of-operations.md)、 [Windows ソケット: アーカイブを使用するソケットの例](../../mfc/windows-sockets-example-of-sockets-using-archives.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxsock.h  
  
##  <a name="attach"></a>  Csocket::attach  
 アタッチするには、このメンバー関数を呼び出す、`hSocket`へのハンドル、`CSocket`オブジェクト。  
  
```  
BOOL Attach(SOCKET hSocket);
```  
  
### <a name="parameters"></a>パラメーター  
 `hSocket`  
 ソケットへのハンドルが含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。  
  
### <a name="remarks"></a>コメント  
 **ソケット**ハンドルが、オブジェクトに格納されている[m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket)データ メンバーです。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]  
  
 [!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]  
  
##  <a name="cancelblockingcall"></a>  CSocket::CancelBlockingCall  
 現在実行中のブロッキング呼び出しをキャンセルするには、このメンバー関数を呼び出します。  
  
```  
void CancelBlockingCall();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、このソケットに対する未処理ブロッキング操作をキャンセルします。 元のブロッキング呼び出しは、エラーのため、できるだけ早く終了**WSAEINTR**です。  
  
 ブロッキング**接続**操作、Windows ソケットの実装が終了ブロッキング呼び出しが、できない可能性がありますソケット リソースは、接続が完了するまでにリリースされるとすぐに(および後リセットされる) またはタイムアウトです。これは、すぐに読み込もうと新しい (使用可能な sockets がない場合)、ソケットを開くか、同じピアに接続する場合にのみある可能性があります。  
  
 以外の任意の操作がキャンセル**Accept**不定状態で、ソケットのままにできます。 アプリケーションはソケットでを実行できることに依存する唯一の操作への呼び出しは、アプリケーションでは、ソケット上でブロッキング操作をキャンセルした場合**閉じる**、他の操作は一部の Windows ソケット実装です。 アプリケーションの最大の移植性を希望する場合、キャンセル後に操作の実行に依存しないように注意する必要があります。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)です。  
  
##  <a name="create"></a>  CSocket::Create  
 呼び出す、**作成**メンバー関数は、Windows ソケットを作成し、アタッチするソケット オブジェクトを構築した後です。  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSocketPort`  
 MFC にポートを選択する場合、または 0 で使用する特定のポートです。  
  
 `nSocketType`  
 **SOCK_STREAM**または**SOCK_DGRAM**です。  
  
 `lpszSocketAddress`  
 接続のソケットでは、「128.56.22.8」などのピリオドで区切られた数のネットワーク アドレスを含む文字列へのポインター。 渡す、 **NULL**このパラメーターを文字列、 **CSocket**インスタンスがすべてのネットワーク インターフェイス上のクライアント アクティビティを待機する必要があります。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。0、および特定のエラー コードを呼び出すことによって取得するそれ以外の場合`GetLastError`です。  
  
### <a name="remarks"></a>コメント  
 **作成**を呼び出して**バインド**指定されたアドレスにソケットをバインドします。 次のソケットの種類がサポートされています。  
  
- **SOCK_STREAM** sequenced、信頼性の高い、双方向、接続に基づくバイト ストリームを提供します。 インターネット アドレス ファミリ用には、伝送制御プロトコル (TCP) を使用します。  
  
- **SOCK_DGRAM**データグラム固定 (通常はわずか) の最大長のコネクションレス、信頼性の低いのバッファーをサポートしています。 インターネット アドレス ファミリ用には、ユーザー データグラム プロトコル (UDP) を使用します。 このオプションを使用する、ソケットを使用する必要がありますいないを`CArchive`オブジェクト。  
  
    > [!NOTE]
    >  **Accept**メンバー関数は、新しい空への参照を受け取ります`CSocket`オブジェクトをパラメーターとして。 呼び出す前に、このオブジェクトを構築する必要があります**Accept**です。 ただし、このソケット オブジェクトがスコープ接続は閉じられますなくなる場合。 呼び出す必要はありません**作成**この新しいソケット オブジェクト。  
  
 ストリームとデータグラム ソケットの詳細については、記事を参照してください[Windows ソケット: バック グラウンド](../../mfc/windows-sockets-background.md)、 [Windows ソケット: ポートとソケット アドレス](../../mfc/windows-sockets-ports-and-socket-addresses.md)、および[Windows ソケット: を使用する。アーカイブ付きソケットの](../../mfc/windows-sockets-using-sockets-with-archives.md)します。  
  
##  <a name="csocket"></a>  CSocket::CSocket  
 `CSocket` オブジェクトを構築します。  
  
```  
CSocket();
```  
  
### <a name="remarks"></a>コメント  
 構築後に呼び出す必要があります、**作成**メンバー関数。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)です。  
  
##  <a name="fromhandle"></a>  CSocket::FromHandle  
 ポインターを返します、`CSocket`オブジェクト。  
  
```  
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>パラメーター  
 `hSocket`  
 ソケットへのハンドルが含まれています。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CSocket`オブジェクト、または**NULL**がある場合ありません`CSocket`オブジェクトにアタッチ`hSocket`です。  
  
### <a name="remarks"></a>コメント  
 指定した場合、**ソケット**を処理する場合、`CSocket`オブジェクトがハンドルに関連付けられていない、メンバー関数を返します**NULL**され、一時的なオブジェクトは作成されません。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)です。  
  
##  <a name="isblocking"></a>  CSocket::IsBlocking  
 ブロッキング呼び出しが進行中のかどうかを確認するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsBlocking();
```  
  
### <a name="return-value"></a>戻り値  
 ソケットがブロッキングされている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)です。  
  
##  <a name="onmessagepending"></a>  種類  
 Windows からの特定のメッセージを確認して、ソケットに対応するには、この関数をオーバーライドします。  
  
```  
virtual BOOL OnMessagePending();
```  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これは、高度なオーバーライド可能です。  
  
 フレームワークによって`OnMessagePending`ソケットがアプリケーションに関心のあるメッセージを処理する機会を提供する Windows メッセージをポンプ中です。 使用する方法の例については`OnMessagePending`、記事を参照して[Windows ソケット: ソケット クラスから派生する](../../mfc/windows-sockets-deriving-from-socket-classes.md)です。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
