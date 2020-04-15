---
title: クラスをドロップダウンメニューバー
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
ms.openlocfilehash: 68dd976471b39d7f50c2f0378b2fce99ad3feeca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367597"
---
# <a name="cmfcdropdowntoolbar-class"></a>クラスをドロップダウンメニューバー

ユーザーがトップレベルのツール バー ボタンを押し続けたときに表示されるツール バーです。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[メニューメニューを表示します。](#allowshowonpanemenu)|( `CPane::AllowShowOnPaneMenu`をオーバーライドします)。|
|[コントロール バー::ビットマップの読み込み](#loadbitmap)|(CMFC ツールバーをオーバーライド[します。:ロードビットマップ](../../mfc/reference/cmfctoolbar-class.md#loadbitmap).)|
|[ツールバー::読み込みツールバー](#loadtoolbar)|[(CMFC ツールバーを](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar)オーバーライドします。|
|[コントロールバー::オンルボタンアップ](#onlbuttonup)||
|[コントロール バー::マウス移動時](#onmousemove)||
|[ツールバー::オンセンドコマンド](#onsendcommand)|( `CMFCToolBar::OnSendCommand`をオーバーライドします)。|
|[コントロール バー::オンアップデートCmdUI](#onupdatecmdui)|(CMFC ツールバーをオーバーライド[します。](cmfctoolbar-class.md)|

### <a name="remarks"></a>解説

オブジェクト`CMFCDropDownToolBar`は、ツールバーの外観とポップアップ メニューの動作を組み合わせたものです。 ユーザーがドロップダウン ツール バー ボタンを押したままにすると[(CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)を参照)、ドロップダウン ツール バーが表示され、ユーザーはドロップダウン ツール バーのボタンを選択できます。 ユーザーがドロップダウン ツールバーのボタンを選択すると、そのボタンが最上位のツールバーの現在のボタンとして表示されます。

ドロップダウン ツール バーはカスタマイズまたはドッキングできず、ティアオフ状態もできません。

次の図は、`CMFCDropDownToolBar`オブジェクトを示しています。

![CMFCDropDownToolbar の例](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDownToolbar の例")

通常のツール`CMFCDropDownToolBar`バーを作成するのと同じ方法でオブジェクトを作成します[(「CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)」を参照)。

親ツール バーにドロップダウン ツール バーを挿入するには:

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。

2. ドロップダウン`CMFCDropDownToolBarButton`ツール バーを含むオブジェクトを作成します (詳細については[、「CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)」を参照してください)。

3. ダミー ボタンをオブジェクトに`CMFCDropDownToolBarButton`置き換えるには[、CMFC ツール バー::置換ボタン](../../mfc/reference/cmfctoolbar-class.md#replacebutton)を使用します。

ツール バー ボタンの詳細については、「[チュートリアル : ツールバーにコントロールを配置](../../mfc/walkthrough-putting-controls-on-toolbars.md)する 」を参照してください。 ドロップダウン ツール バーの例については、サンプル プロジェクトの VisualStudioDemo を参照してください。

## <a name="example"></a>例

クラスでメソッドを使用する方法を`Create`次の例に`CMFCDropDownToolBar`示します。 このコード スニペットは[、Visual Studio のデモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[ツールバー](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>メニューメニューを表示します。

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a>コントロール バー::ビットマップの読み込み

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

*UIResID*<br/>
[in]ホット ツール バー イメージを参照するビットマップのリソース ID。

*をクリックします。*<br/>
[in]コールド ツール バー イメージを参照するビットマップのリソース ID。

*をクリックします。*<br/>
[in]通常のメニュー イメージを参照するビットマップのリソース ID。

*ブロック*<br/>
[in]ツール バーをロックする場合は TRUE。それ以外の場合は FALSE。

*を無効にします。*<br/>
[in]無効なツール バー イメージを参照するビットマップのリソース ID。

*を無効にします。*<br/>
[in]無効なメニュー イメージを参照するビットマップのリソース ID。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

[CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) メソッドはこのメソッドを呼び出して、ツール バーに関連付けられたイメージを読み込みます。 このメソッドをオーバーライドして、イメージ リソースのカスタムの読み込みを実行します。

ツール バーの作成後に、 `LoadBitmapEx` メソッドを呼び出して追加のイメージを読み込みます。

## <a name="cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a>ツールバー::読み込みツールバー

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

[in]*UIResID*<br/>

[in]*をクリックします。*<br/>

[in]*をクリックします。*<br/>

[in]*ブール*<br/>

[in]*を無効にします。*<br/>

[in]*を無効にします。*<br/>

[in]*をクリックします。*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a>コントロールバー::オンルボタンアップ

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

[in]*nフラグ*<br/>

[in]*ポイント*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a>コントロール バー::マウス移動時

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

[in]*nフラグ*<br/>

[in]*ポイント*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a>ツールバー::オンセンドコマンド

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>パラメーター

[in]*ボタン*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>コントロール バー::オンアップデートCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>パラメーター

[in]*pターゲット*<br/>

[in]*ノフドラー*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCツールバー::作成](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[ボタンを置き換える](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[クラスをドロップダウンダウンツール バーボタン](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)
