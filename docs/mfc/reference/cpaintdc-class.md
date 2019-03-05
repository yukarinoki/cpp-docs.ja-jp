---
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
ms.openlocfilehash: 5dbe08eae911433c256d3f8dd1f60dea2db9478c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274428"
---
# <a name="cpaintdc-class"></a>CPaintDC クラス

デバイス コンテキスト クラスから派生した[CDC](../../mfc/reference/cdc-class.md)します。

## <a name="syntax"></a>構文

```
class CPaintDC : public CDC
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CPaintDC::CPaintDC](#cpaintdc)|構築、`CPaintDC`を指定した接続[CWnd](../../mfc/reference/cwnd-class.md)します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPaintDC::m_ps](#m_ps)|含まれています、 [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct)クライアント領域を描画するために使用します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CPaintDC::m_hWnd](#m_hwnd)|この HWND`CPaintDC`オブジェクトがアタッチされています。|

## <a name="remarks"></a>Remarks

実行、 [cwnd::beginpaint](../../mfc/reference/cwnd-class.md#beginpaint)構築時に、 [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint)破棄時。

A`CPaintDC`オブジェクトに応答する場合にのみ使用できます、 [WM_PAINT](/windows/desktop/gdi/wm-paint)メッセージでは、通常、`OnPaint`メッセージ ハンドラー メンバー関数。

使用しての詳細については`CPaintDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC

構築、`CPaintDC`オブジェクト、描画、アプリケーション ウィンドウを準備し、格納、 [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct)構造体、[塗りつぶす対象となる](#m_ps)メンバー変数。

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
指す、`CWnd`先となるオブジェクト、`CPaintDC`オブジェクトが属しています。

### <a name="remarks"></a>Remarks

例外 (型の`CResourceException`) 場合にスローされる、Windows [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc)呼び出しは失敗します。 Windows が既に割り当てられているすべての利用可能なデバイス コンテキストの場合は、デバイス コンテキストを使用しないことがあります。 アプリケーションは、共通のディスプレイ コンテキスト Windows の任意の時点でご利用いただけますの 5 つの競合します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd

`HWND`この`CPaintDC`オブジェクトがアタッチされています。

```
HWND m_hWnd;
```

### <a name="remarks"></a>Remarks

*m_hWnd* HWND の種類の保護された変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

##  <a name="m_ps"></a>  CPaintDC::m_ps

`m_ps` 型のパブリック メンバー変数[PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct)します。

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>Remarks

`PAINTSTRUCT`に渡され、記入は[cwnd::beginpaint](../../mfc/reference/cwnd-class.md#beginpaint)します。

`PAINTSTRUCT`に関連付けられているウィンドウのクライアント領域を塗りつぶすために、アプリケーションが使用される情報が含まれています、`CPaintDC`オブジェクト。

使ってデバイス コンテキスト ハンドルにアクセスできることに注意してください、`PAINTSTRUCT`します。 ただしを使って直接ハンドルをアクセスすることができます、`m_hDC`メンバー変数を`CPaintDC`CDC から継承します。

### <a name="example"></a>例

  例をご覧ください[CPaintDC::m_hWnd](#m_hwnd)します。

## <a name="see-also"></a>関連項目

[MFC サンプル MDI](../../visual-cpp-samples.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
