---
description: '詳細情報: CMFCVisualManagerVS2005 クラス'
title: CMFCVisualManagerVS2005 クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetDockingTabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetMDITabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetPropertyGridGroupColor
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetTabFrameColors
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawCaptionButton
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawPaneCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawSeparator
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawTab
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawToolBoxFrame
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnEraseTabsArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillHighlightedArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillMiniFrameCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnUpdateSystemColors
helpviewer_keywords:
- CMFCVisualManagerVS2005 [MFC], GetDockingTabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetMDITabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetPropertyGridGroupColor
- CMFCVisualManagerVS2005 [MFC], GetTabFrameColors
- CMFCVisualManagerVS2005 [MFC], HasOverlappedAutoHideButtons
- CMFCVisualManagerVS2005 [MFC], OnDrawAutoHideButtonBorder
- CMFCVisualManagerVS2005 [MFC], OnDrawCaptionButton
- CMFCVisualManagerVS2005 [MFC], OnDrawPaneCaption
- CMFCVisualManagerVS2005 [MFC], OnDrawSeparator
- CMFCVisualManagerVS2005 [MFC], OnDrawTab
- CMFCVisualManagerVS2005 [MFC], OnDrawToolBoxFrame
- CMFCVisualManagerVS2005 [MFC], OnEraseTabsArea
- CMFCVisualManagerVS2005 [MFC], OnFillAutoHideButtonBackground
- CMFCVisualManagerVS2005 [MFC], OnFillHighlightedArea
- CMFCVisualManagerVS2005 [MFC], OnFillMiniFrameCaption
- CMFCVisualManagerVS2005 [MFC], OnUpdateSystemColors
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
ms.openlocfilehash: 74192e1c0e4c7189a64d872bcc1761cf21e5365d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331653"
---
# <a name="cmfcvisualmanagervs2005-class"></a>CMFCVisualManagerVS2005 クラス

`CMFCVisualManagerVS2005` アプリケーションに2005の外観を Microsoft Visual Studio します。

## <a name="syntax"></a>構文

