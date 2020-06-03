---
title: CMFCOutlookBar クラス
ms.date: 06/25/2018
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
helpviewer_keywords:
- CMFCOutlookBar [MFC], AllowDestroyEmptyTabbedPane
- CMFCOutlookBar [MFC], CanAcceptPane
- CMFCOutlookBar [MFC], CanSetCaptionTextToTabName
- CMFCOutlookBar [MFC], Create
- CMFCOutlookBar [MFC], CreateCustomPage
- CMFCOutlookBar [MFC], DoesAllowDynInsertBefore
- CMFCOutlookBar [MFC], FloatTab
- CMFCOutlookBar [MFC], GetButtonsFont
- CMFCOutlookBar [MFC], GetTabArea
- CMFCOutlookBar [MFC], IsMode2003
- CMFCOutlookBar [MFC], OnAfterAnimation
- CMFCOutlookBar [MFC], OnBeforeAnimation
- CMFCOutlookBar [MFC], OnScroll
- CMFCOutlookBar [MFC], RemoveCustomPage
- CMFCOutlookBar [MFC], SetButtonsFont
- CMFCOutlookBar [MFC], SetMode2003
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
ms.openlocfilehash: fe328cb0d857ff9154624d218b1b56362890ce81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369655"
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar クラス

Microsoft Outlook 2000 または Outlook 2003 の **ナビゲーション ウィンドウ** と同じ外観を持つタブ付きペインです。 オブジェクト`CMFCOutlookBar`には、[クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)オブジェクトと一連のタブが含まれています。 タブは[、クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)オブジェクトまたは`CWnd`派生オブジェクトのいずれかです。 ユーザーに対しては、Outlook バーは一連のボタンおよび表示領域として表示されます。 ユーザーがボタンをクリックすると、対応するコントロールまたはボタン ペインが表示されます。

## <a name="syntax"></a>構文

