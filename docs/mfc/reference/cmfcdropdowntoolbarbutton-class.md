---
title: クラスをドロップダウンダウンツール バーボタン
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
ms.openlocfilehash: f09a2f3fe66abb86a8f220dbdf6744813ad9db0d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752409"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>クラスをドロップダウンダウンツール バーボタン

ツール バー ボタンの一種で、クリックされたときは標準ボタンと同じように動作します。 ただし、ドロップダウン ツール バー (ユーザーがツール バー ボタンを押し下げたり押し下げたりすると[、CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)) が開きます。

## <a name="syntax"></a>構文

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ツールバーボタン::CMFCドロップダウンツールバーボタン](#cmfcdropdowntoolbarbutton)|`CMFCDropDownToolbarButton` オブジェクトを構築します。|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ツールバーボタン::コピーフロイン](#copyfrom)|別のツール バー ボタンのプロパティを現在のボタンにコピーします。 [(CMFCツールバーボタンをオーバーライドします。.](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)|
|`CMFCDropDownToolbarButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[ツールバーボタン::Dロップダウンツールバー](#dropdowntoolbar)|ドロップダウン ツールバーを開きます。|
|[ボタン::メニューへ移動](#exporttomenubutton)|ツールバー ボタンからメニューにテキストをコピーします。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|
|[ツールバーボタン::GetDropDownツールバー](#getdropdowntoolbar)|ボタンに関連付けられているドロップダウン ツール バーを取得します。|
|`CMFCDropDownToolbarButton::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[ツールバーボタン::IsDropDown](#isdropdown)|ドロップダウン ツール バーが現在開いているかどうかを判断します。|
|[ツールバーボタン::アイスエクストラサイズ](#isextrasize)|ボタンを拡張枠線で表示できるかどうかを指定します。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize)|
|[ツールバーボタン::計算サイズ](#oncalculatesize)|指定したデバイス コンテキストとドッキング状態のボタンのサイズを計算するために、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします::計算サイズ](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|`CMFCDropDownToolbarButton::OnCancelMode`|[WM_CANCELMODE](/windows/win32/winmsg/wm-cancelmode)メッセージを処理するために、フレームワークによって呼び出されます。 ( `CMCToolBarButton::OnCancelMode`をオーバーライドします)。|
|[ツールバーボタン::オンチェンジペアレント](#onchangeparentwnd)|ボタンが新しいツール バーに挿入されたときに、フレームワークによって呼び出されます。 (オーバーライド[CMFCツールバーボタン::オンチェンジペアレントウンド](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[クリック時ボタン::クリック時](#onclick)|ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします。:クリック時](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[ツールバーボタン::クリックアップ時](#onclickup)|ユーザーがマウス ボタンを離したときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします。.)](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)|
|[ツールバーボタン::オンコンテキストヘルプ](#oncontexthelp)|親ツール バーがWM_HELPHITTEST メッセージを処理するときに、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)|
|[メニューボタン::メニューのオン](#oncustomizemenu)|アプリケーションが親ツール バーにショートカット メニューを表示するときに、指定されたメニューを変更します。 (オーバーライド[CMFCツールバーボタン::オンカスタマアメメニュー](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|
|[ツールバーボタン::ドロー上げ](#ondraw)|指定したスタイルとオプションを使用してボタンを描画するために、フレームワークによって呼び出されます。 (オーバーライド[CMFCツールバーボタン::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|[ツールバーボタン::オンドローオンカスタマイプリスト](#ondrawoncustomizelist)|[**カスタマイズ**] ダイアログ ボックスの **[コマンド**] ウィンドウにボタンを描画するために、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)|
|[ツールバーボタン::シリアル化](#serialize)|このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます。 (オーバーライド[CMFCツールバーボタン::シリアル化](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|[ツールバーボタン::既定のコマンド](#setdefaultcommand)|ユーザーがボタンをクリックしたときにフレームワークが使用する既定のコマンドを設定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[ツールバーボタン::m_uiShowBarDelay](#m_uishowbardelay)|ドロップダウン ツール バーが表示されるまでにマウス ボタンを押したままにする必要がある時間の長さを指定します。|

## <a name="remarks"></a>解説

A`CMFCDropDownToolBarButton`は通常のボタンとは異なり、ボタンの右下隅に小さな矢印が表示されます。 ユーザーがドロップダウン ツールバーからボタンを選択すると、フレームワークは最上位のツールバー ボタン (右下隅に小さい矢印が付いたボタン) にアイコンを表示します。

ドロップダウン ツール バーを実装する方法については、「 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)」を参照してください。

オブジェクト`CMFCDropDownToolBarButton`は[、CMFCToolBarMenuButton クラス オブジェクト](../../mfc/reference/cmfctoolbarmenubutton-class.md)にエクスポートでき、ポップアップ メニューを持つメニュー ボタンとして表示されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarbuttoncopyfrom"></a><a name="copyfrom"></a>ツールバーボタン::コピーフロイン

別のツール バー ボタンのプロパティを現在のボタンにコピーします。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]コピー元のボタンへの参照。

### <a name="remarks"></a>解説

このツール バー ボタンに別のツール バー ボタンをコピーします。 *src*は 型`CMFCDropDownToolbarButton`でなければなりません。

## <a name="cmfcdropdowntoolbarbuttoncmfcdropdowntoolbarbutton"></a><a name="cmfcdropdowntoolbarbutton"></a>ツールバーボタン::CMFCドロップダウンツールバーボタン

`CMFCDropDownToolbarButton` オブジェクトを構築します。

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]ボタンの既定のテキスト。

*をクリックします。*<br/>
[in]ユーザーがボタンを`CMFCDropDownToolBar`押したときに表示されるオブジェクトへのポインター。

### <a name="remarks"></a>解説

コンストラクターの 2 番目のオーバーロードは *、pToolBar*が指定するツール バーの最初のボタンをドロップダウン ボタンにコピーします。

通常、ドロップダウン ツール バー ボタンは *、pToolBar*で指定したツール バーの最近使用したボタンのテキストを使用します。 ボタンがメニュー ボタンに変換されるか、[**カスタマイズ**] ダイアログ ボックスの [**コマンド**] タブに表示されるときに*lpszName*で指定されたテキストが使用されます。 **[カスタマイズ**] ダイアログ ボックスの詳細については、「 [CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)」を参照してください。

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に`CMFCDropDownToolbarButton`示します。 このコード スニペットは[、Visual Studio のデモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

## <a name="cmfcdropdowntoolbarbuttondropdowntoolbar"></a><a name="dropdowntoolbar"></a>ツールバーボタン::Dロップダウンツールバー

ドロップダウン ツールバーを開きます。

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]ドロップダウン フレームの親ウィンドウ、またはドロップダウン ツール バー ボタンの親ウィンドウを使用する場合は NULL。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

[CMFCDropDownToolbarButton::OnClick](#onclick)メソッドは、ユーザーがツール バー ボタンを押しながら押したときにドロップダウン ツール バーを開くために、このメソッドを呼び出します。

このメソッドは[、CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create)メソッドを使用してドロップダウン ツール バーを作成します。 親ツールバーが垂直にドッキングされている場合、このメソッドは、ドロップダウン ツールバーを親ツール バーの左側または右側に配置します。 それ以外の場合、このメソッドは、親ツール バーの下にドロップダウン ツール バーを配置します。

このメソッドは *、pWnd*が NULL で、ドロップダウン ツール バー ボタンに親ウィンドウがない場合に失敗します。

## <a name="cmfcdropdowntoolbarbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>ボタン::メニューへ移動

ツールバー ボタンからメニューにテキストをコピーします。

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>パラメーター

*メニューボタン*<br/>
[in]ターゲット メニュー ボタンへの参照。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) を呼び出し、このボタンの各ツール バー メニュー項目を含むポップアップ メニューをターゲット メニュー ボタンに追加します。 このメソッドは、サブメニューをポップアップ メニューに追加しません。

親ツール バーが NULL`m_pToolBar`の場合、または基本クラスの実装が FALSE を返した場合、このメソッドは失敗します。

## <a name="cmfcdropdowntoolbarbuttongetdropdowntoolbar"></a><a name="getdropdowntoolbar"></a>ツールバーボタン::GetDropDownツールバー

ボタンに関連付けられているドロップダウン ツール バーを取得します。

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>戻り値

ボタンに関連付けられているドロップダウン ツール バー。

### <a name="remarks"></a>解説

このメソッドは、`m_pToolBar`データ メンバーを返します。

## <a name="cmfcdropdowntoolbarbuttonisdropdown"></a><a name="isdropdown"></a>ツールバーボタン::IsDropDown

ドロップダウン ツール バーが現在開いているかどうかを判断します。

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>戻り値

ドロップダウン ツールバーが現在開いている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

フレームワークは、メソッドを使用してドロップダウン ツール バー [:D](#dropdowntoolbar)開きます。 ユーザーがドロップダウン ツールバーの非クライアント領域でマウスの左ボタンを押すと、フレームワークはドロップダウン ツール バーを閉じます。

## <a name="cmfcdropdowntoolbarbuttonisextrasize"></a><a name="isextrasize"></a>ツールバーボタン::アイスエクストラサイズ

ボタンを拡張枠線で表示できるかどうかを指定します。

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>戻り値

ツール バー ボタンを拡張枠線で表示できる場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

拡張境界線の詳細については[、「CMFC ツール バー ボタン::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize)」を参照してください。

## <a name="cmfcdropdowntoolbarbuttonm_uishowbardelay"></a><a name="m_uishowbardelay"></a>ツールバーボタン::m_uiShowBarDelay

ドロップダウン ツール バーが表示されるまでにマウス ボタンを押したままにする必要がある時間の長さを指定します。

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>解説

遅延時間はミリ秒単位で測定されます。 既定値は 500 です。 この共有データ メンバーの値を変更することで、別の遅延を設定できます。

## <a name="cmfcdropdowntoolbarbuttononcalculatesize"></a><a name="oncalculatesize"></a>ツールバーボタン::計算サイズ

指定したデバイス コンテキストとドッキング状態のボタンのサイズを計算するために、フレームワークによって呼び出されます。

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*サイズデフォルト*<br/>
[in]ボタンの既定のサイズ。

*bHorz*<br/>
[in]親ツール バーのドッキング状態。 このパラメーターは、ツール バーが水平にドッキングされている場合、またはフローティング状態の場合は TRUE、ツール バーが垂直方向にドッキングされている場合は FALSE です。

### <a name="return-value"></a>戻り値

ボタン`SIZE`のサイズをピクセル単位で格納する構造体。

### <a name="remarks"></a>解説

このメソッドは、ボタン サイズの水平ディメンションにドロップダウン矢印の幅を追加することで、基本クラスの実装 ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)) を拡張します。

## <a name="cmfcdropdowntoolbarbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>ツールバーボタン::オンチェンジペアレント

ボタンが新しいツール バーに挿入されたときに、フレームワークによって呼び出されます。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]新しい親ウィンドウ。

### <a name="remarks"></a>解説

このメソッドは、テキスト ラベル (CMFCツールバーボタン::m_strText) をクリアし[、CMFC ツールバー ボタン::m_bTextと CMFC ツールバー ボタン::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext)データ メンバーを FALSE[CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton)に設定することで、基本クラスの実装 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) をオーバーライドします。 [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)

## <a name="cmfcdropdowntoolbarbuttononclick"></a><a name="onclick"></a>クリック時ボタン::クリック時

ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]ツール バー ボタンの親ウィンドウ。

*bディレイ*<br/>
[in]メッセージを遅延で処理する必要がある場合は TRUE。

### <a name="return-value"></a>戻り値

ボタンがクリック メッセージを処理する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、ドロップダウン ツール バーの状態を更新することにより、基本クラスの実装[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)を拡張します。

ユーザーがツール バー ボタンをクリックすると、このメソッドは[、CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)データ メンバーで指定された時間を待機するタイマーを作成し[、CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)メソッドを使用してドロップダウン ツール バーを開きます。 このメソッドは、ユーザーがツール バー ボタンを 2 回目にクリックすると、ドロップダウン ツール バーを閉じます。

## <a name="cmfcdropdowntoolbarbuttononclickup"></a><a name="onclickup"></a>ツールバーボタン::クリックアップ時

ユーザーがマウス ボタンを離したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>戻り値

ボタンがクリック メッセージを処理する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、ドロップダウン ツール バーの状態を更新することで、基本クラスの実装である[CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)を拡張します。

このメソッドは、ドロップダウン ツール バー タイマーがアクティブな場合は停止します。 ドロップダウン ツールバーが開いている場合は、そのツールバーが閉じます。

ドロップダウン ツール バーとドロップダウン ツール バー タイマーの詳細については[、「CMFCDropDownToolbarButton::OnClick](#onclick)」を参照してください。

## <a name="cmfcdropdowntoolbarbuttononcontexthelp"></a><a name="oncontexthelp"></a>ツールバーボタン::オンコンテキストヘルプ

親ツール バーがWM_HELPHITTEST メッセージを処理するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]ツール バー ボタンの親ウィンドウ。

### <a name="return-value"></a>戻り値

ボタンがヘルプ メッセージを処理する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、基本クラスの実装を拡張します ( [CMFCツールバーボタン::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) を呼び出すことによって、 *bDelay*を FALSE に設定してメソッド[を呼び](#onclick)出します。 このメソッドは[、CMFCDropDownToolbarButton::OnClick](#onclick)によって返される値を返します。

WM_HELPHITTEST メッセージの詳細については、「 [TN028: 状況依存ヘルプのサポート](../../mfc/tn028-context-sensitive-help-support.md)」を参照してください。

## <a name="cmfcdropdowntoolbarbuttononcustomizemenu"></a><a name="oncustomizemenu"></a>メニューボタン::メニューのオン

アプリケーションが親ツール バーにショートカット メニューを表示するときに、指定されたメニューを変更します。

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
[in]カスタマイズするメニュー。

### <a name="return-value"></a>戻り値

このメソッドは TRUE を返します。

### <a name="remarks"></a>解説

このメソッドは、次のメニュー項目を無効にすることで、基本クラスの実装 ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) を拡張します。

- **ボタンイメージのコピー**

- **ボタンの外観**

- **Image**

- **[テキスト]**

- **画像とテキスト**

フレームワークがカスタマイズ モードで表示するショートカット メニューを変更するには、このメソッドをオーバーライドします。

## <a name="cmfcdropdowntoolbarbuttonondraw"></a><a name="ondraw"></a>ツールバーボタン::ドロー上げ

指定したスタイルとオプションを使用してボタンを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*Rect*<br/>
[in]ボタンの外接する四角形。

*pイメージズ*<br/>
[in]ボタンに関連付けられているツール バー イメージのコレクション。

*bHorz*<br/>
[in]親ツール バーのドッキング状態。 このパラメーターは、ボタンが水平方向にドッキングされている場合は TRUE、ボタンが垂直方向にドッキングされている場合は FALSE です。

*モードをカスタマイズする*<br/>
[in]ツール バーがカスタマイズ モードかどうかを指定します。 このパラメーターは、ツール バーがカスタマイズ モードの場合は TRUE、ツール バーがカスタマイズ モードでない場合は FALSE です。

*bハイライト*<br/>
[in]ボタンを強調表示するかどうかを指定します。 このパラメーターは、ボタンが強調表示されている場合は TRUE、ボタンが強調表示されていない場合は FALSE です。

*ボーダーを描く*<br/>
[in]ボタンに境界線を表示するかどうかを指定します。 このパラメーターは、ボタンに境界線を表示する場合は TRUE、ボタンに境界線を表示しない場合は FALSE です。

*ボタン*<br/>
[in]無効なボタンを網かけにするか、無効なイメージ コレクションを使用するかを指定します。 無効なボタンをシェーディングする場合は TRUE、無効なイメージ コレクションを使用する必要がある場合は FALSE です。

### <a name="remarks"></a>解説

ツール バー ボタンの描画をカスタマイズするには、このメソッドをオーバーライドします。

## <a name="cmfcdropdowntoolbarbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>ツールバーボタン::オンドローオンカスタマイプリスト

[**カスタマイズ**] ダイアログ ボックスの **[コマンド**] ウィンドウにボタンを描画するために、フレームワークによって呼び出されます。

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*Rect*<br/>
[in]ボタンの外接する四角形。

*b選択済み*<br/>
[in]ボタンが選択されているかどうか。 このパラメーターが TRUE の場合、ボタンが選択されます。 このパラメーターが FALSE の場合、ボタンは選択されません。

### <a name="return-value"></a>戻り値

指定したデバイス コンテキストのボタンの幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、オーナー描画リスト ボックスにボタンを表示する必要がある場合に、カスタマイズ ダイアログ ボックス **([コマンド**]タブ) によって呼び出されます。

このメソッドは、ボタンのテキスト ラベルをボタンの名前 (つまり、コンストラクターに渡した*lpszName*パラメーターの値) に変更することで、基本クラスの実装 ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) を拡張します。

## <a name="cmfcdropdowntoolbarbuttonserialize"></a><a name="serialize"></a>ツールバーボタン::シリアル化

このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
[in]シリアル`CArchive`化の対象またはシリアル化先のオブジェクト。

### <a name="remarks"></a>解説

このメソッドは、親ツール バーのリソース ID をシリアル化することによって、基本クラスの実装 ( [CMFCToolBarButton::シリアル化](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) を拡張します。 アーカイブの読み込み中[(CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading)は 0 以外の`m_pToolBar`値を返します) 場合、このメソッドは、シリアル化されたリソース ID を含むツール バーにデータ メンバーを設定します。

## <a name="cmfcdropdowntoolbarbuttonsetdefaultcommand"></a><a name="setdefaultcommand"></a>ツールバーボタン::既定のコマンド

ユーザーがボタンをクリックしたときにフレームワークが使用する既定のコマンドを設定します。

```cpp
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]既定のコマンドの ID。

### <a name="remarks"></a>解説

ユーザーがボタンをクリックしたときにフレームワークが実行する既定のコマンドを指定します。 *uiCmd*で指定されたコマンド ID を持つ項目は、親ドロップダウン ツールバーに配置する必要があります。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラスをドロップダウンメニューバー](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)
