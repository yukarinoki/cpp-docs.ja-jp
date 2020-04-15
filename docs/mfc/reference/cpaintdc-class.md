---
title: CペイントDCクラス
ms.date: 11/04/2016
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
ms.openlocfilehash: 55342b03454a6dba07bc10ea5f0464c34e0e8db3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374774"
---
# <a name="cpaintdc-class"></a>CペイントDCクラス

[CDC](../../mfc/reference/cdc-class.md)から派生したデバイス コンテキスト クラス。

## <a name="syntax"></a>構文

```
class CPaintDC : public CDC
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CペイントDC::CペイントDC](#cpaintdc)|指定した`CPaintDC`[CWnd](../../mfc/reference/cwnd-class.md)に接続されたを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CペイントDC:m_ps](#m_ps)|クライアント領域の描画に使用される[PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct)が含まれています。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CペイントDC:m_hWnd](#m_hwnd)|この`CPaintDC`オブジェクトがアタッチされている HWND。|

## <a name="remarks"></a>解説

これは、構築時に[CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint)を実行し、破壊時に[CWnd::EndPaintを実行します](../../mfc/reference/cwnd-class.md#endpaint)。

オブジェクト`CPaintDC`は[、WM_PAINT](/windows/win32/gdi/wm-paint)メッセージに応答する場合にのみ使用できます`OnPaint`。

の詳細`CPaintDC`については、「 デバイス[コンテキスト](../../mfc/device-contexts.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cpaintdccpaintdc"></a><a name="cpaintdc"></a>CペイントDC::CペイントDC

オブジェクトを`CPaintDC`構築し、描画用のアプリケーション ウィンドウを準備し、m_ps[メンバー変数](#m_ps)に[PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct)構造体を格納します。

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
オブジェクトが`CWnd`属するオブジェクトへの`CPaintDC`ポインター。

### <a name="remarks"></a>解説

Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) `CResourceException`呼び出しが失敗した場合は、(種類の) 例外がスローされます。 Windows が使用可能なすべてのデバイス コンテキストを既に割り当て済みの場合、デバイス コンテキストは使用できない可能性があります。 アプリケーションは、Windows でいつでも利用可能な 5 つの一般的な表示コンテキストを競合します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

## <a name="cpaintdcm_hwnd"></a><a name="m_hwnd"></a>CペイントDC:m_hWnd

この`HWND``CPaintDC`オブジェクトがアタッチされる。

```
HWND m_hWnd;
```

### <a name="remarks"></a>解説

*m_hWnd*は、HWND 型の保護された変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

## <a name="cpaintdcm_ps"></a><a name="m_ps"></a>CペイントDC:m_ps

`m_ps`型のパブリック メンバー変数[です](/windows/win32/api/winuser/ns-winuser-paintstruct)。

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>解説

これは`PAINTSTRUCT`[、CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint)によって渡され、入力されるのです。

`PAINTSTRUCT`には、オブジェクトに関連付けられたウィンドウのクライアント領域を描画するためにアプリケーションが使用する`CPaintDC`情報が含まれます。

デバイス コンテキスト ハンドルには、`PAINTSTRUCT`を使用してアクセスできます。 ただし、CDC から`m_hDC``CPaintDC`継承するメンバー変数を使用して、ハンドルに直接アクセスできます。

### <a name="example"></a>例

  [CPaintDC::m_hWnd](#m_hwnd)の例を参照してください。

## <a name="see-also"></a>関連項目

[MDI のサンプル](../../overview/visual-cpp-samples.md)<br/>
[CDCクラス](../../mfc/reference/cdc-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
