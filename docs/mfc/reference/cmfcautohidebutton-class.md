---
title: CMFCAutoHideButton クラス
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
helpviewer_keywords:
- CMFCAutoHideButton [MFC], BringToTop
- CMFCAutoHideButton [MFC], Create
- CMFCAutoHideButton [MFC], GetAlignment
- CMFCAutoHideButton [MFC], GetAutoHideWindow
- CMFCAutoHideButton [MFC], GetParentToolBar
- CMFCAutoHideButton [MFC], GetRect
- CMFCAutoHideButton [MFC], GetSize
- CMFCAutoHideButton [MFC], GetTextSize
- CMFCAutoHideButton [MFC], HighlightButton
- CMFCAutoHideButton [MFC], IsActive
- CMFCAutoHideButton [MFC], IsHighlighted
- CMFCAutoHideButton [MFC], IsHorizontal
- CMFCAutoHideButton [MFC], IsTop
- CMFCAutoHideButton [MFC], IsVisible
- CMFCAutoHideButton [MFC], Move
- CMFCAutoHideButton [MFC], OnDraw
- CMFCAutoHideButton [MFC], OnDrawBorder
- CMFCAutoHideButton [MFC], OnFillBackground
- CMFCAutoHideButton [MFC], ReplacePane
- CMFCAutoHideButton [MFC], ShowAttachedWindow
- CMFCAutoHideButton [MFC], ShowButton
- CMFCAutoHideButton [MFC], UnSetAutoHideMode
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
ms.openlocfilehash: 3ea6ce13b8cca7e0130fe14459a832b476391b0c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751676"
---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton クラス

