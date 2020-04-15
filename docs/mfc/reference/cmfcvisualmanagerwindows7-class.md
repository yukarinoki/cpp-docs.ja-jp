---
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
ms.openlocfilehash: 6686afecc2b8ef97ea24ef45ff5225433677a954
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319844"
---
# <a name="cmfcvisualmanagerwindows7-class"></a>CMFCVisualManagerWindows7 クラス

アプリケーション`CMFCVisualManagerWindows7`は、Windows 7 アプリケーションの外観を提供します。

## <a name="syntax"></a>構文

```
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ウィンドウズマネージャーウィンドウズ7:::CMFC ビジュアル マネージャーウィンドウズ7](#cmfcvisualmanagerwindows7)|既定のコンストラクターです。|
|[ウィンドウズマネージャーウィンドウズ7:~CMFC ビジュアルマネージャーウィンドウズ7](#_dtorcmfcvisualmanagerwindows7)|既定のデストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCVisualManagerWindows7::CleanStyle`|現在の表示スタイルをクリアし、既定の表示スタイルをリセットします。|
|`CMFCVisualManagerWindows7::CleanUp`|ユーザー インターフェイス内のすべてのオブジェクトをクリアし、メニューをリセットします。|
|`CMFCVisualManagerWindows7::DrawNcBtn`|フレームの非クライアント領域にボタンを描画します。 フレームワークは、ウィンドウ フレームの右上隅にある最小化、最大化、閉じる、および復元ボタンを描画するには、このメソッドを使用します。 このメソッドは、プログラムがテーマを使用する`Aero`場合にのみ呼び出されます。|
|`CMFCVisualManagerWindows7::DrawNcText`|フレーム上の非クライアント領域にテキストを描画します。 フレームワークは、このメソッドを使用して、フレーム ウィンドウの上部にあるタイトル バーにアプリケーション タイトルを描画します。|
|`CMFCVisualManagerWindows7::DrawSeparator`|[CMFC ツール バー クラス](../../mfc/reference/cmfctoolbar-class.md)に区切り記号を描画します。|
|`CMFCVisualManagerWindows7::GetRibbonBar`|ユーザー インターフェイスに関連付けられている[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)を取得します。|
|[ウィンドウズコントロールウィンドウズ7::リボン編集バックグラウンドカラー](#getribboneditbackgroundcolor)|リボンエディット ボックスの背景色を取得します。|
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin)|
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem)|
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck)|
|`CMFCVisualManagerWindows7::IsRibbonPresent`|が存在し`CMFCRibbonBar`、表示されているかどうかを判断します。|
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex)|
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton)|
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage)|
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder)|
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)|
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel)|
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|`CMFCVisualManager::OnDrawRadioButton` をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab)|
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|`CMFCVisualManager::OnDrawRibbonLaunchButton` をオーバーライドします。|
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonmenucheckframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanelcaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar)|
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonrecentfilesframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonstatusbarpane)|
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbontabsframe)|
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawstatusbarsizebox)|
|`CMFCVisualManagerWindows7::OnFillBarBackground`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbarbackground)|
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbuttoninterior)|
|[をクリックします。](#onfillmenuimagerect)|フレームワークは、メニュー項目イメージの周囲の領域を塗りつぶすときに、このメソッドを呼び出します。|
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton)|
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup)|
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|をオーバーライド[します。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem)|
|`CMFCVisualManagerWindows7::OnNcActivate`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate)|
|`CMFCVisualManagerWindows7::OnNcPaint`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint)|
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|をオーバーライドします[。](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors)|
|`CMFCVisualManagerWindows7::SetResourceHandle`|ビジュアル マネージャーの属性を記述するリソース ハンドルを設定します。|
|`CMFCVisualManagerWindows7::SetStyle`|GUI の配色を設定`CMFCVisualManagerWindows7`します。|

## <a name="remarks"></a>解説

このクラス`CMFCVisualManagerWindows7`を使用して、既定の Windows 7 アプリケーションを模倣するようにアプリケーションの外観を変更します。 アプリケーションが Windows 7 より前のバージョンの Windows で実行されている場合、このクラスは無効なことがあります。 このシナリオでは、アプリケーションは[、CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)で定義された既定のビジュアル マネージャーを使用します。

クラス[とクラス](../../mfc/reference/cmfcvisualmanagerwindows-class.md)の両方から複数のメソッドを継承します`CMFCVisualManager`。 前のセクションに示したメソッドは、クラスの`CMFCVisualManagerWindows7`新しいメソッドです。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[ビジュアル マネージャー](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[オフィスXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)

`CMFCVisualManagerWindows7`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx ビジュアルマネージャーウィンドウズ7.h

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="_dtorcmfcvisualmanagerwindows7"></a>ウィンドウズマネージャーウィンドウズ7:~CMFC ビジュアルマネージャーウィンドウズ7

既定のデストラクター。

```
virtual ~CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="cmfcvisualmanagerwindows7"></a>ウィンドウズマネージャーウィンドウズ7:::CMFC ビジュアル マネージャーウィンドウズ7

既定のコンストラクターです。

```
CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7getribboneditbackgroundcolor"></a><a name="getribboneditbackgroundcolor"></a>ウィンドウズコントロールウィンドウズ7::リボン編集バックグラウンドカラー

リボン編集ボックスの背景色を取得します。

```
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,
    BOOL bIsHighlighted,
    BOOL bIsPaneHighlighted,
    BOOL bIsDisabled);
```

### <a name="parameters"></a>パラメーター

*を編集する*<br/>
[in]エディット コントロールへのポインター。 この値を NULL にすることはできません。

*bIs強調表示*<br/>
[アウト]リボン ボックスが強調表示されているかどうかを返します。

*bIsPane強調表示*<br/>
[アウト]*pEdit*を含むリボン パネルが強調表示されている場合は TRUE を返します。

*無効*<br/>
[アウト]*pEdit*が無効になっているかどうかを返します。

### <a name="return-value"></a>戻り値

編集ボックス*pEdit*の背景色。

### <a name="remarks"></a>解説

## <a name="cmfcvisualmanagerwindows7onfillmenuimagerect"></a><a name="onfillmenuimagerect"></a>をクリックします。

フレームワークは、メニュー項目イメージの周囲の領域を塗りつぶすときに、このメソッドを呼び出します。

```
virtual void OnFillMenuImageRect(
    CDC* pDC,
    CMFCToolBarButton* pButton,
    CRect rectangle,
    CMFCVisualManager::AFX_BUTTON_STATE state);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]メニュー ボタンのデバイス コンテキストへのポインター。

*ボタン*<br/>
[in]へのポインター。 `CMFCToolBarButton` フレームワークは、このボタンの背景を塗りつぶします。

*四角 形*<br/>
[in]メニュー ボタンのイメージ領域の境界を指定する四角形。

*状態*<br/>
[in]ボタンの状態。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[クラス](../../mfc/reference/cmfcvisualmanagerwindows-class.md)
