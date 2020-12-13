---
description: '詳細情報: CMFCAutoHideButton クラス'
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
ms.openlocfilehash: 9d100417193ea8a757b02b9cc8fad0cdedf668f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336575"
---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton クラス

非表示になるように構成されている [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) を表示または非表示にするボタンです。

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

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
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|自動的に隠すボタンに関連付けられている [CDockablePane](../../mfc/reference/cdockablepane-class.md) オブジェクトを返します。|
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
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|関連付けられている [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)の表示と非表示を切り替えます。|
|[CMFCAutoHideButton::ShowButton](#showbutton)|自動的に隠すボタンの表示と非表示を切り替えます。|
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>解説

作成時に、 `CMFCAutoHideButton` オブジェクトは [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)にアタッチされます。 ユーザーが `CMFCAutoHideButton` オブジェクトと対話操作を行うと、`CDockablePane` オブジェクトの非表示と表示が切り替えられます。

既定では、ユーザーが自動非表示をオンにすると、フレームワークが自動的に `CMFCAutoHideButton` を作成します。 フレームワークは、`CMFCAutoHideButton` クラスではなく、カスタム UI クラスの要素を作成できます。 フレームワークが使用するカスタム UI クラスを指定するには、静的メンバー変数 `CMFCAutoHideBar::m_pAutoHideButtonRTS` をカスタム UI クラスと等しくなるように設定します。 既定では、この変数は `CMFCAutoHideButton` に設定されます。

## <a name="example"></a>例

`CMFCAutoHideButton` オブジェクトを構築して `CMFCAutoHideButton` クラスのさまざまなメソッドを使用する方法を次の例に示します。 この例では、`Create` メソッドを使用して `CMFCAutoHideButton` オブジェクトを初期化する方法、関連付けられている `CDockablePane` クラスを表示する方法、および自動非表示ボタンを表示する方法を示しています。

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>要件

**ヘッダー:** afxautohidebutton.h

## <a name="cmfcautohidebuttonbringtotop"></a><a name="bringtotop"></a> CMFCAutoHideButton:: BringToTop

```cpp
void BringToTop();
```

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttoncreate"></a><a name="create"></a> CMFCAutoHideButton:: Create

自動的に隠すボタンを作成し、初期化します。

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

*pParentBar*<br/>
から親ツールバーへのポインター。

*pAutoHideWnd*<br/>
から [CDockablePane](../../mfc/reference/cdockablepane-class.md) オブジェクトへのポインター。 この自動非表示ボタンをクリックすると、が表示さ `CDockablePane` れます。

*dwAlignment*<br/>
からメインフレームウィンドウでのボタンの配置を指定する値。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

オブジェクトを作成するときは、 `CMFCAutoHideButton` 自動的に隠すボタンを特定のに関連付ける必要があり `CDockablePane` ます。 ユーザーは、[自動的に隠す] ボタンを使用して、関連付けられているを非表示にしたり表示したりでき `CDockablePane` ます。

*DwAlignment* パラメーターは、自動的に隠すボタンがアプリケーション内に存在する場所を示します。 このパラメーターは次のいずれかの値に設定できます。

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetalignment"></a><a name="getalignment"></a> CMFCAutoHideButton:: GetAlignment

自動的に隠すボタンの配置を取得します。

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>戻り値

自動的に隠すボタンの現在の配置を含む DWORD 値です。

### <a name="remarks"></a>解説

[自動的に隠す] ボタンの配置は、アプリケーション上のボタンが存在する場所を示します。 次のいずれかの値を指定できます。

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetautohidewindow"></a><a name="getautohidewindow"></a> CMFCAutoHideButton:: GetAutoHideWindow

自動的に隠すボタンに関連付けられている [CDockablePane](../../mfc/reference/cdockablepane-class.md) オブジェクトを返します。

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>戻り値

関連付けられたオブジェクトへのポインター `CDockablePane` 。

### <a name="remarks"></a>解説

自動的に隠すボタンをと関連付けるには、を `CDockablePane` `CDockablePane` パラメーターとして [Cmfcautohidebutton:: Create](#create) メソッドに渡します。

## <a name="cmfcautohidebuttongetparenttoolbar"></a><a name="getparenttoolbar"></a> CMFCAutoHideButton:: GetParentToolBar

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttongetrect"></a><a name="getrect"></a> CMFCAutoHideButton:: GetRect

```
CRect GetRect() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttongetsize"></a><a name="getsize"></a> CMFCAutoHideButton:: GetSize

自動的に隠すボタンのサイズを調べます。

```
CSize GetSize() const;
```

### <a name="return-value"></a>戻り値

`CSize`ボタンのサイズを格納しているオブジェクト。

### <a name="remarks"></a>解説

計算されたサイズには、自動的に隠すボタンの境界線のサイズが含まれます。

## <a name="cmfcautohidebuttongettextsize"></a><a name="gettextsize"></a> CMFCAutoHideButton:: GetTextSize パラメーター化

自動的に隠すボタンのテキスト ラベルのサイズを返します。

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>戻り値

自動的に隠すボタンのテキストのサイズを格納している [CSize](../../atl-mfc-shared/reference/csize-class.md) オブジェクト。

## <a name="cmfcautohidebuttonisactive"></a><a name="isactive"></a> CMFCAutoHideButton:: IsActive

自動的に隠すボタンがアクティブかどうかを示します。

```
BOOL IsActive() const;
```

### <a name="return-value"></a>戻り値

自動的に隠すボタンがアクティブである場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

関連付けられている [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md) ウィンドウが表示されると、自動的に隠すボタンがアクティブになります。

## <a name="cmfcautohidebuttonishorizontal"></a><a name="ishorizontal"></a> CMFCAutoHideButton:: IsHorizontal

自動的に隠すボタンの表示方向が水平と垂直のどちらであるかを判断します。

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>戻り値

ボタンが水平の場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

このフレームワークは、作成時に [Cmfcautohidebutton](../../mfc/reference/cmfcautohidebutton-class.md) オブジェクトの向きを設定します。  この方向を制御するには、 [Cmfcautohidebutton:: Create](#create)メソッドで *dwAlignment* パラメーターを使用します。

## <a name="cmfcautohidebuttonistop"></a><a name="istop"></a> CMFCAutoHideButton:: IsTop

```
BOOL IsTop() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonisvisible"></a><a name="isvisible"></a> CMFCAutoHideButton:: IsVisible

自動的に隠すボタンを表示するかどうかを示します。

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>戻り値

ボタンが表示される場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcautohidebuttonondraw"></a><a name="ondraw"></a> CMFCAutoHideButton:: OnDraw

フレームワークは、自動的に隠すボタンを描画するときにこのメソッドを呼び出します。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

### <a name="remarks"></a>解説

アプリケーションで自動的に隠すボタンの外観をカスタマイズする場合は、から派生した新しいクラスを作成 `CMFCAutoHideButton` します。 派生クラスで、このメソッドをオーバーライドします。

## <a name="cmfcautohidebuttonondrawborder"></a><a name="ondrawborder"></a> CMFCAutoHideButton:: OnDrawBorder

フレームワークは、自動的に隠すボタンの境界線を描画するときにこのメソッドを呼び出します。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rectBounds*<br/>
から自動的に隠すボタンの外接する四角形。

*rectBorderSize*<br/>
から[自動的に隠す] ボタンの横の境界線の太さ。

### <a name="remarks"></a>解説

アプリケーションの各自動非表示ボタンの境界線をカスタマイズする場合は、から派生した新しいクラスを作成し `CMFCAutoHideButton` ます。 派生クラスで、このメソッドをオーバーライドします。

## <a name="cmfcautohidebuttononfillbackground"></a><a name="onfillbackground"></a> CMFCAutoHideButton:: OnFillBackground

フレームワークは、自動的に隠すボタンの背景を塗りつぶすときにこのメソッドを呼び出します。

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rect*<br/>
から自動的に隠すボタンの外接する四角形。

### <a name="remarks"></a>解説

アプリケーションで自動的に隠すボタンの背景をカスタマイズする場合は、から派生した新しいクラスを作成し `CMFCAutoHideButton` ます。 派生クラスで、このメソッドをオーバーライドします。

## <a name="cmfcautohidebuttonshowattachedwindow"></a><a name="showattachedwindow"></a> CMFCAutoHideButton:: ShowAttachedWindow

関連付けられている [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)の表示と非表示を切り替えます。

```cpp
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
からこのメソッドが、アタッチされたを表示するかどうかを指定するブール値 `CDockablePane` 。

## <a name="cmfcautohidebuttonshowbutton"></a><a name="showbutton"></a> CMFCAutoHideButton:: ShowButton

自動的に隠すボタンの表示と非表示を切り替えます。

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
から自動的に隠すボタンを表示するかどうかを指定するブール値。

## <a name="cmfcautohidebuttonmove"></a><a name="move"></a> CMFCAutoHideButton:: Move

```cpp
void Move(int nOffset);
```

### <a name="parameters"></a>パラメーター

から *Noffset*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonreplacepane"></a><a name="replacepane"></a> CMFCAutoHideButton:: ReplacePane

```cpp
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>パラメーター

から *Pnewbar*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonunsetautohidemode"></a><a name="unsetautohidemode"></a> CMFCAutoHideButton:: UnSetAutoHideMode

自動的に隠すモードを無効にします。

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>パラメーター

*pFirstBarInGroup*<br/>
からグループ内の最初のバーへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonhighlightbutton"></a><a name="highlightbutton"></a> CMFCAutoHideButton:: HighlightButton

[自動的に隠す] ボタンを強調表示します。

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>パラメーター

*bHighlight 表示*<br/>
新しい [自動的に隠す] ボタンの状態を指定します。 TRUE はボタンが強調表示されていることを示し、FALSE はボタンが強調表示されていないことを示します。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebuttonishighlighted"></a><a name="ishighlighted"></a> CMFCAutoHideButton:: IsHighlighted

[自動的に隠す] ボタンの強調表示の状態を返します。

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>戻り値

[自動的に隠す] ボタンが強調表示されている場合に TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAutoHideBar クラス](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[CAutoHideDockSite クラス](../../mfc/reference/cautohidedocksite-class.md)
