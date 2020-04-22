---
title: クラス
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
ms.openlocfilehash: 409c97aba64c97ecf0443d14a70848cc298a44ba
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750003"
---
# <a name="cmfcrebar-class"></a>クラス

オブジェクト`CMFCReBar`は、Rebar コントロールのレイアウト、永続性、および状態情報を提供するコントロール バーです。
詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCReBar : public CPane
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロール バー::追加バー](#addbar)|帯をリバーに追加します。|
|[コントロールバー::計算式レイアウト](#calcfixedlayout)|(CBase ペインをオーバーライド[します::計算固定レイアウト](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCReBar::缶詰](#canfloat)|[(CBasePane をオーバーライドします::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[作成](#create)|Rebar コントロールを作成し、オブジェクトに`CMFCReBar`アタッチします。|
|[ドッキングを有効にする](#enabledocking)|[(CBasePane をオーバーライドします::ドッキングを有効にします](../../mfc/reference/cbasepane-class.md#enabledocking)。|
|[を返します。](#getrebarbandinfosize)||
|[を返します。](#getrebarctrl)|基になる[CReBarCtrl](../../mfc/reference/crebarctrl-class.md)コモン コントロールに直接アクセスできます。|
|[コントロールバーメニューを表示します。](#onshowcontrolbarmenu)|(CPane をオーバーライド[します::オンショーコントロールバーメニュー](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[コントロールバー::オンツールヒットテスト](#ontoolhittest)|[(CWnd をオーバーライドします::オンツールヒットテスト](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[をクリックします。](#onupdatecmdui)|(C[ベースペインをオーバーライドします。:オンアップデートCmdUI](cbasepane-class.md).)|
|[整列を設定します。](#setpanealignment)|(CBase ペインをオーバーライド[します::セットペインアライメント](../../mfc/reference/cbasepane-class.md#setpanealignment).)|

## <a name="remarks"></a>解説

オブジェクト`CMFCReBar`には、さまざまな子ウィンドウを含めることができます。 これには、編集ボックス、ツールバー、およびリスト ボックスが含まれます。 Rebar のサイズをプログラムで変更したり、ユーザーがグリッパ バーをドラッグして手動でリバーのサイズを変更したりできます。 Rebar オブジェクトの背景を、選択したビットマップに設定することもできます。

rebar オブジェクトは、ツールバー オブジェクトと同様に動作します。 Rebar コントロールには 1 つまたは複数のバンドを含めることができ、各バンドにはグリッパー バー、ビットマップ、テキスト ラベル、および子ウィンドウを含めることができます。

## <a name="example"></a>例

`CMFCReBar` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、Rebar コントロールを作成し、そのコントロールにバンドを追加する方法を示します。 バンドは、内部ツールバーとして機能します。 このコード スニペットは[、Rebar テストのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[Cobject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdターゲット](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRebar.h

## <a name="cmfcrebaraddbar"></a><a name="addbar"></a>コントロール バー::追加バー

帯をリバーに追加します。

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

*pバー*<br/>
[イン、アウト]Rebar に挿入される子ウィンドウへのポインター。 参照されるオブジェクトは **、WS_CHILD**ウィンドウ スタイルを持つ必要があります。

*テキスト*<br/>
[in]REBAR に表示するテキストを指定します。 テキストは子ウィンドウの一部ではありません。 むしろ、それは、筋棒自体に表示されます。

*pbmp*<br/>
[イン、アウト]Rebar の背景に表示するビットマップを指定します。

*Dwstyle*<br/>
[in]バンドに適用するスタイルを含みます。 バンド スタイルの完全な一覧については、Windows `fStyle` SDK ドキュメントの[REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow)構造体の説明を参照してください。

*clrFore*<br/>
[in]Rebar の前景色を表します。

*clrバック*<br/>
[in]Rebar の背景色を表します。

### <a name="return-value"></a>戻り値

バンドが正常に Rebar に追加された場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcrebarcreate"></a><a name="create"></a>作成

Rebar コントロールを作成し[、CMFCReBar](../../mfc/reference/cmfcrebar-class.md)オブジェクトにアタッチします。

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
[イン、アウト]この Rebar コントロールの親ウィンドウへのポインター。

*スタイル*<br/>
[in]Rebar コントロールのスタイルを指定します。 既定のスタイル値は**RBS_BANDBORDERS**で、Rebar コントロール上の隣接するバンドを分離するために狭い線が表示されます。 有効なスタイルの一覧については、Windows SDK のドキュメントの[「Rebar コントロール スタイル](/windows/win32/Controls/rebar-control-styles)」を参照してください。

*Dwstyle*<br/>
[in]Rebar コントロールのウィンドウ スタイル。 有効なスタイルの一覧については、「[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)」を参照してください。

*nID*<br/>
[in]rebar の子ウィンドウ ID。

### <a name="return-value"></a>戻り値

REBAR が正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcrebargetrebarctrl"></a><a name="getrebarctrl"></a>を返します。

オブジェクトの基になる`CReBarCtrl`コモン コントロールに直接`CMFCReBar`アクセスできます。

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>戻り値

基になる`CReBarCtrl`オブジェクトへの参照。

### <a name="remarks"></a>解説

このメソッドを呼び出して、Rebar をカスタマイズするときに、Windows rebar コモン コントロール機能を利用します。

## <a name="cmfcrebarcalcfixedlayout"></a><a name="calcfixedlayout"></a>コントロールバー::計算式レイアウト

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

[in]*bストレッチ*<br/>
[in]*bHorz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebarcanfloat"></a><a name="canfloat"></a>CMFCReBar::缶詰

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebarenabledocking"></a><a name="enabledocking"></a>ドッキングを有効にする

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

[in]*ドウドックスタイル*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcrebargetrebarbandinfosize"></a><a name="getrebarbandinfosize"></a>を返します。

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a>コントロールバーメニューを表示します。

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>パラメーター

[in]*CPoint*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebarontoolhittest"></a><a name="ontoolhittest"></a>コントロールバー::オンツールヒットテスト

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>パラメーター

[in]*ポイント*<br/>
[in]*pTI*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcrebaronupdatecmdui"></a><a name="onupdatecmdui"></a>をクリックします。

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>パラメーター

[in]*pターゲット*<br/>
[in]*ノフドラー*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcrebarsetpanealignment"></a><a name="setpanealignment"></a>整列を設定します。

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

[in]*dw配置*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)
