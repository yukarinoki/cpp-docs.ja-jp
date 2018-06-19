---
title: CDockablePane クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockablePane
- AFXDOCKABLEPANE/CDockablePane
- AFXDOCKABLEPANE/CDockablePane::CDockablePane
- AFXDOCKABLEPANE/CDockablePane::AttachToTabWnd
- AFXDOCKABLEPANE/CDockablePane::CalcFixedLayout
- AFXDOCKABLEPANE/CDockablePane::CanAcceptMiniFrame
- AFXDOCKABLEPANE/CDockablePane::CanAcceptPane
- AFXDOCKABLEPANE/CDockablePane::CanAutoHide
- AFXDOCKABLEPANE/CDockablePane::CanBeAttached
- AFXDOCKABLEPANE/CDockablePane::ConvertToTabbedDocument
- AFXDOCKABLEPANE/CDockablePane::CopyState
- AFXDOCKABLEPANE/CDockablePane::Create
- AFXDOCKABLEPANE/CDockablePane::CreateDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::CreateEx
- AFXDOCKABLEPANE/CDockablePane::CreateTabbedPane
- AFXDOCKABLEPANE/CDockablePane::DockPaneContainer
- AFXDOCKABLEPANE/CDockablePane::DockPaneStandard
- AFXDOCKABLEPANE/CDockablePane::DockToRecentPos
- AFXDOCKABLEPANE/CDockablePane::DockToWindow
- AFXDOCKABLEPANE/CDockablePane::EnableAutohideAll
- AFXDOCKABLEPANE/CDockablePane::EnableGripper
- AFXDOCKABLEPANE/CDockablePane::GetAHRestoredRect
- AFXDOCKABLEPANE/CDockablePane::GetAHSlideMode
- AFXDOCKABLEPANE/CDockablePane::GetCaptionHeight
- AFXDOCKABLEPANE/CDockablePane::GetDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::GetDockingStatus
- AFXDOCKABLEPANE/CDockablePane::GetDragSensitivity
- AFXDOCKABLEPANE/CDockablePane::GetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::GetTabArea
- AFXDOCKABLEPANE/CDockablePane::GetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::HasAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::HitTest
- AFXDOCKABLEPANE/CDockablePane::IsAutohideAllEnabled
- AFXDOCKABLEPANE/CDockablePane::IsAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsDocked
- AFXDOCKABLEPANE/CDockablePane::IsHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsInFloatingMultiPaneFrameWnd
- AFXDOCKABLEPANE/CDockablePane::IsResizable
- AFXDOCKABLEPANE/CDockablePane::IsTabLocationBottom
- AFXDOCKABLEPANE/CDockablePane::IsTracked
- AFXDOCKABLEPANE/CDockablePane::IsVisible
- AFXDOCKABLEPANE/CDockablePane::OnAfterChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnAfterDockFromMiniFrame
- AFXDOCKABLEPANE/CDockablePane::OnBeforeChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnBeforeFloat
- AFXDOCKABLEPANE/CDockablePane::RemoveFromDefaultPaneDividier
- AFXDOCKABLEPANE/CDockablePane::ReplacePane
- AFXDOCKABLEPANE/CDockablePane::RestoreDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideParents
- AFXDOCKABLEPANE/CDockablePane::SetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::SetRestoredDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::ShowPane
- AFXDOCKABLEPANE/CDockablePane::Slide
- AFXDOCKABLEPANE/CDockablePane::ToggleAutoHide
- AFXDOCKABLEPANE/CDockablePane::UndockPane
- AFXDOCKABLEPANE/CDockablePane::CheckAutoHideCondition
- AFXDOCKABLEPANE/CDockablePane::CheckStopSlideCondition
- AFXDOCKABLEPANE/CDockablePane::DrawCaption
- AFXDOCKABLEPANE/CDockablePane::OnPressButtons
- AFXDOCKABLEPANE/CDockablePane::OnSlide
- AFXDOCKABLEPANE/CDockablePane::m_bDisableAnimation
- AFXDOCKABLEPANE/CDockablePane::m_bHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::m_nSlideSteps
dev_langs:
- C++
helpviewer_keywords:
- CDockablePane [MFC], CDockablePane
- CDockablePane [MFC], AttachToTabWnd
- CDockablePane [MFC], CalcFixedLayout
- CDockablePane [MFC], CanAcceptMiniFrame
- CDockablePane [MFC], CanAcceptPane
- CDockablePane [MFC], CanAutoHide
- CDockablePane [MFC], CanBeAttached
- CDockablePane [MFC], ConvertToTabbedDocument
- CDockablePane [MFC], CopyState
- CDockablePane [MFC], Create
- CDockablePane [MFC], CreateDefaultPaneDivider
- CDockablePane [MFC], CreateEx
- CDockablePane [MFC], CreateTabbedPane
- CDockablePane [MFC], DockPaneContainer
- CDockablePane [MFC], DockPaneStandard
- CDockablePane [MFC], DockToRecentPos
- CDockablePane [MFC], DockToWindow
- CDockablePane [MFC], EnableAutohideAll
- CDockablePane [MFC], EnableGripper
- CDockablePane [MFC], GetAHRestoredRect
- CDockablePane [MFC], GetAHSlideMode
- CDockablePane [MFC], GetCaptionHeight
- CDockablePane [MFC], GetDefaultPaneDivider
- CDockablePane [MFC], GetDockingStatus
- CDockablePane [MFC], GetDragSensitivity
- CDockablePane [MFC], GetLastPercentInPaneContainer
- CDockablePane [MFC], GetTabArea
- CDockablePane [MFC], GetTabbedPaneRTC
- CDockablePane [MFC], HasAutoHideMode
- CDockablePane [MFC], HitTest
- CDockablePane [MFC], IsAutohideAllEnabled
- CDockablePane [MFC], IsAutoHideMode
- CDockablePane [MFC], IsDocked
- CDockablePane [MFC], IsHideInAutoHideMode
- CDockablePane [MFC], IsInFloatingMultiPaneFrameWnd
- CDockablePane [MFC], IsResizable
- CDockablePane [MFC], IsTabLocationBottom
- CDockablePane [MFC], IsTracked
- CDockablePane [MFC], IsVisible
- CDockablePane [MFC], OnAfterChangeParent
- CDockablePane [MFC], OnAfterDockFromMiniFrame
- CDockablePane [MFC], OnBeforeChangeParent
- CDockablePane [MFC], OnBeforeFloat
- CDockablePane [MFC], RemoveFromDefaultPaneDividier
- CDockablePane [MFC], ReplacePane
- CDockablePane [MFC], RestoreDefaultPaneDivider
- CDockablePane [MFC], SetAutoHideMode
- CDockablePane [MFC], SetAutoHideParents
- CDockablePane [MFC], SetLastPercentInPaneContainer
- CDockablePane [MFC], SetRestoredDefaultPaneDivider
- CDockablePane [MFC], SetTabbedPaneRTC
- CDockablePane [MFC], ShowPane
- CDockablePane [MFC], Slide
- CDockablePane [MFC], ToggleAutoHide
- CDockablePane [MFC], UndockPane
- CDockablePane [MFC], CheckAutoHideCondition
- CDockablePane [MFC], CheckStopSlideCondition
- CDockablePane [MFC], DrawCaption
- CDockablePane [MFC], OnPressButtons
- CDockablePane [MFC], OnSlide
- CDockablePane [MFC], m_bDisableAnimation
- CDockablePane [MFC], m_bHideInAutoHideMode
- CDockablePane [MFC], m_nSlideSteps
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0b00c40ded45d1d71b42c126e2461c404eb5223
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378801"
---
# <a name="cdockablepane-class"></a>CDockablePane Class
ドッキング サイトにドッキングできる、またはタブ付きペインに含めることができるペインを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDockablePane : public CPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDockablePane::CDockablePane](#cdockablepane)|`CDockablePane` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Cdockablepane::attachtotabwnd](#attachtotabwnd)|ペインを別のペインにアタッチします。 これには、タブ付きペインが作成されます。|  
|[CDockablePane::CalcFixedLayout](#calcfixedlayout)|ペインの四角形のサイズを返します。|  
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|指定ミニフレーム ウィンドウにドッキングできるかどうかを判断します。|  
|[CDockablePane::CanAcceptPane](#canacceptpane)|現在のウィンドウに別のペインをドッキングできるかどうかを判断します。|  
|[CDockablePane::CanAutoHide](#canautohide)|ペインが自動的に隠すモードをサポートするかどうかを判断します。 (上書き[CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide))。|  
|[CDockablePane::CanBeAttached](#canbeattached)|現在のウィンドウを別のペインにドッキングできるかどうかを判断します。|  
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|1 つまたは複数のドッキング可能ペインを MDI タブ付きドキュメントに変換します。|  
|[CDockablePane::CopyState](#copystate)|ドッキング可能なウィンドウの状態をコピーします。|  
|[CDockablePane::Create](#create)|Windows コントロールを作成し、それにアタッチ、`CDockablePane`オブジェクト。|  
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|フレーム ウィンドウにドッキングされているウィンドウの既定の区分線を作成します。|  
|[Cdockablepane::createex](#createex)|Windows コントロールを作成し、それにアタッチ、`CDockablePane`オブジェクト。|  
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|現在のウィンドウからタブ付きペインを作成します。|  
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|ペインに、コンテナーにドッキングします。|  
|[CDockablePane::DockPaneStandard](#dockpanestandard)|アウトライン (標準) のドッキングを使用して、ウィンドウをドッキングします。|  
|`CDockablePane::DockToFrameWindow`|内部的に使用します。 ペインをドッキングするには、使用[CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)または[CDockablePane::DockToWindow](#docktowindow)です。|  
|[CDockablePane::DockToRecentPos](#docktorecentpos)|その格納されている最新のドッキング位置をペインをドッキングします。|  
|[CDockablePane::DockToWindow](#docktowindow)|別のドッキング ペインには、1 つのドッキング ペインをドッキングします。|  
|[CDockablePane::EnableAutohideAll](#enableautohideall)|有効またはコンテナー内の他のウィンドウと共にこのペインの自動非表示モードを無効にします。|  
|[CDockablePane::EnableGripper](#enablegripper)|キャプション (グリップ) の表示と非表示を切り替えます。|  
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|自動非表示モードで表示されているときにウィンドウの位置を指定します。|  
|[CDockablePane::GetAHSlideMode](#getahslidemode)|ウィンドウの自動非表示のスライド ショー モードを取得します。|  
|`CDockablePane::GetAutoHideButton`|内部的に使用します。|  
|`CDockablePane::GetAutoHideToolBar`|内部的に使用します。|  
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|現在のキャプションの高さを返します。|  
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|ペインのコンテナーの既定ペイン分割バーを返します。|  
|[CDockablePane::GetDockingStatus](#getdockingstatus)|指定されたポインターの位置に基づいて、ドッキング ペインの機能を決定します。|  
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|ドッキング ウィンドウのドラッグと小文字の区別を返します。|  
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|ペインをそのコンテナー内で占有する領域の割合を取得します。|  
|[CDockablePane::GetTabArea](#gettabarea)|ウィンドウのタブ領域を取得します。|  
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|現在のウィンドウを別のペインをドッキング時に作成されるタブ付きウィンドウに関するランタイム クラス情報を返します。|  
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|ドッキング ペインを自動的に隠すモードに切り替えることができるかどうかを指定します。|  
|[CDockablePane::HitTest](#hittest)|ユーザーがマウスをクリックしたウィンドウで特定の場所を指定します。|  
|`CDockablePane::IsAccessibilityCompatible`|内部的に使用します。|  
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|ドッキング ペインと、コンテナー内の他のすべてのウィンドウを自動的に隠すモードで配置できるかどうかを示します。|  
|[CDockablePane::IsAutoHideMode](#isautohidemode)|ペインが自動的に隠すモードかどうかを判断します。|  
|`CDockablePane::IsChangeState`|内部的に使用します。|  
|[CDockablePane::IsDocked](#isdocked)|現在のウィンドウがドッキングされているかどうかを判断します。|  
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|場合はそれを示すように (または非表示) を呼び出して、自動非表示モードになっているウィンドウの動作を決定`ShowPane`です。|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|複数のウィンドウ フレーム ウィンドウのウィンドウがかどうかを指定します。|  
|[CDockablePane::IsResizable](#isresizable)|そのウィンドウはサイズを変更できるかどうかを指定します。|  
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|タブが上部またはウィンドウの下部にあるかどうかを指定します。|  
|[CDockablePane::IsTracked](#istracked)|ユーザーが、ウィンドウがドラッグされているかどうかを指定します。|  
|[CDockablePane::IsVisible](#isvisible)|現在のウィンドウが表示されているかどうかを判断します。|  
|[Cdockablepane::loadstate](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917)|内部的に使用します。|  
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|ウィンドウの親が変更されたときに、フレームワークによって呼び出されます。 (上書き[CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent))。|  
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|フレーム ウィンドウのフローティング、ドッキング バーをドッキングすると、フレームワークによって呼び出されます。|  
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|ウィンドウの親を変更するときに、フレームワークによって呼び出されます。 (上書き[CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent))。|  
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|ペインが float 型に、フレームワークによって呼び出されます。 (上書き[CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat))。|  
|[CDockablePane::RemoveFromDefaultPaneDividier](#removefromdefaultpanedividier)|フレームワークは、ペインのドッキングを解除中にこのメソッドを呼び出します。|  
|[CDockablePane::ReplacePane](#replacepane)|指定したウィンドウで、ウィンドウを置き換えます。|  
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|フレームワークは、ペインが既定ペイン分割バーを復元する逆シリアル化と、このメソッドを呼び出します。|  
|`CDockablePane::SaveState`|内部的に使用します。|  
|`CDockablePane::Serialize`|ペインをシリアル化します。 (`CBasePane::Serialize` をオーバーライドします)。|  
|[CDockablePane::SetAutoHideMode](#setautohidemode)|ドッキング ペインの表示を切り替えると、自動非表示モード。|  
|[CDockablePane::SetAutoHideParents](#setautohideparents)|自動的に隠すボタンのウィンドウを自動的に隠すツールバーを設定します。|  
|`CDockablePane::SetDefaultPaneDivider`|内部的に使用します。|  
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|ペインをそのコンテナー内で占有する領域の割合を設定します。|  
|`CDockablePane::SetResizeMode`|内部的に使用します。|  
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|復元された既定の分割線を設定します。|  
|[:Settabbedpanertc](#settabbedpanertc)|2 つのペインがドッキング時に作成されるタブ付きウィンドウのランタイム クラス情報を設定します。|  
|[CDockablePane::ShowPane](#showpane)|ペインの表示と非表示を切り替えます。|  
|[CDockablePane::Slide](#slide)|ウィンドウが自動非表示モードの場合にのみを表示するスライド アニメーションが表示されるウィンドウの表示と非表示を切り替えます。|  
|[CDockablePane::ToggleAutoHide](#toggleautohide)|自動非表示モードを切り替えます。 (上書き[CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) )。|  
|[CDockablePane::UndockPane](#undockpane)|メイン フレーム ウィンドウまたはミニフレーム ウィンドウのコンテナーのいずれかからペインのドッキングを解除します。|  
|`CDockablePane::UnSetAutoHideMode`|内部的に使用します。 自動非表示モードを設定するには、使用[CDockablePane::SetAutoHideMode](#setautohidemode)|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|(自動的に隠すモード) では、ドッキング ウィンドウが非表示かどうかを判断します。|  
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|ときに自動的に隠すドッキング ウィンドウがスライディングを停止する必要がありますを決定します。|  
|[CDockablePane::DrawCaption](#drawcaption)|ドッキング ウィンドウのキャプション (グリップ) を描画します。|  
|[CDockablePane::OnPressButtons](#onpressbuttons)|ボタンを押す、キャプション以外のときに呼び出されます、`AFX_HTCLOSE`と`AFX_HTMAXBUTTON`ボタン。|  
|[CDockablePane::OnSlide](#onslide)|ウィンドウが表示または非表示時に自動的に隠すスライド効果を表示するためにフレームワークによって呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|ドッキング可能なウィンドウの自動非表示のアニメーションが無効になっているかどうかを指定します。|  
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|ウィンドウが自動非表示モードの場合は、ウィンドウの動作を決定します。|  
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|されているときに、ウィンドウのアニメーションの速度を指定または自動非表示モードのときに非表示を表示します。|  
  
## <a name="remarks"></a>コメント  
 `CDockablePane` 次の機能を実装します。  
  
-   メイン フレーム ウィンドウに、ウィンドウをドッキングします。  
  
-   ウィンドウを自動非表示モードに切り替えます。  
  
-   ペインをタブ付きウィンドウにアタッチします。  
  
-   ミニフレーム ウィンドウのペインをフローティングです。  
  
-   フローティング ミニフレーム ウィンドウで別のペインに、ウィンドウをドッキングします。  
  
-   ペインのサイズを変更します。  
  
-   読み込み、ドッキング ペインの状態を保存します。  
  
    > [!NOTE]
    >  状態情報は、Windows レジストリに保存されます。  
  
-   キャプションの有無は、ウィンドウを作成します。 キャプション テキスト ラベルを持つことができ、グラデーションの色を指定できます。  
  
-   ウィンドウの内容を表示するときに、ウィンドウをドラッグします。  
  
-   ドラッグ四角形の表示中にウィンドウをドラッグします。  
  
 使用するにはドッキング ペイン、アプリケーションで、ウィンドウ クラスを派生させから、`CDockablePane`クラスです。 メイン フレーム ウィンドウ オブジェクトや、ウィンドウのインスタンスを制御するウィンドウのオブジェクトに、派生オブジェクトを埋め込むか。 まず、 [CDockablePane::Create](#create)メソッドまたは[cdockablepane::createex](#createex)メソッドを処理するとき、`WM_CREATE`メイン フレーム ウィンドウ内のメッセージ。 呼び出して、ウィンドウのオブジェクトを最後に、セットアップ[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)、 [cbasepane::dockpane](../../mfc/reference/cbasepane-class.md#dockpane)、または[cdockablepane::attachtotabwnd](#attachtotabwnd)です。  
  
## <a name="customization-tips"></a>カスタマイズのヒント  
 次のヒントを適用する`CDockablePane`オブジェクト。  
  
-   呼び出す場合[cdockablepane::attachtotabwnd](#attachtotabwnd)で 2 つのタブ付き以外、ドッキング可能なウィンドウのタブ付きウィンドウへのポインターが返されます、`ppTabbedControlBar`パラメーター。 このパラメーターを使用してタブ付きウィンドウにタブを追加する続行することができます。  
  
-   によって作成されるタブ付きウィンドウの種類[cdockablepane::attachtotabwnd](#attachtotabwnd)によって決定されます、`CDockablePane`内のオブジェクト、`pTabControlBarAttachTo`パラメーター。 呼び出すことができます[:settabbedpanertc](#settabbedpanertc)にタブ付きウィンドウの種類を設定、`CDockablePane`が作成されます。 既定値の型によって決定されます、`dwTabbedStyle`の[CDockablePane::Create](#create)作成する場合、`CDockablePane`です。 場合`dwTabbedStyle`は、既定の種類は AFX_CBRS_OUTLOOK_TABS [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)以外の場合は`dwTabbedStyle`は、既定の種類は AFX_CBRS_REGULAR_TABS[派生クラス](../../mfc/reference/ctabbedpane-class.md)です。  
  
-   別の 1 つのドッキング可能なペインをドッキングする場合は、呼び出し、 [CDockablePane::DockToWindow](#docktowindow)メソッドです。 元のウィンドウ ドッキングされていなければなりませんの場所にこのメソッドを呼び出す前にします。  
  
-   メンバー変数[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)コントロール ドッキング可能なウィンドウの動作を自動でどのように非表示モードを呼び出すと[CDockablePane::ShowPane](#showpane)です。 このメンバー変数に設定されている場合`TRUE`、ドッキング可能ペインと、自動非表示ボタンは表示されません。 それ以外の場合、それらはスライドします。  
  
-   設定して自動的に隠すアニメーションを無効にすることができます、 [CDockablePane::m_bDisableAnimation](#m_bdisableanimation)メンバー変数を`TRUE`です。  
  
## <a name="example"></a>例  
 次の例は、構成する方法を示します、`CDockablePane`オブジェクトのさまざまなメソッドを使用して、`CDockablePane`クラスです。 この例を自動的に隠す、ドッキング可能なウィンドウのすべての機能を有効にする、キャプションまたはグリップを有効にする、自動非表示モードを有効にする、ウィンドウを表示および自動非表示モードになっているウィンドウのアニメーション化する方法を示します。 このコード スニペットの一部である、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#27](../../mfc/codesnippet/cpp/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#28](../../mfc/codesnippet/cpp/cdockablepane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxDockablePane.h  
  
##  <a name="attachtotabwnd"></a>  Cdockablepane::attachtotabwnd  
 現在のウィンドウをタブ付きペインを作成するターゲット ウィンドウにアタッチします。  
  
```  
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bSetActive= TRUE,  
    CDockablePane** ppTabbedControlBar = NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pTabControlBarAttachTo`  
 現在のウィンドウにアタッチする、ターゲット ウィンドウを指定します。 対象のペインには、ドッキング可能ペインをする必要があります。  
  
 [入力] `dockMethod`  
 ドッキング方法を指定します。  
  
 [入力] `bSetActive`  
 `TRUE` アタッチ操作後に、タブ付きウィンドウをアクティブ化するにはそれ以外の場合、`FALSE`です。  
  
 [出力] `ppTabbedControlBar`  
 タブ付きウィンドウ、アタッチ操作を実行した結果が含まれています。  
  
### <a name="return-value"></a>戻り値  
 現在のウィンドウがない場合は、タブ付きペインへのポインターそれ以外の場合、アタッチ操作を実行した結果、タブ付きペインへのポインター。 戻り値は`NULL`現在のウィンドウをアタッチすることはできません、またはエラーが発生した場合。  
  
### <a name="remarks"></a>コメント  
 1 つのドッキング可能なペインは、このメソッドを使用して別のペインに関連付ける、ときに、以下の処理が行われます。  
  
1.  Framework チェックするかどうかターゲット ウィンドウ`pTabControlBarAttachTo`は、通常のドッキング ウィンドウまたはかどうかから派生[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)です。  
  
2.  ターゲット ウィンドウがタブ付きペインは、フレームワークによって、現在のウィンドウにタブとして追加します。  
  
3.  対象のペインでは、標準のドッキング ペインは、フレームワークはタブ付きペインを作成します。  
  
    -   フレームワークによって`pTabControlBarAttachTo->CreateTabbedPane`です。 新しいタブ付きウィンドウのスタイルは異なります、`m_pTabbedControlBarRTC`メンバー。 既定では、このメンバーのランタイム クラスに設定[派生](../../mfc/reference/ctabbedpane-class.md)です。 渡す場合、`AFX_CBRS_OUTLOOK_TABS`スタイルとして、`dwTabbedStyle`パラメーターを[CDockablePane::Create](#create)方法、ランタイム クラスのオブジェクトは、のランタイム クラスに設定されて[CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)です。 このメンバーは、新しいウィンドウのスタイルを変更するには、いつでも変更できます。  
  
    -   フレームワークがへのポインターを置き換えるときに、このメソッドは、タブ付きペインを作成し、 `pTabControlBarAttachTo` (かどうか、ウィンドウがドッキングまたはフローティング マルチ ミニフレーム ウィンドウで) 新しいタブ付きペインへのポインター。  
  
    -   フレームワークは、追加、`pTabControlBarAttachTo`最初のタブとしてタブ付きペインにウィンドウです。フレームワークは、2 番目のタブとして、現在のウィンドウを追加します。  
  
4.  現在のウィンドウがから派生している場合`CBaseTabbedPane`、すべてのタブに移動`pTabControlBarAttachTo`と現在のウィンドウが破棄されます。 そのため、注意するこのメソッドを呼び出すと、メソッドが戻るときに現在ペインへのポインターが有効になる可能性があるため。  
  
 ドッキング レイアウトを構築するときに別の 1 つのペインをアタッチする場合は、設定`dockMethod`に`DM_SHOW`です。  
  
 別のペインを添付する前に、最初のペインをドッキングする必要があります。  
  
##  <a name="calcfixedlayout"></a>  CDockablePane::CalcFixedLayout  
 ペインの四角形のサイズを返します。  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bStretch`  
 使用しません。  
  
 [入力] `bHorz`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 A`CSize`ペインの四角形のサイズを含むオブジェクトです。  
  
##  <a name="canacceptminiframe"></a>  CDockablePane::CanAcceptMiniFrame  
 指定ミニフレーム ウィンドウにドッキングできるかどうかを判断します。  
  
```  
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMiniFrame`  
 ポインター、`CPaneFrameWnd`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合`pMiniFrame`、それ以外のウィンドウにドッキング`FALSE`です。  
  
##  <a name="canacceptpane"></a>  CDockablePane::CanAcceptPane  
 現在のウィンドウに別のペインをドッキングできるかどうかを判断します。  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 現在のウィンドウにドッキングするウィンドウを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 指定されたウィンドウですこのペインをドッキングできる場合。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインが現在のウィンドウにドッキングされる前に、このメソッドを呼び出します。  
  
 この関数を有効にするか、特定のペインをドッキングは無効にする派生クラスでオーバーライドします。  
  
 既定では、このメソッドが戻る`TRUE`場合`pBar`か、またはその親が型`CDockablePane`です。  
  
##  <a name="canautohide"></a>  CDockablePane::CanAutoHide  
 かどうかのウィンドウが自動非表示を決定します。  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウが自動非表示場合、です。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 `CDockablePane::CanAutoHide` 返します`FALSE`で次のような場合。  
  
-   ウィンドウには、親がありません。  
  
-   ドッキング マネージャーでは、自動的に隠すウィンドウは許可されません。  
  
-   ウィンドウがドッキングされていません。  
  
##  <a name="canbeattached"></a>  CDockablePane::CanBeAttached  
 現在のウィンドウを別のペインにドッキングできるかどうかを判断します。  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 別のペインに、またはメイン フレーム ウィンドウにドッキング可能ペインをドッキングできる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは常`TRUE`です。 このメソッドを有効または無効に呼び出さずにドッキングする派生クラスでオーバーライド[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)です。  
  
##  <a name="cdockablepane"></a>  CDockablePane::CDockablePane  
 構築して初期化、 [CDockablePane](../../mfc/reference/cdockablepane-class.md)オブジェクト。  
  
```  
CDockablePane();
```  
  
### <a name="remarks"></a>コメント  
 ドッキング可能なウィンドウのオブジェクトを構築した後で呼び出す[CDockablePane::Create](#create)または[cdockablepane::createex](#createex)を作成します。  
  
##  <a name="converttotabbeddocument"></a>  CDockablePane::ConvertToTabbedDocument  
 1 つまたは複数のドッキング可能ペインを MDI タブ付きドキュメントに変換します。  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActiveTabOnly`  
 変換する際に、 `CTabbedPane`、指定`TRUE`にアクティブなタブのみを変換します。指定`FALSE`ペイン内のすべてのタブに変換します。  
  
##  <a name="checkautohidecondition"></a>  CDockablePane::CheckAutoHideCondition  
 (自動非表示モードとも呼ばれます) のドッキング ウィンドウが非表示かどうかを判断します。  
  
```  
virtual BOOL CheckAutoHideCondition();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 非表示にする条件を満たした場合場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、タイマーを使用して、定期的に自動非表示のドッキング可能ウィンドウを非表示にするかどうかを確認します。 このメソッドを返します`TRUE`と、ウィンドウがアクティブでないのウィンドウ サイズを変更できませんが、ウィンドウ上にマウス ポインターがありません。  
  
 以前のすべての条件が満たされた場合、フレームワークによって呼び出されます[CDockablePane::Slide](#slide)ウィンドウを非表示にします。  
  
##  <a name="checkstopslidecondition"></a>  CDockablePane::CheckStopSlideCondition  
 ときに自動的に隠すドッキング ウィンドウがスライディングを停止する必要がありますを決定します。  
  
```  
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDirection`  
 `TRUE` ペインが表示されている場合`FALSE`ウィンドウが表示されていない場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は停止状態になっています。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能なウィンドウが自動的に隠すモードに設定されている場合、フレームワークは、ウィンドウを非表示のスライド効果を使用します。 フレームワークは、ペインがスライドときに、この関数を呼び出します。 `CheckStopSlideCondition` 返します`TRUE`ウィンドウが完全に表示されているとき、またはと完全に非表示にされています。  
  
 カスタム自動非表示の効果を実装する派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="copystate"></a>  CDockablePane::CopyState  
 ドッキング可能なウィンドウの状態をコピーします。  
  
```  
virtual void CopyState(CDockablePane* pOrgBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOrgBar`  
 ドッキング可能ペインへのポインター。  
  
### <a name="remarks"></a>コメント  
 `CDockablePane::CopyState` 状態をコピー`pOrgBar`次のメソッドを呼び出すことによって現在のペインに。  
  
- [CPane::CopyState](../../mfc/reference/cpane-class.md#copystate)  
  
- [CDockablePane::GetAHRestoredRect](#getahrestoredrect)  
  
- [CDockablePane::GetAHSlideMode](#getahslidemode)  
  
- [CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)  
  
- [CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)  
  
##  <a name="create"></a>  CDockablePane::Create  
 Windows コントロールを作成し、それにアタッチ、 [CDockablePane](../../mfc/reference/cdockablepane-class.md)オブジェクト。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);

 
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    CSize sizeDefault,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle = WS_CHILD|WS_VISIBLE|CBRS_TOP|CBRS_HIDE_INPLACE,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszCaption`  
 ウィンドウの名前を指定します。  
  
 [in][out] `pParentWnd`  
 親ウィンドウを指定します。  
  
 [入力] `rect`  
 クライアント座標で、ウィンドウの位置とサイズを指定`pParentWnd`です。  
  
 [入力] `bHasGripper`  
 `TRUE` キャプション付きのウィンドウを作成するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `nID`  
 子ウィンドウの ID を指定します。 この値は、このドッキング ウィンドウのドッキング状態を保存する場合は、一意でなければなりません。  
  
 [入力] `dwStyle`  
 ウィンドウのスタイル属性を指定します。  
  
 [入力] `dwTabbedStyle`  
 ユーザーは、このウィンドウのキャプションのペインをドラッグしたときに作成されるタブ付きウィンドウのタブ付きのスタイルを指定します。  
  
 [入力] `dwControlBarStyle`  
 追加のスタイル属性を指定します。  
  
 [in][out] `pContext`  
 ウィンドウの作成のコンテキストを指定します。  
  
 [入力] `lpszWindowName`  
 ウィンドウの名前を指定します。  
  
 [入力] `sizeDefault`  
 ウィンドウのサイズを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング可能ペインは正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 Windows ウィンドウを作成し、それにアタッチ、`CDockablePane`オブジェクト。  
  
 場合、`dwStyle`ウィンドウ スタイルが、`CBRS_FLOAT_MULTI`フラグ、ミニフレーム ウィンドウをミニフレーム ウィンドウの他のペインをフローティングできます。 既定では、ドッキング ペインだけをフローティングできる個別にします。  
  
 場合、`dwTabbedStyle`パラメーターには、`AFX_CBRS_OUTLOOK_TABS`フラグが指定されて、このペインを使用する別のペインが関連付けられている場合、ペインを Outlook スタイルのタブ付きウィンドウを作成、 [cdockablepane::attachtotabwnd](#attachtotabwnd)メソッドです。 既定では、ドッキング可能ペインは型の通常のタブ付きペインを作成する[派生](../../mfc/reference/ctabbedpane-class.md)です。  
  
##  <a name="createdefaultpanedivider"></a>  CDockablePane::CreateDefaultPaneDivider  
 フレーム ウィンドウにドッキングされているウィンドウの既定の区分線を作成します。  
  
```  
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,  
    CWnd* pParent,  
    CRuntimeClass* pSliderRTC = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 ペインをドッキングするメイン フレームの辺を指定します。 場合`dwAlignment`が含まれています、`CBRS_ALIGN_LEFT`または`CBRS_ALIGN_RIGHT`フラグは、このメソッドを作成、垂直方向 ( `CPaneDivider::SS_VERT`) 区切りです。 それ以外の場合、このメソッドは、水平方向を作成 ( `CPaneDivider::SS_HORZ`) 区分線。  
  
 [入力] `pParent`  
 親フレームへのポインター。  
  
 [入力] `pSliderRTC`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが、新しく作成された区分線へのポインターを返しますまたは`NULL`区分線の作成が失敗した場合。  
  
### <a name="remarks"></a>コメント  
 `dwAlignment` 値は次のいずれかを指定できます。  
  
|[値]|説明|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|ウィンドウ フレーム ウィンドウのクライアント領域の上部にドッキングします。|  
|`CBRS_ALIGN_BOTTOM`|ウィンドウ フレーム ウィンドウのクライアント領域の下部にドッキングします。|  
|`CBRS_ALIGN_LEFT`|ウィンドウ フレーム ウィンドウのクライアント領域の左側にドッキングします。|  
|`CBRS_ALIGN_RIGHT`|ウィンドウ フレーム ウィンドウのクライアント領域の右側にドッキングします。|  
  
##  <a name="createex"></a>  Cdockablepane::createex  
 Windows コントロールを作成し、それにアタッチ、 [CDockablePane](../../mfc/reference/cdockablepane-class.md)オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyleEx`  
 新しいウィンドウの拡張スタイル属性を指定します。  
  
 [入力] `lpszCaption`  
 ウィンドウの名前を指定します。  
  
 [in][out] `pParentWnd`  
 親ウィンドウを指定します。  
  
 [入力] `rect`  
 クライアント座標で、ウィンドウの位置とサイズを指定`pParentWnd`です。  
  
 [入力] `bHasGripper`  
 `TRUE` キャプション付きのウィンドウを作成するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `nID`  
 子ウィンドウの ID を指定します。 この値は、このドッキング ウィンドウのドッキング状態を保存する場合は一意である必要があります。  
  
 [入力] `dwStyle`  
 ウィンドウのスタイル属性を指定します。  
  
 [入力] `dwTabbedStyle`  
 ユーザーは、このウィンドウのキャプションのペインをドラッグしたときに作成されるタブ付きウィンドウのタブ付きのスタイルを指定します。  
  
 [入力] `dwControlBarStyle`  
 追加のスタイル属性を指定します。  
  
 [in][out] `pContext`  
 ウィンドウの作成のコンテキストを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング可能ペインは正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 Windows ウィンドウを作成し、それにアタッチ、`CDockablePane`オブジェクト。  
  
 場合、`dwStyle`ウィンドウ スタイルが、`CBRS_FLOAT_MULTI`フラグ、ミニフレーム ウィンドウをミニフレーム ウィンドウの他のペインをフローティングできます。 既定では、ドッキング ペインだけをフローティングできる個別にします。  
  
 場合、`dwTabbedStyle`パラメーターには、`AFX_CBRS_OUTLOOK_TABS`フラグが指定されて、このペインを使用する別のペインが関連付けられている場合、ペインを Outlook スタイルのタブ付きウィンドウを作成、 [cdockablepane::attachtotabwnd](#attachtotabwnd)メソッドです。 既定では、ドッキング可能ペインは型の通常のタブ付きペインを作成する[派生](../../mfc/reference/ctabbedpane-class.md)です。  
  
##  <a name="createtabbedpane"></a>  CDockablePane::CreateTabbedPane  
 現在のウィンドウからタブ付きペインを作成します。  
  
```  
virtual CTabbedPane* CreateTabbedPane();
```  
  
### <a name="return-value"></a>戻り値  
 新しいタブ付きウィンドウ、または`NULL`作成操作が失敗した場合。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、このペインを置換するタブ付きペインを作成するときに、このメソッドを呼び出します。 詳細については、次を参照してください。 [cdockablepane::attachtotabwnd](#attachtotabwnd)です。  
  
 タブ付きペインをカスタマイズする派生クラスでは、このメソッドが作成され、初期化をオーバーライドします。  
  
 格納されているランタイム クラス情報に従って、タブ付きウィンドウが作成された、`m_pTabbedControlBarRTC`によって初期化されるメンバー、 [cdockablepane::createex](#createex)メソッドです。  
  
##  <a name="dockpanecontainer"></a>  CDockablePane::DockPaneContainer  
 ペインに、コンテナーにドッキングします。  
  
```  
virtual BOOL DockPaneContainer(
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `barContainerManager`  
 ドッキングされるコンテナーのコンテナー マネージャーへの参照。  
  
 [入力] `dwAlignment`  
 `DWORD` コンテナーのドッキング ウィンドウの辺を指定します。  
  
 [入力] `dockMethod`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` コンテナーが正常に、ウィンドウにドッキングされている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 `dwAlignment` 値は次のいずれかを指定できます。  
  
|[値]|説明|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|コンテナーは、ウィンドウの上部にドッキングされているされます。|  
|`CBRS_ALIGN_BOTTOM`|コンテナーのウィンドウの下部にドッキングします。|  
|`CBRS_ALIGN_LEFT`|コンテナーは、ペインの左側にドッキングされているされます。|  
|`CBRS_ALIGN_RIGHT`|コンテナーは、ウィンドウの右側にドッキングされているされます。|  
  
##  <a name="dockpanestandard"></a>  CDockablePane::DockPaneStandard  
 アウトライン (標準) のドッキングを使用して、ウィンドウをドッキングします。  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bWasDocked`  
 この値が含まれる、メソッドが戻るとき`TRUE`含まれている場合は、ウィンドウは、正常にドッキングされている以外の場合はそれ以外の場合に、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 タブ付きウィンドウに、ウィンドウがドッキングされている場合、またはタブ付きウィンドウがドッキングした結果として作成された場合は、このメソッドは、タブ付きウィンドウへのポインターを返します。 かどうか、ウィンドウにはそれが正常にドッキングされている、このメソッドが戻る、`this`ポインター。 ドッキングが失敗したかどうか、このメソッドが戻る`NULL`です。  
  
##  <a name="docktorecentpos"></a>  CDockablePane::DockToRecentPos  
 ストアドのドッキング位置に、ウィンドウをドッキングします。  
  
```  
BOOL CDockablePane::DockToRecentPos();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウが正常にドッキングされている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ペインは最近ドッキング情報を格納、 [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)オブジェクト。  
  
##  <a name="docktowindow"></a>  CDockablePane::DockToWindow  
 別のドッキング ペインには、1 つのドッキング ペインをドッキングします。  
  
```  
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pTargetWindow`  
 このペインをドッキングする、ドッキング可能ウィンドウを指定します。  
  
 [入力] `dwAlignment`  
 ペインのドッキングの配置を指定します。 CBRS_ALIGN_LEFT、CBRS_ALIGN_TOP、CBRS_ALIGN_RIGHT、CBRS_ALIGN_BOTTOM CBRS_ALIGN_ANY のいずれかがあります。 (Afxres.h 内で定義)。  
  
 [入力] `lpRect`  
 ウィンドウのドッキングする四角形を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウが正常にドッキング可能な場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 指定された配置と別のペインに 1 つのペインをドッキングするには、このメソッドを呼び出す`dwAlignment`です。  
  
##  <a name="drawcaption"></a>  CDockablePane::DrawCaption  
 ドッキング ウィンドウのキャプション ("グリッパー"とも呼ばれます) を描画します。  
  
```  
virtual void DrawCaption(
    CDC* pDC,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 描画に使用するデバイス コンテキストを表します。  
  
 [入力] `rectCaption`  
 ペインのキャプションに外接する四角形を指定します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ドッキング可能なウィンドウのキャプションを描画するには、このメソッドを呼び出します。  
  
 キャプションの外観をカスタマイズする派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="enableautohideall"></a>  CDockablePane::EnableAutohideAll  
 有効またはこのペイン、およびコンテナー内の他のウィンドウの自動非表示モードを無効にします。  
  
```  
void EnableAutohideAll(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` 自動非表示のドッキング可能ペイン; のすべての機能を有効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ユーザーが保持している、`Ctrl`キーおよびペインを autohide モード、同じコンテナー内の他のすべてのペインに切り替えるには、暗証番号 (pin) ボタンが自動的に隠すモードに切り替えられますもクリックします。  
  
 このメソッドを呼び出します`bEnable`'éý'`FALSE`特定のペインのこの機能を無効にします。  
  
##  <a name="enablegripper"></a>  CDockablePane::EnableGripper  
 ("グリッパー"とも呼ばれます) のキャプションの表示と非表示を切り替えます。  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` キャプションを有効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ドッキング可能ペインを作成するときはありません、 **WS_STYLE**ウィンドウ スタイルを指定した場合でもです。 つまり、ペインのキャプションは、フレームワークによって制御される非クライアント領域は、この領域は、標準のウィンドウ キャプションによって異なります。  
  
 表示またはキャプションをいつでも非表示にできます。 フレームワークでは、タブ付きウィンドウに、またはミニフレーム ウィンドウのペインがフローティング状態になった、ウィンドウがタブとして追加されるときに、キャプションが表示されません。  
  
##  <a name="getahrestoredrect"></a>  CDockablePane::GetAHRestoredRect  
 自動非表示モードのときにウィンドウの位置を指定します。  
  
```  
CRect GetAHRestoredRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CRect`自動非表示モードにあるときに、ウィンドウの位置を含むオブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getahslidemode"></a>  CDockablePane::GetAHSlideMode  
 ウィンドウの自動非表示のスライド ショー モードを取得します。  
  
```  
virtual UINT GetAHSlideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`UINT`ペインの自動非表示のスライド ショー モードを指定します。 戻り値には、いずれかを指定できる`AFX_AHSM_MOVE`または`AFX_AHSM_STRETCH`、実装を使用してのみが、`AFX_AHSM_MOVE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcaptionheight"></a>  CDockablePane::GetCaptionHeight  
 (ピクセル単位) の現在のキャプションの高さを返します。  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 (ピクセル単位)、キャプションの高さ。  
  
### <a name="remarks"></a>コメント  
 キャプションの高さは、0 で、キャプションが表示されていない場合、 [CDockablePane::EnableGripper](#enablegripper)メソッド、または、ウィンドウで、キャプションがあるない場合。  
  
##  <a name="getdefaultpanedivider"></a>  CDockablePane::GetDefaultPaneDivider  
 ペインのコンテナーの既定ペイン分割バーを返します。  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>戻り値  
 有効な[CPaneDivider](../../mfc/reference/cpanedivider-class.md)メイン フレーム ウィンドウにドッキング可能なウィンドウがドッキングされている場合は、オブジェクトまたは`NULL`ドッキング可能なウィンドウがドッキングされていない場合、またはそれが固定されていない場合。  
  
### <a name="remarks"></a>コメント  
 ペイン分割バーの詳細については、次を参照してください。 [CPaneDivider クラス](../../mfc/reference/cpanedivider-class.md)です。  
  
##  <a name="getdockingstatus"></a>  CDockablePane::GetDockingStatus  
 指定されたポインターの位置に基づいて、ドッキング ペインの機能を決定します。  
  
```  
virtual AFX_CS_STATUS GetDockingStatus(
    CPoint pt,  
    int nSensitivity);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pt`  
 画面座標でポインターの場所です。  
  
 [入力] `nSensitivity`  
 距離 (ピクセル単位) を四角形の端から離れた場所ポインターでなければなりませんドッキング可能にします。  
  
### <a name="return-value"></a>戻り値  
 状態値は次のいずれかです。  
  
|`AFX_CS_STATUS` の値|説明|  
|---------------------------|-------------|  
|`CS_NOTHING`|ドッキング サイト上、ポインターはします。 フレームワークは、ウィンドウをドッキングしていません。|  
|`CS_DOCK_IMMEDIATELY`|ポインターが上にあるドッキング サイト イミディ エイト モード (ウィンドウを使用して、`DT_IMMEDIATE`ドッキング モード)。 フレームワークは、すぐに、ウィンドウをドッキングします。|  
|`CS_DELAY_DOCK`|ドッキング サイトは、別のドッキング ペインまたはメイン フレームの境界を上にポインターがします。 フレームワークは、遅延後に、ウィンドウをドッキングします。 この遅延時間の詳細については「解説」セクションを参照してください。|  
|`CS_DELAY_DOCK_TO_TAB`|ポインターが、タブ付きウィンドウにドッキングするのには、ウィンドウの原因となるドッキング サイト上にあります。 これは、別のドッキング ペインのキャプションまたはタブ付きウィンドウのタブ領域の上にポインターがあるときに発生します。|  
  
### <a name="remarks"></a>コメント  
 フレームワークは、フローティング ペインのドッキングを処理するには、このメソッドを呼び出します。  
  
 フローティング ツールバーのドッキング ペインを使用する、`DT_IMMEDIATE`フレームワーク モードをドッキング、ドッキングを実行する前に、親フレームのクライアント領域から、ウィンドウを移動するユーザーを有効にする、ドッキング コマンドが遅延します。 遅延の長さ (ミリ秒) で測定され、によって制御されます、 [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock)データ メンバー. 既定値の[CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) 200 です。 この動作のドッキング動作をエミュレートする[!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)]2007。  
  
 ドッキング状態を遅延のため (`CS_DELAY_DOCK`と`CS_DELAY_DOCK_TO_TAB`)、フレームワークは、ユーザーがマウス ボタンを離すまでのドッキングを実行できません。 ウィンドウを使用している場合、`DT_STANDARD`モードをドッキングするには、フレームワークによって表示四角形のドッキング場所にします。 ウィンドウを使用している場合、`DT_SMART`モードをドッキングするには、フレームワークによって表示スマート ドッキング マーカーおよび半透明四角形のドッキング場所にします。 呼び出し、ウィンドウのドッキングのモードを指定する、 [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode)メソッドです。 スマート ドッキングの詳細については、次を参照してください。 [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams)です。  
  
##  <a name="getdragsensitivity"></a>  CDockablePane::GetDragSensitivity  
 ドッキング ウィンドウのドラッグと小文字の区別を返します。  
  
```  
static const CSize& GetDragSensitivity();
```  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)幅と高さ (ピクセル単位)、ドラッグ ポイントを中心とする四角形を含むオブジェクト。 ドラッグ操作では、マウス ポインターがこの四角形の外側に移動するまでは開始しません。  
  
##  <a name="getlastpercentinpanecontainer"></a>  CDockablePane::GetLastPercentInPaneContainer  
 コンテナーで、ウィンドウを占有する領域の割合を取得します ( [CPaneContainer クラス](../../mfc/reference/cpanecontainer-class.md))。  
  
```  
int GetLastPercentInPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `int`コンテナー内のウィンドウを占有する領域の割合を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コンテナーのレイアウトが調整される場合に使用されます。  
  
##  <a name="gettabarea"></a>  CDockablePane::GetTabArea  
 ウィンドウのタブ領域を取得します。  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectTabAreaTop`  
 `GetTabArea` タブがウィンドウの上部にある場合、この変数をタブ領域に設定します。 タブがウィンドウの下部にある場合は、この変数は、空の四角形が入力されます。  
  
 [入力] `rectTabAreaBottom`  
 `GetTabArea` タブがウィンドウの下部にある場合、この変数をタブ領域に設定します。 タブがウィンドウの上部にある場合は、この変数は、空の四角形が入力されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドはから派生したクラスでのみ使用`CDockablePane`タブがあるとします。 詳細については、次を参照してください。 [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea)と[CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea)です。  
  
##  <a name="gettabbedpanertc"></a>  CDockablePane::GetTabbedPaneRTC  
 現在のウィンドウを別のペインをドッキング時に作成されるタブ付きウィンドウに関するランタイム クラス情報を返します。  
  
```  
CRuntimeClass* GetTabbedPaneRTC() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドッキング可能ペインのランタイム クラス情報。  
  
### <a name="remarks"></a>コメント  
 動的に作成されるタブ付きウィンドウのランタイム クラス情報を取得するには、このメソッドを呼び出します。 これは、ユーザーが別のウィンドウのキャプションに 1 つのペインをドラッグしたときに、または呼び出す場合に発生することができます、 [cdockablepane::attachtotabwnd](#attachtotabwnd)メソッドをプログラムで 2 つのドッキング可能ペインからタブ付きペインを作成します。  
  
 ランタイム クラス情報を設定するには呼び出すことによって、 [:settabbedpanertc](#settabbedpanertc)メソッドです。  
  
##  <a name="hasautohidemode"></a>  CDockablePane::HasAutoHideMode  
 ドッキング ペインを autohide モードに切り替えることができるかどうかを指定します。  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング可能ウィンドウを隠すモードに切り替えることができる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 特定のドッキング可能なペインを autohide モードを無効にする派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="hittest"></a>  CDockablePane::HitTest  
 ユーザーがマウスをクリックしたウィンドウで、場所を指定します。  
  
```  
virtual int HitTest(
    CPoint point,  
    BOOL bDetectCaption = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 テストする点を指定します。  
  
 [入力] `bDetectCaption`  
 `TRUE` 場合`HTCAPTION`を返すかどうか、ポイントは、ウィンドウのキャプションです。 それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
- `HTNOWHERE` 場合`point`ドッキング可能なペインに表示されていません。  
  
- `HTCLIENT` 場合`point`がドッキング可能なウィンドウのクライアント領域内です。  
  
- `HTCAPTION` 場合`point`ドッキング可能なウィンドウのキャプションの領域にします。  
  
- `AFX_HTCLOSE` 場合`point`閉じるボタンにします。  
  
- `HTMAXBUTTON` 場合`point`ピン ボタンにします。  
  
##  <a name="isautohideallenabled"></a>  CDockablePane::IsAutohideAllEnabled  
 ドッキング ペインと、コンテナー内の他のすべてのウィンドウが自動的に隠すモードに切り替えることができるかどうかを示します。  
  
```  
virtual BOOL IsAutohideAllEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング可能ペイン、およびコンテナー内の他のすべてのウィンドウを自動的に隠すモードに切り替えることができる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ユーザーが保持しているときにドッキング暗証番号 (pin) ボタンをクリックして自動的に隠すモードを有効、 **Ctrl**キー  
  
 有効またはこの動作を無効にする、呼び出し、 [CDockablePane::EnableAutohideAll](#enableautohideall)メソッドです。  
  
##  <a name="isautohidemode"></a>  CDockablePane::IsAutoHideMode  
 ペインが自動的に隠すモードかどうかを判断します。  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング可能ペインが自動的に隠すモードである場合それ以外の場合、`FALSE`です。  
  
##  <a name="isdocked"></a>  CDockablePane::IsDocked  
 現在のウィンドウがドッキングされているかどうかを判断します。  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ミニフレーム ウィンドウにドッキング可能ペインが属していない場合、または別のペインを持つミニフレーム ウィンドウでそれが固定されていない場合。 `FALSE` ミニフレーム ウィンドウの子は、ウィンドウがミニフレーム ウィンドウに属している他のウィンドウがない場合。  
  
### <a name="remarks"></a>コメント  
 メイン フレーム ウィンドウに、ウィンドウがドッキングされているかどうかを判断するのには、呼び出す[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)です。 メソッドが NULL ポインターを返す場合は、メイン フレーム ウィンドウに、ウィンドウがドッキングされています。  
  
##  <a name="ishideinautohidemode"></a>  CDockablePane::IsHideInAutoHideMode  
 場合はそれを示すように (または非表示) を呼び出して、自動非表示モードになっているウィンドウの動作を決定[CDockablePane::ShowPane](#showpane)です。  
  
```  
virtual BOOL IsHideInAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 自動非表示モードのときに、ドッキング可能ウィンドウを非表示にする場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ウィンドウは、自動的に隠すモードが、これとは異なる動作を呼び出すと`ShowPane`ウィンドウを表示または非表示にします。 この動作は、静的メンバーによって制御されます[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)です。 このメンバーは場合`TRUE`、ドッキング可能ペインとその関連自動的に隠すツールバーまたは自動的に隠す ボタンを非表示またはを呼び出すときに表示される`ShowPane`です。 それ以外の場合、ドッキング可能なウィンドウがアクティブ化または非アクティブ化、および、関連する自動的に隠すツールバーまたは自動的に隠す ボタンは常に表示します。  
  
 各ペインの既定の動作を変更する派生クラスでは、このメソッドをオーバーライドします。  
  
 `m_bHideInAutoHideMode` の既定値は `FALSE` です。  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CDockablePane::IsInFloatingMultiPaneFrameWnd  
 複数のウィンドウ フレーム ウィンドウのウィンドウがかどうかを指定します ( [CMultiPaneFrameWnd クラス](../../mfc/reference/cmultipaneframewnd-class.md))。  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 複数のウィンドウ フレーム ウィンドウが、ウィンドウの場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isresizable"></a>  CDockablePane::IsResizable  
 そのウィンドウはサイズを変更できるかどうかを指定します。  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインがサイズを変更できる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 既定では、ドッキング可能なウィンドウのサイズは変更できます。 サイズ変更を防ぐためには、派生クラスでは、このメソッドをオーバーライドし、返す`FALSE`です。 なお、`FALSE`値は、失敗につながります`ASSERT`で[CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)です。 使用して[CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane)代わりに親フレーム内のペインをドッキングします。  
  
 ウィンドウ サイズを変更することはできませんがどちらも float も自動的に隠すモードに切り替わるし、親フレームの外側のエッジは、常にします。  
  
##  <a name="istablocationbottom"></a>  CDockablePane::IsTabLocationBottom  
 タブが上部またはウィンドウの下部にあるかどうかを指定します。  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` タブは、ウィンドウの下部にある場合`FALSE`タブがウィンドウの上部にある場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom)です。  
  
##  <a name="istracked"></a>  CDockablePane::IsTracked  
 ペインがユーザーによって移動されたかどうかを指定します。  
  
```  
BOOL IsTracked() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウが移動されています。それ以外の場合、`FALSE`です。  
  
##  <a name="isvisible"></a>  CDockablePane::IsVisible  
 現在のウィンドウが表示されているかどうかを判断します。  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング可能ペインを表示する場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能ペインを表示するかどうかを決定するには、このメソッドを呼び出します。 このメソッドを呼び出す代わりに使用することができます[CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible)のためのテストや、`WS_VISIBLE`スタイル。 返される可視性の状態は、自動非表示モードを有効または無効にするかどうかとの値によって異なります、 [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)プロパティです。  
  
 ドッキング可能なウィンドウが自動非表示モードの場合と`IsHideInAutoHideMode`返します`FALSE`可視性の状態は常に`FALSE`です。  
  
 ドッキング可能なウィンドウが自動非表示モードの場合と`IsHideInAutoHideMode`返します`TRUE`可視性の状態は、関連する自動的に隠すツールバーの可視性の状態によって異なります。  
  
 可視性の状態がによって決まりますが、ドッキング可能ペインが自動的に隠すモードでない場合、 [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible)メソッドです。  
  
##  <a name="m_bdisableanimation"></a>  CDockablePane::m_bDisableAnimation  
 ドッキング可能なウィンドウの自動非表示のアニメーションが無効になっているかどうかを指定します。  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableAnimation;  
```  
  
##  <a name="m_bhideinautohidemode"></a>  CDockablePane::m_bHideInAutoHideMode  
 ペインが自動的に隠すモードのときは、ウィンドウの動作を決定します。  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideInAutoHideMode;  
```  
  
### <a name="remarks"></a>コメント  
 この値は、アプリケーションのすべてのドッキング ウィンドウに影響します。  
  
 このメンバーを設定する場合`TRUE`、ドッキング可能ウィンドウを非表示またはを呼び出すときの関連する自動的に隠すツールバーとボタンに表示される[CDockablePane::ShowPane](#showpane)です。  
  
 このメンバーを設定する場合`FALSE`、ドッキング可能ペインがアクティブまたは非アクティブに呼び出すときに[CDockablePane::ShowPane](#showpane)です。  
  
##  <a name="m_nslidesteps"></a>  CDockablePane::m_nSlideSteps  
 自動非表示モードにあるときは、ウィンドウのアニメーションの速度を指定します。  
  
```  
AFX_IMPORT_DATA static int m_nSlideSteps;  
```  
  
### <a name="remarks"></a>コメント  
 アニメーション効果を高速化するには、この値を小さきます。 アニメーション効果を遅くするには、この値を増やします。  
  
##  <a name="onafterchangeparent"></a>  CDockablePane::OnAfterChangeParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndOldParent`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onafterdockfromminiframe"></a>  CDockablePane::OnAfterDockFromMiniFrame  
 フレーム ウィンドウのフローティング、ドッキング バーをドッキングすると、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterDockFromMiniFrame();
```  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは何も行いません。  
  
##  <a name="onbeforechangeparent"></a>  CDockablePane::OnBeforeChangeParent  
 フレームワークは、ウィンドウの親を変更する前に、このメソッドを呼び出します。  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndNewParent`  
 新しい親ウィンドウへのポインター。  
  
 [入力] `bDelay`  
 `BOOL` ウィンドウがドッキングされていない場合は、ドッキング レイアウトの再計算を延期するかどうかを指定します。 詳細については、次を参照してください。 [CDockablePane::UndockPane](#undockpane)です。  
  
### <a name="remarks"></a>コメント  
 ペインをドッキングし、を新しい親がドッキングを許可していない場合、このメソッドには、ウィンドウがドッキング解除します。  
  
 場合は、ウィンドウはタブ付きドキュメントに変換される、このメソッドは、最近のドッキング位置を格納します。 フレームワークは、ドッキングされた状態に戻すことが変換されるときに、ウィンドウの位置を復元するのに最近のドッキング位置を使用します。  
  
##  <a name="onbeforefloat"></a>  CDockablePane::OnBeforeFloat  
 フレームワークは、フローティング状態に遷移のウィンドウを前にこのメソッドを呼び出します。  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectFloat`  
 フローティング状態にあるときは、ウィンドウのサイズと位置を指定します。  
  
 [入力] `dockMethod`  
 ドッキング方法を指定します。 参照してください[CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)使用可能な値の一覧についてはします。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウをフロートことができます。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ペインが float 型に、フレームワークによって呼び出されます。 ペインをフローティング前に、どのような処理を実行する場合は、派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="onpressbuttons"></a>  CDockablePane::OnPressButtons  
 ボタンを押す、キャプション以外のときに呼び出されます、`AFX_HTCLOSE`と`AFX_HTMAXBUTTON`ボタン。  
  
```  
virtual void OnPressButtons(UINT nHit);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nHit`  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能なウィンドウのキャプションにカスタム ボタンを追加する場合は、ユーザーがボタンを押したときに通知を受信するには、このメソッドをオーバーライドします。  
  
##  <a name="onslide"></a>  CDockablePane::OnSlide  
 自動非表示モードであるときに、ウィンドウのアニメーション化するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnSlide(BOOL bSlideOut);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSlideOut`  
 `TRUE` ウィンドウを表示するには`FALSE`ウィンドウを非表示にします。  
  
### <a name="remarks"></a>コメント  
 カスタム自動非表示の効果を実装する派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="removefromdefaultpanedividier"></a>  CDockablePane::RemoveFromDefaultPaneDividier  
 フレームワークは、ペインのドッキングを解除中にこのメソッドを呼び出します。  
  
```  
void RemoveFromDefaultPaneDividier();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、既定ペイン分割バーを設定`NULL`し、そのコンテナーから、ウィンドウを削除します。  
  
##  <a name="replacepane"></a>  CDockablePane::ReplacePane  
 指定したウィンドウで、ウィンドウを置き換えます。  
  
```  
BOOL ReplacePane(
    CDockablePane* pBarToReplaceWith,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bRegisterWithFrame = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBarToReplaceWith`  
 ドッキング可能ペインへのポインター。  
  
 [入力] `dockMethod`  
 使用しません。  
  
 [入力] `bRegisterWithFrame`  
 場合`TRUE`、新規作成 ウィンドウは、古いウィンドウの親のドッキング マネージャーに登録されています。 新しいウィンドウは、古いペイン、ドッキング マネージャーによって管理されているペインの一覧でのインデックスに挿入されます。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 置換が成功した場合それ以外の場合、`FALSE`です。  
  
##  <a name="restoredefaultpanedivider"></a>  CDockablePane::RestoreDefaultPaneDivider  
 ペインが逆シリアル化されるときに、フレームワークは、既定ペイン分割バーを復元するには、このメソッドを呼び出します。  
  
```  
void RestoreDefaultPaneDivider();
```  
  
### <a name="remarks"></a>コメント  
 元に戻した既定ペイン分割バーでは、存在する場合、現在の既定ペイン分割バーが置き換えられます。  
  
##  <a name="setautohidemode"></a>  CDockablePane::SetAutoHideMode  
 ドッキング ペインの表示を切り替えますと自動非表示モード。  
  
```  
virtual CMFCAutoHideBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMode`  
 `TRUE` 自動非表示モードを有効にするには`FALSE`標準ドッキング モードを有効にします。  
  
 [入力] `dwAlignment`  
 作成する、自動的に隠すウィンドウの配置を指定します。  
  
 [in][out] `pCurrAutoHideBar`  
 現在の自動的に隠すツールバーへのポインター。 指定できます`NULL`です。  
  
 [入力] `bUseTimer`  
 ユーザーが、ウィンドウを autohide モードに切り替えるときに自動的に隠す効果を使用するか、すぐに、ウィンドウを非表示にするかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 自動非表示モードに切り替えるの結果として作成された、自動的に隠すツールバーまたは`NULL`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ユーザーは、自動非表示モードまたは標準ドッキング モードにドッキング可能ペインを切り替えるには暗証番号 (pin) ボタンをクリックしたときに、このメソッドを呼び出します。  
  
 プログラムによって自動的に隠すモードにドッキング可能ウィンドウを切り替えるには、このメソッドを呼び出します。 メイン フレーム ウィンドウに、ウィンドウをドッキングする必要があります ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)への有効なポインターを返す必要があります、 [CPaneDivider](../../mfc/reference/cpanedivider-class.md))。  
  
##  <a name="setautohideparents"></a>  CDockablePane::SetAutoHideParents  
 自動的に隠すボタンのウィンドウを自動的に隠すツールバーを設定します。  
  
```  
void SetAutoHideParents(
    CMFCAutoHideBar* pToolBar,  
    CMFCAutoHideButton* pBtn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pToolBar`  
 自動的に隠すツールバーへのポインター。  
  
 [入力] `pBtn`  
 自動的に隠すボタンへのポインター。  
  
##  <a name="setlastpercentinpanecontainer"></a>  CDockablePane::SetLastPercentInPaneContainer  
 コンテナーで、ウィンドウを占有する領域の割合を設定します。  
  
```  
void SetLastPercentInPaneContainer(int n);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `n`  
 `int`コンテナー内のウィンドウを占有する領域の割合を指定します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、レイアウトを再計算時に、新しい値を使用するウィンドウを調整します。  
  
##  <a name="setrestoreddefaultpanedivider"></a>  CDockablePane::SetRestoredDefaultPaneDivider  
 復元された既定の分割線を設定します。  
  
```  
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hRestoredSlider`  
 ペイン分割バー (つまみ) へのハンドル。  
  
### <a name="remarks"></a>コメント  
 ペインが逆シリアル化されるときに、復元された既定のウィンドウの区分線が取得されます。 詳細については、次を参照してください。 [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)です。  
  
##  <a name="settabbedpanertc"></a>  :Settabbedpanertc  
 2 つのペインがドッキング時に作成されるタブ付きウィンドウのランタイム クラス情報を設定します。  
  
```  
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRTC`  
 タブ付きペインのランタイム クラス情報。  
  
### <a name="remarks"></a>コメント  
 動的に作成されるタブ付きウィンドウのランタイム クラス情報を設定するには、このメソッドを呼び出します。 これは、ユーザーが別のウィンドウのキャプションに 1 つのペインをドラッグしたときに、または呼び出す場合に発生することができます、 [cdockablepane::attachtotabwnd](#attachtotabwnd)メソッドをプログラムで 2 つのドッキング可能ペインからタブ付きペインを作成します。  
  
 既定のランタイム クラスに従って設定されて、`dwTabbedStyle`のパラメーター [CDockablePane::Create](#create)と[cdockablepane::createex](#createex)です。 新しいタブ付きペインをカスタマイズするには、クラスを次のいずれかからクラスを派生します。  
  
- [CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)  
  
- [CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md)  
  
- [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)です。  
  
 次に、そのランタイム クラス情報へのポインターがこのメソッドを呼び出します。  
  
##  <a name="showpane"></a>  CDockablePane::ShowPane  
 ペインの表示と非表示を切り替えます。  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 `TRUE` ウィンドウを表示するには`FALSE`ウィンドウを非表示にします。  
  
 [入力] `bDelay`  
 `TRUE` ドッキングのレイアウトを調整することを遅延するには`FALSE`をすぐにドッキング レイアウトを調整します。  
  
 [入力] `bActivate`  
 `TRUE` 表示中に、ウィンドウをアクティブ化するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 代わりにこのメソッドを呼び出して、[また](../../mfc/reference/cwnd-class.md#showwindow)を表示またはドッキング可能ウィンドウを非表示にするときにします。  
  
##  <a name="slide"></a>  CDockablePane::Slide  
 自動非表示モードになっているウィンドウをアニメーション化します。  
  
```  
virtual void Slide(
    BOOL bSlideOut,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSlideOut`  
 `TRUE` ウィンドウを表示するには`FALSE`ウィンドウを非表示にします。  
  
 [入力] `bUseTimer`  
 `TRUE` 、効果が自動的に隠すウィンドウを非表示`FALSE`またはすぐに、ウィンドウを非表示にします。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、自動的に隠すモードになっているウィンドウをアニメーション化するには、このメソッドを呼び出します。  
  
 このメソッドを使用して、`CDockablePane::m_nSlideDefaultTimeOut`スライド効果のタイムアウトを決定する値。 タイムアウトの既定値は 1 です。 自動的に隠すアルゴリズムをカスタマイズする場合は、タイムアウトを変更するには、このメンバーを変更します。  
  
##  <a name="toggleautohide"></a>  CDockablePane::ToggleAutoHide  
 表示されているペインの間で常に、自動非表示モードを切り替えます。  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出すことによって、ウィンドウの自動非表示モードを切り替えます[CDockablePane::SetAutoHideMode](#setautohidemode)です。  
  
##  <a name="undockpane"></a>  CDockablePane::UndockPane  
 メイン フレーム ウィンドウまたはミニフレーム ウィンドウのコンテナーのいずれかからペインのドッキングを解除します。  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDelay`  
 `TRUE` ドッキングのレイアウトの計算を遅延するには`FALSE`をドッキング レイアウトをすぐに再計算します。  
  
### <a name="remarks"></a>コメント  
 メイン フレーム ウィンドウまたはマルチ ミニフレーム ウィンドウ コンテナー (とその他のウィンドウの単一のミニフレーム ウィンドウのフローティング ウィンドウ) から、ウィンドウのドッキングを解除するには、このメソッドを呼び出します。  
  
 実行されていない、外部の操作を実行する前に、ペインをドッキング解除する必要があります、 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)です。 たとえばに移動するプログラムで 1 つの場所から別のウィンドウのドッキングを解除する必要があります。  
  
 フレームワークでは、破棄される前にも自動的にペインをドッキング解除します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)
