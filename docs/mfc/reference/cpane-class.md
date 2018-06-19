---
title: CPane クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPane
- AFXPANE/CPane
- AFXPANE/CPane::AdjustSizeImmediate
- AFXPANE/CPane::AllocElements
- AFXPANE/CPane::AllowShowOnPaneMenu
- AFXPANE/CPane::CalcAvailableSize
- AFXPANE/CPane::CalcInsideRect
- AFXPANE/CPane::CalcRecentDockedRect
- AFXPANE/CPane::CalcSize
- AFXPANE/CPane::CanBeDocked
- AFXPANE/CPane::CanBeTabbedDocument
- AFXPANE/CPane::ConvertToTabbedDocument
- AFXPANE/CPane::CopyState
- AFXPANE/CPane::Create
- AFXPANE/CPane::CreateDefaultMiniframe
- AFXPANE/CPane::CreateEx
- AFXPANE/CPane::DockByMouse
- AFXPANE/CPane::DockPane
- AFXPANE/CPane::DockPaneStandard
- AFXPANE/CPane::DockToFrameWindow
- AFXPANE/CPane::DoesAllowSiblingBars
- AFXPANE/CPane::FloatPane
- AFXPANE/CPane::GetAvailableExpandSize
- AFXPANE/CPane::GetAvailableStretchSize
- AFXPANE/CPane::GetBorders
- AFXPANE/CPane::GetClientHotSpot
- AFXPANE/CPane::GetDockSiteRow
- AFXPANE/CPane::GetExclusiveRowMode
- AFXPANE/CPane::GetHotSpot
- AFXPANE/CPane::GetMinSize
- AFXPANE/CPane::GetPaneName
- AFXPANE/CPane::GetVirtualRect
- AFXPANE/CPane::IsChangeState
- AFXPANE/CPane::IsDragMode
- AFXPANE/CPane::IsInFloatingMultiPaneFrameWnd
- AFXPANE/CPane::IsLeftOf
- AFXPANE/CPane::IsResizable
- AFXPANE/CPane::IsTabbed
- AFXPANE/CPane::LoadState
- AFXPANE/CPane::MoveByAlignment
- AFXPANE/CPane::MovePane
- AFXPANE/CPane::OnAfterChangeParent
- AFXPANE/CPane::OnBeforeChangeParent
- AFXPANE/CPane::OnPressCloseButton
- AFXPANE/CPane::OnShowControlBarMenu
- AFXPANE/CPane::RecalcLayout
- AFXPANE/CPane::SaveState
- AFXPANE/CPane::SetActiveInGroup
- AFXPANE/CPane::SetBorders
- AFXPANE/CPane::SetClientHotSpot
- AFXPANE/CPane::SetDockState
- AFXPANE/CPane::SetExclusiveRowMode
- AFXPANE/CPane::SetMiniFrameRTC
- AFXPANE/CPane::SetMinSize
- AFXPANE/CPane::SetVirtualRect
- AFXPANE/CPane::StretchPaneDeferWndPos
- AFXPANE/CPane::ToggleAutoHide
- AFXPANE/CPane::UndockPane
- AFXPANE/CPane::UpdateVirtualRect
- AFXPANE/CPane::OnAfterDock
- AFXPANE/CPane::OnAfterFloat
- AFXPANE/CPane::OnBeforeDock
- AFXPANE/CPane::OnBeforeFloat
- AFXPANE/CPane::m_bHandleMinSize
- AFXPANE/CPane::m_recentDockInfo
dev_langs:
- C++
helpviewer_keywords:
- CPane [MFC], AdjustSizeImmediate
- CPane [MFC], AllocElements
- CPane [MFC], AllowShowOnPaneMenu
- CPane [MFC], CalcAvailableSize
- CPane [MFC], CalcInsideRect
- CPane [MFC], CalcRecentDockedRect
- CPane [MFC], CalcSize
- CPane [MFC], CanBeDocked
- CPane [MFC], CanBeTabbedDocument
- CPane [MFC], ConvertToTabbedDocument
- CPane [MFC], CopyState
- CPane [MFC], Create
- CPane [MFC], CreateDefaultMiniframe
- CPane [MFC], CreateEx
- CPane [MFC], DockByMouse
- CPane [MFC], DockPane
- CPane [MFC], DockPaneStandard
- CPane [MFC], DockToFrameWindow
- CPane [MFC], DoesAllowSiblingBars
- CPane [MFC], FloatPane
- CPane [MFC], GetAvailableExpandSize
- CPane [MFC], GetAvailableStretchSize
- CPane [MFC], GetBorders
- CPane [MFC], GetClientHotSpot
- CPane [MFC], GetDockSiteRow
- CPane [MFC], GetExclusiveRowMode
- CPane [MFC], GetHotSpot
- CPane [MFC], GetMinSize
- CPane [MFC], GetPaneName
- CPane [MFC], GetVirtualRect
- CPane [MFC], IsChangeState
- CPane [MFC], IsDragMode
- CPane [MFC], IsInFloatingMultiPaneFrameWnd
- CPane [MFC], IsLeftOf
- CPane [MFC], IsResizable
- CPane [MFC], IsTabbed
- CPane [MFC], LoadState
- CPane [MFC], MoveByAlignment
- CPane [MFC], MovePane
- CPane [MFC], OnAfterChangeParent
- CPane [MFC], OnBeforeChangeParent
- CPane [MFC], OnPressCloseButton
- CPane [MFC], OnShowControlBarMenu
- CPane [MFC], OnShowControlBarMenu
- CPane [MFC], RecalcLayout
- CPane [MFC], SaveState
- CPane [MFC], SetActiveInGroup
- CPane [MFC], SetBorders
- CPane [MFC], SetClientHotSpot
- CPane [MFC], SetDockState
- CPane [MFC], SetExclusiveRowMode
- CPane [MFC], SetMiniFrameRTC
- CPane [MFC], SetMinSize
- CPane [MFC], SetVirtualRect
- CPane [MFC], StretchPaneDeferWndPos
- CPane [MFC], ToggleAutoHide
- CPane [MFC], UndockPane
- CPane [MFC], UpdateVirtualRect
- CPane [MFC], OnAfterDock
- CPane [MFC], OnAfterFloat
- CPane [MFC], OnBeforeDock
- CPane [MFC], OnBeforeFloat
- CPane [MFC], m_bHandleMinSize
- CPane [MFC], m_recentDockInfo
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b764777f33b0ae8ea1521e931ee45740f7057ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378442"
---
# <a name="cpane-class"></a>CPane Class
`CPane`クラスは、の機能強化、 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)です。 既存の MFC プロジェクトをアップグレードする場合は、すべての出現を置換`CControlBar`で`CPane`です。  
  
## <a name="syntax"></a>構文  
  
