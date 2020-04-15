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
ms.openlocfilehash: 17351eaed585ec34117a2ef825964fd51bd0d86b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365945"
---
# <a name="ctabbedpane-class"></a>CTabbedPane クラス

切り離し可能なタブを持つペインの機能を実装します。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CTabbedPane : public CBaseTabbedPane
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CTabbedPane::CTabbedPane`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTabbedPane::DetachPane](#detachpane)|[(CBaseTabbedPane::Dエタッハペイン](../../mfc/reference/cbasetabbedpane-class.md#detachpane)をオーバーライドします。|
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|タブの色の自動設定を有効または無効にします。|
|[CTabbedPane::FloatTab](#floattab)|ペインをフロートしますが、ペインが現在取り外し可能なタブにある場合に限ります[(CBaseTabbedPane::FloatTab.](../../mfc/reference/cbasetabbedpane-class.md#floattab)をオーバーライドします)。|
|[CTabbedPane::GetTabArea](#gettabarea)|タブ付きウィンドウ内のタブ領域のサイズと位置を返します。|
|[CTabbedPane::GetTabWnd](#gettabwnd)||
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|タブ付きペインを AutoHide モードに切り替えられるかどうかを判断します。 [(CBaseTabbedPane をオーバーライドします::HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|タブがウィンドウの下部にあるかどうかを判断します。|
|[CTabbedPane::ResetTabs](#resettabs)|すべてのタブ付きペインを既定の状態にリセットします。|
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|色の自動設定機能が有効になっているときに使用できるカスタム色の一覧を設定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|アプリケーション内のタブの既定の場所。|
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|カスタムの `CMFCTabCtrl` から派生したオブジェクトに関するランタイム クラス情報。|

## <a name="remarks"></a>解説

2 つ目のペインのキャプションをポイントして、ユーザーがあるペインを別のペインにアタッチすると、フレームワークにより自動的にこのクラスのインスタンスが作成されます。 -1 の ID を持つフレームワークにより作成される、すべてのタブ付きペイン。

Outlook スタイルのタブの代わりに通常のタブを指定するには[、cDockablePane::CreateEx](../../mfc/reference/cdockablepane-class.md#createex)メソッドにAFX_CBRS_REGULAR_TABSスタイルを渡します。

切り離し可能なタブを持つタブ付きペインを作成すると、フレームワークによってペインが自動的に破棄される可能性があるため、ポインターを格納しないでください。 タブ付きペインへのポインターを取得するには、`CBasePane::GetParentTabbedPane` メソッドを呼び出します。

## <a name="example"></a>例

この例では `CTabbedPane` オブジェクトを作成します。 次に[、CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab)を使用して追加のタブをアタッチします。

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

## <a name="example"></a>例

タブ付きコントロール バー オブジェクトを作成するもう 1 つの方法は[、CDockablePane::AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd)を使用することです。 この`AttachToTabWnd`メソッドは[、CDockablePane](../../mfc/reference/cdockablepane-class.md#settabbedpanertc)によって設定されたランタイム クラス情報を使用して、タブ付きペイン オブジェクトを動的に作成します。

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

**ヘッダー:** afxTabbedPane.h

## <a name="ctabbedpanedetachpane"></a><a name="detachpane"></a>タブ付きペイン::Dエタッハペイン

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

[in]*bHide*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="ctabbedpaneenabletabautocolor"></a><a name="enabletabautocolor"></a>タブ付きペイン::タブ自動カラーを有効にする

タブの色の自動設定を有効または無効にします。

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]タブの自動色分けを有効にする場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この静的メソッドを使用して、アプリケーション内のすべてのタブ付きペインでタブの自動色付けを有効または無効にします。 この機能が有効になっている場合、各タブは独自の色で塗りつぶされます。 タブの色付けに使用される色の一覧を見つけるには、[メソッド](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors)を呼び出します。

タブに使用する色のリストを指定するには[、CTabbedPane::SetTabAutoColors](#settabautocolors)を呼び出します。

既定では、このオプションは無効になっています。

## <a name="ctabbedpanefloattab"></a><a name="floattab"></a>タブ付きペイン::フロートタブ

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>
[in]*タブID*<br/>
[in]*ドックメソッド*<br/>
[in]*bHide*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="ctabbedpanegettabarea"></a><a name="gettabarea"></a>タブ付きペイン::ゲットタブエリア

タブ付きウィンドウのタブ領域のサイズと位置を返します。

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>パラメーター

*レクトタブエリアトップ*<br/>
[アウト]上部タブ領域のサイズと位置を画面座標で指定します。

*タブエリア下部*<br/>
[アウト]下部タブ領域のサイズと位置を画面座標で指定します。

### <a name="remarks"></a>解説

フレームワークは、ユーザーがドラッグしているペインをドッキングする方法を決定するために、このメソッドを呼び出します。 ユーザーがペインをターゲット ペインのタブ領域にドラッグすると、フレームワークはペインをターゲット ペインの新しいタブとして追加しようとします。 それ以外の場合は、ペインをターゲット ペインの側にドッキングしようとします。

この動作を変更するには`CTabbedPane`、-derived クラスでこのメソッドをオーバーライドします。

## <a name="ctabbedpanegettabwnd"></a><a name="gettabwnd"></a>タブ付きペイン::ゲットタブンド

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="ctabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>タブ付きペイン::ハズオートハイドモード

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="ctabbedpaneistablocationbottom"></a><a name="istablocationbottom"></a>タブ付きペイン::IsTabLocationボトム

タブがウィンドウの下部にあるかどうかを判断します。

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>戻り値

タブ領域がタブ付きウィンドウの下部にある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="ctabbedpanem_btabsalwaystop"></a><a name="m_btabsalwaystop"></a>タブ付きペイン::m_bTabsAlwaysTop

アプリケーション内のタブの既定の場所。

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>解説

この静的メンバーを TRUE に設定すると、アプリケーション内のすべてのタブがタブ付きペインの上部に表示されます。

タブ付きペインを作成する前に、この値を設定する必要があります。

既定値は FALSE です。

## <a name="ctabbedpanem_ptabwndrtc"></a><a name="m_ptabwndrtc"></a>タブ付きペイン::m_pTabWndRTC

カスタムの `CMFCTabCtrl` から派生したオブジェクトに関するランタイム クラス情報。

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>解説

タブ付きペイン内でカスタムタブ付きウィンドウを使用している場合`CMFCTabCtrl`は、この静的メンバー変数を-derived オブジェクトのランタイム クラス情報へのポインターに設定します。

## <a name="ctabbedpaneresettabs"></a><a name="resettabs"></a>タブ付きペイン::リセットタブ

すべてのタブ付きペインを既定の状態にリセットします。

```
static void ResetTabs();
```

### <a name="remarks"></a>解説

すべてのタブ付きペインを既定の状態に戻します。 このメソッドを呼び出すと、すべてのタブ付きペインの境界線サイズと自動色の状態がリセットされます。

## <a name="ctabbedpanesettabautocolors"></a><a name="settabautocolors"></a>タブ付きペイン::セットタブオートカラー

自動カラー機能が有効な場合に使用されるカスタムカラーのリストを設定します。

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>パラメーター

*アカラーズ*<br/>
[in]設定する色の配列を格納します。

### <a name="remarks"></a>解説

このメソッドは、自動カラー機能が有効な場合に使用される色のリストをカスタマイズするために使います。 これは静的な関数であり、アプリケーションのすべてのタブ付きペインに影響します。

[自動カラー機能を有効または無効にするには、CTabbedPane を使用します::タブオートカラーを有効](#enabletabautocolor)または無効にします。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)<br/>
[CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[クラス](../../mfc/reference/cmfcoutlookbar-class.md)
