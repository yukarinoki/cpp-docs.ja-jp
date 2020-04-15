---
title: CMFCToolBarEditBoxButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
ms.openlocfilehash: 52989f7b523bf0ba9a00da350242a968ca0db153
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360478"
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton クラス

エディット コントロール ( [CEdit Class](../../mfc/reference/cedit-class.md)) を含むツール バー ボタン。

## <a name="syntax"></a>構文

```
class CMFCToolBarEditBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ボックス ボタン::CMFCツール バーエディット ボックス ボタン](#cmfctoolbareditboxbutton)|`CMFCToolBarEditBoxButton` オブジェクトを構築します。|
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ボックスボタン::缶詰ストレッチ](#canbestretched)|ユーザーがカスタマイズ中にボタンを伸張できるかどうかを指定します。 [(CMFCツールバーボタンをオーバーライドします。:缶詰ストレッチ](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[ボックスボタン::コピーから](#copyfrom)|別のツール バー ボタンのプロパティを現在のボタンにコピーします。 [(CMFCツールバーボタンをオーバーライドします。.](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)|
|`CMFCToolBarEditBoxButton::`[ボックスボタン::編集](#createedit)|ボタンに新しいエディット コントロールを作成します。|
|`CMFCToolBarEditBoxButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[ボックスボタン::ゲットバイコマンド](#getbycmd)|指定したコマンド`CMFCToolBarEditBoxButton`ID を持つアプリケーション内の最初のオブジェクトを取得します。|
|[ボックス ボタン::すべてのコンテンツを取得します。](#getcontentsall)|指定したコマンド ID を持つ最初のエディット ボックス ツール バー コントロールのテキストを取得します。|
|[ボックス ボタン::コンテキストメニューID](#getcontextmenuid)|ボタンに関連付けられているショートカット メニューのリソース ID を取得します。|
|[ボックスボタン::ゲットエディットボーダー](#geteditborder)|エディット ボックス ボタンの編集部分の外接する四角形を取得します。|
|`CMFCToolBarEditBoxButton::`[ボックスボタン::取得ボックス](#geteditbox)|ボタンに埋め込まれているエディット コントロールへのポインターを返します。|
|[ボックスボタン::ゲットワード](#gethwnd)|ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。 [(CMFCツールバーボタンをオーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)|
|[ボックス ボタン::取得イン検証レクト](#getinvalidaterect)|再描画する必要があるボタンのクライアント領域の領域を取得します。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)|
|`CMFCToolBarEditBoxButton::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[ボックスボタン::フトボーダー](#havehotborder)|ユーザーがボタンをクリックしたときにボタンの境界線を表示するかどうかを指定します。 [(CMFCツールバーボタンをオーバーライドします::フアホボーダー](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[ボックスボタン::イズフラットモード](#isflatmode)|エディット ボックス ボタンがフラット なスタイルかどうかを判断します。|
|[ボックスボタン::コマンドを通知します。](#notifycommand)|ボタンが[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージを処理するかどうかを指定します。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)|
|[ボタン::アドオンカスタマイズページ](#onaddtocustomizepage)|ボタンが **[カスタマイズ**] ダイアログ ボックスに追加されたときに、フレームワークによって呼び出されます。 (CMFC ツールバー ボタンをオーバーライド[します。:アドオンをカスタマイズページ](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|指定したデバイス コンテキストとドッキング状態のボタンのサイズを計算するために、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします::計算サイズ](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[ボックスボタン::オンチェンジペアレント](#onchangeparentwnd)|ボタンが新しいツール バーに挿入されたときに、フレームワークによって呼び出されます。 (オーバーライド[CMFCツールバーボタン::オンチェンジペアレントウンド](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[クリック時ボタン::クリック時](#onclick)|ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします。:クリック時](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[ボックスボタン::オンCtlカラー](#onctlcolor)|親ツール バーがWM_CTLCOLOR メッセージを処理するときに、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)|
|`CMFCToolBarEditBoxButton::OnDraw`|指定したスタイルとオプションを使用してボタンを描画するために、フレームワークによって呼び出されます。 (オーバーライド[CMFCツールバーボタン::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|[**カスタマイズ**] ダイアログ ボックスの **[コマンド**] ウィンドウにボタンを描画するために、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)|
|[ボタン::グローバルフォント変更](#onglobalfontschanged)|グローバル フォントが変更されたときに、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)|
|[ボックスボタン::移動時](#onmove)|親ツール バーが移動したときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします。:オンムーブ](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[ボックスボタン::オンショー](#onshow)|ボタンが表示または非表示になったときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします::オンショー](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|[ボックスボタン::オンサイズ](#onsize)|親ツール バーのサイズまたは位置が変更され、この変更によってボタンのサイズが変更されたときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします。:オンサイズ](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[ボタン::オンアップデートツールチップ](#onupdatetooltip)|親ツール バーがツールヒント テキストを更新するときに、フレームワークによって呼び出されます。 (オーバーライド[CMFCツールバーボタン::オンアップデートツールチップ](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarEditBoxButton::Serialize`|このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます。 (オーバーライド[CMFCツールバーボタン::シリアル化](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarEditBoxButton::SetACCData`|ツール バー`CAccessibilityData`ボタンから、指定されたオブジェクトにアクセシビリティ データを設定します。 [(CMFCツールバーボタンをオーバーライドします。::セットアックデータ](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|
|`CMFCToolBarEditBoxButton::`[ボックスボタン::コンテンツの設定](#setcontents)|ボタンのエディット コントロールのテキストを設定します。|
|`CMFCToolBarEditBoxButton::`[ボックスボタン::すべてのコンテンツを設定します。](#setcontentsall)|指定したコマンド ID を持つエディット コントロール ボタンを検索し、そのボタンのエディット コントロールのテキストを設定します。|
|[ボックス ボタン::コンテキストメニューID](#setcontextmenuid)|ボタンに関連付けられているショートカット メニューのリソース ID を指定します。|
|[ボックスボタン::セットフラットモード](#setflatmode)|アプリケーションの編集ボックス ボタンのフラット スタイルの外観を指定します。|
|`CMFCToolBarEditBoxButton::`[ボックスボタン::セットスタイル](#setstyle)|ボタンのスタイルを指定します。 (オーバーライド[CMFCツールバーボタン::セットスタイル](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|

## <a name="remarks"></a>解説

ツールバーに編集ボックスボタンを追加するには、次の手順を実行します。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。

2. `CMFCToolBarEditBoxButton` オブジェクトを構築します。

3. AFX_WM_RESETTOOLBAR メッセージを処理するメッセージ ハンドラーで[、CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)を使用して、ダミー ボタンを新しいコンボ ボックス ボタンに置き換えます。

詳細については、「[チュートリアル : ツールバーにコントロールを配置](../../mfc/walkthrough-putting-controls-on-toolbars.md)する 」を参照してください。

## <a name="example"></a>例

`CMFCToolBarEditBoxButton` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、カスタマイズ時にユーザーがボタンを拡大できることを指定し、ユーザーがボタンをクリックしたときにボタンの境界線を表示するように指定し、テキスト ボックス コントロールでテキストを設定し、アプリケーションの編集ボックス ボタンのフラット スタイルの外観を指定し、ツールバーの編集ボックス コントロールのスタイルを指定する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxツールバーエディットボックスボタン.h

## <a name="cmfctoolbareditboxbuttoncanbestretched"></a><a name="canbestretched"></a>ボックスボタン::缶詰ストレッチ

ユーザーがカスタマイズ中にボタンを伸張できるかどうかを指定します。

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>戻り値

このメソッドは TRUE を返します。

### <a name="remarks"></a>解説

既定では、フレームワークでは、ユーザーがカスタマイズ中にツール バー ボタンを伸ばすことを許可しません。 このメソッドは、ユーザーがカスタマイズ中に編集ボックスのツール バー ボタンを伸ばすことができるようにして、基本クラスの実装 ( [CMFCToolBarButton::CanBeStretch](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) を拡張します。

## <a name="cmfctoolbareditboxbuttoncmfctoolbareditboxbutton"></a><a name="cmfctoolbareditboxbutton"></a>ボックス ボタン::CMFCツール バーエディット ボックス ボタン

[オブジェクトを](../../mfc/reference/cmfctoolbareditboxbutton-class.md)作成します。

```
CMFCToolBarEditBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=ES_AUTOHSCROLL,
    int iWidth=0);
```

### <a name="parameters"></a>パラメーター

*Uiid*<br/>
[in]コントロール ID を指定します。

*iイメージ*<br/>
[in]ツール バー イメージの 0 から始まるインデックスを指定します。 イメージは、[クラスクラス](../../mfc/reference/cmfctoolbarimages-class.md)が保持するクラス のクラスのクラス[に](../../mfc/reference/cmfctoolbar-class.md)配置されます。

*Dwstyle*<br/>
[in]エディット コントロール スタイルを指定します。

*幅*<br/>
[in]エディット コントロールの幅をピクセル単位で指定します。

### <a name="remarks"></a>解説

既定のコンストラクターは、エディット コントロールスタイルを次の組み合わせに設定します。

WS_CHILD |WS_VISIBLE |ES_AUTOHSCROLL

コントロールの既定の幅は 150 ピクセルです。

## <a name="cmfctoolbareditboxbuttoncopyfrom"></a><a name="copyfrom"></a>ボックスボタン::コピーから

別のツール バー ボタンのプロパティを現在のボタンにコピーします。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]コピー元のボタンへの参照。

### <a name="remarks"></a>解説

このツール バー ボタンに別のツール バー ボタンをコピーします。 *src*は 型`CMFCToolBarEditBoxButton`でなければなりません。

## <a name="cmfctoolbareditboxbuttoncreateedit"></a><a name="createedit"></a>ボックスボタン::編集

ボタンに新しいエディット コントロールを作成します。

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]エディット コントロールの親ウィンドウを指定します。 NULL にすることはできません。

*Rect*<br/>
[in]エディット コントロールのサイズと位置を指定します。

### <a name="return-value"></a>戻り値

新しく作成されたエディット コントロールへのポインター。コントロールの作成とアタッチに失敗した場合は NULL になります。

### <a name="remarks"></a>解説

オブジェクトは`CMFCToolBarEditBoxButton`2 つの手順で作成します。 まず、コンストラクターを呼び出し`CreateEdit`、次に`CMFCToolBarEditBoxButton`を呼び出します。

## <a name="cmfctoolbareditboxbuttongetbycmd"></a><a name="getbycmd"></a>ボックスボタン::ゲットバイコマンド

指定したコマンド`CMFCToolBarEditBoxButton`ID を持つアプリケーション内の最初のオブジェクトを取得します。

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]取得するボタンのコマンド ID。

### <a name="return-value"></a>戻り値

指定した`CMFCToolBarEditBoxButton`コマンド ID を持つアプリケーション内の最初のオブジェクト。

### <a name="remarks"></a>解説

この共有ユーティリティ メソッドは、指定されたコマンド ID を持つ最初の編集ボックス ツール バー コントロールのテキストを設定または取得するために[、CMFCToolBarEditBoxButton:::セットコンテンツオール](#setcontentsall)および[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)などのメソッドで使用されます。

## <a name="cmfctoolbareditboxbuttongetcontentsall"></a><a name="getcontentsall"></a>ボックス ボタン::すべてのコンテンツを取得します。

指定したコマンド ID を持つ最初のエディット ボックス ツール バー コントロールのテキストを取得します。

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]コンテンツを取得するボタンのコマンド ID。

### <a name="return-value"></a>戻り値

指定`CString`したコマンド ID を持つ最初のエディット ボックス ツール バー コントロールのテキストを格納するオブジェクト。

### <a name="remarks"></a>解説

指定したコマンド ID を持`CMFCToolBarEditBoxButton`つオブジェクトがない場合、このメソッドは空の文字列を返します。

## <a name="cmfctoolbareditboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>ボックス ボタン::コンテキストメニューID

ボタンに関連付けられているショートカット メニューのリソース ID を取得します。

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>戻り値

ボタンに関連付けられているショートカット メニューのリソース ID。

### <a name="remarks"></a>解説

フレームワークは、ユーザーがボタンを右クリックしたときに、リソース ID を使用してショートカット メニューを作成します。

## <a name="cmfctoolbareditboxbuttongeteditborder"></a><a name="geteditborder"></a>ボックスボタン::ゲットエディットボーダー

エディット ボックス ボタンの編集部分の外接する四角形を取得します。

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>パラメーター

*レクトボーダー*<br/>
[アウト]外接する四`CRect`角形を受け取るオブジェクトへの参照。

### <a name="remarks"></a>解説

このメソッドは、クライアント座標でエディット コントロールの外接する四角形を取得します。 各方向の四角形のサイズを 1 ピクセル拡大します。

メソッドは[、](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder)オブジェクトの周囲に境界線を描画するときに、このメソッドを`CMFCToolBarEditBoxButton`呼び出します。

## <a name="cmfctoolbareditboxbuttongeteditbox"></a><a name="geteditbox"></a>ボックスボタン::取得ボックス

ボタンに埋め込まれている[CEdit クラス](../../mfc/reference/cedit-class.md)コントロールへのポインターを返します。

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>戻り値

ボタンに含まれる[CEdit クラス](../../mfc/reference/cedit-class.md)コントロールへのポインター。 `CEdit`コントロールがまだ作成されていない場合は NULL です。

### <a name="remarks"></a>解説

コントロールを作成`CEdit`するには[、CMFC ツール バー エディット ボックス ボタンを](#createedit)呼び出します。

## <a name="cmfctoolbareditboxbuttongethwnd"></a><a name="gethwnd"></a>ボックスボタン::ゲットワード

ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>戻り値

ボタンに関連付けられているウィンドウ ハンドル。

### <a name="remarks"></a>解説

このメソッドは、編集ボックス ボタンのエディット コントロール部分のウィンドウ ハンドルを返すことによって[、CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)メソッドをオーバーライドします。

## <a name="cmfctoolbareditboxbuttongetinvalidaterect"></a><a name="getinvalidaterect"></a>ボックス ボタン::取得イン検証レクト

再描画する必要があるボタンのクライアント領域の領域を取得します。

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>戻り値

再`CRect`描画する必要がある領域を指定するオブジェクト。

### <a name="remarks"></a>解説

このメソッドは、テキスト ラベルの領域を領域に含めることによって、基本クラスの実装である[CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)を拡張します。

## <a name="cmfctoolbareditboxbuttonhavehotborder"></a><a name="havehotborder"></a>ボックスボタン::フトボーダー

ユーザーがボタンをクリックしたときにボタンの境界線を表示するかどうかを指定します。

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>戻り値

ボタンが選択されているときに境界線を表示する場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、コントロールが表示されている場合は 0 以外の値を返すことによって、基本クラスの実装[CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)を拡張します。

## <a name="cmfctoolbareditboxbuttonisflatmode"></a><a name="isflatmode"></a>ボックスボタン::イズフラットモード

エディット ボックス ボタンがフラット なスタイルかどうかを判断します。

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>戻り値

ボタンがフラット スタイルの場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

既定では、編集ボックス ボタンはフラット なスタイルになっています。 アプリケーションの[フラット](#setflatmode)スタイルの外観を変更するには、メソッドを使用します。

## <a name="cmfctoolbareditboxbuttonnotifycommand"></a><a name="notifycommand"></a>ボックスボタン::コマンドを通知します。

ボタンが[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージを処理するかどうかを指定します。

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
[in]コマンドに関連付けられている通知メッセージ。

### <a name="return-value"></a>戻り値

ボタンがWM_COMMAND メッセージを処理する場合は TRUE、親ツール バーでメッセージを処理する必要があることを示す FALSE。

### <a name="remarks"></a>解説

フレームワークは、親ウィンドウに[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージを送信する際に、このメソッドを呼び出します。

このメソッドは[、EN_UPDATE](/windows/win32/Controls/en-update)通知を処理することによって基本クラスの実装 ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) を拡張します。 このオブジェクトと同じコマンド ID を持つ各エディット ボックスに対して、そのテキスト ラベルをこのオブジェクトのテキスト ラベルに設定します。

## <a name="cmfctoolbareditboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>ボタン::アドオンカスタマイズページ

ボタンが **[カスタマイズ**] ダイアログ ボックスに追加されたときに、フレームワークによって呼び出されます。

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>解説

このメソッドは、このオブジェクトと同じコマンド ID を持つ任意のツール バーのエディット ボックス コントロールからプロパティをコピーすることによって、基本クラスの実装 ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) を拡張します。 このメソッドは、このオブジェクトと同じコマンド ID を持つ編集ボックス コントロールを持つツール バーがない場合は何も実行しません。

**[カスタマイズ**] ダイアログ ボックスの詳細については、「 [CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)」を参照してください。

## <a name="cmfctoolbareditboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>ボックスボタン::オンチェンジペアレント

ボタンが新しいツール バーに挿入されたときに、フレームワークによって呼び出されます。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]新しい親ウィンドウへのポインター。

### <a name="remarks"></a>解説

このメソッドは、内部`CEdit`オブジェクトを再作成することによって、基本クラスの実装 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) をオーバーライドします。

## <a name="cmfctoolbareditboxbuttononclick"></a><a name="onclick"></a>クリック時ボタン::クリック時

ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]未使用。

*bディレイ*<br/>
[in]未使用。

### <a name="return-value"></a>戻り値

ボタンがクリック メッセージを処理する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、内部`CEdit`オブジェクトが表示されている場合は 0 以外の値を返すことによって、基本クラスの実装 ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) をオーバーライドします。

## <a name="cmfctoolbareditboxbuttononctlcolor"></a><a name="onctlcolor"></a>ボックスボタン::オンCtlカラー

親ツール バーがWM_CTLCOLOR メッセージを処理するときに、フレームワークによって呼び出されます。

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*をクリックします。*<br/>
[in]未使用。

### <a name="return-value"></a>戻り値

グローバル ウィンドウ ブラシへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、指定されたデバイス コンテキストのテキストと背景色をそれぞれグローバル テキストと背景色に設定することで、基本クラスの実装 ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) をオーバーライドします。

アプリケーションで使用できるグローバル オプションの詳細については、「 [AFX_GLOBAL_DATAの構造](../../mfc/reference/afx-global-data-structure.md)」を参照してください。

## <a name="cmfctoolbareditboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>ボタン::グローバルフォント変更

グローバル フォントが変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>解説

このメソッドは、コントロールのフォントをグローバル フォントのフォントに変更することで、基本クラスの実装 ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) を拡張します。

アプリケーションで使用できるグローバル オプションの詳細については、「 [AFX_GLOBAL_DATAの構造](../../mfc/reference/afx-global-data-structure.md)」を参照してください。

## <a name="cmfctoolbareditboxbuttononmove"></a><a name="onmove"></a>ボックスボタン::移動時

親ツール バーが移動したときに、フレームワークによって呼び出されます。

```
virtual void OnMove();
```

### <a name="remarks"></a>解説

このメソッドは、内部`CEdit`オブジェクトの位置を更新することによって、既定のクラスの実装 ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) をオーバーライドします。

## <a name="cmfctoolbareditboxbuttononshow"></a><a name="onshow"></a>ボックスボタン::オンショー

ボタンが表示または非表示になったときに、フレームワークによって呼び出されます。

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
[in]ボタンを表示するかどうかを指定します。 このパラメーターが TRUE の場合、ボタンは表示されます。 それ以外の場合、ボタンは表示されません。

### <a name="remarks"></a>解説

このメソッドは *、bShow*が TRUE の場合はボタンを表示することによって、基本クラスの実装を拡張します ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) 。 それ以外の場合、このメソッドはボタンを非表示にします。

## <a name="cmfctoolbareditboxbuttononsize"></a><a name="onsize"></a>ボックスボタン::オンサイズ

親ツール バーのサイズまたは位置が変更され、この変更によってボタンのサイズが変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>パラメーター

*iサイズ*<br/>
[in]ボタンの新しい幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、内部`CEdit`オブジェクトのサイズと位置を更新することによって、既定のクラス実装[CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)をオーバーライドします。

## <a name="cmfctoolbareditboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>ボタン::オンアップデートツールチップ

親ツール バーがツールヒント テキストを更新するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]未使用。

*ボタンインデックス*<br/>
[in]未使用。

*wnd ツールヒント*<br/>
[in]ツールヒント テキストを表示するコントロール。

*Str*<br/>
[アウト]更新`CString`されたツールヒント テキストを受け取るオブジェクト。

### <a name="return-value"></a>戻り値

メソッドがツールヒント テキストを更新する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、ボタンの編集部分に関連付けられているツールヒント テキストを表示することによって、基本クラスの実装 ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) を拡張します。 内部`CEdit`オブジェクトが NULL の場合、または`CEdit`オブジェクトのウィンドウ ハンドルが既存のウィンドウを識別しない場合、このメソッドは何も実行せず、FALSE を返します。

## <a name="cmfctoolbareditboxbuttonsetcontents"></a><a name="setcontents"></a>ボックスボタン::コンテンツの設定

テキスト ボックス コントロールのテキストを設定します。

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>パラメーター

*sコンテンツ*<br/>
[in]設定する新しいテキストを指定します。

## <a name="cmfctoolbareditboxbuttonsetcontentsall"></a><a name="setcontentsall"></a>ボックスボタン::すべてのコンテンツを設定します。

指定した[コマンド](../../mfc/reference/cmfctoolbareditboxbutton-class.md)ID を持ち、テキスト ボックス内の指定したテキストを設定するオブジェクトを検索します。

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]テキストを変更するコントロールのコマンド ID を指定します。

*strコンテンツ*<br/>
[in]設定する新しいテキストを指定します。

### <a name="return-value"></a>戻り値

テキストが設定されている場合は 0 以外の値を返します。指定されたコマンド`CMFCToolBarEditBoxButton`ID を持つコントロールが存在しない場合は 0。

## <a name="cmfctoolbareditboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>ボックス ボタン::コンテキストメニューID

ボタンに関連付けられているショートカット メニューのリソース ID を指定します。

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]ショートカット メニューのリソース ID。

### <a name="remarks"></a>解説

ユーザーがツール バー ボタンを右クリックすると、フレームワークはリソース ID を使用してショートカット メニューを作成します。

## <a name="cmfctoolbareditboxbuttonsetflatmode"></a><a name="setflatmode"></a>ボックスボタン::セットフラットモード

アプリケーションの編集ボックス ボタンのフラット スタイルの外観を指定します。

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>パラメーター

*bフラット*<br/>
[in]エディット ボックス ボタンのフラット スタイル。 このパラメーターが TRUE の場合、フラット スタイルの外観は有効になります。それ以外の場合、フラット スタイルの外観は無効になります。

### <a name="remarks"></a>解説

エディット ボックス ボタンの既定のフラット スタイルは TRUE です。 アプリケーションの[フラット](#isflatmode)スタイルの外観を取得するには、メソッドを使用します。

## <a name="cmfctoolbareditboxbuttonsetstyle"></a><a name="setstyle"></a>ボックスボタン::セットスタイル

ツール バー エディット ボックス コントロールのスタイルを指定します。

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nStyle*<br/>
[in]設定する新しいスタイル。

### <a name="remarks"></a>解説

このメソッドは[、CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)を*nStyle*に設定アプリケーションがカスタマイズ モードのときにもテキスト ボックスを無効にし、アプリケーションがカスタマイズ モードでない場合に有効にします[(CMFC ツール バー::セットカスタマイズ モード](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode)と[CMFC ツール バー::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)を参照)。 有効なスタイル フラグの一覧については、「[ツール バー コントロールのスタイル](../../mfc/reference/toolbar-control-styles.md)」を参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[ボタンを置き換える](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)
