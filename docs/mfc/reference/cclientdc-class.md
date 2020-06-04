---
title: CClientDC クラス
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: abe8a3220fd37a0375fcf37504c715edf4c6962e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352304"
---
# <a name="cclientdc-class"></a>CClientDC クラス

Windows 関数[GetDC](/windows/win32/api/winuser/nf-winuser-getdc)の呼び出しを構築時に、破棄時に[リリース DC](/windows/win32/api/winuser/nf-winuser-releasedc)を処理します。

## <a name="syntax"></a>構文

```
class CClientDC : public CDC
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[C クライアントDC::CクライアントDC](#cclientdc)|に接続された`CClientDC`オブジェクトを構築します`CWnd`。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[クライアントDC:m_hWnd](#m_hwnd)|これが`CClientDC`有効なウィンドウの HWND。|

## <a name="remarks"></a>解説

つまり、`CClientDC`オブジェクトに関連付けられているデバイス コンテキストは、ウィンドウのクライアント領域です。

の詳細については、「 `CClientDC`[デバイス コンテキスト](../../mfc/device-contexts.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cclientdccclientdc"></a><a name="cclientdc"></a>C クライアントDC::CクライアントDC

`CClientDC` *pWnd*が指す[CWnd](../../mfc/reference/cwnd-class.md)のクライアント領域にアクセスするオブジェクトを構築します。

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
デバイス コンテキスト オブジェクトがアクセスするクライアント領域のウィンドウ。

### <a name="remarks"></a>解説

コンストラクターは、Windows 関数[GetDC](/windows/win32/api/winuser/nf-winuser-getdc)を呼び出します。

Windows`GetDC`呼び出`CResourceException`しが失敗した場合は、(種類の) 例外がスローされます。 Windows が使用可能なすべてのデバイス コンテキストを既に割り当て済みの場合、デバイス コンテキストは使用できない可能性があります。 アプリケーションは、Windows でいつでも利用可能な 5 つの一般的な表示コンテキストを競合します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

## <a name="cclientdcm_hwnd"></a><a name="m_hwnd"></a>クライアントDC:m_hWnd

オブジェクト`HWND`の`CWnd`構築に使用するポインターの`CClientDC`。

```
HWND m_hWnd;
```

### <a name="remarks"></a>解説

*m_hWnd*は保護された変数です。

### <a name="example"></a>例

  [「C クライアントDC::CClientDC」](#cclientdc)の例を参照してください。

## <a name="see-also"></a>関連項目

[MDI のサンプル](../../overview/visual-cpp-samples.md)<br/>
[CDCクラス](../../mfc/reference/cdc-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CDCクラス](../../mfc/reference/cdc-class.md)