非表示になるように構成されている [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) を表示または非表示にするボタンです。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCAutoHideButton::BringToTop](#bringtotop)||
|[CMFCAutoHideButton::Create](#create)|自動的に隠すボタンを作成して初期化します。|
|[CMFCAutoHideButton::GetAlignment](#getalignment)|自動的に隠すボタンの配置を取得します。|
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|自動非表示ボタンに関連付けられている[CDockablePane](../../mfc/reference/cdockablepane-class.md)オブジェクトを返します。|
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton::GetRect](#getrect)||
|[CMFCAutoHideButton::GetSize](#getsize)|自動的に隠すボタンのサイズを調べます。|
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|自動的に隠すボタンのテキスト ラベルのサイズを返します。|
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|自動的に隠すボタンを強調表示します。|
|[CMFCAutoHideButton::IsActive](#isactive)|自動的に隠すボタンがアクティブかどうかを示します。|
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|自動的に隠すボタンの強調表示状態を返します。|
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|自動的に隠すボタンの表示方向が水平と垂直のどちらであるかを判断します。|
|[CMFCAutoHideButton::IsTop](#istop)||
|[CMFCAutoHideButton::IsVisible](#isvisible)|ボタンが表示されるかどうかを示します。|
|[CMFCAutoHideButton::Move](#move)||
|[CMFCAutoHideButton::OnDraw](#ondraw)|フレームワークは、自動的に隠すボタンを描画するときにこのメソッドを呼び出します。|
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|フレームワークは、自動的に隠すボタンの境界線を描画するときにこのメソッドを呼び出します。|
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|フレームワークは、自動的に隠すボタンの背景を塗りつぶすときにこのメソッドを呼び出します。|
|[CMFCAutoHideButton::ReplacePane](#replacepane)||
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|関連付けられた[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)を表示または非表示にします。|
|[CMFCAutoHideButton::ShowButton](#showbutton)|自動的に隠すボタンの表示と非表示を切り替えます。|
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>解説

作成時に`CMFCAutoHideButton`、オブジェクトは[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)にアタッチされます。 ユーザーが `CMFCAutoHideButton` オブジェクトと対話操作を行うと、`CDockablePane` オブジェクトの非表示と表示が切り替えられます。

既定では、ユーザーが自動非表示をオンにすると、フレームワークが自動的に `CMFCAutoHideButton` を作成します。 フレームワークは、`CMFCAutoHideButton` クラスではなく、カスタム UI クラスの要素を作成できます。 フレームワークが使用するカスタム UI クラスを指定するには、静的メンバー変数 `CMFCAutoHideBar::m_pAutoHideButtonRTS` をカスタム UI クラスと等しくなるように設定します。 既定では、この変数は `CMFCAutoHideButton` に設定されます。

## <a name="example"></a>例

`CMFCAutoHideButton` オブジェクトを構築して `CMFCAutoHideButton` クラスのさまざまなメソッドを使用する方法を次の例に示します。 この例では、`Create` メソッドを使用して `CMFCAutoHideButton` オブジェクトを初期化する方法、関連付けられている `CDockablePane` クラスを表示する方法、および自動非表示ボタンを表示する方法を示しています。

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxautohidebutton.h

## <a name="cmfcautohidebuttonbringtotop"></a><a name="bringtotop"></a>CMFCオートハイドボタン::ブリングトップ

```cpp
void BringToTop();
```

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttoncreate"></a><a name="create"></a>CMFC自動隠しボタン::作成

自動非表示ボタンを作成および初期化します。

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

*バー*<br/>
[in]親ツール バーへのポインター。

*を自動非表示にする*<br/>
[in][オブジェクト](../../mfc/reference/cdockablepane-class.md)へのポインター。 この自動非表示ボタンは、その`CDockablePane`を非表示にして表示します。

*dw配置*<br/>
[in]ボタンとメイン フレーム ウィンドウの配置を指定する値。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

オブジェクトを作成する`CMFCAutoHideButton`場合は、自動非表示ボタンを特定`CDockablePane`の . ユーザーは自動非表示ボタンを使用して、関連付けられている`CDockablePane`を非表示にしたり、表示することができます。

*dwAlignment*パラメーターは、アプリケーション内の自動非表示ボタンの位置を示します。 このパラメーターは次のいずれかの値に設定できます。

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetalignment"></a><a name="getalignment"></a>CMFC 自動ハイドボタン::取得配置

自動的に隠すボタンの配置を取得します。

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>戻り値

自動非表示ボタンの現在の配置を格納する DWORD 値。

### <a name="remarks"></a>解説

自動非表示ボタンの配置は、アプリケーション上のボタンの位置を示します。 次のいずれかの値を指定できます。

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetautohidewindow"></a><a name="getautohidewindow"></a>CMFC 自動ハイドボタン::取得自動ハイドウィンドウ

自動非表示ボタンに関連付けられている[CDockablePane](../../mfc/reference/cdockablepane-class.md)オブジェクトを返します。

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>戻り値

関連付けられた`CDockablePane`オブジェクトへのポインター。

### <a name="remarks"></a>解説

自動非表示ボタンを`CDockablePane`に関連付けるには、`CDockablePane`パラメーターとして[CMFCAutoHideButton::Create](#create)メソッドに渡します。

## <a name="cmfcautohidebuttongetparenttoolbar"></a><a name="getparenttoolbar"></a>コントロール バーの自動非表示ボタン

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttongetrect"></a><a name="getrect"></a>CMFC 自動ハイドボタン::ゲットレック

```
CRect GetRect() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttongetsize"></a><a name="getsize"></a>CMFC 自動ハイドボタン::取得サイズ

自動的に隠すボタンのサイズを調べます。

```
CSize GetSize() const;
```

### <a name="return-value"></a>戻り値

ボタン`CSize`のサイズを格納するオブジェクト。

### <a name="remarks"></a>解説

計算されたサイズには、自動非表示ボタンの境界線のサイズが含まれます。

## <a name="cmfcautohidebuttongettextsize"></a><a name="gettextsize"></a>CMFC 自動ハイドボタン::テキストサイズを取得します。

自動的に隠すボタンのテキスト ラベルのサイズを返します。

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>戻り値

自動非表示ボタンのテキストのサイズを格納する[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

## <a name="cmfcautohidebuttonisactive"></a><a name="isactive"></a>CMFC 自動ハイドボタン::IsActive

自動的に隠すボタンがアクティブかどうかを示します。

```
BOOL IsActive() const;
```

### <a name="return-value"></a>戻り値

自動非表示ボタンがアクティブな場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

関連付けられた[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)ウィンドウが表示されている場合、自動非表示ボタンがアクティブになります。

## <a name="cmfcautohidebuttonishorizontal"></a><a name="ishorizontal"></a>CMFCオートハイドボタン::イス水平

自動的に隠すボタンの表示方向が水平と垂直のどちらであるかを判断します。

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>戻り値

ボタンが水平の場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

フレームワークは、作成時に[CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)オブジェクトの向きを設定します。  方向を制御するには[、CMFCAutoHideButton::Create](#create)メソッドの*dwAlignment*パラメーターを使用します。

## <a name="cmfcautohidebuttonistop"></a><a name="istop"></a>CMFCオートハイドボタン::イズトップ

```
BOOL IsTop() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonisvisible"></a><a name="isvisible"></a>CMFC自動ハイドボタン::イズビジブル

自動非表示ボタンが表示されているかどうかを示します。

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>戻り値

ボタンが表示されている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcautohidebuttonondraw"></a><a name="ondraw"></a>CMFC自動ハイドボタン::オンドロー

フレームワークは、自動的に隠すボタンを描画するときにこのメソッドを呼び出します。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

アプリケーションの自動非表示ボタンの外観をカスタマイズする場合は、 から`CMFCAutoHideButton`派生した新しいクラスを作成します。 派生クラスで、このメソッドをオーバーライドします。

## <a name="cmfcautohidebuttonondrawborder"></a><a name="ondrawborder"></a>CMFCオートハイドボタン::オンドローボーダー

フレームワークは、自動的に隠すボタンの境界線を描画するときにこのメソッドを呼び出します。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*レクトバウンド*<br/>
[in]自動非表示ボタンの外接する四角形。

*レクトボーダーサイズ*<br/>
[in]自動非表示ボタンの各辺の境界線の太さ。

### <a name="remarks"></a>解説

アプリケーションの各自動非表示ボタンの境界線をカスタマイズする場合は、 から派生した新しいクラスを作成します`CMFCAutoHideButton`。 派生クラスで、このメソッドをオーバーライドします。

## <a name="cmfcautohidebuttononfillbackground"></a><a name="onfillbackground"></a>CMFCオートハイドボタン::オンフィルバックグラウンド

フレームワークは、自動的に隠すボタンの背景を塗りつぶすときにこのメソッドを呼び出します。

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]自動非表示ボタンの外接する四角形。

### <a name="remarks"></a>解説

アプリケーションの自動非表示ボタンの背景をカスタマイズする場合は、 から派生した新しいクラスを作成します`CMFCAutoHideButton`。 派生クラスで、このメソッドをオーバーライドします。

## <a name="cmfcautohidebuttonshowattachedwindow"></a><a name="showattachedwindow"></a>CMFC自動ハイドボタン::添付ウィンドウを表示

関連付けられた[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)を表示または非表示にします。

```cpp
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
[in]このメソッドが添付された`CDockablePane`を表示するかどうかを指定するブール値。

## <a name="cmfcautohidebuttonshowbutton"></a><a name="showbutton"></a>CMFC自動ハイドボタン::ショーボタン

自動的に隠すボタンの表示と非表示を切り替えます。

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
[in]自動非表示ボタンを表示するかどうかを指定するブール値。

## <a name="cmfcautohidebuttonmove"></a><a name="move"></a>CMFC自動ハイドボタン::移動

```cpp
void Move(int nOffset);
```

### <a name="parameters"></a>パラメーター

[in]*オフセット*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonreplacepane"></a><a name="replacepane"></a>CMFC自動隠しボタン::ペインを置き換える

```cpp
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonunsetautohidemode"></a><a name="unsetautohidemode"></a>CMFC 自動ハイドボタン::自動隠しモードを設定解除

自動的に隠すモードを無効にします。

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>パラメーター

*グループ*<br/>
[in]グループ内の最初のバーへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonhighlightbutton"></a><a name="highlightbutton"></a>CMFCオートハイドボタン::ハイライトボタン

自動非表示ボタンを強調表示します。

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>パラメーター

*bハイライト*<br/>
新しい自動非表示ボタンの状態を指定します。 TRUE は、ボタンが強調表示されていることを示し、FALSE は、ボタンが強調表示されないことを示します。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonishighlighted"></a><a name="ishighlighted"></a>CMFC自動ハイドボタン::ハイライト

自動非表示ボタンの強調表示状態を返します。

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>戻り値

自動非表示ボタンが強調表示されている場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAutoHideBar クラス](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[クラスを自動非表示にする](../../mfc/reference/cautohidedocksite-class.md)
