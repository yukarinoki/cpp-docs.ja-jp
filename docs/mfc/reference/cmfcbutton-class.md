---
title: クラス
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
ms.openlocfilehash: e949feaaac3570e1518cfb488cc1c42a471a1c46
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754877"
---
# <a name="cmfcbutton-class"></a>クラス

この`CMFCButton`クラスは、ボタン テキストの配置、ボタン テキストとイメージの結合、カーソルの選択、ツール ヒントの指定などの機能を[CButton](../../mfc/reference/cbutton-class.md)クラスに追加します。

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
|[CMFCボタン::クリーンアップ](#cleanup)|内部変数をリセットし、イメージ、ビットマップ、アイコンなどの割り当てられたリソースを解放します。|
|`CMFCButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCButton::DrawItem`|オーナー描画ボタンの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。 [(CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem)をオーバーライドします。|
|[ボタン::フルテキストツールチップを有効にします。](#enablefulltexttooltip)|ツールヒントのテキスト全体を大きなツールヒント ウィンドウに表示するか、小さなツールヒント ウィンドウに切り詰められたテキストを表示するかを指定します。|
|[メニューフォントを有効にする](#enablemenufont)|ボタンテキストフォントがアプリケーションメニューのフォントと同じかどうかを指定します。|
|[ボタン::イネーブルウィンドウステーマ](#enablewindowstheming)|ボタンの境界線のスタイルが現在の Windows テーマに対応するかどうかを指定します。|
|`CMFCButton::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[ツールチップを取得します。](#gettooltipctrl)|基になるツールヒント コントロールへの参照を返します。|
|[CMFCボタン::Isオートチェック](#isautocheck)|チェック ボックスまたはオプション ボタンが自動ボタンかどうかを示します。|
|[コントロール モード::自動繰り返しコマンド モード](#isautorepeatcommandmode)|ボタンが自動繰り返しモードに設定されているかどうかを示します。|
|[CMFCボタン::Isチェックボックス](#ischeckbox)|ボタンがチェック ボックス ボタンかどうかを示します。|
|[CMFCボタン::チェック](#ischecked)|現在のボタンがオンになっているかどうかを示します。|
|[CMFCボタン::ハイライト](#ishighlighted)|ボタンが強調表示されているかどうかを示します。|
|[CMFCボタン::イズプレス](#ispressed)|ボタンを押して強調表示するかどうかを示します。|
|[CMFCボタン::イズプッシュ](#ispushed)|ボタンが押されているかどうかを示します。|
|[ボタン::イスラジオボタン](#isradiobutton)|ボタンがラジオ ボタンかどうかを示します。|
|[ボタン::IsWindows テーマが有効です。](#iswindowsthemingenabled)|ボタンの境界線のスタイルが現在の Windows テーマに対応しているかどうかを示します。|
|`CMFCButton::OnDrawParentBackground`|指定した領域にボタンの親の背景を描画します。 (AFX_GLOBAL_DATAをオーバーライド[する:DrawParent背景](../../mfc/reference/afx-global-data-structure.md)|
|`CMFCButton::PreTranslateMessage`|ウィンドウ メッセージが変換メッセージおよびディスパッチ メッセージの Windows 関数にディスパッチされる前に、ウィンドウ[メッセージを](/windows/win32/api/winuser/nf-winuser-dispatchmessage)[変換](/windows/win32/api/winuser/nf-winuser-translatemessage)します。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[CMFCボタン::セットオートリピートモード](#setautorepeatmode)|ボタンを自動繰り返しモードに設定します。|
|[をクリックします。](#setcheckedimage)|チェックボタンのイメージを設定します。|
|[CMFCボタン::セットフェイスカラー](#setfacecolor)|ボタンテキストの背景色を設定します。|
|[をクリックします。](#setimage)|ボタンのイメージを設定します。|
|[ボタン::マウスカーソルを設定します。](#setmousecursor)|カーソルイメージを設定します。|
|[CMFCボタン::マウスカーソルハンド](#setmousecursorhand)|カーソルを手のイメージに設定します。|
|[をクリックします。](#setstdimage)|オブジェクトを`CMenuImages`使用してボタンイメージを設定します。|
|[コントロール::テキストの色を設定します。](#settextcolor)|選択されていないボタンのボタン テキストの色を設定します。|
|[CMFCボタン::セットテキストホットカラー](#settexthotcolor)|選択したボタンのボタン テキストの色を設定します。|
|[ツールチップの設定](#settooltip)|ツールヒントをボタンに関連付けます。|
|[コンテンツのサイズ](#sizetocontent)|ボタンのテキストとイメージを含むボタンのサイズを変更します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCボタン::オンドロー](#ondraw)|ボタンを描画するために、フレームワークによって呼び出されます。|
|[ウィンドウの境界線](#ondrawborder)|ボタンの境界線を描画するために、フレームワークによって呼び出されます。|
|[CMFCボタン::オンドローフォーカスレック](#ondrawfocusrect)|ボタンのフォーカス四角形を描画するために、フレームワークによって呼び出されます。|
|[ウィンドウボタン::オンドローテキスト](#ondrawtext)|ボタン テキストを描画するために、フレームワークによって呼び出されます。|
|[CMFCボタン::オンフィルバックグラウンド](#onfillbackground)|ボタン テキストの背景を描画するために、フレームワークによって呼び出されます。|
|[ボタン::フォントの選択](#selectfont)|指定したデバイス コンテキストに関連付けられているフォントを取得します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[M_nAlignStyle](#m_nalignstyle)|ボタン テキストの配置を指定します。|
|[コMFCボタン:m_bDontUseWinXPTheme](#m_bDontUseWinXPTheme)|Windows XP のテーマを使用するかどうかを指定します。|
|[CMFCボタン::m_bDrawFocus](#m_bdrawfocus)|ボタンの周囲にフォーカスの四角形を描画するかどうかを示します。|
|[CMFCボタン::m_nFlatStyle](#m_nflatstyle)|ボーダレス、フラット、半フラット、3D などのボタンのスタイルを指定します。|
|[CMFCボタン::m_bGrayDisabled](#m_bGrayDisabled)|TRUE の場合、無効なボタンをグレー表示で描画できます。|
|[CMFCボタン:m_bHighlightChecked](#m_bhighlightchecked)|カーソルをBS_CHECKBOXボタンの上に置いたときに、そのボタンを強調表示するかどうかを示します。|
|[CMFCボタン::m_bResponseOnButtonDown](#m_bResponseOnButtonDown)|ボタン ダウン イベントに応答するかどうかを示します。|
|[CMFCボタン::m_bRightImage](#m_brightimage)|ボタンの右側にイメージを表示するかどうかを示します。|
|[CMFCボタン::m_bTopImage](#m_bTopImage)| イメージがボタンの上にあるかどうかを示します。|
|[CMFCボタン::m_bTransparent](#m_btransparent)|ボタンが透明かどうかを示します。|
|[コM_BWASDBLCLKボタン](#m_bWasDblClk)| 最後のクリック イベントがダブルクリックであったかどうかを示します。|

## <a name="remarks"></a>解説

他の種類のボタンは、ハイパーリンク`CMFCButton`をサポートする[CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md)クラスや、カラー ピッカー ダイアログ`CMFCColorButton`ボックスをサポートするクラスなど、クラスから派生します。

オブジェクト`CMFCButton`のスタイルは *、3D*、*フラット*、*半フラット*、または*境界線なし*です。 ボタンテキストは、ボタンの左、上、または中央に揃えることができます。 実行時に、ボタンにテキスト、イメージ、またはテキストとイメージを表示するかどうかを制御できます。 また、カーソルがボタンの上に置いたときに、特定のカーソル イメージを表示することもできます。

コード内で直接、または**MFC クラス ウィザード**ツールとダイアログ ボックス テンプレートを使用して、ボタン コントロールを作成します。 ボタン コントロールを直接作成する場合は、`CMFCButton`アプリケーションに変数を追加し、オブジェクトのコンストラクターと`Create`メソッドを`CMFCButton`呼び出します。 MFC クラス**ウィザード**を使用する場合`CButton`は、アプリケーションに変数を追加し、変数の型を`CButton`に`CMFCButton`変更します。

ダイアログ ボックス アプリケーションで通知メッセージを処理するには、各通知のメッセージ マップ エントリとイベント ハンドラーを追加します。 `CMFCButton`オブジェクトによって送信される通知は、オブジェクトによって送信されるものと同`CButton`じです。

## <a name="example"></a>例

次の例は、クラスのさまざまなメソッドを使用してボタンのプロパティを構成する方法を`CMFCButton`示しています。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

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

## <a name="cmfcbuttoncleanup"></a><a name="cleanup"></a>CMFCボタン::クリーンアップ

内部変数をリセットし、イメージ、ビットマップ、アイコンなどの割り当てられたリソースを解放します。

```
virtual void CleanUp();
```

## <a name="cmfcbuttonenablefulltexttooltip"></a><a name="enablefulltexttooltip"></a>ボタン::フルテキストツールチップを有効にします。

ツールヒントのテキスト全体を大きなツールヒント ウィンドウに表示するか、小さなツールヒント ウィンドウに切り詰められたテキストを表示するかを指定します。

```cpp
void EnableFullTextTooltip(BOOL bOn=TRUE);
```

### <a name="parameters"></a>パラメーター

*ボン*<br/>
[in]すべてのテキストを表示する場合は TRUE。テキストを切り捨てる場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonenablemenufont"></a><a name="enablemenufont"></a>メニューフォントを有効にする

ボタンテキストフォントがアプリケーションメニューのフォントと同じかどうかを指定します。

```cpp
void EnableMenuFont(
    BOOL bOn=TRUE,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*ボン*<br/>
[in]アプリケーション メニューのフォントをボタン テキスト フォントとして使用する場合は TRUE。システム フォントを使用する場合は FALSE。 デフォルトは TRUE です。

*引き出し*<br/>
[in]直ちに画面を再描画する場合は TRUE。それ以外の場合は FALSE。 デフォルトは TRUE です。

### <a name="remarks"></a>解説

このメソッドを使用してボタンテキストのフォントを指定しない場合は[、CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont)メソッドを使用してフォントを指定できます。 フォントをまったく指定しない場合、フレームワークは既定のフォントを設定します。

## <a name="cmfcbuttonenablewindowstheming"></a><a name="enablewindowstheming"></a>ボタン::イネーブルウィンドウステーマ

ボタンの境界線のスタイルが現在の Windows テーマに対応するかどうかを指定します。

```
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]現在の Windows テーマを使用してボタンの境界線を描画する場合は TRUE。Windows テーマを使用しない場合は FALSE。 デフォルトは TRUE です。

### <a name="remarks"></a>解説

このメソッドは、クラスから派生したアプリケーションのすべてのボタンに影響`CMFCButton`します。

## <a name="cmfcbuttongettooltipctrl"></a><a name="gettooltipctrl"></a>ツールチップを取得します。

基になるツールヒント コントロールへの参照を返します。

```
CToolTipCtrl& GetToolTipCtrl();
```

### <a name="return-value"></a>戻り値

基になるツールヒント コントロールへの参照。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonisautocheck"></a><a name="isautocheck"></a>CMFCボタン::Isオートチェック

チェック ボックスまたはオプション ボタンが自動ボタンかどうかを示します。

```
BOOL IsAutoCheck() const;
```

### <a name="return-value"></a>戻り値

ボタンにスタイル BS_AUTOCHECKBOXまたはBS_AUTORADIOBUTTONがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonisautorepeatcommandmode"></a><a name="isautorepeatcommandmode"></a>コントロール モード::自動繰り返しコマンド モード

ボタンが自動繰り返しモードに設定されているかどうかを示します。

```
BOOL IsAutorepeatCommandMode() const;
```

### <a name="return-value"></a>戻り値

ボタンが自動繰り返しモードに設定されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ボタンを自動繰り返しモードに設定するには[、CMFCButton::SetAutorepeatMode](#setautorepeatmode)メソッドを使用します。

## <a name="cmfcbuttonischeckbox"></a><a name="ischeckbox"></a>CMFCボタン::Isチェックボックス

ボタンがチェック ボックス ボタンかどうかを示します。

```
BOOL IsCheckBox() const;
```

### <a name="return-value"></a>戻り値

ボタンにBS_CHECKBOXまたはBS_AUTOCHECKBOXスタイルがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonischecked"></a><a name="ischecked"></a>CMFCボタン::チェック

現在のボタンがオンになっているかどうかを示します。

```
BOOL IsChecked() const;
```

### <a name="return-value"></a>戻り値

現在のボタンがオンになっている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは、さまざまな種類のボタンがチェックされることを示すためにさまざまな方法を使用します。 たとえば、ラジオ ボタンにドットが含まれている場合はチェックされます。**X**が含まれている場合は、チェック ボックスがオンになります。

## <a name="cmfcbuttonishighlighted"></a><a name="ishighlighted"></a>CMFCボタン::ハイライト

ボタンが強調表示されているかどうかを示します。

```
BOOL IsHighlighted() const;
```

### <a name="return-value"></a>戻り値

ボタンが強調表示されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

マウスをボタンの上に置くと、ボタンが強調表示されます。

## <a name="cmfcbuttonispressed"></a><a name="ispressed"></a>CMFCボタン::イズプレス

ボタンを押して強調表示するかどうかを示します。

```
BOOL IsPressed() const;
```

### <a name="return-value"></a>戻り値

ボタンが押された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonispushed"></a><a name="ispushed"></a>CMFCボタン::イズプッシュ

ボタンが押されているかどうかを示します。

```
BOOL IsPushed() const;
```

### <a name="return-value"></a>戻り値

ボタンが押された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonisradiobutton"></a><a name="isradiobutton"></a>ボタン::イスラジオボタン

ボタンがラジオ ボタンかどうかを示します。

```
BOOL IsRadioButton() const;
```

### <a name="return-value"></a>戻り値

ボタンのスタイルがBS_RADIOBUTTONまたはBS_AUTORADIOBUTTON場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcbuttoniswindowsthemingenabled"></a><a name="iswindowsthemingenabled"></a>ボタン::IsWindows テーマが有効です。

ボタンの境界線のスタイルが現在の Windows テーマに対応しているかどうかを示します。

```
static BOOL IsWindowsThemingEnabled();
```

### <a name="return-value"></a>戻り値

ボタンの境界線のスタイルが現在の Windows テーマに対応する場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbuttonm_bdontusewinxptheme"></a><a name="m_bDontUseWinXPTheme"/>コMFCボタン:m_bDontUseWinXPTheme

ボタンを描画するときに Windows XP のテーマを使用するかどうかを指定します。

```
BOOL m_bDontUseWinXPTheme;
```

## <a name="cmfcbuttonm_bdrawfocus"></a><a name="m_bdrawfocus"></a>CMFCボタン::m_bDrawFocus

ボタンの周囲にフォーカスの四角形を描画するかどうかを示します。

```
BOOL m_bDrawFocus;
```

### <a name="remarks"></a>解説

ボタンが`m_bDrawFocus`フォーカスを受け取った場合に、フレームワークがボタンのテキストとイメージの周囲にフォーカス四角形を描画するように指定するには、メンバーを TRUE に設定します。

コンストラクター`CMFCButton`は、このメンバーを TRUE に初期化します。

## <a name="cmfcbuttonm_bgraydisabled"></a><a name="m_bGrayDisabled"></a>CMFCボタン::m_bGrayDisabled

TRUE の場合、無効なボタンをグレー表示で描画できます。

```
BOOL m_bGrayDisabled;
```

## <a name="cmfcbuttonm_bhighlightchecked"></a><a name="m_bhighlightchecked"></a>CMFCボタン:m_bHighlightChecked

カーソルをBS_CHECKBOXボタンの上に置いたときに、そのボタンを強調表示するかどうかを示します。

```
BOOL m_bHighlightChecked;
```

### <a name="remarks"></a>解説

マウスを`m_bHighlightChecked`マウスでポイントしたときに、フレームワークがBS_CHECKBOX スタイルのボタンを強調表示するように指定するには、メンバーを TRUE に設定します。

## <a name="cmfcbuttonm_bresponseonbuttondown"></a><a name="m_bResponseOnButtonDown"></a>CMFCボタン::m_bResponseOnButtonDown

ボタン ダウン イベントに応答するかどうかを示します。

```
BOOL m_bResponseOnButtonDown;
```

## <a name="cmfcbuttonm_brightimage"></a><a name="m_brightimage"></a>CMFCボタン::m_bRightImage

ボタンの右側にイメージを表示するかどうかを示します。

```
BOOL m_bRightImage;
```

## <a name="cmfcbuttonm_btopimagem_btopimage"></a><a name="m_bTopImage"></a>CMFCボタン::m_bTopImage](#m_bTopImage)

イメージがボタンの上にあるかどうかを示します。

```
BOOL m_bTopImage;
```

### <a name="remarks"></a>解説

ボタンの`m_bRightImage`テキスト ラベルの右側にボタンのイメージを表示するように指定するには、メンバーを TRUE に設定します。

## <a name="cmfcbuttonm_btransparent"></a><a name="m_btransparent"></a>CMFCボタン::m_bTransparent

ボタンが透明かどうかを示します。

```
BOOL m_bTransparent;
```

### <a name="remarks"></a>解説

メンバーを`m_bTransparent`TRUE に設定して、フレームワークがボタンを透明にすることを指定します。 コンストラクター`CMFCButton`は、このメンバーを FALSE に初期化します。

## <a name="cmfcbuttonm_nalignstyle"></a><a name="m_nalignstyle"></a>M_nAlignStyle

ボタン テキストの配置を指定します。

```
AlignStyle m_nAlignStyle;
```

### <a name="remarks"></a>解説

ボタン テキストの配置`CMFCButton::AlignStyle`を指定するには、次のいずれかの列挙値を使用します。

|値|説明|
|-----------|-----------------|
|ALIGN_CENTER|(デフォルト)ボタンテキストをボタンの中央に揃えます。|
|ALIGN_LEFT|ボタンテキストをボタンの左側に揃えます。|
|ALIGN_RIGHT|ボタンテキストをボタンの右側に揃えます。|

コンストラクター`CMFCButton`は、このメンバーをALIGN_CENTERに初期化します。

## <a name="cmfcbuttonm_bwasdblclkm_bwasdblclk"></a><a name="m_bWasDblClk"></a>CMFCボタン::m_bWasDblClk](#m_bWasDblClk)|

最後のクリック イベントがダブルクリックであったかどうかを示します。|

```
BOOL m_bWasDblClk;
```

## <a name="cmfcbuttonm_nflatstyle"></a><a name="m_nflatstyle"></a>CMFCボタン::m_nFlatStyle

ボーダレス、フラット、半フラット、3D などのボタンのスタイルを指定します。

```
FlatStyle  m_nFlatStyle;
```

### <a name="remarks"></a>解説

次の表は、`CMFCButton::m_nFlatStyle`ボタンの外観を指定する列挙値の一覧です。

|値|説明|
|-----------|-----------------|
|BUTTONSTYLE_3D|(デフォルト)ボタンは高い 3 次元の側面を持っているように見えます。 ボタンをクリックすると、ボタンが深いインデントに押されたように見えます。|
|BUTTONSTYLE_FLAT|マウスがボタンの上に置かれていない場合、ボタンは 2 次元で、上げられた辺はありません。 マウスボタンの上にマウスが置くと、ボタンの側面が低く、3 次元に表示されます。 ボタンをクリックすると、ボタンが押されて浅いインデントが表示されます。|
|BUTTONSTYLE_SEMIFLAT|ボタンは、低い 3 次元の側面を持っているように見えます。 ボタンをクリックすると、ボタンが深いインデントに押されたように見えます。|
|BUTTONSTYLE_NOBORDERS|ボタンは上がった辺ではなく、常に 2 次元で表示されます。 ボタンがクリックされたときに、ボタンがインデントに押されたようには見えません。|

コンストラクター`CMFCButton`は、このメンバーをBUTTONSTYLE_3Dに初期化します。

### <a name="example"></a>例

クラス内のメンバー変数の値を設定する方法を`m_nFlatStyle`次の例に`CMFCButton`示します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]

## <a name="cmfcbuttonondraw"></a><a name="ondraw"></a>CMFCボタン::オンドロー

ボタンを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]ボタンに境界を持つ四角形への参照。

*ui状態*<br/>
[in]現在のボタンの状態。 詳細については、トピックの`itemState`[メンバーを参照](/windows/win32/api/winuser/ns-winuser-drawitemstruct)してください。

### <a name="remarks"></a>解説

独自のコードを使用してボタンを描画するには、このメソッドをオーバーライドします。

## <a name="cmfcbuttonondrawborder"></a><a name="ondrawborder"></a>ウィンドウの境界線

ボタンの境界線を描画するために、フレームワークによって呼び出されます。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*レクトクライアント*<br/>
[in]ボタンに境界を持つ四角形への参照。

*ui状態*<br/>
[in]現在のボタンの状態。 詳細については、トピックの`itemState`[メンバーを参照](/windows/win32/api/winuser/ns-winuser-drawitemstruct)してください。

### <a name="remarks"></a>解説

独自のコードを使用して境界線を描画するには、このメソッドをオーバーライドします。

## <a name="cmfcbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCボタン::オンドローフォーカスレック

ボタンのフォーカス四角形を描画するために、フレームワークによって呼び出されます。

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*レクトクライアント*<br/>
[in]ボタンに境界を持つ四角形への参照。

### <a name="remarks"></a>解説

このメソッドをオーバーライドして、独自のコードを使用してフォーカスの四角形を描画します。

## <a name="cmfcbuttonondrawtext"></a><a name="ondrawtext"></a>ウィンドウボタン::オンドローテキスト

ボタン テキストを描画するために、フレームワークによって呼び出されます。

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

*Rect*<br/>
[in]ボタンに境界を持つ四角形への参照。

*str テキスト*<br/>
[in]描画するテキスト。

*uiDT フラグ*<br/>
[in]テキストの書式設定方法を指定するフラグ。 詳細については、メソッドの*nFormat*パラメーター [:D参照](../../mfc/reference/cdc-class.md#drawtext)してください。

*ui状態*<br/>
[in] 予約されています。

### <a name="remarks"></a>解説

ボタン テキストを描画する独自のコードを使用するには、このメソッドをオーバーライドします。

## <a name="cmfcbuttononfillbackground"></a><a name="onfillbackground"></a>CMFCボタン::オンフィルバックグラウンド

ボタン テキストの背景を描画するために、フレームワークによって呼び出されます。

```
virtual void OnFillBackground(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*レクトクライアント*<br/>
[in]ボタンに境界を持つ四角形への参照。

### <a name="remarks"></a>解説

独自のコードを使用してボタンの背景を描画するには、このメソッドをオーバーライドします。

## <a name="cmfcbuttonselectfont"></a><a name="selectfont"></a>ボタン::フォントの選択

指定したデバイス コンテキストに関連付けられているフォントを取得します。

```
virtual CFont* SelectFont(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

### <a name="return-value"></a>戻り値

独自のコードを使用してフォントを取得するには、このメソッドをオーバーライドします。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonsetautorepeatmode"></a><a name="setautorepeatmode"></a>CMFCボタン::セットオートリピートモード

ボタンを自動繰り返しモードに設定します。

```cpp
void SetAutorepeatMode(int nTimeDelay=500);
```

### <a name="parameters"></a>パラメーター

*遅延時間*<br/>
[in]親ウィンドウに送信されるメッセージの間隔を指定する負でない数。 間隔はミリ秒単位で、デフォルト値は 500 ミリ秒です。 自動繰り返しメッセージ モードを無効にするには、0 を指定します。

### <a name="remarks"></a>解説

このメソッドを使用すると、ボタンが解放されるまで、または*nTimeDelay*パラメーターが 0 に設定されるまで、ボタンは常に親ウィンドウにWM_COMMANDメッセージを送信します。

## <a name="cmfcbuttonsetcheckedimage"></a><a name="setcheckedimage"></a>をクリックします。

チェックボタンのイメージを設定します。

```cpp
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

*Hicon*<br/>
[in]新しいイメージのビットマップとマスクを含むアイコンへのハンドル。

*b自動破壊*<br/>
[in]ビットマップ リソースが自動的に破棄されるように指定する場合は TRUE。それ以外の場合は FALSE。 デフォルトは TRUE です。

*アイコンホット*<br/>
[in]選択した状態のイメージを含むアイコンへのハンドル。

*hビットマップ*<br/>
[in]選択されていない状態のイメージを含むビットマップへのハンドル。

*をクリックします。*<br/>
[in]選択した状態のイメージを含むビットマップへのハンドル。

*カラー*<br/>
[in]ボタンの背景に透明な色を指定します。つまり、ボタンの面です。 TRUE はカラー値 RGB(192、192、192)を使用します。で定義された色の値を使用`AFX_GLOBAL_DATA::clrBtnFace`する場合は FALSE。

*をクリックします。*<br/>
[in]選択されていないイメージのリソース ID。

*をクリックします。*<br/>
[in]選択したイメージのリソース ID。

*アイコン無効*<br/>
[in]無効なイメージのアイコンへのハンドル。

*無効なビットマップ*<br/>
[in]無効なイメージを含むビットマップへのハンドル。

*をクリックします。*<br/>
[in]無効なビットマップのリソース ID。

*をブレンド*<br/>
[in]アルファ チャネルを使用する 32 ビット イメージのみを使用する場合は TRUE。アルファ チャンネル画像のみを使用しない場合は FALSE。 デフォルトは FALSE です。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonsetfacecolor"></a><a name="setfacecolor"></a>CMFCボタン::セットフェイスカラー

ボタンテキストの背景色を設定します。

```cpp
void SetFaceColor(
    COLORREF crFace,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*クレフェイス*<br/>
[in]RGB カラー値。

*引き出し*<br/>
[in]直ちに画面を再描画する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタンの背景 (面) の新しい塗りつぶし色を定義するために使います。 [CMFCButton::m_bTransparent](#m_btransparent)メンバー変数が TRUE の場合、背景が埋められていないことに注意してください。

## <a name="cmfcbuttonsetimage"></a><a name="setimage"></a>をクリックします。

ボタンのイメージを設定します。

```cpp
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

*Hicon*<br/>
[in]新しいイメージのビットマップとマスクを含むアイコンへのハンドル。

*b自動破壊*<br/>
[in]ビットマップ リソースが自動的に破棄されるように指定する場合は TRUE。それ以外の場合は FALSE。 デフォルトは TRUE です。

*アイコンホット*<br/>
[in]選択した状態のイメージを含むアイコンへのハンドル。

*hビットマップ*<br/>
[in]選択されていない状態のイメージを含むビットマップへのハンドル。

*をクリックします。*<br/>
[in]選択した状態のイメージを含むビットマップへのハンドル。

*をクリックします。*<br/>
[in]選択されていないイメージのリソース ID。

*をクリックします。*<br/>
[in]選択したイメージのリソース ID。

*カラー*<br/>
[in]ボタンの背景に透明な色を指定します。つまり、ボタンの面です。 TRUE はカラー値 RGB(192、192、192)を使用します。で定義された色の値を使用`AFX_GLOBAL_DATA::clrBtnFace`する場合は FALSE。

*アイコン無効*<br/>
[in]無効なイメージのアイコンへのハンドル。

*無効なビットマップ*<br/>
[in]無効なイメージを含むビットマップへのハンドル。

*をクリックします。*<br/>
[in]無効なビットマップのリソース ID。

*をブレンド*<br/>
[in]アルファ チャネルを使用する 32 ビット イメージのみを使用する場合は TRUE。アルファ チャンネル画像のみを使用しない場合は FALSE。 デフォルトは FALSE です。

### <a name="remarks"></a>解説

### <a name="example"></a>例

クラス内でさまざまなバージョンのメソッドを使用する方法を`SetImage`次の例`CMFCButton`に示します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]

## <a name="cmfcbuttonsetmousecursor"></a><a name="setmousecursor"></a>ボタン::マウスカーソルを設定します。

カーソルイメージを設定します。

```cpp
void SetMouseCursor(HCURSOR hcursor);
```

### <a name="parameters"></a>パラメーター

*hcursor*<br/>
[in]カーソルのハンドル。

### <a name="remarks"></a>解説

このメソッドは、カーソルイメージ (ハンドカーソルなど) をボタンに関連付けるために使います。 カーソルはアプリケーション リソースから読み込まれます。

### <a name="example"></a>例

クラスでメソッドを使用する方法を`SetMouseCursor`次の例に`CMFCButton`示します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)のコードの一部です。

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]

## <a name="cmfcbuttonsetmousecursorhand"></a><a name="setmousecursorhand"></a>CMFCボタン::マウスカーソルハンド

カーソルを手のイメージに設定します。

```cpp
void SetMouseCursorHand();
```

### <a name="remarks"></a>解説

このメソッドは、手のカーソル イメージをボタンに関連付けるために使います。 カーソルはアプリケーション リソースから読み込まれます。

## <a name="cmfcbuttonsetstdimage"></a><a name="setstdimage"></a>をクリックします。

オブジェクトを`CMenuImages`使用してボタンイメージを設定します。

```cpp
void SetStdImage(
    CMenuImages::IMAGES_IDS id,
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]`CMenuImage::IMAGES_IDS`列挙体で定義されているボタン イメージ識別子の 1 つ。 イメージ値は、矢印、ピン、ラジオ ボタンなどのイメージを指定します。

*state*<br/>
[in]列挙体で定義されているボタン イメージの状態識別子の`CMenuImages::IMAGE_STATE`1 つ。 イメージの状態は、黒、グレー、明るいグレー、白、濃い灰色などのボタンの色を指定します。 既定値は `CMenuImages::ImageBlack` です。

*無効な ID*<br/>
[in]`CMenuImage::IMAGES_IDS`列挙体で定義されているボタン イメージ識別子の 1 つ。 この画像は、ボタンが無効であることを示しています。 既定値は、最初のボタン イメージ`CMenuImages::IdArrowDown`( ) です。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonsettextcolor"></a><a name="settextcolor"></a>コントロール::テキストの色を設定します。

選択されていないボタンのボタン テキストの色を設定します。

```cpp
void SetTextColor(COLORREF clrText);
```

### <a name="parameters"></a>パラメーター

*clrText*<br/>
[in]RGB カラー値。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonsettexthotcolor"></a><a name="settexthotcolor"></a>CMFCボタン::セットテキストホットカラー

選択したボタンのボタン テキストの色を設定します。

```cpp
void SetTextHotColor(COLORREF clrTextHot);
```

### <a name="parameters"></a>パラメーター

*テキストホット*<br/>
[in]RGB カラー値。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonsettooltip"></a><a name="settooltip"></a>ツールチップの設定

ツールヒントをボタンに関連付けます。

```cpp
void SetTooltip(LPCTSTR lpszToolTipText);
```

### <a name="parameters"></a>パラメーター

*ヒントを表示します。*<br/>
[in]ツールヒントのテキストへのポインター。 ツールヒントを無効にするには、NULL を指定します。

### <a name="remarks"></a>解説

## <a name="cmfcbuttonsizetocontent"></a><a name="sizetocontent"></a>コンテンツのサイズ

ボタンのテキストとイメージを含むボタンのサイズを変更します。

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>パラメーター

*唯一の時間*<br/>
[in]TRUE は、ボタンの新しいサイズを計算しますが、変更はしません。FALSE を指定すると、ボタンのサイズを変更できます。 デフォルトは FALSE です。

### <a name="return-value"></a>戻り値

ボタン`CSize`の新しいサイズを格納するオブジェクト。

### <a name="remarks"></a>解説

既定では、このメソッドは、水平方向の余白が 10 ピクセル、垂直マージンが 5 ピクセルである新しいサイズを計算します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCLinkCtrl クラス](../../mfc/reference/cmfclinkctrl-class.md)<br/>
[クラス](../../mfc/reference/cmfccolorbutton-class.md)<br/>
[CMFCMenuButton クラス](../../mfc/reference/cmfcmenubutton-class.md)
