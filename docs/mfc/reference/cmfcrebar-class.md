---
title: CMFCReBar クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
ms.openlocfilehash: 7776bf504d502feee8ef51949b8adc8e44f94c8e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772294"
---
# <a name="cmfcrebar-class"></a>CMFCReBar クラス

A`CMFCReBar`オブジェクトは、コントロール バー レイアウト、永続化、および rebar コントロールの状態情報を提供します。
詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。
## <a name="syntax"></a>構文

```
class CMFCReBar : public CPane
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCReBar::AddBar](#addbar)|Rebar バンドに追加します。|
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(上書き[cbasepane::calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout))。|
|[CMFCReBar::CanFloat](#canfloat)|(上書き[CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat))。|
|[CMFCReBar::Create](#create)|Rebar コントロールを作成し、それにアタッチします、`CMFCReBar`オブジェクト。|
|[CMFCReBar::EnableDocking](#enabledocking)|(上書き[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking))。|
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|基になるに直接アクセスできる[crebarctrl の比較](../../mfc/reference/crebarctrl-class.md)コモン コントロール。|
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(上書き[cpane::onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu))。|
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(上書き[CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest))。|
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(上書き[CBasePane::OnUpdateCmdUI](cbasepane-class.md))。|
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(上書き[CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment))。|

## <a name="remarks"></a>Remarks

A`CMFCReBar`オブジェクトは、さまざまな子ウィンドウを含めることができます。 これには、エディット ボックス、ツールバー、およびリスト ボックスが含まれます。 Rebar サイズを変更できるプログラムで、または、ユーザーがグリッパー バーをドラッグして、rebar を手動でサイズ変更します。 好みのビットマップに rebar オブジェクトの背景を設定することもできます。

Rebar オブジェクトは、ツールバーのオブジェクトと同様に動作します。 Rebar コントロールは、1 つまたは複数のバンドを含めることができ、各バンドはグリッパー バー、ビットマップ、テキスト ラベル、および子ウィンドウに含めることができます。

## <a name="example"></a>例

`CMFCReBar` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、rebar コントロールを作成し、バンドを追加する方法を示します。 バンドが内部ツールバーとして機能します。 このコード スニペットの一部、 [Rebar のテスト サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRebar.h

##  <a name="addbar"></a>  CMFCReBar::AddBar

Rebar バンドに追加します。

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
[入力、出力]Rebar に挿入するのには、子ウィンドウへのポインター。 参照先オブジェクトには、 **WS_CHILD**ウィンドウ スタイル。

*pszText*<br/>
[in]Rebar に表示されるテキストを指定します。 子ウィンドウの一部でないテキスト。 代わりに、rebar 自体に表示されます。

*pbmp*<br/>
[入力、出力]Rebar の背景に表示されるビットマップを指定します。

*dwStyle*<br/>
[in]Band に適用するスタイルが含まれています。 バンド スタイルの完全な一覧の説明を参照してください。`fStyle`で、 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) 、Windows SDK ドキュメントの構造体。

*clrFore*<br/>
[in]Rebar の前景色を表します。

*clrBack*<br/>
[in]Rebar の背景色を表します。

### <a name="return-value"></a>戻り値

バンドが rebar; に正常に追加する場合は TRUE。それ以外の場合、FALSE です。

##  <a name="create"></a>  CMFCReBar::Create

Rebar コントロールを作成し、それにアタッチします、 [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)オブジェクト。

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
[入力、出力]この rebar コントロールの親ウィンドウへのポインター。

*dwCtrlStyle*<br/>
[in]Rebar コントロールのスタイルを指定します。 既定のスタイルの値は**RBS_BANDBORDERS**これが表示されますが、rebar コントロールでの隣接するバンドの区切り線を絞り込みます。 有効なスタイルの一覧は、次を参照してください。 [Rebar コントロールのスタイル](/windows/desktop/Controls/rebar-control-styles)Windows SDK のドキュメント。

*dwStyle*<br/>
[in]Rebar コントロールのウィンドウ スタイル。 有効なスタイルの一覧は、[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を参照してください。

*nID*<br/>
[in]Rebar の子ウィンドウの id。

### <a name="return-value"></a>戻り値

Rebar が正常に作成された場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="getrebarctrl"></a>  CMFCReBar::GetReBarCtrl

直接アクセスを提供します。`CReBarCtrl`の基になる一般的なコントロール`CMFCReBar`オブジェクト。

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>戻り値

基になるへの参照を`CReBarCtrl`オブジェクト。

### <a name="remarks"></a>Remarks

Rebar をカスタマイズするときの Windows rebar の一般的な管理機能を利用するには、このメソッドを呼び出します。

##  <a name="calcfixedlayout"></a>  CMFCReBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

[in]*bStretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="canfloat"></a>  CMFCReBar::CanFloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="enabledocking"></a>  CMFCReBar::EnableDocking

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

[in]*dwDockStyle*<br/>

### <a name="remarks"></a>Remarks

##  <a name="getrebarbandinfosize"></a>  CMFCReBar::GetReBarBandInfoSize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onshowcontrolbarmenu"></a>  CMFCReBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>パラメーター

[in]*CPoint*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="ontoolhittest"></a>  CMFCReBar::OnToolHitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>パラメーター

[in]*ポイント*<br/>
[in]*pTI*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onupdatecmdui"></a>  CMFCReBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>パラメーター

[in]*pTarget*<br/>
[in]*持たず*<br/>

### <a name="remarks"></a>Remarks

##  <a name="setpanealignment"></a>  CMFCReBar::SetPaneAlignment

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

[in] *dwAlignment*<br/>

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl クラス](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane クラス](../../mfc/reference/cpane-class.md)
