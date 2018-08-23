---
title: CMFCAutoHideBar クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 263667b96c052025550f4d366cd236d256e7f7a8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539301"
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar クラス
`CMFCAutoHideBar` クラスは、自動非表示機能を実装している、特殊なツール バー クラスです。  

 詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。    
## <a name="syntax"></a>構文  
  
```  
class CMFCAutoHideBar : public CPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||  
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(`CPane::AllowShowOnPaneMenu` をオーバーライドします)。|  
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(上書き[cbasepane::calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout))。|  
|[CMFCAutoHideBar::Create](#create)|コントロール バーを作成し、それにアタッチします、 [CPane](../../mfc/reference/cpane-class.md)オブジェクト。 (上書き[cpane::create](../../mfc/reference/cpane-class.md#create))。|  
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||  
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。 (上書き[cpane::onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu))。|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||  
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(上書き[cpane::setactiveingroup](../../mfc/reference/cpane-class.md#setactiveingroup))。|  
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||  
|[CMFCAutoHideBar::StretchPane](#stretchpane)|垂直または水平方向にウィンドウを拡大します。 (上書き[cbasepane::stretchpane](../../mfc/reference/cbasepane-class.md#stretchpane))。|  
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||  
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|経由でユーザーがマウス カーソルを配置するときに、現時点までの時間、 [CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)から、フレームワークが関連付けられているウィンドウを示しています。|  
  
## <a name="remarks"></a>Remarks  
 ユーザーがドック ウィンドウを自動非表示モードに切り替えると、フレームワークは自動的に `CMFCAutoHideBar` オブジェクトを作成します。 また、必要な作成[CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)と[CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)オブジェクト。 各 `CAutoHideDockSite` オブジェクトは、個別の `CMFCAutoHideButton` に関連付けられます。  
  
 `CMFCAutoHideBar` クラスは、ユーザーのマウスが `CMFCAutoHideButton` の上に移動したときの `CAutoHideDockSite` の表示を実装しています。 ツール バーが WM_MOUSEMOVE メッセージを受信すると、`CMFCAutoHideBar` がタイマーを開始します。 タイマーが終了したら、ツール バーに WM_TIMER イベント通知を送信します。 ツール バーは、タイマーが開始したときにマウス ポインターが位置していた自動非表示ボタン上にまだマウス ポインターがあるかどうかをチェックして、このイベントを処理します。 ある場合は、アタッチされている `CAutoHideDockSite` が表示されます。  
  
 タイマーの遅延の長さを制御するには、`m_nShowAHWndDelay` を設定します。 既定値は 400 ミリ秒です。  
  
## <a name="example"></a>例  
 `CMFCAutoHideBar` オブジェクトを構築して、その `GetDockSiteRow` メソッドを使用する方法を、次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxautohidebar.h  
  
##  <a name="addautohidewindow"></a>  CMFCAutoHideBar::AddAutoHideWindow  
 自動的に隠す機能を `CDockablePane` ウィンドウに追加します。  
  
```  
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pAutoHideWnd*  
 隠すウィンドウ。  
  
 [in]*場合*  
 アプリケーション ウィンドウを使用して [自動的に隠す] ボタンの配置を指定する値。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
 *場合*パラメーターは、アプリケーションでは、自動的に隠す ボタンが存在する場所を示します。 このパラメーターは次のいずれかの値に設定できます。  
  
- CBRS_ALIGN_LEFT  
  
- CBRS_ALIGN_RIGHT  
  
- CBRS_ALIGN_TOP  
  
- CBRS_ALIGN_BOTTOM  
  
##  <a name="allowshowonpanemenu"></a>  CMFCAutoHideBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="calcfixedlayout"></a>  CMFCAutoHideBar::CalcFixedLayout  

  
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
  
##  <a name="cmfcautohidebar"></a>  CMFCAutoHideBar::CMFCAutoHideBar  
 CMFCAutoHideBar オブジェクトを構築します。  
  
```  
CMFCAutoHideBar();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="create"></a>  CMFCAutoHideBar::Create  

  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszClassName*  
 [in]*dwStyle*  
 [in]*rect*  
 [in]*pParentWnd*  
 [in]*nID*  
 [in]*dwControlBarStyle*  
 [in]*pContext*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getfirstahwindow"></a>  CMFCAutoHideBar::GetFirstAHWindow  
 アプリケーションの最初の自動非表示ウィンドウへのポインターを返します。  
  
```  
CDockablePane* GetFirstAHWindow();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションの最初の自動非表示ウィンドウ、または NULL (ウィンドウがない場合)。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getvisiblecount"></a>  CMFCAutoHideBar::GetVisibleCount  
 自動的に隠すボタンのうち、表示されているものの数を取得します。  
  
