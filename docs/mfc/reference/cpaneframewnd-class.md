---
title: CPaneFrameWnd クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd::AddPane
- AFXPANEFRAMEWND/CPaneFrameWnd::AddRemovePaneFromGlobalList
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustPaneFrames
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcBorderSize
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcExpectedDockedRect
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeAttached
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeDockedToPane
- AFXPANEFRAMEWND/CPaneFrameWnd::CheckGripperVisibility
- AFXPANEFRAMEWND/CPaneFrameWnd::ConvertToTabbedDocument
- AFXPANEFRAMEWND/CPaneFrameWnd::Create
- AFXPANEFRAMEWND/CPaneFrameWnd::CreateEx
- AFXPANEFRAMEWND/CPaneFrameWnd::DockPane
- AFXPANEFRAMEWND/CPaneFrameWnd::FindFloatingPaneByID
- AFXPANEFRAMEWND/CPaneFrameWnd::FrameFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionHeight
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionText
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingMode
- AFXPANEFRAMEWND/CPaneFrameWnd::GetFirstVisiblePane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::GetParent
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPinState
- AFXPANEFRAMEWND/CPaneFrameWnd::GetRecentFloatingRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetVisiblePaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::HitTest
- AFXPANEFRAMEWND/CPaneFrameWnd::IsCaptured
- AFXPANEFRAMEWND/CPaneFrameWnd::IsDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollDown
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollUp
- AFXPANEFRAMEWND/CPaneFrameWnd::KillDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::LoadState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnBeforeDock
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDockToRecentPos
- AFXPANEFRAMEWND/CPaneFrameWnd::OnKillRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnMovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::OnPaneRecalcLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::OnSetRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnShowPane
- AFXPANEFRAMEWND/CPaneFrameWnd::PaneFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::Pin
- AFXPANEFRAMEWND/CPaneFrameWnd::RedrawAll
- AFXPANEFRAMEWND/CPaneFrameWnd::RemoveNonValidPanes
- AFXPANEFRAMEWND/CPaneFrameWnd::RemovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::ReplacePane
- AFXPANEFRAMEWND/CPaneFrameWnd::SaveState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetCaptionButtons
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::SetPreDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SizeToContent
- AFXPANEFRAMEWND/CPaneFrameWnd::StartTearOff
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentDockSiteInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentTabRelatedInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::OnCheckRollState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDrawBorder
- AFXPANEFRAMEWND/CPaneFrameWnd::m_bUseSaveBits
dev_langs:
- C++
helpviewer_keywords:
- CPaneFrameWnd [MFC], AddPane
- CPaneFrameWnd [MFC], AddRemovePaneFromGlobalList
- CPaneFrameWnd [MFC], AdjustLayout
- CPaneFrameWnd [MFC], AdjustPaneFrames
- CPaneFrameWnd [MFC], CalcBorderSize
- CPaneFrameWnd [MFC], CalcExpectedDockedRect
- CPaneFrameWnd [MFC], CanBeAttached
- CPaneFrameWnd [MFC], CanBeDockedToPane
- CPaneFrameWnd [MFC], CheckGripperVisibility
- CPaneFrameWnd [MFC], ConvertToTabbedDocument
- CPaneFrameWnd [MFC], Create
- CPaneFrameWnd [MFC], CreateEx
- CPaneFrameWnd [MFC], DockPane
- CPaneFrameWnd [MFC], FindFloatingPaneByID
- CPaneFrameWnd [MFC], FrameFromPoint
- CPaneFrameWnd [MFC], GetCaptionHeight
- CPaneFrameWnd [MFC], GetCaptionRect
- CPaneFrameWnd [MFC], GetCaptionText
- CPaneFrameWnd [MFC], GetDockingManager
- CPaneFrameWnd [MFC], GetDockingMode
- CPaneFrameWnd [MFC], GetFirstVisiblePane
- CPaneFrameWnd [MFC], GetHotPoint
- CPaneFrameWnd [MFC], GetPane
- CPaneFrameWnd [MFC], GetPaneCount
- CPaneFrameWnd [MFC], GetParent
- CPaneFrameWnd [MFC], GetPinState
- CPaneFrameWnd [MFC], GetRecentFloatingRect
- CPaneFrameWnd [MFC], GetVisiblePaneCount
- CPaneFrameWnd [MFC], HitTest
- CPaneFrameWnd [MFC], IsCaptured
- CPaneFrameWnd [MFC], IsDelayShow
- CPaneFrameWnd [MFC], IsRollDown
- CPaneFrameWnd [MFC], IsRollUp
- CPaneFrameWnd [MFC], KillDockingTimer
- CPaneFrameWnd [MFC], LoadState
- CPaneFrameWnd [MFC], OnBeforeDock
- CPaneFrameWnd [MFC], OnDockToRecentPos
- CPaneFrameWnd [MFC], OnKillRollUpTimer
- CPaneFrameWnd [MFC], OnMovePane
- CPaneFrameWnd [MFC], OnPaneRecalcLayout
- CPaneFrameWnd [MFC], OnSetRollUpTimer
- CPaneFrameWnd [MFC], OnShowPane
- CPaneFrameWnd [MFC], PaneFromPoint
- CPaneFrameWnd [MFC], Pin
- CPaneFrameWnd [MFC], RedrawAll
- CPaneFrameWnd [MFC], RemoveNonValidPanes
- CPaneFrameWnd [MFC], RemovePane
- CPaneFrameWnd [MFC], ReplacePane
- CPaneFrameWnd [MFC], SaveState
- CPaneFrameWnd [MFC], SetCaptionButtons
- CPaneFrameWnd [MFC], SetDelayShow
- CPaneFrameWnd [MFC], SetDockingManager
- CPaneFrameWnd [MFC], SetDockingTimer
- CPaneFrameWnd [MFC], SetDockState
- CPaneFrameWnd [MFC], SetHotPoint
- CPaneFrameWnd [MFC], SetPreDockState
- CPaneFrameWnd [MFC], SizeToContent
- CPaneFrameWnd [MFC], StartTearOff
- CPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
- CPaneFrameWnd [MFC], OnCheckRollState
- CPaneFrameWnd [MFC], OnDrawBorder
- CPaneFrameWnd [MFC], m_bUseSaveBits
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcc4ec99ea8dc7dfc0706237e274b6b96f437829
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214992"
---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd クラス
詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。  
  
 1 つのペインを含むミニフレーム ウィンドウを実装します。 そのペインは、ウィンドウのクライアント領域になります。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneFrameWnd::AddPane](#addpane)|ペインを追加します。|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|グローバル リストに対してペインを追加または削除します。|  
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|ミニフレーム ウィンドウのレイアウトを調整します。|  
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||  
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|ミニフレーム ウィンドウの境界線のサイズを計算します。|  
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|ドッキング ウィンドウの予想される四角形を計算します。|  
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|現在のペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを判定します。|  
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|ミニフレーム ウィンドウをペインにドッキングできるかどうかを判定します。|  
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|ペインをタブ付きドキュメントに変換します。|  
|[CPaneFrameWnd::Create](#create)|ミニフレーム ウィンドウを作成し、`CPaneFrameWnd` オブジェクトにアタッチします。|  
|[CPaneFrameWnd::CreateEx](#createex)|ミニフレーム ウィンドウを作成し、`CPaneFrameWnd` オブジェクトにアタッチします。|  
|[CPaneFrameWnd::DockPane](#dockpane)|ペインをドッキングします。|  
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|フローティング ペインのグローバル リストで、指定したコントロール ID のペインを検索します。|  
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|ユーザーが指定したポイントを含むミニフレーム ウィンドウを検索します。|  
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|ミニフレーム ウィンドウのキャプションの高さを返します。|  
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|ミニフレーム ウィンドウのキャプションに外接する四角形を計算します。|  
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|キャプション テキストを返します。|  
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||  
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|ドッキングのモードを返します。|  
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|ミニフレーム ウィンドウに含まれる最初の可視ペインを返します。|  
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||  
|[CPaneFrameWnd::GetPane](#getpane)|ミニフレーム ウィンドウに含まれるペインを返します。|  
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|ミニフレーム ウィンドウに含まれるペインの数を返します。|  
|[CPaneFrameWnd::GetParent](#getparent)||  
|[CPaneFrameWnd::GetPinState](#getpinstate)||  
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||  
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|ミニフレーム ウィンドウに含まれる可視ペインの数を返します。|  
|[CPaneFrameWnd::HitTest](#hittest)|特定のポイントに、ミニフレーム ウィンドウのどの部分があるか判定します。|  
|[CPaneFrameWnd::IsCaptured](#iscaptured)||  
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||  
|[CPaneFrameWnd::IsRollDown](#isrolldown)|ミニフレーム ウィンドウをロール ダウンするかどうかを判断します。|  
|[CPaneFrameWnd::IsRollUp](#isrollup)|ミニフレーム ウィンドウをロール アップするかどうかを判断します。|  
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|ドッキング タイマーを停止します。|  
|[CPaneFrameWnd::LoadState](#loadstate)|レジストリからペインの状態を読み込みます。|  
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|ドッキングが可能かどうかを判定します。|  
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|ミニフレーム ウィンドウを直前の位置にドッキングします。|  
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|ロールアップ タイマーを停止します。|  
|[CPaneFrameWnd::OnMovePane](#onmovepane)|ミニフレーム ウィンドウを指定したオフセットだけ移動します。|  
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|含まれているペインのレイアウトを調整します。|  
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|ロールアップ タイマーを設定します。|  
|[CPaneFrameWnd::OnShowPane](#onshowpane)|ミニフレーム ウィンドウ内のペインが非表示になるとき、または表示されるときに、フレームワークによって呼び出されます。|  
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|ユーザーが指定した位置がミニフレーム ウィンドウ内のペインに含まれている場合、そのペインを返します。|  
|[CPaneFrameWnd::Pin](#pin)||  
|`CPaneFrameWnd::PreTranslateMessage`|クラスによって使用される[CWinApp](../../mfc/reference/cwinapp-class.md)にディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](https://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数。|  
|[CPaneFrameWnd::RedrawAll](#redrawall)|すべてのミニフレーム ウィンドウを再描画します。|  
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|有効でないウィンドウを削除するために、フレームワークによって呼び出されます。|  
|[CPaneFrameWnd::RemovePane](#removepane)|ミニフレーム ウィンドウから、ペインを削除します。|  
|[CPaneFrameWnd::ReplacePane](#replacepane)|ペインを別のペインに置き換えます。|  
|[CPaneFrameWnd::SaveState](#savestate)|レジストリにペインの状態を保存します。|  
|`CPaneFrameWnd::Serialize`|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。|  
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|キャプションのボタンを設定します。|  
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||  
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||  
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|ドッキング タイマーを設定します。|  
|[CPaneFrameWnd::SetDockState](#setdockstate)|ドッキング状態を設定します。|  
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||  
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|ドッキング前の状態を設定するために、フレームワークによって呼び出されます。|  
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|含まれているペインとサイズを同じにするために、ミニフレーム ウィンドウのサイズを調整します。|  
|[CPaneFrameWnd::StartTearOff](#starttearoff)|メニューをティアオフします。|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|ミニフレーム ウィンドウをロール アップまたはロール ダウンするかどうかを判断します。|  
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|ミニフレーム ウィンドウの境界線を描画します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|CS_SAVEBITS クラスのスタイルを使用して、ウィンドウ クラスを登録するかどうかを指定します。|  
  
## <a name="remarks"></a>Remarks  
 ペインがドッキング状態からフローティング状態に切り替わるときに、フレームワークは自動的に `CPaneFrameWnd` オブジェクトを作成します。  
  
 ミニフレーム ウィンドウは内容を表示した状態でドラッグ (直接ドッキング) するか、ドラッグ四角形を使用してドラッグ (標準ドッキング) することができます。 ミニフレームのコンテナー ペインのドッキング モードにより、ミニフレームのドラッグ動作が決まります。 詳細については、次を参照してください。 [cbasepane::getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode)します。  
  
 ミニフレーム ウィンドウには、含まれているペインのスタイルに従って、キャプションのボタンが表示されます。 場合は、ウィンドウを閉じることができます ( [cbasepane::canbeclosed](../../mfc/reference/cbasepane-class.md#canbeclosed))、[閉じる] ボタンが表示されます。 ウィンドウが AFX_CBRS_AUTO_ROLLUP スタイルは、pin が表示されます。  
  
 `CPaneFrameWnd` からクラスを派生させる場合は、フレームワークで作成方法を定義する必要があります。 オーバーライドすることで、クラスを作成するか[cpane::createdefaultminiframe](../../mfc/reference/cpane-class.md#createdefaultminiframe)、設定や、`CPane::m_pMiniFrameRTC`メンバーことが、クラスのランタイム クラス情報を指すようにします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPaneFrameWnd`   
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxPaneFrameWnd.h  
  
##  <a name="addpane"></a>  CPaneFrameWnd::AddPane  
 ペインを追加します。  
  
```  
virtual void AddPane(CBasePane* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*我が物*  
 追加するウィンドウ。  
  
##  <a name="addremovepanefromgloballist"></a>  CPaneFrameWnd::AddRemovePaneFromGlobalList  
 グローバル リストに対してペインを追加または削除します。  
  
```  
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,  
    BOOL bAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*我が物*  
 追加または削除するウィンドウ。  
  
 [in]*bAdd*  
 0 以外の場合は、ウィンドウを追加します。 0 の場合は、ウィンドウを削除します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、0 以外の場合それ以外の場合 0 を返します。  
  
##  <a name="adjustlayout"></a>  CPaneFrameWnd::AdjustLayout  
 ミニフレーム ウィンドウのレイアウトを調整します。  
  
```  
virtual void AdjustLayout();
```  
  
##  <a name="adjustpaneframes"></a>  CPaneFrameWnd::AdjustPaneFrames  

  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="calcbordersize"></a>  CPaneFrameWnd::CalcBorderSize  
 ミニフレーム ウィンドウの境界線のサイズを計算します。  
  
```  
virtual void CalcBorderSize(CRect& rectBorderSize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*rectBorderSize*  
 ミニフレーム ウィンドウの枠線のピクセル単位でサイズを格納します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ミニフレーム ウィンドウの境界線のサイズを計算するためにフレームワークによって呼び出されます。 ミニフレーム ウィンドウのツールバーにあるかどうか、返されるサイズによって異なります[CDockablePane](../../mfc/reference/cdockablepane-class.md)します。  
  
##  <a name="calcexpecteddockedrect"></a>  CPaneFrameWnd::CalcExpectedDockedRect  
 ドッキング ウィンドウの予想される四角形を計算します。  
  
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
 ドッキングするウィンドウへのポインター。  
  
 [in]*ptMouse*  
 マウスの位置。  
  
 [out]*rectResult*  
 計算される四角形。  
  
 [out]*bDrawTab*  
 TRUE の場合は、タブを描画します。FALSE の場合は、タブを描画できません。  
  
 [out]*ppTargetBar*  
 [ターゲット] ウィンドウへのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ウィンドウがユーザーによって指定されたポイントに、ウィンドウをドラッグした場合に使用される四角形を計算*ptMouse*し、そこにドッキングします。  
  
##  <a name="canbeattached"></a>  CPaneFrameWnd::CanBeAttached  
 現在のペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを判定します。  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>戻り値  
 別のウィンドウまたはフレーム ウィンドウに、ウィンドウをドッキングできる場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="canbedockedtopane"></a>  CPaneFrameWnd::CanBeDockedToPane  
 ミニフレーム ウィンドウをペインにドッキングできるかどうかを判定します。  
  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDockingBar*  
 ウィンドウ。  
  
### <a name="return-value"></a>戻り値  
 ミニ フレームにドッキングできる場合は 0 以外*pDockingBar*。 それ以外の場合に 0 です。  
  
##  <a name="checkgrippervisibility"></a>  CPaneFrameWnd::CheckGripperVisibility  

  
```  
virtual void CheckGripperVisibility();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="converttotabbeddocument"></a>  CPaneFrameWnd::ConvertToTabbedDocument  
 ペインをタブ付きドキュメントに変換します。  
  
```  
virtual void ConvertToTabbedDocument();
```  
  
##  <a name="create"></a>  CPaneFrameWnd::Create  
 ミニフレーム ウィンドウを作成しにアタッチします、 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)オブジェクト。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*したとき*  
 ミニフレーム ウィンドウに表示されるテキストを指定します。  
  
 [in]*dwStyle*  
 ウィンドウ スタイルを指定します。 詳細については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。  
  
 [in]*rect*  
 ミニフレーム ウィンドウの位置と初期サイズを指定します。  
  
 [in][out]*pParentWnd*  
 ミニフレーム ウィンドウの親フレームを指定します。 この値は、NULL は指定できません。  
  
 [in][out]*pContext*  
 ユーザー定義のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウを正常に作成した場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 ミニフレーム ウィンドウは、2 つの手順で作成されます。 最初に、フレームワークを作成、`CPaneFrameWnd`オブジェクト。 次から`Create`Windows ミニフレーム ウィンドウを作成し、アタッチ先に、`CPaneFrameWnd`オブジェクト。  
  
##  <a name="createex"></a>  CPaneFrameWnd::CreateEx  
 ミニフレーム ウィンドウを作成しにアタッチします、 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwStyleEx*  
 拡張ウィンドウ スタイルを指定します。 詳細については、次を参照してください[拡張ウィンドウ スタイル。](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
 [in]*したとき*  
 ミニフレーム ウィンドウに表示されるテキストを指定します。  
  
 [in]*dwStyle*  
 ウィンドウ スタイルを指定します。 詳細については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。  
  
 [in]*rect*  
 ミニフレーム ウィンドウの位置と初期サイズを指定します。  
  
 [in][out]*pParentWnd*  
 ミニフレーム ウィンドウの親フレームを指定します。 この値は、NULL は指定できません。  
  
 [in][out]*pContext*  
 ユーザー定義のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウを正常に作成した場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 ミニフレーム ウィンドウは、2 つの手順で作成されます。 最初に、フレームワークを作成、`CPaneFrameWnd`オブジェクト。 次から`Create`Windows ミニフレーム ウィンドウを作成し、アタッチ先に、`CPaneFrameWnd`オブジェクト。  
  
##  <a name="dockpane"></a>  CPaneFrameWnd::DockPane  
 ペインをドッキングします。  
  
```  
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*bWasDocked*  
 ウィンドウが既にドッキングされている場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合、`CDockablePane`にドッキングされた状態は NULL それ以外の場合、ウィンドウをしたことです。  
  
##  <a name="findfloatingpanebyid"></a>  CPaneFrameWnd::FindFloatingPaneByID  
 フローティング ペインのグローバル リストで、指定したコントロール ID のペインを検索します。  
  
```  
static CBasePane* FindFloatingPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nID*  
 検索する、ウィンドウのコントロール ID を表します。  
  
### <a name="return-value"></a>戻り値  
 指定したコントロール id; ウィンドウウィンドウに指定したコントロール ID があるない場合、それ以外の場合、NULL します。  
  
##  <a name="framefrompoint"></a>  CPaneFrameWnd::FrameFromPoint  
 指定したポイントを含むミニフレーム ウィンドウを検索します。  
  
```  
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,  
    int nSensitivity,  
    CPaneFrameWnd* pFrameToExclude = NULL,  
    BOOL bFloatMultiOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pt*  
 画面座標にポイントします。  
  
 [in]*nSensitivity*  
 このサイズに、ミニフレーム ウィンドウの検索領域を増やします。 ミニフレーム ウィンドウは、指定したポイントが拡大された領域内にある場合に、検索条件を満たします。  
  
 [in]*pFrameToExclude*  
 検索から除外ミニフレーム ウィンドウを指定します。  
  
 [in]*bFloatMultiOnly*  
 TRUE の場合のみ CBRS_FLOAT_MULTI スタイルのミニフレーム ウィンドウを検索します。 FALSE の場合は、すべてのミニフレーム ウィンドウを検索します。  
  
### <a name="return-value"></a>戻り値  
 含むミニフレーム ウィンドウへのポインター *pt*null それ以外の場合。  
  
##  <a name="getcaptionheight"></a>  CPaneFrameWnd::GetCaptionHeight  
 ミニフレーム ウィンドウのキャプションの高さを返します。  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウのピクセル単位の高さ。  
  
### <a name="remarks"></a>Remarks  
 ミニフレーム ウィンドウの高さを決定するには、このメソッドを呼び出します。 既定では、高さは SM_CYSMCAPTION に設定されます。 詳細については、次を参照してください。 [GetSystemMetrics 関数](https://msdn.microsoft.com/library/windows/desktop/ms724385)します。  
  
##  <a name="getcaptionrect"></a>  CPaneFrameWnd::GetCaptionRect  
 ミニフレーム ウィンドウのキャプションに外接する四角形を計算します。  
  
```  
virtual void GetCaptionRect(CRect& rectCaption) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*rectCaption*  
 ミニフレーム ウィンドウのキャプションの画面座標の位置とサイズが含まれています。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ミニフレーム ウィンドウのキャプションの外接する四角形を計算するためにフレームワークによって呼び出されます。  
  
##  <a name="getcaptiontext"></a>  CPaneFrameWnd::GetCaptionText  
 キャプション テキストを返します。  
  
```  
virtual CString GetCaptionText();
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウのキャプション テキスト。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、キャプション テキストを表示するときにフレームワークによって呼び出されます。  
  
##  <a name="getdockingmanager"></a>  CPaneFrameWnd::GetDockingManager  

  
```  
CDockingManager* GetDockingManager() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getdockingmode"></a>  CPaneFrameWnd::GetDockingMode  
 ドッキングのモードを返します。  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドッキングのモード。 次のいずれかの値です。  
  
- DT_STANDARD  
  
- DT_IMMEDIATE  
  
- DT_SMART  
  
##  <a name="getfirstvisiblepane"></a>  CPaneFrameWnd::GetFirstVisiblePane  
 ミニフレーム ウィンドウに含まれる最初の可視ペインを返します。  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウ、またはミニフレーム ウィンドウにペインが含まれていない場合は NULL の最初のウィンドウ。  
  
##  <a name="gethotpoint"></a>  CPaneFrameWnd::GetHotPoint  

  
```  
CPoint GetHotPoint() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getpane"></a>  CPaneFrameWnd::GetPane  
 ミニフレーム ウィンドウに含まれるペインを返します。  
  
```  
virtual CWnd* GetPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウにペインが含まれていない場合に、ミニフレーム、または NULL に含まれるウィンドウです。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getpanecount"></a>  CPaneFrameWnd::GetPaneCount  
 ミニフレーム ウィンドウに含まれるペインの数を返します。  
  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウのペインの数。 この値は 0 を指定できます。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getparent"></a>  CPaneFrameWnd::GetParent  

  
```  
CWnd* GetParent();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getpinstate"></a>  CPaneFrameWnd::GetPinState  

  
```  
BOOL GetPinState() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getrecentfloatingrect"></a>  CPaneFrameWnd::GetRecentFloatingRect  

  
```  
CRect GetRecentFloatingRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getvisiblepanecount"></a>  CPaneFrameWnd::GetVisiblePaneCount  
 ミニフレーム ウィンドウに含まれる可視ペインの数を返します。  
  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 表示されているペインの数。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="hittest"></a>  CPaneFrameWnd::HitTest  
 特定のポイントに、ミニフレーム ウィンドウのどの部分があるか判定します。  
  
```  
virtual LRESULT HitTest(
    CPoint point,  
    BOOL bDetectCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 テストする点です。  
  
 [in]*bDetectCaption*  
 TRUE の場合は、キャプションに対するポイントを確認します。 FALSE の場合は、キャプションを無視します。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
|[値]|説明|  
|-----------|-------------|  
|HTNOWHERE|ミニフレーム ウィンドウ外です。|  
|HTCLIENT|クライアント領域内です。|  
|HTCAPTION|キャプションがポイントです。|  
|HTTOP|上部にあります。|  
|HTTOPLEFT|左上にあります。|  
|HTTOPRIGHT|右上にあります。|  
|HTLEFT|ポイントは、左側にあります。|  
|HTRIGHT|右側にあります。|  
|HTBOTTOM|下部にあります。|  
|HTBOTTOMLEFT|左下です。|  
|HTBOTTOMRIGHT|右下にあります。|  
  
##  <a name="iscaptured"></a>  CPaneFrameWnd::IsCaptured  

  
```  
BOOL IsCaptured() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isdelayshow"></a>  CPaneFrameWnd::IsDelayShow  

  
```  
BOOL IsDelayShow() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isrolldown"></a>  CPaneFrameWnd::IsRollDown  
 ミニフレーム ウィンドウをロール ダウンするかどうかを判断します。  
  
```  
virtual BOOL IsRollDown() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウをロール ダウンする必要がある場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ミニフレーム ウィンドウをロール ダウンするかどうかを判断するためにフレームワークによって呼び出されます。 プログラムのロールアップ/ロールダウン機能は、AFX_CBRS_AUTO_ROLLUP フラグが少なくとも 1 つのペインが含まれている場合に、ミニフレーム ウィンドウに有効です。 ウィンドウが作成されたときに、このフラグが設定されます。 詳細については、次を参照してください。 [cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)します。  
  
 既定では、フレームワークは、マウス ポインターをウィンドウをロール ダウンする必要があるかどうかを判断するミニフレーム ウィンドウ外接する四角形がかどうかをチェックします。 派生クラスでは、この動作をオーバーライドすることができます。  
  
##  <a name="isrollup"></a>  CPaneFrameWnd::IsRollUp  
 ミニフレーム ウィンドウをロール アップするかどうかを判断します。  
  
```  
virtual BOOL IsRollUp() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウをロール アップする必要がある場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ミニフレーム ウィンドウをロール アップするかどうかを判断するためにフレームワークによって呼び出されます。 プログラムのロールアップ/ロールダウン機能は、AFX_CBRS_AUTO_ROLLUP フラグが少なくとも 1 つのペインが含まれている場合に、ミニフレーム ウィンドウに有効です。 ウィンドウが作成されたときに、このフラグが設定されます。 詳細については、次を参照してください。 [cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)します。  
  
 既定では、フレームワークは、マウス ポインターが、ウィンドウが、ロール アップするかどうかを判断するミニフレーム ウィンドウ外接する四角形がかどうかをチェックします。 派生クラスでは、この動作をオーバーライドすることができます。  
  
##  <a name="killdockingtimer"></a>  CPaneFrameWnd::KillDockingTimer  
 ドッキング タイマーを停止します。  
  
```  
void KillDockingTimer();
```  
  
##  <a name="loadstate"></a>  CPaneFrameWnd::LoadState  
 レジストリからペインの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 プロファイル名。  
  
 [in]*uiID*  
 ペインの ID  
  
### <a name="return-value"></a>戻り値  
 ペインの状態が正常に読み込まれている場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="m_busesavebits"></a>  CPaneFrameWnd::m_bUseSaveBits  
 CS_SAVEBITS クラスのスタイルがウィンドウ クラスを登録するかどうかを指定します。  
  
```  
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;  
```  
  
### <a name="remarks"></a>Remarks  
 この静的なメンバーを CS_SAVEBITS スタイルがミニフレーム ウィンドウ クラスを登録する場合は true を設定します。 これにより、ミニフレーム ウィンドウをドラッグすると、ちらつきを減らすことができます。  
  
##  <a name="onbeforedock"></a>  CPaneFrameWnd::OnBeforeDock  
 ドッキングが可能かどうかを判定します。  
  
```  
virtual BOOL OnBeforeDock();
```  
  
### <a name="return-value"></a>戻り値  
 ドッキング可能な場合は TRUE。それ以外の場合、FALSE です。  
  
##  <a name="oncheckrollstate"></a>  CPaneFrameWnd::OnCheckRollState  
 ミニフレーム ウィンドウをロール アップまたはロール ダウンするかどうかを判断します。  
  
```  
virtual void OnCheckRollState();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、上または下に、ミニフレーム ウィンドウをロールかどうかを判断するためにフレームワークによって呼び出されます。  
  
 既定では、フレームワーク[CPaneFrameWnd::IsRollUp](#isrollup)と[CPaneFrameWnd::IsRollDown](#isrolldown)とだけ拡大またはミニフレーム ウィンドウを復元します。 別の視覚効果を使用する派生クラスでこのメソッドをオーバーライドすることができます。  
  
##  <a name="ondocktorecentpos"></a>  CPaneFrameWnd::OnDockToRecentPos  
 ミニフレーム ウィンドウを直前の位置にドッキングします。  
  
```  
virtual void OnDockToRecentPos();
```  
  
##  <a name="ondrawborder"></a>  CPaneFrameWnd::OnDrawBorder  
 ミニフレーム ウィンドウの境界線を描画します。  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 境界線を描画するために使用するデバイス コンテキスト。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ミニフレーム ウィンドウの境界線を描画するためにフレームワークによって呼び出されます。  
  
##  <a name="onkillrolluptimer"></a>  CPaneFrameWnd::OnKillRollUpTimer  
 ロールアップ タイマーを停止します。  
  
```  
virtual void OnKillRollUpTimer();
```  
  
##  <a name="onmovepane"></a>  CPaneFrameWnd::OnMovePane  
 ミニフレーム ウィンドウを指定したオフセットだけ移動します。  
  
```  
virtual void OnMovePane(
    CPane* pBar,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 (無視) ウィンドウへのポインター。  
  
 [in]*ptOffset*  
 ウィンドウを移動するためのオフセット。  
  
##  <a name="onpanerecalclayout"></a>  CPaneFrameWnd::OnPaneRecalcLayout  
 ミニフレーム ウィンドウ内のペインのレイアウトを調整します。  
  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>Remarks  
 ミニフレーム ウィンドウ内のペインのレイアウトを調整する必要がありますと、フレームワークはこのメソッドを呼び出します。  
  
 既定では、ミニフレーム ウィンドウの完全なクライアント領域をカバーする、ウィンドウが配置されます。  
  
##  <a name="onsetrolluptimer"></a>  CPaneFrameWnd::OnSetRollUpTimer  
 ロールアップ タイマーを設定します。  
  
```  
virtual void OnSetRollUpTimer();
```  
  
##  <a name="onshowpane"></a>  CPaneFrameWnd::OnShowPane  
 ミニフレーム ウィンドウ内のペインが非表示になるとき、または表示されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 ウィンドウを表示または非表示になります。  
  
 [in]*bShow*  
 TRUE の場合、ウィンドウは表示されています。ウィンドウが非表示の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 ミニフレーム ウィンドウのペインの表示または非表示のときに、フレームワークによって呼び出されます。 既定の実装では、何も行われません。  
  
##  <a name="pin"></a>  CPaneFrameWnd::Pin  

  
```  
void Pin(BOOL bPin = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bPin*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="panefrompoint"></a>  CPaneFrameWnd::PaneFromPoint  
 ユーザーが指定した位置がミニフレーム ウィンドウ内のペインに含まれている場合、そのペインを返します。  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bCheckVisibility);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 ポイント画面座標で、ユーザーがクリックしました。  
  
 [in]*nSensitivity*  
 このパラメーターは使用されません。  
  
 [in]*bCheckVisibility*  
 表示されているペインのみが返されること; を指定する場合は TRUEそれ以外の場合、FALSE です。  
  
### <a name="return-value"></a>戻り値  
 ユーザーがクリックしたペインまたはウィンドウがその場所に存在しない場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 指定したポイントを含むウィンドウを取得するには、このメソッドを呼び出します。  
  
##  <a name="redrawall"></a>  CPaneFrameWnd::RedrawAll  
 すべてのミニフレーム ウィンドウを再描画します。  
  
```  
static void RedrawAll();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出してすべてのミニフレーム ウィンドウを更新する[CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow)ウィンドウごとにします。  
  
##  <a name="removenonvalidpanes"></a>  CPaneFrameWnd::RemoveNonValidPanes  
 有効でないウィンドウを削除するために、フレームワークによって呼び出されます。  
  
```  
virtual void RemoveNonValidPanes();
```  
  
##  <a name="removepane"></a>  CPaneFrameWnd::RemovePane  
 ミニフレーム ウィンドウから、ペインを削除します。  
  
```  
virtual void RemovePane(
    CBasePane* pWnd,  
    BOOL bDestroy = FALSE,  
    BOOL bNoDelayedDestroy = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*我が物*  
 削除するウィンドウへのポインター。  
  
 [in]*bDestroy*  
 ミニフレーム ウィンドウの動作を指定します。 場合*bDestroy*が true の場合、このメソッドはすぐに、ミニフレーム ウィンドウを破棄します。 FALSE の場合、このメソッドは、特定の遅延後に、ミニフレーム ウィンドウを破棄します。  
  
 [in]*bNoDelayedDestroy*  
 TRUE の場合、遅延の破棄は無効です。 FALSE の場合、遅延の破棄が有効にします。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、すぐに、または特定の遅延の後、ミニフレーム ウィンドウを破棄できます。 ミニフレーム ウィンドウの破棄を遅延する場合に FALSE を渡す、 *bNoDelayedDestroy*パラメーター。 遅延の破棄は、フレームワークが AFX_WM_CHECKEMPTYMINIFRAME メッセージを処理するときに発生します。  
  
##  <a name="replacepane"></a>  CPaneFrameWnd::ReplacePane  
 ペインを別のペインに置き換えます。  
  
```  
virtual void ReplacePane(
    CBasePane* pBarOrg,  
    CBasePane* pBarReplaceWith);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBarOrg*  
 元のウィンドウへのポインター。  
  
 [in]*pBarReplaceWith*  
 元のウィンドウを置換するウィンドウへのポインター。  
  
##  <a name="savestate"></a>  CPaneFrameWnd::SaveState  
 レジストリにペインの状態を保存します。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 プロファイル名。  
  
 [in]*uiID*  
 ペインの ID  
  
### <a name="return-value"></a>戻り値  
 ペインの状態が正常に保存されている場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="setcaptionbuttons"></a>  CPaneFrameWnd::SetCaptionButtons  
 キャプションのボタンを設定します。  
  
```  
virtual void SetCaptionButtons(DWORD dwButtons);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwButtons*  
 次の値のビットごとの OR の組み合わせです。  
  
- AFX_CAPTION_BTN_CLOSE  
  
- AFX_CAPTION_BTN_PIN  
  
- AFX_CAPTION_BTN_MENU  
  
- AFX_CAPTION_BTN_CUSTOMIZE  
  
##  <a name="setdelayshow"></a>  CPaneFrameWnd::SetDelayShow  

  
```  
void SetDelayShow(BOOL bDelayShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bDelayShow*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setdockingmanager"></a>  CPaneFrameWnd::SetDockingManager  

  
```  
void SetDockingManager(CDockingManager* pManager);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pManager*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setdockingtimer"></a>  CPaneFrameWnd::SetDockingTimer  
 ドッキング タイマーを設定します。  
  
```  
void SetDockingTimer(UINT nTimeOut);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*タイムアウト*  
 タイムアウト値 (ミリ秒単位)。  
  
##  <a name="setdockstate"></a>  CPaneFrameWnd::SetDockState  
 ドッキング状態を設定します。  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDockManager*  
 ドッキングのマネージャーへのポインター。  
  
##  <a name="sethotpoint"></a>  CPaneFrameWnd::SetHotPoint  

  
```  
void SetHotPoint(CPoint& ptNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ptNew*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setpredockstate"></a>  CPaneFrameWnd::SetPreDockState  
 ドッキング前の状態を設定するために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,  
    CBasePane* pBarToDock = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*preDockState*  
 次の値を使用できます。  
  
- PDS_NOTHING、  
  
- PDS_DOCK_REGULAR、  
  
- PDS_DOCK_TO_TAB  
  
 [in]*pBarToDock*  
 ドッキング ウィンドウへのポインター。  
  
 [in]*dockMethod*  
 ドッキング メソッド。 (このパラメーターが無視されます)  
  
### <a name="return-value"></a>戻り値  
 ミニフレーム ウィンドウがドッキング解除する場合は TRUE。ドッキングされている場合は FALSE。  
  
##  <a name="sizetocontent"></a>  CPaneFrameWnd::SizeToContent  
 これは含まれているペインに相当するように、ミニフレーム ウィンドウのサイズを調整します。  
  
```  
virtual void SizeToContent();
```  
  
### <a name="remarks"></a>Remarks  
 含まれているペインのサイズにミニフレーム ウィンドウのサイズを調整するには、このメソッドを呼び出します。  
  
##  <a name="starttearoff"></a>  CPaneFrameWnd::StartTearOff  
 メニューをティアオフします。  
  
```  
BOOL StartTearOff(CMFCPopu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pMenu*  
 メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE。それ以外の場合、FALSE です。  
  
##  <a name="storerecentdocksiteinfo"></a>  CPaneFrameWnd::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="storerecenttabrelatedinfo"></a>  CPaneFrameWnd::StoreRecentTabRelatedInfo  

  
```  
virtual void StoreRecentTabRelatedInfo(
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
 [CWnd クラス](../../mfc/reference/cwnd-class.md)
