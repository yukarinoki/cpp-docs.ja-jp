---
title: Cペインディバイダークラス
ms.date: 11/04/2016
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
helpviewer_keywords:
- CPaneDivider [MFC], CPaneDivider
- CPaneDivider [MFC], AddPaneContainer
- CPaneDivider [MFC], AddPane
- CPaneDivider [MFC], AddRecentPane
- CPaneDivider [MFC], CalcExpectedDockedRect
- CPaneDivider [MFC], CalcFixedLayout
- CPaneDivider [MFC], CheckVisibility
- CPaneDivider [MFC], CreateEx
- CPaneDivider [MFC], DoesAllowDynInsertBefore
- CPaneDivider [MFC], DoesContainFloatingPane
- CPaneDivider [MFC], FindPaneContainer
- CPaneDivider [MFC], FindTabbedPane
- CPaneDivider [MFC], GetDefaultWidth
- CPaneDivider [MFC], GetFirstPane
- CPaneDivider [MFC], GetPaneDividerStyle
- CPaneDivider [MFC], GetRootContainerRect
- CPaneDivider [MFC], GetWidth
- CPaneDivider [MFC], Init
- CPaneDivider [MFC], InsertPane
- CPaneDivider [MFC], IsAutoHideMode
- CPaneDivider [MFC], IsDefault
- CPaneDivider [MFC], IsHorizontal
- CPaneDivider [MFC], Move
- CPaneDivider [MFC], NotifyAboutRelease
- CPaneDivider [MFC], OnShowPane
- CPaneDivider [MFC], ReleaseEmptyPaneContainers
- CPaneDivider [MFC], RemovePane
- CPaneDivider [MFC], ReplacePane
- CPaneDivider [MFC], RepositionPanes
- CPaneDivider [MFC], Serialize
- CPaneDivider [MFC], SetAutoHideMode
- CPaneDivider [MFC], SetPaneContainerManager
- CPaneDivider [MFC], ShowWindow
- CPaneDivider [MFC], StoreRecentDockSiteInfo
- CPaneDivider [MFC], StoreRecentTabRelatedInfo
- CPaneDivider [MFC], GetPanes
- CPaneDivider [MFC], GetPaneDividers
- CPaneDivider [MFC], m_nDefaultWidth
- CPaneDivider [MFC], m_pSliderRTC
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
ms.openlocfilehash: 41fa3204712749a3b1123a20d31b01ba8b5fbaa4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364115"
---
# <a name="cpanedivider-class"></a>Cペインディバイダークラス

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

この`CPaneDivider`クラスは、2 つのペインを分割したり、ペインのグループを 2 つ分割したり、ペインのグループをメイン フレーム ウィンドウのクライアント領域から分離したりします。

## <a name="syntax"></a>構文

