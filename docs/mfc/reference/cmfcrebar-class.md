---
description: '詳細情報: CMFCReBar クラス'
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
ms.openlocfilehash: fcfad39ddb9c5f3bdacc5a06ebb65d22bc8c7a4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289830"
---
# <a name="cmfcrebar-class"></a>CMFCReBar クラス

`CMFCReBar`オブジェクトは、rebar コントロールのレイアウト、永続性、および状態に関する情報を提供するコントロールバーです。
詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCReBar : public CPane
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCReBar:: AddBar](#addbar)|バンドを rebar に追加します。|
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|( [Cbasepane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout)をオーバーライドします)。|
|[CMFCReBar:: CanFloat](#canfloat)|( [Cbasepane:: CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)をオーバーライドします)。|
|[CMFCReBar:: Create](#create)|Rebar コントロールを作成し、オブジェクトにアタッチし `CMFCReBar` ます。|
|[CMFCReBar:: EnableDocking](#enabledocking)|( [Cbasepane:: EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)をオーバーライドします)。|
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|基になる [Crebarctrl](../../mfc/reference/crebarctrl-class.md) コモンコントロールへの直接アクセスを提供します。|
|[CMFCReBar:: OnShowControlBarMenu](#onshowcontrolbarmenu)|( [CPane:: OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu)をオーバーライドします)。|
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|( [CWnd:: OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest)をオーバーライドします)。|
|[CMFCReBar:: OnUpdateCmdUI](#onupdatecmdui)|( [Cbasepane:: OnUpdateCmdUI](cbasepane-class.md)をオーバーライドします)。|
|[CMFCReBar:: Set Alignment](#setpanealignment)|( [Cbasepane:: Setpane alignment](../../mfc/reference/cbasepane-class.md#setpanealignment)をオーバーライドします)。|

## <a name="remarks"></a>解説

オブジェクトには `CMFCReBar` 、さまざまな子ウィンドウを含めることができます。 これには、エディットボックス、ツールバー、およびリストボックスが含まれます。 Rebar のサイズはプログラムで変更することも、ユーザーがグリップバーをドラッグして rebar のサイズを手動で変更することもできます。 Rebar オブジェクトの背景を任意のビットマップに設定することもできます。

Rebar オブジェクトは、toolbar オブジェクトと同様に動作します。 Rebar コントロールには1つ以上のバンドを含めることができ、各バンドにはグリップバー、ビットマップ、テキストラベル、および子ウィンドウを含めることができます。

## <a name="example"></a>例

`CMFCReBar` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、rebar コントロールを作成し、バンドを追加する方法を示します。 バンドは内部ツールバーとして機能します。 このコードスニペットは、 [Rebar テストサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)\
└ &nbsp; [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [Cbasepane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxRebar

## <a name="cmfcrebaraddbar"></a><a name="addbar"></a> CMFCReBar:: AddBar

バンドを rebar に追加します。

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
[入力、出力]Rebar に挿入される子ウィンドウへのポインター。 参照されるオブジェクトには、 **WS_CHILD** ウィンドウスタイルが必要です。

*pszText*<br/>
からRebar に表示するテキストを指定します。 テキストは子ウィンドウの一部ではありません。 代わりに、rebar 自体に表示されます。

*.pbmp*<br/>
[入力、出力]Rebar の背景に表示されるビットマップを指定します。

*dwStyle*<br/>
からバンドに適用するスタイルを格納します。 バンドスタイルの完全な一覧については、 `fStyle` Windows SDK のドキュメントの [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) 構造にあるの説明を参照してください。

*clrFore*<br/>
からRebar の前景色を表します。

*clrBack*<br/>
からRebar の背景色を表します。

### <a name="return-value"></a>戻り値

バンドが rebar; に正常に追加された場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcrebarcreate"></a><a name="create"></a> CMFCReBar:: Create

Rebar コントロールを作成し、 [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) オブジェクトにアタッチします。

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
からRebar コントロールのスタイルを指定します。 既定のスタイル値は **RBS_BANDBORDERS** です。これにより、rebar コントロールの隣接するバンドを区切るためのナロー線が表示されます。 有効なスタイルの一覧については、Windows SDK ドキュメントの「 [Rebar コントロールスタイル](/windows/win32/Controls/rebar-control-styles) 」を参照してください。

*dwStyle*<br/>
からRebar コントロールのウィンドウスタイル。 有効なスタイルの一覧については、「 [ウィンドウスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)」を参照してください。

*nID*<br/>
からRebar の子ウィンドウ ID。

### <a name="return-value"></a>戻り値

Rebar が正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcrebargetrebarctrl"></a><a name="getrebarctrl"></a> CMFCReBar::GetReBarCtrl

オブジェクトの基になるコモンコントロールへの直接アクセスを提供し `CReBarCtrl` `CMFCReBar` ます。

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>戻り値

基になるオブジェクトへの参照 `CReBarCtrl` 。

### <a name="remarks"></a>解説

Rebar をカスタマイズするときに、Windows の rebar コモンコントロール機能を利用するには、このメソッドを呼び出します。

## <a name="cmfcrebarcalcfixedlayout"></a><a name="calcfixedlayout"></a> CMFCReBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

から *Bstretch*<br/>
から *bHorz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebarcanfloat"></a><a name="canfloat"></a> CMFCReBar:: CanFloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebarenabledocking"></a><a name="enabledocking"></a> CMFCReBar:: EnableDocking

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

から *dwDockStyle*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcrebargetrebarbandinfosize"></a><a name="getrebarbandinfosize"></a> CMFCReBar::GetReBarBandInfoSize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a> CMFCReBar:: OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>パラメーター

から *CPoint*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebarontoolhittest"></a><a name="ontoolhittest"></a> CMFCReBar::OnToolHitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>パラメーター

から *ポイント*<br/>
から *pTI*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebaronupdatecmdui"></a><a name="onupdatecmdui"></a> CMFCReBar:: OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>パラメーター

から *Ptarget*<br/>
から *Bdisableifnohndler*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcrebarsetpanealignment"></a><a name="setpanealignment"></a> CMFCReBar:: Set Alignment

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

から *dwAlignment*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl クラス](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane クラス](../../mfc/reference/cpane-class.md)