```cpp
class CMFCOutlookBar : public CBaseTabbedPane
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCOutlookBar::CMFCOutlookBar`|既定のコンストラクターです。|
|`CMFCOutlookBar::~CMFCOutlookBar`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|空のタブ付きペインを破棄できるかどうかを指定します。 [(CBase タブ付きペインをオーバーライドします。::破棄する空のタブ付きペイン](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|
|[ウィンドウの承認](#canacceptpane)|別のペインを Outlook バー ペインにドッキングできるかどうかを指定します。 (CDockable ペインをオーバーライドします。|
|[タブ名を設定します。](#cansetcaptiontexttotabname)|タブ付きペインのキャプションがアクティブなタブと同じテキストを表示するかどうかを決定します[(CBaseTabbedPane をオーバーライドします::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|
|[を作成します。](#create)|Outlook バー コントロールを作成します。|
|[ページの作成](#createcustompage)|Outlook のカスタム バー タブを作成します。|
|`CMFCOutlookBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[前に挿入 :Dする](#doesallowdyninsertbefore)|ユーザーが Outlook バーの外端にコントロール バーをドッキングできるかどうかを指定します。|
|[フロートタブ](#floattab)|ペインをフロートしますが、ペインが現在取り外し可能なタブにある場合に限ります[(CBaseTabbedPane::FloatTab.](../../mfc/reference/cbasetabbedpane-class.md#floattab)をオーバーライドします)。|
|[ボタンを取得します。](#getbuttonsfont)|Outlook バーのボタンのテキストのフォントを返します。|
|[を使用します。](#gettabarea)|Outlook バーのタブ領域のサイズと位置を返します。 [(CBase タブ付きペイン](../../mfc/reference/cbasetabbedpane-class.md#gettabarea)をオーバーライドします。.|
|`CMFCOutlookBar::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[を使用します。](#ismode2003)|Outlook バーの動作が、Outlook 2003 の動作を模倣するかどうかを決定します (解説を参照)。|
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|アニメーションを使用してアクティブなタブが設定された後に呼[び](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)出されます。|
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|アニメーションを使用してアクティブなタブとしてタブ ページが設定される前に[、CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)によって呼び出されます。|
|[CMFCOutlookBar::OnScroll](#onscroll)|Outlook バーが上下にスクロールしている場合に、フレームワークによって呼び出されます。|
|[ページの削除](#removecustompage)|Outlook のカスタム バー タブを削除します。|
|[フォントを設定します。](#setbuttonsfont)|Outlook バーのボタンのテキストのフォントを設定します。|
|[を設定します。](#setmode2003)|Outlook バーの動作が Outlook 2003 の動作を模倣するかどうかを指定します (解説を参照)。|

## <a name="remarks"></a>解説

Outlook バーの例については[、「OutlookDemo サンプル: MFC OutlookDemo アプリケーション](../../overview/visual-cpp-samples.md)」を参照してください。

## <a name="implementing-the-outlook-bar"></a>Outlook バーの実装

アプリケーションで、`CMFCOutlookBar` コントロールを使用するには、次の手順に従います。

1. `CMFCOutlookBar` オブジェクトをメイン フレーム ウィンドウ クラスに埋め込みます。

    ```cpp
    class CMainFrame : public CMDIFrameWnd
    {
        // ...
        CMFCOutlookBar m_wndOutlookBar;
        CMFCOutlookBarPane m_wndOutlookPane;
        // ...
    };
    ```

1. メイン フレームでWM_CREATE メッセージを処理する場合は[、CMFCOutlookBar::Create](#create)メソッドを呼び出して Outlook バー タブ コントロールを作成します。

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. 基になる`CMFCOutlookBarTabCtrl`ポインターを取得するには[、CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow)を使用します。

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. ボタンを含む各タブの[CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)オブジェクトを作成します。

    ```cpp
    m_wndOutlookPane.Create(&m_wndOutlookBar,
        AFX_DEFAULT_TOOLBAR_STYLE,
        ID_OUTLOOK_PANE_GENERAL,
        AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);

    // make the Outlook pane detachable (enable docking)
    m_wndOutlookPane.EnableDocking(CBRS_ALIGN_ANY);

    // add buttons
    m_wndOutlookPane.AddButton(theApp.LoadIcon (IDR_MAINFRAME),
        "About",
        ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON),
        "Open",
        ID_FILE_OPEN);
    ```

1. 呼び出し[CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)を呼び*bDetachable*出して新しいタブを追加します。 または、取り外し可能なページを追加するには[、CMFCOutlookBarTabCtrl::コントロールの追加](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol)を使用します。

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. 派生コントロール`CWnd`([たとえば、CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)) をタブとして追加するには、コントロールを作成し、Outlook バーに追加する[CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)を呼び出します。

> [!NOTE]
> 各[CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)オブジェクトおよび派生オブジェクトごとに一意`CWnd`のコントロール ID を使用する必要があります。

実行時に新しいページを動的に追加または削除するには[、CMFCOutlookBar:::カスタム ページ](#createcustompage)と[CMFCOutlook バー::カスタム ページの削除](#removecustompage)を使用します。

## <a name="outlook-2003-mode"></a>Outlook 2003 モード

Outlook 2003 モードでは、タブ ボタンは Outlook バー ペインの下部に配置されます。 ボタンを表示するための十分な領域がない場合、ペインの下部に沿ってツールバーのような領域にアイコンとして表示されます。

[Outlook 2003 モードを有効にするには、CMFCOutlookBar::SetMode2003](#setmode2003)を使用します。 Outlook バーの下部に表示されるアイコンを含むビットマップを設定するには[、CMFCOutlookBarTabCtrl::セットツールバーイメージリスト](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist)を使用します。 ビットマップ内のアイコンは、タブインデックスで並べ替える必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxoutlookbar.h

## <a name="cmfcoutlookbarallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>ウィンドウウィンドウウィンドウ

空のタブ付きペインを破棄できるかどうかを指定します。

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>戻り値

空のタブ付きペインを破棄できる場合は TRUE。それ以外の場合は FALSE。 既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

空のタブ付きペインを破棄できない場合、フレームワークは代わりに非表示にします。

## <a name="cmfcoutlookbarcanacceptpane"></a><a name="canacceptpane"></a>ウィンドウの承認

別のペインを Outlook バー ペインにドッキングできるかどうかを指定します。

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]このペインにドッキングされている別のペインへのポインター。

### <a name="return-value"></a>戻り値

True の場合は、別のペインを Outlook バー ペインにドッキングできます。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

Outlook バーが Outlook 2003 モードの場合、ドッキングはサポートされていないので、戻り値は FALSE です。

*pBar*パラメーターが NULL の場合、このメソッドは FALSE を返します。

それ以外の場合、このメソッドは基本メソッド[CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane)として動作しますが、ドッキングが有効になっていない場合でも、Outlook バーは別の Outlook バーをドッキングできます。

## <a name="cmfcoutlookbarcansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>タブ名を設定します。

タブ付きペインのキャプションに、アクティブなタブと同じテキストを表示するかどうかを指定します。

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>戻り値

True の場合、Outlook バー ウィンドウのキャプションがアクティブなタブのテキストに自動的に設定されます。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この機能を有効または無効にするには[、CBaseTabbedPane:::有効に設定キャプションテキストタブ名](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname)を使用します。

Outlook 2003 モードでは、この設定は常に有効になっています。

## <a name="cmfcoutlookbarcreate"></a><a name="create"></a>を作成します。

Outlook バー コントロールを作成します。

```cpp
virtual BOOL Create(
    LPCTSTR lpszCaption,
    CWnd* pParentWnd,
    const RECT& rect,
    UINT nID,
    DWORD dwStyle,
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>パラメーター

*一方、一時おくもみ*<br/>
[in]ウィンドウのキャプションを指定します。

*pParentWnd*<br/>
[in]親ウィンドウへのポインターを指定します。 NULL にすることはできません。

*Rect*<br/>
[in]見通しのバーのサイズと位置をピクセル単位で指定します。

*nID*<br/>
[in]コントロール ID を指定します。 アプリケーションで使用する他のコントロール ID とは異なる必要があります。

*Dwstyle*<br/>
[in]目的のコントロール バーのスタイルを指定します。 値については、「ウィンドウ[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)」を参照してください。

*コントロール バースタイル*<br/>
[in]特別なライブラリ定義スタイルを指定します。

*pContext*<br/>
[in]コンテキストを作成します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

オブジェクトは`CMFCOutlookBar`2 つの手順で作成します。 まず、コンストラクターを呼び出し`Create`、次に`CMFCOutlookBar`を呼び出します。

*dwControlBarStyle*で指定する使用可能なライブラリ定義スタイルの一覧については[、CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)を参照してください。

### <a name="example"></a>例

クラスのメソッドの使用方法を`Create`次の例に示します`CMFCOutlookBar`。 このコード スニペットは[、Outlook マルチ ビュー サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

## <a name="cmfcoutlookbarcreatecustompage"></a><a name="createcustompage"></a>ページの作成

Outlook のカスタム バー タブを作成します。

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>パラメーター

*ページ名*<br/>
[in]ページ ラベル。

*ページをアクティブにする*<br/>
[in]TRUE の場合、ページは作成時にアクティブになります。

*ドウ有効化ドッキング*<br/>
[in]ページがデタッチされるときに有効なドッキング側を指定するCBRS_ALIGN_フラグの組み合わせ。

*テキストラベルを有効にする*<br/>
[in]TRUE の場合、テキスト ラベルは、ページ上のボタンに対して有効になります。

### <a name="return-value"></a>戻り値

新しく作成されたページへのポインター。

### <a name="remarks"></a>解説

このメソッドを使用して、ユーザーが Outlook バーのカスタム ページを作成できるようにします。 アプリケーションごとに最大 100 ページを作成できます。 ページ コントロール ID は 0xF000 から始まります。 カスタム Outlook バー ページの合計数が 100 を超えると、作成に失敗します。

カスタム ページを削除するには[、CMFCOutlookBar::カスタム ページの削除](#removecustompage)を使用します。

## <a name="cmfcoutlookbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>前に挿入 :Dする

ユーザーが Outlook バーの外端にペインをドッキングできるかどうかを指定します。

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

既定の実装では FALSE が返されます。

### <a name="remarks"></a>解説

フレームワークは、動的`DoesAllowDynInsertBefore`ペインをドッキングする場所を検索するときにメソッドを呼び出します。 関数が FALSE を返した場合、フレームワークはペインの外側の端に動的ペインをドッキングできません。

通常は、静的な非フローティング コントロールとして Outlook バーを作成します。 この関数を派生クラスでオーバーライドし、TRUE を返してこの動作を変更できます。

> [!NOTE]
> 動的ペインはドッキング時にドッキングされた静的ペインの状態をチェックするので、可能な限り静的ペインの後に動的ペインをドッキングする必要があります。

## <a name="cmfcoutlookbarfloattab"></a><a name="floattab"></a>フロートタブ

ペインをフローティングします。

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]フローティングするペインへのポインター。

*タブID*<br/>
[in]浮動するタブの 0 から始まるインデックス。

*ドックメソッド*<br/>
[in]ペインをフロートにする方法を指定します。  詳細については[、「CBaseTabbedPane::フロートタブ](../../mfc/reference/cbasetabbedpane-class.md#floattab)」を参照してください。

*bHide*<br/>
[in]フローティングの前にペインを非表示にする場合は TRUE。それ以外の場合は FALSE。 このメソッドの基本クラスバージョンとは異なり、このパラメーターにはデフォルト値がありません。

### <a name="return-value"></a>戻り値

ペインが浮動表示された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Outlook バー コントロールの最後の残りのタブをフローティングに使用できない点を除いて[、CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)に似ています。

## <a name="cmfcoutlookbargetbuttonsfont"></a><a name="getbuttonsfont"></a>ボタンを取得します。

Outlook バーのページ ボタン タブのテキストのフォントを返します。

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>戻り値

Outlook バー ページ のボタン タブにテキストを表示するために使用されるフォント オブジェクトへのポインター。

### <a name="remarks"></a>解説

この関数を使用して、Outlook ページ ボタン タブにテキストを表示するために使用するフォントを取得します。 フォントを設定するには[、次](#setbuttonsfont)のコマンドを実行します。

## <a name="cmfcoutlookbargettabarea"></a><a name="gettabarea"></a>を使用します。

Outlook バーのタブ領域のサイズと位置を指定します。

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>パラメーター

*レクトタブエリアトップ*<br/>
[アウト]関数が返されるときに、最上位のタブ領域のサイズと位置をクライアント座標で格納します。

*タブエリア下部*<br/>
[アウト]関数が返されるときに、下部タブ領域のサイズと位置 (クライアント座標) を格納します。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを呼び出して、ターゲット ペインへのドッキングの種類を決定します。 フレームワークは、ユーザーがドッキングするペインをターゲット ペインのタブ領域上にドラッグすると判断すると、最初のペインをターゲット ペインの新しいタブとして追加しようとします。 それ以外の場合は、最初のペインをターゲット ペインの適切な側にドッキングしようとします。 フレームワークは、追加のドッキング ペインを収容するスライダーを持つ新しいコンテナーを作成します。

既定の`GetTabArea`実装では、Outlook バーが静的な場合は、Outlook バーのクライアント領域全体を返します。つまり、Outlook バーをフローティングできない場合です。 それ以外の場合は、Outlook バー コントロールの上部と下部にあるページ ボタンの領域が返されます。

この動作を変更するには、派生`CMFCOutlookBar`したクラスでこのメソッドをオーバーライドします。

## <a name="cmfcoutlookbarismode2003"></a><a name="ismode2003"></a>を使用します。

Outlook バーの動作が、Outlook 2003 の動作を模倣するかどうかを指定します。

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>戻り値

Outlook バーが Office 2003 モードで実行されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このモードを有効にするには[、次のコマンドを](#setmode2003)実行します。

## <a name="cmfcoutlookbaronafteranimation"></a><a name="onafteranimation"></a>アニメーションの後に

アニメーションを使用してアクティブなタブが設定された後に呼[び](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)出されます。

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>パラメーター

*nページ*<br/>
[in]アクティブにされたタブ ページの 0 から始まるインデックス。

### <a name="remarks"></a>解説

アクティブなタブを設定する視覚効果は、アニメーションを有効にしたかどうかによって異なります。 詳細については、「[アニメーションを有効に](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation)する」を参照してください。

## <a name="cmfcoutlookbaronbeforeanimation"></a><a name="onbeforeanimation"></a>アニメーションの前に

アニメーションを使用してアクティブなタブとしてタブ ページが設定される前に[、CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)によって呼び出されます。

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>パラメーター

*nページ*<br/>
[in]アクティブに設定されるタブ ページの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

新しいアクティブなタブの設定でアニメーションを使用する場合は TRUE を返し、アニメーションを無効にする場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcoutlookbaronscroll"></a><a name="onscroll"></a>スクロール時に

Outlook バーが上下にスクロールしている場合に、フレームワークによって呼び出されます。

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>パラメーター

*bダウン*<br/>
[in]True を指定すると、Outlook バーが下にスクロールしている場合は FALSE、上にスクロールしている場合は FALSE になります。

### <a name="remarks"></a>解説

## <a name="cmfcoutlookbarremovecustompage"></a><a name="removecustompage"></a>ページの削除

Outlook のカスタム バー タブ ページを削除します。

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>パラメーター

*uiページ*<br/>
[in]親の Outlook ウィンドウ内のページの 0 から始まるインデックス。

*をクリックします。*<br/>
[in]親の Outlook ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

カスタム ページが正常に削除された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

カスタム ページを削除します。 ページが削除されると、そのコントロール ID は使用可能な ID のプールに返されます。

削除するページが現在存在する[クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)オブジェクトへのポインターを指定する必要があります。 ユーザーは、別の Outlook バー間で取り外し可能なページを移動できますが、カスタム ページに関する情報は[、CMFCOutlookBar:CreateCustomPage](#createcustompage)という名前の Outlook バー オブジェクトに格納されています。

Outlook ウィンドウへのポインターを取得するには[、CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow)を使用します。

## <a name="cmfcoutlookbarsetbuttonsfont"></a><a name="setbuttonsfont"></a>フォントを設定します。

Outlook バーのボタンのテキストのフォントを設定します。

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
[in]新しいフォントを指定します。

*引き出し*<br/>
[in]TRUE の場合は、Outlook バーが再描画されます。

### <a name="remarks"></a>解説

このメソッドは、Outlook タブ ページ ボタンに表示されるテキストのフォントを設定するために使います。

## <a name="cmfcoutlookbarsetmode2003"></a><a name="setmode2003"></a>を設定します。

Outlook バーの動作が Outlook 2003 の動作と似ているかどうかを指定します。

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>パラメーター

*bモード2003*<br/>
[in]TRUE の場合、Office 2003 モードが有効になります。

### <a name="remarks"></a>解説

この機能を使用して、Office 2003 モードを有効または無効にします。 このモードでは、Outlook バーには、カスタマイズ ボタンを備えた追加のツールバーが表示されます。 Outlook バーの動作は、Office 2003 の Outlook バーの動作に準拠しています。

既定では、このモードは無効になっています。

> [!NOTE]
> この関数は[、CMFCOutlookBar::作成](#create)の前に呼び出す必要があります。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)
