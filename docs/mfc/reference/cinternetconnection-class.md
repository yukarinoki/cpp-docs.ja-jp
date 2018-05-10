---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
dev_langs:
- C++
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07b269afce3ec0c3ef60e6cc37782fdea18260cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cinternetconnection-class"></a>関数クラス
インターネット サーバーへの接続を管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CInternetConnection : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](#cinternetconnection)|`CInternetConnection` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetConnection::GetContext](#getcontext)|この接続オブジェクトのコンテキスト ID を取得します。|  
|[CInternetConnection::GetServerName](#getservername)|接続に関連付けられているサーバーの名前を取得します。|  
|[CInternetConnection::GetSession](#getsession)|ポインターを取得、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)接続に関連付けられているオブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|インターネット セッションへのハンドル。|  
  
## <a name="remarks"></a>コメント  
 MFC クラスの基本クラスである[CFtpConnection](../../mfc/reference/cftpconnection-class.md)、 [CHttpConnection](../../mfc/reference/chttpconnection-class.md)、および[関数](../../mfc/reference/cgopherconnection-class.md)です。 これらの各クラスは、それぞれ、FTP、HTTP、または gopher サーバーと通信するための追加機能を提供します。  
  
 インターネット サーバーと直接通信する必要があります、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトおよび`CInternetConnection`オブジェクト。  
  
 WinInet クラスの動作に関する詳細については、記事を参照してください。 [wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cinternetconnection"></a>  CInternetConnection::CInternetConnection  
 このメンバー関数が呼び出されます、`CInternetConnection`オブジェクトを作成します。  
  
```  
CInternetConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSession`  
 ポインター、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。  
  
 `pstrServer`  
 サーバー名を含む文字列へのポインター。  
  
 `nPort`  
 この接続のインターネット ポートを識別する番号。  
  
 `dwContext`  
 コンテキスト識別子、`CInternetConnection`オブジェクト。 参照してください**解説**の詳細については`dwContext`します。  
  
### <a name="remarks"></a>コメント  
 呼び出さないように`CInternetConnection`考えてください。 代わりに、、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)を確立する接続の種類のメンバー関数。  
  
- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)  
  
- [代わりに](../../mfc/reference/cinternetsession-class.md#gethttpconnection)  
  
- [代わり](../../mfc/reference/cinternetsession-class.md#getgopherconnection)  
  
 既定値`dwContext`に MFC によって送信される、 `CInternetConnection`-オブジェクトから派生した、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、**です**-派生オブジェクト。 既定値を 1 に設定します。ただしで特定のコンテキスト識別子を割り当てることができますに明示的に、 [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession)接続のコンス トラクターです。 オブジェクトとその動作はしたコンテキスト ID と関連付けられます コンテキスト識別子に返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)いる識別されるオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="getcontext"></a>  CInternetConnection::GetContext  
 このセッションのコンテキスト ID を取得するには、このメンバー関数を呼び出します。  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コンテキストのアプリケーションによって割り当てられた id。  
  
### <a name="remarks"></a>コメント  
 コンテキスト ID が指定した[CInternetSession](../../mfc/reference/cinternetsession-class.md)に反映されると`CInternetConnection`- と[CInternetFile](../../mfc/reference/cinternetfile-class.md)の異なる方法で表示される関数の呼び出しに指定しない限り、派生クラス接続です。 コンテキスト ID が指定したオブジェクトのすべての操作に関連付けられているし、によって返される操作のステータス情報を識別する[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)です。  
  
 方法の詳細についての**GetContext**ユーザー状態情報を提供するには、他の wininet の基礎クラスとの連携が、記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)コンテキストの詳細については識別子です。  
  
##  <a name="getservername"></a>  CInternetConnection::GetServerName  
 このインターネット接続に関連付けられているサーバーの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetServerName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この接続オブジェクトは連携し、サーバーの名前。  
  
##  <a name="getsession"></a>  CInternetConnection::GetSession  
 ポインターを取得するには、このメンバー関数を呼び出す、`CInternetSession`この接続に関連付けられているオブジェクト。  
  
```  
CInternetSession* GetSession() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)インターネット接続オブジェクトに関連付けられているオブジェクト。  
  
##  <a name="operator_hinternet"></a>  CInternetConnection::operator HINTERNET  
 この演算子を使用して、現在のインターネット セッションの API レベルのハンドルを取得します。  
  
```  
operator HINTERNET() const;  
```  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