```
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCVisualManagerVS2005:: Getdoc Tabsborderssize](#getdockingtabsborderssize)|フレームワークは、ドッキングされてタブ付きのペインを描画するときに、このメソッドを呼び出します。 ( [Cmfcvisualmanager:: GetDockingTabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getdockingtabsborderssize)をオーバーライドします)。|
|[CMFCVisualManagerVS2005:: GetMDITabsBordersSize](#getmditabsborderssize)|フレームワークは、このメソッドを呼び出して、ウィンドウを描画する前に、MDITabs ウィンドウの境界線のサイズを決定します。 ( [Cmfcvisualmanager:: GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize)をオーバーライドします)。|
|[CMFCVisualManagerVS2005:: GetPropertyGridGroupColor](#getpropertygridgroupcolor)|( [CMFCVisualManagerOffice2003:: GetPropertyGridGroupColor](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#getpropertygridgroupcolor)をオーバーライドします)。|
|[CMFCVisualManagerVS2005:: GetTabFrameColors](#gettabframecolors)|( [CMFCVisualManagerOffice2003:: GetTabFrameColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#gettabframecolors)をオーバーライドします。)|
|[CMFCVisualManagerVS2005:: HasOverlappedAutoHideButtons](#hasoverlappedautohidebuttons)|現在のビジュアルマネージャーで自動非表示ボタンが重なっているかどうかを返します。 ( [Cmfcvisualmanager:: HasOverlappedAutoHideButtons](../../mfc/reference/cmfcvisualmanager-class.md#hasoverlappedautohidebuttons)をオーバーライドします)。|
|[CMFCVisualManagerVS2005:: OnDrawAutoHideButtonBorder](#ondrawautohidebuttonborder)|( [CMFCVisualManagerOffice2003:: OnDrawAutoHideButtonBorder](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawautohidebuttonborder)をオーバーライドします。)|
|[CMFCVisualManagerVS2005:: OnDrawCaptionButton](#ondrawcaptionbutton)|( `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`をオーバーライドします)。|
|[CMFCVisualManagerVS2005:: OnDrawPaneCaption](#ondrawpanecaption)|( [CMFCVisualManagerOffice2003:: OnDrawPaneCaption](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawpanecaption)をオーバーライドします。)|
|[CMFCVisualManagerVS2005:: OnDrawSeparator](#ondrawseparator)|( [CMFCVisualManagerOffice2003:: OnDrawSeparator](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawseparator)をオーバーライドします。)|
|[CMFCVisualManagerVS2005:: OnDrawTab](#ondrawtab)|( [CMFCVisualManagerOffice2003:: OnDrawTab](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawtab)をオーバーライドします。)|
|[CMFCVisualManagerVS2005:: OnDrawToolBoxFrame](#ondrawtoolboxframe)|( [Cmfcvisualmanager:: OnDrawToolBoxFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawtoolboxframe)をオーバーライドします)。|
|[CMFCVisualManagerVS2005:: OnEraseTabsArea](#onerasetabsarea)|( [CMFCVisualManagerOffice2003:: OnEraseTabsArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onerasetabsarea)をオーバーライドします。)|
|[CMFCVisualManagerVS2005:: OnFillAutoHideButtonBackground](#onfillautohidebuttonbackground)|( [CMFCVisualManagerOffice2003:: OnFillAutoHideButtonBackground](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillautohidebuttonbackground)をオーバーライドします)。|
|[CMFCVisualManagerVS2005:: OnFillHighlightedArea](#onfillhighlightedarea)|( [CMFCVisualManagerOffice2003:: OnFillHighlightedArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillhighlightedarea)をオーバーライドします。)|
|[CMFCVisualManagerVS2005:: onfillminiframecap](#onfillminiframecaption)|( `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`をオーバーライドします)。|
|[CMFCVisualManagerVS2005:: OnUpdateSystemColors](#onupdatesystemcolors)|( [CMFCVisualManagerOffice2003:: OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onupdatesystemcolors)をオーバーライドします。)|

## <a name="remarks"></a>解説

CMFCVisualManagerVS2005 クラスを使用して、Microsoft Visual Studio 2005 のようにアプリケーションの外観を変更します。

このクラスのすべてのメンバーは、このクラスの先祖 ( [Cmfcvisualmanager クラス](../../mfc/reference/cmfcvisualmanager-class.md)) から派生した仮想関数です。

## <a name="example"></a>例

次の例は、visual manager と2005を使用する方法を示しています。 このコードスニペットは、 [デスクトップアラートのデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagervs2005-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)

[CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxvisualmanagervs2005

## <a name="cmfcvisualmanagervs2005getdockingtabsborderssize"></a><a name="getdockingtabsborderssize"></a> CMFCVisualManagerVS2005:: Getdoc Tabsborderssize

```
virtual int GetDockingTabsBordersSize();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005getmditabsborderssize"></a><a name="getmditabsborderssize"></a> CMFCVisualManagerVS2005:: GetMDITabsBordersSize

```
virtual int GetMDITabsBordersSize();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005getpropertygridgroupcolor"></a><a name="getpropertygridgroupcolor"></a> CMFCVisualManagerVS2005:: GetPropertyGridGroupColor

```
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```

### <a name="parameters"></a>パラメーター

から *Pproplist*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005gettabframecolors"></a><a name="gettabframecolors"></a> CMFCVisualManagerVS2005:: GetTabFrameColors

```
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,
    COLORREF& clrDark,
    COLORREF& clrBlack,
    COLORREF& clrHighlight,
    COLORREF& clrFace,
    COLORREF& clrDarkShadow,
    COLORREF& clrLight,
    CBrush*& pbrFace,
    CBrush*& pbrBlack);