```
class CPaneDivider : public CBasePane
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cペインディバイダー::Cペインディバイダー](#cpanedivider)||

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cペインディバイダー::ペインコンテナの追加](#addpanecontainer)||
|[Cペインディバイダー::ペインの追加](#addpane)||
|[Cペインディバイダー::最近のペインを追加](#addrecentpane)||
|[CPane ディバイダー::カルク予期しないドッキングレクト](#calcexpecteddockedrect)||
|[CPane ディバイダー::計算固定レイアウト](#calcfixedlayout)|(CBase ペインをオーバーライド[します::計算固定レイアウト](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CPaneディバイダー::チェックビジビリティ](#checkvisibility)||
|[Cペインディバイダー::作成します。](#createex)|(CBasePane をオーバーライド[します。::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|
|[前に挿入:D](#doesallowdyninsertbefore)|[(CBase ペインをオーバーライドします::DoesAllowDynInsert前に](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[Cパネディバイダー::Doesフローティングペインを含む](#doescontainfloatingpane)||
|[Cペインディバイダー::ペインコンテナを検索](#findpanecontainer)||
|[Cペインディバイダー::タブベッドペインを見つける](#findtabbedpane)||
|[クパネディバイダー::取得既定の幅](#getdefaultwidth)||
|[Cパネディバイダー::ゲットファーストペイン](#getfirstpane)||
|[クパネディバイダー::ゲパディバースタイル](#getpanedividerstyle)||
|[クネパディバイダー::ゲットルートコンテナレクト](#getrootcontainerrect)||
|[クパネディバイダー::取得幅](#getwidth)||
|[CPaneディバイダー::イニト](#init)||
|[Cペインディバイダー::ペインの挿入](#insertpane)||
|[CPane ディバイダー::IsAutoHideMode](#isautohidemode)|(CBase ペインをオーバーライド[します::IsAutoHideMode](../../mfc/reference/cbasepane-class.md#isautohidemode).)|
|[CPane ディバイダー::IsDefault](#isdefault)||
|[CPane ディバイダー::イス水平](#ishorizontal)|[(CBasePane をオーバーライドします::IsHorizontal](../../mfc/reference/cbasepane-class.md#ishorizontal).)|
|[CPaneディバイダー::移動](#move)||
|[CPane ディバイダー::リリースについて通知](#notifyaboutrelease)||
|[Cペインディバイダー::オンショーペイン](#onshowpane)||
|[Cペインディバイダー::リリース空のペインコンテナ](#releaseemptypanecontainers)||
|[Cペインディバイダー::ウィンドウの削除](#removepane)||
|[Cペインディバイダー::交換ペイン](#replacepane)||
|[CPane ディバイダー::ペインの位置変更](#repositionpanes)||
|[CPaneディバイダー::シリアライズ](#serialize)|( `CBasePane::Serialize`をオーバーライドします)。|
|[CPane ディバイダー::セットオートハイドモード](#setautohidemode)||
|[Cペインディバイダー::セットペインコンテナマネージャー](#setpanecontainermanager)||
|[Cペインディバイダー::ショーウィンドウ](#showwindow)||
|[クネパディバイダー::ストア最近ドックサイト情報](#storerecentdocksiteinfo)||
|[CPane ディバイダー::ストア最近タブ関連情報](#storerecenttabrelatedinfo)||

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cペインディバイダー::ゲパネ](#getpanes)|[CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)に存在するペインの一覧を返します。 このメソッドは、既定のペイン区分線に対してのみ呼び出す必要があります。|
|[CPane ディバイダー::ゲパネディバイダー](#getpanedividers)|[CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)に存在するペイン区分線の一覧を返します。 このメソッドは、既定のペイン区分線に対してのみ呼び出す必要があります。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[Cペインディバイダー::m_nDefaultWidth](#m_ndefaultwidth)|アプリケーション内のすべてのペイン分割線の既定の幅をピクセル単位で指定します。|
|[Cペインディバイダー::m_pSliderRTC](#m_psliderrtc)|派生オブジェクトに関するランタイム クラス情報への`CPaneDivider`ポインターを保持します。|

## <a name="remarks"></a>解説

フレームワークは、`CPaneDivider`ペインがドッキングされると自動的にオブジェクトを作成します。

ペイン区切りには、次の 2 種類があります。

- ペインのグループがメイン フレーム ウィンドウの側面にドッキングされると、既定のペイン分割線が作成されます。 既定のペイン区分線は[、CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)へのポインターを保持し、ペインのグループに対するほとんどの操作 (ペインのサイズ変更、別のペインまたはコンテナーのドッキングなど) をコンテナー マネージャーにリダイレクトします。 各ドッキング ペインは、既定のペイン分割線へのポインターを保持します。

- 通常のペイン分割は、コンテナー内の 2 つのペインを分割するだけです。 詳細については[、「CPane コンテナ クラス」を](../../mfc/reference/cpanecontainer-class.md)参照してください。

## <a name="example"></a>例

`CWorkspaceBar` オブジェクトから `CPaneDivider` オブジェクトを取得する方法を次の例に示します。 このコード スニペットは[、MDI タブデモサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[Cobject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdターゲット](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cペインディバイダ](../../mfc/reference/cpanedivider-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxPane ディバイダー.h

## <a name="cpanedividersetautohidemode"></a><a name="setautohidemode"></a>CPane ディバイダー::セットオートハイドモード

```
void SetAutoHideMode(BOOL bMode);
```

### <a name="parameters"></a>パラメーター

[in]*bモード*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividersetpanecontainermanager"></a><a name="setpanecontainermanager"></a>Cペインディバイダー::セットペインコンテナマネージャー

```
void SetPaneContainerManager(CPaneContainerManager* p);
```

### <a name="parameters"></a>パラメーター

[in]*p*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedivideraddpane"></a><a name="addpane"></a>Cペインディバイダー::ペインの追加

```
virtual void AddPane(CDockablePane* pBar);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedivideraddpanecontainer"></a><a name="addpanecontainer"></a>Cペインディバイダー::ペインコンテナの追加

