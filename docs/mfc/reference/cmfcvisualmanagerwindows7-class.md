---
description: '詳細情報: CMFCVisualManagerWindows7 クラス'
title: CMFCVisualManagerWindows7 クラス
ms.date: 03/27/2019
f1_keywords:
- CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::OnFillMenuImageRect
helpviewer_keywords:
- CMFCVisualManagerWindows7 Class [MFC]
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
ms.openlocfilehash: 108d4144bbcfbfcb82d91678611435f14365302e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331634"
---
# <a name="cmfcvisualmanagerwindows7-class"></a>CMFCVisualManagerWindows7 クラス

は、 `CMFCVisualManagerWindows7` アプリケーションに Windows 7 アプリケーションの外観を提供します。

## <a name="syntax"></a>構文

```
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7)|既定のコンストラクターです。|
|[CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7](#_dtorcmfcvisualmanagerwindows7)|既定のデストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCVisualManagerWindows7::CleanStyle`|現在の visual スタイルをクリアし、既定の visual スタイルをリセットします。|
|`CMFCVisualManagerWindows7::CleanUp`|ユーザーインターフェイス内のすべてのオブジェクトをクリアし、メニューをリセットします。|
|`CMFCVisualManagerWindows7::DrawNcBtn`|フレームの非クライアント領域にボタンを描画します。 フレームワークは、このメソッドを使用して、ウィンドウフレームの右上隅に最小化、最大化、閉じる、および元に戻すボタンを描画します。 このメソッドは、プログラムがテーマを使用する場合にのみ呼び出され `Aero` ます。|
|`CMFCVisualManagerWindows7::DrawNcText`|フレームの非クライアント領域にテキストを描画します。 フレームワークは、このメソッドを使用して、フレームウィンドウの上部にあるタイトルバーにアプリケーションタイトルを描画します。|
|`CMFCVisualManagerWindows7::DrawSeparator`|[Cmfctoolbar クラス](../../mfc/reference/cmfctoolbar-class.md)に区切り記号を描画します。|
|`CMFCVisualManagerWindows7::GetRibbonBar`|ユーザーインターフェイスに関連付けられている [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md) を取得します。|
|[CMFCVisualManagerWindows7:: GetRibbonEditBackgroundColor](#getribboneditbackgroundcolor)|リボンのエディットボックスの背景色を取得します。|
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|[Cmfcvisualmanager:: GetRibbonPopupBorderSize](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize)をオーバーライドします。|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|[Cmfcvisualmanager:: GetRibbonQuickAccessToolBarChevronOffset](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset)をオーバーライドします。|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|[Cmfcvisualmanager:: GetRibbonQuickAccessToolBarRightMargin](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin)をオーバーライドします。|
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|[Cmfcvisualmanagerwindows:: IsHighlightWholeMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem)をオーバーライドします。|
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|[Cmfcvisualmanager:: IsOwnerDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck)をオーバーライドします。|
|`CMFCVisualManagerWindows7::IsRibbonPresent`|`CMFCRibbonBar`が存在し、表示されているかどうかを判断します。|
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|[Cmfcvisualmanagerwindows:: OnDrawButtonBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|[Cmfcvisualmanagerwindows:: OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|[Cmfcvisualmanagerwindows:: OnDrawComboDropButton](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|[Cmfcvisualmanager:: OnDrawDefaultRibbonImage](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|[Cmfcvisualmanagerwindows:: OnDrawMenuBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|[Cmfcvisualmanager:: OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|[Cmfcvisualmanager:: OnDrawMenuLabel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|`CMFCVisualManager::OnDrawRadioButton` をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|[Cmfcvisualmanager:: OnDrawRibbonApplicationButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|[Cmfcvisualmanager:: OnDrawRibbonButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|[Cmfcvisualmanager:: OnDrawRibbonCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|[Cmfcvisualmanager:: OnDrawRibbonCaptionButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|[Cmfcvisualmanager:: OnDrawRibbonCategory](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|[Cmfcvisualmanager:: OnDrawRibbonCategoryTab](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|[Cmfcvisualmanager:: OnDrawRibbonDefaultPaneButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|[Cmfcvisualmanager:: OnDrawRibbonGalleryButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|`CMFCVisualManager::OnDrawRibbonLaunchButton` をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|[Cmfcvisualmanager:: OnDrawRibbonMenuCheckFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonmenucheckframe)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|[Cmfcvisualmanager:: OnDrawRibbonPanel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanel)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|[Cmfcvisualmanager:: OnDrawRibbonPanelCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanelcaption)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|[Cmfcvisualmanager:: OnDrawRibbonProgressBar](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|[Cmfcvisualmanager:: OnDrawRibbonRecentFilesFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonrecentfilesframe)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|[Cmfcvisualmanager:: OnDrawRibbonSliderChannel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|[Cmfcvisualmanager:: OnDrawRibbonSliderThumb](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|[Cmfcvisualmanager:: OnDrawRibbonSliderZoomButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|[Cmfcvisualmanager:: OnDrawRibbonStatusBarPane](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonstatusbarpane)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|[Cmfcvisualmanager:: OnDrawRibbonTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbontabsframe)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|[Cmfcvisualmanagerwindows:: OnDrawStatusBarSizeBox](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawstatusbarsizebox)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnFillBarBackground`|[Cmfcvisualmanagerwindows:: OnFillBarBackground](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbarbackground)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|[Cmfcvisualmanagerwindows:: OnFillButtonInterior](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbuttoninterior)をオーバーライドします。|
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](#onfillmenuimagerect)|フレームワークは、メニュー項目イメージの周囲に領域を塗りつぶすときに、このメソッドを呼び出します。|
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|[Cmfcvisualmanager:: OnFillRibbonButton](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|[Cmfcvisualmanager:: OnFillRibbonQuickAccessToolBarPopup](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|[Cmfcvisualmanagerwindows:: OnHighlightMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnNcActivate`|[Cmfcvisualmanager:: OnNcActivate](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnNcPaint`|[Cmfcvisualmanager:: OnNcPaint](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint)をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|[Cmfcvisualmanagerwindows:: OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors)をオーバーライドします。|
|`CMFCVisualManagerWindows7::SetResourceHandle`|ビジュアルマネージャーの属性を記述するリソースハンドルを設定します。|
|`CMFCVisualManagerWindows7::SetStyle`|GUI の配色を設定し `CMFCVisualManagerWindows7` ます。|

## <a name="remarks"></a>解説

クラスを使用して、 `CMFCVisualManagerWindows7` アプリケーションの外観を変更し、既定の Windows 7 アプリケーションを模倣します。 アプリケーションが Windows 7 より前のバージョンの Windows で実行されている場合、このクラスは有効でない可能性があります。 このシナリオでは、アプリケーションは [Cmfcvisualmanager](../../mfc/reference/cmfcvisualmanager-class.md)で定義された既定のビジュアルマネージャーを使用します。

CMFCVisualManagerWindows7 は、 [Cmfcvisualmanagerwindows クラス](../../mfc/reference/cmfcvisualmanagerwindows-class.md) とクラスの両方から複数のメソッドを継承し `CMFCVisualManager` ます。 前のセクションで示したメソッドは、クラスの新しいメソッドです `CMFCVisualManagerWindows7` 。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)

`CMFCVisualManagerWindows7`

## <a name="requirements"></a>要件

**ヘッダー:** afxvisualmanagerwindows7

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="_dtorcmfcvisualmanagerwindows7"></a> CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7

既定のデストラクター。

```
virtual ~CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="cmfcvisualmanagerwindows7"></a> CMFCVisualManagerWindows7::CMFCVisualManagerWindows7

既定のコンストラクターです。

```
CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7getribboneditbackgroundcolor"></a><a name="getribboneditbackgroundcolor"></a> CMFCVisualManagerWindows7:: GetRibbonEditBackgroundColor

リボンのエディットボックスの背景色を取得します。

```
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,
    BOOL bIsHighlighted,
    BOOL bIsPaneHighlighted,
    BOOL bIsDisabled);
```

### <a name="parameters"></a>パラメーター

*pEdit*<br/>
からエディットコントロールへのポインター。 この値を NULL にすることはできません。

*bIsHighlighted*<br/>
入出力リボンボックスが強調表示されているかどうかを返します。

*bIsPaneHighlighted*<br/>
入出力 *Pedit* を含むリボンパネルが強調表示されている場合に TRUE を返します。

*bIsDisabled*<br/>
入出力 *Pedit* が無効になっているかどうかを返します。

### <a name="return-value"></a>戻り値

エディットボックスの *Pedit* の背景色。

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagerwindows7onfillmenuimagerect"></a><a name="onfillmenuimagerect"></a> CMFCVisualManagerWindows7::OnFillMenuImageRect

フレームワークは、メニュー項目イメージの周囲に領域を塗りつぶすときに、このメソッドを呼び出します。

```
virtual void OnFillMenuImageRect(
    CDC* pDC,
    CMFCToolBarButton* pButton,
    CRect rectangle,
    CMFCVisualManager::AFX_BUTTON_STATE state);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からメニューボタンのデバイスコンテキストへのポインター。

*pButton*<br/>
からへのポインター `CMFCToolBarButton` 。 フレームワークは、このボタンの背景を塗りつぶします。

*四角形*<br/>
からメニューボタンのイメージ領域の境界を指定する四角形。

*state*<br/>
からボタンの状態。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[CMFCVisualManagerWindows クラス](../../mfc/reference/cmfcvisualmanagerwindows-class.md)