```

### <a name="parameters"></a>パラメーター

から *pTabWnd*<br/>
から *Clrdark*<br/>
から *Clrblack*<br/>
から *Clrhighlight 表示*<br/>
から *Clrface*<br/>
から *clrDarkShadow*<br/>
から *Clrlight*<br/>
から *Pbrface*<br/>
から *Pbrblack*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005hasoverlappedautohidebuttons"></a><a name="hasoverlappedautohidebuttons"></a> CMFCVisualManagerVS2005:: HasOverlappedAutoHideButtons

```
virtual BOOL HasOverlappedAutoHideButtons() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawautohidebuttonborder"></a><a name="ondrawautohidebuttonborder"></a> CMFCVisualManagerVS2005:: OnDrawAutoHideButtonBorder

```
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *rectBounds*<br/>
から *rectBorderSize*<br/>
から *Pbutton*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawcaptionbutton"></a><a name="ondrawcaptionbutton"></a> CMFCVisualManagerVS2005:: OnDrawCaptionButton

```
virtual void OnDrawCaptionButton(
    CDC* pDC,
    CMFCCaptionButton* pButton,
    BOOL bActive,
    BOOL bHorz,
    BOOL bMaximized,
    BOOL bDisabled,
    int nImageID = -1);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *Pbutton*<br/>
から *Bactive*<br/>
から *bHorz*<br/>
から *Bmaximized*<br/>
から *Bdisabled*<br/>
から *Nimageid*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawpanecaption"></a><a name="ondrawpanecaption"></a> CMFCVisualManagerVS2005:: OnDrawPaneCaption

```
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,
    CDockablePane* pBar,
    BOOL bActive,
    CRect rectCaption,
    CRect rectButtons);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *Pbar*<br/>
から *Bactive*<br/>
から *rectCaption*<br/>
から *rectButtons*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawseparator"></a><a name="ondrawseparator"></a> CMFCVisualManagerVS2005:: OnDrawSeparator

```
virtual void OnDrawSeparator(
    CDC* pDC,
    CBasePane* pBar,
    CRect rect,
    BOOL bIsHoriz);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *Pbar*<br/>
から *rect*<br/>
から *bIsHoriz*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawtab"></a><a name="ondrawtab"></a> CMFCVisualManagerVS2005:: OnDrawTab

```
virtual void OnDrawTab(
    CDC* pDC,
    CRect rectTab,
    int iTab,
    BOOL bIsActive,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *rectTab*<br/>
から *Itab*<br/>
から *bIsActive*<br/>
から *pTabWnd*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawtoolboxframe"></a><a name="ondrawtoolboxframe"></a> CMFCVisualManagerVS2005:: OnDrawToolBoxFrame

```
virtual void OnDrawToolBoxFrame(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *rect*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onerasetabsarea"></a><a name="onerasetabsarea"></a> CMFCVisualManagerVS2005:: OnEraseTabsArea

```
virtual void OnEraseTabsArea(
    CDC* pDC,
    CRect rect,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *rect*<br/>
から *pTabWnd*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onfillautohidebuttonbackground"></a><a name="onfillautohidebuttonbackground"></a> CMFCVisualManagerVS2005:: OnFillAutoHideButtonBackground

```
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,
    CRect rect,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *rect*<br/>
から *Pbutton*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onfillhighlightedarea"></a><a name="onfillhighlightedarea"></a> CMFCVisualManagerVS2005:: OnFillHighlightedArea

```
virtual void OnFillHighlightedArea(
    CDC* pDC,
    CRect rect,
    CBrush* pBrush,
    CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *rect*<br/>
から *Pbrush*<br/>
から *Pbutton*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onfillminiframecaption"></a><a name="onfillminiframecaption"></a> CMFCVisualManagerVS2005:: onfillminiframecap

```
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,
    CRect rectCaption,
    CPaneFrameWnd* pFrameWnd,
    BOOL bActive);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>
から *rectCaption*<br/>
から *pFrameWnd*<br/>
から *Bactive*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onupdatesystemcolors"></a><a name="onupdatesystemcolors"></a> CMFCVisualManagerVS2005:: OnUpdateSystemColors

```
virtual void OnUpdateSystemColors();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[CMFCVisualManagerOfficeXP クラス](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)<br/>
[CMFCVisualManagerWindows クラス](../../mfc/reference/cmfcvisualmanagerwindows-class.md)<br/>
[CMFCVisualManagerOffice2003 クラス](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)