```
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,
    BOOL bOuterEdge);

virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,
    CPaneContainerManager& barContainerManager,
    DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

[in]*バーコンテナマネージャー*<br/>
[in]*ボターエッジ*<br/>
[in]*をクリックします。*<br/>
[in]*dw配置*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedivideraddrecentpane"></a><a name="addrecentpane"></a>Cペインディバイダー::最近のペインを追加

```
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CPane ディバイダー::カルク予期しないドッキングレクト

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>パラメーター

[in]*ドック*<br/>
[in]*ptマウス*<br/>
[in]*レクト結果*<br/>
[in]*タブを描く*<br/>
[in]*ターゲットバー*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividercalcfixedlayout"></a><a name="calcfixedlayout"></a>CPane ディバイダー::計算固定レイアウト

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

[in]*bストレッチ*<br/>
[in]*bHorz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividercheckvisibility"></a><a name="checkvisibility"></a>CPaneディバイダー::チェックビジビリティ

```
virtual BOOL CheckVisibility();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividercpanedivider"></a><a name="cpanedivider"></a>Cペインディバイダー::Cペインディバイダー

```
CPaneDivider();

CPaneDivider(
    BOOL bDefaultSlider,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*ビデフォルトスライダー*<br/>
[in]*親*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividercreateex"></a><a name="createex"></a>Cペインディバイダー::作成します。

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext);
```

### <a name="parameters"></a>パラメーター

[in]*ドウスタイルエックス*<br/>
[in]*ドウスタイル*<br/>
[in]*レクト*<br/>
[in]*親子*<br/>
[in]*nID*<br/>
[in]*コンテキスト*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerdoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>前に挿入:D

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerdoescontainfloatingpane"></a><a name="doescontainfloatingpane"></a>Cパネディバイダー::Doesフローティングペインを含む

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerfindpanecontainer"></a><a name="findpanecontainer"></a>Cペインディバイダー::ペインコンテナを検索

```
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>
[in]*バー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerfindtabbedpane"></a><a name="findtabbedpane"></a>Cペインディバイダー::タブベッドペインを見つける

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>パラメーター

[in]*nID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividergetdefaultwidth"></a><a name="getdefaultwidth"></a>クパネディバイダー::取得既定の幅

```
static int __stdcall GetDefaultWidth();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividergetfirstpane"></a><a name="getfirstpane"></a>Cパネディバイダー::ゲットファーストペイン

```
const CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividergetpanedividers"></a><a name="getpanedividers"></a>CPane ディバイダー::ゲパネディバイダー

[CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)に存在するペイン区分線の一覧を返します。 このメソッドは、既定のペイン区分線に対してのみ呼び出す必要があります。

```
void GetPaneDividers(CObList& lstSliders);
```

### <a name="parameters"></a>パラメーター

*lstスライダー*<br/>
[アウト]ペイン コンテナーに存在するペイン区分線の一覧が含まれています。

### <a name="remarks"></a>解説

このメソッドは、既定のペイン区分線に対してのみ呼び出す必要があります。 既定のペイン区分線は、ペイン コンテナー全体のサイズを変更する区分線です。

## <a name="cpanedividergetpanedividerstyle"></a><a name="getpanedividerstyle"></a>クパネディバイダー::ゲパディバースタイル

```
DWORD GetPaneDividerStyle() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividergetpanes"></a><a name="getpanes"></a>Cペインディバイダー::ゲパネ

[CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)に存在するペインの一覧を返します。 このメソッドは、既定のペインの区分線を取得するためだけに呼び出す必要があります。

```
void GetPanes(CObList& lstBars);
```

### <a name="parameters"></a>パラメーター

*lstバー*<br/>
[アウト]ペイン コンテナーに存在するペインの一覧が含まれています。

### <a name="remarks"></a>解説

このメソッドは、既定のペイン区分線に対してのみ呼び出す必要があります。 既定のペイン区分線は、ペイン コンテナー全体のサイズを変更する区分線です。

## <a name="cpanedividergetrootcontainerrect"></a><a name="getrootcontainerrect"></a>クネパディバイダー::ゲットルートコンテナレクト

```
CRect GetRootContainerRect();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividergetwidth"></a><a name="getwidth"></a>クパネディバイダー::取得幅

