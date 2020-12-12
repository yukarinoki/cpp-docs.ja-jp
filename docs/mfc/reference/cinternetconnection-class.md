---
description: '詳細情報: CInternetConnection クラス'
title: CInternetConnection クラス
ms.date: 11/04/2016
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
ms.openlocfilehash: 2ae869e8cbf3bbfb3ce19e78088a465ae1d6aa65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143547"
---
# <a name="cinternetconnection-class"></a>CInternetConnection クラス

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
|[CInternetConnection:: GetContext](#getcontext)|この接続オブジェクトのコンテキスト ID を取得します。|
|[CInternetConnection:: GetServerName](#getservername)|接続に関連付けられているサーバーの名前を取得します。|
|[CInternetConnection:: GetSession](#getsession)|接続に関連付けられている [CInternetSession](../../mfc/reference/cinternetsession-class.md) オブジェクトへのポインターを取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CInternetConnection:: operator HINTERNET](#operator_hinternet)|インターネットセッションを処理するハンドル。|

## <a name="remarks"></a>解説

これは、MFC クラス [CFtpConnection](../../mfc/reference/cftpconnection-class.md)、 [CHttpConnection](../../mfc/reference/chttpconnection-class.md)、および [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)の基底クラスです。 これらの各クラスには、それぞれの FTP、HTTP、または gopher サーバーと通信するための追加機能が用意されています。

インターネットサーバーと直接通信するには、 [CInternetSession](../../mfc/reference/cinternetsession-class.md) オブジェクトとオブジェクトが必要 `CInternetConnection` です。

WinInet クラスのしくみの詳細については、「 [wininet を使用したインターネットプログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>要件

**ヘッダー:** afxinet.h

## <a name="cinternetconnectioncinternetconnection"></a><a name="cinternetconnection"></a> CInternetConnection::CInternetConnection

このメンバー関数は、オブジェクトが作成されるときに呼び出され `CInternetConnection` ます。

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*pSession*<br/>
[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトへのポインター。

*pstrServer*<br/>
サーバー名を格納している文字列へのポインター。

*nPort*<br/>
この接続のインターネットポートを識別する番号。

*dwContext*<br/>
オブジェクトのコンテキスト識別子 `CInternetConnection` 。 *DwContext* の詳細については、「**解説**」を参照してください。

### <a name="remarks"></a>解説

自分では呼び出さないでください `CInternetConnection` 。代わりに、確立する接続の種類に対応する [CInternetSession](../../mfc/reference/cinternetsession-class.md) メンバー関数を呼び出してください。

- [CInternetSession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

*DwContext* の既定値は、 `CInternetConnection` **internetconnection** 派生オブジェクトを作成した [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトから派生したオブジェクトに、MFC によって送信されます。 既定値は1に設定されています。ただし、接続の [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) コンストラクターに特定のコンテキスト識別子を明示的に割り当てることができます。 オブジェクトとそれが実行する作業は、そのコンテキスト ID に関連付けられます。 コンテキスト識別子は、 [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) に返され、識別されたオブジェクトの状態を提供します。 コンテキスト識別子の詳細については、「 [インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md) 」を参照してください。

## <a name="cinternetconnectiongetcontext"></a><a name="getcontext"></a> CInternetConnection:: GetContext

このメンバー関数を呼び出して、このセッションのコンテキスト ID を取得します。

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>戻り値

アプリケーションによって割り当てられたコンテキスト ID。

### <a name="remarks"></a>解説

コンテキスト ID は、最初は [CInternetSession](../../mfc/reference/cinternetsession-class.md) で指定され、 `CInternetConnection` 接続を開く関数の呼び出しで別に指定されていない限り、と [CInternetFile](../../mfc/reference/cinternetfile-class.md)の派生クラスに反映されます。 コンテキスト ID は、指定されたオブジェクトのすべての操作に関連付けられ、 [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)によって返される操作の状態情報を識別します。

が `GetContext` 他の WinInet クラスと連携してユーザーステータス情報を提供する方法の詳細については、「 [インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md) 」を参照してください。

## <a name="cinternetconnectiongetservername"></a><a name="getservername"></a> CInternetConnection:: GetServerName

このメンバー関数を呼び出して、このインターネット接続に関連付けられているサーバーの名前を取得します。

```
CString GetServerName() const;
```

### <a name="return-value"></a>戻り値

この接続オブジェクトが使用しているサーバーの名前。

## <a name="cinternetconnectiongetsession"></a><a name="getsession"></a> CInternetConnection:: GetSession

このメンバー関数を呼び出して、 `CInternetSession` この接続に関連付けられているオブジェクトへのポインターを取得します。

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>戻り値

このインターネット接続オブジェクトに関連付けられている [CInternetSession](../../mfc/reference/cinternetsession-class.md) オブジェクトへのポインター。

## <a name="cinternetconnectionoperator-hinternet"></a><a name="operator_hinternet"></a> CInternetConnection:: operator HINTERNET

現在のインターネットセッションの API レベルハンドルを取得するには、この演算子を使用します。

```
operator HINTERNET() const;
```

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
