---
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
ms.openlocfilehash: b92077ecf4670dd5395296327c767ee3c7b848ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319904"
---
# <a name="cmfcvisualmanagervs2005-class"></a>CMFCVisualManagerVS2005 クラス

`CMFCVisualManagerVS2005`アプリケーションに、Visual Studio 2005 の外観を提供します。

## <a name="syntax"></a>構文

```
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#getdockingtabsborderssize)|フレームワークは、ドッキングされタブ付きのペインを描画するときに、このメソッドを呼び出します。 (オーバーライド[CMFC ビジュアル マネージャー::取得ドッキング タブボーダーズサイズ](../../mfc/reference/cmfcvisualmanager-class.md#getdockingtabsborderssize).)|
|[ウィンドウズマネージャー VS2005::ウィンドウディタブボーダーズサイズ](#getmditabsborderssize)|フレームワークは、ウィンドウを描画する前に MDITabs ウィンドウの境界線のサイズを決定するために、このメソッドを呼び出します。 (オーバーライド[CMFC ビジュアル マネージャー::GetMDI タブボーダーズサイズ](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize).)|
|[をグループ化します。](#getpropertygridgroupcolor)|(オーバーライドします[。](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#getpropertygridgroupcolor)|
|[をクリックします。](#gettabframecolors)|(オーバーライドします[。](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#gettabframecolors)|
|[を切り替えた自動非表示ボタン](#hasoverlappedautohidebuttons)|現在のビジュアル マネージャーで、自動非表示ボタンが重なっているかどうかを返します。 (オーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#hasoverlappedautohidebuttons)|
|[をクリックして、自動非表示ボタンボーダーを表示します。](#ondrawautohidebuttonborder)|(オーバーライドします[。](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawautohidebuttonborder)|
|[ボタンをクリックします。](#ondrawcaptionbutton)|( `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`をオーバーライドします)。|
|[ウィンドウスマネージャー 2005::オンドローペインキャプション](#ondrawpanecaption)|(オーバーライドします[。](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawpanecaption)|
|[を切り取る](#ondrawseparator)|(オーバーライドします[。](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawseparator)|
|[をクリックします。](#ondrawtab)|(オーバーライドします[。](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawtab)|
|[をクリックします。](#ondrawtoolboxframe)|([オーバーライド](../../mfc/reference/cmfcvisualmanager-class.md#ondrawtoolboxframe)します。|
|[をクリックします。](#onerasetabsarea)|([オーバーライドします。](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onerasetabsarea)|
|[をクリックして、自動非表示ボタンの背景を表示します。](#onfillautohidebuttonbackground)|(オーバーライドします[。](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillautohidebuttonbackground)|
|[をクリックします。](#onfillhighlightedarea)|(オーバーライド[CMFCビジュアルマネージャーオフィス2003::オンフィルハイライトエリア](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillhighlightedarea).)|
|[をクリックします。](#onfillminiframecaption)|( `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`をオーバーライドします)。|
|[システムカラーのオンアップデート](#onupdatesystemcolors)|([オーバーライドします。](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onupdatesystemcolors)|

## <a name="remarks"></a>解説

アプリケーションの外観を変更して、アプリケーションの外観を変更するには、CMFCVisualManagerVS2005 クラスを使用します。

このクラスのすべてのメンバーは、このクラスの先祖から派生した仮想関数[です。](../../mfc/reference/cmfcvisualmanager-class.md)

## <a name="example"></a>例

ビジュアル マネージャー VS 2005 の使用方法を次の例に示します。 このコード スニペットは[、デスクトップ警告デモのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagervs2005-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[ビジュアル マネージャー](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[オフィスXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)

[CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx ビジュアルマネージャーvs2005.h

## <a name="cmfcvisualmanagervs2005getdockingtabsborderssize"></a><a name="getdockingtabsborderssize"></a>をクリックします。

```
virtual int GetDockingTabsBordersSize();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005getmditabsborderssize"></a><a name="getmditabsborderssize"></a>ウィンドウズマネージャー VS2005::ウィンドウディタブボーダーズサイズ

