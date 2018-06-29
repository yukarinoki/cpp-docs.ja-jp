---
title: CPaneDivider クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7315adc855b0bfbe1cc4ffae87c416fbaa584d57
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079365"
---
# <a name="cpanedivider-class"></a>CPaneDivider クラス
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 `CPaneDivider`クラスが 2 つのペインに分割し、ペインの 2 つのグループに分割またはウィンドウ メイン フレーム ウィンドウのクライアント領域からのグループを区切るです。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaneDivider : public CBasePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneDivider::CPaneDivider](#cpanedivider)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneDivider::AddPaneContainer](#addpanecontainer)||  
|[CPaneDivider::AddPane](#addpane)||  
|[CPaneDivider::AddRecentPane](#addrecentpane)||  
|[CPaneDivider::CalcExpectedDockedRect](#calcexpecteddockedrect)||  
|[CPaneDivider::CalcFixedLayout](#calcfixedlayout)|(上書き[cbasepane::calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout))。|  
|[CPaneDivider::CheckVisibility](#checkvisibility)||  
|[CPaneDivider::CreateEx](#createex)|(上書き[cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex))。|  
|[CPaneDivider::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(上書き[cbasepane::doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore))。|  
|[CPaneDivider::DoesContainFloatingPane](#doescontainfloatingpane)||  
|[CPaneDivider::FindPaneContainer](#findpanecontainer)||  
|[CPaneDivider::FindTabbedPane](#findtabbedpane)||  
|[CPaneDivider::GetDefaultWidth](#getdefaultwidth)||  
|[CPaneDivider::GetFirstPane](#getfirstpane)||  
|[CPaneDivider::GetPaneDividerStyle](#getpanedividerstyle)||  
|[CPaneDivider::GetRootContainerRect](#getrootcontainerrect)||  
|[CPaneDivider::GetWidth](#getwidth)||  
|[CPaneDivider::Init](#init)||  
|[CPaneDivider::InsertPane](#insertpane)||  
|[CPaneDivider::IsAutoHideMode](#isautohidemode)|(上書き[CBasePane::IsAutoHideMode](../../mfc/reference/cbasepane-class.md#isautohidemode))。|  
|[CPaneDivider::IsDefault](#isdefault)||  
|[CPaneDivider::IsHorizontal](#ishorizontal)|(上書き[CBasePane::IsHorizontal](../../mfc/reference/cbasepane-class.md#ishorizontal))。|  
|[CPaneDivider::Move](#move)||  
|[CPaneDivider::NotifyAboutRelease](#notifyaboutrelease)||  
|[CPaneDivider::OnShowPane](#onshowpane)||  
|[CPaneDivider::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||  
|[CPaneDivider::RemovePane](#removepane)||  
|[CPaneDivider::ReplacePane](#replacepane)||  
|[CPaneDivider::RepositionPanes](#repositionpanes)||  
|[CPaneDivider::Serialize](#serialize)|(`CBasePane::Serialize` をオーバーライドします)。|  
|[CPaneDivider::SetAutoHideMode](#setautohidemode)||  
|[CPaneDivider::SetPaneContainerManager](#setpanecontainermanager)||  
|[CPaneDivider::ShowWindow](#showwindow)||  
|[CPaneDivider::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneDivider::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneDivider::GetPanes](#getpanes)|格納されているペインの一覧を返します、 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)です。 このメソッドは、既定ペインの区分線に対してのみ呼び出す必要があります。|  
|[CPaneDivider::GetPaneDividers](#getpanedividers)|格納されているペインの区分線の一覧を返します、 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)です。 このメソッドは、既定ペインの区分線に対してのみ呼び出す必要があります。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CPaneDivider::m_nDefaultWidth](#m_ndefaultwidth)|アプリケーションのすべてのペインの区分線のピクセル単位の既定の幅を指定します。|  
|[CPaneDivider::m_pSliderRTC](#m_psliderrtc)|ランタイム クラス情報へのポインターを保持する`CPaneDivider`-派生オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 フレームワークによって作成`CPaneDivider`ペインがドッキングされているときに自動的にオブジェクトします。  
  
 ペイン分割バーの 2 つの種類があります。  
  
-   既定ペインの区分線は、ウィンドウのグループがメイン フレーム ウィンドウの一辺にドッキングされているときに作成されます。 既定ペインの区分線へのポインターを保持する、 [CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)し、ウィンドウのグループでほとんどの操作をリダイレクト (、ウィンドウのサイズ変更や、別のドッキングなどウィンドウまたはコンテナー) のコンテナー マネージャーをします。 各ドッキング ペインでは、その既定ペインの区分線へのポインターを保持します。  
  
-   標準のペインの区分線は、コンテナー内の 2 つのペインを分割するだけです。 詳細については、次を参照してください。 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)です。  
  
## <a name="example"></a>例  
 `CWorkspaceBar` オブジェクトから `CPaneDivider` オブジェクトを取得する方法を次の例に示します。 このコード スニペットの一部である、 [MDI タブ デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPaneDivider](../../mfc/reference/cpanedivider-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxPaneDivider.h  
  
##  <a name="setautohidemode"></a>  CPaneDivider::SetAutoHideMode  

  
```  
void SetAutoHideMode(BOOL bMode);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bMode*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setpanecontainermanager"></a>  CPaneDivider::SetPaneContainerManager  

  
```  
void SetPaneContainerManager(CPaneContainerManager* p);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*p*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="addpane"></a>  CPaneDivider::AddPane  

  
```  
virtual void AddPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="addpanecontainer"></a>  CPaneDivider::AddPaneContainer  

  
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
 [in]*barContainerManager*  
 [in]*bOuterEdge*  
 [in]*pTargetBar*  
 [in]*場合*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="addrecentpane"></a>  CPaneDivider::AddRecentPane  

  
```  
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="calcexpecteddockedrect"></a>  CPaneDivider::CalcExpectedDockedRect  

  
```  
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndToDock*  
 [in]*ptMouse*  
 [in]*rectResult*  
 [in]*bDrawTab*  
 [in]*ppTargetBar*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="calcfixedlayout"></a>  CPaneDivider::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bStretch*  
 [in]*bHorz*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="checkvisibility"></a>  CPaneDivider::CheckVisibility  

  
```  
virtual BOOL CheckVisibility();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="cpanedivider"></a>  CPaneDivider::CPaneDivider  

  
```  
CPaneDivider();

 
CPaneDivider(
    BOOL bDefaultSlider,  
    CWnd* pParent = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bDefaultSlider*  
 [in]*pParent*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="createex"></a>  CPaneDivider::CreateEx  

  
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
 [in]*dwStyleEx*  
 [in]*dwStyle*  
 [in]*rect*  
 [in]*pParentWnd*  
 [in]*nID*  
 [in]*pContext*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="doesallowdyninsertbefore"></a>  CPaneDivider::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="doescontainfloatingpane"></a>  CPaneDivider::DoesContainFloatingPane  

  
```  
virtual BOOL DoesContainFloatingPane();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="findpanecontainer"></a>  CPaneDivider::FindPaneContainer  

  
```  
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,  
    BOOL& bLeftBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 [in]*bLeftBar*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="findtabbedpane"></a>  CPaneDivider::FindTabbedPane  

  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nID*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getdefaultwidth"></a>  CPaneDivider::GetDefaultWidth  

  
```  
static int __stdcall GetDefaultWidth();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getfirstpane"></a>  CPaneDivider::GetFirstPane  

  
```  
const CBasePane* GetFirstPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getpanedividers"></a>  CPaneDivider::GetPaneDividers  
 格納されているペインの区分線の一覧を返します、 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)です。 このメソッドは、既定ペインの区分線に対してのみ呼び出す必要があります。  
  
```  
void GetPaneDividers(CObList& lstSliders);
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*lstSliders*  
 ペインのコンテナーに格納されているペインの区分線の一覧が含まれています。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、既定のペイン分割バーのみを呼び出す必要があります。 既定ペインの区分線は、ウィンドウ全体のコンテナーのサイズを変更する区分線です。  
  
##  <a name="getpanedividerstyle"></a>  CPaneDivider::GetPaneDividerStyle  

  
```  
DWORD GetPaneDividerStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getpanes"></a>  CPaneDivider::GetPanes  
 格納されているペインの一覧を返します、 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)です。 既定ペインの区分線を取得する場合のみ、このメソッドを呼び出す必要があります。  
  
```  
void GetPanes(CObList& lstBars);
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*lstBars*  
 ウィンドウのコンテナーに格納されているペインの一覧が含まれています。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、既定のペイン分割バーのみを呼び出す必要があります。 既定ペインの区分線は、ウィンドウ全体のコンテナーのサイズを変更する区分線です。  
  
##  <a name="getrootcontainerrect"></a>  CPaneDivider::GetRootContainerRect  

  
```  
CRect GetRootContainerRect();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getwidth"></a>  CPaneDivider::GetWidth  

  
```  
int GetWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="init"></a>  CPaneDivider::Init  

  
```  
void Init(
    BOOL bDefaultSlider = FALSE,  
    CWnd* pParent = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bDefaultSlider*  
 [in]*pParent*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="insertpane"></a>  CPaneDivider::InsertPane  

  
```  
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,  
    CDockablePane* pTargetBar,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBarToInsert*  
 [in]*pTargetBar*  
 [in]*場合*  
 [in]*lpRect*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isautohidemode"></a>  CPaneDivider::IsAutoHideMode  

  
```  
BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isdefault"></a>  CPaneDivider::IsDefault  

  
```  
BOOL IsDefault() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ishorizontal"></a>  CPaneDivider::IsHorizontal  

  
```  
BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_ndefaultwidth"></a>  CPaneDivider::m_nDefaultWidth  
 アプリケーションのすべてのペインの区分線のピクセル単位で既定の幅を指定します。  
  
```  
AFX_IMPORT_DATA static int m_nDefaultWidth;  
```  
  
##  <a name="move"></a>  CPaneDivider::Move  

  
```  
virtual void Move(
    CPoint& ptOffset,  
    BOOL bAdjustLayout = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ptOffset*  
 [in]*bAdjustLayout*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_psliderrtc"></a>  CPaneDivider::m_pSliderRTC  
 ランタイム クラス情報へのポインターを保持する`CPaneDivider`-派生オブジェクト。  
  
```  
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;  
```  
  
### <a name="remarks"></a>Remarks  
 カスタムのウィンドウの境界線を作成する場合は、このメンバー変数を設定します。 これにより、ウィンドウが描画されると、ペイン分割バーを作成するためにフレームワークです。  
  
### <a name="example"></a>例  
 次の例は、設定する方法を示します、`m_pSliderRTC`メンバー変数。  
  
```  
class CMySplitter : public CPaneDivider  
{  
...  
};  
 
CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```  
  
##  <a name="notifyaboutrelease"></a>  CPaneDivider::NotifyAboutRelease  

  
```  
virtual void NotifyAboutRelease();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onshowpane"></a>  CPaneDivider::OnShowPane  

  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 [in]*bShow*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="releaseemptypanecontainers"></a>  CPaneDivider::ReleaseEmptyPaneContainers  

  
```  
void ReleaseEmptyPaneContainers();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="removepane"></a>  CPaneDivider::RemovePane  

  
```  
virtual void RemovePane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="replacepane"></a>  CPaneDivider::ReplacePane  

  
```  
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,  
    CDockablePane* pBarToReplaceWith);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBarToReplace*  
 [in]*pBarToReplaceWith*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="repositionpanes"></a>  CPaneDivider::RepositionPanes  

  
```  
virtual void RepositionPanes(
    CRect& rectNew,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*rectNew*  
 [in]*hdwp*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="serialize"></a>  CPaneDivider::Serialize  

  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ar*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="showwindow"></a>  CPaneDivider::ShowWindow  

  
```  
void ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nCmdShow*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="storerecentdocksiteinfo"></a>  CPaneDivider::StoreRecentDockSiteInfo  

  
```  
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="storerecenttabrelatedinfo"></a>  CPaneDivider::StoreRecentTabRelatedInfo  

  
```  
void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDockingBar*  
 [in]*pTabbedBar*  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)   
 [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md)   
 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)   
 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)
