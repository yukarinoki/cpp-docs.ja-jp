---
title: CMFCTabCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl::ActivateMDITab
- AFXTABCTRL/CMFCTabCtrl::AllowDestroyEmptyTabbedPane
- AFXTABCTRL/CMFCTabCtrl::AutoSizeWindow
- AFXTABCTRL/CMFCTabCtrl::CalcRectEdit
- AFXTABCTRL/CMFCTabCtrl::Create
- AFXTABCTRL/CMFCTabCtrl::EnableActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::EnableInPlaceEdit
- AFXTABCTRL/CMFCTabCtrl::EnableTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::EnsureVisible
- AFXTABCTRL/CMFCTabCtrl::GetDocumentIcon
- AFXTABCTRL/CMFCTabCtrl::GetFirstVisibleTabNum
- AFXTABCTRL/CMFCTabCtrl::GetResizeMode
- AFXTABCTRL/CMFCTabCtrl::GetScrollBar
- AFXTABCTRL/CMFCTabCtrl::GetTabArea
- AFXTABCTRL/CMFCTabCtrl::GetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::GetTabsHeight
- AFXTABCTRL/CMFCTabCtrl::GetTabsRect
- AFXTABCTRL/CMFCTabCtrl::GetWndArea
- AFXTABCTRL/CMFCTabCtrl::HideActiveWindowHorzScrollBar
- AFXTABCTRL/CMFCTabCtrl::HideInactiveWindow
- AFXTABCTRL/CMFCTabCtrl::HideNoTabs
- AFXTABCTRL/CMFCTabCtrl::HideSingleTab
- AFXTABCTRL/CMFCTabCtrl::IsActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::IsDrawFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatTab
- AFXTABCTRL/CMFCTabCtrl::IsLeftRightRounded
- AFXTABCTRL/CMFCTabCtrl::IsMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsOneNoteStyle
- AFXTABCTRL/CMFCTabCtrl::IsSharedScroll
- AFXTABCTRL/CMFCTabCtrl::IsTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::IsVS2005Style
- AFXTABCTRL/CMFCTabCtrl::ModifyTabStyle
- AFXTABCTRL/CMFCTabCtrl::OnDragEnter
- AFXTABCTRL/CMFCTabCtrl::OnDragOver
- AFXTABCTRL/CMFCTabCtrl::OnShowTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::SetActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::SetActiveTab
- AFXTABCTRL/CMFCTabCtrl::SetActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::SetDrawFrame
- AFXTABCTRL/CMFCTabCtrl::SetFlatFrame
- AFXTABCTRL/CMFCTabCtrl::SetImageList
- AFXTABCTRL/CMFCTabCtrl::SetResizeMode
- AFXTABCTRL/CMFCTabCtrl::SetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::StopResize
- AFXTABCTRL/CMFCTabCtrl::SynchronizeScrollBar
- AFXTABCTRL/CMFCTabCtrl::m_bEnableActivate
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabCtrl [MFC], ActivateMDITab
- CMFCTabCtrl [MFC], AllowDestroyEmptyTabbedPane
- CMFCTabCtrl [MFC], AutoSizeWindow
- CMFCTabCtrl [MFC], CalcRectEdit
- CMFCTabCtrl [MFC], Create
- CMFCTabCtrl [MFC], EnableActiveTabCloseButton
- CMFCTabCtrl [MFC], EnableInPlaceEdit
- CMFCTabCtrl [MFC], EnableTabDocumentsMenu
- CMFCTabCtrl [MFC], EnsureVisible
- CMFCTabCtrl [MFC], GetDocumentIcon
- CMFCTabCtrl [MFC], GetFirstVisibleTabNum
- CMFCTabCtrl [MFC], GetResizeMode
- CMFCTabCtrl [MFC], GetScrollBar
- CMFCTabCtrl [MFC], GetTabArea
- CMFCTabCtrl [MFC], GetTabMaxWidth
- CMFCTabCtrl [MFC], GetTabsHeight
- CMFCTabCtrl [MFC], GetTabsRect
- CMFCTabCtrl [MFC], GetWndArea
- CMFCTabCtrl [MFC], HideActiveWindowHorzScrollBar
- CMFCTabCtrl [MFC], HideInactiveWindow
- CMFCTabCtrl [MFC], HideNoTabs
- CMFCTabCtrl [MFC], HideSingleTab
- CMFCTabCtrl [MFC], IsActiveInMDITabGroup
- CMFCTabCtrl [MFC], IsActiveTabBoldFont
- CMFCTabCtrl [MFC], IsActiveTabCloseButton
- CMFCTabCtrl [MFC], IsDrawFrame
- CMFCTabCtrl [MFC], IsFlatFrame
- CMFCTabCtrl [MFC], IsFlatTab
- CMFCTabCtrl [MFC], IsLeftRightRounded
- CMFCTabCtrl [MFC], IsMDITabGroup
- CMFCTabCtrl [MFC], IsOneNoteStyle
- CMFCTabCtrl [MFC], IsSharedScroll
- CMFCTabCtrl [MFC], IsTabDocumentsMenu
- CMFCTabCtrl [MFC], IsVS2005Style
- CMFCTabCtrl [MFC], ModifyTabStyle
- CMFCTabCtrl [MFC], OnDragEnter
- CMFCTabCtrl [MFC], OnDragOver
- CMFCTabCtrl [MFC], OnShowTabDocumentsMenu
- CMFCTabCtrl [MFC], SetActiveInMDITabGroup
- CMFCTabCtrl [MFC], SetActiveTab
- CMFCTabCtrl [MFC], SetActiveTabBoldFont
- CMFCTabCtrl [MFC], SetDrawFrame
- CMFCTabCtrl [MFC], SetFlatFrame
- CMFCTabCtrl [MFC], SetImageList
- CMFCTabCtrl [MFC], SetResizeMode
- CMFCTabCtrl [MFC], SetTabMaxWidth
- CMFCTabCtrl [MFC], StopResize
- CMFCTabCtrl [MFC], SynchronizeScrollBar
- CMFCTabCtrl [MFC], m_bEnableActivate
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad7a5331a2826df9dd6804e5c6a0f918bfeeb9d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfctabctrl-class"></a>CMFCTabCtrl Class
`CMFCTabCtrl`クラス タブ コントロールの機能を提供します。 タブ コントロールは、上または下にフラットまたは 3D のタブを持つ、ドッキング可能なウィンドウを表示します。 タブにはテキストとイメージを表示でき、アクティブな状態のときに色を変更することもできます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|既定のコンストラクター|  
|`CMFCTabCtrl::~CMFCTabCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](#activatemditab)|現在のタブ コントロールの指定したタブを表示し、そのタブにフォーカスを設定します。|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)||  
|[CMFCTabCtrl::AutoSizeWindow](#autosizewindow)|フレームワークがタブ コントロールのすべてのウィンドウとタブ コントロールのユーザー インターフェイス要素のクライアント領域のサイズを変更するかどうかを指定します。|  
|[CMFCTabCtrl::CalcRectEdit](#calcrectedit)|指定したタブ領域のサイズを縮小します。 (`CMFCBaseTabCtrl::CalcRectEdit` をオーバーライドします)。|  
|[CMFCTabCtrl::Create](#create)|タブ コントロールを作成し、それにアタッチ、`CMFCTabCtrl`オブジェクト。|  
|`CMFCTabCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](#enableactivetabclosebutton)|閉じるボタンの表示と非表示を切り替えます ( **X**) アクティブなタブにします。|  
|[CMFCTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|有効または編集可能なタブのラベルを無効にします。 (上書き[CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit))。|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)|スクロール ウィンドウのタブをタブ付きウィンドウのメニューを表示するボタンと 2 つのボタンに置換します。|  
|[CMFCTabCtrl::EnsureVisible](#ensurevisible)|タブが表示されていることを確認します。|  
|[CMFCTabCtrl::GetDocumentIcon](#getdocumenticon)|タブ付きウィンドウのポップアップ メニューのタブに関連付けられているシンボルを取得します。|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)|現在のタブ コントロールに表示されている最初のタブのインデックスを取得します。|  
|[CMFCTabCtrl::GetResizeMode](#getresizemode)|現在のタブ コントロールのサイズを変更できる方法を指定する値を取得します。|  
|[CMFCTabCtrl::GetScrollBar](#getscrollbar)|タブ コントロールに関連付けられているスクロール バーのオブジェクトへのポインターを取得します。|  
|[CMFCTabCtrl::GetTabArea](#gettabarea)|上部またはタブ コントロールの下部にあるタブ ラベル領域に外接する四角形を取得します。 (上書き[CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea))。|  
|`CMFCTabCtrl::GetTabFromPoint`|指定したポイントを含むタブを取得します。 (上書き[CMFCBaseTabCtrl::GetTabFromPoint](../../mfc/reference/cmfcbasetabctrl-class.md#gettabfrompoint))。|  
|[CMFCTabCtrl::GetTabMaxWidth](#gettabmaxwidth)|タブの最大幅を取得します。|  
|[CMFCTabCtrl::GetTabsHeight](#gettabsheight)|現在のタブ コントロールのタブ領域の高さを取得します。|  
|[CMFCTabCtrl::GetTabsRect](#gettabsrect)|現在のタブ コントロールのタブ領域に外接する四角形を取得します。 (上書き[CMFCBaseTabCtrl::GetTabsRect](../../mfc/reference/cmfcbasetabctrl-class.md#gettabsrect))。|  
|`CMFCTabCtrl::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCTabCtrl::GetWndArea](#getwndarea)|現在のタブ コントロールのクライアント領域の境界を取得します。|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)|いずれかのアクティブ ウィンドウの場合は、水平スクロール バーを非表示にします。|  
|[CMFCTabCtrl::HideInactiveWindow](#hideinactivewindow)|フレームワークが非アクティブなタブ コントロール ウィンドウを表示するかどうかを指定します。|  
|[CMFCTabCtrl::HideNoTabs](#hidenotabs)|有効または表示されるタブが存在しない場合、タブ領域の描画を無効にします。|  
|[CMFCTabCtrl::HideSingleTab](#hidesingletab)|有効または 1 つのタブ付きウィンドウがある場合に、タブを描画を無効にします。 (上書き[CMFCBaseTabCtrl::HideSingleTab](../../mfc/reference/cmfcbasetabctrl-class.md#hidesingletab))。|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](#isactiveinmditabgroup)|タブ コントロールの現在のタブがマルチ ドキュメント インターフェイスのタブ グループにアクティブなタブであるかどうかを示します。|  
|[CMFCTabCtrl::IsActiveTabBoldFont](#isactivetabboldfont)|太字のフォントを使用して、アクティブなタブのテキストを表示するかどうかを示します。|  
|[CMFCTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)|示すかどうか閉じるボタン ( **X**) が、アクティブなタブまたはタブ領域の右上隅に表示されます。|  
|[CMFCTabCtrl::IsDrawFrame](#isdrawframe)|タブ付きウィンドウが埋め込みウィンドウの周囲のフレームの四角形を描画するかどうかを示します。|  
|[CMFCTabCtrl::IsFlatFrame](#isflatframe)|タブ領域を囲むフレームがフラットまたは 3D であるかどうかを示します。|  
|[CMFCTabCtrl::IsFlatTab](#isflattab)|現在のタブ コントロールのタブの外観がフラットかどうかを示します。|  
|[CMFCTabCtrl::IsLeftRightRounded](#isleftrightrounded)|左側と右側にある現在のタブ コントロールのタブの外観が丸められるかどうかを示します。|  
|[CMFCTabCtrl::IsMDITabGroup](#ismditabgroup)|現在のタブ コントロールがマルチ ドキュメント インターフェイス ウィンドウのクライアント領域に含まれているかどうかを示します。|  
|[CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)|現在のタブ コントロールがの Microsoft OneNote スタイルで表示されるかどうかを示します。|  
|`CMFCTabCtrl::IsPtInTabArea`|ポイントがタブ領域の内部かどうかを判断します。 (上書き[CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea))。|  
|[CMFCTabCtrl::IsSharedScroll](#issharedscroll)|現在のタブ コントロールがグループとして、タブをスクロールできるスクロール バーを持つかどうかを示します。|  
|[CMFCTabCtrl::IsTabDocumentsMenu](#istabdocumentsmenu)|タブ コントロールがスクロール ボタンまたはタブ付きウィンドウのメニューを表示するボタンを表示するかどうかを示します。|  
|[CMFCTabCtrl::IsVS2005Style](#isvs2005style)|Visual Studio .NET 2005 のスタイルでタブを表示するかどうかを示します。|  
|[CMFCTabCtrl::ModifyTabStyle](#modifytabstyle)|現在のタブ コントロールのタブの外観を指定します。|  
|`CMFCTabCtrl::MoveTab`|別のタブ位置にタブを移動します。 (上書き[CMFCBaseTabCtrl::MoveTab](../../mfc/reference/cmfcbasetabctrl-class.md#movetab))。|  
|[CMFCTabCtrl::OnDragEnter](#ondragenter)|カーソルが最初に、タブ コントロール ウィンドウにドラッグされたときに、フレームワークによって呼び出されます。|  
|[CMFCTabCtrl::OnDragOver](#ondragover)|マウスをドロップ ターゲットのウィンドウに移動するドラッグ操作中に、フレームワークによって呼び出されます (上書き[CMFCBaseTabCtrl::OnDragOver](../../mfc/reference/cmfcbasetabctrl-class.md#ondragover))。|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](#onshowtabdocumentsmenu)|タブ付きウィンドウのポップアップ メニューを表示、タブを選択し、ユーザー選択されているタブ アクティブなタブまで待機します。|  
|`CMFCTabCtrl::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数。 (上書き[CMFCBaseTabCtrl::PreTranslateMessage](../../mfc/reference/cmfcbasetabctrl-class.md#pretranslatemessage))。|  
|`CMFCTabCtrl::RecalcLayout`|タブ コントロールの内部レイアウトを再計算されます。 (上書き[CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout))。|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](#setactiveinmditabgroup)|タブ コントロールの現在のタブは、マルチ ドキュメント インターフェイスのタブ グループにアクティブなタブとして設定します。|  
|[CMFCTabCtrl::SetActiveTab](#setactivetab)|タブをアクティブにします。(上書き[CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab))。|  
|[CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)|有効またはアクティブなタブ上の太字のフォントの使用を無効にします。|  
|[CMFCTabCtrl::SetDrawFrame](#setdrawframe)|有効または埋め込みバーの周囲におけるフレームの四角形を無効にします。|  
|[CMFCTabCtrl::SetFlatFrame](#setflatframe)|タブ領域の周囲にフラットまたは 3D のフレームを描画するかどうかを指定します。|  
|[CMFCTabCtrl::SetImageList](#setimagelist)|イメージ リストを指定します。 (上書き[CMFCBaseTabCtrl::SetImageList](../../mfc/reference/cmfcbasetabctrl-class.md#setimagelist))。|  
|[CMFCTabCtrl::SetResizeMode](#setresizemode)|現在のタブ コントロールのサイズを変更できる方法を指定し、し、コントロールを再表示します。|  
|[CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)|タブ付きウィンドウでタブの最大幅を指定します。|  
|[CMFCTabCtrl::StopResize](#stopresize)|タブ コントロールの現在のサイズ変更操作を終了します。|  
|`CMFCTabCtrl::SwapTabs`|タブのペアを交換します。 (上書き[CMFCBaseTabCtrl::SwapTabs](../../mfc/reference/cmfcbasetabctrl-class.md#swaptabs))。|  
|[CMFCTabCtrl::SynchronizeScrollBar](#synchronizescrollbar)|フラット タブを表示するタブ コントロールの水平スクロール バーを描画します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCTabCtrl::m_bEnableActivate](#m_benableactivate)|アクティブなビューが新しいタブが挿入され、有効になっているときに、フォーカスを失うを防ぎます。|  
  
## <a name="remarks"></a>コメント  
 `CMFCTabCtrl`クラスでサポートします。  
  
-   3 D、フラット、およびフラット付き共有の水平スクロール バー コントロールのスタイル タブします。  
  
-   最上部またはウィンドウの下部にあるタブ。  
  
-   テキスト、画像、またはテキストおよびイメージを表示するタブです。  
  
-   色を変更する、タブがアクティブなタブ。  
  
-   調整可能なタブの境界線のサイズ変更します。  
  
-   切り離し可能なタブ付きウィンドウです。  
  
 `CMFCTabCtrl`  ダイアログ ボックスでは、クラスを使用できますが、目的のコントロールのようなバーのドッキングを使用するアプリケーション[!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)]と[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]です。 詳細については、次を参照してください。 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)です。  
  
 アプリケーションでタブ コントロールのドッキングをサイズ変更、追加するこれらの手順に従います。  
  
1.  インスタンスを作成する[派生クラス](../../mfc/reference/ctabbedpane-class.md)です。  
  
2.  呼び出す[CDockablePane::Create](../../mfc/reference/cdockablepane-class.md#create)です。  
  
3.  使用して[cbasetabbedpane::addtab](../../mfc/reference/cbasetabbedpane-class.md#addtab)または[cmfcbasetabctrl::inserttab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab)新しいタブを追加します。  
  
4.  呼び出す[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking)メイン フレーム ウィンドウに現在のドッキング タブ コントロールがドッキングできるようにします。  
  
5.  呼び出す[CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane)メイン フレームにタブ付きウィンドウをドッキングします。  
  
 タブ付きウィンドウとしてドッキング コントロール バーを作成する方法の例は、次を参照してください。[派生クラス](../../mfc/reference/ctabbedpane-class.md)です。 使用する`CMFCTabCtrl`非ドッキング コントロールとして作成、`CMFCTabCtrl`オブジェクトを呼び出す[CMFCTabCtrl::Create](#create)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [から派生しているのではない](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCTabCtrl`を構成するクラス、`CMFCTabCtrl`オブジェクト。 この例では、タブを追加、アクティブなタブの閉じるボタンの表示、編集可能なタブのラベルを有効にする、およびラベルのタブ付きウィンドウのポップアップ メニューを表示する方法について説明します。 この例の一部である、[状態コレクションのサンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#3](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtabctrl.h  
  
##  <a name="activatemditab"></a>  CMFCTabCtrl::ActivateMDITab  
 現在のタブ コントロールの指定したタブを表示し、そのタブにフォーカスを設定します。  
  
```  
void ActivateMDITab(int nTab = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTab`  
 表示、または現在アクティブなタブを指定する場合は-1 をタブの 0 から始まるインデックス。  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CMFCTabCtrl::AllowDestroyEmptyTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="autosizewindow"></a>  CMFCTabCtrl::AutoSizeWindow  
 フレームワークがタブ コントロールのすべてのウィンドウとタブ コントロールのユーザー インターフェイス要素のクライアント領域のサイズを変更するかどうかを指定します。  
  
```  
void AutoSizeWindow(BOOL bAutoSize = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAutoSize`  
 `TRUE` タブ コントロール ウィンドウを自動的にサイズ変更それ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="create"></a>  CMFCTabCtrl::Create  
 タブ コントロールを作成し、それにアタッチ、`CMFCTabCtrl`オブジェクト。  
  
```  
BOOL Create(
    Style style,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    Location location=LOCATION_BOTTOM,  
    BOOL bCloseBtn=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `style`  
 タブ コントロールのスタイルです。 詳細については、「解説」を参照してください。  
  
 [入力] `rect`  
 タブ コントロールに外接する四角形。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。 `NULL` にすることはできません。  
  
 [入力] `nID`  
 タブ コントロールの ID。  
  
 [入力] `location`  
 タブの位置。 既定値は `LOCATION_BOTTOM` です。 詳細については、「解説」を参照してください。  
  
 [入力] `bCloseBtn`  
 `TRUE` [;] タブで [閉じる] ボタンを表示するにはそれ以外の場合、`FALSE`です。 既定値は `FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`、それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 次の表に、指定できる値、`style`パラメーター。  
  
|スタイル|説明|  
|-----------|-----------------|  
|STYLE_3D|3 次元の外観を持つタブ コントロールを作成します。|  
|STYLE_FLAT|フラット タブをタブ コントロールを作成します。|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|フラット タブ、および親ウィンドウがクリップされている場合、タブをスクロールできるスクロール バーをタブ コントロールを作成します。|  
|STYLE_3D_ONENOTE|Microsoft OneNote スタイルでタブ コントロールを作成します。|  
|STYLE_3D_VS2005|Microsoft Visual Studio 2005 のスタイルでタブ コントロールを作成します。|  
|STYLE_3D_ROUNDED|Microsoft Visual Studio 2005 のスタイルの丸められたタブをタブ コントロールを作成します。|  
|STYLE_3D_ROUNDED_SCROLL|角の丸いタブおよび Microsoft Visual Studio 2005 のスタイルのスクロール ボタンをタブ コントロールを作成します。|  
  
 次の表に、指定できる値、`location`パラメーター。  
  
|場所|説明|  
|--------------|-----------------|  
|LOCATION_BOTTOM|タブは、タブ コントロールの下部にあります。|  
|LOCATION_TOP|タブは、タブ コントロールの上部にあります。|  
  
### <a name="example"></a>例  
 次の例で使用する方法、`Create`メソッドで、`CMFCTabCtrl`クラスです。 この例の一部である、[状態コレクションのサンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#2](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_3.cpp)]  
  
##  <a name="calcrectedit"></a>  CMFCTabCtrl::CalcRectEdit  
 指定したタブ領域のサイズを縮小します。  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectEdit`  
 タブの領域を指定する四角形。  
  
### <a name="remarks"></a>コメント  
 タブのラベルを変更するときに、このメソッドが呼び出されます。このメソッドは、現在タブ高さを 30 分で指定した四角形の左右を縮小し、上部と下部で 1 つの単位を縮小します。  
  
##  <a name="enableactivetabclosebutton"></a>  CMFCTabCtrl::EnableActiveTabCloseButton  
 閉じるボタンの表示と非表示を切り替えます ( **X**) アクティブなタブにします。  
  
```  
void EnableActiveTabCloseButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` アクティブなタブを閉じる ボタンを表示するには`FALSE`タブ領域の右上隅にある閉じるボタンを表示します。 既定値は `TRUE` です。  
  
##  <a name="enableinplaceedit"></a>  CMFCTabCtrl::EnableInPlaceEdit  
 有効または編集可能なタブのラベルを無効にします。  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` 編集可能なタブのラベルを有効にするには`FALSE`編集可能なタブのラベルを無効にします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enabletabdocumentsmenu"></a>  CMFCTabCtrl::EnableTabDocumentsMenu  
 ウィンドウ タブをスクロールする 2 つのボタンを使用するユーザー インターフェイスと、タブ付きウィンドウのポップアップ メニューを表示するインターフェイスを切り替えます。  
  
```  
void EnableTabDocumentsMenu(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` タブ付きウィンドウ ラベルのポップアップ メニューを表示するには`FALSE`前方または後方スクロール ボタンを表示します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
 ユーザーには、タブのラベルがクリックすると、フレームワークに対応するタブ付きウィンドウが表示されます。 タブ ラベルが表示されている位置を変更せず、タブ付きウィンドウが開かれます。 ユーザーがポップアップ メニューから、ドキュメントを選択し、対応するタブ付きウィンドウが画面外には場合、は、最初のタブがタブ付きウィンドウになります。  
  
##  <a name="ensurevisible"></a>  CMFCTabCtrl::EnsureVisible  
 タブが表示されていることを確認します。  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTab`  
 タブの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 成功した場合`FALSE`場合、`iTab`パラメーター インデックスが無効です。  
  
### <a name="remarks"></a>コメント  
 指定したタブが表示されていることを保証するのにには、このメソッドを使用します。 必要な場合は、タブ コントロールがスクロールします。  
  
##  <a name="getdocumenticon"></a>  CMFCTabCtrl::GetDocumentIcon  
 タブ付きウィンドウのポップアップ メニューのタブに関連付けられているイメージを取得します。  
  
```  
static HICON __stdcall GetDocumentIcon(UINT nCmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nCmdID`  
 タブ付きウィンドウのポップアップ メニューのタブのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 ビットマップ イメージのハンドルです。  
  
##  <a name="getfirstvisibletabnum"></a>  CMFCTabCtrl::GetFirstVisibleTabNum  
 現在のタブ コントロールに表示されている最初のタブのインデックスを取得します。  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ コントロールのタブの 0 から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 Microsoft OneNote スタイルでタブ コントロールが表示される場合にのみ、このメソッドを使用します。 使用して、 [CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)スタイルを決定するメソッド。  
  
##  <a name="getresizemode"></a>  CMFCTabCtrl::GetResizeMode  
 現在のタブ コントロールのサイズを変更できる方法を指定する値を取得します。  
  
```  
ResizeMode GetResizeMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 1 つ、`CMFCTabCtrl::ResizeMode`タブ コントロールのサイズを変更できる方法を指定する列挙値。 使用可能な値の一覧は、の「解説」セクションを参照してください、 [CMFCTabCtrl::SetResizeMode](#setresizemode)メソッドです。  
  
##  <a name="getscrollbar"></a>  CMFCTabCtrl::GetScrollBar  
 タブ コントロールに関連付けられているスクロール バーのオブジェクトへのポインターを取得します。  
  
```  
CScrollBar* GetScrollBar();
```  
  
### <a name="return-value"></a>戻り値  
 スクロール バーのオブジェクトへのポインター、または`NULL`タブ コントロールを使用して作成されていない場合、`STYLE_FLAT_SHARED_HORZ_SCROLL`スタイル。  
  
### <a name="remarks"></a>コメント  
 タブ コントロールの埋め込みのスクロール バーにアクセスするのにには、このメソッドを使用します。 タブ コントロールがある場合のみ、スクロール バーのオブジェクトが作成された、`STYLE_FLAT_SHARED_HORZ_SCROLL`スタイル。  
  
##  <a name="gettabarea"></a>  CMFCTabCtrl::GetTabArea  
 上部またはタブ コントロールの下部にあるタブ ラベル領域に外接する四角形を取得します。  
  
```  
void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectTabAreaTop`  
 このメソッドが戻るとき、この参照には、最上位タブのラベル領域に外接する四角形が含まれています。 四角形は、クライアント座標でです。 この参照は、タブ コントロールの上部にあるタブ ラベルの領域が存在しない場合は、空です。  
  
 [出力] `rectTabAreaBottom`  
 このメソッドが戻るとき、この参照には、下部にあるタブ ラベル領域に外接する四角形が含まれています。 四角形は、クライアント座標でです。 この参照は、タブ コントロールの下部にあるタブ ラベルの領域が存在しない場合は、空です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、タブ付きウィンドウ内のタブ領域の位置とサイズを決定します。  
  
##  <a name="gettabmaxwidth"></a>  CMFCTabCtrl::GetTabMaxWidth  
 タブの最大幅を取得します。  
  
```  
int GetTabMaxWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、タブの最大幅。 戻り値が 0 の場合、タブの幅を制限することはありません。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)タブの最大幅を設定します。  
  
##  <a name="gettabsheight"></a>  CMFCTabCtrl::GetTabsHeight  
 現在のタブ コントロールのタブ領域の高さを取得します。  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 任意のタブが表示されている、または場合は 0 タブが表示されていない場合は、タブ領域の高さ。  
  
##  <a name="gettabsrect"></a>  CMFCTabCtrl::GetTabsRect  
 現在のタブ コントロールのタブ領域に外接する四角形を取得します。  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rect`  
 このメソッドが戻るとき、`rect`パラメーターには、タブ領域に外接する四角形が含まれています。  
  
##  <a name="getwndarea"></a>  CMFCTabCtrl::GetWndArea  
 現在のタブ コントロールのクライアント領域の境界を取得します。  
  
```  
void GetWndArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `rect`  
 このメソッドが戻るとき、このパラメーターには、現在のタブ コントロールの外接する四角形が含まれています。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hideactivewindowhorzscrollbar"></a>  CMFCTabCtrl::HideActiveWindowHorzScrollBar  
 アクティブ ウィンドウで、存在する場合は、水平スクロール バーを非表示にします。  
  
```  
void HideActiveWindowHorzScrollBar();
```  
  
### <a name="remarks"></a>コメント  
 タブ コントロールが、ユーザーがコントロールのタブ ページ間で切り替わるときに点滅していることを防ぐには、このメソッドを使用します。  
  
##  <a name="hideinactivewindow"></a>  CMFCTabCtrl::HideInactiveWindow  
 フレームワークが非アクティブなタブ コントロール ウィンドウを表示するかどうかを指定します。  
  
```  
void HideInactiveWindow(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHide`  
 `TRUE` 非アクティブなウィンドウを表示しないように`FALSE`を非アクティブなウィンドウを表示します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hidenotabs"></a>  CMFCTabCtrl::HideNoTabs  
 有効または表示されるタブが存在しない場合、タブ領域の描画を無効にします。  
  
```  
void HideNoTabs(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHide`  
 `TRUE` タブ領域の描画を有効にするには`FALSE`描画を無効にします。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hidesingletab"></a>  CMFCTabCtrl::HideSingleTab  
 有効または 1 つのタブ付きウィンドウがある場合は、タブの描画を無効にします。  
  
```  
virtual void HideSingleTab(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHide`  
 `TRUE` 1 つのタブ付きウィンドウのタブを描画しません。`FALSE`を 1 つのタブを描画します。既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isactiveinmditabgroup"></a>  CMFCTabCtrl::IsActiveInMDITabGroup  
 タブ コントロールの現在のタブがマルチ ドキュメント インターフェイスのタブ グループにアクティブなタブであるかどうかを示します。  
  
```  
BOOL IsActiveInMDITabGroup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` タブ コントロールの現在のタブが; MDI タブ グループにアクティブなタブの場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 いずれか垂直または水平タブ グループに複数のドキュメント ウィンドウを整理し、簡単に 1 つのタブ グループから別のドキュメントをランダム再生できます。  
  
##  <a name="isactivetabboldfont"></a>  CMFCTabCtrl::IsActiveTabBoldFont  
 太字のフォントを使用して、アクティブなタブのテキストを表示するかどうかを示します。  
  
```  
BOOL IsActiveTabBoldFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 太字のフォントを使用してアクティブなタブに表示されている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)アクティブなタブのフォントを変更する方法です。  
  
##  <a name="isactivetabclosebutton"></a>  CMFCTabCtrl::IsActiveTabCloseButton  
 示すかどうか閉じるボタン ( **X**) が、アクティブなタブまたはタブ領域の右上隅に表示されます。  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` [閉じる] ボタンがアクティブなタブに表示されている場合`FALSE`閉じるボタンがタブ領域の右上隅に表示される場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdrawframe"></a>  CMFCTabCtrl::IsDrawFrame  
 タブ付きウィンドウが埋め込みウィンドウの周囲のフレームの四角形を描画するかどうかを示します。  
  
```  
BOOL IsDrawFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` フレームの四角形が描画された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::SetDrawFrame](#setdrawframe)メソッドを有効にするにまたはフレームの四角形の描画を無効にします。  
  
##  <a name="isflatframe"></a>  CMFCTabCtrl::IsFlatFrame  
 タブ領域を囲むフレームがフラットまたは 3D であるかどうかを示します。  
  
```  
BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` タブ領域を囲むフレームがフラットな場合`FALSE`フレームが 3 次元の場合。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::SetFlatFrame](#setflatframe)フレームを描画する方法を変更するメソッド。  
  
##  <a name="isflattab"></a>  CMFCTabCtrl::IsFlatTab  
 現在のタブ コントロールのタブの外観がフラットかどうかを示します。  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 現在のタブ コントロールのタブの外観がフラットな場合それ以外の場合、`FALSE`です。  
  
##  <a name="isleftrightrounded"></a>  CMFCTabCtrl::IsLeftRightRounded  
 左側と右側にある現在のタブ コントロールのタブの外観が丸められるかどうかを示します。  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 各タブの辺は丸められます場合。それ以外の場合、`FALSE`です。  
  
##  <a name="ismditabgroup"></a>  CMFCTabCtrl::IsMDITabGroup  
 現在のタブ コントロールがマルチ ドキュメント インターフェイス ウィンドウのクライアント領域に含まれているかどうかを示します。  
  
```  
virtual BOOL IsMDITabGroup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 現在のタブ コントロールが MDI クライアント領域のウィンドウ以外の場合それ以外の場合、`FALSE`です。  
  
##  <a name="isonenotestyle"></a>  CMFCTabCtrl::IsOneNoteStyle  
 現在のタブ コントロールがの Microsoft OneNote スタイルで表示されるかどうかを示します。  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` Microsoft OneNote; のスタイルでタブ コントロールが表示されている場合それ以外の場合、`FALSE`です。  
  
##  <a name="issharedscroll"></a>  CMFCTabCtrl::IsSharedScroll  
 現在のタブ コントロールがグループとして、タブをスクロールできるスクロール バーを持つかどうかを示します。  
  
```  
BOOL IsSharedScroll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` タブ コントロールに共有のスクロール バーです。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る`TRUE`場合、`style`のパラメーター、 [CMFCTabCtrl::Create](#create)メソッドは STYLE_FLAT_SHARED_HORZ_SCROLL します。  
  
##  <a name="istabdocumentsmenu"></a>  CMFCTabCtrl::IsTabDocumentsMenu  
 タブ コントロールがスクロール ボタンまたはタブ付きウィンドウのメニューを表示するボタンを表示するかどうかを示します。  
  
```  
BOOL IsTabDocumentsMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` タブ付きウィンドウ ラベルのポップアップ メニューを使用してタブ付きウィンドウがスクロール可能な場合`FALSE`前方または後方スクロール ボタンを使用してタブ付きウィンドウがスクロール可能な場合です。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)タブ付きウィンドウのスクロール方法を指定するメソッド。  
  
##  <a name="isvs2005style"></a>  CMFCTabCtrl::IsVS2005Style  
 Visual Studio 2005 のスタイルを使用してタブを描画するかどうかを示します。  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` Visual Studio 2005; のスタイルを使用してタブが描画される場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用して、`style`のパラメーター、 [CMFCTabCtrl::Create](#create)タブを描画する方法を指定します。  
  
##  <a name="m_benableactivate"></a>  CMFCTabCtrl::m_bEnableActivate  
 アクティブなビューが新しいタブが挿入され、有効になっているときに、フォーカスを失うを防ぎます。  
  
```  
static BOOL m_bEnableActivate;  
```  
  
### <a name="remarks"></a>コメント  
 通常、フォーカスは新しいタブ付きウィンドウによって取得されます、タブが挿入され、アクティブになったときにします。 設定、`CMFCTabCtrl::m_bEnableActivate`メンバー変数を`FALSE`を元のフォーカスを保持します。 既定値は `TRUE` です。  
  
##  <a name="modifytabstyle"></a>  CMFCTabCtrl::ModifyTabStyle  
 現在のタブ コントロールのタブの外観を指定します。  
  
```  
BOOL ModifyTabStyle(Style style);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `style`  
 タブ コントロールの外観を指定する列挙値の 1 つ。 詳細については、「解説」表を参照してください。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE`。  
  
### <a name="remarks"></a>コメント  
 値、`style`パラメーターは、次のいずれかを指定できます`CMFCTabCtrl::Style`列挙体です。  
  
|名前|説明|  
|----------|-----------------|  
|STYLE_3D|角が丸い 3 次元の四角形のタブが表示されます。|  
|STYLE_3D_ONENOTE|1 つの側が垂直および傾斜した一方の側を持ち、角が丸い 3d のタブが表示されます。|  
|STYLE_3D_ROUNDED|辺を斜めがあり、角を丸く 3d のタブが表示されます。|  
|STYLE_3D_ROUNDED_SCROLL|辺を斜めがあり、角を丸く 3d のタブが表示されます。 同時に表示できる数以上のタブがある場合は、フレームワークは、ドロップダウン矢印とアクティブにするタブのメニューを表示します。|  
|STYLE_3D_SCROLLED|3 次元の四角形タブが表示されます。 同時に表示できる数以上のタブがある場合は、フレームワークは、ドロップダウン矢印とアクティブにするタブのメニューを表示します。|  
|STYLE_3D_VS2005|、3 d では、を持つ 1 つの傾斜側、1 つの側が垂直タブで丸められます。|  
|STYLE_FLAT|左辺と右辺が斜めになった 2 次元のタブが表示されます。|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|2 次元のタブが表示されます。 同時に表示できる数以上のタブがある場合は、フレームワークは、タブ領域の末尾にあるスクロール バーの矢印を表示します。|  
  
##  <a name="ondragenter"></a>  CMFCTabCtrl::OnDragEnter  
 カーソルが最初に現在のタブ コントロールのウィンドウに入ったとき、ドラッグ アンド ドロップ操作中に、フレームワークによって呼び出されます  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDataObject`  
 ユーザーがドラッグされるデータを含むデータ オブジェクトへのポインター。  
  
 [入力] `dwKeyState`  
 修飾子キーの状態を格納します。 このパラメーターは、次の値のビットごとの組み合わせ (OR): `MK_CONTROL`、 `MK_SHIFT`、 `MK_ALT`、 `MK_LBUTTON`、 `MK_MBUTTON`、および`MK_RBUTTON`です。 詳細については、次を参照してください。、**メッセージ パラメーター**のセクション[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)です。  
  
 [入力] `point`  
 クライアント座標で、カーソルの現在の場所が含まれています。  
  
### <a name="return-value"></a>戻り値  
 常に`DROPEFFECT_NONE`、つまり、ドロップ先がデータを受け入れることはできません。  
  
### <a name="remarks"></a>コメント  
 ドラッグ アンド ドロップ操作をサポートするために、このメソッドを使用します。 独自のカスタム動作を実装するには、このメソッドをオーバーライドします。  
  
 既定では、このメソッドのみが呼び出す`CMFCTabCtrl::OnDragOver`、常に返します`DROPEFFECT_NONE`です。  
  
##  <a name="ondragover"></a>  CMFCTabCtrl::OnDragOver  
 マウスをドロップ ターゲットのウィンドウに移動するドラッグ操作中に、フレームワークによって呼び出されます  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md)がドロップ ターゲット上にドラッグされているオブジェクト。  
  
 [入力] `dwKeyState`  
 ビットごとの組み合わせである修飾子キー (または) の状態`MK_CONTROL`、 `MK_SHIFT`、 `MK_ALT`、 `MK_LBUTTON`、 `MK_MBUTTON`、および`MK_RBUTTON`です。 詳細については、「メッセージ パラメーター」を参照してください[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)です。  
  
 [入力] `point`  
 現在、マウスの位置。  
  
### <a name="return-value"></a>戻り値  
 常に `DROPEFFECT_NONE`。  
  
### <a name="remarks"></a>コメント  
 このメソッドをカスタム実装をオーバーライドします。 詳細については、次を参照してください。、[直前](../../mfc/reference/cview-class.md#ondragover)メソッドです。  
  
##  <a name="onshowtabdocumentsmenu"></a>  CMFCTabCtrl::OnShowTabDocumentsMenu  
 タブ付きウィンドウのポップアップ メニューを表示、タブを選択し、ユーザー選択されているタブ アクティブなタブまで待機します。  
  
```  
virtual void OnShowTabDocumentsMenu(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 ポップアップ メニューを表示する場所の座標。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setactiveinmditabgroup"></a>  CMFCTabCtrl::SetActiveInMDITabGroup  
 タブ コントロールの現在のタブは、マルチ ドキュメント インターフェイスのタブ グループにアクティブなタブとして設定します。  
  
```  
void SetActiveInMDITabGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActive`  
 `TRUE` 現在のタブにアクティブなタブを作成するには`FALSE`現在のタブを非アクティブにします。  
  
### <a name="remarks"></a>コメント  
 いずれか垂直または水平タブ グループに複数のドキュメント ウィンドウを整理し、簡単に 1 つのタブ グループから別のドキュメントをランダム再生できます。  
  
##  <a name="setactivetab"></a>  CMFCTabCtrl::SetActiveTab  
 タブをアクティブにします。  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTab`  
 アクティブ化 タブの 0 から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 指定したタブがアクティブであるに行われた場合`FALSE`場合、指定した`iTab`パラメーターの値が無効です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは送信しません、`AFX_WM_CHANGE_ACTIVE_TAB`タブ コントロールの親ウィンドウに通知します。  
  
 `SetActiveTab`メソッドが自動的に呼び出し、 [CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)メソッドを画面が点滅していることを防ぐためにします。  
  
##  <a name="setactivetabboldfont"></a>  CMFCTabCtrl::SetActiveTabBoldFont  
 有効またはアクティブなタブ上の太字のフォントの使用を無効にします。  
  
```  
void SetActiveTabBoldFont(BOOL bIsBold=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsBold`  
 `TRUE` アクティブなタブのラベルを表示する太字のフォントを使用するには`FALSE`ラベルを表示する標準のフォントを使用します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdrawframe"></a>  CMFCTabCtrl::SetDrawFrame  
 埋め込まれたバーの周囲にフレームの四角形を描画するかどうかを指定します。  
  
```  
void SetDrawFrame(BOOL bDraw=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDraw`  
 `TRUE` 表示される埋め込みバーをフレームの四角形を表示するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setflatframe"></a>  CMFCTabCtrl::SetFlatFrame  
 タブ領域の周囲にフラットまたは 3D のフレームを描画するかどうかを指定します。  
  
```  
void SetFlatFrame(
    BOOL bFlat=TRUE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bFlat`  
 `TRUE` タブ領域の周りフラット (2 D) フレームを描画するには`FALSE`を 3 次元 (3 D) フレームを描画します。 既定値は `TRUE` です。  
  
 [入力] `bRepaint`  
 `TRUE` ウィンドウをすぐに再描画するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setimagelist"></a>  CMFCTabCtrl::SetImageList  
 イメージ リストを指定します。  
  
```  
virtual BOOL SetImageList(
    UINT uiID,  
    int cx=15,  
    COLORREF clrTransp=RGB(255, 0, 255));  
  
virtual BOOL SetImageList(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 イメージ リストを含むビットマップ リソースの ID。  
  
 [入力] `cx`  
 ピクセル単位の各イメージの幅。 既定値は 15 です。  
  
 [入力] `clrTransp`  
 透明な画像の色。 この色であるイメージの部分は透過的になります。 既定値は、マゼンタ、RGB(255,0,255) です。  
  
 [入力] `hImageList`  
 プリロードされているイメージ リストへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合。 `FALSE` タブ コントロールがフラット スタイルを使用して作成された場合、または最初のメソッド オーバー ロードがで指定されているビットマップを読み込むことはできません、`uiID`パラメーター。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、タブ コントロールのイメージ リストを設定できます。 タブ ラベルの横にあるイメージ リストのイメージが表示されます。 このメソッドでは、タブのサイズがイメージとテキストの両方を含めるように、タブの高さが再計算します。  
  
 使用して、 [cmfcbasetabctrl::addtab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)タブ コントロールに表示するイメージのインデックスを指定するによって継承されるメソッド。  
  
##  <a name="setresizemode"></a>  CMFCTabCtrl::SetResizeMode  
 現在のタブ コントロールのサイズを変更できる方法を指定し、し、コントロールを再表示します。  
  
```  
void SetResizeMode(ResizeMode resizeMode);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `resizeMode`  
 1 つ、`CMFCTabCtrl::ResizeMode`タブ コントロールのサイズを変更できる方法を指定する列挙値。 使用可能な値の一覧は、「解説」表を参照してください。  
  
### <a name="remarks"></a>コメント  
 `resizeMode`パラメーターは、次のいずれかを指定できます`ResizeMode`列挙値。  
  
|名前|説明|  
|----------|-----------------|  
|RESIZE_NO|タブ コントロールのサイズを変更できません。|  
|RESIZE_VERT|タブ コントロールは、いない水平、垂直方向にサイズ変更できます。|  
|RESIZE_HORIZ|タブ コントロールは、縦方向にしないが、水平方向にサイズ変更できます。|  
  
##  <a name="settabmaxwidth"></a>  CMFCTabCtrl::SetTabMaxWidth  
 タブ付きウィンドウでタブの最大幅を指定します。  
  
```  
void SetTabMaxWidth(int nTabMaxWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTabMaxWidth`  
 タブの最大幅 (ピクセル単位)。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、各タブにタブ付きウィンドウの幅を制限できます。 このメソッドは、タブのラベルが非常に長い場合に便利です。 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)クラス コンス トラクターは、実際には、幅が無制限であることを意味する 0 タブの最大幅を初期化します。  
  
##  <a name="stopresize"></a>  CMFCTabCtrl::StopResize  
 タブ コントロールの現在のサイズ変更操作を終了します。  
  
```  
void StopResize(BOOL bCancel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCancel`  
 `TRUE` 現在のサイズの変更操作を中止するのには`FALSE`現在を完了するには、操作をサイズ変更します。 どちらの場合は、フレームワークは、サイズ変更の四角形の描画を停止します。  
  
##  <a name="synchronizescrollbar"></a>  CMFCTabCtrl::SynchronizeScrollBar  
 フラット タブを表示するタブ コントロールの水平スクロール バーを描画します。  
  
```  
BOOL SynchronizeScrollBar(SCROLLINFO* pScrollInfo = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `pScrollInfo`  
 ポインター、 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造または`NULL`です。 このパラメーターがない場合、このメソッドが戻るとき`NULL`、構造体には、スクロール バーのすべてのパラメーターが含まれています。 既定値は `NULL` です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、フラットなタブを表示するタブ コントロールのみに影響します。 スクロール バーは、すべてのタブを同時に影響します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)