```
int GetWidth() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerinit"></a><a name="init"></a>CPaneディバイダー::イニト

```
void Init(
    BOOL bDefaultSlider = FALSE,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*ビデフォルトスライダー*<br/>
[in]*親*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividerinsertpane"></a><a name="insertpane"></a>Cペインディバイダー::ペインの挿入

```
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,
    CDockablePane* pTargetBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*挿入する*<br/>
[in]*をクリックします。*<br/>
[in]*dw配置*<br/>
[in]*lpRect*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerisautohidemode"></a><a name="isautohidemode"></a>CPane ディバイダー::IsAutoHideMode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerisdefault"></a><a name="isdefault"></a>CPane ディバイダー::IsDefault

```
BOOL IsDefault() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerishorizontal"></a><a name="ishorizontal"></a>CPane ディバイダー::イス水平

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerm_ndefaultwidth"></a><a name="m_ndefaultwidth"></a>Cペインディバイダー::m_nDefaultWidth

アプリケーション内のすべてのペイン分割線の既定の幅をピクセル単位で指定します。

```
AFX_IMPORT_DATA static int m_nDefaultWidth;
```

## <a name="cpanedividermove"></a><a name="move"></a>CPaneディバイダー::移動

```
virtual void Move(
    CPoint& ptOffset,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*ptオフセット*<br/>
[in]*レイアウトを調整する*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividerm_psliderrtc"></a><a name="m_psliderrtc"></a>Cペインディバイダー::m_pSliderRTC

派生オブジェクトに関するランタイム クラス情報`CPaneDivider`へのポインターを保持します。

```
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;
```

### <a name="remarks"></a>解説

カスタム ペインの区分線を作成する場合は、このメンバー変数を設定します。 これにより、ペインが描画されるときに、フレームワークでペインの区分線を作成できます。

### <a name="example"></a>例

次の例は、メンバー変数を`m_pSliderRTC`設定する方法を示しています。

```
class CMySplitter : public CPaneDivider
{
...
};

CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```

## <a name="cpanedividernotifyaboutrelease"></a><a name="notifyaboutrelease"></a>CPane ディバイダー::リリースについて通知

```
virtual void NotifyAboutRelease();
```

### <a name="remarks"></a>解説

## <a name="cpanedivideronshowpane"></a><a name="onshowpane"></a>Cペインディバイダー::オンショーペイン

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>
[in]*bショー*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>Cペインディバイダー::リリース空のペインコンテナ

```
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>解説

## <a name="cpanedividerremovepane"></a><a name="removepane"></a>Cペインディバイダー::ウィンドウの削除

```
virtual void RemovePane(CDockablePane* pBar);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividerreplacepane"></a><a name="replacepane"></a>Cペインディバイダー::交換ペイン

```
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,
    CDockablePane* pBarToReplaceWith);
```

### <a name="parameters"></a>パラメーター

[in]*置き換える*<br/>
[in]*置き換える*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpanedividerrepositionpanes"></a><a name="repositionpanes"></a>CPane ディバイダー::ペインの位置変更

```
virtual void RepositionPanes(
    CRect& rectNew,
    HDWP& hdwp);
```

### <a name="parameters"></a>パラメーター

[in]*レクト新しい*<br/>
[in]*hdwp*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividerserialize"></a><a name="serialize"></a>CPaneディバイダー::シリアライズ

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

[in]*ar*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividershowwindow"></a><a name="showwindow"></a>Cペインディバイダー::ショーウィンドウ

```
void ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividerstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>クネパディバイダー::ストア最近ドックサイト情報

```
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

### <a name="remarks"></a>解説

## <a name="cpanedividerstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>CPane ディバイダー::ストア最近タブ関連情報

```
void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,
    CDockablePane* pTabbedBar);
```

### <a name="parameters"></a>パラメーター

[in]*pドッキングバー*<br/>
[in]*pタブ付きバー*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)<br/>
[CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)<br/>
[CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)<br/>
[Cベースウィンドウクラス](../../mfc/reference/cbasepane-class.md)
