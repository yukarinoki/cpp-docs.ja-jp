---
title: CPaneFrameWnd クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 02eee13928979a7d220ce03f9f61c789c6320b6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364099"
---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd クラス

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

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
|`CPaneFrameWnd::PreTranslateMessage`|クラス[CWinApp](../../mfc/reference/cwinapp-class.md)がウィンドウ メッセージを変換するために使用し、[変換メッセージ](/windows/win32/api/winuser/nf-winuser-translatemessage)および[ディスパッチ メッセージ](/windows/win32/api/winuser/nf-winuser-dispatchmessage)Windows 関数にディスパッチします。|
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

|名前|説明|
|----------|-----------------|
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|ウィンドウ クラスをCS_SAVEBITS クラス スタイルに登録するかどうかを指定します。|

## <a name="remarks"></a>解説

ペインがドッキング状態からフローティング状態に切り替わるときに、フレームワークは自動的に `CPaneFrameWnd` オブジェクトを作成します。

ミニフレーム ウィンドウは内容を表示した状態でドラッグ (直接ドッキング) するか、ドラッグ四角形を使用してドラッグ (標準ドッキング) することができます。 ミニフレームのコンテナー ペインのドッキング モードにより、ミニフレームのドラッグ動作が決まります。 詳細については[、「CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode)」を参照してください。

