---
title: CMFCButton クラス
ms.date: 08/28/2018
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
helpviewer_keywords:
- CMFCButton [MFC], CleanUp
- CMFCButton [MFC], EnableFullTextTooltip
- CMFCButton [MFC], EnableMenuFont
- CMFCButton [MFC], EnableWindowsTheming
- CMFCButton [MFC], GetToolTipCtrl
- CMFCButton [MFC], IsAutoCheck
- CMFCButton [MFC], IsAutorepeatCommandMode
- CMFCButton [MFC], IsCheckBox
- CMFCButton [MFC], IsChecked
- CMFCButton [MFC], IsHighlighted
- CMFCButton [MFC], IsPressed
- CMFCButton [MFC], IsPushed
- CMFCButton [MFC], IsRadioButton
- CMFCButton [MFC], IsWindowsThemingEnabled
- CMFCButton [MFC], SetAutorepeatMode
- CMFCButton [MFC], SetCheckedImage
- CMFCButton [MFC], SetFaceColor
- CMFCButton [MFC], SetImage
- CMFCButton [MFC], SetMouseCursor
- CMFCButton [MFC], SetMouseCursorHand
- CMFCButton [MFC], SetStdImage
- CMFCButton [MFC], SetTextColor
- CMFCButton [MFC], SetTextHotColor
- CMFCButton [MFC], SetTooltip
- CMFCButton [MFC], SizeToContent
- CMFCButton [MFC], OnDraw
- CMFCButton [MFC], OnDrawBorder
- CMFCButton [MFC], OnDrawFocusRect
- CMFCButton [MFC], OnDrawText
- CMFCButton [MFC], OnFillBackground
- CMFCButton [MFC], SelectFont
- CMFCButton [MFC], m_bDrawFocus
- CMFCButton [MFC], m_bHighlightChecked
- CMFCButton [MFC], m_bRightImage
- CMFCButton [MFC], m_bTransparent
- CMFCButton [MFC], m_nAlignStyle
- CMFCButton [MFC], m_nFlatStyle
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
ms.openlocfilehash: 0659e5335e1ebc495280a4e0cb5c0167f3b45e1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403829"
---
# <a name="cmfcbutton-class"></a>CMFCButton クラス

`CMFCButton`クラスに機能を追加する、 [CButton](../../mfc/reference/cbutton-class.md)ボタン テキストの配置、ボタンのテキストとイメージの組み合わせ、カーソルの選択、ツール ヒントの指定などのクラス。

## <a name="syntax"></a>構文

