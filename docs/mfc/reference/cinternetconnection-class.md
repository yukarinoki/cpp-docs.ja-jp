---
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
ms.openlocfilehash: 6649986f279e010a833b31157922cb4fd1ea8613
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372424"
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
|[インターネット接続::インターネット接続](#cinternetconnection)|`CInternetConnection` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[接続を取得します。](#getcontext)|この接続オブジェクトのコンテキスト ID を取得します。|
|[接続を取得します。](#getservername)|接続に関連付けられているサーバーの名前を取得します。|
|[インターネット接続::ゲットセッション](#getsession)|接続に関連付けられている[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトへのポインターを取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[インターネット接続::オペレーター H インターネット](#operator_hinternet)|インターネット セッションへのハンドル。|

## <a name="remarks"></a>解説

これは、MFC クラス[CFtpConnection](../../mfc/reference/cftpconnection-class.md) [、CHttp 接続](../../mfc/reference/chttpconnection-class.md)、および[CGopherConnection](../../mfc/reference/cgopherconnection-class.md)の基本クラスです。 これらの各クラスは、それぞれの FTP、HTTP、または gopher サーバーと通信するための追加機能を提供します。

インターネット サーバーと直接通信するには[、CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトとオブジェクトが必要です`CInternetConnection`。

WinInet クラスの動作の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cinternetconnectioncinternetconnection"></a><a name="cinternetconnection"></a>インターネット接続::インターネット接続

このメンバー関数は、オブジェクトが`CInternetConnection`作成されるときに呼び出されます。

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*セッション*<br/>
[オブジェクト](../../mfc/reference/cinternetsession-class.md)へのポインター。

*を行う*<br/>
サーバー名を含む文字列へのポインター。

*nポート*<br/>
この接続のインターネット ポートを識別する番号。

*dw コンテキスト*<br/>
`CInternetConnection`オブジェクトのコンテキスト識別子。 *dwContext*の詳細については **、「解説**」を参照してください。

### <a name="remarks"></a>解説

あなたは決して`CInternetConnection`自分自身を呼び出すことはありません。代わりに、確立する接続の種類に対して[CInternetSession](../../mfc/reference/cinternetsession-class.md)メンバー関数を呼び出します。

- [インターネットセッション::ゲットFtp接続](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [インターネットセッション::取得Http接続](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [インターネットセッション::ゲットゴファーコネクション](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

*dwContext*の既定値は、MFC によって`CInternetConnection`**、インターネット接続**派生オブジェクトを作成した[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトから派生オブジェクトに送信されます。 デフォルトは 1 に設定されています。ただし、接続の[CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession)コンストラクターで特定のコンテキスト識別子を明示的に割り当てることができます。 オブジェクトとオブジェクトが行うすべての作業は、そのコンテキスト ID に関連付けられます。 コンテキスト識別子は、識別されるオブジェクトのステータスを提供するために[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

## <a name="cinternetconnectiongetcontext"></a><a name="getcontext"></a>接続を取得します。

このセッションのコンテキスト ID を取得します。

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>戻り値

アプリケーションに割り当てられたコンテキスト ID。

### <a name="remarks"></a>解説

コンテキスト ID は、もともと[CInternetSession](../../mfc/reference/cinternetsession-class.md)で指定`CInternetConnection`され、接続を開く関数の呼び出しで異なる方法で指定されていない限り、 - および[CInternetFile](../../mfc/reference/cinternetfile-class.md)派生クラスに伝搬されます。 コンテキスト ID は、指定されたオブジェクトの操作に関連付けられており[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)によって返される操作の状態情報を識別します。

他の WinInet クラスと連携してユーザーの状態情報を提供する方法`GetContext`の詳細については、コンテキスト識別子の詳細については、「[インターネットファースト ステップ : WinInet」](../../mfc/wininet-basics.md)を参照してください。

## <a name="cinternetconnectiongetservername"></a><a name="getservername"></a>接続を取得します。

このメンバー関数を呼び出して、このインターネット接続に関連付けられているサーバーの名前を取得します。

```
CString GetServerName() const;
```

### <a name="return-value"></a>戻り値

この接続オブジェクトが使用しているサーバーの名前。

## <a name="cinternetconnectiongetsession"></a><a name="getsession"></a>インターネット接続::ゲットセッション

このメンバー関数を呼び出して、この`CInternetSession`接続に関連付けられているオブジェクトへのポインターを取得します。

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>戻り値

このインターネット接続オブジェクトに関連付けられた[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトへのポインター。

## <a name="cinternetconnectionoperator-hinternet"></a><a name="operator_hinternet"></a>インターネット接続::オペレーター H インターネット

この演算子を使用して、現在のインターネット セッションの API レベルのハンドルを取得します。

```
operator HINTERNET() const;
```

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
