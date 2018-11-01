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
ms.openlocfilehash: e89293d7b7803cf661bce7a91ea6df72b9a06122
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531574"
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
|[CInternetException::CInternetException](#cinternetexception)|`CInternetException` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CInternetException::m_dwContext](#m_dwcontext)|例外の原因となった操作に関連付けられたコンテキストの値です。|
|[CInternetException::m_dwError](#m_dwerror)|例外の原因となったエラー。|

## <a name="remarks"></a>Remarks

`CInternetException`クラスには、2 つのパブリック データ メンバーが含まれています。 例外に関連付けられたエラー コードを保持する 1 つと、他のエラーに関連付けられているインターネット アプリケーションのコンテキスト識別子を保持します。

インターネット アプリケーションのコンテキスト識別子の詳細については、記事を参照してください。[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

##  <a name="cinternetexception"></a>  CInternetException::CInternetException

このメンバー関数が呼び出されます、`CInternetException`オブジェクトが作成されます。

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>パラメーター

*dwError*<br/>
例外の原因となったエラー。

### <a name="remarks"></a>Remarks

MFC のグローバル関数を呼び出し、CInternetException をスローする[AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception)します。

##  <a name="m_dwcontext"></a>  CInternetException::m_dwContext

関連するインターネット操作に関連付けられたコンテキストの値です。

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Remarks

コンテキスト識別子がで指定された最初[CInternetSession](../../mfc/reference/cinternetsession-class.md)に MFC によって渡されると[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- と[CInternetFile](../../mfc/reference/cinternetfile-class.md)-クラスを派生します。 この既定をオーバーライドして割り当てる*独自*パラメーターの値。 *独自*指定したオブジェクトのすべての操作に関連付けられています。 *独自*によって返される操作の状態情報を識別する[対応](../../mfc/reference/cinternetsession-class.md#onstatuscallback)します。

##  <a name="m_dwerror"></a>  CInternetException::m_dwError

例外の原因となったエラー。

```
DWORD m_dwError;
```

### <a name="remarks"></a>Remarks

このエラーの値には、システムが可能性があります WINERROR で見つかった、エラー コード。H、または WININET エラー値。H.

Win32 エラー コードの一覧は、次を参照してください。[エラーコード](/windows/desktop/Debug/system-error-codes)します。 インターネットに固有のエラー メッセージの一覧を参照してください。 両方のトピックでは、Windows SDK にします。

## <a name="see-also"></a>関連項目

[CException クラス](../../mfc/reference/cexception-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CException クラス](../../mfc/reference/cexception-class.md)