ミニフレーム ウィンドウには、含まれているペインのスタイルに従って、キャプションのボタンが表示されます。 ウィンドウを閉じることができる場合 ( [CBasePane::CanBeClosed](../../mfc/reference/cbasepane-class.md#canbeclosed)) 、 閉じるボタンが表示されます。 ペインにAFX_CBRS_AUTO_ROLLUPスタイルがある場合は、ピンが表示されます。

`CPaneFrameWnd` からクラスを派生させる場合は、フレームワークで作成方法を定義する必要があります。 [CPane::CreateDefaultMiniframe](../../mfc/reference/cpane-class.md#createdefaultminiframe)をオーバーライドしてクラスを作成するか、クラスの`CPane::m_pMiniFrameRTC`ランタイム クラス情報を指し示すメンバーを設定します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPaneFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxPaneFrameWnd.h

## <a name="cpaneframewndaddpane"></a><a name="addpane"></a>ウィンドウフレームウンド::ペインの追加

ペインを追加します。

```
virtual void AddPane(CBasePane* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]追加するペイン。

## <a name="cpaneframewndaddremovepanefromgloballist"></a><a name="addremovepanefromgloballist"></a>グループフレーム::グローバルリストから削除ウィンドウを追加します。

グローバル リストに対してペインを追加または削除します。

```
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,
    BOOL bAdd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]追加または削除するペイン。

*b追加*<br/>
[in]0 以外の場合は、ペインを追加します。 0 の場合は、ウィンドウを削除します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cpaneframewndadjustlayout"></a><a name="adjustlayout"></a>フレームを調整します。

ミニフレーム ウィンドウのレイアウトを調整します。

```
virtual void AdjustLayout();
```

## <a name="cpaneframewndadjustpaneframes"></a><a name="adjustpaneframes"></a>フレームフレームを調整します。

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>解説

## <a name="cpaneframewndcalcbordersize"></a><a name="calcbordersize"></a>ウィンドウ枠::カルクボーダーサイズ

ミニフレーム ウィンドウの境界線のサイズを計算します。

```
virtual void CalcBorderSize(CRect& rectBorderSize) const;
```

### <a name="parameters"></a>パラメーター

*レクトボーダーサイズ*<br/>
[アウト]ミニフレーム ウィンドウの境界線のサイズ (ピクセル単位) を格納します。

### <a name="remarks"></a>解説

このメソッドは、ミニフレーム ウィンドウの境界線のサイズを計算するために、フレームワークによって呼び出されます。 返されるサイズは、ミニフレーム ウィンドウにツールバーまたは[CDockablePane](../../mfc/reference/cdockablepane-class.md)が含まれているかどうかによって異なります。

## <a name="cpaneframewndcalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CPaneFrameWnd::カルク期待ドッキングレクト

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

*ドック*<br/>
[in]ドッキングするウィンドウへのポインター。

*ptマウス*<br/>
[in]マウスの位置。

*レクト結果*<br/>
[アウト]計算される四角形。

*タブを描く*<br/>
[アウト]TRUE の場合は、タブを描画します。FALSE の場合は、タブを描画しません。

*ターゲットバー*<br/>
[アウト]ターゲット ペインへのポインター。

### <a name="remarks"></a>解説

このメソッドは、ユーザーが *、ptMouse*で指定されたポイントにウィンドウをドラッグして、そこにドッキングした場合に、ウィンドウが占有する四角形を計算します。

## <a name="cpaneframewndcanbeattached"></a><a name="canbeattached"></a>ウィンドウフレームウンド::缶詰添付

現在のペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを判定します。

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>戻り値

ペインを別のペインまたはフレーム ウィンドウにドッキングできる場合は TRUE。それ以外の場合は FALSE。

## <a name="cpaneframewndcanbedockedtopane"></a><a name="canbedockedtopane"></a>ウィンドウフレーム::缶詰トペイン

ミニフレーム ウィンドウをペインにドッキングできるかどうかを判定します。

```
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;
```

### <a name="parameters"></a>パラメーター

*pドッキングバー*<br/>
[in]ペイン。

### <a name="return-value"></a>戻り値

ミニフレームを*pDockingBar*にドッキングできる場合は 0 以外の値を指定します。それ以外の場合は 0。

## <a name="cpaneframewndcheckgrippervisibility"></a><a name="checkgrippervisibility"></a>CPaneFrameWnd::チェックグリッパー可視性

```
virtual void CheckGripperVisibility();
```

### <a name="remarks"></a>解説

## <a name="cpaneframewndconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>ウィンドウ枠::変換タブベッドドキュメント

ペインをタブ付きドキュメントに変換します。

```
virtual void ConvertToTabbedDocument();
```

## <a name="cpaneframewndcreate"></a><a name="create"></a>CPane フレームウンド::作成

ミニフレーム ウィンドウを作成し[、CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)オブジェクトにアタッチします。

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

*名前をクリックします。*<br/>
[in]ミニフレーム ウィンドウに表示するテキストを指定します。

*Dwstyle*<br/>
[in]ウィンドウ スタイルを指定します。 詳細については、「ウィンドウ[スタイル」を](../../mfc/reference/styles-used-by-mfc.md#window-styles)参照してください。

*Rect*<br/>
[in]ミニフレーム ウィンドウの初期サイズと位置を指定します。

*pParentWnd*<br/>
[イン、アウト]ミニフレーム ウィンドウの親フレームを指定します。 この値は NULL にできません。

*pContext*<br/>
[イン、アウト]ユーザー定義のコンテキストを指定します。

### <a name="return-value"></a>戻り値

ウィンドウが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ミニフレーム ウィンドウは 2 つの手順で作成されます。 まず、フレームワークはオブジェクトを`CPaneFrameWnd`作成します。 次に、Windows`Create`ミニフレーム ウィンドウを作成し、オブジェクトにアタッチ`CPaneFrameWnd`する呼び出しです。

## <a name="cpaneframewndcreateex"></a><a name="createex"></a>ウィンドウフレーム::作成します。

ミニフレーム ウィンドウを作成し[、CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)オブジェクトにアタッチします。

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

*ドウスタイルエックス*<br/>
[in]拡張ウィンドウ スタイルを指定します。 詳細については、「[拡張ウィンドウ スタイル」を](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)参照してください。

*名前をクリックします。*<br/>
[in]ミニフレーム ウィンドウに表示するテキストを指定します。

*Dwstyle*<br/>
[in]ウィンドウ スタイルを指定します。 詳細については、「ウィンドウ[スタイル」を](../../mfc/reference/styles-used-by-mfc.md#window-styles)参照してください。

*Rect*<br/>
[in]ミニフレーム ウィンドウの初期サイズと位置を指定します。

*pParentWnd*<br/>
[イン、アウト]ミニフレーム ウィンドウの親フレームを指定します。 この値は NULL にできません。

*pContext*<br/>
[イン、アウト]ユーザー定義のコンテキストを指定します。

### <a name="return-value"></a>戻り値

ウィンドウが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ミニフレーム ウィンドウは 2 つの手順で作成されます。 まず、フレームワークはオブジェクトを`CPaneFrameWnd`作成します。 次に、Windows`Create`ミニフレーム ウィンドウを作成し、オブジェクトにアタッチ`CPaneFrameWnd`する呼び出しです。

## <a name="cpaneframewnddockpane"></a><a name="dockpane"></a>パネフレーム::Dのパネ

ペインをドッキングします。

```
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```

### <a name="parameters"></a>パラメーター

*bワスドッキング*<br/>
[アウト]ペインが既にドッキングされている場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

操作が成功した場合は、`CDockablePane`ペインがドッキングされた。それ以外の場合は NULL。

## <a name="cpaneframewndfindfloatingpanebyid"></a><a name="findfloatingpanebyid"></a>ウィンドウフレームウンド::検索フローティングペインバイID

フローティング ペインのグローバル リストで、指定したコントロール ID のペインを検索します。

```
static CBasePane* FindFloatingPaneByID(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]検索するペインのコントロール ID を表します。

### <a name="return-value"></a>戻り値

指定したコントロール ID を持つペイン。指定したコントロール ID を持つペインがない場合は NULL。

## <a name="cpaneframewndframefrompoint"></a><a name="framefrompoint"></a>フレームからポイント

指定したポイントを含むミニフレーム ウィンドウを検索します。

```
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,
    int nSensitivity,
    CPaneFrameWnd* pFrameToExclude = NULL,
    BOOL bFloatMultiOnly = FALSE);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
[in]画面座標で示した点。

*n感度*<br/>
[in]ミニフレーム ウィンドウの検索領域をこのサイズに大きくします。 ミニフレーム ウィンドウは、指定したポイントが増加した領域に入った場合に検索条件を満たします。

*を除外します。*<br/>
[in]検索から除外するミニフレーム ウィンドウを指定します。

*をクリックする*<br/>
[in]TRUE の場合は、CBRS_FLOAT_MULTIスタイルを持つミニフレーム ウィンドウのみを検索します。 FALSE の場合は、すべてのミニフレーム ウィンドウを検索します。

### <a name="return-value"></a>戻り値

*pt*を含むミニフレーム ウィンドウへのポインター。それ以外の場合は NULL。

## <a name="cpaneframewndgetcaptionheight"></a><a name="getcaptionheight"></a>ウィンドウフレームウンド::ゲットキャプションハイト

ミニフレーム ウィンドウのキャプションの高さを返します。

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>戻り値

ミニフレーム ウィンドウの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

ミニフレーム ウィンドウの高さを調べます。 デフォルトでは、高さはSM_CYSMCAPTIONに設定されています。 詳細については、「[関数の取得 」 を](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)参照してください。

## <a name="cpaneframewndgetcaptionrect"></a><a name="getcaptionrect"></a>ウィンドウフレームウンド::ゲットキャプションレクト

ミニフレーム ウィンドウのキャプションに外接する四角形を計算します。

```
virtual void GetCaptionRect(CRect& rectCaption) const;
```

### <a name="parameters"></a>パラメーター

*直流キャプション*<br/>
[アウト]ミニフレーム ウィンドウのキャプションのサイズと位置を画面座標で格納します。

### <a name="remarks"></a>解説

このメソッドは、ミニフレーム ウィンドウ キャプションの外接する四角形を計算するために、フレームワークによって呼び出されます。

## <a name="cpaneframewndgetcaptiontext"></a><a name="getcaptiontext"></a>ウィンドウフレームウィンドウ::テキストを取得します。

キャプション テキストを返します。

```
virtual CString GetCaptionText();
```

### <a name="return-value"></a>戻り値

ミニフレーム ウィンドウのキャプション テキスト。

### <a name="remarks"></a>解説

このメソッドは、キャプション テキストを表示するときにフレームワークによって呼び出されます。

## <a name="cpaneframewndgetdockingmanager"></a><a name="getdockingmanager"></a>ウィンドウフレーム::GetDockingManager

```
CDockingManager* GetDockingManager() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpaneframewndgetdockingmode"></a><a name="getdockingmode"></a>ウィンドウフレーム::GetDockingモード

ドッキングのモードを返します。

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>戻り値

ドッキング モード。 次のいずれかの値:

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

## <a name="cpaneframewndgetfirstvisiblepane"></a><a name="getfirstvisiblepane"></a>ウィンドウフレーム分割::最初に見えるペイン

ミニフレーム ウィンドウに含まれる最初の可視ペインを返します。

```
virtual CWnd* GetFirstVisiblePane() const;
```

### <a name="return-value"></a>戻り値

ミニフレーム ウィンドウの最初のペイン、またはミニフレーム ウィンドウにペインが含まれている場合は NULL。

## <a name="cpaneframewndgethotpoint"></a><a name="gethotpoint"></a>ウィンドウフレームウンド::ゲットホットポイント

```
CPoint GetHotPoint() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpaneframewndgetpane"></a><a name="getpane"></a>ウィンドウフレームウンド::ゲットペイン

ミニフレーム ウィンドウに含まれるペインを返します。

```
virtual CWnd* GetPane() const;
```

### <a name="return-value"></a>戻り値

ミニフレームに含まれるペイン。

### <a name="remarks"></a>解説

## <a name="cpaneframewndgetpanecount"></a><a name="getpanecount"></a>ウィンドウフレームウンド::取得ペインカウント

ミニフレーム ウィンドウに含まれるペインの数を返します。

```
virtual int GetPaneCount() const;
```

### <a name="return-value"></a>戻り値

ミニフレーム ウィンドウのペインの数。 この値はゼロの場合があります。

### <a name="remarks"></a>解説

## <a name="cpaneframewndgetparent"></a><a name="getparent"></a>ウィンドウフレーム::ゲットペアレント

```
CWnd* GetParent();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpaneframewndgetpinstate"></a><a name="getpinstate"></a>ウィンドウフレームウンド::GetPinState

```
BOOL GetPinState() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpaneframewndgetrecentfloatingrect"></a><a name="getrecentfloatingrect"></a>ウィンドウフレームウンド::ゲットRecentフローティングレクト

```
CRect GetRecentFloatingRect() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpaneframewndgetvisiblepanecount"></a><a name="getvisiblepanecount"></a>ウィンドウフレーム分割:::取得VisiblePaneカウント

ミニフレーム ウィンドウに含まれる可視ペインの数を返します。

```
virtual int GetVisiblePaneCount() const;
```

### <a name="return-value"></a>戻り値

表示されるペインの数。

### <a name="remarks"></a>解説

## <a name="cpaneframewndhittest"></a><a name="hittest"></a>ウィンドウフレーム::ヒットテスト

特定のポイントに、ミニフレーム ウィンドウのどの部分があるか判定します。

```
virtual LRESULT HitTest(
    CPoint point,
    BOOL bDetectCaption);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]テストするポイント。

*を検出します。*<br/>
[in]TRUE の場合は、キャプションに対してポイントを確認します。 FALSE の場合は、キャプションを無視します。

### <a name="return-value"></a>戻り値

次のいずれかの値:

|[値]|意味|
|-----------|-------------|
|HTNOWHERE|ポイントはミニフレーム ウィンドウの外側にあります。|
|HTクライアント|ポイントはクライアント領域にあります。|
|HTキャプション|ポイントはキャプションにあります。|
|HTTOP|ポイントは一番上にあります。|
|HTTOPLEFT|ポイントは左上にあります。|
|HTTOPRIGHT|ポイントは右上にあります。|
|HTレフト|ポイントは左側にあります。|
|HTRIGHT|ポイントは右にあります。|
|HTボトム|ポイントは一番下にあります。|
|HTボトムレフト|ポイントは左下にあります。|
|HTボトムライト|ポイントは右下にあります。|

## <a name="cpaneframewndiscaptured"></a><a name="iscaptured"></a>CPaneFrameWnd::キャプチャー

```
BOOL IsCaptured() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpaneframewndisdelayshow"></a><a name="isdelayshow"></a>ウィンドウフレーム::イズディレイショー

```
BOOL IsDelayShow() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cpaneframewndisrolldown"></a><a name="isrolldown"></a>ウィンドウフレームウンド::イズロールダウン

ミニフレーム ウィンドウをロール ダウンするかどうかを判断します。

```
virtual BOOL IsRollDown() const;
```

### <a name="return-value"></a>戻り値

ミニフレーム ウィンドウをロール ダウンする必要がある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ミニフレーム ウィンドウをロール ダウンするかどうかを決定するために、フレームワークによって呼び出されます。 ミニフレーム ウィンドウにAFX_CBRS_AUTO_ROLLUP フラグを持つペインが少なくとも 1 つ含まれている場合、ロールアップ/ロールダウン機能は有効になります。 このフラグは、ペインの作成時に設定されます。 詳細については[、「CBasePane::CreateEx」](../../mfc/reference/cbasepane-class.md#createex)を参照してください。

既定では、フレームワークは、ミニフレーム ウィンドウの境界領域内にマウス ポインターがあるかどうかをチェックして、ウィンドウをロール ダウンする必要があるかどうかを判断します。 この動作は、派生クラスでオーバーライドできます。

## <a name="cpaneframewndisrollup"></a><a name="isrollup"></a>ウィンドウフレームウンド::イズロールアップ

ミニフレーム ウィンドウをロール アップするかどうかを判断します。

```
virtual BOOL IsRollUp() const;
```

### <a name="return-value"></a>戻り値

ミニフレーム ウィンドウをロールアップする必要がある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ミニフレーム ウィンドウをロールアップするかどうかを決定するために、フレームワークによって呼び出されます。 ミニフレーム ウィンドウにAFX_CBRS_AUTO_ROLLUP フラグを持つペインが少なくとも 1 つ含まれている場合、ロールアップ/ロールダウン機能は有効になります。 このフラグは、ペインの作成時に設定されます。 詳細については[、「CBasePane::CreateEx」](../../mfc/reference/cbasepane-class.md#createex)を参照してください。

既定では、フレームワークは、ミニフレーム ウィンドウの境界領域内にマウス ポインターがあるかどうかをチェックして、ウィンドウをロールアップする必要があるかどうかを判断します。 この動作は、派生クラスでオーバーライドできます。

## <a name="cpaneframewndkilldockingtimer"></a><a name="killdockingtimer"></a>CPaneFrameWnd::キルドッキングタイマー

ドッキング タイマーを停止します。

```
void KillDockingTimer();
```

## <a name="cpaneframewndloadstate"></a><a name="loadstate"></a>ウィンドウフレーム::ロードステート

レジストリからペインの状態を読み込みます。

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]プロファイル名。

*Uiid*<br/>
[in]ペイン ID。

### <a name="return-value"></a>戻り値

ペインの状態が正常に読み込まれた場合は TRUE。それ以外の場合は FALSE。

## <a name="cpaneframewndm_busesavebits"></a><a name="m_busesavebits"></a>ウィンドウフレーム::m_bUseSaveBits

CS_SAVEBITS クラス スタイルを持つウィンドウ クラスを登録するかどうかを指定します。

```
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;
```

### <a name="remarks"></a>解説

この静的メンバーを TRUE に設定すると、CS_SAVEBITS スタイルを持つミニフレーム ウィンドウ クラスが登録されます。 これにより、ユーザーがミニフレーム ウィンドウをドラッグしたときにちらつきが少なくなることがあります。

## <a name="cpaneframewndonbeforedock"></a><a name="onbeforedock"></a>ウィンドウフレーム::オン・ウオーニング

ドッキングが可能かどうかを判定します。

```
virtual BOOL OnBeforeDock();
```

### <a name="return-value"></a>戻り値

ドッキングが可能な場合は TRUE。それ以外の場合は FALSE。

## <a name="cpaneframewndoncheckrollstate"></a><a name="oncheckrollstate"></a>ウィンドウフレーム::オンチェックロールステート

ミニフレーム ウィンドウをロール アップまたはロール ダウンするかどうかを判断します。

```
virtual void OnCheckRollState();
```

### <a name="remarks"></a>解説

このメソッドは、ミニフレーム ウィンドウをロール アップするか、または下に重ねるかを決定するために、フレームワークによって呼び出されます。

既定では、フレームワークは[CPaneFrameWnd::IsRollUp](#isrollup)と[CPaneFrameWnd::IsRollDown](#isrolldown)を呼び出し、ミニフレーム ウィンドウを伸縮または復元するだけです。 派生クラスでこのメソッドをオーバーライドして、別の視覚効果を使用できます。

## <a name="cpaneframewndondocktorecentpos"></a><a name="ondocktorecentpos"></a>ウィンドウフレーム::オンドックト最近のポス

ミニフレーム ウィンドウを直前の位置にドッキングします。

```
virtual void OnDockToRecentPos();
```

## <a name="cpaneframewndondrawborder"></a><a name="ondrawborder"></a>ウィンドウ枠::オンドローボーダー

ミニフレーム ウィンドウの境界線を描画します。

```
virtual void OnDrawBorder(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]境界線の描画に使用されるデバイス コンテキスト。

### <a name="remarks"></a>解説

このメソッドは、ミニフレーム ウィンドウの境界線を描画するためにフレームワークによって呼び出されます。

## <a name="cpaneframewndonkillrolluptimer"></a><a name="onkillrolluptimer"></a>ウィンドウフレームウンド::オンキルロールアップタイマー

ロールアップ タイマーを停止します。

```
virtual void OnKillRollUpTimer();
```

## <a name="cpaneframewndonmovepane"></a><a name="onmovepane"></a>ウィンドウフレーム::オンムーブペイン

ミニフレーム ウィンドウを指定したオフセットだけ移動します。

```
virtual void OnMovePane(
    CPane* pBar,
    CPoint ptOffset);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]ペインへのポインター (無視)。

*ptオフセット*<br/>
[in]ペインの移動に使用するオフセット。

## <a name="cpaneframewndonpanerecalclayout"></a><a name="onpanerecalclayout"></a>ウィンドウフレーム::オンパネレカルクレイアウト

ミニフレーム ウィンドウ内のペインのレイアウトを調整します。

```
virtual void OnPaneRecalcLayout();
```

### <a name="remarks"></a>解説

フレームワークは、ミニフレーム ウィンドウ内のペインのレイアウトを調整する必要がある場合に、このメソッドを呼び出します。

既定では、ミニフレーム ウィンドウの完全なクライアント領域をカバーするペインが配置されます。

## <a name="cpaneframewndonsetrolluptimer"></a><a name="onsetrolluptimer"></a>CPane フレームオンド::オンセットロールアップタイマー

ロールアップ タイマーを設定します。

```
virtual void OnSetRollUpTimer();
```

## <a name="cpaneframewndonshowpane"></a><a name="onshowpane"></a>ウィンドウ枠::オンショーペイン

ミニフレーム ウィンドウ内のペインが非表示になるとき、または表示されるときに、フレームワークによって呼び出されます。

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]表示または非表示になっているペイン。

*bショー*<br/>
[in]ペインが表示されている場合は TRUE。ウィンドウが非表示になっている場合は FALSE。

### <a name="remarks"></a>解説

ミニフレーム ウィンドウのペインが表示または非表示のときに、フレームワークによって呼び出されます。 既定の実装では、何も行われません。

## <a name="cpaneframewndpin"></a><a name="pin"></a>ウィンドウフレーム::Pイン

```
void Pin(BOOL bPin = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*bピン*<br/>

### <a name="remarks"></a>解説

## <a name="cpaneframewndpanefrompoint"></a><a name="panefrompoint"></a>ウィンドウフレーム::Pアネのフロトポイント

ユーザーが指定した位置がミニフレーム ウィンドウ内のペインに含まれている場合、そのペインを返します。

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    BOOL bCheckVisibility);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]ユーザーがクリックしたポイントを画面座標で指定します。

*n感度*<br/>
[in]このパラメーターは使用されません。

*可視性を確認する*<br/>
[in]表示されているペインのみを返す場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ユーザーがクリックしたペイン、またはその場所にペインが存在しない場合は NULL。

### <a name="remarks"></a>解説

指定したポイントを含むペインを取得します。

## <a name="cpaneframewndredrawall"></a><a name="redrawall"></a>ウィンドウフレームウンド::すべてを再描画

すべてのミニフレーム ウィンドウを再描画します。

```
static void RedrawAll();
```

### <a name="remarks"></a>解説

このメソッドは、各ウィンドウの[CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow)を呼び出すことによって、すべてのミニフレーム ウィンドウを更新します。

## <a name="cpaneframewndremovenonvalidpanes"></a><a name="removenonvalidpanes"></a>ウィンドウフレーム::削除非有効なペイン

有効でないウィンドウを削除するために、フレームワークによって呼び出されます。

```
virtual void RemoveNonValidPanes();
```

## <a name="cpaneframewndremovepane"></a><a name="removepane"></a>ウィンドウフレーム::ウィンドウの削除

ミニフレーム ウィンドウから、ペインを削除します。

```
virtual void RemovePane(
    CBasePane* pWnd,
    BOOL bDestroy = FALSE,
    BOOL bNoDelayedDestroy = FALSE);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]削除するペインへのポインター。

*bデストロイ*<br/>
[in]ミニフレーム ウィンドウに対する動作を指定します。 *bDestroy*が TRUE の場合、このメソッドはミニフレーム ウィンドウを即座に破棄します。 FALSE の場合、このメソッドは、一定の遅延後にミニフレーム ウィンドウを破棄します。

*遅延デストロイ*<br/>
[in]TRUE の場合、遅延破棄は無効になります。 FALSE の場合、遅延破壊が有効になります。

### <a name="remarks"></a>解説

フレームワークは、ミニフレーム ウィンドウをすぐに、または特定の遅延の後に破棄できます。 ミニフレーム ウィンドウの破棄を遅延する場合は *、bNoDelayedDestroy*パラメーターに FALSE を渡します。 遅延破棄は、フレームワークがAFX_WM_CHECKEMPTYMINIFRAME メッセージを処理するときに発生します。

## <a name="cpaneframewndreplacepane"></a><a name="replacepane"></a>ウィンドウフレーム::ペインを置き換える

ペインを別のペインに置き換えます。

```
virtual void ReplacePane(
    CBasePane* pBarOrg,
    CBasePane* pBarReplaceWith);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]元のペインへのポインター。

*置き換える*<br/>
[in]元のペインを置き換えるペインへのポインター。

## <a name="cpaneframewndsavestate"></a><a name="savestate"></a>ウィンドウフレーム::セーブステート

レジストリにペインの状態を保存します。

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]プロファイル名。

*Uiid*<br/>
[in]ペイン ID。

### <a name="return-value"></a>戻り値

ペインの状態が正常に保存された場合は TRUE。それ以外の場合は FALSE。

## <a name="cpaneframewndsetcaptionbuttons"></a><a name="setcaptionbuttons"></a>ウィンドウ枠::セットキャプションボタン

キャプションのボタンを設定します。

```
virtual void SetCaptionButtons(DWORD dwButtons);
```

### <a name="parameters"></a>パラメーター

*dwボタン*<br/>
[in]次の値のビットごとの OR の組み合わせ:

- AFX_CAPTION_BTN_CLOSE

- AFX_CAPTION_BTN_PIN

- AFX_CAPTION_BTN_MENU

- AFX_CAPTION_BTN_CUSTOMIZE

## <a name="cpaneframewndsetdelayshow"></a><a name="setdelayshow"></a>ウィンドウフレーム:::セットディレイショー

```
void SetDelayShow(BOOL bDelayShow);
```

### <a name="parameters"></a>パラメーター

[in]*ビディレイショー*<br/>

### <a name="remarks"></a>解説

## <a name="cpaneframewndsetdockingmanager"></a><a name="setdockingmanager"></a>ウィンドウフレーム::セットドッキングマネージャー

```
void SetDockingManager(CDockingManager* pManager);
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>

### <a name="remarks"></a>解説

## <a name="cpaneframewndsetdockingtimer"></a><a name="setdockingtimer"></a>ウィンドウフレーム::セットドッキングタイマー

ドッキング タイマーを設定します。

```
void SetDockingTimer(UINT nTimeOut);
```

### <a name="parameters"></a>パラメーター

*アウト*<br/>
[in]タイムアウト値 (ミリ秒単位)。

## <a name="cpaneframewndsetdockstate"></a><a name="setdockstate"></a>ウィンドウフレームオード::セットドックステート

ドッキング状態を設定します。

```
virtual void SetDockState(CDockingManager* pDockManager);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ドッキング マネージャーへのポインター。

## <a name="cpaneframewndsethotpoint"></a><a name="sethotpoint"></a>ウィンドウフレーム::セットホットポイント

```
void SetHotPoint(CPoint& ptNew);
```

### <a name="parameters"></a>パラメーター

[in]*ptNew*<br/>

### <a name="remarks"></a>解説

## <a name="cpaneframewndsetpredockstate"></a><a name="setpredockstate"></a>ウィンドウフレームオード::セットプレドックステート

ドッキング前の状態を設定するために、フレームワークによって呼び出されます。

```
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,
    CBasePane* pBarToDock = NULL,
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```

### <a name="parameters"></a>パラメーター

*プレドックステート*<br/>
[in]指定できる値:

- PDS_NOTHING、

- PDS_DOCK_REGULAR、

- PDS_DOCK_TO_TAB

*をクリックします。*<br/>
[in]ドッキングするペインへのポインター。

*ドックメソッド*<br/>
[in]ドッキング方法。 (このパラメーターは無視されます。

### <a name="return-value"></a>戻り値

ミニフレーム ウィンドウがドッキングされていない場合は TRUE。ドッキングされている場合は FALSE。

## <a name="cpaneframewndsizetocontent"></a><a name="sizetocontent"></a>ウィンドウフレーム::サイズコンテンツ

ミニフレーム ウィンドウのサイズを調整して、含まれているペインと同じになるようにします。

```
virtual void SizeToContent();
```

### <a name="remarks"></a>解説

ミニフレーム ウィンドウのサイズを、含まれているペインのサイズに調整します。

## <a name="cpaneframewndstarttearoff"></a><a name="starttearoff"></a>ウィンドウフレームウンド::スタートティアオフ

メニューをティアオフします。

```
BOOL StartTearOff(CMFCPopu* pMenu);
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
[in]メニューへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cpaneframewndstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>ウィンドウフレーム:::ストア最近ドックサイト情報

```
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

### <a name="remarks"></a>解説

## <a name="cpaneframewndstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>ウィンドウ枠:::ストア最近タブ関連情報

```
virtual void StoreRecentTabRelatedInfo(
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
[CWnd クラス](../../mfc/reference/cwnd-class.md)