```  
int GetVisibleCount();
```  
  
### <a name="return-value"></a>戻り値  
 自動的に隠すボタンのうち、表示されているものの数を返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_nshowahwnddelay"></a>  CMFCAutoHideBar::m_nShowAHWndDelay  
 経由でユーザーがマウス カーソルを配置するときに、現時点までの時間、 [CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)から、フレームワークが関連付けられているウィンドウを示しています。  
  
```  
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;  
```  
  
### <a name="remarks"></a>Remarks  
 経由でユーザーがマウス カーソルを配置するときに、`CMFCAutoHideButton`フレームワークは、関連するウィンドウを表示する前に、わずかに遅延があります。 このパラメーターは、その遅延 (ミリ秒単位) の長さを決定します。  
  
##  <a name="onshowcontrolbarmenu"></a>  CMFCAutoHideBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*CPoint*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="removeautohidewindow"></a>  CMFCAutoHideBar::RemoveAutoHideWindow  
 自動的に隠すウィンドウを削除して破棄します。  
  
```  
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 CDockablePane * *pAutoHideWnd*  
 削除する自動的に隠すウィンドウ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setactiveingroup"></a>  CMFCAutoHideBar::SetActiveInGroup  
 自動的に隠すバーにアクティブというフラグを付けます。  
  
```  
virtual void SetActiveInGroup(BOOL bActive);  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]BOOL*描画*  
 アクティブに設定する場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 参照してください[cpane::setactiveingroup](../../mfc/reference/cpane-class.md#setactiveingroup)します。  
  
##  <a name="setrecentvisiblestate"></a>  CMFCAutoHideBar::SetRecentVisibleState  

  
```  
void SetRecentVisibleState(BOOL bState);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*この*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="showautohidewindow"></a>  CMFCAutoHideBar::ShowAutoHideWindow  
 自動的に隠すウィンドウを示します。  
  
```  
BOOL ShowAutoHideWindow(
        CDockablePane* pAutoHideWnd,  
        BOOL bShow,  
        BOOL bDelay);  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]CDockablePane * *pAutoHideWnd*  
 [in]BOOL *bShow*  
 ウィンドウを表示する場合は TRUE。  
  
 [in]BOOL *bDelay*  
 このパラメーターは無視されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="stretchpane"></a>  CMFCAutoHideBar::StretchPane  
 折りたたまれた状態の自動的に隠すバーを `CMFCAutoHideButton` オブジェクトに合わせてサイズ変更します。  
  
```  
virtual CSize StretchPane(
    int nLength,   
    BOOL bVert);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*されて*  
 この値は、基本実装では使用されません。 派生実装では、サイズを変更するウィンドウの長さを指定するためにこの値を使用します。  
  
 [in]*bVert*  
 この値は、基本実装では使用されません。 派生実装で、自動的に隠すバーが水平方向に折りたたまれたケースのハンドルを自動的に隠すバーが垂直方向に折りたたまれている場所の場合と FALSE の場合は true を使用します。  
  
### <a name="return-value"></a>戻り値  
 サイズを変更するウィンドウの結果のサイズ。  
  
### <a name="remarks"></a>Remarks  
 派生クラスは、このメソッドをオーバーライドして動作をカスタマイズできます。  
  
##  <a name="unsetautohidemode"></a>  CMFCAutoHideBar::UnSetAutoHideMode  
 自動的に隠すバーのグループの自動非表示モードを無効にします。  
  
```  
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)  
```  
  
### <a name="parameters"></a>パラメーター  
 [in] pFirstBarInGroup  
 グループ内で最初の自動的に隠すバーを指すポインター。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="updatevisiblestate"></a>  CMFCAutoHideBar::UpdateVisibleState  
 自動的に隠すバーを再描画する必要がある場合に、フレームワークによって呼び出されます。  
  
```  
void UpdateVisibleState();
```  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)   
 [CAutoHideDockSite クラス](../../mfc/reference/cautohidedocksite-class.md)   
 [CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)
