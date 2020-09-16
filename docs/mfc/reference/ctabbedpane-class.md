---
title: CTabbedPane クラス
ms.date: 11/04/2016
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
ms.openlocfilehash: cfc0a3099b1d5ff9bd1093cc911745bd61cde64c
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686640"
---
# <a name="ctabbedpane-class"></a>CTabbedPane クラス

切り離し可能なタブを持つペインの機能を実装します。

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CTabbedPane : public CBaseTabbedPane
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|`CTabbedPane::CTabbedPane`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[CTabbedPane::DetachPane](#detachpane)|( [CBaseTabbedPane::D etachPane](../../mfc/reference/cbasetabbedpane-class.md#detachpane)をオーバーライドします)。|
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|タブの色の自動設定を有効または無効にします。|
|[CTabbedPane::FloatTab](#floattab)|ウィンドウをフローティングしますが、ペインが現在切り離し可能なタブに存在する場合に限ります。 ( [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)をオーバーライドします)。|
|[CTabbedPane::GetTabArea](#gettabarea)|タブ付きウィンドウ内のタブ領域のサイズと位置を返します。|
|[CTabbedPane::GetTabWnd](#gettabwnd)||
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|タブ付きペインを AutoHide モードに切り替えられるかどうかを判断します。 ( [CBaseTabbedPane:: HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode)をオーバーライドします)。|
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|タブがウィンドウの下部にあるかどうかを判断します。|
|[CTabbedPane::ResetTabs](#resettabs)|すべてのタブ付きペインを既定の状態にリセットします。|
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|色の自動設定機能が有効になっているときに使用できるカスタム色の一覧を設定します。|

### <a name="data-members"></a>データ メンバー

|名前|[説明]|
|----------|-----------------|
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|アプリケーション内のタブの既定の場所。|
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|カスタムの `CMFCTabCtrl` から派生したオブジェクトに関するランタイム クラス情報。|

## <a name="remarks"></a>注釈

2 つ目のペインのキャプションをポイントして、ユーザーがあるペインを別のペインにアタッチすると、フレームワークにより自動的にこのクラスのインスタンスが作成されます。 -1 の ID を持つフレームワークにより作成される、すべてのタブ付きペイン。

Outlook スタイルのタブではなく通常のタブを指定するには、AFX_CBRS_REGULAR_TABS スタイルを [CDockablePane:: CreateEx](../../mfc/reference/cdockablepane-class.md#createex) メソッドに渡します。

切り離し可能なタブを持つタブ付きペインを作成すると、フレームワークによってペインが自動的に破棄される可能性があるため、ポインターを格納しないでください。 タブ付きペインへのポインターを取得するには、`CBasePane::GetParentTabbedPane` メソッドを呼び出します。

## <a name="examples"></a>例

この例では `CTabbedPane` オブジェクトを作成します。 次に、 [CBaseTabbedPane:: AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) を使用して追加のタブをアタッチします。

```cpp
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),
    TRUE,
    (UINT) -1,
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |
    WS_CLIPCHILDREN | CBRS_LEFT |
    CBRS_FLOAT_MULTI))
{
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create
}

pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```

タブ付きコントロールバーオブジェクトを作成するもう1つの方法は、 [CDockablePane:: AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd)を使用することです。 メソッドは、 `AttachToTabWnd` [CDockablePane:: SetTabbedPaneRTC](../../mfc/reference/cdockablepane-class.md#settabbedpanertc)によって設定されたランタイムクラス情報を使用して、タブ付きペインオブジェクトを動的に作成します。

この例では、タブ付きペインを動的に作成し、2 つのタブをアタッチし、2 番目のタブを切り離し不可能にします。

```cpp
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CTabbedPane](../../mfc/reference/ctabbedpane-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxTabbedPane

## <a name="ctabbedpanedetachpane"></a><a name="detachpane"></a> CTabbedPane::D etachPane

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

から *Pbar*<br/>

から *Bhide*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>注釈

## <a name="ctabbedpaneenabletabautocolor"></a><a name="enabletabautocolor"></a> CTabbedPane:: EnableTabAutoColor

タブの色の自動設定を有効または無効にします。

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からタブの色の自動設定を有効にする場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>注釈

この静的メソッドを使用して、アプリケーションのすべてのタブ付きペインのタブの自動色付けを有効または無効にします。 この機能を有効にすると、各タブは独自の色で塗りつぶされます。 [CMFCBaseTabCtrl:: GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors)メソッドを呼び出すことによって、タブの色を設定するために使用される色の一覧を見つけることができます。

[CTabbedPane:: SetTabAutoColors](#settabautocolors)を呼び出すことによって、タブに使用される色の一覧を指定できます。

既定では、このオプションは無効になっています。

## <a name="ctabbedpanefloattab"></a><a name="floattab"></a> CTabbedPane::FloatTab

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

から *Pbar*<br/>
から *Ntabid*<br/>
から *dockMethod*<br/>
から *Bhide*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>注釈

## <a name="ctabbedpanegettabarea"></a><a name="gettabarea"></a> CTabbedPane:: GetTabArea

タブ付きウィンドウ内のタブ領域のサイズと位置を返します。

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>パラメーター

*rectTabAreaTop*<br/>
入出力上部のタブ領域のサイズと位置を画面座標で格納します。

*rectTabAreaBottom*<br/>
入出力下部のタブ領域のサイズと位置を画面座標で格納します。

### <a name="remarks"></a>注釈

フレームワークは、ユーザーがドラッグしているペインをドッキングする方法を決定するために、このメソッドを呼び出します。 ユーザーがターゲットペインのタブ領域の上にペインをドラッグすると、フレームワークはターゲットペインの新しいタブとしてペインを追加しようとします。 それ以外の場合は、ターゲットペインの横にペインをドッキングしようとします。これには、2つのペインを分離するペインの区分線を持つ新しいペインコンテナーを作成する必要があります。

`CTabbedPane`この動作を変更するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctabbedpanegettabwnd"></a><a name="gettabwnd"></a> CTabbedPane::GetTabWnd

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>注釈

## <a name="ctabbedpanehasautohidemode"></a><a name="hasautohidemode"></a> CTabbedPane:: HasAutoHideMode

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>注釈

## <a name="ctabbedpaneistablocationbottom"></a><a name="istablocationbottom"></a> CTabbedPane:: IsTabLocationBottom

タブがウィンドウの下部にあるかどうかを判断します。

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>戻り値

タブ領域がタブ付きウィンドウの下部にある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>注釈

## <a name="ctabbedpanem_btabsalwaystop"></a><a name="m_btabsalwaystop"></a> CTabbedPane:: m_bTabsAlwaysTop

アプリケーション内のタブの既定の場所。

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>注釈

アプリケーションのすべてのタブをタブ付きペインの上部に強制的に表示するには、この静的メンバーを TRUE に設定します。

この値は、タブ付きペインが作成される前に設定する必要があります。

既定値は FALSE です。

## <a name="ctabbedpanem_ptabwndrtc"></a><a name="m_ptabwndrtc"></a> CTabbedPane:: m_pTabWndRTC

カスタムの `CMFCTabCtrl` から派生したオブジェクトに関するランタイム クラス情報。

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>注釈

`CMFCTabCtrl`タブ付きペイン内でカスタムタブ付きウィンドウを使用する場合は、この静的メンバー変数に、派生オブジェクトのランタイムクラス情報へのポインターを設定します。

## <a name="ctabbedpaneresettabs"></a><a name="resettabs"></a> CTabbedPane:: ResetTabs

すべてのタブ付きペインを既定の状態にリセットします。

```
static void ResetTabs();
```

### <a name="remarks"></a>注釈

すべてのタブ付きペインを既定の状態に戻すには、このメソッドを呼び出します。 このメソッドを呼び出すと、すべてのタブ付きペインの境界線のサイズと自動色の状態がリセットされます。

## <a name="ctabbedpanesettabautocolors"></a><a name="settabautocolors"></a> CTabbedPane:: SetTabAutoColors

自動カラー機能が有効になっている場合に使用されるカスタム色の一覧を設定します。

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>パラメーター

*arColors*<br/>
から設定する色の配列を格納します。

### <a name="remarks"></a>注釈

この方法を使用して、自動色機能が有効になっている場合に使用される色の一覧をカスタマイズします。 これは静的な関数であり、アプリケーションのすべてのタブ付きペインに影響します。

[CTabbedPane:: EnableTabAutoColor](#enabletabautocolor)を使用して、自動色機能を有効または無効にします。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)<br/>
[CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)
