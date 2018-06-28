---
title: CMFCOutlookBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 935728856a00a27afa1f386f493832ddb955538b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041001"
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar クラス
Microsoft Outlook 2000 または Outlook 2003 の **ナビゲーション ウィンドウ** と同じ外観を持つタブ付きペインです。 `CMFCOutlookBar`オブジェクトが含まれています、 [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)オブジェクトと一連のタブです。 タブには、いずれかを指定できる[CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)オブジェクトまたは`CWnd`-派生オブジェクト。 ユーザーに対しては、Outlook バーは一連のボタンおよび表示領域として表示されます。 ユーザーがボタンをクリックすると、対応するコントロールまたはボタン ペインが表示されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|既定のコンストラクター|  
|`CMFCOutlookBar::~CMFCOutlookBar`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|空のタブ付きペインを破棄するかどうかを指定します。 (上書き[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane))。|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|別のペインを Outlook バー ペインにドッキングできるかどうかを判断します。 (CDockablePane::CanAcceptPane をオーバーライドします)。|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|タブ付きウィンドウのキャプションがアクティブなタブとして、同じテキストを表示するかどうかを判断します。(上書き[CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname))。|  
|[CMFCOutlookBar::Create](#create)|Outlook バー コントロールを作成します。|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|カスタム Outlook バー タブを作成します。|  
|`CMFCOutlookBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|ユーザーが Outlook バーの外側のエッジにあるコントロール バーをドッキングできるかどうかを判断します。|  
|[CMFCOutlookBar::FloatTab](#floattab)|現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。(上書き[cbasetabbedpane::floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab))。|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Outlook バーのボタンのテキストのフォントを返します。|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Outlook バーのサイズとタブ領域の位置を返します。 (上書き[CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea))。|  
|`CMFCOutlookBar::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Microsoft Office Outlook 2003 (「解説」を参照してください) の Outlook バー動作を模倣するかどうかを判断します。|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|によって呼び出されます[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)アニメーションを使用してアクティブなタブに設定した後です。|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|によって呼び出されます[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)タブの前にページがアニメーションを使用してアクティブなタブとして設定します。|  
|[CMFCOutlookBar::OnScroll](#onscroll)|Outlook バーを上または下にスクロールする場合に、フレームワークによって呼び出されます。|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|カスタム Outlook バー タブを削除します。|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Outlook バーのボタンのテキストのフォントを設定します。|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Outlook バーの動作を模倣する Outlook 2003 (「解説」を参照してください) かどうかを指定します。|  
  
## <a name="remarks"></a>Remarks  
 Outlook バーの例は、次を参照してください。、 [OutlookDemo サンプル: MFC OutlookDemo アプリケーション](../../visual-cpp-samples.md)です。  
  
## <a name="implementing-the-outlook-bar"></a>Outlook バーを実装します。  
 アプリケーションで、`CMFCOutlookBar` コントロールを使用するには、次の手順に従います。  
  
1.  `CMFCOutlookBar` オブジェクトをメイン フレーム ウィンドウ クラスに埋め込みます。  
  
 ```  
    class CMainFrame : public CMDIFrameWnd  
 { ...  
    CMFCOutlookBar m_wndOutlookBar;  
    CMFCOutlookBarPane m_wndOutlookPane;  
 ... };  
 ```  
2.  メイン フレームで WM_CREATE メッセージを処理するときに呼び出す、 [CMFCOutlookBar::Create](#create) Outlook タブ コントロール バーを作成します。  
  
 ```  
    m_wndOutlookBar.Create (_T("Shortcuts"),
    this,
    CRect (0,
    0,
    100,
    100),
    ID_VIEW_OUTLOOKBAR,
    WS_CHILD | WS_VISIBLE | CBRS_LEFT);

 ```  
3.  基になるポインターを取得する`CMFCOutlookBarTabCtrl`を使用して[CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow)です。  
  
 ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();

 ```  
4.  作成、 [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)ボタンを含む各タブのオブジェクト。  
  
 ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar,
    AFX_DEFAULT_TOOLBAR_STYLE,
    ID_OUTLOOK_PANE_GENERAL,
    AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);
*// make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);
*// add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About",
    ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open",
    ID_FILE_OPEN);

 ```  
5.  呼び出す[CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)をそれぞれの新しいタブを追加します。設定、 *bDetachable*パラメーターを`FALSE`切り離し不可能なページを作成します。 または、使用して[CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol)切り離し可能なページを追加します。  
  
 ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1,
    TRUE);

 ```  
6.  追加する、 `CWnd`-派生コントロール (たとえば、 [CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md))、タブとしてコントロールを作成して呼び出し[CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) Outlook バーに追加します。  
  
> [!NOTE]
>  それぞれに一意のコントロール Id を使用する必要があります[CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)オブジェクトおよび各`CWnd`-派生オブジェクト。  
  
 使用して動的に追加または削除の実行時に新しいページ、 [CMFCOutlookBar::CreateCustomPage](#createcustompage)と[CMFCOutlookBar::RemoveCustomPage](#removecustompage)です。  
  
## <a name="outlook-2003-mode"></a>Outlook 2003 モード  
 Outlook 2003 モードでは、タブのボタンは、Outlook バー ペインの下部に配置されます。 ボタンを表示するための十分な領域がない場合、ウィンドウの下部にあるツールバーのような領域にアイコンとして表示されます。  
  
 使用して[CMFCOutlookBar::SetMode2003](#setmode2003) Outlook 2003 モードを有効にします。 使用して[CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist)を Outlook バーの下部に表示されるアイコンを含むビットマップを設定します。 ビットマップのアイコンは、タブ インデックスを使用して並べ替えられている必要があります。  
  
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
  
##  <a name="allowdestroyemptytabbedpane"></a>  CMFCOutlookBar::AllowDestroyEmptyTabbedPane  
 空のタブ付きペインを破棄するかどうかを指定します。  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は空のタブ付きウィンドウに破棄できます。それ以外の場合、`FALSE`です。 既定の実装では、常に `TRUE` を返します。  
  
### <a name="remarks"></a>Remarks  
 場合は空のタブ付きウィンドウを破棄することはできません、フレームワークを非表示に、代わりにします。  
  
##  <a name="canacceptpane"></a>  CMFCOutlookBar::CanAcceptPane  
 別のペインを Outlook バー ペインにドッキングできるかどうかを判断します。  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 このペインにドッキングされているが別のウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 別のペインを Outlook バー ペインにドッキングできる場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 Outlook バーが Outlook 2003 モードである場合は、ドッキングがサポートされないので、戻り値は`FALSE`します。  
  
 場合、 *pBar*パラメーターは`NULL`、このメソッドが戻る`FALSE`です。  
  
 それ以外の場合、このメソッドの基本メソッドとして動作[cbasepane::canacceptpane](../../mfc/reference/cbasepane-class.md#canacceptpane)ドッキングが有効でない場合でもある Outlook バーも有効にできます別の Outlook バーを上にドッキングする点を除いて、します。  
  
##  <a name="cansetcaptiontexttotabname"></a>  CMFCOutlookBar::CanSetCaptionTextToTabName  
 タブ付きウィンドウのキャプションがアクティブなタブとして、同じテキストを表示するかどうかを判断します。  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` Outlook ウィンドウのキャプション バーが自動的にアクティブなタブのテキストに設定されている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 使用して[CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname)有効またはこの機能を無効にします。  
  
 Outlook 2003 モードでは、この設定は常に有効にします。  
  
##  <a name="create"></a>  CMFCOutlookBar::Create  
 Outlook バー コントロールを作成します。  
  
```  
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
 [in]*lpszCaption*  
 ウィンドウのキャプションを指定します。  
  
 [in]*pParentWnd*  
 親ウィンドウへのポインターを指定します。 NULL は指定できません。  
  
 [in]*rect*  
 Outlook バーのサイズと位置 (ピクセル単位) を指定します。  
  
 [in]*nID*  
 コントロール ID を指定します その他のコントロール、アプリケーションで使用される Id と異なる名前にする必要があります。  
  
 [in]*dwStyle*  
 目的のコントロール バーのスタイルを指定します。 使用可能な値は、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。  
  
 [in]*dwControlBarStyle*  
 特殊なライブラリで定義されたスタイルを指定します。  
  
 [in]*pContext*  
 コンテキストを作成します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CMFCOutlookBar` 2 つのステップ内のオブジェクト。 まず、コンス トラクターを呼び出します`Create`、outlook バー コントロールを作成しにアタッチする、`CMFCOutlookBar`オブジェクト。  
  
 参照してください[cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)によって指定される使用可能なライブラリで定義されたスタイルの一覧については*dwControlBarStyle*です。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`Create`のメソッド、`CMFCOutlookBar`クラスです。 このコード スニペットの一部である、 [Outlook マルチ ビュー サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>  CMFCOutlookBar::CreateCustomPage  
 カスタム Outlook バー タブを作成します。  
  
```  
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,  
    BOOL bActivatePage=TRUE,  
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,  
    BOOL bEnableTextLabels=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszPageName*  
 ページ ラベルです。  
  
 [in]*bActivatePage*  
 場合`TRUE`ページが作成時にアクティブになります。  
  
 [in]*dwEnabledDocking*  
 ページがデタッチされると、有効なドッキング辺を指定する cbrs_align _ フラグの組み合わせ。  
  
 [in]*bEnableTextLabels*  
 場合`TRUE`ページ上に存在するボタンのテキスト ラベルを有効にします。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたページへのポインターまたは`NULL`場合は、作成に失敗しました。  
  
### <a name="remarks"></a>Remarks  
 カスタムの Outlook バー ページを作成するのにユーザーを有効にするのにには、このメソッドを使用します。 アプリケーションごとに最大 100 のページを作成することができます。 ページ コントロール Id は、一部が 0xF000 から起動します。 カスタム Outlook バー ページの合計数が 100 を超えると、作成が失敗します。  
  
 使用して[CMFCOutlookBar::RemoveCustomPage](#removecustompage)をカスタム ページを削除します。  
  
##  <a name="doesallowdyninsertbefore"></a>  CMFCOutlookBar::DoesAllowDynInsertBefore  
 ユーザーが Outlook バーの外側のエッジにあるペインをドッキングできるかどうかを指定します。  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、`FALSE` が返されます。  
  
### <a name="remarks"></a>Remarks  
 フレームワークによって、`DoesAllowDynInsertBefore`メソッド動的ペインをドッキングする場所を探すときにします。 関数を返した場合`FALSE`フレームワークは、ウィンドウの外側のエッジの動的ペインのドッキングを許可していません。  
  
 通常、静的な非フローティング コントロールとして Outlook バーを作成します。 派生クラスでは、この関数をオーバーライドして返す`TRUE`この動作を変更します。  
  
> [!NOTE]
>  動的ペインは、ドッキングするときに、ドッキングされた静的なペインの状態を確認、ために、できる限り静的ペインの後動的ペインをドッキングする必要があります。  
  
##  <a name="floattab"></a>  CMFCOutlookBar::FloatTab  
 ペインを切り離して表示します。  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 浮動小数点 ウィンドウへのポインター。  
  
 [in]*nTabID*  
 浮動小数点 タブの 0 から始まるインデックス。  
  
 [in]*dockMethod*  
 ペインをフローティングの作成に使用する方法を指定します。  詳細については、次を参照してください。 [cbasetabbedpane::floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab)です。  
  
 [in]*bHide*  
 `TRUE` フローティングする前に、ウィンドウを非表示にするにはそれ以外の場合、`FALSE`です。 このメソッドの基本クラスのバージョンとは異なりこのパラメーターに既定値はありません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ペインをフローティング状態それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 同様に、このメソッドは[cbasetabbedpane::floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab)を浮動小数点の Outlook バー コントロールの最後の残りのタブが有効にしない点が異なります。  
  
##  <a name="getbuttonsfont"></a>  CMFCOutlookBar::GetButtonsFont  
 Outlook バーのボタン タブ ページで、テキストのフォントを返します。  
  
```  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Outlook のページ ボタン タブ バーのテキストの表示に使用されるフォント オブジェクトへのポインター。  
  
### <a name="remarks"></a>Remarks  
 この関数を使用して、Outlook のページ ボタンのタブに、テキストを表示するために使用するフォントを取得します。 呼び出すことで、フォントを設定することができます[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)です。  
  
##  <a name="gettabarea"></a>  CMFCOutlookBar::GetTabArea  
 Outlook バー上のタブ領域の位置とサイズを決定します。  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*rectTabAreaTop*  
 関数が返す場合 (クライアント座標で最上位のタブ領域の位置とサイズが含まれています。  
  
 [out]*rectTabAreaBottom*  
 関数が返す場合 (クライアント座標) を下のタブ領域の位置とサイズが含まれています。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、対象のペインをドッキングの種類を確認するには、このメソッドを呼び出します。 フレームワークは、ユーザーがターゲット ウィンドウのタブ領域にドッキングするのには、ウィンドウをドラッグすることを判断した場合、対象のペインの新しいタブとして最初のウィンドウを追加しようとします。 それ以外の場合、最初のウィンドウを対象のペインの適切な辺に固定しようとします。 フレームワークは、追加のドッキング ウィンドウに対応するスライダーを新しいコンテナーを作成します。  
  
 既定の実装`GetTabArea`Outlook バーが静的; である場合は、クライアント領域全体の Outlook バーを返します、Outlook バーがフローティングことはできません。 それ以外の場合、ページのボタンが上部と Outlook バー コントロールの下部になる領域を返します。  
  
 このメソッドから派生したクラスでオーバーライド`CMFCOutlookBar`この動作を変更します。  
  
##  <a name="ismode2003"></a>  CMFCOutlookBar::IsMode2003  
 Microsoft Office Outlook 2003 の Outlook バーの動作を模倣するかどうかを指定します。  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Outlook バーが Microsoft Office 2003 モードで実行されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用してこのモードを有効にすることができます[CMFCOutlookBar::SetMode2003](#setmode2003)です。  
  
##  <a name="onafteranimation"></a>  CMFCOutlookBar::OnAfterAnimation  
 によって呼び出されます[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)アニメーションを使用してアクティブなタブに設定した後です。  
  
```  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nPage*  
 アクティブなようになっているタブ ページの 0 から始まるインデックス。  
  
### <a name="remarks"></a>Remarks  
 アクティブなタブの設定の視覚効果は、アニメーションを有効にするかどうかによって異なります。 詳細については、次を参照してください。 [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation)です。  
  
##  <a name="onbeforeanimation"></a>  CMFCOutlookBar::OnBeforeAnimation  
 によって呼び出されます[CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab)タブの前にページがアニメーションを使用してアクティブなタブとして設定します。  
  
```  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nPage*  
 アクティブな設定しようとしているタブ ページの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`アニメーションを新規のアクティブなタブの設定に使用する場合または`FALSE`アニメーションを無効にする場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onscroll"></a>  CMFCOutlookBar::OnScroll  
 Outlook バーを上または下にスクロールする場合に、フレームワークによって呼び出されます。  
  
```  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bDown*  
 `TRUE` Outlook バーをスクロールして、ダウン場合または`FALSE`をスクロールする場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="removecustompage"></a>  CMFCOutlookBar::RemoveCustomPage  
 カスタム Outlook バー タブ ページを削除します。  
  
```  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiPage*  
 親の Outlook のウィンドウ内のページの 0 から始まるインデックス。  
  
 [in]*pTargetWnd*  
 Outlook の親ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 カスタムのページが正常に削除された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 カスタム ページを削除するには、この関数を呼び出します。 ページが削除されたときにそのコントロールの ID が使用可能な Id のプールに返されます。  
  
 ポインターを指定する必要があります[CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)現在削除するページが存在するオブジェクトします。 ユーザーが別の Outlook バー間の切り離し可能なページを移動できますが、カスタム ページに関する情報が呼び出しの Outlook バー オブジェクトに存在する[CMFCOutlookBar::CreateCustomPage](#createcustompage)です。  
  
 使用して[CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) Outlook のウィンドウにポインターを取得します。  
  
##  <a name="setbuttonsfont"></a>  CMFCOutlookBar::SetButtonsFont  
 Outlook バーのボタンのテキストのフォントを設定します。  
  
```  
void SetButtonsFont(
    CFont* pFont,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pFont*  
 新しいフォントを指定します。  
  
 [in]*bRedraw*  
 場合`TRUE`、Outlook バーが再描画されます。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用すると、outlook のタブ ページのボタンに表示されるテキストのフォントを設定できます。  
  
##  <a name="setmode2003"></a>  CMFCOutlookBar::SetMode2003  
 Outlook 2003 の Outlook バーの動作を模倣するかどうかを指定します。  
  
```  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bMode2003*  
 TRUE の場合、Office 2003 モードを有効にします。  
  
### <a name="remarks"></a>Remarks  
 有効にするにまたは、Office 2003 モードを無効にするには、この関数を使用します。 このモードでは、Outlook バーは、カスタム ボタンを含む追加のツールバーがします。 Outlook バーの動作は、Microsoft Office 2003 Outlook バーの動作に準拠しています。  
  
 既定では、このモードは無効です。  
  
> [!NOTE]
>  この関数は、前に呼び出す必要があります[CMFCOutlookBar::Create](#create)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)
