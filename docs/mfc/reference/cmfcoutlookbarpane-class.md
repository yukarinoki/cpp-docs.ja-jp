---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
ms.openlocfilehash: 82d8f1da0640e5b487a06585c72279e7d7ffdf99
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369637"
---
# <a name="cmfcoutlookbarpane-class"></a>クラス

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

Outlook バー ( [CMFCOutlookBar クラス](../../mfc/reference/cmfctoolbar-class.md)) に挿入できる[CMFC](../../mfc/reference/cmfcoutlookbar-class.md)ツール バー クラスから派生したコントロール。 Outlook バー ペインには、大きいボタンの列があります。 ボタンのリストがペインより長い場合、ユーザーはリストを上下にスクロールできます。 ユーザーが Outlook バー ペインを Outlook バーから切り離すと、そのペインをフローティング状態にするかメイン フレーム ウィンドウにドッキングできます。

## <a name="syntax"></a>構文

```
class CMFCOutlookBarPane : public CMFCToolBar
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|既定のコンストラクターです。|
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ボタンの追加](#addbutton)|Outlook バー ペインにボタンを追加します。|
|[をクリックします。](#canbeattached)|ペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを決定します。 [(CBasePane をオーバーライドします::CanBe添付.)](../../mfc/reference/cbasepane-class.md#canbeattached)|
|`CMFCOutlookBarPane::CanBeRestored`|カスタマイズ後に、システムがツール バーを元の状態に復元できるかどうかを決定します。 [(CMFCツールバーをオーバーライドします::缶詰復元](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[ウィンドウすべて](#clearall)|Outlook バー ウィンドウのイメージで使用されているリソースを解放します。|
|[を作成します。](#create)|Outlook バー ペインを作成します。|
|`CMFCOutlookBarPane::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCOutlookBarPane::Dock`|フレームワークが Outlook バー ペインをドッキングするために呼び出します。 ( `CPane::Dock`をオーバーライドします)。|
|[をクリックします。](#enablepagescrollmode)|Outlook バー ウィンドウのスクロール バーの矢印ボタンを、ボタンの一覧をページごとに進めるか、ボタンごとに進めるかを指定します。|
|[コントロール バー ペイン::取得レギュラーカラー](#getregularcolor)|Outlook バー ペインの通常の (選択されていない) テキストの色を返します。|
|`CMFCOutlookBarPane::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[テクスチャーを表示します。](#isbackgroundtexture)|Outlook バー ペインにバックグラウンド イメージが読み込まれているかどうかを判断します。|
|`CMFCOutlookBarPane::IsChangeState`|フローティング ペインをドッキングできるかどうかを判断します。 ( `CPane::IsChangeState`をオーバーライドします)。|
|[をクリックします。](#isdrawshadedhighlight)|ボタンが強調表示され、背景イメージが表示されるときに、ボタンの境界線をシェーディングするかどうかを指定します。|
|`CMFCOutlookBarPane::OnBeforeFloat`|ペインがフロートされるときに、フレームワークによって呼び出されます。 (CPane をオーバーライド[します::オン事前フロート](../../mfc/reference/cpane-class.md#onbeforefloat).)|
|[ボタンの削除](#removebutton)|指定したコマンド ID を持つボタンを削除します。|
|`CMFCOutlookBarPane::RestoreOriginalstate`|ツール バーを元の状態に戻します。 (CMFC ツールバーをオーバーライド[します。:元に戻します](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate)。|
|[を切り開く](#setbackcolor)|背景色を設定します。|
|[を切り開く](#setbackimage)|背景イメージを設定します。|
|[を設定します。](#setdefaultstate)|Outlook バー ペインを元のボタンのセットにリセットします。|
|[を設定します。](#setextraspace)|Outlook バー ペインのボタンの周囲に使用されるパディングのピクセル数を設定します。|
|[ウィンドウ::テキストの色を設定します。](#settextcolor)|Outlook バー ペインで、標準テキストと強調表示されたテキストの色を設定します。|
|[ウィンドウ::透明な色を設定します。](#settransparentcolor)|Outlook バー ペインの透明色を設定します。|
|`CMFCOutlookBarPane::SmartUpdate`|Outlook バーを更新するために内部的に使用されます。 ( `CMFCToolBar::SmartUpdate`をオーバーライドします)。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[メニュー項目を有効にする](#enablecontextmenuitems)|カスタマイズ モードで表示するショートカット メニュー項目を指定します。|
|[ボタンの削除](#removeallbuttons)|Outlook バー ペインからすべてのボタンを削除します。 (CMFC ツールバーをオーバーライド[します::すべてのボタンを削除](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons)します。|

## <a name="remarks"></a>解説

Outlook バーを実装する方法の詳細については[、「CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照してください。

Outlook バーの例については、OutlookDemo サンプル プロジェクトを参照してください。

## <a name="example"></a>例

クラスのさまざまなメソッドを使用する方法を次の例に`CMFCOutlookBarPane`示します。 この例では、Outlook バー ペインを作成し、ページスクロール モードを有効にし、ドッキングを有効にし、Outlook バーの背景色を設定する方法を示します。 このコード スニペットは[、Outlook マルチ ビュー サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[ツールバー](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxoutlookバーペイン.h

## <a name="cmfcoutlookbarpaneaddbutton"></a><a name="addbutton"></a>ボタンの追加

Outlook バー ペインにボタンを追加します。

```
BOOL AddButton(
    UINT uiImage,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    UINT uiImage,
    UINT uiLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    LPCTSTR szBmpFileName,
    LPCTSTR szLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HBITMAP hBmp,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HICON hIcon,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1,
    BOOL bAlphaBlend=FALSE);
```

### <a name="parameters"></a>パラメーター

*uiイメージ*<br/>
[in]ビットマップのリソース識別子を指定します。

*ラベル*<br/>
[in]ボタンのテキストを指定します。

*コマンド*<br/>
[in]ボタン コントロールの ID を指定します。

*挿入*<br/>
[in]ボタンを挿入する Outlook バーのページの 0 から始まるインデックスを指定します。

*uiラベル*<br/>
[in]文字列リソース ID。

*ファイル名*<br/>
[in]ロードするディスク イメージ ファイルの名前を指定します。

*szラベル*<br/>
[in]ボタンのテキストを指定します。

*hBmp*<br/>
[in]ボタンのビットマップへのハンドル。

*Hicon*<br/>
[in]ボタンのアイコンへのハンドル。

### <a name="return-value"></a>戻り値

ボタンが正常に追加された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Outlook バーのページに新しいボタンを挿入するために使います。 ボタンのイメージは、アプリケーションリソースまたはディスクファイルからロードできます。

*uiPageID*で指定されたページ ID が -1 の場合、ボタンは最初のページに挿入されます。

*iInsertAt*で指定されたインデックスが -1 の場合、ボタンはページの最後に追加されます。

## <a name="cmfcoutlookbarpanecanbeattached"></a><a name="canbeattached"></a>をクリックします。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcoutlookbarpaneclearall"></a><a name="clearall"></a>ウィンドウすべて

Outlook バー ウィンドウのイメージで使用されているリソースを解放します。

```
void ClearAll();
```

### <a name="remarks"></a>解説

このメソッドは、Outlook バー ペインで使用されるイメージで呼び出される[CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear)を直接呼び出します。

## <a name="cmfcoutlookbarpanecreate"></a><a name="create"></a>を作成します。

Outlook バー ペインを作成します。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,
    UINT uiID=(UINT)-1,
    DWORD dwControlBarStyle=0);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
[in]Outlook バー ペイン コントロールの親ウィンドウを指定します。 NULL にすることはできません。

*Dwstyle*<br/>
[in]ウィンドウ スタイル。  ウィンドウ スタイルの一覧については、「[ウィンドウ](../../mfc/reference/styles-used-by-mfc.md#window-styles)スタイル」を参照してください。

*Uiid*<br/>
[in]コントロール ID。 コントロールの状態の保存を有効にするには、一意である必要があります。

*コントロール バースタイル*<br/>
[in]Outlook バーから切り離したときの Outlook バー ペイン コントロールの動作を定義する特殊なスタイルを指定します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトを`CMFCOutlookBarPane`構築するには、まずコンストラクターを呼び出し、`Create`を`CMFCOutlookBarPane`呼び出します。

詳細については`dwControlBarStyle`[、「CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)」を参照してください。

## <a name="cmfcoutlookbarpaneenablecontextmenuitems"></a><a name="enablecontextmenuitems"></a>メニュー項目を有効にする

カスタマイズ モードで表示するショートカット メニュー項目を指定します。

```
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,
    CMenu* pPopup);
```

### <a name="parameters"></a>パラメーター

*ボタン*<br/>
[in]ユーザーがクリックしたツール バー ボタンへのポインター。

*pPopup*<br/>
[in]ショートカット メニューへのポインター。

### <a name="return-value"></a>戻り値

ショートカット メニューを表示する必要がある場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークがカスタマイズ モードで表示するフレームワーク標準のショートカット メニューを変更するには、このメソッドをオーバーライドします。

既定の実装では、カスタマイズ モード ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) がチェックされ、TRUE に設定されている場合は **、削除**以外のすべてのショートカット メニュー項目が無効になります。 次に、入力パラメータを に渡す`CMFCToolBar::EnableContextMenuItems`だけです。

> [!NOTE]
> *コンテキスト メニュー*は、ショートカット メニューの同義語です。

## <a name="cmfcoutlookbarpaneenablepagescrollmode"></a><a name="enablepagescrollmode"></a>をクリックします。

Outlook バー ウィンドウのスクロール バーの矢印ボタンをクリックして、ボタンの一覧をページごとに進めるか、ボタンごとに進めるかを指定します。

```
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```

### <a name="parameters"></a>パラメーター

*ページスクロール*<br/>
[in]TRUE の場合は、ページスクロールモードを有効にします。 FALSE の場合は、ページスクロールモードを無効にします。

## <a name="cmfcoutlookbarpanegetregularcolor"></a><a name="getregularcolor"></a>コントロール バー ペイン::取得レギュラーカラー

Outlook バー ペインの標準 (選択されていない) テキストの色を返します。

```
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;
```

### <a name="return-value"></a>戻り値

RGB カラー値としての現在のテキストの色。

### <a name="remarks"></a>解説

Outlook バーの現在の (通常および選択された) テキストの色を設定するには[、CMFCOutlook バー ペイン](#settextcolor)を使用します。 既定のテキストの色を取得するには、COLOR_WINDOWインデックスを使用して[GetSysColor](/windows/win32/api/winuser/nf-winuser-getsyscolor)関数を呼び出します。

## <a name="cmfcoutlookbarpaneisbackgroundtexture"></a><a name="isbackgroundtexture"></a>テクスチャーを表示します。

Outlook バー ペインにバックグラウンド イメージが読み込まれているかどうかを判断します。

```
BOOL IsBackgroundTexture() const;
```

### <a name="return-value"></a>戻り値

表示する背景イメージがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

関数を呼び出して、背景イメージ[を](#setbackimage)追加できます。

背景イメージがない場合は[、CMFCOutlookBarPane::SetBackColor](#setbackcolor)を使用して指定された色で背景が描画されます。

## <a name="cmfcoutlookbarpaneisdrawshadedhighlight"></a><a name="isdrawshadedhighlight"></a>をクリックします。

ボタンが強調表示され、背景イメージが表示されるときに、ボタンの境界線をシェーディングするかどうかを指定します。

```
BOOL IsDrawShadedHighlight() const;
```

### <a name="return-value"></a>戻り値

TRUE ボタンの境界線がシェーディングされている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcoutlookbarpaneremoveallbuttons"></a><a name="removeallbuttons"></a>ボタンの削除

Outlook バー ペインからすべてのボタンを削除します。

```
virtual void RemoveAllButtons();
```

## <a name="cmfcoutlookbarpaneremovebutton"></a><a name="removebutton"></a>ボタンの削除

指定したコマンド ID を持つボタンを削除します。

```
BOOL RemoveButton(UINT iIdCommand);
```

### <a name="parameters"></a>パラメーター

*コマンド*<br/>
[in]削除するボタンのコマンド ID を指定します。

### <a name="return-value"></a>戻り値

ボタンが正常に削除された場合は TRUE。指定されたコマンド ID が無効な場合は FALSE。

## <a name="cmfcoutlookbarpanesetbackcolor"></a><a name="setbackcolor"></a>を切り開く

Outlook バーの背景色を設定します。

```
void SetBackColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]新しい背景色を指定します。

### <a name="remarks"></a>解説

Outlook バーの現在の背景色を設定します。 背景色は、背景画像がない場合にのみ使用されます。

## <a name="cmfcoutlookbarpanesetbackimage"></a><a name="setbackimage"></a>を切り開く

背景イメージを設定します。

```
void SetBackImage(UINT uiImageID);
```

### <a name="parameters"></a>パラメーター

*イメージID*<br/>
[in]イメージ リソース ID を指定します。

### <a name="remarks"></a>解説

Outlook バーの背景イメージを設定します。 背景イメージの一覧は、埋め込まれた[CMFCToolBarImages クラス オブジェクト](../../mfc/reference/cmfctoolbarimages-class.md)によって管理されます。

## <a name="cmfcoutlookbarpanesetdefaultstate"></a><a name="setdefaultstate"></a>を設定します。

Outlook バー ペインを元のボタンのセットにリセットします。

```
void SetDefaultState();
```

### <a name="remarks"></a>解説

このメソッドは、Outlook バーのボタンを元のセットに戻します。 このメソッドは、`CMFCOutlookBarPane::RestoreOriginalstate`に似ていますが、Outlook バー ペインの再描画は行われません。

## <a name="cmfcoutlookbarpanesetextraspace"></a><a name="setextraspace"></a>を設定します。

Outlook バー ペインのボタンの周囲に使用されるパディングのピクセル数を設定します。

```
void SetExtraSpace()
```

## <a name="cmfcoutlookbarpanesettextcolor"></a><a name="settextcolor"></a>ウィンドウ::テキストの色を設定します。

Outlook バー ペインで、標準テキストと強調表示されたテキストの色を設定します。

```
void SetTextColor(
    COLORREF clrRegText,
    COLORREF clrSelText=0);
```

### <a name="parameters"></a>パラメーター

*テキスト*<br/>
[in]選択されていないテキストの新しい色を指定します。

*テキスト*<br/>
[in]選択したテキストの新しい色を指定します。

## <a name="cmfcoutlookbarpanesettransparentcolor"></a><a name="settransparentcolor"></a>ウィンドウ::透明な色を設定します。

Outlook バー ペインの透明色を設定します。

```
void SetTransparentColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
新しい透明色を指定します。

### <a name="remarks"></a>解説

透明な画像を表示するには、透明な色が必要です。 イメージ内でこの色が出現する場合は、背景色で描画されます。  背景画像と前景画像のブレンドはありません。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[クラス](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
