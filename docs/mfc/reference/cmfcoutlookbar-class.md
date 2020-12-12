---
description: '詳細情報: CMFCOutlookBar クラス'
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
ms.openlocfilehash: e54e44e702aaf8d6883ada6be9c127f63ecee97d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265039"
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar クラス

Microsoft Outlook 2000 または Outlook 2003 の **ナビゲーション ウィンドウ** と同じ外観を持つタブ付きペインです。 オブジェクトには、 `CMFCOutlookBar` [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md) オブジェクトと一連のタブが含まれています。 これらのタブには、 [Cmfcoutlookbarpane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md) オブジェクトまたは派生オブジェクトのいずれかを指定でき `CWnd` ます。 ユーザーに対しては、Outlook バーは一連のボタンおよび表示領域として表示されます。 ユーザーがボタンをクリックすると、対応するコントロールまたはボタン ペインが表示されます。

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
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|空のタブ付きペインを破棄できるかどうかを指定します。 ( [CBaseTabbedPane:: AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane)をオーバーライドします。)|
|[CMFCOutlookBar:: CanAcceptPane](#canacceptpane)|別のペインを Outlook バーペインにドッキングできるかどうかを決定します。 (CDockablePane:: CanAcceptPane をオーバーライドします)。|
|[CMFCOutlookBar:: CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|タブ付きペインのキャプションにアクティブなタブと同じテキストを表示するかどうかを決定します ( [CBaseTabbedPane:: CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname)をオーバーライドします)。|
|[CMFCOutlookBar:: 作成](#create)|Outlook バーコントロールを作成します。|
|[CMFCOutlookBar:: CreateCustomPage](#createcustompage)|カスタム Outlook バータブを作成します。|
|`CMFCOutlookBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCOutlookBar::D oesAllowDynInsertBefore](#doesallowdyninsertbefore)|ユーザーが Outlook バーの外縁にコントロールバーをドッキングできるかどうかを決定します。|
|[CMFCOutlookBar:: FloatTab](#floattab)|ウィンドウをフローティングしますが、ペインが現在切り離し可能なタブに存在する場合に限ります。 ( [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)をオーバーライドします)。|
|[CMFCOutlookBar:: GetButtonsFont](#getbuttonsfont)|Outlook バーのボタンのテキストのフォントを返します。|
|[CMFCOutlookBar:: GetTabArea](#gettabarea)|Outlook バーのタブ領域のサイズと位置を返します。 ( [CBaseTabbedPane:: GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea)をオーバーライドします)。|
|`CMFCOutlookBar::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCOutlookBar:: IsMode2003](#ismode2003)|Outlook バーの動作が Outlook 2003 Microsoft Office を模倣しているかどうかを判断します (「解説」を参照してください)。|
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|アニメーションを使用してアクティブなタブを設定した後、 [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) によって呼び出されます。|
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|アニメーションを使用してタブページがアクティブなタブとして設定される前に、 [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) によって呼び出されます。|
|[CMFCOutlookBar::OnScroll](#onscroll)|Outlook バーが上下にスクロールしている場合に、フレームワークによって呼び出されます。|
|[CMFCOutlookBar:: RemoveCustomPage](#removecustompage)|カスタム Outlook バータブを削除します。|
|[CMFCOutlookBar:: SetButtonsFont](#setbuttonsfont)|Outlook バーのボタンのテキストのフォントを設定します。|
|[CMFCOutlookBar:: SetMode2003](#setmode2003)|Outlook バーの動作が Outlook 2003 の動作を模倣するかどうかを指定します (「解説」を参照してください)。|

## <a name="remarks"></a>解説

Outlook バーの例については、「 [Outlookdemo Sample: MFC Outlookdemo Application](../../overview/visual-cpp-samples.md)」を参照してください。

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

1. メインフレームで WM_CREATE メッセージを処理するときに、 [Cmfcoutlookbar:: CREATE](#create) メソッドを呼び出して Outlook バータブコントロールを作成します。

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. `CMFCOutlookBarTabCtrl` [CBaseTabbedPane:: GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow)を使用して、基になるへのポインターを取得します。

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. 各タブのボタンを含む [Cmfcoutlookbarpane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md) オブジェクトを作成します。

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

1. [CMFCOutlookBarTabCtrl:: addtab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)を呼び出して、新しいタブをそれぞれ追加します。*Bdetachable* 可能なパラメーターを FALSE に設定して、ページを非デタッチにします。 または、 [CMFCOutlookBarTabCtrl:: AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) を使用して、切り離し可能ページを追加します。

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. 派生した `CWnd` コントロール (たとえば、 [CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)) をタブとして追加するには、コントロールを作成し、 [CMFCOutlookBarTabCtrl:: addtab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) を呼び出して、それを Outlook バーに追加します。

> [!NOTE]
> 各 [Cmfcoutlookbarpane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md) オブジェクトと、それぞれの派生オブジェクトに対して、一意のコントロール id を使用する必要があり `CWnd` ます。

実行時に新しいページを動的に追加または削除するには、 [Cmfcoutlookbar:: CreateCustomPage](#createcustompage) と [Cmfcoutlookbar:: RemoveCustomPage](#removecustompage)を使用します。

## <a name="outlook-2003-mode"></a>Outlook 2003 モード

Outlook 2003 モードでは、タブボタンは Outlook バーペインの下部に配置されます。 ボタンを表示するための十分な領域がない場合は、ウィンドウの下部にあるツールバーのような領域にアイコンとして表示されます。

[Cmfcoutlookbar:: SetMode2003](#setmode2003)を使用して Outlook 2003 モードを有効にします。 [CMFCOutlookBarTabCtrl:: SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist)を使用して、Outlook バーの下部に表示されるアイコンを含むビットマップを設定します。 ビットマップ内のアイコンは、タブインデックスで並べられている必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxoutlookbar

## <a name="cmfcoutlookbarallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a> CMFCOutlookBar:: AllowDestroyEmptyTabbedPane

空のタブ付きペインを破棄できるかどうかを指定します。

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>戻り値

空のタブ付きペインを破棄できる場合は TRUE。それ以外の場合は FALSE。 既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

空のタブ付きペインを破棄できない場合は、フレームワークによって非表示になります。

## <a name="cmfcoutlookbarcanacceptpane"></a><a name="canacceptpane"></a> CMFCOutlookBar:: CanAcceptPane

別のペインを Outlook バーペインにドッキングできるかどうかを決定します。

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
からこのペインにドッキングされている別のペインへのポインター。

### <a name="return-value"></a>戻り値

別のペインを Outlook バーペインにドッキングできる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

Outlook バーが Outlook 2003 モードの場合、ドッキングはサポートされていないため、戻り値は FALSE になります。

*Pbar* パラメーターが NULL の場合、このメソッドは FALSE を返します。

それ以外の場合、このメソッドは、基本メソッド [Cbasepane:: CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane)として動作します。ただし、ドッキングが有効になっていない場合でも、outlook バーは別の outlook バーをドッキング可能にすることができます。

## <a name="cmfcoutlookbarcansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a> CMFCOutlookBar:: CanSetCaptionTextToTabName

タブ付きペインのキャプションに、アクティブなタブと同じテキストを表示するかどうかを決定します。

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>戻り値

Outlook バーウィンドウのキャプションがアクティブなタブのテキストに自動的に設定される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この機能を有効または無効にするには、 [CBaseTabbedPane:: EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) を使用します。

Outlook 2003 モードでは、この設定は常に有効になります。

## <a name="cmfcoutlookbarcreate"></a><a name="create"></a> CMFCOutlookBar:: 作成

Outlook バーコントロールを作成します。

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

*lpszCaption*<br/>
からウィンドウのキャプションを指定します。

*pParentWnd*<br/>
から親ウィンドウへのポインターを指定します。 NULL にすることはできません。

*rect*<br/>
からOutlook バーのサイズと位置をピクセル単位で指定します。

*nID*<br/>
からコントロール ID を指定します。 アプリケーションで使用される他のコントロール Id とは別にする必要があります。

*dwStyle*<br/>
から必要なコントロールバーのスタイルを指定します。 使用可能な値については、「 [ウィンドウスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)」を参照してください。

*dwControlBarStyle*<br/>
からライブラリで定義された特殊なスタイルを指定します。

*pContext*<br/>
からコンテキストを作成します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

オブジェクトを構築するには、 `CMFCOutlookBar` 2 つの手順を実行します。 まず、コンストラクターを呼び出し、次に `Create` を呼び出します。これにより、outlook バーコントロールが作成され、オブジェクトにアタッチさ `CMFCOutlookBar` れます。

*Dwcontrolbarstyle* によって指定されるライブラリ定義の使用可能なスタイルの一覧については、「 [Cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) 」を参照してください。

### <a name="example"></a>例

クラスのメソッドを使用する方法を次の例に示し `Create` `CMFCOutlookBar` ます。 このコードスニペットは、 [Outlook マルチビューサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

## <a name="cmfcoutlookbarcreatecustompage"></a><a name="createcustompage"></a> CMFCOutlookBar:: CreateCustomPage

カスタム Outlook バータブを作成します。

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszPageName*<br/>
からページラベル。

*B[アクティブ] ページ*<br/>
からTRUE の場合、作成時にページがアクティブになります。

*dwEnabledDocking*<br/>
からページがデタッチされたときに有効なドッキング側を指定する CBRS_ALIGN_ フラグの組み合わせ。

*bEnableTextLabels*<br/>
からTRUE の場合、ページ上に存在するボタンのテキストラベルが有効になります。

### <a name="return-value"></a>戻り値

新しく作成されたページへのポインター。作成に失敗した場合は NULL。

### <a name="remarks"></a>解説

ユーザーがカスタム Outlook バーページを作成できるようにするには、この方法を使用します。 アプリケーションごとに最大100ページを作成できます。 ページコントロール Id は、0xF000 から始まります。 カスタム Outlook バーページの合計数が100を超えた場合、作成は失敗します。

カスタムページを削除するには、 [Cmfcoutlookbar:: RemoveCustomPage](#removecustompage) を使用します。

## <a name="cmfcoutlookbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCOutlookBar::D oesAllowDynInsertBefore

ユーザーが Outlook バーの外縁にウィンドウをドッキングできるかどうかを指定します。

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

既定の実装では、FALSE が返されます。

### <a name="remarks"></a>解説

フレームワークは、 `DoesAllowDynInsertBefore` 動的ペインをドッキングする場所を検索するときに、メソッドを呼び出します。 関数が FALSE を返す場合、フレームワークはペインの外縁に動的ペインをドッキングすることを許可しません。

通常、Outlook バーは静的な非フローティングコントロールとして作成します。 派生クラスでこの関数をオーバーライドし、TRUE を返すことでこの動作を変更できます。

> [!NOTE]
> 動的ペインはドッキング時にドッキングされた静的ペインの状態を確認するため、可能な限り、静的ペインの後に動的ペインをドッキングする必要があります。

## <a name="cmfcoutlookbarfloattab"></a><a name="floattab"></a> CMFCOutlookBar:: FloatTab

ペインをフローティングします。

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
からフローティングするペインへのポインター。

*nTabID*<br/>
からフローティングするタブの0から始まるインデックス。

*dockMethod*<br/>
からペインをフローティングするために使用するメソッドを指定します。  詳細については、「 [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)」を参照してください。

*bHide*<br/>
からフローティングの前にペインを非表示にする場合は TRUE。それ以外の場合は FALSE。 このメソッドの基本クラスのバージョンとは異なり、このパラメーターには既定値がありません。

### <a name="return-value"></a>戻り値

ペインがフローティングになった場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) に似ていますが、Outlook バーコントロールの最後の残りのタブはフローティングにできない点が異なります。

## <a name="cmfcoutlookbargetbuttonsfont"></a><a name="getbuttonsfont"></a> CMFCOutlookBar:: GetButtonsFont

Outlook バーの [ページ] ボタンのタブに表示されるテキストのフォントを返します。

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>戻り値

Outlook バーページのボタンタブにテキストを表示するために使用されるフォントオブジェクトへのポインター。

### <a name="remarks"></a>解説

Outlook ページのボタンタブにテキストを表示するために使用されるフォントを取得するには、この関数を使用します。 [Cmfcoutlookbar:: SetButtonsFont](#setbuttonsfont)でを呼び出すことにより、フォントを設定できます。

## <a name="cmfcoutlookbargettabarea"></a><a name="gettabarea"></a> CMFCOutlookBar:: GetTabArea

Outlook バーのタブ領域のサイズと位置を決定します。

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>パラメーター

*rectTabAreaTop*<br/>
入出力関数が戻るときの、上部のタブ領域のサイズと位置 (クライアント座標) を格納します。

*rectTabAreaBottom*<br/>
入出力関数が戻るときの下部タブ領域のサイズと位置 (クライアント座標) を格納します。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを呼び出して、ターゲットウィンドウへのドッキングの種類を決定します。 フレームワークは、ターゲットペインのタブ領域の上にドッキングするペインをユーザーがドラッグしたと判断したときに、最初のペインを [ターゲット] ペインの新しいタブとして追加しようとします。 それ以外の場合は、最初のペインをターゲットペインの適切な側にドッキングしようとします。 フレームワークは、追加のドッキングペインに対応するスライダーを備えた新しいコンテナーを作成します。

Outlook バーが静的な場合、つまり outlook バーをフローティングできない場合、の既定の実装は `GetTabArea` outlook バーのクライアント領域全体を返します。 それ以外の場合は、ページのボタンが Outlook バーコントロールの上部および下部に表示される領域を返します。

この動作を変更するには、から派生したクラスでこのメソッドをオーバーライドし `CMFCOutlookBar` ます。

## <a name="cmfcoutlookbarismode2003"></a><a name="ismode2003"></a> CMFCOutlookBar:: IsMode2003

Outlook 2003 Microsoft Office の Outlook バーの動作を模倣するかどうかを指定します。

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>戻り値

Outlook バーが Microsoft Office 2003 モードで実行されている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このモードは、 [Cmfcoutlookbar:: SetMode2003](#setmode2003)を使用して有効にすることができます。

## <a name="cmfcoutlookbaronafteranimation"></a><a name="onafteranimation"></a> CMFCOutlookBar:: OnAfterAnimation

アニメーションを使用してアクティブなタブを設定した後、 [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) によって呼び出されます。

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>パラメーター

*nPage*<br/>
からアクティブになったタブページの0から始まるインデックス。

### <a name="remarks"></a>解説

[アクティブ] タブを設定した場合の視覚効果は、アニメーションを有効にしたかどうかによって異なります。 詳細については、「 [CMFCOutlookBarTabCtrl:: EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation)」を参照してください。

## <a name="cmfcoutlookbaronbeforeanimation"></a><a name="onbeforeanimation"></a> CMFCOutlookBar:: OnBeforeAnimation

アニメーションを使用してタブページがアクティブなタブとして設定される前に、 [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) によって呼び出されます。

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>パラメーター

*nPage*<br/>
からアクティブに設定されようとしているタブページの0から始まるインデックス。

### <a name="return-value"></a>戻り値

新しいアクティブなタブの設定でアニメーションを使用する場合は TRUE を返し、アニメーションを無効にする場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcoutlookbaronscroll"></a><a name="onscroll"></a> CMFCOutlookBar:: OnScroll

Outlook バーが上下にスクロールしている場合に、フレームワークによって呼び出されます。

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>パラメーター

*bDown*<br/>
からOutlook バーがスクロールしている場合は TRUE、スクロール中の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcoutlookbarremovecustompage"></a><a name="removecustompage"></a> CMFCOutlookBar:: RemoveCustomPage

カスタム Outlook バータブページを削除します。

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>パラメーター

*uiPage*<br/>
から親 Outlook ウィンドウ内のページの0から始まるインデックス。

*pTargetWnd*<br/>
から親 Outlook ウィンドウを Pointerto します。

### <a name="return-value"></a>戻り値

カスタムページが正常に削除された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

カスタムページを削除するには、この関数を呼び出します。 ページが削除されると、そのコントロール ID が使用可能な Id のプールに返されます。

削除するページが現在存在する [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md) オブジェクトへのポインターを指定する必要があります。 ユーザーは異なる Outlook バー間で切り離し可能なページを移動できますが、カスタムページに関する情報は、 [Cmfcoutlookbar:: CreateCustomPage](#createcustompage)という名前の outlook bar オブジェクトに格納されています。

Outlook ウィンドウへのポインターを取得するには、 [CBaseTabbedPane:: GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) を使用します。

## <a name="cmfcoutlookbarsetbuttonsfont"></a><a name="setbuttonsfont"></a> CMFCOutlookBar:: SetButtonsFont

Outlook バーのボタンのテキストのフォントを設定します。

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
から新しいフォントを指定します。

*より描画*<br/>
からTRUE の場合、Outlook バーは再描画されます。

### <a name="remarks"></a>解説

Outlook タブページに表示されるテキストのフォントを設定するには、このメソッドを使用します。

## <a name="cmfcoutlookbarsetmode2003"></a><a name="setmode2003"></a> CMFCOutlookBar:: SetMode2003

Outlook バーの動作が Outlook 2003 の動作を模倣するかどうかを指定します。

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>パラメーター

*bMode2003*<br/>
からTRUE の場合、Office 2003 モードが有効になります。

### <a name="remarks"></a>解説

Office 2003 モードを有効または無効にするには、この関数を使用します。 このモードでは、Outlook バーにはカスタマイズボタンを備えたツールバーが追加されています。 Outlook バーの動作は、Microsoft Office 2003 の Outlook バーの動作に準拠しています。

既定では、このモードは無効になっています。

> [!NOTE]
> この関数は、 [Cmfcoutlookbar:: Create](#create)の前に呼び出す必要があります。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)