```  
class CPane : public CBasePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CPane::~CPane`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPane::AdjustSizeImmediate](#adjustsizeimmediate)|すぐに、ウィンドウのレイアウトを再計算します。|  
|[CPane::AllocElements](#allocelements)|内部使用のためには、記憶域を割り当てます。|  
|[CPane::AllowShowOnPaneMenu](#allowshowonpanemenu)|ランタイムによって生成されるアプリケーションに対し、ウィンドウの一覧で、ウィンドウを示すかどうかを指定します。|  
|[CPane::CalcAvailableSize](#calcavailablesize)|指定した四角形と現在のウィンドウの四角形のサイズの差を計算します。|  
|[CPane::CalcInsideRect](#calcinsiderect)|内部の計算の罫線とグリッパー考慮に入れて、ペインの四角形。|  
|[CPane::CalcRecentDockedRect](#calcrecentdockedrect)|ドッキングされた最近の四角形を計算します。|  
|[CPane::CalcSize](#calcsize)|ウィンドウのサイズを計算します。|  
|[CPane::CanBeDocked](#canbedocked)|指定された基本ペインで、ペインをドッキングできるかどうかを判断します。|  
|[CPane::CanBeTabbedDocument](#canbetabbeddocument)|ペインをタブ付きドキュメントに変換できるかどうかを判断します。|  
|[CPane::ConvertToTabbedDocument](#converttotabbeddocument)|ドッキング可能ペインをタブ付きドキュメントに変換します。|  
|[CPane::CopyState](#copystate)|ペインの状態をコピーします。 (上書き[CBasePane::CopyState](../../mfc/reference/cbasepane-class.md#copystate))。|  
|[Cpane::create](#create)|コントロール バーを作成し、それにアタッチ、`CPane`オブジェクト。|  
|[Cpane::createdefaultminiframe](#createdefaultminiframe)|フローティング ペインのミニフレーム ウィンドウを作成します。|  
|[Cpane::createex](#createex)|コントロール バーを作成し、それにアタッチ、`CPane`オブジェクト。|  
|`CPane::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CPane::DockByMouse](#dockbymouse)|メソッドをドッキング マウスを使用して、ウィンドウをドッキングします。|  
|[CPane::DockPane](#dockpane)|基本のペインをフローティング ペインをドッキングします。|  
|[CPane::DockPaneStandard](#dockpanestandard)|アウトライン (標準) のドッキングを使用して、ウィンドウをドッキングします。|  
|[CPane::DockToFrameWindow](#docktoframewindow)|フレームにドッキング可能ペインをドッキングします。 (`CBasePane::DockToFrameWindow` をオーバーライドします)。|  
|[CPane::DoesAllowSiblingBars](#doesallowsiblingbars)|現在のウィンドウがドッキングされているのと同じ行の別のペインをドッキングできるかどうかを示します。|  
|[CPane::FloatPane](#floatpane)|ペインをフローティング状態です。|  
|[CPane::GetAvailableExpandSize](#getavailableexpandsize)|(ピクセル単位) のウィンドウが拡張可能な量を返します。|  
|[CPane::GetAvailableStretchSize](#getavailablestretchsize)|ウィンドウを縮小できます (ピクセル単位) の量を返します。|  
|[CPane::GetBorders](#getborders)|ウィンドウの境界線の幅を返します。|  
|[CPane::GetClientHotSpot](#getclienthotspot)|返します、*ホット スポット*ペインのです。|  
|[CPane::GetDockSiteRow](#getdocksiterow)|これで、ウィンドウがドッキングされているドッキング行を返します。|  
|[CPane::GetExclusiveRowMode](#getexclusiverowmode)|ウィンドウが、排他行モードにするかどうかを判断します。|  
|[CPane::GetHotSpot](#gethotspot)|返します、基になるに格納されているホット スポット`CMFCDragFrameImpl`オブジェクト。|  
|[CPane::GetMinSize](#getminsize)|下限のウィンドウのサイズを取得します。|  
|[CPane::GetPaneName](#getpanename)|ウィンドウのタイトルを取得します。|  
|`CPane::GetResizeStep`|内部的に使用します。|  
|`CPane::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CPane::GetVirtualRect](#getvirtualrect)|取得、*仮想の長方形*ウィンドウのです。|  
|[CPane::IsChangeState](#ischangestate)|このメソッドが他のペイン、ドッキング行、およびミニフレーム ウィンドウと比較してウィンドウの位置を分析し、適切な返しますように、ウィンドウが移動されて`AFX_CS_STATUS`値。|  
|[CPane::IsDragMode](#isdragmode)|ウィンドウがドラッグされているかどうかを指定します。|  
|[CPane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|複数のウィンドウ フレーム ウィンドウのウィンドウがかどうかを指定します。 (`CBasePane::IsInFloatingMultiPaneFrameWnd` をオーバーライドします)。|  
|[CPane::IsLeftOf](#isleftof)|(以上) に、ウィンドウを残すかどうかを決定します。 指定した四角形。|  
|[CPane::IsResizable](#isresizable)|ウィンドウのサイズを変更できるかどうかを判断します。 (上書き[cbasepane::isresizable](../../mfc/reference/cbasepane-class.md#isresizable))。|  
|[CPane::IsTabbed](#istabbed)|タブ付きウィンドウのタブ コントロールに、ウィンドウが挿入されたかどうかを判断します。 (上書き[CBasePane::IsTabbed](../../mfc/reference/cbasepane-class.md#istabbed))。|  
|[CPane::LoadState](#loadstate)|レジストリからペインの状態を読み込みます。 (上書き[CBasePane::LoadState](../../mfc/reference/cbasepane-class.md#loadstate))。|  
|[CPane::MoveByAlignment](#movebyalignment)|指定した量によって、ウィンドウと仮想の長方形を移動します。|  
|[CPane::MovePane](#movepane)|指定した四角形に、ウィンドウを移動します。|  
|[CPane::OnAfterChangeParent](#onafterchangeparent)|ウィンドウの親が変更されたときに、フレームワークによって呼び出されます。|  
|[CPane::OnBeforeChangeParent](#onbeforechangeparent)|ウィンドウの親を変更するときに、フレームワークによって呼び出されます。|  
|[CPane::OnPressCloseButton](#onpressclosebutton)|ウィンドウのキャプションの閉じるボタンを選択すると、フレームワークによって呼び出されます。|  
|`CPane::OnProcessDblClk`|内部的に使用します。|  
|[Cpane::onshowcontrolbarmenu](#onshowcontrolbarmenu)|特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。|  
|[Cpane::onshowcontrolbarmenu](#onshowcontrolbarmenu)|特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。|  
|`CPane::PrepareToDock`|内部的に使用します。|  
|[Cpane::recalclayout](#recalclayout)|ウィンドウのレイアウト情報を再計算されます。 (上書き[CBasePane::RecalcLayout](../../mfc/reference/cbasepane-class.md#recalclayout))。|  
|[CPane::SaveState](#savestate)|レジストリにペインの状態を保存します。 (上書き[CBasePane::SaveState](../../mfc/reference/cbasepane-class.md#savestate))。|  
|[Cpane::setactiveingroup](#setactiveingroup)|アクティブなウィンドウのフラグを設定します。|  
|[CPane::SetBorders](#setborders)|ウィンドウの境界線の値を設定します。|  
|[CPane::SetClientHotSpot](#setclienthotspot)|ウィンドウのホット スポットを設定します。|  
|[CPane::SetDockState](#setdockstate)|ドッキング ペインの状態情報を復元します。|  
|[CPane::SetExclusiveRowMode](#setexclusiverowmode)|有効または排他行モードを無効にします。|  
|[CPane::SetMiniFrameRTC](#setminiframertc)|既定のミニフレーム ウィンドウのランタイム クラス情報を設定します。|  
|[CPane::SetMinSize](#setminsize)|下限のウィンドウのサイズを設定します。|  
|[CPane::SetVirtualRect](#setvirtualrect)|セット、*仮想の長方形*ウィンドウのです。|  
|[CPane::StretchPaneDeferWndPos](#stretchpanedeferwndpos)|垂直または水平にドッキング スタイルに基づいてウィンドウを拡大します。|  
|[CPane::ToggleAutoHide](#toggleautohide)|自動非表示モードを切り替えます。|  
|[CPane::UndockPane](#undockpane)|ドッキング サイト、既定のスライダーまたはミニフレーム ウィンドウの現在のドッキング位置から、ウィンドウを削除します。 (上書き[CBasePane::UndockPane](../../mfc/reference/cbasepane-class.md#undockpane))。|  
|[CPane::UpdateVirtualRect](#updatevirtualrect)|仮想の長方形を更新します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPane::OnAfterDock](#onafterdock)|ペインがドッキングされているときに、フレームワークによって呼び出されます。|  
|[CPane::OnAfterFloat](#onafterfloat)|ペインがフローティング状態になるときに、フレームワークによって呼び出されます。|  
|[CPane::OnBeforeDock](#onbeforedock)|ウィンドウがドッキングされると、フレームワークによって呼び出されます。|  
|[CPane::OnBeforeFloat](#onbeforefloat)|ペインをフローティング状態にできるときに、フレームワークによって呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPane::m_bHandleMinSize](#m_bhandleminsize)|ウィンドウの最小サイズの一貫した処理を有効にします。|  
|[:M_recentdockinfo](#m_recentdockinfo)|最新のドッキング情報が含まれています。|  
  
## <a name="remarks"></a>コメント  
 通常、`CPane`オブジェクトは直接インスタンス化されません。 ドッキングの機能を持つウィンドウを必要とする場合から、オブジェクトを派生させる[CDockablePane](../../mfc/reference/cdockablepane-class.md)です。 ツールバーの機能を必要とする場合から、オブジェクトを派生させる[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)です。  
  
 クラスを派生する`CPane`にドッキングできる、 [CDockSite](../../mfc/reference/cdocksite-class.md)辺にし、 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxPane.h  
  
##  <a name="adjustsizeimmediate"></a>  CPane::AdjustSizeImmediate  
 すぐに、ウィンドウのレイアウトを再計算します。  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bRecalcLayout`  
 `TRUE` 、ウィンドウのレイアウトを自動的に再計算するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのレイアウトを動的に変更するときに、このメソッドを呼び出します。 たとえば、ツール バー ボタンを表示または非表示をするときに、このメソッドを呼び出す可能性があります。  
  
##  <a name="allocelements"></a>  CPane::AllocElements  
 内部使用のためには、記憶域を割り当てます。  
  
```  
BOOL AllocElements(
    int nElements,  
    int cbElement);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nElements`  
 記憶域の割り当てが必要な要素の数。  
  
 [入力] `cbElement`  
 要素のバイト単位のサイズ。  
  
### <a name="return-value"></a>戻り値  
 `FALSE` メモリの割り当てが失敗した場合です。それ以外の場合、`TRUE`です。  
  
##  <a name="allowshowonpanemenu"></a>  CPane::AllowShowOnPaneMenu  
 ランタイムによって生成されるアプリケーションに対し、ウィンドウの一覧で、ウィンドウを示すかどうかを指定します。  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 一覧にある、ウィンドウが表示されている場合それ以外の場合、`FALSE`です。 基本の実装は常に返します`TRUE`です。  
  
### <a name="remarks"></a>コメント  
 AppWizard で生成されたアプリケーションには、それに含まれるウィンドウを一覧表示するメニュー オプションが含まれています。 このメソッドは、一覧で、ウィンドウが表示されているかどうかを判断します。  
  
##  <a name="calcavailablesize"></a>  CPane::CalcAvailableSize  
 指定した四角形と現在のウィンドウの四角形のサイズの差を計算します。  
  
```  
virtual CSize CalcAvailableSize(CRect rectRequired);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectRequired`  
 必要な四角形。  
  
### <a name="return-value"></a>戻り値  
 幅と高さの間の違い`rectRequired`と現在のウィンドウの四角形。  
  
##  <a name="calcinsiderect"></a>  CPane::CalcInsideRect  
 内部の計算の罫線とグリッパーを含む、ウィンドウの四角形。  
  
```  
void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rect`  
 ウィンドウのクライアント領域のオフセットとサイズが含まれています。  
  
 [入力] `bHorz`  
 `TRUE` ウィンドウが水平方向に指向場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ウィンドウのレイアウトを再計算する必要があるときにフレームワークによって呼び出されます。 `rect`パラメーターは、ウィンドウのクライアント領域のオフセットとサイズで塗りつぶされます。 これには、境界線とグリッパーが含まれます。  
  
##  <a name="calcrecentdockedrect"></a>  CPane::CalcRecentDockedRect  
 ドッキングされた最近の四角形を計算します。  
  
```  
void CalcRecentDockedRect();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは更新[:m_recentdockinfo](#m_recentdockinfo)です。  
  
##  <a name="calcsize"></a>  CPane::CalcSize  
 ウィンドウのサイズを計算します。  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bVertDock`  
 `TRUE` ペインを垂直方向にドッキングされているが場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 このメソッドの既定の実装を返しますのサイズ (0, 0) です。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドをオーバーライドする必要があります。  
  
##  <a name="canbedocked"></a>  CPane::CanBeDocked  
 指定された基本ペインで、ペインをドッキングできるかどうかを判断します。  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockBar`  
 このペインをドッキング ペインを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このペインは、指定のドッキング ウィンドウにドッキングできる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは通常、指定されたドッキング ペインで、ペインをドッキングできるかどうかを判断するためにフレームワークによって呼び出されます。 メソッドが現在ペインを評価する、ウィンドウをドッキングできるかどうかを確認するのには、ドッキング配置を有効になります。  
  
 呼び出すことにより、フレーム ウィンドウのさまざまな側面にドッキングを有効にした[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)です。  
  
##  <a name="canbetabbeddocument"></a>  CPane::CanBeTabbedDocument  
 ペインをタブ付きドキュメントに変換できるかどうかを判断します。  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインをタブ付きドキュメントに変換できる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドをオーバーライドし、返す`FALSE`ウィンドウがタブ付きドキュメントに変換されないようにする場合。 タブ付きドキュメント ウィンドウの位置 メニューでは表示されません。  
  
##  <a name="converttotabbeddocument"></a>  CPane::ConvertToTabbedDocument  
 ドッキング可能ペインをタブ付きドキュメントに変換します。  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActiveTabOnly`  
 は使用されません`CPane::ConvertToTabbedDocument`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ペインだけは、タブ付きドキュメントに変換できます。 詳細については、次を参照してください。 [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument)です。  
  
##  <a name="copystate"></a>  CPane::CopyState  
 ペインの状態をコピーします。  
  
```  
virtual void CopyState(CPane* pOrgBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOrgBar`  
 ペインへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドはコピーの状態`pOrgBar`現在のペインにします。  
  
##  <a name="create"></a>  Cpane::create  
 コントロール バーを作成し、それにアタッチ、 [CPane](../../mfc/reference/cpane-class.md)オブジェクト。  
  
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
 [入力] `lpszClassName`  
 Windows クラスの名前を指定します。  
  
 [入力] `dwStyle`  
 ウィンドウのスタイル属性を指定します。 詳細については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。  
  
 [入力] `rect`  
 初期サイズとの位置を指定、`pParentWnd`クライアント座標でのウィンドウ。  
  
 [in][out] `pParentWnd`  
 このウィンドウの親ウィンドウを指定します。  
  
 [入力] `nID`  
 ペインの ID を指定します。  
  
 [入力] `dwControlBarStyle`  
 ウィンドウのスタイルを指定します。 詳細については、次を参照してください。 [cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)です。  
  
 [in][out] `pContext`  
 ウィンドウの作成のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインが正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Windows ウィンドウを作成し、それにアタッチ、`CPane`オブジェクト。  
  
 明示的に初期化されない場合[:m_recentdockinfo](#m_recentdockinfo)を呼び出す前に`Create`、パラメーター`rect`浮動小数点型またはペインをドッキングするときに四角形として使用されます。  
  
##  <a name="createdefaultminiframe"></a>  Cpane::createdefaultminiframe  
 フローティング ペインのミニフレーム ウィンドウを作成します。  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectInitial`  
 初期サイズと位置を画面座標で、ミニフレーム ウィンドウを作成するを指定します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたミニフレーム ウィンドウです。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ペインがフローティング状態になったミニフレーム ウィンドウを作成するためにフレームワークによって呼び出されます。 ミニフレーム ウィンドウは、型にできます[CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)または型の[CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)です。 場合は、ウィンドウには、マルチ ミニフレーム ウィンドウが作成された、`AFX_CBRS_FLOAT_MULTI`スタイル。  
  
 ミニフレーム ウィンドウのランタイム クラス情報は、`CPane::m_pMiniFrameRTC`メンバー。 派生クラスを使用して、カスタマイズされたミニフレーム ウィンドウを作成する場合は、このメンバーを設定することができます。  
  
##  <a name="createex"></a>  Cpane::createex  
 コントロール バーを作成し、それにアタッチ、 [CPane](../../mfc/reference/cpane-class.md)オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyleEx`  
 拡張ウィンドウ スタイル属性を指定します。 詳細については、次を参照してください。[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)です。  
  
 [入力] `lpszClassName`  
 Windows クラスの名前を指定します。  
  
 [入力] `dwStyle`  
 ウィンドウのスタイル属性を指定します。 詳細については、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。  
  
 [入力] `rect`  
 初期サイズとの位置を指定、`pParentWnd`クライアント座標でのウィンドウ。  
  
 [in][out] `pParentWnd`  
 このウィンドウの親ウィンドウを指定します。  
  
 [入力] `nID`  
 ペインの ID を指定します。  
  
 [入力] `dwControlBarStyle`  
 ウィンドウのスタイルを指定します。 詳細については、次を参照してください。 [cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)です。  
  
 [in][out] `pContext`  
 ウィンドウの作成のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインが正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Windows ウィンドウを作成し、それにアタッチ、`CPane`オブジェクト。  
  
 明示的に初期化されない場合[:m_recentdockinfo](#m_recentdockinfo)を呼び出す前に`CreateEx`、パラメーター`rect`浮動小数点型またはペインをドッキングするときに四角形として使用されます。  
  
##  <a name="dockbymouse"></a>  CPane::DockByMouse  
 マウスを使用して、ウィンドウをドッキングします。  
  
```  
virtual BOOL DockByMouse(CBasePane* pDockBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockBar`  
 このペインをドッキングする基本ウィンドウを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウが正常にドッキング可能な場合それ以外の場合、`FALSE`です。  
  
##  <a name="dockpane"></a>  CPane::DockPane  
 基本のペインをフローティング ペインをドッキングします。  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pDockBar`  
 このペインをドッキングする基本ウィンドウを指定します。  
  
 [入力] `lpRect`  
 このウィンドウがドッキングされる基本ペイン上の四角形を指定します。  
  
 [入力] `dockMethod`  
 ドッキングを使用する方法を指定します。 使用可能なオプションは次のとおりです。  
  
|オプション|説明|  
|------------|-----------------|  
|`DM_UNKNOWN`|フレームワークは、ドッキング方法が不明の場合、このオプションを使用します。 ウィンドウでは、直前の浮動小数点位置は格納されません。 また、最近の浮動小数点位置を格納するのに必要はないときに、プログラムで、ペインをドッキングするのには、このオプションを使用することができます。|  
|`DM_MOUSE`|内部的に使用します。|  
|`DM_DBL_CLICK`|グリッパーがダブルクリックされたときに、このオプションが使用されます。 最新のドッキング位置に、ウィンドウの位置を変更します。 場合は、ウィンドウをダブルクリックしてドッキングされていなくても、最新の浮動小数点位置に、ウィンドウが再配置します。|  
|`DM_SHOW`|このオプションは、プログラムによって、ウィンドウをドッキングするのには使用できます。 ウィンドウでは、直前の浮動小数点位置を格納します。|  
|`DM_RECT`|指定されているリージョンに、ウィンドウがドッキングされて`lpRect`です。|  
|`DM_STANDARD`|このオプションを使用するときに、フレームワークは移動中に、アウトライン フレームとして、ウィンドウを描画します。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウが正常にドッキング可能な場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定されている基本ウィンドウ ペインをドッキング、`pDockBar`パラメーター。 呼び出してドッキングを有効にする必要がありますまず[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)です。  
  
##  <a name="dockpanestandard"></a>  CPane::DockPaneStandard  
 アウトライン (標準) のドッキングを使用して、ウィンドウをドッキングします。  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bWasDocked`  
 `TRUE` 場合は、ウィンドウがドッキングされた正常;それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは常に返します、`this`ポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドはだけから派生したペインの使用、 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)です。 詳細については、次を参照してください。 [CDockablePane::DockPaneStandard](../../mfc/reference/cdockablepane-class.md#dockpanestandard)です。  
  
##  <a name="docktoframewindow"></a>  CPane::DockToFrameWindow  
 フレームにドッキング可能ペインをドッキングします。  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 ペインをドッキングする親フレームの側です。  
  
 [入力] `lpRect`  
 指定したサイズです。  
  
 [入力] `dwDockFlags`  
 無視されます。  
  
 [入力] `pRelativeBar`  
 無視されます。  
  
 [入力] `nRelativeIndex`  
 無視されます。  
  
 [入力] `bOuterEdge`  
 場合`TRUE`で指定されている側にドッキング可能なその他のペインが`dwAlignment`、他のウィンドウの外側のウィンドウがドッキングされている親フレームの端に近づきます。 場合`FALSE`、近いクライアント領域の中央に、ペインはドッキングします。  
  
### <a name="return-value"></a>戻り値  
 `FALSE` 場合ペイン分割バー ( [CPaneDivider クラス](../../mfc/reference/cpanedivider-class.md)) に作成された、それ以外にすることはできません`TRUE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="doesallowsiblingbars"></a>  CPane::DoesAllowSiblingBars  
 現在のウィンドウがドッキングされているのと同じ行の別のペインをドッキングできるかどうかを示します。  
  
```  
virtual BOOL DoesAllowSiblingBars() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このペインは、別のペインに自体と同じ行にドッキングできる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 有効にするにまたは呼び出すことによってこの動作を無効にする[CPane::SetExclusiveRowMode](#setexclusiverowmode)です。  
  
 既定では、ツールバーが排他行モードを無効にあり、メニュー バーが排他行モードを有効にします。  
  
##  <a name="floatpane"></a>  CPane::FloatPane  
 ペインをフローティング状態です。  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN,  
    bool bShow = true);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectFloat`  
 ときに移動、ペインがフローティング状態の画面座標で、場所を指定します。  
  
 [入力] `dockMethod`  
 ドッキング ペインがフローティング状態のときに使用する方法を指定します。 使用可能な値の一覧は、次を参照してください。 [CPane::DockPane](#dockpane)です。  
  
 [入力] `bShow`  
 `TRUE` フローティング状態になったときにウィンドウを表示するにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウが正常にフローティング、またはため、ペインをフローティングすることはできません[CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)返します`FALSE`、それ以外の`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定された位置にあるペインをフローティングを呼び出して、`rectFloat`パラメーター。 このメソッドは、ウィンドウの親ミニフレーム ウィンドウを自動的に作成されます。  
  
##  <a name="getavailableexpandsize"></a>  CPane::GetAvailableExpandSize  
 (ピクセル単位) のウィンドウが拡張可能な量を返します。  
  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 戻り値は、使用可能な幅;、ウィンドウが水平にドッキングされている場合それ以外の場合、戻り値の値は、使用可能な高さです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getavailablestretchsize"></a>  CPane::GetAvailableStretchSize  
 ウィンドウを縮小できます (ピクセル単位) の量を返します。  
  
```  
virtual int GetAvailableStretchSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウを縮小できます (ピクセル単位) の量。 場合は、ウィンドウが水平にドッキングされているメモリの量が利用可能な幅です。それ以外の場合は、使用可能な高さです。  
  
### <a name="remarks"></a>コメント  
 利用可能な拡張のサイズがウィンドウのサイズが許容される最小を差し引いて計算されます ( [CPane::GetMinSize](#getminsize)) 現在のサイズから ( [CWnd::GetWindowRect](../../mfc/reference/cwnd-class.md#getwindowrect))。  
  
##  <a name="getborders"></a>  CPane::GetBorders  
 ウィンドウの境界線の幅を返します。  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md)ペインの各辺のピクセル単位で、現在の幅を含むオブジェクトです。 たとえばの値、`left`のメンバー、`CRect`オブジェクトは、左罫線の幅。  
  
### <a name="remarks"></a>コメント  
 境界線のサイズを設定するには、呼び出す[CPane::SetBorders](#setborders)です。  
  
##  <a name="getclienthotspot"></a>  CPane::GetClientHotSpot  
 返します、*ホット スポット*ペインのです。  
  
```  
CPoint GetClientHotSpot() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 *ホット スポット*ウィンドウで、ユーザーを選択し、ウィンドウを移動するを保持するポイントです。 ホット スポットは滑らかなアニメーションのドッキング位置から、ウィンドウが移動したときに使用されます。  
  
##  <a name="getdocksiterow"></a>  CPane::GetDockSiteRow  
 ドッキングの行を返します ( [CDockingPanesRow クラス](../../mfc/reference/cdockingpanesrow-class.md)) で、ウィンドウがドッキングされています。  
  
```  
CDockingPanesRow* GetDockSiteRow() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A `CDockingPanesRow`*、ウィンドウがドッキングされてドッキング行を指すまたは`NULL`ウィンドウがドッキングされていない場合。  
  
##  <a name="getexclusiverowmode"></a>  CPane::GetExclusiveRowMode  
 かどうか、ウィンドウが排他行モードを決定します。  
  
```  
virtual BOOL GetExclusiveRowMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウが排他行モードである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 排他行モードの詳細については、次を参照してください。 [CPane::SetExclusiveRowMode](#setexclusiverowmode)です。  
  
##  <a name="gethotspot"></a>  CPane::GetHotSpot  
 返します、基になるに格納されているホット スポット`CMFCDragFrameImpl`オブジェクト。  
  
```  
CPoint GetHotSpot() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 `CPane`クラスに含まれる、`CMFCDragFrameImpl`オブジェクト、 `m_dragFrameImpl`、つまりを標準ドッキング モードで、ウィンドウを動かしたときに表示される四角形を描画します。 ホット スポットを使用すると、ユーザーが、ウィンドウを移動すると、現在、マウスの位置を基準とした四角形を描画します。  
  
##  <a name="getminsize"></a>  CPane::GetMinSize  
 下限のウィンドウのサイズを取得します。  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `size`  
 A`CSize`最小サイズで塗りつぶされているオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanename"></a>  CPane::GetPaneName  
 ウィンドウのタイトルを取得します。  
  
```  
virtual void GetPaneName(CString& strName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `strName`  
 A`CString`キャプション名で塗りつぶされているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのタイトルは、ウィンドウがドッキングまたはフローティング キャプション領域に表示されます。 ウィンドウがタブ付きグループの一部である場合は、タイトルがタブ領域に表示されます。 タイトルを表示する場合は、ウィンドウが自動的に隠すモードでは、`CMFCAutoHideButton`です。  
  
##  <a name="getvirtualrect"></a>  CPane::GetVirtualRect  
 取得、*仮想の長方形*ウィンドウのです。  
  
```  
void GetVirtualRect(CRect& rectVirtual) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectVirtual`  
 A`CRect`仮想の長方形で塗りつぶされているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ウィンドウを移動すると、フレームワークは、仮想の長方形で、ウィンドウの元の位置を格納します。 フレームワークは、仮想の長方形を使用して、ウィンドウの元の位置を復元できます。  
  
 ウィンドウをプログラムで移動する場合を除き、仮想四角形に関連するメソッドを呼び出す必要はありません。  
  
##  <a name="ischangestate"></a>  CPane::IsChangeState  
 このメソッドが他のペイン、ドッキング行、およびミニフレーム ウィンドウの位置を分析し、適切な返しますように、ウィンドウが移動されて`AFX_CS_STATUS`値。  
  
```  
virtual AFX_CS_STATUS IsChangeState(
    int nOffset,  
    CBasePane** ppTargetBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 ドッキングと小文字の区別を指定します。 内で移動するウィンドウなど、`nOffset`ドッキング行からピクセルはドッキングされます。  
  
 [入力] `ppTargetBar`  
 メソッドが戻るときに`ppTargetBar`を現在のペインをドッキングする必要があります、オブジェクトへのポインターを含むまたは`NULL`ドッキングする必要がありますが発生しなかった場合。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの`AFX_CS_STATUS`値。  
  
|[値]|説明|  
|-----------|-----------------|  
|`CS_NOTHING`|ペインはドッキング サイトの近くにできません。 フレームワークは、ウィンドウをドッキングしていません。|  
|`CS_DOCK_IMMEDIATELY`|ドッキング サイト上のウィンドウは、および`DT_IMMEDIATE`スタイルを有効にします。 フレームワークは、すぐに、ウィンドウをドッキングします。|  
|`CS_DELAY_DOCK`|ウィンドウでは、別のドッキング ペインまたはメイン フレームのエッジのいずれかであるドッキング サイト over です。 フレームワークは、移動を離したときに、ウィンドウをドッキングします。|  
|`CS_DELAY_DOCK_TO_TAB`|ウィンドウでは、タブ付きウィンドウにドッキングするのには、ウィンドウの原因となるドッキング サイト over です。 これは、ウィンドウが、別のドッキング ペインのキャプションまたはタブ付きウィンドウのタブ領域の上に発生します。 フレームワークは、移動を離したときに、ウィンドウをドッキングします。|  
  
##  <a name="isdragmode"></a>  CPane::IsDragMode  
 ウィンドウが移動されているかどうかを指定します。  
  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウが移動されています。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CPane::IsInFloatingMultiPaneFrameWnd  
 複数のウィンドウ フレーム ウィンドウのウィンドウがかどうかを指定します ( [CMultiPaneFrameWnd クラス](../../mfc/reference/cmultipaneframewnd-class.md))。  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 複数のウィンドウ フレーム ウィンドウが、ウィンドウの場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 複数のウィンドウ フレーム ウィンドウのみドッキング可能ペインをフローティングできます。 したがって、`CPane::IsInFloatingMultiPaneFrameWnd`は常に返します`FALSE`です。  
  
##  <a name="isleftof"></a>  CPane::IsLeftOf  
 (以上) に、ウィンドウを残すかどうかを決定します。 指定した四角形。  
  
```  
bool IsLeftOf(
    CRect rect,  
    bool bWindowRect = true) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 A`CRect`比較のために使用されるオブジェクト。  
  
 [入力] `bWindowRect`  
 場合`TRUE`、`rect`場合は、画面座標を格納すると見なされます`FALSE`、`rect`クライアント座標を格納すると見なされます。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ウィンドウが水平にドッキングされている場合の位置を残すかどうかチェック`rect`です。 それ以外の場合、このメソッドをチェックするかどうかの場所は、上記`rect`です。  
  
##  <a name="isresizable"></a>  CPane::IsResizable  
 そのウィンドウはサイズを変更できるかどうかを指定します。  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインがサイズを変更できる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ベース`CPane`オブジェクト サイズは変更できません。  
  
 ドッキング マネージャーでは、サイズ変更可能なフラグを使用して、ウィンドウのレイアウトを決定します。 非サイズ変更可能なウィンドウでは、親フレームの外側のエッジにある常にします。  
  
 非サイズ変更可能なウィンドウがドッキング コンテナー内に配置できません。  
  
##  <a name="istabbed"></a>  CPane::IsTabbed  
 ウィンドウがタブ付きウィンドウのタブ コントロールに挿入されたかどうかを判断します。  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウがタブ付きです。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 タブ付きの状態、浮動小数点から個別に扱われます、ドッキングされている、および状態を自動的に隠すです。  
  
##  <a name="loadstate"></a>  CPane::LoadState  
 レジストリからペインの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイルの名前。  
  
 [入力] `nIndex`  
 プロファイルのインデックス。  
  
 [入力] `uiID`  
 ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインの状態が正常に読み込まれている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、レジストリからペインの状態を読み込むには、このメソッドを呼び出します。 によって保存された追加情報を読み込む派生クラスでオーバーライド[CPane::SaveState](#savestate)です。  
  
 このメソッドをオーバーライドする場合も、基本メソッドを呼び出すし、返す`FALSE`基本メソッドが返す場合`FALSE`です。  
  
##  <a name="m_bhandleminsize"></a>  CPane::m_bHandleMinSize  
 最小ウィンドウ サイズの一貫した処理を有効にします。  
  
```  
AFX_IMPORT_DATA static BOOL m_bHandleMinSize;  
```  
  
### <a name="remarks"></a>コメント  
 場合は、アプリケーションで 1 つまたは複数のドッキング ペインをオーバーライド`GetMinSize`、またはアプリケーションが呼び出す場合`SetMinSize`、この静的メンバーを設定することがあります`TRUE`ウィンドウのサイズは一貫して処理するためにフレームワークを有効にするためにします。  
  
 この値に設定されている場合`TRUE`、伸縮せず、すべてのウィンドウのサイズは、その最小サイズより小さく必要があるされます。 フレームワークは、ペインのサイズのウィンドウ領域を使用するためこの値が設定されている場合、ドッキング ペイン ウィンドウ領域のサイズは変更しないでください`TRUE`です。  
  
##  <a name="m_recentdockinfo"></a>  :M_recentdockinfo  
 最新のドッキング情報が含まれています。  
  
```  
CRecentDockSiteInfo m_recentDockInfo;  
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、このメンバーに、ウィンドウの状態情報を最新のドッキングを格納します。  
  
##  <a name="movebyalignment"></a>  CPane::MoveByAlignment  
 指定した量によって、ウィンドウと仮想の長方形を移動します。  
  
```  
BOOL MoveByAlignment(
    DWORD dwAlignment,  
    int nOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 ペインの配置を指定します。  
  
 [入力] `nOffset`  
 (ピクセル単位) をペインと仮想の長方形を移動する量。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 `dwAlignment` 値は次のいずれかを指定できます。  
  
|[値]|説明|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|フレーム ウィンドウのクライアント領域の上部にドッキングするのには、ウィンドウを有効にします。|  
|`CBRS_ALIGN_BOTTOM`|フレーム ウィンドウのクライアント領域の下部にドッキング可能ウィンドウを有効にします。|  
|`CBRS_ALIGN_LEFT`|フレーム ウィンドウのクライアント領域の左側にドッキング可能ウィンドウを有効にします。|  
|`CBRS_ALIGN_RIGHT`|フレーム ウィンドウのクライアント領域の右側にドッキング可能ウィンドウを有効にします。|  
|`CBRS_ALIGN_ANY`|フレーム ウィンドウのクライアント領域の任意の辺にドッキング可能ウィンドウを有効にします。|  
  
 場合`dwAlignment`が含まれています、`CBRS_ALIGN_LEFT`または`CBRS_ALIGN_RIGHT`フラグ、ペイン、および仮想の四角形は水平方向に、それ以外の場合移動`dwAlignment`が含まれています、`CBRS_ALIGN_TOP`または`CBRS_ALIGN_BOTTOM`フラグ、ペイン、および仮想の長方形を移動垂直方向にします。  
  
##  <a name="movepane"></a>  CPane::MovePane  
 指定した四角形に、ウィンドウを移動します。  
  
```  
virtual CSize MovePane(
    CRect rectNew,  
    BOOL bForceMove,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectNew`  
 ウィンドウの新しい四角形を指定します。  
  
 [入力] `bForceMove`  
 場合`TRUE`、このメソッドは、最小の許可されているウィンドウのサイズを無視 ( [CPane::GetMinSize](#getminsize))、それ以外のウィンドウは、必要に応じて調整、ことを確認するには、少なくとも最小サイズ。  
  
 [入力] `hdwp`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 A`CSize`新旧の四角形の幅と高さで違いを格納しているオブジェクト (古い四角形の`rectNew`)。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ドッキング可能ペインに対してのみ使用されます。  
  
##  <a name="onafterchangeparent"></a>  CPane::OnAfterChangeParent  
 ウィンドウの親が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pWndOldParent`  
 ペインの以前の親ウィンドウです。  
  
### <a name="remarks"></a>コメント  
 ドッキングまたはフローティング操作により、ウィンドウの親が変更されたときに、このメソッドは、フレームワークによって呼び出されます。  
  
##  <a name="onafterdock"></a>  CPane::OnAfterDock  
 ペインがドッキングされているときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterDock(
    CBasePane* pBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 このパラメーターは使用されません。  
  
 [入力] `lpRect`  
 このパラメーターは使用されません。  
  
 [入力] `dockMethod`  
 このパラメーターは使用されません。  
  
##  <a name="onafterfloat"></a>  CPane::OnAfterFloat  
 ペインがフローティング状態になった後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterFloat();
```  
  
### <a name="remarks"></a>コメント  
 ペインがフローティング状態になった後にどのような処理を実行する場合は、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onbeforechangeparent"></a>  CPane::OnBeforeChangeParent  
 ウィンドウの親を変更するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pWndNewParent`  
 新しい親ウィンドウを指定します。  
  
 [入力] `bDelay`  
 `TRUE` 遅延グローバルのドッキング レイアウト調整です。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、フレームワークによってペインの親が、ウィンドウを中のための変更とドッキングまたはドッキング解除します。  
  
 既定では、ペインはドッキング ペインで登録されているを呼び出して`CDockSite::RemovePane`です。  
  
##  <a name="onbeforedock"></a>  CPane::OnBeforeDock  
 ウィンドウがドッキングするときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnBeforeDock(
    CBasePane** ppDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `ppDockBar`  
 このペインのドッキング先のウィンドウを指定します。  
  
 [入力] `lpRect`  
 ドッキングする四角形を指定します。  
  
 [入力] `dockMethod`  
 ドッキング方法を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウをドッキングすることができます。 関数を返した場合`FALSE`、ドッキングの操作は中止されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、フレームワークによってペインがドッキングされるとします。 ペインが最後にドッキングする前に、どのような処理を実行する場合は、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onbeforefloat"></a>  CPane::OnBeforeFloat  
 ペインが float 型に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectFloat`  
 フローティング状態にあるときは、ウィンドウのサイズと位置を指定します。  
  
 [入力] `dockMethod`  
 ウィンドウのドッキング方法を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウをフロートことができます。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ペインが float 型に、フレームワークによって呼び出されます。 ペインが最後に寄せて配置前に、どのような処理を実行する場合は、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onpressclosebutton"></a>  CPane::OnPressCloseButton  
 ユーザーがウィンドウのキャプションの閉じるボタンを押したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnPressCloseButton();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、フレームワークによって、ユーザーが押すと、**閉じる**ペインのキャプションのボタンをクリックします。 に関する通知を受信する、**閉じる**イベント、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onshowcontrolbarmenu"></a>  Cpane::onshowcontrolbarmenu  
 特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowControlBarMenu(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 メニューの場所を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メニューを表示できます。 場合、それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 メニューには、つまり、ウィンドウの動作を指定するいくつかの項目が含まれます:**フローティング**、**ドッキング**、**自動的に隠す**、および**を非表示に**. 呼び出してすべてのペインについては、このメニューを有効にすることができます[CDockingManager::EnableDockSiteMenu](../../mfc/reference/cdockingmanager-class.md#enabledocksitemenu)です。  
  
##  <a name="recalclayout"></a>  Cpane::recalclayout  
 ウィンドウのレイアウト情報を再計算されます。  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウがドッキングされている場合、このメソッドは、ウィンドウの現在のサイズにそのサイズを設定ウィンドウに対して仮想四角形を更新します。  
  
 ペインがフローティング状態の場合、このメソッドは、ミニフレームのサイズをウィンドウのサイズを調整するには、親ミニ フレームを通知します。 フレームワークにより、ミニフレームが少なくともウィンドウのサイズが許容される最小 ( [CPane::GetMinSize](#getminsize))、必要に応じて、ミニフレームのサイズを変更します。  
  
##  <a name="savestate"></a>  CPane::SaveState  
 レジストリにペインの状態を保存します。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイルの名前。  
  
 [入力] `nIndex`  
 プロファイルのインデックス。  
  
 [入力] `uiID`  
 ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 状態が正常に保存されている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインの状態をレジストリに保存するときに、このメソッドを呼び出します。 オーバーライド`SaveState`追加情報を格納する派生クラスでします。  
  
 このメソッドをオーバーライドする場合も、基本メソッドを呼び出すし、返す`FALSE`基本メソッドが返す場合`FALSE`です。  
  
##  <a name="setactiveingroup"></a>  Cpane::setactiveingroup  
 アクティブなウィンドウのフラグを設定します。  
  
```  
virtual void SetActiveInGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActive`  
 A`BOOL`ウィンドウをアクティブとしてにフラグが設定するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能なウィンドウが表示されるか、自動的に隠すボタンが選択された、対応するを自動的に隠すウィンドウがアクティブとしてマークされます。  
  
 ウィンドウに関連付けられている自動的に隠すボタンの外観は、2 つの要因に基づいています。 ウィンドウがアクティブな場合、`static BOOL CMFCAutoHideButton::m_bOverlappingTabs`は`TRUE`フレームワークは、アイコンとラベルとして自動的に隠すボタンを表示します。 非アクティブなウィンドウでは、フレームワークには、自動非表示のアイコンのみが表示されます。  
  
 場合`CMFCAutoHideButton::m_bOverlappingTabs`は`FALSE`、または、ウィンドウがグループにない場合は、フレームワークが、アイコンとラベルとして関連付けを自動的に隠す ボタンを表示します。  
  
##  <a name="setborders"></a>  CPane::SetBorders  
 ウィンドウの境界線の値を設定します。  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `cxLeft`  
 (ピクセル単位) ウィンドウの左罫線の幅を指定します。  
  
 [入力] `cyTop`  
 (ピクセル単位) ウィンドウの上罫線の幅を指定します。  
  
 [入力] `cxRight`  
 (ピクセル単位) ウィンドウの右罫線の幅を指定します。  
  
 [入力] `cyBottom`  
 (ピクセル単位) ウィンドウの下罫線の幅を指定します。  
  
 [入力] `lpRect`  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) (ピクセル単位) の各ウィンドウの境界線の幅を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの境界線のサイズを設定するには、この関数を呼び出します。  
  
##  <a name="setclienthotspot"></a>  CPane::SetClientHotSpot  
 セット、*ホット スポット*ペインのです。  
  
```  
void SetClientHotSpot(const CPoint& ptNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptNew`  
 A`CPoint`新しいホット スポットを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 *ホット スポット*ウィンドウで、ユーザーを選択し、ウィンドウを移動するを保持するポイントです。 ホット スポットは、ウィンドウがドッキング位置からドラッグされると、滑らかなアニメーションが使用されます。  
  
##  <a name="setdockstate"></a>  CPane::SetDockState  
 ドッキング ペインの状態情報を復元します。  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockManager`  
 メイン フレーム ウィンドウのドッキング マネージャーへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ウィンドウの最近のドッキング状態情報を復元するためにフレームワークによって呼び出されます。 ペインのドッキング状態の情報を最新の格納[:m_recentdockinfo](#m_recentdockinfo)です。 詳細については、次を参照してください。、 [CRecentDockSiteInfo クラス](../../mfc/reference/crecentdocksiteinfo-class.md)です。  
  
 外部ソースからウィンドウの情報を読み込むときに、ドッキング状態を設定するには、このメソッドを呼び出すこともできます。  
  
##  <a name="setexclusiverowmode"></a>  CPane::SetExclusiveRowMode  
 有効または排他行モードを無効にします。  
  
```  
virtual void SetExclusiveRowMode(BOOL bExclusive = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bExclusive`  
 `TRUE` 排他行モードを有効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 有効にするにまたは排他行モードを無効にするには、このメソッドを呼び出します。 ペインは、排他行モードでは、ときに、他のツールバーで、同じ行と共有ことはできません。  
  
 既定では、すべてのツールバーが排他行モードを無効にあり、メニュー バーが排他行モードを有効にします。  
  
##  <a name="setminsize"></a>  CPane::SetMinSize  
 下限のウィンドウのサイズを設定します。  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `size`  
 A`CSize`下限のウィンドウのサイズを含むオブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setvirtualrect"></a>  CPane::SetVirtualRect  
 セット、*仮想の長方形*ウィンドウのです。  
  
```  
void SetVirtualRect(
    const CRect& rect,  
    BOOL bMapToParent = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 A`CRect`を設定する仮想四角形を指定するオブジェクト。  
  
 [入力] `bMapToParent`  
 指定`TRUE`場合`rect`親ウィンドウの基準とした点が含まれています。  
  
### <a name="remarks"></a>コメント  
 A*仮想の長方形*が移動されると、ウィンドウの元の位置を格納します。 フレームワークは、仮想の長方形を使用して、元の位置を復元できます。  
  
 ウィンドウをプログラムで移動する場合を除き、仮想四角形に関連するメソッドを呼び出す必要はありません。  
  
##  <a name="setminiframertc"></a>  CPane::SetMiniFrameRTC  
 既定のミニフレーム ウィンドウのランタイム クラス情報を設定します。  
  
```  
void SetMiniFrameRTC(CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pClass`  
 ミニフレーム ウィンドウのランタイム クラス情報を指定します。  
  
### <a name="remarks"></a>コメント  
 登録されますペインがフローティング状態になった、 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) (ミニフレーム) ウィンドウです。 カスタムを指定することができます`CPaneFrameWnd`-となるクラスを派生する場合に使用[cpane::createdefaultminiframe](#createdefaultminiframe)と呼びます。  
  
##  <a name="stretchpanedeferwndpos"></a>  CPane::StretchPaneDeferWndPos  
 垂直または水平にドッキング スタイルに基づいてウィンドウを拡大します。  
  
```  
virtual int StretchPaneDeferWndPos(
    int nStretchSize,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nStretchSize`  
 (ピクセル単位) をウィンドウの拡張量。 ウィンドウを縮小するのにには、負の値を使用します。  
  
 [入力] `hdwp`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 実際の量 (ピクセル単位) のウィンドウがストレッチされたことです。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、このメソッドによって`nStretchSize`をウィンドウ サイズの制限を超えていないことを確認します。 これらの制限が呼び出すことによって取得された[CPane::GetAvailableStretchSize](#getavailablestretchsize)と[CPane::GetAvailableExpandSize](#getavailableexpandsize)です。  
  
##  <a name="toggleautohide"></a>  CPane::ToggleAutoHide  
 自動非表示モードを切り替えます。  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>コメント  
 自動非表示モードを切り替えるには、このメソッドを呼び出します。 ペインは、自動非表示モードを切り替えるにはメイン フレーム ウィンドウにドッキングする必要があります。  
  
##  <a name="undockpane"></a>  CPane::UndockPane  
 ドッキング サイト、既定のスライダーまたはミニフレーム ウィンドウの現在のドッキング位置から、ウィンドウを削除します。  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDelay`  
 場合`FALSE`、フレームワークによって[cbasepane::adjustdockinglayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout)ドッキング レイアウトを調整します。  
  
### <a name="remarks"></a>コメント  
 プログラムでウィンドウをドッキングを解除するのにには、このメソッドを使用します。  
  
##  <a name="updatevirtualrect"></a>  CPane::UpdateVirtualRect  
 仮想の長方形を更新します。  
  
```  
void UpdateVirtualRect();  
void UpdateVirtualRect(CPoint ptOffset);  
  void UpdateVirtualRect(CSize sizeNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptOffset`  
 A`CPoint`をウィンドウをシフトするオフセットを指定するオブジェクト。  
  
 [入力] `sizeNew`  
 A`CSize`ウィンドウの新しいサイズを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のオーバー ロードは、現在の位置と、ウィンドウのサイズを使用して仮想の長方形を設定します。  
  
 2 番目のオーバー ロードでは、仮想の長方形をシフトで指定された量だけ`ptOffset`です。  
  
 3 番目のオーバー ロードでは、仮想の四角形を設定、ペインとで指定されたサイズの現在の位置を使用して、`sizeNew`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)
