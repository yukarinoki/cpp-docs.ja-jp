---
description: '詳細情報: CPaintDC クラス'
title: CPaintDC クラス
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
ms.openlocfilehash: cb8f3b81615390ab6af8e9a244a95f91a3b3f96c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345213"
---
# <a name="cpaintdc-class"></a>CPaintDC クラス

[CDC](../../mfc/reference/cdc-class.md)から派生したデバイスコンテキストクラス。

## <a name="syntax"></a>構文

```
class CPaintDC : public CDC
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CPaintDC:: CPaintDC](#cpaintdc)|`CPaintDC`指定した[CWnd](../../mfc/reference/cwnd-class.md)に接続されているを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPaintDC:: m_ps](#m_ps)|クライアント領域の描画に使用される [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct) を格納します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CPaintDC:: m_hWnd](#m_hwnd)|このオブジェクトがアタッチされている HWND `CPaintDC` 。|

## <a name="remarks"></a>解説

このメソッドは、構築時に [cwnd:: BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) を実行し、破棄時に [Cwnd:: endpaint](../../mfc/reference/cwnd-class.md#endpaint) を実行します。

オブジェクトは、 `CPaintDC` [WM_PAINT](/windows/win32/gdi/wm-paint) メッセージに応答する場合にのみ使用できます。通常は、 `OnPaint` メッセージハンドラーのメンバー関数で指定します。

の使用方法の詳細につい `CPaintDC` ては、「 [デバイスコンテキスト](../../mfc/device-contexts.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cpaintdccpaintdc"></a><a name="cpaintdc"></a> CPaintDC:: CPaintDC

オブジェクトを構築し `CPaintDC` 、アプリケーションウィンドウに描画を準備し、 [m_ps](#m_ps)のメンバー変数に[PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct)構造体を格納します。

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
`CWnd`オブジェクトが属するオブジェクトを指し `CPaintDC` ます。

### <a name="remarks"></a>解説

`CResourceException`Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc)の呼び出しが失敗した場合、例外 (型) がスローされます。 Windows によって使用可能なデバイスコンテキストがすべて既に割り当てられている場合、デバイスコンテキストを使用できない可能性があります。 アプリケーションは、Windows で任意の時点で使用可能な5つの共通表示コンテキストを競合しています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

## <a name="cpaintdcm_hwnd"></a><a name="m_hwnd"></a> CPaintDC:: m_hWnd

`HWND`この `CPaintDC` オブジェクトがアタッチされる。

```
HWND m_hWnd;
```

### <a name="remarks"></a>解説

*m_hWnd* は hWnd 型の保護された変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

## <a name="cpaintdcm_ps"></a><a name="m_ps"></a> CPaintDC:: m_ps

`m_ps` は、 [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct)型のパブリックメンバー変数です。

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>解説

これは、 `PAINTSTRUCT` [CWnd:: beginpaint](../../mfc/reference/cwnd-class.md#beginpaint)によって渡され、入力されるです。

には、 `PAINTSTRUCT` オブジェクトに関連付けられたウィンドウのクライアント領域を描画するためにアプリケーションが使用する情報が含まれてい `CPaintDC` ます。

デバイスコンテキストハンドルには、を介してアクセスできることに注意して `PAINTSTRUCT` ください。 ただし、 `m_hDC` CDC から継承したメンバー変数を介して、ハンドルに直接アクセスでき `CPaintDC` ます。

### <a name="example"></a>例

  [CPaintDC:: m_hWnd](#m_hwnd)の例を参照してください。

## <a name="see-also"></a>関連項目

[MFC のサンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