```
virtual int GetMDITabsBordersSize();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005getpropertygridgroupcolor"></a><a name="getpropertygridgroupcolor"></a>をグループ化します。

```
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```

### <a name="parameters"></a>パラメーター

[in]*プロップリスト*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005gettabframecolors"></a><a name="gettabframecolors"></a>をクリックします。

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

[in]*pタブーンド*<br/>
[in]*clrダーク*<br/>
[in]*clrブラック*<br/>
[in]*clrハイライト*<br/>
[in]*clrFace*<br/>
[in]*ブラックシャドウ*<br/>
[in]*clrLight*<br/>
[in]*pbrFace*<br/>
[in]*pbrブラック*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005hasoverlappedautohidebuttons"></a><a name="hasoverlappedautohidebuttons"></a>を切り替えた自動非表示ボタン

```
virtual BOOL HasOverlappedAutoHideButtons() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawautohidebuttonborder"></a><a name="ondrawautohidebuttonborder"></a>をクリックして、自動非表示ボタンボーダーを表示します。

```
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*レクトバウンド*<br/>
[in]*レクトボーダーサイズ*<br/>
[in]*ボタン*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawcaptionbutton"></a><a name="ondrawcaptionbutton"></a>ボタンをクリックします。

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

[in]*pDC*<br/>
[in]*ボタン*<br/>
[in]*bアクティブ*<br/>
[in]*bHorz*<br/>
[in]*b最大化*<br/>
[in]*b無効*<br/>
[in]*イメージID*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawpanecaption"></a><a name="ondrawpanecaption"></a>ウィンドウスマネージャー 2005::オンドローペインキャプション

```
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,
    CDockablePane* pBar,
    BOOL bActive,
    CRect rectCaption,
    CRect rectButtons);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*pバー*<br/>
[in]*bアクティブ*<br/>
[in]*直流キャプション*<br/>
[in]*レクトボタン*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawseparator"></a><a name="ondrawseparator"></a>を切り取る

```
virtual void OnDrawSeparator(
    CDC* pDC,
    CBasePane* pBar,
    CRect rect,
    BOOL bIsHoriz);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*pバー*<br/>
[in]*レクト*<br/>
[in]*ビショリス*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawtab"></a><a name="ondrawtab"></a>をクリックします。

```
virtual void OnDrawTab(
    CDC* pDC,
    CRect rectTab,
    int iTab,
    BOOL bIsActive,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*直タブ*<br/>
[in]*iタブ*<br/>
[in]*ビイシスアクティブ*<br/>
[in]*pタブーンド*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005ondrawtoolboxframe"></a><a name="ondrawtoolboxframe"></a>をクリックします。

```
virtual void OnDrawToolBoxFrame(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*レクト*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onerasetabsarea"></a><a name="onerasetabsarea"></a>をクリックします。

```
virtual void OnEraseTabsArea(
    CDC* pDC,
    CRect rect,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*レクト*<br/>
[in]*pタブーンド*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onfillautohidebuttonbackground"></a><a name="onfillautohidebuttonbackground"></a>をクリックして、自動非表示ボタンの背景を表示します。

```
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,
    CRect rect,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*レクト*<br/>
[in]*ボタン*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onfillhighlightedarea"></a><a name="onfillhighlightedarea"></a>をクリックします。

```
virtual void OnFillHighlightedArea(
    CDC* pDC,
    CRect rect,
    CBrush* pBrush,
    CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*レクト*<br/>
[in]*pブラシ*<br/>
[in]*ボタン*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onfillminiframecaption"></a><a name="onfillminiframecaption"></a>をクリックします。

```
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,
    CRect rectCaption,
    CPaneFrameWnd* pFrameWnd,
    BOOL bActive);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*直流キャプション*<br/>
[in]*をクリックします。*<br/>
[in]*bアクティブ*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagervs2005onupdatesystemcolors"></a><a name="onupdatesystemcolors"></a>システムカラーのオンアップデート

```
virtual void OnUpdateSystemColors();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[クラス](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)<br/>
[クラス](../../mfc/reference/cmfcvisualmanagerwindows-class.md)<br/>
[クラス](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)
