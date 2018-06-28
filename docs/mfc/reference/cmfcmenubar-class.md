---
title: CMFCMenuBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar::AdjustLocations
- AFXMENUBAR/CMFCMenuBar::AllowChangeTextLabels
- AFXMENUBAR/CMFCMenuBar::AllowShowOnPaneMenu
- AFXMENUBAR/CMFCMenuBar::CalcFixedLayout
- AFXMENUBAR/CMFCMenuBar::CalcLayout
- AFXMENUBAR/CMFCMenuBar::CalcMaxButtonHeight
- AFXMENUBAR/CMFCMenuBar::CanBeClosed
- AFXMENUBAR/CMFCMenuBar::CanBeRestored
- AFXMENUBAR/CMFCMenuBar::Create
- AFXMENUBAR/CMFCMenuBar::CreateEx
- AFXMENUBAR/CMFCMenuBar::CreateFromMenu
- AFXMENUBAR/CMFCMenuBar::EnableHelpCombobox
- AFXMENUBAR/CMFCMenuBar::EnableMenuShadows
- AFXMENUBAR/CMFCMenuBar::GetAvailableExpandSize
- AFXMENUBAR/CMFCMenuBar::GetColumnWidth
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenu
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::GetFloatPopupDirection
- AFXMENUBAR/CMFCMenuBar::GetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::GetHelpCombobox
- AFXMENUBAR/CMFCMenuBar::GetHMenu
- AFXMENUBAR/CMFCMenuBar::GetMenuFont
- AFXMENUBAR/CMFCMenuBar::GetMenuItem
- AFXMENUBAR/CMFCMenuBar::GetRowHeight
- AFXMENUBAR/CMFCMenuBar::GetSystemButton
- AFXMENUBAR/CMFCMenuBar::GetSystemButtonsCount
- AFXMENUBAR/CMFCMenuBar::GetSystemMenu
- AFXMENUBAR/CMFCMenuBar::HighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsButtonExtraSizeAvailable
- AFXMENUBAR/CMFCMenuBar::IsHighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsMenuShadows
- AFXMENUBAR/CMFCMenuBar::IsRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommands
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommandsDelay
- AFXMENUBAR/CMFCMenuBar::LoadState
- AFXMENUBAR/CMFCMenuBar::OnChangeHot
- AFXMENUBAR/CMFCMenuBar::OnDefaultMenuLoaded
- AFXMENUBAR/CMFCMenuBar::OnSendCommand
- AFXMENUBAR/CMFCMenuBar::OnSetDefaultButtonText
- AFXMENUBAR/CMFCMenuBar::OnToolHitTest
- AFXMENUBAR/CMFCMenuBar::PreTranslateMessage
- AFXMENUBAR/CMFCMenuBar::RestoreOriginalstate
- AFXMENUBAR/CMFCMenuBar::SaveState
- AFXMENUBAR/CMFCMenuBar::SetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::SetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::SetMaximizeMode
- AFXMENUBAR/CMFCMenuBar::SetMenuButtonRTC
- AFXMENUBAR/CMFCMenuBar::SetMenuFont
- AFXMENUBAR/CMFCMenuBar::SetRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::SetShowAllCommands
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuBar [MFC], AdjustLocations
- CMFCMenuBar [MFC], AllowChangeTextLabels
- CMFCMenuBar [MFC], AllowShowOnPaneMenu
- CMFCMenuBar [MFC], CalcFixedLayout
- CMFCMenuBar [MFC], CalcLayout
- CMFCMenuBar [MFC], CalcMaxButtonHeight
- CMFCMenuBar [MFC], CanBeClosed
- CMFCMenuBar [MFC], CanBeRestored
- CMFCMenuBar [MFC], Create
- CMFCMenuBar [MFC], CreateEx
- CMFCMenuBar [MFC], CreateFromMenu
- CMFCMenuBar [MFC], EnableHelpCombobox
- CMFCMenuBar [MFC], EnableMenuShadows
- CMFCMenuBar [MFC], GetAvailableExpandSize
- CMFCMenuBar [MFC], GetColumnWidth
- CMFCMenuBar [MFC], GetDefaultMenu
- CMFCMenuBar [MFC], GetDefaultMenuResId
- CMFCMenuBar [MFC], GetFloatPopupDirection
- CMFCMenuBar [MFC], GetForceDownArrows
- CMFCMenuBar [MFC], GetHelpCombobox
- CMFCMenuBar [MFC], GetHMenu
- CMFCMenuBar [MFC], GetMenuFont
- CMFCMenuBar [MFC], GetMenuItem
- CMFCMenuBar [MFC], GetRowHeight
- CMFCMenuBar [MFC], GetSystemButton
- CMFCMenuBar [MFC], GetSystemButtonsCount
- CMFCMenuBar [MFC], GetSystemMenu
- CMFCMenuBar [MFC], HighlightDisabledItems
- CMFCMenuBar [MFC], IsButtonExtraSizeAvailable
- CMFCMenuBar [MFC], IsHighlightDisabledItems
- CMFCMenuBar [MFC], IsMenuShadows
- CMFCMenuBar [MFC], IsRecentlyUsedMenus
- CMFCMenuBar [MFC], IsShowAllCommands
- CMFCMenuBar [MFC], IsShowAllCommandsDelay
- CMFCMenuBar [MFC], LoadState
- CMFCMenuBar [MFC], OnChangeHot
- CMFCMenuBar [MFC], OnDefaultMenuLoaded
- CMFCMenuBar [MFC], OnSendCommand
- CMFCMenuBar [MFC], OnSetDefaultButtonText
- CMFCMenuBar [MFC], OnToolHitTest
- CMFCMenuBar [MFC], PreTranslateMessage
- CMFCMenuBar [MFC], RestoreOriginalstate
- CMFCMenuBar [MFC], SaveState
- CMFCMenuBar [MFC], SetDefaultMenuResId
- CMFCMenuBar [MFC], SetForceDownArrows
- CMFCMenuBar [MFC], SetMaximizeMode
- CMFCMenuBar [MFC], SetMenuButtonRTC
- CMFCMenuBar [MFC], SetMenuFont
- CMFCMenuBar [MFC], SetRecentlyUsedMenus
- CMFCMenuBar [MFC], SetShowAllCommands
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63e7fd651cf8a5524f3dc6c521de742ced7741ac
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039272"
---
# <a name="cmfcmenubar-class"></a>CMFCMenuBar クラス
ドッキングを実装するメニュー バーです。  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(`CMFCToolBar::AdjustLocations` をオーバーライドします)。|  
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|ツール バー ボタンのイメージの下のテキスト ラベルを表示できるかどうかを指定します。 (上書き[CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels))。|  
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(`CPane::AllowShowOnPaneMenu` をオーバーライドします)。|  
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|ツールバーの水平方向のサイズを計算します。 (上書き[CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout))。|  
|[CMFCMenuBar::CalcLayout](#calclayout)|(`CMFCToolBar::CalcLayout` をオーバーライドします)。|  
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|ツールバーのボタンの最大の高さを計算します。 (上書き[CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight))。|  
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|ユーザーがツールバーを閉じるかどうかを指定します。 (上書き[CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed))。|  
|[CMFCMenuBar::CanBeRestored](#canberestored)|システムが、カスタマイズ後ツールバーを元の状態に復元できるかどうかを判断します。 (上書き[CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored))。|  
|[CMFCMenuBar::Create](#create)|メニュー コントロールを作成し、それにアタッチ、`CMFCMenuBar`オブジェクト。|  
|[CMFCMenuBar::CreateEx](#createex)|作成、`CMFCMenuBar`追加スタイル オプションを含むオブジェクト。|  
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|初期化、`CMFCMenuBar`オブジェクト。 受け付ける、`HMENU`パラメーターを設定済みのテンプレートとして機能する`CMFCMenuBar`です。|  
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|有効な**ヘルプ**コンボ ボックス、メニュー バーの右側にあります。|  
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|ポップアップ メニューの影を表示するかどうかを指定します。|  
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(上書き[CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize))。|  
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|ツール バー ボタンの幅を返します。 (上書き[CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth))。|  
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|元のメニュー リソース ファイル内のハンドルを返します。|  
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|リソース ファイル内の元のメニュー リソース識別子を返します。|  
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||  
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||  
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|ポインターを返します、**ヘルプ**コンボ ボックス。|  
|[CMFCMenuBar::GetHMenu](#gethmenu)|アタッチされているメニューへのハンドルを返します、`CMFCMenuBar`オブジェクト。|  
|[CMFCMenuBar::GetMenuFont](#getmenufont)|メニュー オブジェクトの現在のグローバル フォントを返します。|  
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|指定した項目のインデックスに関連付けられたツール バー ボタンを返します。|  
|[CMFCMenuBar::GetRowHeight](#getrowheight)|ツール バー ボタンの高さを返します。 (上書き[CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight))。|  
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||  
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||  
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||  
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|無効なメニュー項目が強調表示されているかどうかを示します。|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|罫線を拡張したボタンをツールバーが表示できるかどうかを判断します。 (上書き[CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable))。|  
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|無効な項目が強調表示されているかどうかを示します。|  
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|ポップアップ メニューの影を描画するかどうかを示します。|  
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|メニュー バーで最近使用したメニュー コマンドを表示するかどうかを示します。|  
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|ポップアップ メニューがすべてのコマンドを表示するかどうかを示します。|  
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|メニューが短い遅延後にすべてのコマンドを表示するかどうかを示します。|  
|[CMFCMenuBar::LoadState](#loadstate)|状態を読み込み、`CMFCMenuBar`レジストリからのオブジェクト。|  
|[CMFCMenuBar::OnChangeHot](#onchangehot)|ユーザーがツールバーのボタンを選択したときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot))。|  
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|フレーム ウィンドウは、リソース ファイルから既定のメニューを読み込むときに、フレームワークによって呼び出されます。|  
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(`CMFCToolBar::OnSendCommand` をオーバーライドします)。|  
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|メニューは、カスタマイズ モードでは、ユーザーがメニュー項目のテキストを変更したときに、フレームワークによって呼び出されます。|  
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(`CMFCToolBar::OnToolHitTest` をオーバーライドします)。|  
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(`CMFCToolBar::PreTranslateMessage` をオーバーライドします)。|  
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|カスタマイズ モードにメニューがあり、ユーザーが選択したときに、フレームワークによって呼び出されます**リセット**メニュー バーのです。|  
|[CMFCMenuBar::SaveState](#savestate)|状態を保存、`CMFCMenuBar`レジストリ オブジェクト。|  
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|リソース ファイルの元のメニューを設定します。|  
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||  
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|MDI 子ウィンドウの表示モードが変更されたときに、フレームワークによって呼び出されます。 MDI 子ウィンドウが最大化新しくまたはが不要になった最大化は、このメソッドは、メニュー バーを更新します。|  
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|ユーザーのメニュー ボタンを動的に作成するときに生成されるランタイム クラス情報を設定します。|  
|[CMFCMenuBar::SetMenuFont](#setmenufont)|アプリケーションのすべてのメニューのフォントを設定します。|  
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|メニュー バーが最近使用したメニュー コマンドを表示するかどうかを指定します。|  
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|メニュー バーがすべてのコマンドを表示するかどうかを指定します。|  
  
## <a name="remarks"></a>Remarks  
 `CMFCMenuBar`クラスは、メニュー バーのドッキング機能の実装です。 ツールバーに似ていますが、終了することはできません - 常に表示されます。  
  
 `CMFCMenuBar` 最近使用したメニュー項目オブジェクトの表示オプションをサポートしています。 このオプションが有効になっている場合、`CMFCMenuBar`を最初に表示に使用できるコマンドのサブセットのみが表示されます。 その後、最近使用されたコマンドは、コマンドの元のサブセットと表示されます。 さらに、ユーザーはすべての利用可能なコマンドを表示するメニューを常に展開することができます。 したがって、使用可能な各コマンドでは、常に表示するか、最後に選択されている場合にのみ表示するには構成されます。  
  
 使用する、`CMFCMenuBar`オブジェクト、メイン ウィンドウ フレーム オブジェクトに埋め込むことです。 処理するときに、`WM_CREATE`メッセージで、呼び出す`CMFCMenuBar::Create`または`CMFCMenuBar::CreateEx`です。 関数を作成するに関係なく使用する、メイン フレーム ウィンドウにポインターを渡します。 ドッキング可能に呼び出すことによって[:enabledocking](../../mfc/reference/cframewndex-class.md#enabledocking)です。 呼び出してこのメニューをドッキング[CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane)です。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCMenuBar`クラスです。 例では、ペインのスタイルを設定、[カスタマイズ] ボタンを有効にする、ヘルプのボックスを有効にする、ポップアップ メニューは、の影を有効にするおよびメニュー バーを更新する方法を示します。 このコード スニペットの一部である、 [IE デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 `CMFCMenuBar`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxmenubar.h  
  
##  <a name="adjustlocations"></a>  CMFCMenuBar::AdjustLocations  
 メニュー バーのメニュー項目の位置を調整します。  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="allowchangetextlabels"></a>  CMFCMenuBar::AllowChangeTextLabels  
 メニュー バーの画像でテキスト ラベルは許可されているかどうかを判断します。  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`イメージの下のテキスト ラベルを表示するユーザーが選択できる場合です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="allowshowonpanemenu"></a>  CMFCMenuBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="calcfixedlayout"></a>  CMFCMenuBar::CalcFixedLayout  

  
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
  
##  <a name="calclayout"></a>  CMFCMenuBar::CalcLayout  

  
```  
virtual CSize CalcLayout(
    DWORD dwMode,  
    int nLength = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*寸法*  
 [in]*されて*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="calcmaxbuttonheight"></a>  CMFCMenuBar::CalcMaxButtonHeight  

  
```  
virtual int CalcMaxButtonHeight();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="canbeclosed"></a>  CMFCMenuBar::CanBeClosed  

  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="canberestored"></a>  CMFCMenuBar::CanBeRestored  

  
```  
virtual BOOL CanBeRestored() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="create"></a>  CMFCMenuBar::Create  
 メニュー コントロールを作成し、それにアタッチ、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクト。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT nID = AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pParentWnd*  
 新しい親ウィンドウへのポインター`CMFCMenuBar`オブジェクト。  
  
 [in]*dwStyle*  
 新しいメニュー バーのスタイルです。  
  
 [in]*nID*  
 メニュー バーの子ウィンドウの ID。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>Remarks  
 構築した後、`CMFCMenuBar`オブジェクトを呼び出す必要があります`Create`です。 このメソッドを作成、`CMFCMenuBar`を制御し、それを`CMFCMenuBar`オブジェクト。  
  
 ツール バー スタイルの詳細については、次を参照してください。 [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle)です。  
  
##  <a name="createex"></a>  CMFCMenuBar::CreateEx  
 作成、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)指定拡張スタイルを持つオブジェクト。  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    CRect rcBorders = CRect(1,
    1,
    1,
    1),  
    UINT nID =AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pParentWnd*  
 新しい親ウィンドウへのポインター`CMFCMenuBar`オブジェクト。  
  
 [in]*ツール バー*  
 新しいメニュー バーのスタイルを追加します。  
  
 [in]*dwStyle*  
 新しいメニュー バーの主なスタイル。  
  
 [in]*rcBorders*  
 A`CRect`の境界線のサイズを指定するパラメーター、`CMFCMenuBar`オブジェクト。  
  
 [in]*nID*  
 メニュー バーの子ウィンドウの ID。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 代わりにこの関数を使用する必要があります[CMFCMenuBar::Create](#create)に加えて、ツールバーのスタイルのスタイルを指定する場合。 頻繁に使用されるいくつか追加スタイルが`TBSTYLE_TRANSPARENT`と`CBRS_TOP`です。  
  
 その他のスタイルのリストは、次を参照してください。[ツール バー コントロールとボタンのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760439)、[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)、および[共通のウィンドウ スタイル](http://msdn.microsoft.com/library/windows/desktop/ms632600)です。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`CreateEx`のメソッド、`CMFCMenuBar`クラスです。 このコード スニペットの一部である、 [IE デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]  
  
##  <a name="createfrommenu"></a>  CMFCMenuBar::CreateFromMenu  
 初期化、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクト。 このメソッドのモデル、`CMFCMenuBar`オブジェクトの後に、`HMENU`パラメーター。  
  
```  
virtual void CreateFromMenu(
    HMENU hMenu,  
    BOOL bDefaultMenu = FALSE,  
    BOOL bForceUpdate = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hMenu*  
 メニュー リソースへのハンドル。 `CreateFromMenu` このリソースのテンプレートとして使用、`CMFCMenuBar`です。  
  
 [in]*bDefaultMenu*  
 新しいメニューが既定のメニューであるかどうかを示すブール値。  
  
 [in]*bForceUpdate*  
 このメソッドがメニュー更新を強制するかどうかを示すブール値。  
  
### <a name="remarks"></a>Remarks  
 同じメニュー項目をメニュー リソースとしてのメニュー コントロールをする場合は、このメソッドを使用します。 いずれかを呼び出した後は、このメソッドを呼び出す[CMFCMenuBar::Create](#create)または[CMFCMenuBar::CreateEx](#createex)です。  
  
##  <a name="enablehelpcombobox"></a>  CMFCMenuBar::EnableHelpCombobox  
 有効な**ヘルプ**コンボ ボックス、メニュー バーの右側にあります。  
  
```  
void EnableHelpCombobox(
    UINT uiID,  
    LPCTSTR lpszPrompt = NULL,  
    int nComboBoxWidth = 150);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiID*  
 コマンド ID のボタンを**ヘルプ**コンボ ボックス。  
  
 [in]*lpszPrompt*  
 空でアクティブでない場合に、フレームワークがコンボ ボックスに表示されるテキストを含む文字列です。 たとえば、「入力テキストをここで」します。  
  
 [in]*nComboBoxWidth*  
 ピクセルのコンボ ボックスのボタンの幅。  
  
### <a name="remarks"></a>Remarks  
 **ヘルプ**コンボ ボックスに似ています、**ヘルプ**のメニュー バーのコンボ ボックス[!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)]です。  
  
 このメソッドを呼び出す場合*uiID*を 0 に設定すると、このメソッドは、コンボ ボックス非表示にします。 それ以外の場合、このメソッドは、メニュー バーの右側にあるコンボ ボックスを自動的に表示します。 このメソッドを呼び出した後に呼び出す[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) 、挿入されたへのポインターを取得する[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)オブジェクト。  
  
##  <a name="enablemenushadows"></a>  CMFCMenuBar::EnableMenuShadows  
 ポップアップ メニューの影を有効にします。  
  
```  
static void EnableMenuShadows(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 ポップアップ メニューの影を有効にするかどうかを示すブール値パラメーターです。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用するアルゴリズムは複雑で、低速なシステム上のアプリケーションのパフォーマンスが低下する可能性があります。  
  
##  <a name="getavailableexpandsize"></a>  CMFCMenuBar::GetAvailableExpandSize  

  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcolumnwidth"></a>  CMFCMenuBar::GetColumnWidth  

  
```  
virtual int GetColumnWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getdefaultmenu"></a>  CMFCMenuBar::GetDefaultMenu  
 元のメニューへのハンドルを取得します。 フレームワークは、リソース ファイルから元のメニューを読み込みます。  
  
```  
HMENU GetDefaultMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションでは、メニューをカスタマイズする場合は、元のメニューへのハンドルを取得するこのメソッドを使用できます。  
  
##  <a name="getdefaultmenuresid"></a>  CMFCMenuBar::GetDefaultMenuResId  
 既定のメニューのリソース識別子を取得します。  
  
```  
UINT GetDefaultMenuResId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースの識別子。  
  
### <a name="remarks"></a>Remarks  
 フレームワークの既定のメニューを読み込みます、`CMFCMenuBar`リソース ファイルからのオブジェクト。  
  
##  <a name="getfloatpopupdirection"></a>  CMFCMenuBar::GetFloatPopupDirection  

  
```  
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pButton*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getforcedownarrows"></a>  CMFCMenuBar::GetForceDownArrows  

  
```  
BOOL GetForceDownArrows();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gethelpcombobox"></a>  CMFCMenuBar::GetHelpCombobox  
 ポインターを返します、**ヘルプ**コンボ ボックス。  
  
```  
CMFCToolBarComboBoxButton* GetHelpCombobox();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、**ヘルプ**コンボ ボックス。 `NULL` 場合、**ヘルプ**コンボ ボックスが非表示または有効になっていません。  
  
### <a name="remarks"></a>Remarks  
 **ヘルプ**コンボ ボックスは、メニュー バーの右側にあります。 メソッドを呼び出して[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)このコンボ ボックスが有効にします。  
  
##  <a name="gethmenu"></a>  CMFCMenuBar::GetHMenu  
 接続されているメニューへのハンドルを取得、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクト。  
  
```  
HMENU GetHMenu() const;  
```  
  
##  <a name="getmenufont"></a>  CMFCMenuBar::GetMenuFont  
 現在のメニューのフォントを取得します。  
  
```  
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bHorz*  
 水平または垂直のフォントを返すかどうかを指定するブール型パラメーター。 `TRUE` 水平方向のフォントを示します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CFont](../../mfc/reference/cfont-class.md)を現在のメニュー バーのフォントを含むパラメーター。  
  
### <a name="remarks"></a>Remarks  
 返されるフォントは、アプリケーションのグローバル パラメーターです。 2 つのグローバル フォントはすべて保持`CMFCMenuBar`オブジェクト。 水平および垂直方向のメニュー バーでは、これら個別のフォントが使用されます。  
  
##  <a name="getmenuitem"></a>  CMFCMenuBar::GetMenuItem  
 取得、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)項目のインデックスに基づいて、メニュー バー上のオブジェクト。  
  
```  
CMFCToolBarButton* GetMenuItem(int iItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iItem*  
 返されるメニュー項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMFCToolBarButton`で指定されたインデックスと一致するオブジェクト*iItem*です。 `NULL` 場合は、インデックスが有効ではありません。  
  
##  <a name="getrowheight"></a>  CMFCMenuBar::GetRowHeight  

  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getsystembutton"></a>  CMFCMenuBar::GetSystemButton  

  
```  
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,  
    BOOL bByCommand = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiBtn*  
 [in]*bByCommand*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getsystembuttonscount"></a>  CMFCMenuBar::GetSystemButtonsCount  

  
```  
int GetSystemButtonsCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getsystemmenu"></a>  CMFCMenuBar::GetSystemMenu  

  
```  
CMFCToolBarSystemMenuButton* GetSystemMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="highlightdisableditems"></a>  CMFCMenuBar::HighlightDisabledItems  
 フレームワークが無効なメニュー項目を強調表示するかどうかを制御します。  
  
```  
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bHighlight*  
 フレームワークが使用できないメニュー項目を強調表示するかどうかを示すブール値パラメーターです。  
  
### <a name="remarks"></a>Remarks  
 既定では、フレームワークを強調表示しません使用できないメニュー項目、ユーザーは、上にマウス ポインターを置いたときにします。  
  
##  <a name="isbuttonextrasizeavailable"></a>  CMFCMenuBar::IsButtonExtraSizeAvailable  

  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ishighlightdisableditems"></a>  CMFCMenuBar::IsHighlightDisabledItems  
 フレームワークが使用できないメニュー項目を強調表示するかどうかを示します。  
  
```  
static BOOL IsHighlightDisabledItems();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は使用できないメニュー項目が強調表示されます。それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 既定では、フレームワークを強調表示しません使用できないメニュー項目、ユーザーは、上にマウス ポインターを置いたときにします。 使用して、 [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)メソッドはこの機能を有効にします。  
  
##  <a name="ismenushadows"></a>  CMFCMenuBar::IsMenuShadows  
 フレームワークはポップアップ メニューの影を描画するかどうかを示します。  
  
```  
static BOOL IsMenuShadows();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メニュー シャドウを描画する場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 使用して、 [CMFCMenuBar::EnableMenuShadows](#enablemenushadows)メソッドを有効またはこの機能を無効にします。  
  
##  <a name="isrecentlyusedmenus"></a>  CMFCMenuBar::IsRecentlyUsedMenus  
 メニュー バーで最近使用したメニュー コマンドを表示するかどうかを示します。  
  
```  
static BOOL IsRecentlyUsedMenus();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CMFCMenuBar`オブジェクトが最近使用した表示メニュー コマンド以外の場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 関数を使用して[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)を制御するかどうか、メニュー バーが最近表示 メニューのコマンドを使用します。  
  
##  <a name="isshowallcommands"></a>  CMFCMenuBar::IsShowAllCommands  
 すべてのコマンドがメニューに表示するかどうかを示します。  
  
```  
static BOOL IsShowAllCommands();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CMFCMenuBar`すべて表示コマンド以外の場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 A`CMFCMenuBar`オブジェクトは、すべてのコマンドを表示するか、コマンドのサブセットのみを表示するように構成できます。 この機能の詳細については、次を参照してください。 [CMFCMenuBar クラス](../../mfc/reference/cmfcmenubar-class.md)です。  
  
 `IsShowAllCommands` わかるのこの機能を構成する方法、`CMFCMenuBar`オブジェクト。 表示するメニュー コマンドを制御する方法を使用[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)と[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)です。  
  
##  <a name="isshowallcommandsdelay"></a>  CMFCMenuBar::IsShowAllCommandsDelay  
 示すかどうか、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクトは、短い遅延後にすべてのコマンドを表示します。  
  
```  
static BOOL IsShowAllCommandsDelay();
```  
  
### <a name="return-value"></a>戻り値  
 メニュー バーです。 短い遅延後にすべてのメニューが表示される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 最近使用した表示項目にメニュー バーを構成するときに、メニュー バーでは、2 つの方法のいずれかでのすべてのメニューが表示されます。  
  
-   ユーザーがメニューの下部にある矢印上にカーソルを置く場合下手遅延後にすべてのメニューを表示します。  
  
-   ユーザーがメニューの下部にある矢印をクリックした後は、すべてのメニューを表示します。  
  
 既定では、すべて`CMFCMenuBar`オブジェクトは、しばらく時間がかかるの後にすべてのメニューを表示するオプションを使用します。 このオプションをプログラムで変更ことはできません、`CMFCMenuBar`クラスです。 ただし、ユーザー動作を変更できますツールバーのカスタマイズ中を使用して、**カスタマイズ** ダイアログ ボックス.  
  
##  <a name="loadstate"></a>  CMFCMenuBar::LoadState  
 Windows レジストリから、メニュー バーの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 Windows レジストリ キーのパスを含む文字列です。  
  
 [in]*nIndex*  
 メニュー バーのコントロール ID。  
  
 [in]*uiID*  
 予約済みの値。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 使用して、 [CMFCMenuBar::SaveState](#savestate)メニュー バーの状態をレジストリに保存するメソッド。 保存された情報には、メニュー項目、ドッキング状態と、メニュー バーの位置が含まれています。  
  
 ほとんどの場合、アプリケーションは呼び出しません`LoadState`です。 フレームワークは、ワークスペースの初期化時に、このメソッドを呼び出します。  
  
##  <a name="onchangehot"></a>  CMFCMenuBar::OnChangeHot  

  
```  
virtual void OnChangeHot(int iHot);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iHot*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondefaultmenuloaded"></a>  CMFCMenuBar::OnDefaultMenuLoaded  
 フレームワークは、メニュー リソース、リソース ファイルから読み込むときに、このメソッドを呼び出します。  
  
```  
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hMenu*  
 接続されているため、メニューのハンドル、`CMFCMenuBar`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装は、何も行いません。 フレームワーク メニュー リソースをリソース ファイルから読み込まれた後にカスタム コードを実行するには、この関数をオーバーライドします。  
  
##  <a name="onsendcommand"></a>  CMFCMenuBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pButton*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onsetdefaultbuttontext"></a>  CMFCMenuBar::OnSetDefaultButtonText  
 フレームワークは、ユーザーがメニュー バーで、項目のテキストを変更したときに、このメソッドを呼び出します。  
  
```  
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pButton*  
 ポインター、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)ユーザーがカスタマイズするオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` フレームワークは、メニュー バーにユーザーの変更を適用する場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドの既定の実装では、ユーザーが提供するテキストをボタンのテキストを変更します。  
  
##  <a name="ontoolhittest"></a>  CMFCMenuBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 [in]*pTI*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="pretranslatemessage"></a>  CMFCMenuBar::PreTranslateMessage  

  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pMsg*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="restoreoriginalstate"></a>  CMFCMenuBar::RestoreOriginalstate  
 ユーザーが選択したときに、フレームワークによって呼び出されます**リセット**から、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual BOOL RestoreOriginalstate();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ユーザーが選択したときに**リセット**のカスタマイズ メニューからです。 手動でプログラムによって、メニュー バーの状態をリセットするには、このメソッドを呼び出すことができます。 このメソッドは、リソース ファイルから元の状態を読み込みます。  
  
 このメソッドをオーバーライドして、ユーザーを選択すると、任意の処理を実行する場合、**リセット**オプション。  
  
##  <a name="savestate"></a>  CMFCMenuBar::SaveState  
 状態を保存、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Windows レジストリにオブジェクト。  
  
```  
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 Windows レジストリ キーのパスを含む文字列です。  
  
 [in]*nIndex*  
 メニュー バーのコントロール ID。  
  
 [in]*uiID*  
 予約済みの値。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 通常、アプリケーションは呼び出しません`SaveState`です。 フレームワークは、ワークスペースがシリアル化する場合、このメソッドを呼び出します。 詳細については、次を参照してください。 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)です。  
  
 保存された情報には、メニュー項目、ドッキング状態と、メニュー バーの位置が含まれています。  
  
##  <a name="setdefaultmenuresid"></a>  CMFCMenuBar::SetDefaultMenuResId  
 既定のメニューを設定、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクトがに基づいて、リソース id です。  
  
```  
void SetDefaultMenuResId(UINT uiResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiResId*  
 新しい既定のメニューのリソース ID です。  
  
### <a name="remarks"></a>Remarks  
 [CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)メソッドは、リソース ファイルから既定のメニューを復元します。  
  
 使用して、 [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)を使わずに既定のメニューを取得する方法です。  
  
##  <a name="setforcedownarrows"></a>  CMFCMenuBar::SetForceDownArrows  

  
```  
void SetForceDownArrows(BOOL bValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bValue*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setmaximizemode"></a>  CMFCMenuBar::SetMaximizeMode  
 MDI の表示モードを変更すると、メニュー バーを更新する必要があります、フレームワークはこのメソッドを呼び出します。  
  
```  
void SetMaximizeMode(
    BOOL bMax,  
    CWnd* pWnd = NULL,  
    BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bMax*  
 モードを指定するブール値。 詳細については、次の「解説」を参照してください。  
  
 [in]*pWnd*  
 変更の MDI 子ウィンドウへのポインター。  
  
 [in]*bRecalcLayout*  
 メニュー バーのレイアウトをすぐに計算する必要があるかどうかを指定するブール値。  
  
### <a name="remarks"></a>Remarks  
 MDI メイン フレーム ウィンドウにアタッチされているメニュー バーがシステム メニューを表示する MDI 子ウィンドウを最大表示しているときに、**最小化**、**最大化**と**閉じる**ボタン。 場合*bMax*は`TRUE`と*pWnd*は`NULL`MDI 子ウィンドウを最大化し、メニュー バーは、追加のコントロールを組み込む必要があります。 それ以外の場合、メニュー バーは、通常の状態に戻ります。  
  
##  <a name="setmenubuttonrtc"></a>  CMFCMenuBar::SetMenuButtonRTC  
 ユーザーがメニュー ボタンを作成するときにフレームワークによって使用されるランタイム クラス情報を設定します。  
  
```  
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pMenuButtonRTC*  
 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)から派生したクラスの情報、 [CMFCMenuButton クラス](../../mfc/reference/cmfcmenubutton-class.md)です。  
  
### <a name="remarks"></a>Remarks  
 ユーザーが新しいボタンをメニュー バーに追加すると、フレームワークは動的にボタンを作成します。 既定で作成`CMFCMenuButton`オブジェクト。 フレームワークによって作成される button オブジェクトの種類を変更するには、このメソッドをオーバーライドします。  
  
##  <a name="setmenufont"></a>  CMFCMenuBar::SetMenuFont  
 アプリケーションのすべてのメニュー バーのフォントを設定します。  
  
```  
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpLogFont*  
 ポインター、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/bb773327)フォント設定を定義する構造体。  
  
 [in]*bHorz*  
 場合は TRUE、 *lpLogFont*横書きフォントに使用する場合に垂直方向のフォントでは、FALSE を使用するパラメーターです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 2 つのフォントは、すべての使用`CMFCMenuBar`オブジェクト。 水平および垂直方向のメニュー バーでは、これら個別のフォントが使用されます。  
  
 フォントの設定はグローバル変数し、すべてに影響`CMFCMenuBar`オブジェクト。  
  
##  <a name="setrecentlyusedmenus"></a>  CMFCMenuBar::SetRecentlyUsedMenus  
 メニュー コマンドを使用して、メニュー バーが最近表示されるかどうかを制御します。  
  
```  
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*お*  
 最近使用したメニュー コマンドを表示するかどうかを制御するブール値。  
  
##  <a name="setshowallcommands"></a>  CMFCMenuBar::SetShowAllCommands  
 メニューが使用可能なすべてのコマンドを表示するかどうかを制御します。  
  
```  
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bShowAllCommands*  
 すべてのメニュー コマンドがポップアップ メニューに表示するかどうかを指定するブール型のパラメーターです。  
  
### <a name="remarks"></a>Remarks  
 メニューがすべてのメニュー コマンドが表示されない場合は、ほとんど使用されるコマンドが表示されません。 メニュー コマンドを表示する方法についての詳細については、次を参照してください。 [CMFCMenuBar クラス](../../mfc/reference/cmfcmenubar-class.md)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)