```
class CMFCButton : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCButton::CMFCButton`|既定のコンストラクターです。|
|`CMFCButton::~CMFCButton`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCButton::CleanUp](#cleanup)|内部変数をリセットし、イメージ、ビットマップ、アイコンなどの割り当てられたリソースを解放します。|
|`CMFCButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCButton::DrawItem`|オーナー描画ボタンの外観が変更されたときに、フレームワークによって呼び出されます。 (上書き[CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem))。|
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|大規模なツールヒント ウィンドウまたは小規模なツールヒント ウィンドウのテキストの切り捨てられたバージョンでツールヒントのテキスト全体を表示するかどうかを指定します。|
|[CMFCButton::EnableMenuFont](#enablemenufont)|ボタン テキストのフォントがアプリケーション メニューのフォントと同じであるかどうかを指定します。|
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|ボタンの境界線のスタイルを現在の Windows テーマに対応するかどうかを指定します。|
|`CMFCButton::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|基になるツールヒント コントロールへの参照を返します。|
|[CMFCButton::IsAutoCheck](#isautocheck)|チェック ボックスまたはラジオ ボタンが自動のボタンであるかどうかを示します。|
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|ボタンが 自動繰り返しのモードに設定されているかどうかを示します。|
|[CMFCButton::IsCheckBox](#ischeckbox)|ボタンがチェック ボックス ボタンであるかどうかを示します。|
|[CMFCButton::IsChecked](#ischecked)|現在のボタンがオンになっているかどうかを示します。|
|[CMFCButton::IsHighlighted](#ishighlighted)|ボタンが強調表示されているかどうかを示します。|
|[CMFCButton::IsPressed](#ispressed)|ボタンがプッシュされ、強調表示されているかどうかを示します。|
|[CMFCButton::IsPushed](#ispushed)|ボタンがクリックしてされているかどうかを示します。|
|[CMFCButton::IsRadioButton](#isradiobutton)|ボタンがラジオ ボタンであるかどうかを示します。|
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|ボタンの境界線のスタイルを現在の Windows テーマに対応するかどうかを示します。|
|`CMFCButton::OnDrawParentBackground`|指定された領域では、ボタンの親の背景を描画します。 (上書き[AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|
|`CMFCButton::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 関数。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|ボタンを自動繰り返しモードに設定します。|
|[CMFCButton::SetCheckedImage](#setcheckedimage)|チェックされているボタンのイメージを設定します。|
|[CMFCButton::SetFaceColor](#setfacecolor)|ボタンのテキストの背景色を設定します。|
|[CMFCButton::SetImage](#setimage)|ボタンのイメージを設定します。|
|[CMFCButton::SetMouseCursor](#setmousecursor)|カーソルのイメージを設定します。|
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|手の形のイメージにカーソルを設定します。|
|[CMFCButton::SetStdImage](#setstdimage)|使用して、`CMenuImages`ボタンのイメージを設定するオブジェクト。|
|[CMFCButton::SetTextColor](#settextcolor)|選択されていないボタンのボタンのテキストの色を設定します。|
|[CMFCButton::SetTextHotColor](#settexthotcolor)|選択されているボタンのボタンのテキストの色を設定します。|
|[CMFCButton::SetTooltip](#settooltip)|ボタン、ツールヒントに関連付けます。|
|[CMFCButton::SizeToContent](#sizetocontent)|ボタンのテキストおよびイメージを格納するためのボタンのサイズを変更します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCButton::OnDraw](#ondraw)|ボタンを描画するためにフレームワークによって呼び出されます。|
|[CMFCButton::OnDrawBorder](#ondrawborder)|ボタンの境界線を描画するためにフレームワークによって呼び出されます。|
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|ボタンのフォーカスされた四角形を描画するためにフレームワークによって呼び出されます。|
|[CMFCButton::OnDrawText](#ondrawtext)|ボタンのテキストを描画するためにフレームワークによって呼び出されます。|
|[CMFCButton::OnFillBackground](#onfillbackground)|ボタンのテキストの背景を描画するためにフレームワークによって呼び出されます。|
|[CMFCButton::SelectFont](#selectfont)|指定したデバイス コンテキストに関連付けられているフォントを取得します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|ボタンのテキストの配置を指定します。|
|[CMFCButton::m_bDontUseWinXPTheme](#m_bDontUseWinXPTheme)|Windows XP テーマを使用するかどうかを指定します。|
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|ボタンの周囲のフォーカス四角形を描画するかどうかを示します。|
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|ボーダーレス、フラットな半のフラットまたは 3D など、ボタンのスタイルを指定します。|
|[CMFCButton::m_bGrayDisabled](#m_bGrayDisabled)|TRUE の場合、淡色として描画する無効なボタンを有効にします。|
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|上にカーソルを重ねると、BS_CHECKBOX スタイルのボタンを強調表示するかどうかを示します。|
|[CMFCButton::m_bResponseOnButtonDown](#m_bResponseOnButtonDown)|ボタンを押すイベントに応答するかどうかを示します。|
|[CMFCButton::m_bRightImage](#m_brightimage)|ボタンの右側にあるイメージを表示するかどうかを示します。|
|[CMFCButton::m_bTopImage](#m_bTopImage)| ボタンの上にイメージであるかどうかを示します。|
|[CMFCButton::m_bTransparent](#m_btransparent)|ボタンが透明かどうかを示します。|
|[CMFCButton::m_bWasDblClk](#m_bWasDblClk)| イベントをダブルクリックして、最後にをクリックするかどうかを示します。|

## <a name="remarks"></a>Remarks

派生したその他の種類のボタンは、`CMFCButton`クラスなど、 [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md)ハイパーリンクをサポートするクラスと`CMFCColorButton`カラー ピッカー ダイアログ ボックスをサポートするクラス。

スタイルを`CMFCButton`オブジェクトは*3D*、*フラット*、*セミコロン フラット*または*罫線なし*します。 ボタンのテキストは、左、上、またはボタンの中心に配置できます。 実行時に、テキスト、画像、またはテキストおよびイメージ、ボタンが表示されるかどうかを制御できます。 ボタンにカーソルを合わせると、特定のカーソル イメージが表示されることを指定することもできます。

ボタン コントロールを作成、コード内で直接、またはを使用して、 **MFC クラス ウィザード**ツールとダイアログ ボックスのテンプレート。 ボタン コントロールを直接作成する場合は、追加、`CMFCButton`変数を呼び出して、コンス トラクター、アプリケーション、および`Create`のメソッド、`CMFCButton`オブジェクト。 使用する場合、 **MFC クラス ウィザード**、追加、`CButton`アプリケーションには、変数から変数の種類を変更および`CButton`に`CMFCButton`します。

ダイアログ ボックスのアプリケーションでの通知メッセージを処理するには、メッセージ マップ エントリと各通知のイベント ハンドラーを追加します。 によって送信された通知を`CMFCButton`オブジェクトは、によって送信されたものと同じ、`CButton`オブジェクト。

## <a name="example"></a>例

次の例は、さまざまなメソッドを使用して、ボタンのプロパティを構成する方法を示します、`CMFCButton`クラス。 この例は、[新しいコントロール サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxbutton.h

##  <a name="cleanup"></a>  CMFCButton::CleanUp

内部変数をリセットし、イメージ、ビットマップ、アイコンなどの割り当てられたリソースを解放します。

```
virtual void CleanUp();
```

##  <a name="enablefulltexttooltip"></a>  CMFCButton::EnableFullTextTooltip

大規模なツールヒント ウィンドウまたは小規模なツールヒント ウィンドウのテキストの切り捨てられたバージョンでツールヒントのテキスト全体を表示するかどうかを指定します。

```
void EnableFullTextTooltip(BOOL bOn=TRUE);
```

### <a name="parameters"></a>パラメーター

*bOn*<br/>
[in]すべてのテキストを表示する場合は TRUE切り捨て表示テキストには FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="enablemenufont"></a>  CMFCButton::EnableMenuFont

ボタン テキストのフォントがアプリケーション メニューのフォントと同じであるかどうかを指定します。

```
void EnableMenuFont(
    BOOL bOn=TRUE,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*bOn*<br/>
[in]ボタン テキストのフォントとしてアプリケーション メニューのフォントを使用する場合は TRUEシステム フォントを使用する場合は FALSE。 既定では TRUE です。

*bRedraw*<br/>
[in]画面をすぐに再描画する場合は TRUEそれ以外の場合、FALSE です。 既定では TRUE です。

### <a name="remarks"></a>Remarks

ボタン テキストのフォントを指定するこのメソッドを使用しない場合のフォントを指定できます、 [cwnd::setfont](../../mfc/reference/cwnd-class.md#setfont)メソッド。 フォントがまったく指定しない場合、フレームワークは、既定のフォントを設定します。

##  <a name="enablewindowstheming"></a>  CMFCButton::EnableWindowsTheming

ボタンの境界線のスタイルを現在の Windows テーマに対応するかどうかを指定します。

```
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
[in]ボタンの境界線を描画するために、現在の Windows テーマを使用する場合は TRUEWindows テーマを使用しない場合は FALSE。 既定では TRUE です。

### <a name="remarks"></a>Remarks

このメソッドから派生した、アプリケーションでのすべてのボタンの影響、`CMFCButton`クラス。

##  <a name="gettooltipctrl"></a>  CMFCButton::GetToolTipCtrl

基になるツールヒント コントロールへの参照を返します。

```
CToolTipCtrl& GetToolTipCtrl();
```

### <a name="return-value"></a>戻り値

基になるツール ヒント コントロールへの参照。

### <a name="remarks"></a>Remarks

##  <a name="isautocheck"></a>  CMFCButton::IsAutoCheck

チェック ボックスまたはラジオ ボタンが自動のボタンであるかどうかを示します。

```
BOOL IsAutoCheck() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、ボタンにスタイル BS_AUTOCHECKBOX または BS_AUTORADIOBUTTON;それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="isautorepeatcommandmode"></a>  CMFCButton::IsAutorepeatCommandMode

ボタンが 自動繰り返しのモードに設定されているかどうかを示します。

```
BOOL IsAutorepeatCommandMode() const;
```

### <a name="return-value"></a>戻り値

ボタンが 自動繰り返しモードに設定されている場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

使用して、 [CMFCButton::SetAutorepeatMode](#setautorepeatmode)ボタンを自動繰り返しモードに設定します。

##  <a name="ischeckbox"></a>  CMFCButton::IsCheckBox

ボタンがチェック ボックス ボタンであるかどうかを示します。

```
BOOL IsCheckBox() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、ボタンに BS_CHECKBOX または BS_AUTOCHECKBOX のいずれかのスタイル。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="ischecked"></a>  CMFCButton::IsChecked

現在のボタンがオンになっているかどうかを示します。

```
BOOL IsChecked() const;
```

### <a name="return-value"></a>戻り値

現在のボタンがチェックされている場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

フレームワークは、さまざまな種類のボタンをチェックすることを示すさまざまな方法を使用します。 たとえば、ドットが含まれている場合のオプション ボタンがチェックします。格納する場合は、チェック ボックスをオンにします、 **X**します。

##  <a name="ishighlighted"></a>  CMFCButton::IsHighlighted

ボタンが強調表示されているかどうかを示します。

```
BOOL IsHighlighted() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合は、ボタンが強調表示されます。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタンの上にマウス ボタンが強調表示されます。

##  <a name="ispressed"></a>  CMFCButton::IsPressed

ボタンがプッシュされ、強調表示されているかどうかを示します。

```
BOOL IsPressed() const;
```

### <a name="return-value"></a>戻り値

ボタンが押された; は、TRUE を返します。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="ispushed"></a>  CMFCButton::IsPushed

ボタンがクリックしてされているかどうかを示します。

```
BOOL IsPushed() const;
```

### <a name="return-value"></a>戻り値

ボタンが押されている場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="isradiobutton"></a>  CMFCButton::IsRadioButton

ボタンがラジオ ボタンであるかどうかを示します。

```
BOOL IsRadioButton() const;
```

### <a name="return-value"></a>戻り値

ボタンのスタイルが BS_RADIOBUTTON または BS_AUTORADIOBUTTON 以外の場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="iswindowsthemingenabled"></a>  CMFCButton::IsWindowsThemingEnabled

ボタンの境界線のスタイルを現在の Windows テーマに対応するかどうかを示します。

```
static BOOL IsWindowsThemingEnabled();
```

### <a name="return-value"></a>戻り値

ボタンの境界線のスタイルは、現在の Windows テーマに対応している場合は TRUE。それ以外の場合、FALSE です。

## <a name="a-namembdontusewinxptheme-cmfcbuttonmbdontusewinxptheme"></a><a name="m_bDontUseWinXPTheme"/> CMFCButton::m_bDontUseWinXPTheme

ボタンを描画するときに、Windows XP テーマを使用するかどうかを指定します。

```
BOOL m_bDontUseWinXPTheme;
```

##  <a name="m_bdrawfocus"></a>  CMFCButton::m_bDrawFocus

ボタンの周囲のフォーカス四角形を描画するかどうかを示します。

```
BOOL m_bDrawFocus;
```

### <a name="remarks"></a>Remarks

設定、`m_bDrawFocus`フレームワークは、ボタンのテキストを囲むフォーカス四角形を描画し、イメージの場合は、ボタンにフォーカスを指定する場合は TRUE をメンバー。

`CMFCButton`コンス トラクターを TRUE には、このメンバーを初期化します。

##  <a name="m_bGrayDisabled"></a>  CMFCButton::m_bGrayDisabled

TRUE の場合、淡色として描画する無効なボタンを有効にします。

```
BOOL m_bGrayDisabled;
```

##  <a name="m_bhighlightchecked"></a>  CMFCButton::m_bHighlightChecked

上にカーソルを重ねると、BS_CHECKBOX スタイルのボタンを強調表示するかどうかを示します。

```
BOOL m_bHighlightChecked;
```

### <a name="remarks"></a>Remarks

設定、`m_bHighlightChecked`メンバー上にマウスを重ねると、フレームワークが BS_CHECKBOX スタイルのボタンをハイライトことを指定する場合は TRUE にします。

##  <a name="m_bResponseOnButtonDown"></a> CMFCButton::m_bResponseOnButtonDown

ボタンを押すイベントに応答するかどうかを示します。

```
BOOL m_bResponseOnButtonDown;
```

##  <a name="m_brightimage"></a>  CMFCButton::m_bRightImage

ボタンの右側にあるイメージを表示するかどうかを示します。

```
BOOL m_bRightImage;
```

##  <a name="m_bTopImage"></a>  CMFCButton::m_bTopImage](#m_bTopImage)

ボタンの上にイメージであるかどうかを示します。

```
BOOL m_bTopImage;
```

### <a name="remarks"></a>Remarks

設定、`m_bRightImage`メンバーを TRUE に、フレームワークが、ボタンのテキスト ラベルの右側にボタンのイメージを表示するように指定します。

##  <a name="m_btransparent"></a>  CMFCButton::m_bTransparent

ボタンが透明かどうかを示します。

```
BOOL m_bTransparent;
```

### <a name="remarks"></a>Remarks

設定、`m_bTransparent`メンバーにするフレームワークは透明にボタンを指定する場合は TRUE。 `CMFCButton`コンス トラクターを FALSE には、このメンバーを初期化します。

##  <a name="m_nalignstyle"></a>  CMFCButton::m_nAlignStyle

ボタンのテキストの配置を指定します。

```
AlignStyle m_nAlignStyle;
```

### <a name="remarks"></a>Remarks

次のいずれかを使用して、`CMFCButton::AlignStyle`ボタンのテキストの配置を指定する列挙値。

|[値]|説明|
|-----------|-----------------|
|ALIGN_CENTER|(既定値)ボタンのテキスト、ボタンの中央に揃えて配置します。|
|ALIGN_LEFT|ボタンのテキスト、ボタンの左側に揃えて配置します。|
|ALIGN_RIGHT|ボタンのテキスト、ボタンの右側に揃えて配置します。|

`CMFCButton`コンス トラクターが ALIGN_CENTER にこのメンバーを初期化します。

##  <a name="m_bWasDblClk"></a>  CMFCButton::m_bWasDblClk](#m_bWasDblClk)|

イベントがダブルクリックで最後にをクリックするかどうかを示します |。

```
BOOL m_bWasDblClk;
```

##  <a name="m_nflatstyle"></a>  CMFCButton::m_nFlatStyle

ボーダーレス、フラットな半のフラットまたは 3D など、ボタンのスタイルを指定します。

```
FlatStyle  m_nFlatStyle;
```

### <a name="remarks"></a>Remarks

次の表、`CMFCButton::m_nFlatStyle`ボタンの外観を指定する列挙値。

|[値]|説明|
|-----------|-----------------|
|BUTTONSTYLE_3D|(既定値)高、3 次元の辺に、ボタンが表示されます。 ボタンがクリックされたときに、深くインデントに押すことをボタンが表示されます。|
|BUTTONSTYLE_FLAT|マウスがボタン上で停止することと、ボタン 2 次元が発生の辺はありません。 ボタンの上にマウスを置いたときに、低、3 次元の辺に、ボタンが表示されます。 ボタンがクリックされたときに、簡易インデントに押すことをボタンが表示されます。|
|BUTTONSTYLE_SEMIFLAT|低、3 次元の辺に、ボタンが表示されます。 ボタンがクリックされたときに、深くインデントに押すことをボタンが表示されます。|
|BUTTONSTYLE_NOBORDERS|ボタンは、辺発生したいないし、常に 2 次元が表示されます。 クリックしたとき、インデントに押すボタンが表示されません。|

`CMFCButton`コンス トラクターが BUTTONSTYLE_3D にこのメンバーを初期化します。

### <a name="example"></a>例

次の例の値を設定する方法を示します、`m_nFlatStyle`でメンバー変数、`CMFCButton`クラス。 この例は、[新しいコントロール サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]

##  <a name="ondraw"></a>  CMFCButton::OnDraw

ボタンを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*rect*<br/>
[in]ボタンの外接する四角形への参照。

*uiState*<br/>
[in]ボタンの現在の状態。 詳細については、次を参照してください。、`itemState`のメンバー、 [DRAWITEMSTRUCT 構造体](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)トピック。

### <a name="remarks"></a>Remarks

独自のコードを使用して、ボタンを描画するには、このメソッドをオーバーライドします。

##  <a name="ondrawborder"></a>  CMFCButton::OnDrawBorder

ボタンの境界線を描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*rectClient*<br/>
[in]ボタンの外接する四角形への参照。

*uiState*<br/>
[in]ボタンの現在の状態。 詳細については、次を参照してください。、`itemState`のメンバー、 [DRAWITEMSTRUCT 構造体](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)トピック。

### <a name="remarks"></a>Remarks

境界線を描画するために、独自のコードを使用するには、このメソッドをオーバーライドします。

##  <a name="ondrawfocusrect"></a>  CMFCButton::OnDrawFocusRect

ボタンのフォーカスされた四角形を描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*rectClient*<br/>
[in]ボタンの外接する四角形への参照。

### <a name="remarks"></a>Remarks

フォーカスされた四角形を描画するために、独自のコードを使用するには、このメソッドをオーバーライドします。

##  <a name="ondrawtext"></a>  CMFCButton::OnDrawText

ボタンのテキストを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawText(
    CDC* pDC,
    const CRect& rect,
    const CString& strText,
    UINT uiDTFlags,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*rect*<br/>
[in]ボタンの外接する四角形への参照。

*strText*<br/>
[in]描画するテキスト。

*uiDTFlags*<br/>
[in]テキストの書式設定する方法を指定するフラグ。 詳細については、次を参照してください。、*フォーマット*のパラメーター、 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)メソッド。

*uiState*<br/>
[in] 予約されています。

### <a name="remarks"></a>Remarks

独自のコードを使用して、ボタンのテキストを描画するには、このメソッドをオーバーライドします。

##  <a name="onfillbackground"></a>  CMFCButton::OnFillBackground

ボタンのテキストの背景を描画するためにフレームワークによって呼び出されます。

```
virtual void OnFillBackground(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*rectClient*<br/>
[in]ボタンの外接する四角形への参照。

### <a name="remarks"></a>Remarks

ボタンの背景を描画するために、独自のコードを使用するには、このメソッドをオーバーライドします。

##  <a name="selectfont"></a>  CMFCButton::SelectFont

指定したデバイス コンテキストに関連付けられているフォントを取得します。

```
virtual CFont* SelectFont(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

### <a name="return-value"></a>戻り値

独自のコードを使用して、フォントを取得するには、このメソッドをオーバーライドします。

### <a name="remarks"></a>Remarks

##  <a name="setautorepeatmode"></a>  CMFCButton::SetAutorepeatMode

ボタンを自動繰り返しモードに設定します。

```
void SetAutorepeatMode(int nTimeDelay=500);
```

### <a name="parameters"></a>パラメーター

*nTimeDelay*<br/>
[in]親ウィンドウに送信されるメッセージの間隔を示す負でない数値。 間隔はミリ秒単位で計測し、その既定値は 500 ミリ秒です。 自動繰り返しはメッセージ モードを無効にする、0 を指定します。

### <a name="remarks"></a>Remarks

このメソッドは、常に、ボタンが解放されるまで、親ウィンドウに WM_COMMAND メッセージを送信するボタンまたは*nTimeDelay*パラメーターが 0 に設定されます。

##  <a name="setcheckedimage"></a>  CMFCButton::SetCheckedImage

チェックされているボタンのイメージを設定します。

```
void SetCheckedImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetCheckedImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetCheckedImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>パラメーター

*hIcon*<br/>
[in]ビットマップと、新しいイメージのマスクを含むアイコンへのハンドルします。

*bAutoDestroy*<br/>
[in]ビットマップ リソースを自動的に破棄することを指定する場合は TRUEそれ以外の場合、FALSE です。 既定では TRUE です。

*hIconHot*<br/>
[in]選択した状態のイメージを含むアイコンへのハンドルします。

*hBitmap*<br/>
[in]選択されていない状態のイメージを含むビットマップへのハンドルします。

*hBitmapHot*<br/>
[in]選択した状態のイメージを含むビットマップへのハンドルします。

*bMap3dColors*<br/>
[in]ボタンの背景の透明色を指定しますつまり、ボタンのイメージ。 (192, 192, 192) の RGB 色の値を使用する場合は TRUEによって定義された色の値を使用する場合は FALSE`AFX_GLOBAL_DATA::clrBtnFace`します。

*uiBmpResId*<br/>
[in]選択されていないイメージのリソース ID。

*uiBmpHotResId*<br/>
[in]選択したイメージのリソース ID。

*hIconDisabled*<br/>
[in]無効なイメージのアイコンへのハンドルします。

*hBitmapDisabled*<br/>
[in]無効なイメージを含むビットマップへのハンドルします。

*uiBmpDsblResID*<br/>
[in]無効化されたビットマップのリソース ID。

*bAlphaBlend*<br/>
[in]アルファ チャネルを使用するのみの 32 ビット イメージを使用する場合は TrueFALSE のみのアルファ チャネル イメージを使用しないようにします。 既定では FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="setfacecolor"></a>  CMFCButton::SetFaceColor

ボタンのテキストの背景色を設定します。

```
void SetFaceColor(
    COLORREF crFace,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*crFace*<br/>
[in]RGB 色の値。

*bRedraw*<br/>
[in]画面をすぐに再描画する場合は TRUEそれ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドを使用すると、新しい (フェイス) ボタンの背景の塗りつぶしの色を定義します。 ときに、バック グラウンドでないので注意が入力、 [CMFCButton::m_bTransparent](#m_btransparent)メンバー変数は TRUE になります。

##  <a name="setimage"></a>  CMFCButton::SetImage

ボタンのイメージを設定します。

```
void SetImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>パラメーター

*hIcon*<br/>
[in]ビットマップと、新しいイメージのマスクを含むアイコンへのハンドルします。

*bAutoDestroy*<br/>
[in]ビットマップ リソースを自動的に破棄することを指定する場合は TRUEそれ以外の場合、FALSE です。 既定では TRUE です。

*hIconHot*<br/>
[in]選択した状態のイメージを含むアイコンへのハンドルします。

*hBitmap*<br/>
[in]選択されていない状態のイメージを含むビットマップへのハンドルします。

*hBitmapHot*<br/>
[in]選択した状態のイメージを含むビットマップへのハンドルします。

*uiBmpResId*<br/>
[in]選択されていないイメージのリソース ID。

*uiBmpHotResId*<br/>
[in]選択したイメージのリソース ID。

*bMap3dColors*<br/>
[in]ボタンの背景の透明色を指定しますつまり、ボタンのイメージ。 (192, 192, 192) の RGB 色の値を使用する場合は TRUEによって定義された色の値を使用する場合は FALSE`AFX_GLOBAL_DATA::clrBtnFace`します。

*hIconDisabled*<br/>
[in]無効なイメージのアイコンへのハンドルします。

*hBitmapDisabled*<br/>
[in]無効なイメージを含むビットマップへのハンドルします。

*uiBmpDsblResID*<br/>
[in]無効化されたビットマップのリソース ID。

*bAlphaBlend*<br/>
[in]アルファ チャネルを使用するのみの 32 ビット イメージを使用する場合は TrueFALSE のみのアルファ チャネル イメージを使用しないようにします。 既定では FALSE です。

### <a name="remarks"></a>Remarks

### <a name="example"></a>例

次の例では、さまざまなバージョンを使用する方法、`SetImage`メソッドで、`CMFCButton`クラス。 この例は、[新しいコントロール サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]

##  <a name="setmousecursor"></a>  CMFCButton::SetMouseCursor

カーソルのイメージを設定します。

```
void SetMouseCursor(HCURSOR hcursor);
```

### <a name="parameters"></a>パラメーター

*hcursor*<br/>
[in]カーソルのハンドル。

### <a name="remarks"></a>Remarks

このメソッドを使用して、ボタンとハンド カーソルをなど、カーソルのイメージを関連付けます。 カーソルは、アプリケーション リソースから読み込まれます。

### <a name="example"></a>例

次の例では、使用する方法、`SetMouseCursor`メソッドで、`CMFCButton`クラス。 内のコード例は、[新しいコントロール サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]

##  <a name="setmousecursorhand"></a>  CMFCButton::SetMouseCursorHand

手の形のイメージにカーソルを設定します。

```
void SetMouseCursorHand();
```

### <a name="remarks"></a>Remarks

このメソッドを使用して、ボタンに手の形のカーソルのイメージを関連付けます。 カーソルは、アプリケーション リソースから読み込まれます。

##  <a name="setstdimage"></a>  CMFCButton::SetStdImage

使用して、`CMenuImages`ボタンのイメージを設定するオブジェクト。

```
void SetStdImage(
    CMenuImages::IMAGES_IDS id,
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```

### <a name="parameters"></a>パラメーター

*ID*<br/>
[in]定義されているボタン イメージの識別子のいずれか、`CMenuImage::IMAGES_IDS`列挙体。 イメージの値は、矢印、pin、ラジオ ボタンなどのイメージを指定します。

*state*<br/>
[in]定義されているボタンのイメージの状態の識別子のいずれか、`CMenuImages::IMAGE_STATE`列挙体。 イメージの状態は、黒、灰色、明るい灰色、白、および濃い灰色などのボタンの色を指定します。 既定値は `CMenuImages::ImageBlack` です。

*idDisabled*<br/>
[in]定義されているボタン イメージの識別子のいずれか、`CMenuImage::IMAGES_IDS`列挙体。 イメージは、ボタンが無効になっていることを示します。 既定値は、最初のボタンのイメージ ( `CMenuImages::IdArrowDown`)。

### <a name="remarks"></a>Remarks

##  <a name="settextcolor"></a>  CMFCButton::SetTextColor

選択されていないボタンのボタンのテキストの色を設定します。

```
void SetTextColor(COLORREF clrText);
```

### <a name="parameters"></a>パラメーター

*clrText*<br/>
[in]RGB 色の値。

### <a name="remarks"></a>Remarks

##  <a name="settexthotcolor"></a>  CMFCButton::SetTextHotColor

選択されているボタンのボタンのテキストの色を設定します。

```
void SetTextHotColor(COLORREF clrTextHot);
```

### <a name="parameters"></a>パラメーター

*clrTextHot*<br/>
[in]RGB 色の値。

### <a name="remarks"></a>Remarks

##  <a name="settooltip"></a>  CMFCButton::SetTooltip

ボタン、ツールヒントに関連付けます。

```
void SetTooltip(LPCTSTR lpszToolTipText);
```

### <a name="parameters"></a>パラメーター

*lpszToolTipText*<br/>
[in]ツールヒントのテキストへのポインター。 ツールヒントを無効にする NULL を指定します。

### <a name="remarks"></a>Remarks

##  <a name="sizetocontent"></a>  CMFCButton::SizeToContent

ボタンのテキストおよびイメージを格納するためのボタンのサイズを変更します。

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>パラメーター

*bCalcOnly*<br/>
[in]のボタンの新しいサイズを変更しないを計算する場合は TRUEボタンのサイズを変更する場合は FALSE。 既定では FALSE です。

### <a name="return-value"></a>戻り値

A`CSize`ボタンの新しいサイズを格納しているオブジェクト。

### <a name="remarks"></a>Remarks

既定では、このメソッドは、10 ピクセルの左右の余白と 5 ピクセルの縦の余白を含む新しいサイズを計算します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCLinkCtrl クラス](../../mfc/reference/cmfclinkctrl-class.md)<br/>
[CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)<br/>
[CMFCMenuButton クラス](../../mfc/reference/cmfcmenubutton-class.md)
