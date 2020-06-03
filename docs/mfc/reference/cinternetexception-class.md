---
title: CInternetException クラス
ms.date: 11/04/2016
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
ms.openlocfilehash: b0239afa2b984ccf93d661ec11f11013c89fd912
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372403"
---
# <a name="cinternetexception-class"></a>CInternetException クラス

インターネット操作に関する例外条件を表します。

## <a name="syntax"></a>構文

```
class CInternetException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::Cインターネット例外](#cinternetexception)|`CInternetException` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[インターネット例外::m_dwContext](#m_dwcontext)|例外の原因となった操作に関連付けられているコンテキスト値。|
|[インターネット例外::m_dwError](#m_dwerror)|例外の原因となったエラー。|

## <a name="remarks"></a>解説

この`CInternetException`クラスには、例外に関連付けられたエラー コードを保持し、もう 1 つはエラーに関連付けられたインターネット アプリケーションのコンテキスト識別子を保持する 2 つのパブリック データ メンバーが含まれます。

インターネット アプリケーションのコンテキスト識別子の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cinternetexceptioncinternetexception"></a><a name="cinternetexception"></a>::Cインターネット例外

このメンバー関数は、オブジェクトが`CInternetException`作成されるときに呼び出されます。

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>パラメーター

*エラー*<br/>
例外の原因となったエラー。

### <a name="remarks"></a>解説

をスローするには、MFC グローバル関数[AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception)を呼び出します。

## <a name="cinternetexceptionm_dwcontext"></a><a name="m_dwcontext"></a>インターネット例外::m_dwContext

関連するインターネット操作に関連付けられているコンテキスト値。

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>解説

コンテキスト識別子はもともと[CInternetSession](../../mfc/reference/cinternetsession-class.md)で指定され、MFC によって[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)クラスと[CInternetFile](../../mfc/reference/cinternetfile-class.md)派生クラスに渡されます。 このデフォルトをオーバーライドして、任意の*dwContext*パラメーターに任意の値を割り当てることができます。 *dwContext*は、指定されたオブジェクトの任意の操作に関連付けられます。 *dwContext*は[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)によって返される操作の状態情報を識別します。

## <a name="cinternetexceptionm_dwerror"></a><a name="m_dwerror"></a>インターネット例外::m_dwError

例外の原因となったエラー。

```
DWORD m_dwError;
```

### <a name="remarks"></a>解説

このエラー値は、WINERROR で見つかったシステム エラー コードである可能性があります。H、または WININET からのエラー値。H。

Win32 エラー コードの一覧については、「[エラー コード](/windows/win32/Debug/system-error-codes)」を参照してください。 インターネット固有のエラー メッセージの一覧については、を参照してください。 両方のトピックは、Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[クラスの例外](../../mfc/reference/cexception-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスの例外](../../mfc/reference/cexception-class.md)
