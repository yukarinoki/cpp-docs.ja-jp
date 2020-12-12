---
description: '詳細情報: CMFCDropDownToolBar クラス'
title: CMFCDropDownToolBar クラス
ms.date: 11/19/2018
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
ms.openlocfilehash: 158562829cb5bbebfb9a858d34751c56bdf46ed8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293990"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar クラス

ユーザーがトップレベルのツール バー ボタンを押し続けたときに表示されるツール バーです。

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCDropDownToolBar:: AllowShowOnPaneMenu](#allowshowonpanemenu)|( `CPane::AllowShowOnPaneMenu`をオーバーライドします)。|
|[CMFCDropDownToolBar:: LoadBitmap](#loadbitmap)|( [Cmfctoolbar:: LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap)をオーバーライドします)。|
|[CMFCDropDownToolBar:: LoadToolBar](#loadtoolbar)|( [Cmfctoolbar:: loadtoolbar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar)をオーバーライドします)。|
|[CMFCDropDownToolBar:: OnLButtonUp](#onlbuttonup)||
|[CMFCDropDownToolBar:: OnMouseMove](#onmousemove)||
|[CMFCDropDownToolBar:: OnSendCommand](#onsendcommand)|( `CMFCToolBar::OnSendCommand`をオーバーライドします)。|
|[CMFCDropDownToolBar:: OnUpdateCmdUI](#onupdatecmdui)|( [Cmfctoolbar:: OnUpdateCmdUI](cmfctoolbar-class.md)をオーバーライドします。|

### <a name="remarks"></a>解説

オブジェクトは、 `CMFCDropDownToolBar` ツールバーの外観とポップアップメニューの動作を組み合わせたものです。 ユーザーがドロップダウンツールバーボタン ( [CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)を参照) を押して保持すると、ドロップダウンツールバーが表示され、ユーザーはドロップダウンツールバーからボタンを選択して、マウスボタンを放すことができます。 ユーザーがドロップダウンツールバーでボタンを選択すると、そのボタンがトップレベルのツールバーの [現在] ボタンとして表示されます。

ドロップダウンツールバーは、カスタマイズしたりドッキングしたりすることはできず、ティアオフ状態もありません。

次の図は、オブジェクトを示してい `CMFCDropDownToolBar` ます。

![CMFCDropDownToolbar の例](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDownToolbar の例")

オブジェクトは、 `CMFCDropDownToolBar` 通常のツールバーを作成するのと同じ方法で作成します (「 [Cmfctoolbar クラス](../../mfc/reference/cmfctoolbar-class.md)」を参照してください)。

親ツールバーにドロップダウンツールバーを挿入するには、次の操作を行います。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。

2. `CMFCDropDownToolBarButton`ドロップダウンツールバーを含むオブジェクトを作成します (詳細については、「 [CMFCDropDownToolbarButton:: CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)」を参照してください)。

3. `CMFCDropDownToolBarButton` [Cmfctoolbar:: replacebutton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)を使用して、ダミーのボタンをオブジェクトに置き換えます。

ツールバーボタンの詳細については、「 [チュートリアル: ツールバーへのコントロールの配置](../../mfc/walkthrough-putting-controls-on-toolbars.md)」を参照してください。 ドロップダウンツールバーの例については、「sample project VisualStudioDemo」を参照してください。

## <a name="example"></a>例

クラスのメソッドを使用する方法を次の例に示し `Create` `CMFCDropDownToolBar` ます。 このコードスニペットは、 [Visual Studio のデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a> CMFCDropDownToolBar:: AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a> CMFCDropDownToolBar:: LoadBitmap

アプリケーション リソースからツール バー イメージを読み込みます。

```
virtual BOOL LoadBitmap(
    UINT uiResID,
    UINT uiColdResID=0,
    UINT uiMenuResID=0,
    BOOL bLocked=FALSE,
    UINT uiDisabledResID=0,
    UINT uiMenuDisabledResID=0);
```

### <a name="parameters"></a>パラメーター

*uiResID*<br/>
からホットなツールバーイメージを参照するビットマップのリソース ID。

*uiColdResID*<br/>
からコールドツールバーイメージを参照するビットマップのリソース ID。

*uiMenuResID*<br/>
から通常のメニューイメージを参照するビットマップのリソース ID。

*化*<br/>
からツールバーをロックする場合は TRUE。それ以外の場合は FALSE。

*uiDisabledResID*<br/>
から無効なツールバーイメージを参照するビットマップのリソース ID。

*uiMenuDisabledResID*<br/>
から無効なメニューイメージを参照するビットマップのリソース ID。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

[CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) メソッドはこのメソッドを呼び出して、ツール バーに関連付けられたイメージを読み込みます。 このメソッドをオーバーライドして、イメージ リソースのカスタムの読み込みを実行します。

ツール バーの作成後に、 `LoadBitmapEx` メソッドを呼び出して追加のイメージを読み込みます。

## <a name="cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a> CMFCDropDownToolBar:: LoadToolBar

```
virtual BOOL LoadToolBar(
    UINT uiResID,
    UINT uiColdResID = 0,
    UINT uiMenuResID = 0,
    BOOL = FALSE,
    UINT uiDisabledResID = 0,
    UINT uiMenuDisabledResID = 0,
    UINT uiHotResID = 0);
```

### <a name="parameters"></a>パラメーター

から *uiResID*<br/>

から *uiColdResID*<br/>

から *uiMenuResID*<br/>

から *BOOL*<br/>

から *uiDisabledResID*<br/>

から *uiMenuDisabledResID*<br/>

から *uiHotResID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a> CMFCDropDownToolBar:: OnLButtonUp

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

から *nFlags*<br/>

から *ポイント*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a> CMFCDropDownToolBar:: OnMouseMove

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

から *nFlags*<br/>

から *ポイント*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a> CMFCDropDownToolBar:: OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>パラメーター

から *Pbutton*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a> CMFCDropDownToolBar:: OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>パラメーター

から *Ptarget*<br/>

から *Bdisableifnohndler*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBar:: 作成](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[チュートリアル: ツールバーへのコントロールの配置](../../mfc/walkthrough-putting-controls-on-toolbars.md)
