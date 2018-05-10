---
title: CWnd クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWnd
- AFXWIN/CWnd
- AFXWIN/CWnd::CWnd
- AFXWIN/CWnd::accDoDefaultAction
- AFXWIN/CWnd::accHitTest
- AFXWIN/CWnd::accLocation
- AFXWIN/CWnd::accNavigate
- AFXWIN/CWnd::accSelect
- AFXWIN/CWnd::AnimateWindow
- AFXWIN/CWnd::ArrangeIconicWindows
- AFXWIN/CWnd::Attach
- AFXWIN/CWnd::BeginModalState
- AFXWIN/CWnd::BeginPaint
- AFXWIN/CWnd::BindDefaultProperty
- AFXWIN/CWnd::BindProperty
- AFXWIN/CWnd::BringWindowToTop
- AFXWIN/CWnd::CalcWindowRect
- AFXWIN/CWnd::CancelToolTips
- AFXWIN/CWnd::CenterWindow
- AFXWIN/CWnd::ChangeClipboardChain
- AFXWIN/CWnd::CheckDlgButton
- AFXWIN/CWnd::CheckRadioButton
- AFXWIN/CWnd::ChildWindowFromPoint
- AFXWIN/CWnd::ClientToScreen
- AFXWIN/CWnd::CloseWindow
- AFXWIN/CWnd::ContinueModal
- AFXWIN/CWnd::Create
- AFXWIN/CWnd::CreateAccessibleProxy
- AFXWIN/CWnd::CreateCaret
- AFXWIN/CWnd::CreateControl
- AFXWIN/CWnd::CreateEx
- AFXWIN/CWnd::CreateGrayCaret
- AFXWIN/CWnd::CreateSolidCaret
- AFXWIN/CWnd::DeleteTempMap
- AFXWIN/CWnd::DestroyWindow
- AFXWIN/CWnd::Detach
- AFXWIN/CWnd::DlgDirList
- AFXWIN/CWnd::DlgDirListComboBox
- AFXWIN/CWnd::DlgDirSelect
- AFXWIN/CWnd::DlgDirSelectComboBox
- AFXWIN/CWnd::DragAcceptFiles
- AFXWIN/CWnd::DragDetect
- AFXWIN/CWnd::DrawAnimatedRects
- AFXWIN/CWnd::DrawCaption
- AFXWIN/CWnd::DrawMenuBar
- AFXWIN/CWnd::EnableActiveAccessibility
- AFXWIN/CWnd::EnableDynamicLayout
- AFXWIN/CWnd::EnableD2DSupport
- AFXWIN/CWnd::EnableScrollBar
- AFXWIN/CWnd::EnableScrollBarCtrl
- AFXWIN/CWnd::EnableToolTips
- AFXWIN/CWnd::EnableTrackingToolTips
- AFXWIN/CWnd::EnableWindow
- AFXWIN/CWnd::EndModalLoop
- AFXWIN/CWnd::EndModalState
- AFXWIN/CWnd::EndPaint
- AFXWIN/CWnd::ExecuteDlgInit
- AFXWIN/CWnd::FilterToolTipMessage
- AFXWIN/CWnd::FindWindow
- AFXWIN/CWnd::FindWindowEx
- AFXWIN/CWnd::FlashWindow
- AFXWIN/CWnd::FlashWindowEx
- AFXWIN/CWnd::FromHandle
- AFXWIN/CWnd::FromHandlePermanent
- AFXWIN/CWnd::get_accChild
- AFXWIN/CWnd::get_accChildCount
- AFXWIN/CWnd::get_accDefaultAction
- AFXWIN/CWnd::get_accDescription
- AFXWIN/CWnd::get_accFocus
- AFXWIN/CWnd::get_accHelp
- AFXWIN/CWnd::get_accHelpTopic
- AFXWIN/CWnd::get_accKeyboardShortcut
- AFXWIN/CWnd::get_accName
- AFXWIN/CWnd::get_accParent
- AFXWIN/CWnd::get_accRole
- AFXWIN/CWnd::get_accSelection
- AFXWIN/CWnd::get_accState
- AFXWIN/CWnd::get_accValue
- AFXWIN/CWnd::GetActiveWindow
- AFXWIN/CWnd::GetAncestor
- AFXWIN/CWnd::GetCapture
- AFXWIN/CWnd::GetCaretPos
- AFXWIN/CWnd::GetCheckedRadioButton
- AFXWIN/CWnd::GetClientRect
- AFXWIN/CWnd::GetClipboardOwner
- AFXWIN/CWnd::GetClipboardViewer
- AFXWIN/CWnd::GetControlUnknown
- AFXWIN/CWnd::GetDC
- AFXWIN/CWnd::GetDCEx
- AFXWIN/CWnd::GetDCRenderTarget
- AFXWIN/CWnd::GetDescendantWindow
- AFXWIN/CWnd::GetDesktopWindow
- AFXWIN/CWnd::GetDlgCtrlID
- AFXWIN/CWnd::GetDlgItem
- AFXWIN/CWnd::GetDlgItemInt
- AFXWIN/CWnd::GetDlgItemText
- AFXWIN/CWnd::GetDSCCursor
- AFXWIN/CWnd::GetDynamicLayout
- AFXWIN/CWnd::GetExStyle
- AFXWIN/CWnd::GetFocus
- AFXWIN/CWnd::GetFont
- AFXWIN/CWnd::GetForegroundWindow
- AFXWIN/CWnd::GetIcon
- AFXWIN/CWnd::GetLastActivePopup
- AFXWIN/CWnd::GetLayeredWindowAttributes
- AFXWIN/CWnd::GetMenu
- AFXWIN/CWnd::GetNextDlgGroupItem
- AFXWIN/CWnd::GetNextDlgTabItem
- AFXWIN/CWnd::GetNextWindow
- AFXWIN/CWnd::GetOleControlSite
- AFXWIN/CWnd::GetOpenClipboardWindow
- AFXWIN/CWnd::GetOwner
- AFXWIN/CWnd::GetParent
- AFXWIN/CWnd::GetParentFrame
- AFXWIN/CWnd::GetParentOwner
- AFXWIN/CWnd::GetProperty
- AFXWIN/CWnd::GetRenderTarget
- AFXWIN/CWnd::GetSafeHwnd
- AFXWIN/CWnd::GetSafeOwner
- AFXWIN/CWnd::GetScrollBarCtrl
- AFXWIN/CWnd::GetScrollBarInfo
- AFXWIN/CWnd::GetScrollInfo
- AFXWIN/CWnd::GetScrollLimit
- AFXWIN/CWnd::GetScrollPos
- AFXWIN/CWnd::GetScrollRange
- AFXWIN/CWnd::GetStyle
- AFXWIN/CWnd::GetSystemMenu
- AFXWIN/CWnd::GetTitleBarInfo
- AFXWIN/CWnd::GetTopLevelFrame
- AFXWIN/CWnd::GetTopLevelOwner
- AFXWIN/CWnd::GetTopLevelParent
- AFXWIN/CWnd::GetTopWindow
- AFXWIN/CWnd::GetUpdateRect
- AFXWIN/CWnd::GetUpdateRgn
- AFXWIN/CWnd::GetWindow
- AFXWIN/CWnd::GetWindowContextHelpId
- AFXWIN/CWnd::GetWindowDC
- AFXWIN/CWnd::GetWindowedChildCount
- AFXWIN/CWnd::GetWindowInfo
- AFXWIN/CWnd::GetWindowlessChildCount
- AFXWIN/CWnd::GetWindowPlacement
- AFXWIN/CWnd::GetWindowRect
- AFXWIN/CWnd::GetWindowRgn
- AFXWIN/CWnd::GetWindowText
- AFXWIN/CWnd::GetWindowTextLength
- AFXWIN/CWnd::HideCaret
- AFXWIN/CWnd::HiliteMenuItem
- AFXWIN/CWnd::HtmlHelp
- AFXWIN/CWnd::Invalidate
- AFXWIN/CWnd::InvalidateRect
- AFXWIN/CWnd::InvalidateRgn
- AFXWIN/CWnd::InvokeHelper
- AFXWIN/CWnd::IsChild
- AFXWIN/CWnd::IsD2DSupportEnabled
- AFXWIN/CWnd::IsDialogMessage
- AFXWIN/CWnd::IsDlgButtonChecked
- AFXWIN/CWnd::IsDynamicLayoutEnabled
- AFXWIN/CWnd::IsIconic
- AFXWIN/CWnd::IsTouchWindow
- AFXWIN/CWnd::IsWindowEnabled
- AFXWIN/CWnd::IsWindowVisible
- AFXWIN/CWnd::IsZoomed
- AFXWIN/CWnd::KillTimer
- AFXWIN/CWnd::LockWindowUpdate
- AFXWIN/CWnd::MapWindowPoints
- AFXWIN/CWnd::MessageBox
- AFXWIN/CWnd::ModifyStyle
- AFXWIN/CWnd::ModifyStyleEx
- AFXWIN/CWnd::MoveWindow
- AFXWIN/CWnd::NotifyWinEvent
- AFXWIN/CWnd::OnAmbientProperty
- AFXWIN/CWnd::OnDrawIconicThumbnailOrLivePreview
- AFXWIN/CWnd::OnHelp
- AFXWIN/CWnd::OnHelpFinder
- AFXWIN/CWnd::OnHelpIndex
- AFXWIN/CWnd::OnHelpUsing
- AFXWIN/CWnd::OnToolHitTest
- AFXWIN/CWnd::OpenClipboard
- AFXWIN/CWnd::PaintWindowlessControls
- AFXWIN/CWnd::PostMessage
- AFXWIN/CWnd::PreCreateWindow
- AFXWIN/CWnd::PreSubclassWindow
- AFXWIN/CWnd::PreTranslateMessage
- AFXWIN/CWnd::Print
- AFXWIN/CWnd::PrintClient
- AFXWIN/CWnd::PrintWindow
- AFXWIN/CWnd::RedrawWindow
- AFXWIN/CWnd::RegisterTouchWindow
- AFXWIN/CWnd::ReleaseDC
- AFXWIN/CWnd::RepositionBars
- AFXWIN/CWnd::RunModalLoop
- AFXWIN/CWnd::ScreenToClient
- AFXWIN/CWnd::ScrollWindow
- AFXWIN/CWnd::ScrollWindowEx
- AFXWIN/CWnd::SendChildNotifyLastMsg
- AFXWIN/CWnd::SendDlgItemMessage
- AFXWIN/CWnd::SendMessage
- AFXWIN/CWnd::SendMessageToDescendants
- AFXWIN/CWnd::SendNotifyMessage
- AFXWIN/CWnd::SetActiveWindow
- AFXWIN/CWnd::SetCapture
- AFXWIN/CWnd::SetCaretPos
- AFXWIN/CWnd::SetClipboardViewer
- AFXWIN/CWnd::SetDlgCtrlID
- AFXWIN/CWnd::SetDlgItemInt
- AFXWIN/CWnd::SetDlgItemText
- AFXWIN/CWnd::SetFocus
- AFXWIN/CWnd::SetFont
- AFXWIN/CWnd::SetForegroundWindow
- AFXWIN/CWnd::SetIcon
- AFXWIN/CWnd::SetLayeredWindowAttributes
- AFXWIN/CWnd::SetMenu
- AFXWIN/CWnd::SetOwner
- AFXWIN/CWnd::SetParent
- AFXWIN/CWnd::SetProperty
- AFXWIN/CWnd::SetRedraw
- AFXWIN/CWnd::SetScrollInfo
- AFXWIN/CWnd::SetScrollPos
- AFXWIN/CWnd::SetScrollRange
- AFXWIN/CWnd::SetTimer
- AFXWIN/CWnd::SetWindowContextHelpId
- AFXWIN/CWnd::SetWindowPlacement
- AFXWIN/CWnd::SetWindowPos
- AFXWIN/CWnd::SetWindowRgn
- AFXWIN/CWnd::SetWindowText
- AFXWIN/CWnd::ShowCaret
- AFXWIN/CWnd::ShowOwnedPopups
- AFXWIN/CWnd::ShowScrollBar
- AFXWIN/CWnd::ShowWindow
- AFXWIN/CWnd::SubclassDlgItem
- AFXWIN/CWnd::SubclassWindow
- AFXWIN/CWnd::UnlockWindowUpdate
- AFXWIN/CWnd::UnsubclassWindow
- AFXWIN/CWnd::UpdateData
- AFXWIN/CWnd::UpdateDialogControls
- AFXWIN/CWnd::UpdateLayeredWindow
- AFXWIN/CWnd::UpdateWindow
- AFXWIN/CWnd::ValidateRect
- AFXWIN/CWnd::ValidateRgn
- AFXWIN/CWnd::WindowFromPoint
- AFXWIN/CWnd::WinHelp
- AFXWIN/CWnd::Default
- AFXWIN/CWnd::DefWindowProc
- AFXWIN/CWnd::DoDataExchange
- AFXWIN/CWnd::GetCurrentMessage
- AFXWIN/CWnd::InitDynamicLayout
- AFXWIN/CWnd::LoadDynamicLayoutResource
- AFXWIN/CWnd::OnActivate
- AFXWIN/CWnd::OnActivateApp
- AFXWIN/CWnd::OnAppCommand
- AFXWIN/CWnd::OnAskCbFormatName
- AFXWIN/CWnd::OnCancelMode
- AFXWIN/CWnd::OnCaptureChanged
- AFXWIN/CWnd::OnChangeCbChain
- AFXWIN/CWnd::OnChangeUIState
- AFXWIN/CWnd::OnChar
- AFXWIN/CWnd::OnCharToItem
- AFXWIN/CWnd::OnChildActivate
- AFXWIN/CWnd::OnChildNotify
- AFXWIN/CWnd::OnClipboardUpdate
- AFXWIN/CWnd::OnClose
- AFXWIN/CWnd::OnColorizationColorChanged
- AFXWIN/CWnd::OnCommand
- AFXWIN/CWnd::OnCompacting
- AFXWIN/CWnd::OnCompareItem
- AFXWIN/CWnd::OnCompositionChanged
- AFXWIN/CWnd::OnContextMenu
- AFXWIN/CWnd::OnCopyData
- AFXWIN/CWnd::OnCreate
- AFXWIN/CWnd::OnCtlColor
- AFXWIN/CWnd::OnDeadChar
- AFXWIN/CWnd::OnDeleteItem
- AFXWIN/CWnd::OnDestroy
- AFXWIN/CWnd::OnDestroyClipboard
- AFXWIN/CWnd::OnDeviceChange
- AFXWIN/CWnd::OnDevModeChange
- AFXWIN/CWnd::OnDrawClipboard
- AFXWIN/CWnd::OnDrawItem
- AFXWIN/CWnd::OnDropFiles
- AFXWIN/CWnd::OnEnable
- AFXWIN/CWnd::OnEndSession
- AFXWIN/CWnd::OnEnterIdle
- AFXWIN/CWnd::OnEnterMenuLoop
- AFXWIN/CWnd::OnEnterSizeMove
- AFXWIN/CWnd::OnEraseBkgnd
- AFXWIN/CWnd::OnExitMenuLoop
- AFXWIN/CWnd::OnExitSizeMove
- AFXWIN/CWnd::OnFontChange
- AFXWIN/CWnd::OnGetDlgCode
- AFXWIN/CWnd::OnGetMinMaxInfo
- AFXWIN/CWnd::OnHelpInfo
- AFXWIN/CWnd::OnHotKey
- AFXWIN/CWnd::OnHScroll
- AFXWIN/CWnd::OnHScrollClipboard
- AFXWIN/CWnd::OnIconEraseBkgnd
- AFXWIN/CWnd::OnInitMenu
- AFXWIN/CWnd::OnInitMenuPopup
- AFXWIN/CWnd::OnInputDeviceChange
- AFXWIN/CWnd::OnInputLangChange
- AFXWIN/CWnd::OnInputLangChangeRequest
- AFXWIN/CWnd::OnKeyDown
- AFXWIN/CWnd::OnKeyUp
- AFXWIN/CWnd::OnKillFocus
- AFXWIN/CWnd::OnLButtonDblClk
- AFXWIN/CWnd::OnLButtonDown
- AFXWIN/CWnd::OnLButtonUp
- AFXWIN/CWnd::OnMButtonDblClk
- AFXWIN/CWnd::OnMButtonDown
- AFXWIN/CWnd::OnMButtonUp
- AFXWIN/CWnd::OnMDIActivate
- AFXWIN/CWnd::OnMeasureItem
- AFXWIN/CWnd::OnMenuChar
- AFXWIN/CWnd::OnMenuDrag
- AFXWIN/CWnd::OnMenuGetObject
- AFXWIN/CWnd::OnMenuRButtonUp
- AFXWIN/CWnd::OnMenuSelect
- AFXWIN/CWnd::OnMouseActivate
- AFXWIN/CWnd::OnMouseHover
- AFXWIN/CWnd::OnMouseHWheel
- AFXWIN/CWnd::OnMouseLeave
- AFXWIN/CWnd::OnMouseMove
- AFXWIN/CWnd::OnMouseWheel
- AFXWIN/CWnd::OnMove
- AFXWIN/CWnd::OnMoving
- AFXWIN/CWnd::OnNcActivate
- AFXWIN/CWnd::OnNcCalcSize
- AFXWIN/CWnd::OnNcCreate
- AFXWIN/CWnd::OnNcDestroy
- AFXWIN/CWnd::OnNcHitTest
- AFXWIN/CWnd::OnNcLButtonDblClk
- AFXWIN/CWnd::OnNcLButtonDown
- AFXWIN/CWnd::OnNcLButtonUp
- AFXWIN/CWnd::OnNcMButtonDblClk
- AFXWIN/CWnd::OnNcMButtonDown
- AFXWIN/CWnd::OnNcMButtonUp
- AFXWIN/CWnd::OnNcMouseHover
- AFXWIN/CWnd::OnNcMouseLeave
- AFXWIN/CWnd::OnNcMouseMove
- AFXWIN/CWnd::OnNcPaint
- AFXWIN/CWnd::OnNcRButtonDblClk
- AFXWIN/CWnd::OnNcRButtonDown
- AFXWIN/CWnd::OnNcRButtonUp
- AFXWIN/CWnd::OnNcRenderingChanged
- AFXWIN/CWnd::OnNcXButtonDblClk
- AFXWIN/CWnd::OnNcXButtonDown
- AFXWIN/CWnd::OnNcXButtonUp
- AFXWIN/CWnd::OnNextMenu
- AFXWIN/CWnd::OnNotify
- AFXWIN/CWnd::OnNotifyFormat
- AFXWIN/CWnd::OnPaint
- AFXWIN/CWnd::OnPaintClipboard
- AFXWIN/CWnd::OnPaletteChanged
- AFXWIN/CWnd::OnPaletteIsChanging
- AFXWIN/CWnd::OnParentNotify
- AFXWIN/CWnd::OnPowerBroadcast
- AFXWIN/CWnd::OnQueryDragIcon
- AFXWIN/CWnd::OnQueryEndSession
- AFXWIN/CWnd::OnQueryNewPalette
- AFXWIN/CWnd::OnQueryOpen
- AFXWIN/CWnd::OnQueryUIState
- AFXWIN/CWnd::OnRawInput
- AFXWIN/CWnd::OnRButtonDblClk
- AFXWIN/CWnd::OnRButtonDown
- AFXWIN/CWnd::OnRButtonUp
- AFXWIN/CWnd::OnRenderAllFormats
- AFXWIN/CWnd::OnRenderFormat
- AFXWIN/CWnd::OnSessionChange
- AFXWIN/CWnd::OnSetCursor
- AFXWIN/CWnd::OnSetFocus
- AFXWIN/CWnd::OnSettingChange
- AFXWIN/CWnd::OnShowWindow
- AFXWIN/CWnd::OnSize
- AFXWIN/CWnd::OnSizeClipboard
- AFXWIN/CWnd::OnSizing
- AFXWIN/CWnd::OnSpoolerStatus
- AFXWIN/CWnd::OnStyleChanged
- AFXWIN/CWnd::OnStyleChanging
- AFXWIN/CWnd::OnSysChar
- AFXWIN/CWnd::OnSysColorChange
- AFXWIN/CWnd::OnSysCommand
- AFXWIN/CWnd::OnSysDeadChar
- AFXWIN/CWnd::OnSysKeyDown
- AFXWIN/CWnd::OnSysKeyUp
- AFXWIN/CWnd::OnTCard
- AFXWIN/CWnd::OnTimeChange
- AFXWIN/CWnd::OnTimer
- AFXWIN/CWnd::OnTouchInput
- AFXWIN/CWnd::OnTouchInputs
- AFXWIN/CWnd::OnUniChar
- AFXWIN/CWnd::OnUnInitMenuPopup
- AFXWIN/CWnd::OnUpdateUIState
- AFXWIN/CWnd::OnUserChanged
- AFXWIN/CWnd::OnVKeyToItem
- AFXWIN/CWnd::OnVScroll
- AFXWIN/CWnd::OnVScrollClipboard
- AFXWIN/CWnd::OnWindowPosChanged
- AFXWIN/CWnd::OnWindowPosChanging
- AFXWIN/CWnd::OnWinIniChange
- AFXWIN/CWnd::OnWndMsg
- AFXWIN/CWnd::OnXButtonDblClk
- AFXWIN/CWnd::OnXButtonDown
- AFXWIN/CWnd::OnXButtonUp
- AFXWIN/CWnd::PostNcDestroy
- AFXWIN/CWnd::ReflectChildNotify
- AFXWIN/CWnd::ReflectLastMsg
- AFXWIN/CWnd::ResizeDynamicLayout
- AFXWIN/CWnd::WindowProc
- AFXWIN/CWnd::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CWnd [MFC], CWnd
- CWnd [MFC], accDoDefaultAction
- CWnd [MFC], accHitTest
- CWnd [MFC], accLocation
- CWnd [MFC], accNavigate
- CWnd [MFC], accSelect
- CWnd [MFC], AnimateWindow
- CWnd [MFC], ArrangeIconicWindows
- CWnd [MFC], Attach
- CWnd [MFC], BeginModalState
- CWnd [MFC], BeginPaint
- CWnd [MFC], BindDefaultProperty
- CWnd [MFC], BindProperty
- CWnd [MFC], BringWindowToTop
- CWnd [MFC], CalcWindowRect
- CWnd [MFC], CancelToolTips
- CWnd [MFC], CenterWindow
- CWnd [MFC], ChangeClipboardChain
- CWnd [MFC], CheckDlgButton
- CWnd [MFC], CheckRadioButton
- CWnd [MFC], ChildWindowFromPoint
- CWnd [MFC], ClientToScreen
- CWnd [MFC], CloseWindow
- CWnd [MFC], ContinueModal
- CWnd [MFC], Create
- CWnd [MFC], CreateAccessibleProxy
- CWnd [MFC], CreateCaret
- CWnd [MFC], CreateControl
- CWnd [MFC], CreateEx
- CWnd [MFC], CreateGrayCaret
- CWnd [MFC], CreateSolidCaret
- CWnd [MFC], DeleteTempMap
- CWnd [MFC], DestroyWindow
- CWnd [MFC], Detach
- CWnd [MFC], DlgDirList
- CWnd [MFC], DlgDirListComboBox
- CWnd [MFC], DlgDirSelect
- CWnd [MFC], DlgDirSelectComboBox
- CWnd [MFC], DragAcceptFiles
- CWnd [MFC], DragDetect
- CWnd [MFC], DrawAnimatedRects
- CWnd [MFC], DrawCaption
- CWnd [MFC], DrawMenuBar
- CWnd [MFC], EnableActiveAccessibility
- CWnd [MFC], EnableDynamicLayout
- CWnd [MFC], EnableD2DSupport
- CWnd [MFC], EnableScrollBar
- CWnd [MFC], EnableScrollBarCtrl
- CWnd [MFC], EnableToolTips
- CWnd [MFC], EnableTrackingToolTips
- CWnd [MFC], EnableWindow
- CWnd [MFC], EndModalLoop
- CWnd [MFC], EndModalState
- CWnd [MFC], EndPaint
- CWnd [MFC], ExecuteDlgInit
- CWnd [MFC], FilterToolTipMessage
- CWnd [MFC], FindWindow
- CWnd [MFC], FindWindowEx
- CWnd [MFC], FlashWindow
- CWnd [MFC], FlashWindowEx
- CWnd [MFC], FromHandle
- CWnd [MFC], FromHandlePermanent
- CWnd [MFC], get_accChild
- CWnd [MFC], get_accChildCount
- CWnd [MFC], get_accDefaultAction
- CWnd [MFC], get_accDescription
- CWnd [MFC], get_accFocus
- CWnd [MFC], get_accHelp
- CWnd [MFC], get_accHelpTopic
- CWnd [MFC], get_accKeyboardShortcut
- CWnd [MFC], get_accName
- CWnd [MFC], get_accParent
- CWnd [MFC], get_accRole
- CWnd [MFC], get_accSelection
- CWnd [MFC], get_accState
- CWnd [MFC], get_accValue
- CWnd [MFC], GetActiveWindow
- CWnd [MFC], GetAncestor
- CWnd [MFC], GetCapture
- CWnd [MFC], GetCaretPos
- CWnd [MFC], GetCheckedRadioButton
- CWnd [MFC], GetClientRect
- CWnd [MFC], GetClipboardOwner
- CWnd [MFC], GetClipboardViewer
- CWnd [MFC], GetControlUnknown
- CWnd [MFC], GetDC
- CWnd [MFC], GetDCEx
- CWnd [MFC], GetDCRenderTarget
- CWnd [MFC], GetDescendantWindow
- CWnd [MFC], GetDesktopWindow
- CWnd [MFC], GetDlgCtrlID
- CWnd [MFC], GetDlgItem
- CWnd [MFC], GetDlgItemInt
- CWnd [MFC], GetDlgItemText
- CWnd [MFC], GetDSCCursor
- CWnd [MFC], GetDynamicLayout
- CWnd [MFC], GetExStyle
- CWnd [MFC], GetFocus
- CWnd [MFC], GetFont
- CWnd [MFC], GetForegroundWindow
- CWnd [MFC], GetIcon
- CWnd [MFC], GetLastActivePopup
- CWnd [MFC], GetLayeredWindowAttributes
- CWnd [MFC], GetMenu
- CWnd [MFC], GetNextDlgGroupItem
- CWnd [MFC], GetNextDlgTabItem
- CWnd [MFC], GetNextWindow
- CWnd [MFC], GetOleControlSite
- CWnd [MFC], GetOpenClipboardWindow
- CWnd [MFC], GetOwner
- CWnd [MFC], GetParent
- CWnd [MFC], GetParentFrame
- CWnd [MFC], GetParentOwner
- CWnd [MFC], GetProperty
- CWnd [MFC], GetRenderTarget
- CWnd [MFC], GetSafeHwnd
- CWnd [MFC], GetSafeOwner
- CWnd [MFC], GetScrollBarCtrl
- CWnd [MFC], GetScrollBarInfo
- CWnd [MFC], GetScrollInfo
- CWnd [MFC], GetScrollLimit
- CWnd [MFC], GetScrollPos
- CWnd [MFC], GetScrollRange
- CWnd [MFC], GetStyle
- CWnd [MFC], GetSystemMenu
- CWnd [MFC], GetTitleBarInfo
- CWnd [MFC], GetTopLevelFrame
- CWnd [MFC], GetTopLevelOwner
- CWnd [MFC], GetTopLevelParent
- CWnd [MFC], GetTopWindow
- CWnd [MFC], GetUpdateRect
- CWnd [MFC], GetUpdateRgn
- CWnd [MFC], GetWindow
- CWnd [MFC], GetWindowContextHelpId
- CWnd [MFC], GetWindowDC
- CWnd [MFC], GetWindowedChildCount
- CWnd [MFC], GetWindowInfo
- CWnd [MFC], GetWindowlessChildCount
- CWnd [MFC], GetWindowPlacement
- CWnd [MFC], GetWindowRect
- CWnd [MFC], GetWindowRgn
- CWnd [MFC], GetWindowText
- CWnd [MFC], GetWindowTextLength
- CWnd [MFC], HideCaret
- CWnd [MFC], HiliteMenuItem
- CWnd [MFC], HtmlHelp
- CWnd [MFC], Invalidate
- CWnd [MFC], InvalidateRect
- CWnd [MFC], InvalidateRgn
- CWnd [MFC], InvokeHelper
- CWnd [MFC], IsChild
- CWnd [MFC], IsD2DSupportEnabled
- CWnd [MFC], IsDialogMessage
- CWnd [MFC], IsDlgButtonChecked
- CWnd [MFC], IsDynamicLayoutEnabled
- CWnd [MFC], IsIconic
- CWnd [MFC], IsTouchWindow
- CWnd [MFC], IsWindowEnabled
- CWnd [MFC], IsWindowVisible
- CWnd [MFC], IsZoomed
- CWnd [MFC], KillTimer
- CWnd [MFC], LockWindowUpdate
- CWnd [MFC], MapWindowPoints
- CWnd [MFC], MessageBox
- CWnd [MFC], ModifyStyle
- CWnd [MFC], ModifyStyleEx
- CWnd [MFC], MoveWindow
- CWnd [MFC], NotifyWinEvent
- CWnd [MFC], OnAmbientProperty
- CWnd [MFC], OnDrawIconicThumbnailOrLivePreview
- CWnd [MFC], OnHelp
- CWnd [MFC], OnHelpFinder
- CWnd [MFC], OnHelpIndex
- CWnd [MFC], OnHelpUsing
- CWnd [MFC], OnToolHitTest
- CWnd [MFC], OpenClipboard
- CWnd [MFC], PaintWindowlessControls
- CWnd [MFC], PostMessage
- CWnd [MFC], PreCreateWindow
- CWnd [MFC], PreSubclassWindow
- CWnd [MFC], PreTranslateMessage
- CWnd [MFC], Print
- CWnd [MFC], PrintClient
- CWnd [MFC], PrintWindow
- CWnd [MFC], RedrawWindow
- CWnd [MFC], RegisterTouchWindow
- CWnd [MFC], ReleaseDC
- CWnd [MFC], RepositionBars
- CWnd [MFC], RunModalLoop
- CWnd [MFC], ScreenToClient
- CWnd [MFC], ScrollWindow
- CWnd [MFC], ScrollWindowEx
- CWnd [MFC], SendChildNotifyLastMsg
- CWnd [MFC], SendDlgItemMessage
- CWnd [MFC], SendMessage
- CWnd [MFC], SendMessageToDescendants
- CWnd [MFC], SendNotifyMessage
- CWnd [MFC], SetActiveWindow
- CWnd [MFC], SetCapture
- CWnd [MFC], SetCaretPos
- CWnd [MFC], SetClipboardViewer
- CWnd [MFC], SetDlgCtrlID
- CWnd [MFC], SetDlgItemInt
- CWnd [MFC], SetDlgItemText
- CWnd [MFC], SetFocus
- CWnd [MFC], SetFont
- CWnd [MFC], SetForegroundWindow
- CWnd [MFC], SetIcon
- CWnd [MFC], SetLayeredWindowAttributes
- CWnd [MFC], SetMenu
- CWnd [MFC], SetOwner
- CWnd [MFC], SetParent
- CWnd [MFC], SetProperty
- CWnd [MFC], SetRedraw
- CWnd [MFC], SetScrollInfo
- CWnd [MFC], SetScrollPos
- CWnd [MFC], SetScrollRange
- CWnd [MFC], SetTimer
- CWnd [MFC], SetWindowContextHelpId
- CWnd [MFC], SetWindowPlacement
- CWnd [MFC], SetWindowPos
- CWnd [MFC], SetWindowRgn
- CWnd [MFC], SetWindowText
- CWnd [MFC], ShowCaret
- CWnd [MFC], ShowOwnedPopups
- CWnd [MFC], ShowScrollBar
- CWnd [MFC], ShowWindow
- CWnd [MFC], SubclassDlgItem
- CWnd [MFC], SubclassWindow
- CWnd [MFC], UnlockWindowUpdate
- CWnd [MFC], UnsubclassWindow
- CWnd [MFC], UpdateData
- CWnd [MFC], UpdateDialogControls
- CWnd [MFC], UpdateLayeredWindow
- CWnd [MFC], UpdateWindow
- CWnd [MFC], ValidateRect
- CWnd [MFC], ValidateRgn
- CWnd [MFC], WindowFromPoint
- CWnd [MFC], WinHelp
- CWnd [MFC], Default
- CWnd [MFC], DefWindowProc
- CWnd [MFC], DoDataExchange
- CWnd [MFC], GetCurrentMessage
- CWnd [MFC], InitDynamicLayout
- CWnd [MFC], LoadDynamicLayoutResource
- CWnd [MFC], OnActivate
- CWnd [MFC], OnActivateApp
- CWnd [MFC], OnAppCommand
- CWnd [MFC], OnAskCbFormatName
- CWnd [MFC], OnCancelMode
- CWnd [MFC], OnCaptureChanged
- CWnd [MFC], OnChangeCbChain
- CWnd [MFC], OnChangeUIState
- CWnd [MFC], OnChar
- CWnd [MFC], OnCharToItem
- CWnd [MFC], OnChildActivate
- CWnd [MFC], OnChildNotify
- CWnd [MFC], OnClipboardUpdate
- CWnd [MFC], OnClose
- CWnd [MFC], OnColorizationColorChanged
- CWnd [MFC], OnCommand
- CWnd [MFC], OnCompacting
- CWnd [MFC], OnCompareItem
- CWnd [MFC], OnCompositionChanged
- CWnd [MFC], OnContextMenu
- CWnd [MFC], OnCopyData
- CWnd [MFC], OnCreate
- CWnd [MFC], OnCtlColor
- CWnd [MFC], OnDeadChar
- CWnd [MFC], OnDeleteItem
- CWnd [MFC], OnDestroy
- CWnd [MFC], OnDestroyClipboard
- CWnd [MFC], OnDeviceChange
- CWnd [MFC], OnDevModeChange
- CWnd [MFC], OnDrawClipboard
- CWnd [MFC], OnDrawItem
- CWnd [MFC], OnDropFiles
- CWnd [MFC], OnEnable
- CWnd [MFC], OnEndSession
- CWnd [MFC], OnEnterIdle
- CWnd [MFC], OnEnterMenuLoop
- CWnd [MFC], OnEnterSizeMove
- CWnd [MFC], OnEraseBkgnd
- CWnd [MFC], OnExitMenuLoop
- CWnd [MFC], OnExitSizeMove
- CWnd [MFC], OnFontChange
- CWnd [MFC], OnGetDlgCode
- CWnd [MFC], OnGetMinMaxInfo
- CWnd [MFC], OnHelpInfo
- CWnd [MFC], OnHotKey
- CWnd [MFC], OnHScroll
- CWnd [MFC], OnHScrollClipboard
- CWnd [MFC], OnIconEraseBkgnd
- CWnd [MFC], OnInitMenu
- CWnd [MFC], OnInitMenuPopup
- CWnd [MFC], OnInputDeviceChange
- CWnd [MFC], OnInputLangChange
- CWnd [MFC], OnInputLangChangeRequest
- CWnd [MFC], OnKeyDown
- CWnd [MFC], OnKeyUp
- CWnd [MFC], OnKillFocus
- CWnd [MFC], OnLButtonDblClk
- CWnd [MFC], OnLButtonDown
- CWnd [MFC], OnLButtonUp
- CWnd [MFC], OnMButtonDblClk
- CWnd [MFC], OnMButtonDown
- CWnd [MFC], OnMButtonUp
- CWnd [MFC], OnMDIActivate
- CWnd [MFC], OnMeasureItem
- CWnd [MFC], OnMenuChar
- CWnd [MFC], OnMenuDrag
- CWnd [MFC], OnMenuGetObject
- CWnd [MFC], OnMenuRButtonUp
- CWnd [MFC], OnMenuSelect
- CWnd [MFC], OnMouseActivate
- CWnd [MFC], OnMouseHover
- CWnd [MFC], OnMouseHWheel
- CWnd [MFC], OnMouseLeave
- CWnd [MFC], OnMouseMove
- CWnd [MFC], OnMouseWheel
- CWnd [MFC], OnMove
- CWnd [MFC], OnMoving
- CWnd [MFC], OnNcActivate
- CWnd [MFC], OnNcCalcSize
- CWnd [MFC], OnNcCreate
- CWnd [MFC], OnNcDestroy
- CWnd [MFC], OnNcHitTest
- CWnd [MFC], OnNcLButtonDblClk
- CWnd [MFC], OnNcLButtonDown
- CWnd [MFC], OnNcLButtonUp
- CWnd [MFC], OnNcMButtonDblClk
- CWnd [MFC], OnNcMButtonDown
- CWnd [MFC], OnNcMButtonUp
- CWnd [MFC], OnNcMouseHover
- CWnd [MFC], OnNcMouseLeave
- CWnd [MFC], OnNcMouseMove
- CWnd [MFC], OnNcPaint
- CWnd [MFC], OnNcRButtonDblClk
- CWnd [MFC], OnNcRButtonDown
- CWnd [MFC], OnNcRButtonUp
- CWnd [MFC], OnNcRenderingChanged
- CWnd [MFC], OnNcXButtonDblClk
- CWnd [MFC], OnNcXButtonDown
- CWnd [MFC], OnNcXButtonUp
- CWnd [MFC], OnNextMenu
- CWnd [MFC], OnNotify
- CWnd [MFC], OnNotifyFormat
- CWnd [MFC], OnPaint
- CWnd [MFC], OnPaintClipboard
- CWnd [MFC], OnPaletteChanged
- CWnd [MFC], OnPaletteIsChanging
- CWnd [MFC], OnParentNotify
- CWnd [MFC], OnPowerBroadcast
- CWnd [MFC], OnQueryDragIcon
- CWnd [MFC], OnQueryEndSession
- CWnd [MFC], OnQueryNewPalette
- CWnd [MFC], OnQueryOpen
- CWnd [MFC], OnQueryUIState
- CWnd [MFC], OnRawInput
- CWnd [MFC], OnRButtonDblClk
- CWnd [MFC], OnRButtonDown
- CWnd [MFC], OnRButtonUp
- CWnd [MFC], OnRenderAllFormats
- CWnd [MFC], OnRenderFormat
- CWnd [MFC], OnSessionChange
- CWnd [MFC], OnSetCursor
- CWnd [MFC], OnSetFocus
- CWnd [MFC], OnSettingChange
- CWnd [MFC], OnShowWindow
- CWnd [MFC], OnSize
- CWnd [MFC], OnSizeClipboard
- CWnd [MFC], OnSizing
- CWnd [MFC], OnSpoolerStatus
- CWnd [MFC], OnStyleChanged
- CWnd [MFC], OnStyleChanging
- CWnd [MFC], OnSysChar
- CWnd [MFC], OnSysColorChange
- CWnd [MFC], OnSysCommand
- CWnd [MFC], OnSysDeadChar
- CWnd [MFC], OnSysKeyDown
- CWnd [MFC], OnSysKeyUp
- CWnd [MFC], OnTCard
- CWnd [MFC], OnTimeChange
- CWnd [MFC], OnTimer
- CWnd [MFC], OnTouchInput
- CWnd [MFC], OnTouchInputs
- CWnd [MFC], OnUniChar
- CWnd [MFC], OnUnInitMenuPopup
- CWnd [MFC], OnUpdateUIState
- CWnd [MFC], OnUserChanged
- CWnd [MFC], OnVKeyToItem
- CWnd [MFC], OnVScroll
- CWnd [MFC], OnVScrollClipboard
- CWnd [MFC], OnWindowPosChanged
- CWnd [MFC], OnWindowPosChanging
- CWnd [MFC], OnWinIniChange
- CWnd [MFC], OnWndMsg
- CWnd [MFC], OnXButtonDblClk
- CWnd [MFC], OnXButtonDown
- CWnd [MFC], OnXButtonUp
- CWnd [MFC], PostNcDestroy
- CWnd [MFC], ReflectChildNotify
- CWnd [MFC], ReflectLastMsg
- CWnd [MFC], ResizeDynamicLayout
- CWnd [MFC], WindowProc
- CWnd [MFC], m_hWnd
ms.assetid: 49a832ee-bc34-4126-88b3-bc1d9974f6c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b6dadffe56350904fe4c115550590b21d009868
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cwnd-class"></a>CWnd クラス
Microsoft Foundation Class ライブラリにあるすべてのウィンドウ クラスの基本機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CWnd : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::CWnd](#cwnd)|`CWnd` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::accDoDefaultAction](#accdodefaultaction)|オブジェクトの既定のアクションを実行するために、フレームワークによって呼び出されます。|  
|[CWnd::accHitTest](#acchittest)|画面上の指定された位置にある子要素または子オブジェクトを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::accLocation](#acclocation)|指定されたオブジェクトの現在の画面位置を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::accNavigate](#accnavigate)|コンテナー内の他のユーザー インターフェイス要素を走査するため、可能な場合はそのオブジェクトを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::accSelect](#accselect)|選択を変更するため、または指定されたオブジェクトのキーボード フォーカスを移動するために、フレームワークによって呼び出されます。|  
|[CWnd::AnimateWindow](#animatewindow)|関連付けられたウィンドウ オブジェクトをアニメーション化します。|  
|[CWnd::ArrangeIconicWindows](#arrangeiconicwindows)|すべての最小化 (アイコン化) された子ウィンドウを整列します。|  
|[CWnd::Attach](#attach)|Windows ハンドルを `CWnd` オブジェクトに関連付けます。|  
|[CWnd::BeginModalState](#beginmodalstate)|フレーム ウィンドウをモーダルにします。|  
|[CWnd::BeginPaint](#beginpaint)|描画用の `CWnd` を準備します。|  
|[CWnd::BindDefaultProperty](#binddefaultproperty)|タイプ ライブラリに示されているように、呼び出し元オブジェクトの既定の単純バインド プロパティを、データ ソース コントロールに関連付けられているカーソルにバインドします。|  
|[Cwnd::bindproperty](#bindproperty)|データ バインディング コントロールのカーソル バインド プロパティをデータ ソース コントロールにバインドし、そのリレーションシップを MFC バインド マネージャーに登録します。|  
|[CWnd::BringWindowToTop](#bringwindowtotop)|`CWnd` を重なったウィンドウのスタックの最上位に移動します。|  
|[CWnd::CalcWindowRect](#calcwindowrect)|クライアントの四角形からウィンドウ四角形を計算するために呼び出されます。|  
|[CWnd::CancelToolTips](#canceltooltips)|ツール ヒント コントロールを無効にします。|  
|[CWnd::CenterWindow](#centerwindow)|ウィンドウをその親ウィンドウの中央に揃えます。|  
|[CWnd::ChangeClipboardChain](#changeclipboardchain)|クリップボード ビューアーのチェインから `CWnd` を削除します。|  
|[CWnd::CheckDlgButton](#checkdlgbutton)|チェック マークをボタン コントロールの横に配置したり、ボタン コントロールから削除したりします。|  
|[CWnd::CheckRadioButton](#checkradiobutton)|指定されたオプション ボタンにチェック マークを付け、指定されたボタンのグループにある他のすべてのオプション ボタンからチェック マークを削除します。|  
|[CWnd::ChildWindowFromPoint](#childwindowfrompoint)|子ウィンドウがある場合、指定された点を含む子ウィンドウを判断します。|  
|[CWnd::ClientToScreen](#clienttoscreen)|ディスプレイ上の指定された点または四角形のクライアント座標を画面座標に変換します。|  
|[CWnd::CloseWindow](#closewindow)|ウィンドウを最小化します。|  
|[CWnd::ContinueModal](#continuemodal)|ウィンドウのモーダル ステータスを継続します。|  
|[CWnd::Create](#create)|`CWnd` オブジェクトに関連付けられる子ウィンドウを作成し、初期化します。|  
|[CWnd::CreateAccessibleProxy](#createaccessibleproxy)|指定されたオブジェクトの Active Accessibility プロキシを作成します。|  
|[CWnd::CreateCaret](#createcaret)|システム キャレットの新しい形を作成し、そのキャレットの所有権を取得します。|  
|[CWnd::CreateControl](#createcontrol)|MFC プログラムでは `CWnd` オブジェクトによって表される ActiveX コントロールを作成します。|  
|[CWnd::CreateEx](#createex)|Windows のオーバーラップ ウィンドウ、ポップアップ ウィンドウ、または子ウィンドウを作成し、`CWnd` オブジェクトに関連付けます。|  
|[CWnd::CreateGrayCaret](#creategraycaret)|灰色のブロックでシステム キャレットを作成し、そのキャレットの所有権を取得します。|  
|[CWnd::CreateSolidCaret](#createsolidcaret)|純色のブロックでシステム キャレットを作成し、そのキャレットの所有権を取得します。|  
|[CWnd::DeleteTempMap](#deletetempmap)|`FromHandle` 関数で作成した一時的な `CWnd` オブジェクトをすべて削除するために、`CWinApp` のアイドル処理ハンドラーによって自動的に呼び出されます。|  
|[CWnd::DestroyWindow](#destroywindow)|関連付けられている Windows のウィンドウを破棄します。|  
|[CWnd::Detach](#detach)|`CWnd` オブジェクトから Windows のハンドルを切り離し、そのハンドルを返します。|  
|[CWnd::DlgDirList](#dlgdirlist)|リスト ボックスにファイル リストまたはディレクトリ リストを設定します。|  
|[CWnd::DlgDirListComboBox](#dlgdirlistcombobox)|コンボ ボックスにファイル リストまたはディレクトリ リストを設定します。|  
|[CWnd::DlgDirSelect](#dlgdirselect)|リスト ボックスから現在の選択を取得します。|  
|[CWnd::DlgDirSelectComboBox](#dlgdirselectcombobox)|コンボ ボックスから現在の選択を取得します。|  
|[CWnd::DragAcceptFiles](#dragacceptfiles)|ドラッグされたファイルがウィンドウで読み込まれることを示します。|  
|[CWnd::DragDetect](#dragdetect)|マウスをキャプチャし、ユーザーが左ボタンを離すか、Esc キーを押すか、または指定した点を中心にしたドラッグ四角形の外にマウスを移動するまで、移動を追跡します。|  
|[CWnd::DrawAnimatedRects](#drawanimatedrects)|アイコンを開く動作や、ウィンドウの最小化または最大化の動作を、ワイヤ フレームの四角形のアニメーションで表します。|  
|[CWnd::DrawCaption](#drawcaption)|キャプションを描画します。|  
|[CWnd::DrawMenuBar](#drawmenubar)|メニュー バーを再描画します。|  
|[CWnd::EnableActiveAccessibility](#enableactiveaccessibility)|ユーザー定義の `Active Accessibility` 関数を有効にします。|  
|[CWnd::EnableDynamicLayout](#enabledynamiclayout)|ユーザーがウィンドウのサイズを変更したときに、子ウィンドウの位置とサイズを動的に調整できるようにします。|  
|[CWnd::EnableD2DSupport](#enabled2dsupport)|ウィンドウの `D2D` のサポートを有効または無効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|  
|[CWnd::EnableScrollBar](#enablescrollbar)|スクロール バーの矢印の一方または両方を有効または無効にします。|  
|[CWnd::EnableScrollBarCtrl](#enablescrollbarctrl)|兄弟スクロール バーのコントロールを有効または無効にします。|  
|[CWnd::EnableToolTips](#enabletooltips)|ツール ヒント コントロールを有効にします。|  
|[CWnd::EnableTrackingToolTips](#enabletrackingtooltips)|トラッキング モードのツール ヒント コントロールを有効にします。|  
|[CWnd::EnableWindow](#enablewindow)|マウス入力およびキーボード入力を有効または無効にします。|  
|[CWnd::EndModalLoop](#endmodalloop)|ウィンドウのモーダル ステータスを終了します。|  
|[CWnd::EndModalState](#endmodalstate)|フレーム ウィンドウをモーダルからモードレスに変更します。|  
|[CWnd::EndPaint](#endpaint)|描画の終了を示します。|  
|[CWnd::ExecuteDlgInit](#executedlginit)|ダイアログ リソースを開始します。|  
|[CWnd::FilterToolTipMessage](#filtertooltipmessage)|ダイアログ ボックス内のコントロールに関連付けられているタイトルまたはテキストを取得します。|  
|[CWnd::FindWindow](#findwindow)|ウィンドウのハンドルを返します。ウィンドウのハンドルはそのウィンドウ名とウィンドウ クラスによって識別されます。|  
|[CWnd::FindWindowEx](#findwindowex)|ウィンドウのハンドルを返します。ウィンドウのハンドルはそのウィンドウ名とウィンドウ クラスによって識別されます。|  
|[CWnd::FlashWindow](#flashwindow)|ウィンドウを 1 回フラッシュします。|  
|[CWnd::FlashWindowEx](#flashwindowex)|ウィンドウをフラッシュし、追加の機能を実行します。|  
|[CWnd::FromHandle](#fromhandle)|ウィンドウのハンドルが指定されている場合、`CWnd` オブジェクトへのポインターを返します。 `CWnd` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CWnd` オブジェクトが生成され、関連付けられます。|  
|[CWnd::FromHandlePermanent](#fromhandlepermanent)|ウィンドウのハンドルが指定されている場合、`CWnd` オブジェクトへのポインターを返します。 `CWnd` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CWnd` オブジェクトが生成され、関連付けられます。|  
|[CWnd::get_accChild](#get_accchild)|指定された子の `IDispatch` インターフェイスのアドレスを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accChildCount](#get_accchildcount)|このオブジェクトに属する子の数を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accDefaultAction](#get_accdefaultaction)|オブジェクトの既定のアクションを記述する文字列を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accDescription](#get_accdescription)|指定されたオブジェクトの外観を記述する文字列を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accFocus](#get_accfocus)|キーボード フォーカスを保持するオブジェクトを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accHelp](#get_acchelp)|オブジェクトの取得するためにフレームワークによって呼び出されます**ヘルプ**プロパティの文字列。|  
|[CWnd::get_accHelpTopic](#get_acchelptopic)|指定されたオブジェクトに関連付けられている `WinHelp` ファイルの完全パスと、そのファイル内の適切なトピックの識別子を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accKeyboardShortcut](#get_acckeyboardshortcut)|指定されたオブジェクトのショートカット キーまたはアクセス キーを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accName](#get_accname)|指定されたオブジェクトの名前を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accParent](#get_accparent)|オブジェクトの親の `IDispatch` インターフェイスを取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accRole](#get_accrole)|指定されたオブジェクトの役割を記述する情報を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accSelection](#get_accselection)|このオブジェクトの選択されている子を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accState](#get_accstate)|指定されたオブジェクトの現在の状態を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::get_accValue](#get_accvalue)|指定されたオブジェクトの値を取得するために、フレームワークによって呼び出されます。|  
|[CWnd::GetActiveWindow](#getactivewindow)|アクティブなウィンドウを取得します。|  
|[CWnd::GetAncestor](#getancestor)|指定したウィンドウの祖先ウィンドウ オブジェクトを取得します。|  
|[CWnd::GetCapture](#getcapture)|マウス キャプチャを持つ `CWnd` を取得します。|  
|[CWnd::GetCaretPos](#getcaretpos)|キャレットの現在位置を示すクライアント座標を取得します。|  
|[CWnd::GetCheckedRadioButton](#getcheckedradiobutton)|ボタンのグループ内で現在チェックされているオプション ボタンの ID を返します。|  
|[CWnd::GetClientRect](#getclientrect)|`CWnd` クライアント領域の寸法を取得します。|  
|[CWnd::GetClipboardOwner](#getclipboardowner)|クリップボードの現在のオーナーへのポインターを取得します。|  
|[CWnd::GetClipboardViewer](#getclipboardviewer)|クリップボード ビューアーのチェインの最初のウィンドウへのポインターを取得します。|  
|[CWnd::GetControlUnknown](#getcontrolunknown)|不明な ActiveX コントロールへのポインターを取得します。|  
|[CWnd::GetDC](#getdc)|クライアント領域のディスプレイ コンテキストを取得します。|  
|[CWnd::GetDCEx](#getdcex)|クライアント領域のディスプレイ コンテキストを取得し、描画中のクリッピングを有効にします。|  
|[CWnd::GetDCRenderTarget](#getdcrendertarget)|`CWnd` ウィンドウのデバイス コンテキスト (DC) レンダー ターゲットを取得します。|  
|[CWnd::GetDescendantWindow](#getdescendantwindow)|すべての子孫ウィンドウを検索し、指定された ID を持つウィンドウを返します。|  
|[CWnd::GetDesktopWindow](#getdesktopwindow)|Windows のデスクトップ ウィンドウを取得します。|  
|[CWnd::GetDlgCtrlID](#getdlgctrlid)|`CWnd` が子ウィンドウの場合、この関数を呼び出すと、その ID 値が返されます。|  
|[CWnd::GetDlgItem](#getdlgitem)|指定されたダイアログ ボックスから指定された ID を持つコントロールを取得します。|  
|[CWnd::GetDlgItemInt](#getdlgitemint)|指定されたダイアログ ボックスにあるコントロールのテキストを整数値に変換します。|  
|[CWnd::GetDlgItemText](#getdlgitemtext)|コントロールに関連付けられているキャプションまたはテキストを取得します。|  
|[CWnd::GetDSCCursor](#getdsccursor)|データ ソース コントロールの DataSource、UserName、Password、および SQL プロパティで定義されている、基になるカーソルへのポインターを取得します。|  
|[CWnd::GetDynamicLayout](#getdynamiclayout)|動的レイアウト マネージャー オブジェクトへのポインターを取得します。|  
|[CWnd::GetExStyle](#getexstyle)|ウィンドウの拡張スタイルを返します。|  
|[CWnd::GetFocus](#getfocus)|現在入力フォーカスを持っている `CWnd` へのポインターを取得します。|  
|[CWnd::GetFont](#getfont)|現在のフォントを取得します。|  
|[CWnd::GetForegroundWindow](#getforegroundwindow)|手前のウィンドウ (ユーザーが現在作業しているトップレベル ウィンドウ) へのポインターを返します。|  
|[CWnd::GetIcon](#geticon)|アイコンへのハンドルを取得します。|  
|[CWnd::GetLastActivePopup](#getlastactivepopup)|`CWnd` が所有するポップアップ ウィンドウのうち、直前にアクティブだったウィンドウを調べます。|  
|[CWnd::GetLayeredWindowAttributes](#getlayeredwindowattributes)|レイヤード ウィンドウの不透明度および透明度のカラー キーを取得します。|  
|[CWnd::GetMenu](#getmenu)|指定されたメニューへのポインターを取得します。|  
|[CWnd::GetNextDlgGroupItem](#getnextdlggroupitem)|コントロールのグループ内で、指定されたコントロールの直前または次に位置するコントロールを検索します。|  
|[CWnd::GetNextDlgTabItem](#getnextdlgtabitem)|最初のコントロールを取得、 [WS_TABSTOP](styles-used-by-mfc.md#window-styles) (または前) 指定したコントロールのスタイル。|  
|[CWnd::GetNextWindow](#getnextwindow)|ウィンドウ マネージャーのリストから次 (または前) のウィンドウを返します。|  
|[CWnd::GetOleControlSite](#getolecontrolsite)|指定された ActiveX コントロールのカスタム サイトを取得します。|  
|[CWnd::GetOpenClipboardWindow](#getopenclipboardwindow)|現在クリップボードが開いているウィンドウへのポインターを取得します。|  
|[CWnd::GetOwner](#getowner)|`CWnd` のオーナーへのポインターを取得します。|  
|[CWnd::GetParent](#getparent)|`CWnd` の親ウィンドウがある場合、そのウィンドウを取得します。|  
|[CWnd::GetParentFrame](#getparentframe)|`CWnd` オブジェクトの親フレーム ウィンドウを取得します。|  
|[CWnd::GetParentOwner](#getparentowner)|子ウィンドウの親ウィンドウへのポインターを返します。|  
|[CWnd::GetProperty](#getproperty)|ActiveX コントロール プロパティを取得します。|  
|[CWnd::GetRenderTarget](#getrendertarget)|このウィンドウに関連付けられているレンダー ターゲットを取得します。|  
|[CWnd::GetSafeHwnd](#getsafehwnd)|`m_hWnd` を返します。`this` ポインターが `NULL` の場合は、`NULL` を返します。|  
|[CWnd::GetSafeOwner](#getsafeowner)|指定されたウィンドウのセーフ オーナーを取得します。|  
|[CWnd::GetScrollBarCtrl](#getscrollbarctrl)|兄弟スクロール バーのコントロールを返します。|  
|[CWnd::GetScrollBarInfo](#getscrollbarinfo)|指定されたスクロール バーの情報を取得します。|  
|[CWnd::GetScrollInfo](#getscrollinfo)|`SCROLLINFO` 構造体がスクロール バーについて保持している情報を取得します。|  
|[CWnd::GetScrollLimit](#getscrolllimit)|スクロール バーの限界値を取得します。|  
|[CWnd::GetScrollPos](#getscrollpos)|スクロール ボックスの現在位置を取得します。|  
|[CWnd::GetScrollRange](#getscrollrange)|指定されたスクロール バーの現在の最小位置と最大位置をコピーします。|  
|[CWnd::GetStyle](#getstyle)|現在のウィンドウ スタイルを返します。|  
|[CWnd::GetSystemMenu](#getsystemmenu)|アプリケーションがコピーおよび変更のためにコントロール メニューにアクセスできるようにします。|  
|[CWnd::GetTitleBarInfo](#gettitlebarinfo)|指定されたタイトル バーの情報を取得します。|  
|[CWnd::GetTopLevelFrame](#gettoplevelframe)|ウィンドウのトップレベルのフレーム ウィンドウを取得します。|  
|[CWnd::GetTopLevelOwner](#gettoplevelowner)|トップ レベルのウィンドウを取得します。|  
|[CWnd::GetTopLevelParent](#gettoplevelparent)|ウィンドウのトップレベルの親ウィンドウを取得します。|  
|[CWnd::GetTopWindow](#gettopwindow)|`CWnd` に属する第 1 レベルの子ウィンドウを返します。|  
|[CWnd::GetUpdateRect](#getupdaterect)|`CWnd` 更新領域を完全に囲む最小の四角形の座標を取得します。|  
|[CWnd::GetUpdateRgn](#getupdatergn)|`CWnd` 更新領域を取得します。|  
|[CWnd::GetWindow](#getwindow)|対象となるウィンドウとの間に指定された関係が成り立つウィンドウを返します。|  
|[CWnd::GetWindowContextHelpId](#getwindowcontexthelpid)|ヘルプ コンテキスト識別子を取得します。|  
|[CWnd::GetWindowDC](#getwindowdc)|キャプション バー、メニュー、スクロール バーを含むウィンドウ全体のディスプレイ コンテキストを取得します。|  
|[CWnd::GetWindowedChildCount](#getwindowedchildcount)|関連付けられている子ウィンドウの数を返します。|  
|[CWnd::GetWindowInfo](#getwindowinfo)|ウィンドウに関する情報を返します。|  
|[CWnd::GetWindowlessChildCount](#getwindowlesschildcount)|関連付けられているウィンドウなしの子ウィンドウの数を返します。|  
|[CWnd::GetWindowPlacement](#getwindowplacement)|ウィンドウの表示状態、通常の位置 (復元された位置)、最小化された位置、および最大表示された位置を取得します。|  
|[CWnd::GetWindowRect](#getwindowrect)|`CWnd` の画面座標を取得します。|  
|[CWnd::GetWindowRgn](#getwindowrgn)|ウィンドウのウィンドウ領域のコピーを取得します。|  
|[CWnd::GetWindowText](#getwindowtext)|ウィンドウのテキストまたはキャプション タイトル (ある場合) を返します。|  
|[CWnd::GetWindowTextLength](#getwindowtextlength)|ウィンドウのテキストまたはキャプション タイトルの長さを返します。|  
|[CWnd::HideCaret](#hidecaret)|ディスプレイ画面からキャレットを削除して非表示にします。|  
|[CWnd::HiliteMenuItem](#hilitemenuitem)|トップ レベル (メニュー バー) のメニュー項目の強調表示を設定または解除します。|  
|[CWnd::HtmlHelp](#htmlhelp)|HTML ヘルプ アプリケーションを起動するために呼び出されます。|  
|[CWnd::Invalidate](#invalidate)|クライアント領域全体を無効にします。|  
|[CWnd::InvalidateRect](#invalidaterect)|指定された四角形を現在の更新領域に追加して、その四角形内のクライアント領域を無効にします。|  
|[CWnd::InvalidateRgn](#invalidatergn)|指定された領域を現在の更新領域に追加して、その領域内のクライアント領域を無効にします。|  
|[CWnd::InvokeHelper](#invokehelper)|ActiveX コントロール メソッドまたはプロパティを呼び出します。|  
|[CWnd::IsChild](#ischild)|`CWnd` が指定されたウィンドウの子ウィンドウか、または指定されたウィンドウの別の直系の子孫ウィンドウであるかを示します。|  
|[CWnd::IsD2DSupportEnabled](#isd2dsupportenabled)|`D2D` のサポートが有効かどうかを判定します。|  
|[CWnd::IsDialogMessage](#isdialogmessage)|指定されたメッセージがモードレス ダイアログ ボックス用かどうかを判断します。モードレス ダイアログ ボックス用のメッセージである場合は、そのメッセージを処理します。|  
|[CWnd::IsDlgButtonChecked](#isdlgbuttonchecked)|ボタン コントロールがチェックされているかどうかを判断します。|  
|[CWnd::IsDynamicLayoutEnabled](#isdynamiclayoutenabled)|このウィンドウで動的レイアウトが有効かどうかを判断します。 動的レイアウトが有効な場合は、ユーザーが親ウィンドウのサイズを変更したときに、子ウィンドウの位置とサイズを変更できます。|  
|[CWnd::IsIconic](#isiconic)|`CWnd` が最小化 (アイコン化) されているかどうかを判断します。|  
|[CWnd::IsTouchWindow](#istouchwindow)|`CWnd` でタッチ操作がサポートされているかどうかを示します。|  
|[CWnd::IsWindowEnabled](#iswindowenabled)|ウィンドウでマウス入力およびキーボード入力が有効かどうかを判断します。|  
|[CWnd::IsWindowVisible](#iswindowvisible)|ウィンドウが表示可能かどうかを判断します。|  
|[CWnd::IsZoomed](#iszoomed)|`CWnd` が最大表示されているかどうかを判断します。|  
|[CWnd::KillTimer](#killtimer)|システム タイマーを中止します。|  
|[CWnd::LockWindowUpdate](#lockwindowupdate)|指定されたウィンドウでの描画を無効化、または再有効化します。|  
|[CWnd::MapWindowPoints](#mapwindowpoints)|複数の点を `CWnd` の座標空間から他のウィンドウの座標空間へ変換 (マップ) します。|  
|[CWnd::MessageBox](#messagebox)|アプリケーションで用意されたメッセージとキャプションを含むウィンドウを作成し、表示します。|  
|[CWnd::ModifyStyle](#modifystyle)|現在のウィンドウ スタイルを変更します。|  
|[CWnd::ModifyStyleEx](#modifystyleex)|ウィンドウの拡張スタイルを変更します。|  
|[CWnd::MoveWindow](#movewindow)|`CWnd` の位置と寸法を変更します。|  
|[CWnd::NotifyWinEvent](#notifywinevent)|定義済みイベントが発生したことをシステムに通知します。|  
|[CWnd::OnAmbientProperty](#onambientproperty)|アンビエント プロパティ値を実装します。|  
|[CWnd::OnDrawIconicThumbnailOrLivePreview](#ondrawiconicthumbnailorlivepreview)|Windows 7 のタブのサムネイルに表示する、またはアプリケーションのピーク用にクライアントで表示するビットマップを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CWnd::OnHelp](#onhelp)|アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。|  
|[CWnd::OnHelpFinder](#onhelpfinder)|`ID_HELP_FINDER` コマンドおよび `ID_DEFAULT_HELP` コマンドを処理します。|  
|[CWnd::OnHelpIndex](#onhelpindex)|`ID_HELP_INDEX` コマンドを処理し、既定のヘルプ トピックを用意します。|  
|[CWnd::OnHelpUsing](#onhelpusing)|`ID_HELP_USING` コマンドを処理します。|  
|[CWnd::OnToolHitTest](#ontoolhittest)|点が指定されたツールの外接する四角形内にあるかどうかを判断し、そのツールに関する情報を取得します。|  
|[CWnd::OpenClipboard](#openclipboard)|クリップボードを開きます。 他のアプリケーションは、Windows までクリップボードを変更できません[CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035)関数が呼び出されます。|  
|[CWnd::PaintWindowlessControls](#paintwindowlesscontrols)|コントロール コンテナーのウィンドウなしのコントロールを描画します。|  
|[CWnd::PostMessage](#postmessage)|メッセージをアプリケーション キューに配置し、ウィンドウがメッセージを処理するのを待たずに制御を返します。|  
|[CWnd::PreCreateWindow](#precreatewindow)|`CWnd` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。|  
|[CWnd::PreSubclassWindow](#presubclasswindow)|により、前に発生するために必要なその他のサブクラス化[SubclassWindow](#subclasswindow)と呼びます。|  
|[CWnd::PreTranslateMessage](#pretranslatemessage)|ウィンドウ メッセージが Windows 関数の `TranslateMessage` および `DispatchMessage` にディスパッチされる前に、メッセージにフィルターをかけるために `CWinApp` によって使用されます。|  
|[CWnd::Print](#print)|指定されたデバイス コンテキストで現在のウィンドウを描画します。|  
|[CWnd::PrintClient](#printclient)|指定されたデバイス コンテキスト (通常はプリンター デバイス コンテキスト) で、さまざまなウィンドウを描画します。|  
|[CWnd::PrintWindow](#printwindow)|表示されているウィンドウを指定されたデバイス コンテキスト (通常はプリンター DC) にコピーします。|  
|[CWnd::RedrawWindow](#redrawwindow)|クライアント領域内の指定された四角形または領域を更新します。|  
|[CWnd::RegisterTouchWindow](#registertouchwindow)|Windows タッチのサポートを登録または登録解除します。|  
|[CWnd::ReleaseDC](#releasedc)|他のアプリケーションが使用できるように、クライアント デバイス コンテキストおよびウィンドウ デバイス コンテキストを解放します。|  
|[CWnd::RepositionBars](#repositionbars)|クライアント領域のコントロール バーの位置を変更します。|  
|[CWnd::RunModalLoop](#runmodalloop)|モーダル ステータスであるウィンドウのメッセージを取得、変換、またはディスパッチします。|  
|[CWnd::ScreenToClient](#screentoclient)|ディスプレイ上の指定された点または四角形の画面座標をクライアント座標に変換します。|  
|[CWnd::ScrollWindow](#scrollwindow)|クライアント領域の内容をスクロールします。|  
|[CWnd::ScrollWindowEx](#scrollwindowex)|クライアント領域の内容をスクロールします。 `ScrollWindow` と同様に、追加機能があります。|  
|[CWnd::SendChildNotifyLastMsg](#sendchildnotifylastmsg)|子ウィンドウがタスクを処理できるように、親ウィンドウから子ウィンドウへ通知メッセージを送信します。|  
|[CWnd::SendDlgItemMessage](#senddlgitemmessage)|指定されたコントロールにメッセージを送信します。|  
|[CWnd::SendMessage](#sendmessage)|`CWnd` オブジェクトにメッセージを送信し、メッセージが処理されるまで待機します。|  
|[CWnd::SendMessageToDescendants](#sendmessagetodescendants)|対象となるウィンドウのすべての子孫ウィンドウにメッセージを送信します。|  
|[CWnd::SendNotifyMessage](#sendnotifymessage)|指定されたメッセージをウィンドウに送信し、呼び出し元のスレッドがウィンドウを作成したかどうかに応じて、できるだけ早く制御を返します。|  
|[CWnd::SetActiveWindow](#setactivewindow)|ウィンドウをアクティブにします。|  
|[CWnd::SetCapture](#setcapture)|以降のすべてのマウス入力を `CWnd` に送信します。|  
|[CWnd::SetCaretPos](#setcaretpos)|指定された位置にキャレットを移動します。|  
|[CWnd::SetClipboardViewer](#setclipboardviewer)|クリップボードの内容が変更されるたびに通知を受けるウィンドウのチェインに `CWnd` を追加します。|  
|[CWnd::SetDlgCtrlID](#setdlgctrlid)|ウィンドウのウィンドウ ID またはコントロール ID を設定します (ダイアログ ボックス内のコントロールだけでなく、子ウィンドウの場合もあります)。|  
|[CWnd::SetDlgItemInt](#setdlgitemint)|コントロールのテキストを、整数値を表現する文字列に設定します。|  
|[CWnd::SetDlgItemText](#setdlgitemtext)|指定されたダイアログ ボックスにあるコントロールのキャプションまたはテキストを設定します。|  
|[CWnd::SetFocus](#setfocus)|入力フォーカスを要求します。|  
|[CWnd::SetFont](#setfont)|現在のフォントを設定します。|  
|[CWnd::SetForegroundWindow](#setforegroundwindow)|ウィンドウを作成したスレッドをフォアグラウンドに置き、そのウィンドウをアクティブにします。|  
|[CWnd::SetIcon](#seticon)|特定のアイコンへのハンドルを設定します。|  
|[CWnd::SetLayeredWindowAttributes](#setlayeredwindowattributes)|レイヤード ウィンドウの不透明度および透明度のカラー キーを設定します。|  
|[CWnd::SetMenu](#setmenu)|メニューを指定されたメニューに設定します。|  
|[CWnd::SetOwner](#setowner)|`CWnd` のオーナーを変更します。|  
|[CWnd::SetParent](#setparent)|親ウィンドウを変更します。|  
|[CWnd::SetProperty](#setproperty)|ActiveX コントロール プロパティを設定します。|  
|[CWnd::SetRedraw](#setredraw)|`CWnd` の変更内容を再描画したり、または再描画を禁止したりできます。|  
|[CWnd::SetScrollInfo](#setscrollinfo)|スクロール バーの情報を設定します。|  
|[CWnd::SetScrollPos](#setscrollpos)|スクロール ボックスの現在位置を設定します。また、指定されている場合は、新しい位置で表示されるようにスクロール バーを再描画します。|  
|[CWnd::SetScrollRange](#setscrollrange)|指定されたスクロール バーの最小位置と最大位置の値を設定します。|  
|[CWnd::SetTimer](#settimer)|送信するシステム タイマーをインストール、 [WM_TIMER](#ontimer)がトリガーされたときのメッセージします。|  
|[CWnd::SetWindowContextHelpId](#setwindowcontexthelpid)|ヘルプ コンテキスト識別子を設定します。|  
|[CWnd::SetWindowPlacement](#setwindowplacement)|ウィンドウの表示状態、通常の位置 (復元された位置)、最小化された位置、および最大表示された位置を設定します。|  
|[CWnd::SetWindowPos](#setwindowpos)|子ウィンドウ、ポップアップ ウィンドウ、およびトップレベル ウィンドウのサイズ、位置、および順序付けを変更します。|  
|[CWnd::SetWindowRgn](#setwindowrgn)|ウィンドウ領域を設定します。|  
|[CWnd::SetWindowText](#setwindowtext)|ウィンドウ テキストまたはキャプション タイトル (ある場合) を指定されたテキストに設定します。|  
|[CWnd::ShowCaret](#showcaret)|ディスプレイ上のキャレット現在位置にキャレットを表示します。 キャレットは、表示されると自動的に点滅します。|  
|[CWnd::ShowOwnedPopups](#showownedpopups)|ウィンドウが所有するすべてのポップアップ ウィンドウを表示または非表示にします。|  
|[CWnd::ShowScrollBar](#showscrollbar)|スクロール バーを表示または非表示にします。|  
|[CWnd::ShowWindow](#showwindow)|ウィンドウを表示または非表示にします。|  
|[CWnd::SubclassDlgItem](#subclassdlgitem)|Windows コントロールを `CWnd` オブジェクトに関連付け、`CWnd` のメッセージ マップを通じてそのオブジェクトにメッセージを送信します。|  
|[CWnd::SubclassWindow](#subclasswindow)|ウィンドウを `CWnd` オブジェクトに関連付け、その `CWnd` のメッセージ マップを通じてメッセージがルーティングされるようにします。|  
|[CWnd::UnlockWindowUpdate](#unlockwindowupdate)|`CWnd::LockWindowUpdate` でロックされていたウィンドウのロックを解除します。|  
|[CWnd::UnsubclassWindow](#unsubclasswindow)|ウィンドウを切り離します、`CWnd`オブジェクト|  
|[CWnd::UpdateData](#updatedata)|ダイアログ ボックスのデータを初期化または取得します。|  
|[CWnd::UpdateDialogControls](#updatedialogcontrols)|ダイアログの各ボタンの状態および他のコントロールの状態を更新します。|  
|[CWnd::UpdateLayeredWindow](#updatelayeredwindow)|レイヤード ウィンドウの位置、サイズ、形状、内容、および透明度を更新します。|  
|[CWnd::UpdateWindow](#updatewindow)|クライアント領域を更新します。|  
|[CWnd::ValidateRect](#validaterect)|指定された四角形を現在の更新領域から削除して、その四角形内のクライアント領域を有効にします。|  
|[CWnd::ValidateRgn](#validatergn)|現在の更新領域から指定された領域を削除して、その領域内のクライアント領域を有効にします。|  
|[CWnd::WindowFromPoint](#windowfrompoint)|指定された点を含むウィンドウを識別します。|  
|[CWnd::WinHelp](#winhelp)|WinHelp アプリケーションを起動します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::Default](#default)|既定のウィンドウ プロシージャを呼び出します。既定のウィンドウ プロシージャは、アプリケーションが処理しないウィンドウ メッセージに対する既定の処理を提供します。|  
|[CWnd::DefWindowProc](#defwindowproc)|既定のウィンドウ プロシージャを呼び出します。既定のウィンドウ プロシージャは、アプリケーションが処理しないウィンドウ メッセージに対する既定の処理を提供します。|  
|[CWnd::DoDataExchange](#dodataexchange)|ダイアログ データ エクスチェンジとダイアログ データ検証用です。 `UpdateData` によって呼び出されます。|  
|[CWnd::GetCurrentMessage](#getcurrentmessage)|ウィンドウが現在処理しているメッセージへのポインターを返します。 必要がありますでのみ呼び出すことときに、 `On`*メッセージ*メッセージ ハンドラー メンバー関数。|  
|[CWnd::InitDynamicLayout](#initdynamiclayout)|ウィンドウの動的レイアウトを初期化するために、フレームワークによって呼び出されます。|  
|[CWnd::LoadDynamicLayoutResource](#loaddynamiclayoutresource)|リソース ファイルから動的レイアウト情報を読み込みます。|  
|[CWnd::OnActivate](#onactivate)|`CWnd` がアクティブまたは非アクティブになるときに呼び出されます。|  
|[CWnd::OnActivateApp](#onactivateapp)|アプリケーションがアクティブまたは非アクティブになるときに呼び出されます。|  
|[CWnd::OnAppCommand](#onappcommand)|ユーザーがアプリケーションのコマンド イベントを生成するときに呼び出されます。|  
|[CWnd::OnAskCbFormatName](#onaskcbformatname)|クリップボード オーナーがクリップボードの内容を表示するときに、クリップボード ビューアーによって呼び出されます。|  
|[CWnd::OnCancelMode](#oncancelmode)|`CWnd` でマウスのキャプチャなどの内部モードを取り消すことができるようにするために呼び出されます。|  
|[CWnd::OnCaptureChanged](#oncapturechanged)|マウス キャプチャを失うウィンドウにメッセージを送信します。|  
|[CWnd::OnChangeCbChain](#onchangecbchain)|指定されたウィンドウがチェインから削除されようとしていることを通知します。|  
|[CWnd::OnChangeUIState](#onchangeuistate)|ユーザー インターフェイス (UI) 状態を変更する必要があるときに呼び出されます。|  
|[CWnd::OnChar](#onchar)|キーストロークが非システム文字に変換されるときに呼び出されます。|  
|[CWnd::OnCharToItem](#onchartoitem)|子リスト ボックスによって呼び出される、 [LBS_WANTKEYBOARDINPUT](list-box-styles.md)への応答のスタイル、 [WM_CHAR](#onchar)メッセージ。|  
|[CWnd::OnChildActivate](#onchildactivate)|`CWnd` のサイズや位置が変更されたり、`CWnd` がアクティブになったりした場合に、マルチ ドキュメント インターフェイス (MDI) 子ウィンドウに対して呼び出されます。|  
|[CWnd::OnChildNotify](#onchildnotify)|親ウィンドウによって呼び出されます。親ウィンドウにメッセージを送るコントロールが、コントロール通知に対応できるようにします。|  
|[CWnd::OnClipboardUpdate](#onclipboardupdate)|クリップボードの内容が変更されたときに呼び出されます。|  
|[CWnd::OnClose](#onclose)|`CWnd` を終了するシグナルとして呼び出されます。|  
|[CWnd::OnColorizationColorChanged](#oncolorizationcolorchanged)|非クライアント領域のレンダリングのポリシーが変更されたときに呼び出されます。|  
|[CWnd::OnCommand](#oncommand)|ユーザーがコマンドを選択すると呼び出されます。|  
|[CWnd::OnCompacting](#oncompacting)|Windows がシステム メモリの低下を検出すると呼び出されます。|  
|[CWnd::OnCompareItem](#oncompareitem)|子の並べ替えられたオーナー描画コンボ ボックスやリスト ボックス内の新しい項目の相対位置を判断するために、呼び出されます。|  
|[CWnd::OnCompositionChanged](#oncompositionchanged)|Desktop Window Manager (DWM) コンポジションを有効にするか無効にするときに、すべてのトップ レベル ウィンドウに対して呼び出されます。|  
|[CWnd::OnContextMenu](#oncontextmenu)|ウィンドウ内でマウスの右ボタンをクリックすると呼び出されます。|  
|[CWnd::OnCopyData](#oncopydata)|あるアプリケーションから他のアプリケーションにデータをコピーします。|  
|[CWnd::OnCreate](#oncreate)|ウィンドウの作成の一部として呼び出されます。|  
|[CWnd::OnCtlColor](#onctlcolor)|`CWnd` がコントロールの親である場合、コントロールの描画時に呼び出されます。|  
|[CWnd::OnDeadChar](#ondeadchar)|キーストロークが非システムのデッド文字 (アクセント記号付き文字など) に変換されるときに呼び出されます。|  
|[CWnd::OnDeleteItem](#ondeleteitem)|オーナー描画の子リスト ボックスやコンボ ボックスが破棄されるとき、または項目がコントロールから削除されるときに呼び出されます。|  
|[CWnd::OnDestroy](#ondestroy)|`CWnd` が破棄されているときに呼び出されます。|  
|[CWnd::OnDestroyClipboard](#ondestroyclipboard)|Windows を呼び出すことによって、クリップボードを空白にすると呼び出されます[EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037)関数。|  
|[CWnd::OnDeviceChange](#ondevicechange)|デバイスやコンピューターのハードウェア構成が変更されたときに、アプリケーションまたはデバイス ドライバーに通知します。|  
|[CWnd::OnDevModeChange](#ondevmodechange)|ユーザーがデバイス モードの設定を変更したときに、すべてのトップ レベルのウィンドウに対して呼び出されます。|  
|[CWnd::OnDrawClipboard](#ondrawclipboard)|クリップボードの内容が変更されるときに呼び出されます。|  
|[CWnd::OnDrawItem](#ondrawitem)|オーナー描画の子ボタン コントロール、コンボ ボックス コントロール、リスト ボックス コントロール、またはメニューの外観を描画する必要があるときに呼び出されます。|  
|[CWnd::OnDropFiles](#ondropfiles)|ドロップされたファイルを受け取るように登録したウィンドウ上で、ユーザーがマウスの左ボタンを離したときに呼び出されます。|  
|[CWnd::OnEnable](#onenable)|`CWnd` が有効または無効になるときに呼び出されます。|  
|[CWnd::OnEndSession](#onendsession)|セッションが終了するときに呼び出されます。|  
|[CWnd::OnEnterIdle](#onenteridle)|モーダル ダイアログ ボックスまたはメニューがアイドル状態になることをアプリケーションのメイン ウィンドウ プロシージャに通知するために呼び出されます。|  
|[CWnd::OnEnterMenuLoop](#onentermenuloop)|メニュー モーダル ループに入るときに呼び出されます。|  
|[CWnd::OnEnterSizeMove](#onentersizemove)|影響を受けるウィンドウが移動またはサイズ変更のモーダル ループに入った後に呼び出されます。|  
|[CWnd::OnEraseBkgnd](#onerasebkgnd)|ウィンドウの背景を消去する必要があるときに呼び出されます。|  
|[CWnd::OnExitMenuLoop](#onexitmenuloop)|メニュー モーダル ループが終了したときに呼び出されます。|  
|[CWnd::OnExitSizeMove](#onexitsizemove)|影響を受けるウィンドウが移動またはサイズ変更のモーダル ループを終了した後に呼び出されます。|  
|[CWnd::OnFontChange](#onfontchange)|フォント リソースのプールの変更時に呼び出されます。|  
|[CWnd::OnGetDlgCode](#ongetdlgcode)|方向キーおよび Tab キーによる入力そのものをコントロールが処理できるように、そのコントロールに対して呼び出されます。|  
|[CWnd::OnGetMinMaxInfo](#ongetminmaxinfo)|Windows が最大表示されたときの位置や寸法、または最小や最大のトラッキング サイズを知る必要があるときに、必ず呼び出されます。|  
|[CWnd::OnHelpInfo](#onhelpinfo)|ユーザーが F1 キーを押したときに、フレームワークによって呼び出されます。|  
|[CWnd::OnHotKey](#onhotkey)|ユーザーがシステム全体でのショートカット キーを押したときに呼び出されます。|  
|[CWnd::OnHScroll](#onhscroll)|`CWnd` の水平スクロール バーをクリックすると、呼び出されます。|  
|[CWnd::OnHScrollClipboard](#onhscrollclipboard)|クリップボード オーナーがクリップボード内のイメージをスクロールし、適切な部分を無効にし、スクロール バーの値を更新する必要がある場合に呼び出されます。|  
|[CWnd::OnIconEraseBkgnd](#oniconerasebkgnd)|`CWnd` が最小化 (アイコン化) され、アイコンを描画する前にアイコンの背景を設定する必要があるときに呼び出されます。|  
|[CWnd::OnInitMenu](#oninitmenu)|メニューがアクティブになるときに呼び出されます。|  
|[CWnd::OnInitMenuPopup](#oninitmenupopup)|ポップアップ メニューがアクティブになるときに呼び出されます。|  
|[CWnd::OnInputDeviceChange](#oninputdevicechange)|I/O デバイスがシステムで追加または削除されたときに呼び出されます。|  
|[CWnd::OnInputLangChange](#oninputlangchange)|アプリケーションの入力言語が変更されると呼び出されます。|  
|[CWnd::OnInputLangChangeRequest](#oninputlangchangerequest)|ユーザーが新しい入力言語を選択するときに呼び出されます。|  
|[CWnd::OnKeyDown](#onkeydown)|非システム キーが押されると呼び出されます。|  
|[CWnd::OnKeyUp](#onkeyup)|非システム キーが離されると呼び出されます。|  
|[CWnd::OnKillFocus](#onkillfocus)|`CWnd` が入力フォーカスを失う直前に呼び出されます。|  
|[CWnd::OnLButtonDblClk](#onlbuttondblclk)|マウスの左ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnLButtonDown](#onlbuttondown)|マウスの左ボタンを押すと呼び出されます。|  
|[CWnd::OnLButtonUp](#onlbuttonup)|マウスの左ボタンを離すと呼び出されます。|  
|[CWnd::OnMButtonDblClk](#onmbuttondblclk)|マウスの中央ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnMButtonDown](#onmbuttondown)|マウスの中央ボタンを押すと呼び出されます。|  
|[CWnd::OnMButtonUp](#onmbuttonup)|マウスの中央ボタンを離すと呼び出されます。|  
|[CWnd::OnMDIActivate](#onmdiactivate)|MDI 子ウィンドウがアクティブまたは非アクティブになるときに呼び出されます。|  
|[CWnd::OnMeasureItem](#onmeasureitem)|オーナー描画の子コンボ ボックス、リスト ボックス、またはメニュー項目が作成されるときに呼び出されます。 `CWnd` は、コントロールの大きさを Windows に通知します。|  
|[CWnd::OnMenuChar](#onmenuchar)|ユーザーが押したメニューのニーモニック文字が、現在のメニューに組み込まれているニーモニックと一致しないときに呼び出されます。|  
|[CWnd::OnMenuDrag](#onmenudrag)|ユーザーがメニュー項目をドラッグするときに呼び出されます。|  
|[CWnd::OnMenuGetObject](#onmenugetobject)|マウス カーソルがメニュー項目に入るか、項目の中央から項目の上部または下部に移動したときに呼び出されます。|  
|[CWnd::OnMenuRButtonUp](#onmenurbuttonup)|カーソルがメニュー項目にあるときに、マウスの右ボタンを離すと呼び出されます。|  
|[CWnd::OnMenuSelect](#onmenuselect)|ユーザーがメニュー項目を選択するときに呼び出されます。|  
|[CWnd::OnMouseActivate](#onmouseactivate)|カーソルが非アクティブ ウィンドウにあるときに、マウス ボタンを押すと呼び出されます。|  
|[CWnd::OnMouseHover](#onmousehover)|呼び出す前に指定された期間、ウィンドウのクライアント領域にカーソルを合わせるときに呼び出されます[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)です。|  
|[CWnd::OnMouseHWheel](#onmousehwheel)|現在のウィンドウが Desktop Window Manager (DWM) によって構成され、そのウィンドウが最大化されるときに呼び出されます。|  
|[CWnd::OnMouseLeave](#onmouseleave)|呼び出す前に指定されたウィンドウのクライアント領域をカーソルが離れるときに呼び出されます[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)です。|  
|[CWnd::OnMouseMove](#onmousemove)|マウスのカーソルの移動時に呼び出されます。|  
|[CWnd::OnMouseWheel](#onmousewheel)|マウス ホイールの回転時に呼び出されます。 Windows NT 4.0 メッセージ処理を使用します。|  
|[CWnd::OnMove](#onmove)|`CWnd` の位置が変更されると、呼び出されます。|  
|[CWnd::OnMoving](#onmoving)|ユーザーが `CWnd` オブジェクトを移動中であることを示します。|  
|[CWnd::OnNcActivate](#onncactivate)|アクティブまたは非アクティブ状態を示すために、非クライアント領域を変更する必要があるときに呼び出されます。|  
|[CWnd::OnNcCalcSize](#onnccalcsize)|クライアント領域のサイズと位置を計算する必要があるときに呼び出されます。|  
|[CWnd::OnNcCreate](#onnccreate)|前のバージョンと呼ばれる[OnCreate](#oncreate)非クライアント領域の作成時にします。|  
|[CWnd::OnNcDestroy](#onncdestroy)|非クライアント領域が破棄されるときに呼び出されます。|  
|[CWnd::OnNcHitTest](#onnchittest)|`CWnd` がカーソルを含む場合、または `SetCapture` を使用してマウス入力をキャプチャした場合に、マウスを移動するごとに Windows によって呼び出されます。|  
|[CWnd::OnNcLButtonDblClk](#onnclbuttondblclk)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの左ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnNcLButtonDown](#onnclbuttondown)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの左ボタンを押すと呼び出されます。|  
|[CWnd::OnNcLButtonUp](#onnclbuttonup)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの左ボタンを離すと呼び出されます。|  
|[CWnd::OnNcMButtonDblClk](#onncmbuttondblclk)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの中央ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnNcMButtonDown](#onncmbuttondown)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの中央ボタンを押すと呼び出されます。|  
|[CWnd::OnNcMButtonUp](#onncmbuttonup)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの中央ボタンを離すと呼び出されます。|  
|[CWnd::OnNcMouseHover](#onncmousehover)|呼び出す前に指定された期間のウィンドウの非クライアント領域にカーソルを合わせるときに呼び出されます[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)です。|  
|[CWnd::OnNcMouseLeave](#onncmouseleave)|呼び出す前に指定されたウィンドウの非クライアント領域をカーソルが離れるときに、フレームワークはこのメンバー関数を呼び出します[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)です。|  
|[CWnd::OnNcMouseMove](#onncmousemove)|`CWnd` の非クライアント領域内でカーソルが移動するときに呼び出されます。|  
|[CWnd::OnNcPaint](#onncpaint)|非クライアント領域を描画する必要があるときに呼び出されます。|  
|[CWnd::OnNcRButtonDblClk](#onncrbuttondblclk)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの右ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnNcRButtonDown](#onncrbuttondown)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの右ボタンを押すと呼び出されます。|  
|[CWnd::OnNcRButtonUp](#onncrbuttonup)|カーソルが `CWnd` の非クライアント領域内にあるときに、マウスの右ボタンを離すと呼び出されます。|  
|[CWnd::OnNcRenderingChanged](#onncrenderingchanged)|非クライアント領域のレンダリングのポリシーが変更されたときに呼び出されます。|  
|[CWnd::OnNcXButtonDblClk](#onncxbuttondblclk)|カーソルがウィンドウの非クライアント領域内にある間にユーザーが XBUTTON1 または XBUTTON2 をダブルクリックすると呼び出されます。|  
|[CWnd::OnNcXButtonDown](#onncxbuttondown)|カーソルがウィンドウの非クライアント領域内にある間にユーザーがマウスの XBUTTON1 または XBUTTON2 を押すと呼び出されます。|  
|[CWnd::OnNcXButtonUp](#onncxbuttonup)|カーソルがウィンドウの非クライアント領域内にある間にユーザーがマウスの XBUTTON1 または XBUTTON2 を離すと呼び出されます。|  
|[CWnd::OnNextMenu](#onnextmenu)|右方向キーまたは左方向キーでメニュー バーとシステム メニューを切り替えたときに呼び出されます。|  
|[CWnd::OnNotify](#onnotify)|コントロールでイベントが発生したこと、またはコントロールが情報を必要としていることを親ウィンドウに通知するために、フレームワークによって呼び出されます。|  
|[CWnd::OnNotifyFormat](#onnotifyformat)|現在のウィンドウが WM_NOTIFY 通知メッセージで ANSI 構造体または Unicode 構造体を受け入れるかどうかを判断するために呼び出されます。|  
|[CWnd::OnPaint](#onpaint)|ウィンドウの一部を再描画するために呼び出されます。|  
|[CWnd::OnPaintClipboard](#onpaintclipboard)|クリップボード ビューアーのクライアント領域の再描画が必要なときに呼び出されます。|  
|[CWnd::OnPaletteChanged](#onpalettechanged)|カラー パレットを使用するウィンドウによる論理パレットの実体化とクライアント領域の更新を許可するために呼び出されます。|  
|[CWnd::OnPaletteIsChanging](#onpaletteischanging)|あるアプリケーションで論理パレットが実体化されるときに、他のアプリケーションに通知します。|  
|[CWnd::OnParentNotify](#onparentnotify)|子ウィンドウを作成または破棄するか、カーソルが子ウィンドウの上にあるときにマウス ボタンをクリックすると呼び出されます。|  
|[CWnd::OnPowerBroadcast](#onpowerbroadcast)|電源管理イベントが発生したときに呼び出されます。|  
|[CWnd::OnQueryDragIcon](#onquerydragicon)|最小化 (アイコン化) された `CWnd` をユーザーがドラッグするときに呼び出されます。|  
|[CWnd::OnQueryEndSession](#onqueryendsession)|ユーザーが Windows セッションを終了するときに呼び出されます。|  
|[CWnd::OnQueryNewPalette](#onquerynewpalette)|もうすぐ入力フォーカスを受け取ることを、`CWnd` に通知します。|  
|[CWnd::OnQueryOpen](#onqueryopen)|`CWnd` がアイコンであり、ユーザーがそのアイコンを開こうとしたときに呼び出されます。|  
|[CWnd::OnQueryUIState](#onqueryuistate)|ウィンドウのユーザー インターフェイス (UI) 状態を取得するために呼び出されます。|  
|[CWnd::OnRawInput](#onrawinput)|現在のウィンドウが生の入力を取得するときに呼び出されます。|  
|[CWnd::OnRButtonDblClk](#onrbuttondblclk)|マウスの右ボタンをダブルクリックすると呼び出されます。|  
|[CWnd::OnRButtonDown](#onrbuttondown)|マウスの右ボタンを押すと呼び出されます。|  
|[CWnd::OnRButtonUp](#onrbuttonup)|マウスの右ボタンを離すと呼び出されます。|  
|[CWnd::OnRenderAllFormats](#onrenderallformats)|オーナー アプリケーションが破棄され、そのフォーマットすべてのレンダリングが必要なときに呼び出されます。|  
|[CWnd::OnRenderFormat](#onrenderformat)|遅延レンダリングされた固有フォーマットのレンダリングが必要なときに、クリップボード オーナーに対して呼び出されます。|  
|[CWnd::OnSessionChange](#onsessionchange)|セッション状態の変更をアプリケーションに通知するために呼び出されます。|  
|[CWnd::OnSetCursor](#onsetcursor)|マウス入力がキャプチャされずに、ウィンドウ内のカーソルが移動された場合に呼び出されます。|  
|[CWnd::OnSetFocus](#onsetfocus)|`CWnd` が入力フォーカスを取得すると呼び出されます。|  
|[CWnd::OnSettingChange](#onsettingchange)|Win32 `SystemParametersInfo` 関数がシステム全体の設定を変更するときに呼び出されます。|  
|[CWnd::OnShowWindow](#onshowwindow)|`CWnd` が非表示になるか表示されるときに呼び出されます。|  
|[CWnd::OnSize](#onsize)|`CWnd` のサイズが変更された後に呼び出されます。|  
|[CWnd::OnSizeClipboard](#onsizeclipboard)|クリップボード ビューアー ウィンドウのクライアント領域のサイズが変更されたときに呼び出されます。|  
|[CWnd::OnSizing](#onsizing)|四角形のサイズを変更中であることを示します。|  
|[CWnd::OnSpoolerStatus](#onspoolerstatus)|プリント マネージャーのキューでジョブが追加または削除されるたびに、プリント マネージャーから呼び出されます。|  
|[CWnd::OnStyleChanged](#onstylechanged)|示します、 [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows 関数は、1 つまたは複数のウィンドウのスタイルが変更されます。|  
|[CWnd::OnStyleChanging](#onstylechanging)|示します、 [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows 関数が 1 つまたは複数のウィンドウのスタイルを変更しようとしています。|  
|[CWnd::OnSysChar](#onsyschar)|キーストロークがシステム文字に変換されるときに呼び出されます。|  
|[CWnd::OnSysColorChange](#onsyscolorchange)|システム カラーの設定が変更されたときに、すべてのトップ レベル ウィンドウで呼び出されます。|  
|[CWnd::OnSysCommand](#onsyscommand)|ユーザーがコントロール メニューからコマンドを選択するとき、または最大化ボタンまたは最小化ボタンを選択するときに呼び出されます。|  
|[CWnd::OnSysDeadChar](#onsysdeadchar)|キーストロークがシステムのデッド文字 (アクセント記号付き文字など) に変換されるときに呼び出されます。|  
|[CWnd::OnSysKeyDown](#onsyskeydown)|ユーザーが Alt キーを押したまま他のキーを押すときに呼び出されます。|  
|[CWnd::OnSysKeyUp](#onsyskeyup)|Alt キーと一緒に押していたキーを離すときに呼び出されます。|  
|[CWnd::OnTCard](#ontcard)|ユーザーが編集可能なボタンをクリックしたときに呼び出されます。|  
|[CWnd::OnTimeChange](#ontimechange)|システム時間が変更された後、すべてのトップ レベルのウィンドウに対して呼び出されます。|  
|[CWnd::OnTimer](#ontimer)|指定した各間隔後に呼び出される[SetTimer](#settimer)です。|  
|[CWnd::OnTouchInput](#ontouchinput)|Windows タッチからの 1 つの入力を処理します。|  
|[CWnd::OnTouchInputs](#ontouchinputs)|Windows タッチからの複数の入力を処理します。|  
|[CWnd::OnUniChar](#onunichar)|キーが押されるときに呼び出されます。 現在のウィンドウは、キーボード フォーカス、および[WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280)によってメッセージを変換、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)関数。|  
|[CWnd::OnUnInitMenuPopup](#onuninitmenupopup)|ドロップダウン メニューやサブメニューが破棄されたときに呼び出されます。|  
|[CWnd::OnUpdateUIState](#onupdateuistate)|指定したウィンドウとすべての子ウィンドウのユーザー インターフェイス (UI) 状態を変更するときに呼び出されます。|  
|[CWnd::OnUserChanged](#onuserchanged)|ユーザーがログオンまたはログオフした後に呼び出されます。|  
|[CWnd::OnVKeyToItem](#onvkeytoitem)|所有するリスト ボックスによって呼び出されます`CWnd`への応答、 [WM_KEYDOWN](#onkeydown)メッセージ。|  
|[CWnd::OnVScroll](#onvscroll)|ウィンドウの垂直スクロール バーをクリックすると呼び出されます。|  
|[CWnd::OnVScrollClipboard](#onvscrollclipboard)|オーナーがクリップボード内のイメージをスクロールし、適切な部分を無効にし、さらに、スクロール バーの値を更新する必要がある場合に呼び出されます。|  
|[CWnd::OnWindowPosChanged](#onwindowposchanged)|呼び出しの結果として、サイズ、位置、または Z オーダーが変わったときに呼び出されます[SetWindowPos](#setwindowpos)または他のウィンドウ管理関数です。|  
|[CWnd::OnWindowPosChanging](#onwindowposchanging)|サイズ、位置、または Z オーダーはへの呼び出しの結果として変更するときに呼び出されます[SetWindowPos](#setwindowpos)または他のウィンドウ管理関数です。|  
|[CWnd::OnWinIniChange](#onwininichange)|Windows 初期化ファイルの WIN.INI が変更された後、すべてのトップ レベル ウィンドウに対して呼び出されます。|  
|[CWnd::OnWndMsg](#onwndmsg)|ウィンドウのメッセージが処理されたかどうかを示します。|  
|[CWnd::OnXButtonDblClk](#onxbuttondblclk)|カーソルがウィンドウのクライアント領域内にある間にユーザーが XBUTTON1 または XBUTTON2 をダブルクリックすると呼び出されます。|  
|[CWnd::OnXButtonDown](#onxbuttondown)|カーソルがウィンドウのクライアント領域内にある間にユーザーが XBUTTON1 または XBUTTON2 を押すと呼び出されます。|  
|[CWnd::OnXButtonUp](#onxbuttonup)|カーソルがウィンドウのクライアント領域内にある間にユーザーが XBUTTON1 または XBUTTON2 を離すと呼び出されます。|  
|[CWnd::PostNcDestroy](#postncdestroy)|既定では、この仮想関数を呼び出す[OnNcDestroy](#onncdestroy)ウィンドウが破棄された後に機能します。|  
|[CWnd::ReflectChildNotify](#reflectchildnotify)|メッセージをソースに反映するヘルパー関数です。|  
|[CWnd::ReflectLastMsg](#reflectlastmsg)|最後のメッセージを子ウィンドウに反映します。|  
|[CWnd::ResizeDynamicLayout](#resizedynamiclayout)|ウィンドウで動的レイアウトが有効な場合、子ウィンドウのレイアウトを調整するためにウィンドウのサイズが変更されると、フレームワークによって呼び出されます。|  
|[CWnd::WindowProc](#windowproc)|`CWnd` にウィンドウ プロシージャを提供します。 既定では、メッセージ マップを通じてメッセージをディスパッチします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::operator HWND](#operator_hwnd)|ウィンドウへのハンドルを取得するために呼び出します。|  
|[CWnd::operator! =](#operator_neq)|かどうかをウィンドウいないハンドルがあるウィンドウと同じ[m_hWnd](#m_hwnd)です。|  
|[CWnd::operator = =](#operator_eq_eq)|かどうかをウィンドウ ハンドルがあるウィンドウと同じ[m_hWnd](#m_hwnd)です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWnd::m_hWnd](#m_hwnd)|この `CWnd` に関連付けられている `HWND` を示します。|  
  
## <a name="remarks"></a>コメント  
 `CWnd` オブジェクトは、Windows のウィンドウとは異なりますが、両者は密接にリンクされています。 `CWnd` オブジェクトは、`CWnd` コンストラクターとデストラクターによって作成され、破棄されます。 、Windows のウィンドウは、Windows によって作成される内部データ構造体をその一方で、は、**作成**メンバー関数によって破棄されると、`CWnd`仮想デストラクターです。 [DestroyWindow](#destroywindow)関数が、オブジェクトを破棄せずに Windows ウィンドウを破棄します。  
  
 `CWnd`クラスと非表示にするメッセージ マップ機構、 **WndProc**関数。 受信 Windows 通知メッセージは自動的に適切なメッセージ マップを通じてルーティング **で * * * メッセージ*`CWnd`メンバー関数。 オーバーライドする、**で * * * メッセージ*派生クラスでメンバーの特定のメッセージを処理するメンバー関数。  
  
 `CWnd` クラスでは、アプリケーションの Windows 子ウィンドウも作成できます。 アプリケーション固有のデータを格納するには、`CWnd` からクラスを派生させ、その派生クラスにメンバー変数を追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 子ウィンドウは 2 つのステップで作成します。 最初に、コンス トラクターを呼び出す`CWnd`構築するために、`CWnd`オブジェクト、し、呼び出し、[作成](#create)子ウィンドウを作成し、アタッチにメンバー関数、`CWnd`オブジェクト。  
  
 ユーザーが子ウィンドウを終了したら、ウィンドウを削除してそのデータ構造体を破棄するために、`CWnd` オブジェクトを破棄するか、`DestroyWindow` メンバー関数を呼び出します。  
  
 Microsoft Foundation Class ライブラリでは、固有のウィンドウ タイプを提供するために、`CWnd` からさらにクラスが派生されています。 これらのクラスの多くは[CFrameWnd](../../mfc/reference/cframewnd-class.md)、 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)、 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)、 [CView](../../mfc/reference/cview-class.md)、および[CDialog](../../mfc/reference/cdialog-class.md)、さらに派生させるために設計されています。 派生したコントロール クラス`CWnd`など[CButton](../../mfc/reference/cbutton-class.md)直接使用することができます、またはさらに別のクラスの派生に使用できます。  
  
 使用する方法についての`CWnd`を参照してください[フレーム ウィンドウ](../../mfc/frame-windows.md)と[ウィンドウ オブジェクト](../../mfc/window-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="accdodefaultaction"></a>  CWnd::accDoDefaultAction  
 オブジェクトの既定のアクションを実行するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accDoDefaultAction(VARIANT varChild);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 呼び出される既定のアクションがオブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (する場合、オブジェクトの既定のアクションを実行する) または (オブジェクトの子要素のいずれかの既定のアクションを実行する) に child ID のいずれかを指定できます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::accDoDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318470) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-オブジェクトの既定のアクションを実行するクラスを派生します。 詳細については、次を参照してください。 [IAccessible::accDoDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318470) Windows SDK に含まれています。  
  
##  <a name="acchittest"></a>  CWnd::accHitTest  
 画面上の指定された位置にある子要素または子オブジェクトを取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accHitTest(
    long xLeft,  
    long yTop,  
    VARIANT* pvarChild);
```  
  
### <a name="parameters"></a>パラメーター  
 `xLeft`  
 X 座標、ポイントにヒットするテスト (画面単位)。  
  
 `yTop`  
 ヒットする点の Y 座標は、(画面のユニット数) でテストします。  
  
 `pvarChild`  
 指定された位置にあるオブジェクトを識別する情報を受け取る`xLeft`と`yTop`です。 参照してください*pvarID*で[IAccessible::accHitTest](http://msdn.microsoft.com/library/windows/desktop/dd318471) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で**IAccessible::accHitTest** Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 [IAccessible::accHitTest](http://msdn.microsoft.com/library/windows/desktop/dd318471) Windows SDK に含まれています。  
  
##  <a name="acclocation"></a>  CWnd::accLocation  
 指定されたオブジェクトの現在の画面位置を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accLocation(
    long* pxLeft,  
    long* pyTop,  
    long* pcxWidth,  
    long* pcyHeight,  
    VARIANT varChild);
```  
  
### <a name="parameters"></a>パラメーター  
 *pxLeft*  
 画面のユニット数) の「オブジェクトの左上隅の x 座標を受け取ります。  
  
 *pyTop*  
 画面のユニット数) の「オブジェクトの左上隅の y 座標を受け取ります。  
  
 *pcxWidth*  
 画面のユニット数) の「オブジェクトの幅をを受け取ります。  
  
 *pcyHeight*  
 画面のユニット数) の「オブジェクトの高さをを受け取ります。  
  
 `varChild`  
 取得する場所が、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトに関する情報を取得) するか、(情報を取得するオブジェクトの子要素) の子の ID を指定できます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で**IAccessible::accLocation** Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 **IAccessible::accLocation** Windows SDK に含まれています。  
  
##  <a name="accnavigate"></a>  CWnd::accNavigate  
 コンテナー内の他のユーザー インターフェイス要素を走査するため、可能な場合はそのオブジェクトを取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accNavigate(
    long navDir,  
    VARIANT varStart,  
    VARIANT* pvarEndUpAt);
```  
  
### <a name="parameters"></a>パラメーター  
 `navDir`  
 移動する方向を指定します。 参照してください`navDir`で[IAccessible::accNavigate](http://msdn.microsoft.com/library/windows/desktop/dd318473) Windows SDK にします。  
  
 `varStart`  
 開始オブジェクトを指定します。 参照してください`varStart`で**IAccessible::accNavigate** Windows SDK にします。  
  
 *pvarEndUpAt*  
 移行先のユーザー インターフェイス オブジェクトに関する情報を受け取ります。 参照してください*pvarEnd*で**IAccessible::accNavigate** Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で**IAccessible::accNavigate** Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 [IAccessible::accNavigate](http://msdn.microsoft.com/library/windows/desktop/dd318473) Windows SDK に含まれています。  
  
##  <a name="accselect"></a>  CWnd::accSelect  
 選択を変更するため、または指定されたオブジェクトのキーボード フォーカスを移動するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT accSelect(
    long flagsSelect,  
    VARIANT varChild);
```  
  
### <a name="parameters"></a>パラメーター  
 `flagsSelect`  
 現在の選択項目またはフォーカスを変更する方法を指定します。 参照してください`flagsSelect`で[IAccessible::accSelect](http://msdn.microsoft.com/library/windows/desktop/dd318474) Windows SDK にします。  
  
 `varChild`  
 選択するオブジェクトを指定します。 このパラメーターには、CHILDID_SELF (する場合、オブジェクト自体を選択) または (オブジェクトの子のいずれかを選択) に child ID のいずれかを指定できます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で**IAccessible::accSelect** Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 [IAccessible::accSelect](http://msdn.microsoft.com/library/windows/desktop/dd318474) Windows SDK に含まれています。  
  
##  <a name="animatewindow"></a>  CWnd::AnimateWindow  
 Windows と非表示と特殊効果を生成します。  
  
```  
BOOL AnimateWindow(
    DWORD dwTime,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTime*  
 ミリ秒単位でアニメーションの再生にかかる時間を指定します。 アニメーションを再生する 200 ミリ秒がかかります。  
  
 `dwFlags`  
 アニメーションの種類を指定します。 使用可能な値の一覧については、次を参照してください。 [AnimateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632669)です。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[AnimateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632669)Windows SDK で説明されている。  
  
##  <a name="arrangeiconicwindows"></a>  CWnd::ArrangeIconicWindows  
 すべての最小化 (アイコン化) された子ウィンドウを整列します。  
  
```  
UINT ArrangeIconicWindows();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合のアイコンの 1 つの行の高さそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、またデスクトップ ウィンドウで、画面全体のアイコンを整列します。 [GetDesktopWindow](#getdesktopwindow)メンバー関数は、デスクトップ ウィンドウ オブジェクトへのポインターを取得します。  
  
 MDI クライアント ウィンドウで MDI 子ウィンドウを整列するには、呼び出す[ある最小化された](../../mfc/reference/cmdiframewnd-class.md#mdiiconarrange)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#66](../../mfc/reference/codesnippet/cpp/cwnd-class_1.cpp)]  
  
##  <a name="attach"></a>  CWnd::Attach  
 Windows のウィンドウにアタッチ、`CWnd`オブジェクト。  
  
```  
BOOL Attach(HWND hWndNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndNew`  
 Windows のウィンドウへのハンドルを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 この例では、アタッチとデタッチを使用して、MDI クライアント ウィンドウにマップする方法を示します。  
  
 [!code-cpp[NVC_MFCWindowing#67](../../mfc/reference/codesnippet/cpp/cwnd-class_2.h)]  
  
 [!code-cpp[NVC_MFCWindowing#68](../../mfc/reference/codesnippet/cpp/cwnd-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#69](../../mfc/reference/codesnippet/cpp/cwnd-class_4.cpp)]  
  
##  <a name="beginmodalstate"></a>  CWnd::BeginModalState  
 フレーム ウィンドウをモーダルにします。  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="beginpaint"></a>  Cwnd::beginpaint  
 準備`CWnd`描画およびがいっぱいになったのため、`PAINTSTRUCT`描画に関する情報を含むデータ構造体。  
  
```  
CDC* BeginPaint(LPPAINTSTRUCT lpPaint);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPaint`  
 指す、 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)構造体を描画情報を受信します。  
  
### <a name="return-value"></a>戻り値  
 デバイス コンテキストを識別`CWnd`です。 ポインターは、一時的なとの範囲を超えていない格納されている必要があります[EndPaint](#endpaint)です。  
  
### <a name="remarks"></a>コメント  
 塗りつぶしの構造には、更新領域と、バック グラウンドが消去されているかどうかを指定するフラグを完全に囲む最小の四角形を含む RECT データ構造体が含まれています。  
  
 更新領域では設定されて、 [Invalidate](#invalidate)、 [InvalidateRect](#invalidaterect)、または[戻り](#invalidatergn)メンバー関数し、システムによって、サイズは、移動、作成、スクロール、またはクライアント領域に影響を与える、他の操作を実行します。 更新領域が消去されるのマークされている場合`BeginPaint`送信、 [WM_ONERASEBKGND](#onerasebkgnd)メッセージ。  
  
 呼び出す必要はありません、`BeginPaint`への応答以外のメンバー関数、 [WM_PAINT](#onpaint)メッセージ。 呼び出しごとに、`BeginPaint`メンバー関数は、照合の呼び出しをいる必要があります、 [EndPaint](#endpaint)メンバー関数。 キャレットが描画される領域内にある場合、`BeginPaint`メンバー関数に自動的に消去されるようにするキャレットが非表示にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#70](../../mfc/reference/codesnippet/cpp/cwnd-class_5.cpp)]  
  
##  <a name="binddefaultproperty"></a>  CWnd::BindDefaultProperty  
 呼び出し元のオブジェクトの既定単純なバインドされたプロパティ (たとえば、編集コントロール)、タイプ ライブラリでマークされたを基になるデータ ソース コントロールのデータ ソース、ユーザー名、パスワード、および SQL プロパティで定義されているカーソルにバインドします。  
  
```  
void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 データ ソース コントロールにバインドするのには、データ バインド コントロールのプロパティの DISPID を指定します。  
  
 `vtProp`  
 バインドするプロパティの種類を指定 — たとえば、 `VT_BSTR`、 **VT_VARIANT**のようにします。  
  
 `szFieldName`  
 プロパティをバインドする、データ ソース コントロールによって提供されたカーソルで、列の名前を指定します。  
  
 `pDSCWnd`  
 プロパティのバインド先ホスト データ ソースを制御するウィンドウを指定します。 呼び出す`GetDlgItem`リソース id をドメイン コント ローラーのホスト ウィンドウのこのポインターを取得します。  
  
### <a name="remarks"></a>コメント  
 `CWnd`この関数を呼び出すオブジェクトは、データ バインド コントロールである必要があります。  
  
### <a name="example"></a>例  
 `BindDefaultProperty` 次のコンテキストで使用できます。  
  
 [!code-cpp[NVC_MFC_AxDataBinding#1](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#2](../../mfc/reference/codesnippet/cpp/cwnd-class_7.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#3](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="bindproperty"></a>  Cwnd::bindproperty  
 データ ソース コントロールにデータ バインド コントロール (グリッド コントロールなど) のカーソル バインド プロパティをバインドし、そのリレーションシップを MFC バインド マネージャーに登録します。  
  
```  
void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispId*  
 データ ソース コントロールにバインドするのには、データ バインド コントロールのプロパティの DISPID を指定します。  
  
 `pWndDSC`  
 プロパティのバインド先ホスト データ ソースを制御するウィンドウを指定します。 呼び出す`GetDlgItem`リソース id をドメイン コント ローラーのホスト ウィンドウのこのポインターを取得します。  
  
### <a name="remarks"></a>コメント  
 `CWnd`この関数を呼び出すオブジェクトは、データ バインド コントロールである必要があります。  
  
### <a name="example"></a>例  
 `BindProperty` 次のコンテキストで使用できます。  
  
 [!code-cpp[NVC_MFC_AxDataBinding#1](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#4](../../mfc/reference/codesnippet/cpp/cwnd-class_9.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#3](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="bringwindowtotop"></a>  CWnd::BringWindowToTop  
 `CWnd` を重なったウィンドウのスタックの最上位に移動します。  
  
```  
void BringWindowToTop();
```  
  
### <a name="remarks"></a>コメント  
 また、`BringWindowToTop` により、ポップアップ ウィンドウ、トップレベル ウィンドウ、および MDI 子ウィンドウがアクティブになります。 `BringWindowToTop` メンバー関数は、重なったウィンドウによって部分的または完全に隠されているウィンドウを表示する場合に使用します。  
  
 この関数は、Win32 を呼び出すだけ[BringWindowToTop](http://msdn.microsoft.com/library/windows/desktop/ms632673\(v=vs.85\).aspx)関数。 呼び出す、 [SetWindowPos](#setwindowpos) Z オーダーでウィンドウの位置を変更する関数。 `BringWindowToTop` 関数では、ウィンドウ スタイルが変更され、そのウィンドウがトップレベル ウィンドウになることはありません。 詳細については、次を参照してください[HWND_TOP と HWND_TOPMOST の違いは何です。](http://blogs.msdn.com/b/oldnewthing/archive/2005/11/21/495246.aspx)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#71](../../mfc/reference/codesnippet/cpp/cwnd-class_10.cpp)]  
  
##  <a name="calcwindowrect"></a>  CWnd::CalcWindowRect  
 指定したクライアントの四角形を含めることができるウィンドウの四角形を計算します。  
  
```  
virtual void CalcWindowRect(
    LPRECT lpClientRect,  
    UINT nAdjustType = adjustBorder);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `lpClientRect`  
 四角形の構造体へのポインター。 入力では、この構造体には、クライアントの四角形が含まれています。 メソッドが完了したら、この構造体には、指定したクライアントの四角形を含めることができるウィンドウの四角形が含まれています。  
  
 [入力] `nAdjustType`  
 使用して`CWnd::adjustBorder`せずウィンドウ座標を計算する、`WS_EX_CLIENTEDGE`スタイルです。 それ以外の場合、使用`CWnd::adjustOutside`です。  
  
### <a name="remarks"></a>コメント  
 計算されるウィンドウの四角形のサイズでは、メニュー バーの領域は含まれません。  
  
 使用制限については、次を参照してください。 [AdjustWindowRectEx](http://msdn.microsoft.com/library/windows/desktop/ms632667)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#72](../../mfc/reference/codesnippet/cpp/cwnd-class_11.cpp)]  
  
##  <a name="canceltooltips"></a>  CWnd::CancelToolTips  
 ツール ヒントが現在表示されている場合、画面から、ツール ヒントを削除するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL CancelToolTips(BOOL bKeys = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bKeys*  
 **TRUE**キーが押され、ステータス バーのテキストを既定値以外に設定したときに、ツール ヒントを取り消すにそれ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数を使用するのには影響しません、コードによって管理されるツール ヒントです。 これによって管理されるツール ヒント コントロールにのみ影響[CWnd::EnableToolTips](#enabletooltips)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#73](../../mfc/reference/codesnippet/cpp/cwnd-class_12.cpp)]  
  
##  <a name="centerwindow"></a>  CWnd::CenterWindow  
 ウィンドウをその親ウィンドウの中央に揃えます。  
  
```  
void CenterWindow(CWnd* pAlternateOwner = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pAlternateOwner`  
 基準となることが別のウィンドウへのポインターには、(親ウィンドウよりもその他) が中央揃えされます。  
  
### <a name="remarks"></a>コメント  
 通常から呼び出されます[CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)アプリケーションのメイン ウィンドウの基準としたセンター ダイアログ ボックスにします。 既定では、その親ウィンドウとポップアップ ウィンドウをそのオーナーを基準とした子ウィンドウの中央に関数。 ポップアップ ウィンドウが所有していない場合は、画面に対して相対的中央揃えされます。 所有者または親ではない特定のウィンドウの基準とした、ウィンドウの中央に、`pAlternateOwner`パラメーターは、有効なウィンドウに設定することがあります。 画面の中央には、によって返される値を渡す[に揃える](#getdesktopwindow)として`pAlternateOwner`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#74](../../mfc/reference/codesnippet/cpp/cwnd-class_13.cpp)]  
  
##  <a name="changeclipboardchain"></a>  CWnd::ChangeClipboardChain  
 削除`CWnd`で指定されたウィンドウ化されクリップボード ビューアーのチェインから`hWndNext`の子孫、`CWnd`チェーン内の先祖です。  
  
```  
BOOL ChangeClipboardChain(HWND hWndNext);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndNext`  
 これに続くウィンドウを識別`CWnd`クリップボード ビューアーのチェインでします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="checkdlgbutton"></a>  CWnd::CheckDlgButton  
 (場所で横にチェック マーク) をオンまたはオフ (削除からチェック マーク) ボタン、またはその 3 つの状態のボタンの状態を変更します。  
  
```  
void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDButton`  
 変更する ボタンを指定します。  
  
 `nCheck`  
 実行するアクションを指定します。 場合`nCheck`0 以外の場合は、`CheckDlgButton`メンバー関数は、ボタンの横にチェック マークを挿入する以外の場合は 0 の場合、チェック マークが削除されます。 3 つの状態のボタンの場合は`nCheck`2 は、ボタンの状態が不定になります。  
  
### <a name="remarks"></a>コメント  
 `CheckDlgButton`関数の送信、 [BM_SETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775989)メッセージを指定したボタンをクリックします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#75](../../mfc/reference/codesnippet/cpp/cwnd-class_14.cpp)]  
  
##  <a name="checkradiobutton"></a>  CWnd::CheckRadioButton  
 選択 (チェック マークを追加します)、グループ内の特定のオプション ボタンおよびクリア (チェック マーク) 他のすべてのオプション グループ内のボタンです。  
  
```  
void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFirstButton`  
 グループ内の最初のラジオ ボタンの整数識別子を指定します。  
  
 `nIDLastButton`  
 グループ内の最後のラジオ ボタンの整数識別子を指定します。  
  
 `nIDCheckButton`  
 チェックするラジオ ボタンの整数識別子を指定します。  
  
### <a name="remarks"></a>コメント  
 `CheckRadioButton`関数の送信、 [BM_SETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775989)メッセージを指定されたオプション ボタンをクリックします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#76](../../mfc/reference/codesnippet/cpp/cwnd-class_15.cpp)]  
  
##  <a name="childwindowfrompoint"></a>  CWnd::ChildWindowFromPoint  
 これを決定場合、いずれかに属する子ウィンドウの`CWnd`指定したポイントが含まれています。  
  
```  
CWnd* ChildWindowFromPoint(POINT point) const;  
  
CWnd* ChildWindowFromPoint(
    POINT point,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 テストするポイントのクライアント座標を指定します。  
  
 *nflags*  
 スキップするには、どの子ウィンドウを指定します。 このパラメーターは、次の値の組み合わせを指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|**CWP_ALL**|すべての子ウィンドウは省略しないでください。|  
|**CWP_SKIPINVISIBLE**|非表示の子ウィンドウをスキップします|  
|**CWP_SKIPDISABLED**|無効な子ウィンドウをスキップします|  
|**CWP_SKIPTRANSPARENT**|透過的な子ウィンドウをスキップします|  
  
### <a name="return-value"></a>戻り値  
 ポイントを含む子ウィンドウを識別します。 **NULL**特定のポイントがクライアント領域の外側にある場合。 場合は、ポイントがクライアント領域内では、任意の子ウィンドウでは、含まれていない`CWnd`が返されます。  
  
 このメンバー関数では、指定したポイントを含む非表示または無効な子ウィンドウを返します。  
  
 複数のウィンドウには、指定したポイントが含まれます。 ただし、この関数だけを返す、 `CWnd`* 最初のウィンドウの発生したポイントを含むです。  
  
 `CWnd`* 返される、一時的なと、後で使用するために格納する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#77](../../mfc/reference/codesnippet/cpp/cwnd-class_16.cpp)]  
  
##  <a name="clienttoscreen"></a>  CWnd::ClientToScreen  
 ディスプレイ上の指定された点または四角形のクライアント座標を画面座標に変換します。  
  
```  
void ClientToScreen(LPPOINT lpPoint) const;  void ClientToScreen(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoint`  
 指す、 [POINT 構造体](../../mfc/reference/point-structure1.md)または`CPoint`クライアントを含むオブジェクトを変換する座標します。  
  
 `lpRect`  
 指す、 [RECT 構造体](../../mfc/reference/rect-structure1.md)または`CRect`クライアントを含むオブジェクトを変換する座標します。  
  
### <a name="remarks"></a>コメント  
 `ClientToScreen`メンバー関数でのクライアント座標を使用して、**ポイント**または`RECT`構造体、または`CPoint`または`CRect`によって指されるオブジェクト`lpPoint`または`lpRect`新しいを計算するには画面座標。構造の座標に新しい座標によってに置き換えます。 新しい画面座標では、システム ディスプレイの左上隅に対して相対的です。  
  
 `ClientToScreen`メンバー関数は、指定された点または四角形をクライアント座標では前提としています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#78](../../mfc/reference/codesnippet/cpp/cwnd-class_17.cpp)]  
  
##  <a name="closewindow"></a>  CWnd::CloseWindow  
 ウィンドウを最小化します。  
  
```  
void CloseWindow();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[CloseWindow](http://msdn.microsoft.com/library/windows/desktop/ms632678)Windows SDK で説明されている。  
  
##  <a name="continuemodal"></a>  CWnd::ContinueModal  
 によって呼び出されます[RunModalLoop](#runmodalloop)をモーダルの状態を終了する場合を判断します。  
  
```  
virtual BOOL ContinueModal();
```  
  
### <a name="return-value"></a>戻り値  
 モーダルの場合は 0 以外のループです。 続行するのには場合は 0[は](#endmodalloop)と呼びます。  
  
### <a name="remarks"></a>コメント  
 既定では、0 以外を返しますまで`EndModalLoop`と呼びます。  
  
##  <a name="create"></a>  CWnd::Create  
 指定した子ウィンドウを作成し、それにアタッチ、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクト。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    Const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszClassName`  
 登録されているシステム ウィンドウ クラスの名前を表す null で終わる文字列へのポインターまたは、定義済みのシステム ウィンドウ クラスの名前。  
  
 [入力] `lpszWindowName`  
 ウィンドウを表す null で終わる文字列へのポインターの表示名です。それ以外の場合`NULL`のないウィンドウの表示名。  
  
 [入力] `dwStyle`  
 ビットごとの組み合わせ (OR)[ウィンドウ スタイル](styles-used-by-mfc.md#window-styles)です。 `WS_POPUP`オプションが有効なスタイルではありません。  
  
 [入力] `rect`  
 サイズとウィンドウの親ウィンドウの左上隅の相対位置です。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。  
  
 [入力] `nID`  
 ウィンドウの ID です。  
  
 [入力] `pContext`  
 ポインター、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造、アプリケーションのドキュメント/ビュー アーキテクチャをカスタマイズするために使用します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
> [!WARNING]
> `CWnd::PreCreateWindow` hMenu メンバーを割り当てるようになりました、`CREATESTRUCT`パラメーターを`this`ポインターの場合は、メニュー`NULL`スタイルが含まれています`WS_CHILD`です。 適切に機能をダイアログ コントロールにではない ID があることを確認してください`NULL`です。  
>   
>  この変更は、マネージ/ネイティブの相互運用シナリオで、クラッシュを修正します。 A`TRACE`ステートメントで`CWnd::Create`問題の開発者に警告します。  
  
 使用して、 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass)ウィンドウ クラスを登録します。 ユーザーは、登録されているクラスがモジュールで使用可能なウィンドウを定義します。  
  
 [CWnd::OnCreate](#oncreate)メソッドは、前に呼び出されます、`Create`メソッドから返される、ウィンドウが表示される前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#79](../../mfc/reference/codesnippet/cpp/cwnd-class_18.cpp)]  
  
##  <a name="createaccessibleproxy"></a>  CWnd::CreateAccessibleProxy  
 指定されたオブジェクトの Active Accessibility プロキシを作成します。  
  
```  
virtual HRESULT CreateAccessibleProxy(
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult);
```  
   
### <a name="parameters"></a>パラメーター  
 `wParam`  
 Active Accessibility プロキシによってアクセスされるオブジェクトを識別します。 次の値のいずれかになります  
  
|[値]|説明|  
|-----------|-------------|  
|**OBJID_CLIENT**|ウィンドウのクライアント領域を指します。|  
  
 `lParam`  
 追加のメッセージに依存する情報を提供します。  
  
 `pResult`  
 ポインター、 **LRESULT**結果コードを格納します。  
  
### <a name="remarks"></a>コメント  
 指定されたオブジェクトの Active Accessibility プロキシを作成します。  
  
##  <a name="createcaret"></a>  CWnd::CreateCaret  
 システム キャレット新しい図形を作成し、そのキャレットの所有権を要求します。  
  
```  
void CreateCaret(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBitmap`  
 カレットの形を定義するビットマップを識別します。  
  
### <a name="remarks"></a>コメント  
 ビットマップ必要があります以前によって作成された、 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap)メンバー関数の場合、 [CreateDIBitmap](http://msdn.microsoft.com/library/windows/desktop/dd183491) Windows 関数または[CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)メンバー関数。  
  
 `CreateCaret` 自動的にいずれかのウィンドウに関係なく、キャレットを所有している場合は、前のキャレットの形を破棄します。 作成されると、カーソルは最初に表示されません。 カレットを表示する、 [ShowCaret](#showcaret)メンバー関数を呼び出す必要があります。  
  
 システム キャレットは、共有リソースです。 `CWnd` 入力フォーカスがある、またはアクティブな場合にのみ、キャレットを作成する必要があります。 入力フォーカスを失い、非アクティブになったまたは前に、キャレットを破棄にする必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#80](../../mfc/reference/codesnippet/cpp/cwnd-class_19.cpp)]  
  
##  <a name="createcontrol"></a>  CWnd::CreateControl  
 このメンバー関数を使用して、MFC プログラムで表される ActiveX コントロールを作成、`CWnd`オブジェクト。  
  
```  
BOOL CreateControl(
    LPCTSTR pszClass,  
    LPCTSTR pszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);

 
BOOL CreateControl(
    REFCLSID clsid,  
    LPCTSTR pszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);

 
BOOL CreateControl(
    REFCLSID clsid,  
    LPCTSTR pszWindowName,  
    DWORD dwStyle,  
    const POINT* ppt,  
    const SIZE* psize,  
    CWnd* pParentWnd,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pszClass*  
 この文字列は OLE「短い名前」を含めることが (ProgID) クラス、例:"CIRC3 です。Circ3Ctrl.1"です。 名前は、コントロールによって登録されている同じ名前と一致する必要があります。 代わりに、文字列がの文字列形式を含めることがあります、 **CLSID**、中かっこ、たとえば、"{9DBAFCCF-592F-101B-85CE-00608CEC297B}"に含まれています。 どちらの場合、`CreateControl`対応するクラス ID を文字列に変換します  
  
 *pszWindowName*  
 コントロールに表示されるテキストへのポインター。 (該当する場合) は、コントロールのキャプションまたはテキストのプロパティの値を設定します。 場合**NULL**コントロールのキャプションまたはテキストのプロパティは変更されません。  
  
 `dwStyle`  
 Windows のスタイルです。 使用できるスタイルは、「解説」に一覧表示されます。  
  
 `rect`  
 コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)です。  
  
 `ppt`  
 指す、 [POINT 構造体](../../mfc/reference/point-structure1.md)または`CPoint`コントロールの左上隅を含むオブジェクトです。  
  
 `pSize`  
 指す、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または`CSize`コントロールのサイズを格納しているオブジェクト  
  
 `pParentWnd`  
 コントロールの親ウィンドウを指定します。 なければなりません**NULL**です。  
  
 `nID`  
 コントロールの ID を指定します  
  
 `pPersist`  
 ポインター、 [CFile](../../mfc/reference/cfile-class.md)コントロールの永続的な状態を格納します。 既定値は**NULL**、コントロール自体の初期化を永続的な記憶域からの状態を復元することがなくすることを示すです。 ない場合**NULL**へのポインターである必要があります、 `CFile`-派生ストリームまたはストレージのいずれかの形式でのコントロールの永続的なデータを格納するオブジェクト。 このデータは、クライアントの以前のライセンス認証で保存されている可能性があります。 `CFile`他のデータを含めることができますが、読み取り/書き込みを指すポインターへの呼び出し時に永続的なデータの最初のバイトに設定する必要があります`CreateControl`です。  
  
 `bStorage`  
 示すかどうかのデータを`pPersist`IStorage または IStream データとして解釈する必要があります。 場合内のデータ`pPersist`、記憶域は、`bStorage`する必要があります**TRUE**です。 場合内のデータ`pPersist`ストリーム、`bStorage`する必要があります**FALSE**です。 既定値は**FALSE**です。  
  
 *bstrLicKe*y  
 省略可能なライセンス キー データ。 このデータは、実行時ライセンス キーが必要なコントロールを作成するためにのみ必要です。 コントロールは、ライセンスをサポートする場合を正常にコントロールを作成するためのライセンス キーを指定する必要があります。 既定値は**NULL**です。  
  
 `clsid`  
 コントロールの一意のクラス ID。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `CreateControl` 直接のアナログは、 [cwnd::create](#create)関数で、ウィンドウを作成、`CWnd`です。 `CreateControl` 通常のウィンドウではなく、ActiveX コントロールを作成します。  
  
 Windows のサブセットのみ`dwStyle`はフラグ`CreateControl`:  
  
- **WS_VISIBLE**が最初に表示するウィンドウを作成します。 通常のウィンドウと同様に、すぐに表示するコントロールをするかどうかに必要です。  
  
- **WS_DISABLED**最初に無効になっているウィンドウを作成します。 無効になっているウィンドウは、ユーザーから入力を受け取ることはできません。 コントロールは Enabled プロパティを持つ場合、設定できます。  
  
- `WS_BORDER` 細い境界線でウィンドウを作成します。 コントロールに BorderStyle プロパティが設定されている場合、設定できます。  
  
- **WS_GROUP**コントロールのグループの最初のコントロールを指定します。 ユーザーを変更できますキーボード フォーカス、グループ内の 1 つのコントロールから、次への方向キーを使用しています。 定義されているすべてのコントロール、 **WS_GROUP**後、同じグループに属している、最初のコントロールのスタイルを設定します。 [次へ] のコントロールに、 **WS_GROUP**スタイルは、グループを終了し、[次へ] のグループを開始します。  
  
- **WS_TABSTOP**ユーザーが TAB キーを押すと、キーボード フォーカスを受信できるコントロールを指定します。 次のコントロールにキーボード フォーカスを移した TAB キーを押して、 **WS_TABSTOP**スタイル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#81](../../mfc/reference/codesnippet/cpp/cwnd-class_20.h)]  
  
##  <a name="createex"></a>  CWnd::CreateEx  
 指定したウィンドウを作成し、それにアタッチ、`CWnd`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    HWND hWndParent,  
    HMENU nIDorHMenu,  
    LPVOID lpParam = NULL);

 
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    LPVOID lpParam = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 ビットごとの組み合わせ (OR)[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)それ以外の`NULL`既定の拡張ウィンドウ スタイル。  
  
 `lpszClassName`  
 登録されているシステム ウィンドウ クラスの名前を表す null で終わる文字列へのポインターまたは、定義済みのシステム ウィンドウ クラスの名前。  
  
 `lpszWindowName`  
 ウィンドウを表す null で終わる文字列へのポインターの表示名です。それ以外の場合`NULL`のないウィンドウの表示名。  
  
 `dwStyle`  
 ビットごとの組み合わせ (OR)[ウィンドウ スタイル](styles-used-by-mfc.md#window-styles)それ以外の`NULL`の既定のウィンドウ スタイル。  
  
 `x`  
 画面の左側のウィンドウまたは親ウィンドウの初期の水平方向の距離。  
  
 `y`  
 画面の最上位からウィンドウまたは親ウィンドウの初期の垂直距離です。  
  
 `nWidth`  
 (ピクセル単位) ウィンドウの幅。  
  
 `nHeight`  
 (ピクセル単位) ウィンドウの高さ。  
  
 `hwndParent`  
 親ウィンドウへのハンドルを子ウィンドウそれ以外の場合、ウィンドウが所有者である場合は、オーナー ウィンドウのハンドルを返します。  
  
 `nIDorHMenu`  
 子ウィンドウ、ウィンドウの ID。それ以外の場合、ウィンドウのメニューの ID。  
  
 `lpParam`  
 渡されるユーザー データへのポインター、 [CWnd::OnCreate](#oncreate)メソッドで、`lpCreateParams`フィールドです。  
  
 `rect`  
 サイズと画面に対して相対的ウィンドウまたは親ウィンドウの位置。  
  
 `pParentWnd`  
 子ウィンドウ、親ウィンドウへのポインターをウィンドウが所有者である場合は、オーナー ウィンドウに、それ以外の場合のポインター。  
  
 `nID`  
 子ウィンドウ、ウィンドウの ID。それ以外の場合、ウィンドウのメニューの ID。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
> [!WARNING]
> `CWnd::PreCreateWindow` hMenu メンバーを割り当てるようになりました、`CREATESTRUCT`パラメーターを`this`ポインターの場合は、メニュー`NULL`スタイルが含まれています`WS_CHILD`です。 適切に機能をダイアログ コントロールにではない ID があることを確認してください`NULL`です。  
>   
>  この変更は、マネージ/ネイティブの相互運用シナリオで、クラッシュを修正します。 A`TRACE`ステートメントで`CWnd::Create`問題の開発者に警告します。  
  
 拡張ウィンドウ スタイルを既定値は`WS_EX_LEFT`します。 既定のウィンドウ スタイルが`WS_OVERLAPPED`です。  
  
 使用して、 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass)ウィンドウ クラスを登録します。 ユーザーは、登録されているクラスがモジュールで使用可能なウィンドウを定義します。  
  
 子ウィンドウのディメンションでは、親ウィンドウのクライアント領域の左上隅に対して相対的です。 トップ レベル ウィンドウに対してディメンションは、画面の左上隅に対する相対です。  
  
 [CWnd::OnCreate](#oncreate)メソッドは、前に呼び出されます、`CreateEx`メソッドから返される、ウィンドウが表示される前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#82](../../mfc/reference/codesnippet/cpp/cwnd-class_21.cpp)]  
  
##  <a name="creategraycaret"></a>  CWnd::CreateGrayCaret  
 灰色の長方形でシステム キャレットを作成し、そのキャレットの所有権を要求します。  
  
```  
void CreateGrayCaret(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 (論理単位で) 内のキャレットの幅を指定します。 このパラメーターが 0 の場合は、幅がシステム定義のウィンドウの境界線の幅に設定されます。  
  
 `nHeight`  
 (論理単位で) カーソルの高さを指定します。 このパラメーターが 0 の場合は、高さがシステム定義のウィンドウの境界線の高さに設定されます。  
  
### <a name="remarks"></a>コメント  
 カレットの形には、行またはブロックを指定できます。  
  
 パラメーター`nWidth`と`nHeight`キャレットの幅と高さを (論理単位で) 指定以外の場合は、実際の幅と高さ (ピクセル単位) は、マッピング モードによって異なります。  
  
 システムのウィンドウの境界線の幅または高さを取得できる、[問題](http://msdn.microsoft.com/library/windows/desktop/ms724385)で Windows の機能、 **SM_CXBORDER**と**SM_CYBORDER**インデックス。 ウィンドウの境界線の幅または高さを使用して、カレットが高解像度のディスプレイに表示されることをによりします。  
  
 `CreateGrayCaret`キャレットどのウィンドウに関係なく、所有している場合、前のキャレット図形がメンバー関数によって自動的に破棄します。 作成されると、カーソルは最初に表示されません。 カレットを表示する、 [ShowCaret](#showcaret)メンバー関数を呼び出す必要があります。  
  
 システム キャレットは、共有リソースです。 `CWnd` 入力フォーカスがある、またはアクティブな場合にのみ、キャレットを作成する必要があります。 入力フォーカスを失い、非アクティブになったまたは前に、キャレットを破棄にする必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#83](../../mfc/reference/codesnippet/cpp/cwnd-class_22.cpp)]  
  
##  <a name="createsolidcaret"></a>  CWnd::CreateSolidCaret  
 システム キャレット塗りつぶし四角形を作成し、そのキャレットの所有権を要求します。  
  
```  
void CreateSolidCaret(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 (論理単位で) 内のキャレットの幅を指定します。 このパラメーターが 0 の場合は、幅がシステム定義のウィンドウの境界線の幅に設定されます。  
  
 `nHeight`  
 (論理単位で) カーソルの高さを指定します。 このパラメーターが 0 の場合は、高さがシステム定義のウィンドウの境界線の高さに設定されます。  
  
### <a name="remarks"></a>コメント  
 カレットの形には、行またはブロックを指定できます。  
  
 パラメーター`nWidth`と`nHeight`キャレットの幅と高さを (論理単位で) 指定以外の場合は、実際の幅と高さ (ピクセル単位) は、マッピング モードによって異なります。  
  
 システムのウィンドウの境界線の幅または高さを取得できる、[問題](http://msdn.microsoft.com/library/windows/desktop/ms724385)で Windows の機能、 **SM_CXBORDER**と**SM_CYBORDER**インデックス。 ウィンドウの境界線の幅または高さを使用して、カレットが高解像度のディスプレイに表示されることをによりします。  
  
 `CreateSolidCaret`キャレットどのウィンドウに関係なく、所有している場合、前のキャレット図形がメンバー関数によって自動的に破棄します。 作成されると、カーソルは最初に表示されません。 カレットを表示する、 [ShowCaret](#showcaret)メンバー関数を呼び出す必要があります。  
  
 システム キャレットは、共有リソースです。 `CWnd` 入力フォーカスがある、またはアクティブな場合にのみ、キャレットを作成する必要があります。 入力フォーカスを失い、非アクティブになったまたは前に、キャレットを破棄にする必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#84](../../mfc/reference/codesnippet/cpp/cwnd-class_23.cpp)]  
  
##  <a name="cwnd"></a>  CWnd::CWnd  
 `CWnd` オブジェクトを構築します。  
  
```  
CWnd();
```  
  
### <a name="remarks"></a>コメント  
 Windows のウィンドウは作成されず、まで接続されている、 [CreateEx](#createex)または[作成](#create)メンバー関数が呼び出されます。  
  
##  <a name="default"></a>  CWnd::Default  
 既定のウィンドウ プロシージャを呼び出します。  
  
```  
LRESULT Default();
```  
  
### <a name="return-value"></a>戻り値  
 送信メッセージに依存します。  
  
### <a name="remarks"></a>コメント  
 既定のウィンドウ プロシージャは、既定のアプリケーションが処理しないウィンドウ メッセージに対して処理を提供します。 このメンバー関数は、すべてのメッセージが処理されるようにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#85](../../mfc/reference/codesnippet/cpp/cwnd-class_24.cpp)]  
  
##  <a name="defwindowproc"></a>  CWnd::DefWindowProc  
 アプリケーションが処理しないウィンドウ メッセージに対して既定の処理を提供する既定のウィンドウ プロシージャを呼び出します。  
  
```  
virtual LRESULT DefWindowProc(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 処理する Windows メッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 送信メッセージに依存します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、すべてのメッセージが処理されるようにします。 ウィンドウ プロシージャが受け取るものと同じパラメーターを使用して呼び出す必要があります。  
  
##  <a name="deletetempmap"></a>  CWnd::DeleteTempMap  
 アイドル処理ハンドラーによって自動的に呼び出されます、`CWinApp`オブジェクト。  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>コメント  
 一時的な削除`CWnd`によって作成されたオブジェクト、`FromHandle`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#86](../../mfc/reference/codesnippet/cpp/cwnd-class_25.cpp)]  
  
##  <a name="destroywindow"></a>  に  
 接続されている Windows のウィンドウを破棄、`CWnd`オブジェクト。  
  
```  
virtual BOOL DestroyWindow();
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが破棄された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `DestroyWindow`メンバー関数が、ウィンドウを非アクティブ化し、入力フォーカスを削除する適切なメッセージを送信します。 ウィンドウのメニューの破棄、アプリケーション キューをフラッシュ、未完了のタイマーを破棄、クリップボード所有権の除去、場合に、クリップボード ビューアーのチェインを中断`CWnd`がビューアーのチェインの上部にします。 送信[WM_DESTROY](#ondestroy)と[へ](#onncdestroy)メッセージ ウィンドウにします。 破棄しません、`CWnd`オブジェクト。  
  
 `DestroyWindow` クリーンアップを実行するためのプレース ホルダーがします。 `DestroyWindow`仮想関数は、いずれかで表示される`CWnd`-クラス ビュー内のクラスを派生します。 この関数をオーバーライドする場合でも、 `CWnd`-派生クラスに`DestroyWindow`は必ずしもは呼び出されません。 場合`DestroyWindow`を明示的に呼び出すが、独自のコードで呼び出される場合がある場合、MFC のコードでは呼び出されません。  
  
 たとえば、オーバーライドされている`DestroyWindow`で、 `CView`-クラスを派生します。 MFC ソース コードを呼び出しませんため`DestroyWindow`のいずれかでその`CFrameWnd`-派生クラスで、オーバーライドされた`DestroyWindow`明示的に呼び出す場合を除きは呼び出されません。  
  
 ウィンドウが任意の windows の親である場合は、親ウィンドウが破棄されるときにこれらの子ウィンドウが自動的に破棄します。 `DestroyWindow`メンバー関数が子ウィンドウを破棄最初しウィンドウ自体です。  
  
 `DestroyWindow`メンバー関数によって作成されたモードレス ダイアログ ボックスを破棄も[CDialog::Create](../../mfc/reference/cdialog-class.md#create)です。  
  
 場合、`CWnd`子ウィンドウが破棄されはありません、 [WS_EX_NOPARENTNOTIFY](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)スタイル セットで、 [WM_PARENTNOTIFY](https://msdn.microsoft.com/library/ms632638.aspx)親にメッセージを送信します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#87](../../mfc/reference/codesnippet/cpp/cwnd-class_26.cpp)]  
  
##  <a name="detach"></a>  CWnd::Detach  
 `CWnd` オブジェクトから Windows のハンドルを切り離し、そのハンドルを返します。  
  
```  
HWND Detach();
```  
  
### <a name="return-value"></a>戻り値  
 A `HWND` Windows オブジェクトにします。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::Attach](#attach)です。  
  
##  <a name="dlgdirlist"></a>  CWnd::DlgDirList  
 リスト ボックスにファイル リストまたはディレクトリ リストを設定します。  
  
```  
int DlgDirList(
    LPTSTR lpPathSpec,  
    int nIDListBox,  
    int nIDStaticPath,  
    UINT nFileType);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPathSpec`  
 パスまたはファイル名を表す null で終わる文字列へのポインター。 `DlgDirList` この文字列は、対象となる変更を格納するのに十分な長さを変更します。 詳細については、次の「解説」セクションを参照してください。  
  
 `nIDListBox`  
 リスト ボックスの識別子を指定します。 場合`nIDListBox`0 の場合は、`DlgDirList`リスト ボックスは表示されませんが存在し、いずれかを入力しないことを前提としています。  
  
 `nIDStaticPath`  
 現在のドライブとディレクトリを表示するために使用された静的テキスト コントロールの識別子を指定します。 場合`nIDStaticPath`0 の場合は、`DlgDirList`このようなテキスト コントロールが存在しないことを前提としています。  
  
 `nFileType`  
 ファイルを表示するための属性を指定します。 次の値の任意の組み合わせを指定できます。  
  
- **DDL_READWRITE**読み取り/書き込みデータ ファイルに追加の属性がありません。  
  
- **DDL_READONLY**読み取り専用ファイル。  
  
- **DDL_HIDDEN**隠しファイルです。  
  
- **DDL_SYSTEM**システム ファイルです。  
  
- **DDL_DIRECTORY**ディレクトリ。  
  
- **DDL_ARCHIVE**アーカイブします。  
  
- **DDL_POSTMSGS LB_DIR**フラグ。 場合、 **LB_DIR**フラグが設定されて、Windows によって生成されたメッセージは配置`DlgDirList`アプリケーションのキューです。 それ以外の場合、送信されます ダイアログ ボックスのプロシージャに直接できます。  
  
- **含んだ**ドライブです。 場合、**含んだ**フラグが設定されて、 **DDL_EXCLUSIVE**フラグが自動的に設定されます。 したがって、ドライブとファイルを含むディレクトリの一覧を作成する必要がありますを呼び出して`DlgDirList`2 回: が 1 回、**含んだ**一覧の残りのフラグのセットとに 1 回のフラグを設定します。  
  
- **DDL_EXCLUSIVE**排他ビットです。 排他のビットが設定されている場合、指定した型のファイルのみが表示されます。それ以外の場合、指定した種類のファイルと通常のファイルが表示されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `DlgDirList` 送信[LB_RESETCONTENT](http://msdn.microsoft.com/library/windows/desktop/bb761325)と[LB_DIR](http://msdn.microsoft.com/library/windows/desktop/bb775185)をリスト ボックスにメッセージ。 指定された、リスト ボックスを塗りつぶす`nIDListBox`によって指定されたパスに一致するすべてのファイルの名前を持つ`lpPathSpec`します。  
  
 `lpPathSpec`パラメーターには、次の形式。  
  
 `[drive:] [ [\u]directory[\idirectory]...\u] [filename]`  
  
 この例では`drive`、ドライブ文字は、`directory`は有効なディレクトリ名、および*ファイル名*に少なくとも 1 つのワイルドカードを含める必要がある有効なファイル名は、します。 ワイルドカードはありと一致して、任意の文字とアスタリスク (*)、疑問符 ( **\***)、任意の文字数が一致を意味します。  
  
 長さが 0 の文字列を指定する場合`lpPathSpec`にディレクトリ名のみを指定する任意のファイルの仕様を含めない場合は、変更するは、文字列または"*.\*"です。  
  
 場合`lpPathSpec`ドライブまたはディレクトリ名を含む、現在のドライブとディレクトリが、リスト ボックスを入力する前に、指定したドライブとディレクトリに変更されます。 によって識別されるテキスト コントロール`nIDStaticPath`も新しいドライブやディレクトリの名前で更新します。  
  
 リスト ボックスでは、いっぱいになった後`lpPathSpec`パスのドライブまたはディレクトリの部分を削除することで更新します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#88](../../mfc/reference/codesnippet/cpp/cwnd-class_27.cpp)]  
  
##  <a name="dlgdirlistcombobox"></a>  CWnd::DlgDirListComboBox  
 コンボ ボックスにファイル リストまたはディレクトリ リストを設定します。  
  
```  
int DlgDirListComboBox(
    LPTSTR lpPathSpec,  
    int nIDComboBox,  
    int nIDStaticPath,  
    UINT nFileType);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPathSpec`  
 パスまたはファイル名を表す null で終わる文字列へのポインター。 `DlgDirListComboBox` このデータは、リテラル文字列の形式にすることはできませんので、この文字列を変更します。 次の「解説」セクションを参照してください。  
  
 `nIDComboBox`  
 ダイアログ ボックスで、コンボ ボックスの識別子を指定します。 場合`nIDComboBox`0 の場合は、`DlgDirListComboBox`コンボ ボックスは表示されませんが存在し、いずれかを入力しないことを前提としています。  
  
 `nIDStaticPath`  
 現在のドライブとディレクトリを表示するために使用された静的テキスト コントロールの識別子を指定します。 場合`nIDStaticPath`0 の場合は、`DlgDirListComboBox`このようなテキスト コントロールが存在しないことを前提としています。  
  
 `nFileType`  
 DOS ファイルを表示するファイルの属性を指定します。 次の値の任意の組み合わせを指定できます。  
  
- **DDL_READWRITE**読み取り/書き込みデータ ファイルに追加の属性がありません。  
  
- **DDL_READONLY**読み取り専用ファイル。  
  
- **DDL_HIDDEN**隠しファイルです。  
  
- **DDL_SYSTEM**システム ファイルです。  
  
- **DDL_DIRECTORY**ディレクトリ。  
  
- **DDL_ARCHIVE**アーカイブします。  
  
- **DDL_POSTMSGS CB_DIR**フラグ。 場合、 **CB_DIR**フラグが設定されて、Windows によって生成されたメッセージは配置`DlgDirListComboBox`アプリケーションのキューです。 それ以外の場合、送信されます ダイアログ ボックスのプロシージャに直接できます。  
  
- **含んだ**ドライブです。 場合、**含んだ**フラグが設定されて、 **DDL_EXCLUSIVE**フラグが自動的に設定されます。 したがって、ドライブとファイルを含むディレクトリの一覧を作成する必要がありますを呼び出して`DlgDirListComboBox`2 回: が 1 回、**含んだ**一覧の残りのフラグのセットとに 1 回のフラグを設定します。  
  
- **DDL_EXCLUSIVE**排他ビットです。 排他のビットが設定されている場合、指定した型のファイルのみが表示されます。それ以外の場合、指定した種類のファイルと通常のファイルが表示されます。  
  
### <a name="return-value"></a>戻り値  
 関数の結果を指定します。 リストが作成された、空のリストであっても場合は 0 以外の値です。 戻り値 0 は、入力文字列が有効な検索パスを含まないことを意味します。  
  
### <a name="remarks"></a>コメント  
 `DlgDirListComboBox` 送信[CB_RESETCONTENT](http://msdn.microsoft.com/library/windows/desktop/bb775878)と[CB_DIR](http://msdn.microsoft.com/library/windows/desktop/bb775832)コンボ ボックスへのメッセージ。 指定されたコンボ ボックスのリスト ボックスを塗りつぶす`nIDComboBox`によって指定されたパスに一致するすべてのファイルの名前を持つ`lpPathSpec`します。  
  
 `lpPathSpec`パラメーターには、次の形式。  
  
 `[drive:] [ [\u]directory[\idirectory]...\u] [filename]`  
  
 この例では`drive`、ドライブ文字は、`directory`は有効なディレクトリ名、および*ファイル名*に少なくとも 1 つのワイルドカードを含める必要がある有効なファイル名は、します。 ワイルドカードはありと一致して、任意の文字とアスタリスク (*)、疑問符 () ( **\***)、つまり、任意の文字数に一致します。  
  
 長さ 0 の文字列を指定する場合`lpPathSpec`、現在のディレクトリが使用して`lpPathSpec`は変更されません。 ディレクトリ名のみを指定する任意のファイルの仕様を含めない場合は、変更するは、文字列"*"です。  
  
 場合`lpPathSpec`ドライブまたはディレクトリ名を含む、現在のドライブとディレクトリが、リスト ボックスを入力する前に、指定したドライブとディレクトリに変更されます。 によって識別されるテキスト コントロール`nIDStaticPath`も新しいドライブやディレクトリの名前で更新します。  
  
 コンボ ボックスのリスト ボックスでは、いっぱいになった後`lpPathSpec`パスのドライブまたはディレクトリの部分を削除することで更新します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#89](../../mfc/reference/codesnippet/cpp/cwnd-class_28.cpp)]  
  
##  <a name="dlgdirselect"></a>  CWnd::DlgDirSelect  
 リスト ボックスから現在の選択を取得します。  
  
```  
BOOL DlgDirSelect(
    LPTSTR lpString,  
    int nIDListBox);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpString`  
 リスト ボックスで現在の選択範囲を受け取るバッファーへのポインター。  
  
 `nIDListBox`  
 ダイアログ ボックスで、リスト ボックスの整数の ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 によって、リスト ボックスが満杯になったことを想定しています、 [DlgDirList](#dlgdirlist)メンバー関数と、選択したでは、ドライブ文字、ファイルまたはディレクトリ名。  
  
 `DlgDirSelect`メンバー関数は、選択範囲を指定されたバッファーにコピーする`lpString`です。 選択されていない場合`lpString`は変わりません。  
  
 `DlgDirSelect` 送信[LB_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb775197)と[LB_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761313)をリスト ボックスにメッセージ。  
  
 リスト ボックスから返される 1 つ以上のファイル名はできません。 リスト ボックスでは、複数選択のリスト ボックスをすることはできません。  
  
##  <a name="dlgdirselectcombobox"></a>  CWnd::DlgDirSelectComboBox  
 コンボ ボックスから現在の選択を取得します。  
  
```  
BOOL DlgDirSelectComboBox(
    LPTSTR lpString,  
    int nIDComboBox);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpString`  
 選択したパスを受け取るバッファーへのポインター。  
  
 `nIDComboBox`  
 ダイアログ ボックスで、コンボ ボックスの整数の ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 によって、リスト ボックスが満杯になったことを想定しています、 [DlgDirListComboBox](#dlgdirlistcombobox)メンバー関数と、選択したでは、ドライブ文字、ファイルまたはディレクトリ名。  
  
 `DlgDirSelectComboBox`メンバー関数は、選択範囲を指定したバッファーにコピーします。 選択されていない場合、バッファーの内容は変更されません。  
  
 `DlgDirSelectComboBox` 送信[CB_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb775845)と[CB_GETLBTEXT](http://msdn.microsoft.com/library/windows/desktop/bb775862)コンボ ボックスへのメッセージ。  
  
 コンボ ボックスから返される 1 つ以上のファイル名はできません。  
  
##  <a name="dodataexchange"></a>  CWnd::DoDataExchange  
 ダイアログ データ検証し、交換するためにフレームワークによって呼び出されます。  
  
```  
virtual void DoDataExchange(CDataExchange* pDX);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数を直接呼び出すことはありません。 メソッドによって呼び出されます、 [UpdateData](#updatedata)メンバー関数。 呼び出す`UpdateData`初期化ダイアログ ボックスのコントロールまたはダイアログ ボックスからデータを取得します。  
  
 アプリケーション固有のダイアログ クラスを派生する[CDialog](../../mfc/reference/cdialog-class.md)フレームワークのデータの自動交換と検証を利用する場合は、このメンバー関数をオーバーライドする必要があります。 変数の追加ウィザードが記述このメンバー関数のオーバーライド バージョンを含む、必要なダイアログ データ エクス (チェンジ DDX) およびグローバル関数の呼び出しを検証 (DDV) の「データ マップ」です。  
  
 このメンバー関数のオーバーライド バージョンを自動的に生成するには、ダイアログ エディターでダイアログ リソースを作成し、アプリケーション固有のダイアログ クラスを派生します。 関連付ける新しいダイアログ ボックスで、さまざまなコントロール変数、データ、および検証の範囲変数の追加ウィザードを使用しています。 ウィザードが、書き込み、オーバーライドされた`DoDataExchange`、データ マップを含むです。 変数の追加ウィザードによって生成された例 DDX/DDV コード ブロックを次に示します。  
  
 [!code-cpp[NVC_MFCWindowing#90](../../mfc/reference/codesnippet/cpp/cwnd-class_29.cpp)]  
  
 `DoDataExchange`オーバーライドされたメンバー関数は、ソース ファイルでマクロ ステートメントを付ける必要があります。  
  
 ダイアログ データ エクス チェンジと検証の詳細については、次を参照してください。[フォームでの操作のデータの表示と](../../data/odbc/displaying-and-manipulating-data-in-a-form.md)と[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 変数の追加ウィザードによって生成された、ddx _ と DDV_ マクロの説明は、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)です。  
  
##  <a name="dragacceptfiles"></a>  CWnd::DragAcceptFiles  
 このメンバー関数から、ウィンドウ内でを使用して、`CWnd`ポインターは、アプリケーションの[場合は](../../mfc/reference/cwinapp-class.md#initinstance)ウィンドウを受け入れることを示すために関数が、Windows ファイル マネージャーまたはファイル エクスプ ローラーからファイルを削除.  
  
```  
void DragAcceptFiles(BOOL bAccept = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *BAccept*  
 ドラッグされたファイルを受け入れるかどうかを示すフラグです。  
  
### <a name="remarks"></a>コメント  
 呼び出すウィンドウのみ`DragAcceptFiles`で、`bAccept`パラメーターに設定**TRUE**がそれ自体の Windows メッセージを処理することができるように識別`WM_DROPFILES`です。 たとえば、MDI アプリケーションで場合、`CMDIFrameWnd`内ウィンドウ ポインターを使用、`DragAcceptFiles`関数の呼び出しでのみ、`CMDIFrameWnd`ウィンドウを取得、`WM_DROPFILES`メッセージ。 このメッセージは、すべて開く`CMDIChildWnd`windows です。 `CMDIChildWnd`このメッセージを受信するウィンドウを呼び出す必要があります`DragAcceptFiles`で、`CMDIChildWnd`ウィンドウ ポインター。  
  
 ドラッグされたファイルの受信を停止するにはメンバー関数を呼び出し、 `bAccept` 'éý' **FALSE**です。  
  
##  <a name="dragdetect"></a>  CWnd::DragDetect  
 マウスをキャプチャし、ユーザーが左ボタンを離すか、Esc キーを押すか、または指定した点を中心にしたドラッグ四角形の外にマウスを移動するまで、移動を追跡します。  
  
```  
BOOL DragDetect(POINT pt) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 最初の画面座標で、マウスの位置。 関数は、このポイントを使用して、ドラッグ四角形の座標を決定します。  
  
### <a name="return-value"></a>戻り値  
 ユーザーは、左ボタンを押しながらドラッグ四角形の外部でマウスを移動する場合、戻り値は 0 以外の値です。  
  
 場合は、ユーザーは、左ボタンを押しながらドラッグ四角形の外部でマウスを移動しなかった、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[DragDetect](http://msdn.microsoft.com/library/windows/desktop/ms646256)Windows SDK で説明されている。  
  
##  <a name="drawanimatedrects"></a>  CWnd::DrawAnimatedRects  
 アイコンを開く動作や、ウィンドウの最小化または最大化の動作を、ワイヤ フレームの四角形のアニメーションで表します。  
  
```  
BOOL DrawAnimatedRects(
    int idAni,  
    CONST RECT* lprcFrom,  
    CONST RECT* lprcTo);
```  
  
### <a name="parameters"></a>パラメーター  
 *idAni*  
 アニメーションの種類を指定します。 指定した場合**IDANI_CAPTION**、ウィンドウのキャプションの指定した位置からアニメーションが`lprcFrom`によって指定された位置に`lprcTo`です。 影響は最小限にするか、ウィンドウを最大化することに似ています。  
  
 `lprcFrom`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)アイコンまたは最小化されたウィンドウのサイズと場所を指定します。  
  
 `lprcTo`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)復元されたウィンドウのサイズと場所を指定する構造体  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[DrawAnimatedRects](http://msdn.microsoft.com/library/windows/desktop/dd162475)Windows SDK で説明されている。  
  
##  <a name="drawcaption"></a>  CWnd::DrawCaption  
 ウィンドウのキャプションを描画します。  
  
```  
BOOL DrawCaption(
    CDC* pDC,  
    LPCRECT lprc,  
    UINT uFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストへのポインター。 関数は、このデバイス コンテキストにウィンドウのキャプションを描画します。  
  
 `lprc`  
 ウィンドウのキャプションに外接する四角形を指定する RECT 構造体へのポインター。  
  
 `uFlags`  
 描画のオプションを指定します。 値の完全な一覧を参照してください。 [DrawCaption](http://msdn.microsoft.com/library/windows/desktop/dd162476)です。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[DrawCaption](http://msdn.microsoft.com/library/windows/desktop/dd162476)Windows SDK で説明されている。  
  
##  <a name="drawmenubar"></a>  かかわらず  
 メニュー バーを再描画します。  
  
```  
void DrawMenuBar();
```  
  
### <a name="remarks"></a>コメント  
 メニュー バーを Windows には、ウィンドウが作成後に変更する場合は、変更されたメニュー バーを描画するには、この関数を呼び出します。  
  
### <a name="example"></a>例  
  例を参照して[とき](#getmenu)です。  
  
##  <a name="enableactiveaccessibility"></a>  CWnd::EnableActiveAccessibility  
 ユーザー定義できるように Active Accessibility 関数。  
  
```  
void EnableActiveAccessibility();
```  
  
### <a name="remarks"></a>コメント  
 MFC の既定の Active Accessibility のサポートは、標準の windows と ActiveX コントロール; など、コントロールのための十分ですただし場合、 `CWnd`-派生クラスには、ウィンドウのないユーザー インターフェイス要素が含まれています、MFC でそれらについて知ることはありません。 その場合は、する必要がありますをオーバーライドする適切な[Active Accessibility メンバー関数](http://msdn.microsoft.com/en-us/68af04ac-4eb9-4b7d-b33f-c45512097a74)クラスでは、呼び出す必要がありますと**EnableActiveAccessibility**クラスのコンス トラクターでします。  
  
##  <a name="enabledynamiclayout"></a>  CWnd::EnableDynamicLayout  
 動的レイアウト マネージャーを有効または無効にします。 動的レイアウトが有効な場合は、ユーザーがウィンドウのサイズを変更したときに、子ウィンドウの位置とサイズを動的に調整できます。  
  
```  
void EnableDynamicLayout(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 動的レイアウトを有効にする場合は TRUE。動的レイアウトを無効にする場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 動的レイアウトを有効にする場合は、このメソッドを呼び出す以外にも必要な作業があります。 ウィンドウ内のコントロールがサイズ変更にどのように応答するかを指定する、動的レイアウト情報も提供する必要があります。 この情報は、コントロールごとに、リソース エディターで指定することも、プログラムで指定することもできます。 参照してください[動的レイアウト](../../mfc/dynamic-layout.md)です。  
  
##  <a name="enabled2dsupport"></a>  CWnd::EnableD2DSupport  
 ウィンドウの D2D のサポートを有効または無効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。  
  
```  
void EnableD2DSupport(
    BOOL bEnable = TRUE,  
    BOOL bUseDCRenderTarget = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 ウィンドウの D2D のサポートをオンにするかオフにするかを指定します。  
  
 `bUseDCRenderTarget`  
 デバイス コンテキスト (DC) レンダー ターゲット、CDCRenderTarget を使用するかどうかを指定します。 FALSE の場合、CHwndRenderTarget が使用されます。  
  
##  <a name="enablescrollbar"></a>  CWnd::EnableScrollBar  
 スクロール バーの矢印の一方または両方を有効または無効にします。  
  
```  
BOOL EnableScrollBar(
    int nSBFlags,  
    UINT nArrowFlags = ESB_ENABLE_BOTH);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSBFlags*  
 スクロール バーの種類を指定します。 次の値のいずれかを持つことができます。  
  
- **SB_BOTH**有効またはウィンドウに関連付けられた垂直および水平スクロール バーの矢印を無効にします。  
  
- **SB_HORZ**有効またはウィンドウに関連付けられている水平スクロール バーの矢印を無効にします。  
  
- **SB_VERT**有効またはウィンドウに関連付けられた垂直スクロール バーの矢印を無効にします。  
  
 `nArrowFlags`  
 どちらの矢印は、有効または無効にし、スクロール バーの矢印を有効または無効にするかどうかを指定します。 次の値のいずれかを持つことができます。  
  
- **ESB_ENABLE_BOTH**スクロールの両方の矢印を有効にします (既定値)。  
  
- **ESB_DISABLE_LTUP**水平スクロール バーの左側の矢印または上向きの矢印の垂直スクロール バーを無効にします。  
  
- **ESB_DISABLE_RTDN**水平スクロール バーの右矢印または下向きの矢印の垂直スクロール バーを無効にします。  
  
- **ESB_DISABLE_BOTH**スクロール バーの両方の矢印を無効にします。  
  
### <a name="return-value"></a>戻り値  
 矢印が有効にまたは指定された無効になっている場合は 0 以外。 します。 それ以外の場合は 0 で、矢印が既に要求された状態であるか、エラーが発生したことを示します。  
  
##  <a name="enablescrollbarctrl"></a>  CWnd::EnableScrollBarCtrl  
 有効またはこのウィンドウのスクロール バーを無効にします。  
  
```  
void EnableScrollBarCtrl(
    int nBar,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 スクロール バーの識別子です。  
  
 `bEnable`  
 スクロール バーを有効または無効になっているかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 兄弟スクロール バー コントロールをウィンドウに存在する場合は、スクロール バーが使用されます。それ以外の場合、ウィンドウのスクロール バーが使用されます。  
  
##  <a name="enabletooltips"></a>  CWnd::EnableToolTips  
 指定されたウィンドウのツール ヒントを有効にします。  
  
```  
BOOL EnableToolTips(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 ツール ヒント コントロールが有効または無効になっているかどうかを指定します。 **TRUE**コントロールです。**FALSE**コントロールを無効にします。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ツール ヒントは、それ以外の有効な場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 オーバーライド[OnToolHitTest](#ontoolhittest)を提供する、 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)構造体またはウィンドウの構造体。  
  
> [!NOTE]
>  いくつかのウィンドウなど[CToolBar](../../mfc/reference/ctoolbar-class.md)、組み込みの実装を提供[OnToolHitTest](#ontoolhittest)です。  
  
 参照してください[TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)詳細についてはこの構造上の Windows SDK に含まれています。  
  
 呼び出す`EnableToolTips`、子コントロールは、親ウィンドウに由来しない限り、ツール ヒントを表示するには不十分`CFrameWnd`です。 これは、ため`CFrameWnd`の既定のハンドラーを提供、 **TTN_NEEDTEXT**通知します。 親ウィンドウがから派生していない場合`CFrameWnd`は、ダイアログまたはフォーム ビューの場合は、ツール ヒントのハンドラーを提供しない限り、コントロールが正しく表示されませんが、子、 **TTN_NEEDTEXT**ツール ヒントの通知です。 参照してください[ツールチップ](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)です。  
  
 によって、windows の既定ツール ヒント`EnableToolTips`それらに関連付けられたテキストはありません。 テキストを表示するツールヒントを取得する、 **TTN_NEEDTEXT**ツール ヒントのウィンドウが表示される直前に、ツール ヒント コントロールの親ウィンドウに通知が送信されます。 いくつかの値を割り当てるには、このメッセージのハンドラーがないかどうか、`pszText`のメンバー、 **TOOLTIPTEXT**構造体にはないツール ヒントに表示されるテキストです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#91](../../mfc/reference/codesnippet/cpp/cwnd-class_30.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#92](../../mfc/reference/codesnippet/cpp/cwnd-class_31.cpp)]  
  
##  <a name="enabletrackingtooltips"></a>  CWnd::EnableTrackingToolTips  
 有効または無効のツールヒントを追跡します。  
  
```  
BOOL EnableTrackingToolTips(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 指定トラッキング ツール ヒントを有効または無効になっているかどうか。 このパラメーターは場合**TRUE**、追跡ツール ヒントが有効になります。 このパラメーターが場合**FALSE**、追跡ツール ヒントが無効になります。  
  
### <a name="return-value"></a>戻り値  
 前に、の状態を示す、`EnableWindow`メンバー関数が呼び出されました。 戻り値は、ウィンドウが無効だった場合は 0 以外です。 ウィンドウが以前に有効にまたはエラーが発生した場合、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 追跡ツール ヒントは、画面に配置できる動的にツール ヒント ウィンドウです。 滑らかに、移動、または"track"位置を迅速に更新するには、ツール ヒントのウィンドウが表示されます。 この機能は、ツールヒントのテキスト ポインターの位置に移動するときに従う必要がある場合に便利です。  
  
##  <a name="enablewindow"></a>  CWnd::EnableWindow  
 マウス入力およびキーボード入力を有効または無効にします。  
  
```  
BOOL EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 指定されたウィンドウを有効または無効になっているかどうかを指定します。 このパラメーターは場合**TRUE**ウィンドウが有効になります。 このパラメーターが場合**FALSE**ウィンドウは無効になります。  
  
### <a name="return-value"></a>戻り値  
 前に、の状態を示す、`EnableWindow`メンバー関数が呼び出されました。 戻り値は、ウィンドウが無効だった場合は 0 以外です。 ウィンドウが以前に有効にまたはエラーが発生した場合、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 入力が無効にした場合など、マウスのクリックしてやキー操作は無視されますを入力します。 入力が有効になっているときに、ウィンドウは、すべての入力を処理します。  
  
 有効な状態を変更する場合、 [WM_ENABLE](#onenable)この関数が返す前にメッセージを送信します。  
  
 無効な場合、すべての子ウィンドウが暗黙的に無効なが送信されませんが`WM_ENABLE`メッセージ。  
  
 アクティブにする前に、ウィンドウを有効にする必要があります。 たとえば場合は、アプリケーションでは、モードレス ダイアログ ボックスが表示されると、メイン ウィンドウを無効になっていますが、メイン ウィンドウ必要があります有効にする ダイアログ ボックスが破棄される前にします。 それ以外の場合、別のウィンドウが入力フォーカスを取得し、アクティブ化します。 子ウィンドウが無効になっている場合は、Windows をどのウィンドウは、マウスのメッセージを取得する必要がありますを決定しようとすると、無視されます。  
  
 既定では、ウィンドウが作成されるときに有効にします。 アプリケーションを指定できます、 **WS_DISABLED**のスタイルを設定、[作成](#create)または[CreateEx](#createex)メンバー関数を最初に無効になっているウィンドウを作成します。 アプリケーションで使用できますも、ウィンドウが作成された後、`EnableWindow`メンバー関数を有効にするにまたはウィンドウを無効にします。  
  
 アプリケーションでは、有効または無効 ダイアログ ボックス内のコントロールに、この関数を使用できます。 無効なコントロールは、入力フォーカスを受け取ることはできません。 また、ユーザー、アクセスできます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#93](../../mfc/reference/codesnippet/cpp/cwnd-class_32.cpp)]  
  
##  <a name="endmodalloop"></a>  CWnd::EndModalLoop  
 呼び出しを終了する`RunModalLoop`です。  
  
```  
virtual void EndModalLoop(int nResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `nResult`  
 呼び出し元に返される値が含まれる[RunModalLoop](#runmodalloop)です。  
  
### <a name="remarks"></a>コメント  
 `nResult`からの戻り値にパラメーターが反映される`RunModalLoop`です。  
  
##  <a name="endmodalstate"></a>  CWnd::EndModalState  
 フレーム ウィンドウをモーダルからモードレスに変更します。  
  
```  
virtual void EndModalState();
```  
  
##  <a name="endpaint"></a>  CWnd::EndPaint  
 指定されたウィンドウでペイントの末尾をマークします。  
  
```  
void EndPaint(LPPAINTSTRUCT lpPaint);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPaint`  
 指す、 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)によって取得された描画情報を格納する構造体、 [BeginPaint](#beginpaint)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 `EndPaint`メンバー関数は呼び出しごとに必要な`BeginPaint`ペイントの完了後にのみ、メンバー関数。  
  
 によってカーソルが非表示の場合、`BeginPaint`メンバー関数は、`EndPaint`画面にキャレットを復元します。  
  
### <a name="example"></a>例  
  例を参照して[cwnd::beginpaint](#beginpaint)です。  
  
##  <a name="executedlginit"></a>  CWnd::ExecuteDlgInit  
 ダイアログ リソースを開始します。  
  
```  
BOOL ExecuteDlgInit(LPCTSTR lpszResourceName);  
BOOL ExecuteDlgInit(LPVOID lpResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 リソースの名前を指定する null で終わる文字列へのポインター。  
  
 `lpResource`  
 リソースへのポインター。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ダイアログ リソースが実行されるそれ以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 `ExecuteDlgInit` その他のソースからは、実行中のモジュールにバインドされているリソースやリソースを使用します。 このため、`ExecuteDlgInit`リソース ハンドルを呼び出すことによって検索`AfxFindResourceHandle`です。 MFC アプリケーションが共有 DLL を使わないかどうか (MFCx0 [U] [D] です。DLL)、 **AfxFindResourceHandle**呼び出し[AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle)、実行可能ファイルの現在のリソース ハンドルが返されます。 場合 MFCx0 を使用する MFC アプリケーション [U] [D] です。DLL、`AfxFindResourceHandle`を通過する時間、 **CDynLinkLibrary**のオブジェクトの一覧は、共有および MFC 拡張 Dll は、適切なリソースの検索を処理します。  
  
##  <a name="filtertooltipmessage"></a>  CWnd::FilterToolTipMessage  
 ツール ヒントのメッセージを表示するためにフレームワークによって呼び出されます。  
  
```  
void FilterToolTipMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 ツール ヒント メッセージへのポインター。  
  
### <a name="remarks"></a>コメント  
 ほとんどの MFC アプリケーションでこのメソッドは、framework から[PreTranslateMessage](#pretranslatemessage)と[EnableToolTips](#enabletooltips)、し、それを呼び出す必要はありません。  
  
 ただし、一部の ActiveX コントロールなど、特定のアプリケーションでこれらのメソッドは、フレームワークによって呼び出さいない可能性があるし、を FilterToolTipMessage を呼び出す必要があります。 詳細については、次を参照してください。[を作成するツール ヒントのメソッド](../../mfc/methods-of-creating-tool-tips.md)です。  
  
##  <a name="findwindow"></a>  :Findwindow  
 最上位を返します`CWnd`でウィンドウ クラスを指定した`lpszClassName`がウィンドウの名前、または タイトル別であると`lpszWindowName`です。  
  
```  
static CWnd* PASCAL FindWindow(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 ウィンドウのクラス名を指定する null で終わる文字列へのポインター (、 **WNDCLASS**構造体)。 場合`lpClassName`は**NULL**、すべてのクラス名が一致します。  
  
 `lpszWindowName`  
 ウィンドウの名前 (ウィンドウのタイトル) を指定する null で終わる文字列へのポインター。 場合`lpWindowName`は**NULL**、すべてのウィンドウ名と一致します。  
  
### <a name="return-value"></a>戻り値  
 指定されたクラス名とウィンドウの名前を持つウィンドウを識別します。 **NULL**そのようなウィンドウが見つからない場合。  
  
 `CWnd`*、一時的なと、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 この関数は、子ウィンドウを検索しません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#94](../../mfc/reference/codesnippet/cpp/cwnd-class_33.cpp)]  
  
##  <a name="findwindowex"></a>  CWnd::FindWindowEx  
 クラス名とウィンドウの名前は、指定した文字列を一致させます。 ウィンドウ オブジェクトを取得します。  
  
```  
static CWnd* FindWindowEx(
    HWND hwndParent,  
    HWND hwndChildAfter,  
    LPCTSTR lpszClass,  
    LPCTSTR lpszWindow);
```  
  
### <a name="parameters"></a>パラメーター  
 *hwndParent*  
 子ウィンドウを持つが検索するのには、親ウィンドウへのハンドルします。  
  
 *hwndChildAfter*  
 子ウィンドウへのハンドルします。 Z オーダーの次の子ウィンドウの検索を開始します。 子ウィンドウの直接の子ウィンドウをする必要があります*hwndParent*、だけでなく子孫ウィンドウです。  
  
 `lpszClass`  
 クラス名または前回の呼び出しによって作成されたクラス atom を指定する null で終わる文字列へのポインター、 [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586)または[RegisterClassEx](http://msdn.microsoft.com/library/windows/desktop/ms633587)です。  
  
 *lpszWindow*  
 ウィンドウの名前 (ウィンドウのタイトル) を指定する null で終わる文字列へのポインター。 このパラメーターは場合**NULL**、すべてのウィンドウ名と一致します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は、指定したクラスとウィンドウ名を持つウィンドウ オブジェクトへのポインターにです。 戻り値は、関数が失敗した場合、 **NULL**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[FindWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms633500)Windows SDK で説明されている。  
  
##  <a name="flashwindow"></a>  CWnd::FlashWindow  
 指定されたウィンドウを 2 回点滅します。  
  
```  
BOOL FlashWindow(BOOL bInvert);
```  
  
### <a name="parameters"></a>パラメーター  
 `bInvert`  
 指定するかどうか、`CWnd`フラッシュするか、元の状態が返されます。 `CWnd`他の場合は、1 つの状態からアップデートは`bInvert`は**TRUE**です。 場合`bInvert`は**FALSE**、(アクティブまたは非アクティブ)、ウィンドウが元の状態に返されます。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが呼び出しの前にアクティブであった場合は 0 以外、`FlashWindow`メンバー関数以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 後続の点滅システム タイマーを作成し、繰り返し呼び出し`FlashWindow`です。 点滅、 `CWnd` 、タイトル バーの外観を変更することを意味として、`CWnd`が非アクティブ状態、またはその逆に変更します。 (非アクティブなタイトル バーを変更、アクティブなタイトル バー以外のアクティブなタイトル バーを非アクティブなタイトル バーに変更します。)  
  
 通常、注意が必要とすることが入力フォーカスが現在持っていないユーザーに通知するウィンドウをフラッシュします。  
  
 `bInvert`パラメーターでなければなりません**FALSE**ありますだけで、ウィンドウが入力フォーカスを取得してされなくなりますが点滅; **TRUE**入力フォーカスを取得するまでの間の連続呼び出しで。  
  
 この関数は、常に最小化されている windows の場合は 0 以外を返します。 ウィンドウを最小化されている場合`FlashWindow`ウィンドウのアイコンが点滅するだけ`bInvert`最小化ウィンドウは無視されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#95](../../mfc/reference/codesnippet/cpp/cwnd-class_34.cpp)]  
  
##  <a name="flashwindowex"></a>  CWnd::FlashWindowEx  
 指定されたウィンドウをフラッシュします。  
  
```  
BOOL FlashWindowEx(
    DWORD dwFlags,  
    UINT uCount,  
    DWORD dwTimeout);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 フラッシュのステータスを指定します。 値の完全な一覧については、[は](http://msdn.microsoft.com/library/windows/desktop/ms679348)構造体。  
  
 `uCount`  
 ウィンドウをフラッシュする回数を指定します。  
  
 `dwTimeout`  
 (ミリ秒単位) ウィンドウをフラッシュするレートを指定します。 場合`dwTimeout`0 の場合は、関数は既定のカーソルの点滅速度を使用します。  
  
### <a name="return-value"></a>戻り値  
 戻り値を指定する呼び出しの前に、ウィンドウの状態、`FlashWindowEx`関数。 呼び出しの前にアクティブなウィンドウのキャプションが描画されると場合、戻り値は 0 以外の値です。 それ以外の場合、戻り値は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、関数の機能をエミュレート[FlashWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms679347)Windows SDK で説明されている。  
  
##  <a name="fromhandle"></a>  CWnd::FromHandle  
 ウィンドウのハンドルが指定されている場合、`CWnd` オブジェクトへのポインターを返します。 `CWnd` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CWnd` オブジェクトが生成され、関連付けられます。  
  
```  
static CWnd* PASCAL FromHandle(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 `HWND` Windows のウィンドウ。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウのハンドルが指定されている場合、`CWnd` オブジェクトへのポインターを返します。 `CWnd` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CWnd` オブジェクトが生成され、関連付けられます。  
  
 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
##  <a name="fromhandlepermanent"></a>  CWnd::FromHandlePermanent  
 ウィンドウのハンドルが指定されている場合、`CWnd` オブジェクトへのポインターを返します。  
  
```  
static CWnd* PASCAL FromHandlePermanent(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 `HWND` Windows のウィンドウ。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CWnd`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 場合、`CWnd`オブジェクトがハンドルに関連付けられていない**NULL**が返されます。  
  
 この関数とは異なり、 [FromHandle](#fromhandle)、一時オブジェクトを作成しません。  
  
##  <a name="get_accchild"></a>  CWnd::get_accChild  
 指定された子の `IDispatch` インターフェイスのアドレスを取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accChild(
    VARIANT varChild,  
    IDispatch** ppdispChild);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 子識別が`IDispatch`インターフェイスを取得します。  
  
 *ppdispChild*  
 子オブジェクトのアドレスを受け取る`IDispatch`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::get_accChild](http://msdn.microsoft.com/library/windows/desktop/dd318475) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 [IAccessible::get_accChild](http://msdn.microsoft.com/library/windows/desktop/dd318475) Windows SDK に含まれています。  
  
##  <a name="get_accchildcount"></a>  CWnd::get_accChildCount  
 このオブジェクトに属する子の数を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accChildCount(long* pcountChildren);
```  
  
### <a name="parameters"></a>パラメーター  
 *pcountChildren*  
 子の数を受け取ります。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::get_accChildCount](http://msdn.microsoft.com/library/windows/desktop/dd318476) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。 基底クラスのバージョンを呼び出し、ウィンドウのない子要素を追加します。  
  
 詳細については、次を参照してください。 [IAccessible::get_accChildCount](http://msdn.microsoft.com/library/windows/desktop/dd318476) Windows SDK に含まれています。  
  
##  <a name="get_accdefaultaction"></a>  CWnd::get_accDefaultAction  
 オブジェクトの既定のアクションを記述する文字列を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accDefaultAction(
    VARIANT varChild,  
    BSTR* pszDefaultAction);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 既定のアクションを取得するが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトに関する情報を取得) するか、(情報を取得するオブジェクトの子要素) の子の ID を指定できます。  
  
 *pszDefaultAction*  
 アドレス、`BSTR`このオブジェクトには、既定のアクションがあるない場合、指定したオブジェクトまたは NULL の既定のアクションを説明するローカライズされた文字列を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::get_accDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318477) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-オブジェクトの既定のアクションを記述するクラスを派生します。  
  
 詳細については、次を参照してください。 [IAccessible::get_accDefaultAction](http://msdn.microsoft.com/library/windows/desktop/dd318477) Windows SDK に含まれています。  
  
##  <a name="get_accdescription"></a>  CWnd::get_accDescription  
 指定されたオブジェクトの外観を記述する文字列を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accDescription(
    VARIANT varChild,  
    BSTR* pszDescription);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 説明を取得するが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトに関する情報を取得) するか、(情報を取得するオブジェクトの子要素) の子の ID を指定できます。  
  
 `pszDescription`  
 アドレス、`BSTR`を受け取る、ローカライズされた文字列の指定したオブジェクトを記述する、またはこのオブジェクトの使用可能な説明が存在しない場合は NULL です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::get_accDescription](http://msdn.microsoft.com/library/windows/desktop/dd318478) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-、オブジェクトを記述するクラスを派生します。 基底クラスのバージョンを呼び出すし、説明を追加します。  
  
 詳細については、次を参照してください。 [IAccessible::get_accDescription](http://msdn.microsoft.com/library/windows/desktop/dd318478) Windows SDK に含まれています。  
  
##  <a name="get_accfocus"></a>  CWnd::get_accFocus  
 キーボード フォーカスを保持するオブジェクトを取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accFocus(VARIANT* pvarChild);
```  
  
### <a name="parameters"></a>パラメーター  
 `pvarChild`  
 フォーカスのあるオブジェクトに関する情報を受け取ります。 参照してください*pvarID*で[IAccessible::get_accFocus](http://msdn.microsoft.com/library/windows/desktop/dd318479) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で**IAccessible::get_accFocus** Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 [IAccessible::get_accFocus](http://msdn.microsoft.com/library/windows/desktop/dd318479) Windows SDK に含まれています。  
  
##  <a name="get_acchelp"></a>  CWnd::get_accHelp  
 オブジェクトの取得するためにフレームワークによって呼び出されます**ヘルプ**プロパティの文字列。  
  
```  
virtual HRESULT get_accHelp(
    VARIANT varChild,  
    BSTR* pszHelp);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 このヘルプ情報を取得するが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトに関する情報を取得) するか、(情報を取得するオブジェクトの子要素) の子の ID を指定できます。  
  
 *pszHelp*  
 アドレス、`BSTR`ヘルプ情報が使用できない場合に、指定したオブジェクトまたは NULL のヘルプ情報を格納しているローカライズされた文字列を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::get_accHelp](http://msdn.microsoft.com/library/windows/desktop/dd318480) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-オブジェクトのヘルプ テキストを提供するクラスを派生します。  
  
 詳細については、次を参照してください。 [IAccessible::get_accHelp](http://msdn.microsoft.com/library/windows/desktop/dd318480) Windows SDK に含まれています。  
  
##  <a name="get_acchelptopic"></a>  CWnd::get_accHelpTopic  
 完全なパスを取得するためにフレームワークによって呼び出される、 **WinHelp**指定したオブジェクトとそのファイル内の適切なトピックの識別子に関連付けられているファイル。  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszHelpFile`  
 アドレス、`BSTR`の完全なパスを受け取る、`WinHelp`存在する場合は、指定したオブジェクトに関連付けられているファイル。  
  
 `varChild`  
 取得するヘルプ トピックが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトのヘルプ トピックを取得) するか、(オブジェクトの子のいずれかの要素に対応するヘルプ トピックを取得) する子の ID を指定できます。  
  
 `pidTopic`  
 指定したオブジェクトに関連付けられているヘルプ ファイルを識別します。 参照してください`pidTopic`で[IAccessible::get_accHelpTopic](http://msdn.microsoft.com/library/windows/desktop/dd318481) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で**IAccessible::get_accHelpTopic** Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-オブジェクトに関するヘルプ情報を提供するクラスを派生します。  
  
 詳細については、次を参照してください。 [IAccessible::get_accHelpTopic](http://msdn.microsoft.com/library/windows/desktop/dd318481) Windows SDK に含まれています。  
  
##  <a name="get_acckeyboardshortcut"></a>  CWnd::get_accKeyboardShortcut  
 指定されたオブジェクトのショートカット キーまたはアクセス キーを取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accKeyboardShortcut(
    VARIANT varChild,  
    BSTR* pszKeyboardShortcut);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 取得するためのキーボード ショートカットが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトに関する情報を取得) するか、(情報を取得するオブジェクトの子要素) の子の ID を指定できます。  
  
 *pszKeyboardShortcut*  
 アドレス、`BSTR`を受け取る、ローカライズされたキーボード ショートカットを識別する文字列または指定したオブジェクトに関連付けられているショートカット キーがない場合は NULL です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::get_accKeyboardShortcut](http://msdn.microsoft.com/library/windows/desktop/dd318482) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-オブジェクトのキーボード ショートカットを識別するクラスを派生します。  
  
 詳細については、次を参照してください。 [IAccessible::get_accKeyboardShortcut](http://msdn.microsoft.com/library/windows/desktop/dd318482) Windows SDK に含まれています。  
  
##  <a name="get_accname"></a>  CWnd::get_accName  
 指定されたオブジェクトの名前を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accName(
    VARIANT varChild,  
    BSTR* pszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 名前を取得するが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトに関する情報を取得) するか、(情報を取得するオブジェクトの子要素) の子の ID を指定できます。  
  
 `pszName`  
 アドレス、`BSTR`指定されたオブジェクトの名前を表す文字列を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::get_accName](http://msdn.microsoft.com/library/windows/desktop/dd318483) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライド、 `CWnd`-派生クラス オブジェクトの名前を返します。  
  
 詳細については、次を参照してください。 [IAccessible::get_accName](http://msdn.microsoft.com/library/windows/desktop/dd318483) Windows SDK に含まれています。  
  
##  <a name="get_accparent"></a>  CWnd::get_accParent  
 オブジェクトの親の `IDispatch` インターフェイスを取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accParent(IDispatch** ppdispParent);
```  
  
### <a name="parameters"></a>パラメーター  
 *ppdispParent*  
 親オブジェクトのアドレスを受け取る`IDispatch`インターフェイスです。 親が存在しない場合、または、子はその親にアクセスできない場合、変数は NULL に設定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::get_accParent](http://msdn.microsoft.com/library/windows/desktop/dd318484) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 ほとんどの場合この関数をオーバーライドする必要はありません。  
  
 詳細については、次を参照してください。 [IAccessible::get_accParent](http://msdn.microsoft.com/library/windows/desktop/dd318484) Windows SDK に含まれています。  
  
##  <a name="get_accrole"></a>  CWnd::get_accRole  
 指定されたオブジェクトの役割を記述する情報を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accRole(
    VARIANT varChild,  
    VARIANT* pvarRole);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 ロール情報を取得するが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトに関する情報を取得) するか、(情報を取得するオブジェクトの子要素) の子の ID を指定できます。  
  
 `pvarRole`  
 ロール情報を受け取ります。 参照してください`pvarRole`で[IAccessible::get_accRole](http://msdn.microsoft.com/library/windows/desktop/dd318485) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で**IAccessible::get_accRole** Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 [IAccessible::get_accRole](http://msdn.microsoft.com/library/windows/desktop/dd318485) Windows SDK に含まれています。  
  
##  <a name="get_accselection"></a>  CWnd::get_accSelection  
 このオブジェクトの選択されている子を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>パラメーター  
 `pvarChildren`  
 選択されている子に関する情報を受け取ります。 参照してください`pvarChildren`で[IAccessible::get_accSelection](http://msdn.microsoft.com/library/windows/desktop/dd318486) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で**IAccessible::get_accSelection** Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 [IAccessible::get_accSelection](http://msdn.microsoft.com/library/windows/desktop/dd318486) Windows SDK に含まれています。  
  
##  <a name="get_accstate"></a>  CWnd::get_accState  
 指定されたオブジェクトの現在の状態を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accState(
    VARIANT varChild,  
    VARIANT* pvarState);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 状態情報を取得するが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトに関する情報を取得) するか、(情報を取得するオブジェクトの子要素) の子の ID を指定できます。  
  
 `pvarState`  
 オブジェクトの状態に関する情報を受け取ります。 参照してください`pvarState`で[IAccessible::get_accState](http://msdn.microsoft.com/library/windows/desktop/dd318487) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で**IAccessible::get_accState** Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 [IAccessible::get_accState](http://msdn.microsoft.com/library/windows/desktop/dd318487) Windows SDK に含まれています。  
  
##  <a name="get_accvalue"></a>  CWnd::get_accValue  
 指定されたオブジェクトの値を取得するために、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT get_accValue(
    VARIANT varChild,  
    BSTR* pszValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `varChild`  
 値の情報を取得するが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、CHILDID_SELF (オブジェクトに関する情報を取得) するか、(情報を取得するオブジェクトの子要素) の子の ID を指定できます。  
  
 `pszValue`  
 アドレス、`BSTR`オブジェクトの現在の値を格納しているローカライズされた文字列を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、失敗した場合、COM エラー コードは、S_OK を返します。 参照してください**値を返す**で[IAccessible::get_accValue](http://msdn.microsoft.com/library/windows/desktop/dd318488) Windows SDK にします。  
  
### <a name="remarks"></a>コメント  
 この関数は MFC の一部[Active Accessibility](http://msdn.microsoft.com/library/windows/desktop/dd373592)をサポートします。  
  
 この関数をオーバーライドして`CWnd`-(ウィンドウなし ActiveX コントロール、MFC によって処理される) 以外のウィンドウのないユーザー インターフェイス要素があれば、派生クラス。  
  
 詳細については、次を参照してください。 [IAccessible::get_accValue](http://msdn.microsoft.com/library/windows/desktop/dd318488) Windows SDK に含まれています。  
  
##  <a name="getactivewindow"></a>  CWnd::GetActiveWindow  
 アクティブなウィンドウへのポインターを取得します。  
  
```  
static CWnd* PASCAL GetActiveWindow();
```  
  
### <a name="return-value"></a>戻り値  
 作業中のウィンドウまたは**NULL**呼び出し時にアクティブなウィンドウがない場合。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 アクティブなウィンドウが現在入力フォーカスのあるウィンドウまたは明示的に加え、アクティブで、ウィンドウ、 [SetActiveWindow](#setactivewindow)メンバー関数。  
  
##  <a name="getancestor"></a>  CWnd::GetAncestor  
 指定したウィンドウの祖先ウィンドウ オブジェクトを取得します。  
  
```  
CWnd* GetAncestor(UINT gaFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *gaFlags*  
 取得する先祖を指定します。 使用可能な値の完全な一覧は、次を参照してください。 [GetAncestor](http://msdn.microsoft.com/library/windows/desktop/ms633502)です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、戻り値は、祖先ウィンドウ オブジェクトへのポインターです。 戻り値は、関数が失敗した場合、 **NULL**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetAncestor](http://msdn.microsoft.com/library/windows/desktop/ms633502)Windows SDK で説明されている。  
  
##  <a name="getcapture"></a>  CWnd::GetCapture  
 マウス キャプチャを持つウィンドウを取得します。  
  
```  
static CWnd* PASCAL GetCapture();
```  
  
### <a name="return-value"></a>戻り値  
 マウス キャプチャを持つウィンドウを識別します。 **NULL**ウィンドウでマウスのキャプチャされていない場合。  
  
 戻り値は、一時的なされ、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 1 つだけのウィンドウには、特定の時点でキャプチャする、マウスがあります。 ウィンドウは、マウスを受け取るときにキャプチャ、 [SetCapture](#setcapture)メンバー関数が呼び出されます。 このウィンドウは、カーソルが境界内にあるかどうかを示す、マウス入力を受け取ります。  
  
##  <a name="getcaretpos"></a>  CWnd::GetCaretPos  
 キャレットの現在位置を示すクライアント座標を取得し、そのまま返します、`CPoint`です。  
  
```  
static CPoint PASCAL GetCaretPos();
```  
  
### <a name="return-value"></a>戻り値  
 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)のカーソルの位置座標を持つオブジェクト。  
  
### <a name="remarks"></a>コメント  
 クライアント座標で、カーソル位置が指定された、`CWnd`ウィンドウです。  
  
##  <a name="getcheckedradiobutton"></a>  CWnd::GetCheckedRadioButton  
 指定されたグループ内の現在チェックされているオプション ボタンの ID を取得します。  
  
```  
int GetCheckedRadioButton(
    int nIDFirstButton,  
    int nIDLastButton);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFirstButton`  
 グループ内の最初のラジオ ボタンの整数識別子を指定します。  
  
 `nIDLastButton`  
 グループ内の最後のラジオ ボタンの整数識別子を指定します。  
  
### <a name="return-value"></a>戻り値  
 チェックされているオプション ボタンまたは [なし] が選択されている場合は 0 の ID。  
  
##  <a name="getclientrect"></a>  CWnd::GetClientRect  
 クライアント座標をコピー、`CWnd`構造へのクライアント領域を指す`lpRect`です。  
  
```  
void GetClientRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT 構造体](../../mfc/reference/rect-structure1.md)または`CRect`をクライアント座標を取得するオブジェクト。 **左**と**上部**メンバーは 0 になります。 **右**と**下部**メンバーには、ウィンドウの高さと幅が含まれます。  
  
### <a name="remarks"></a>コメント  
 クライアント座標では、クライアント領域の左上隅および右下隅を指定します。 クライアント座標の左上隅を基準としたため、`CWnd`クライアント領域で、左上隅の座標が (0, 0) です。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::IsIconic](#isiconic)です。  
  
##  <a name="getclipboardowner"></a>  CWnd::GetClipboardOwner  
 クリップボードの現在の所有者を取得します。  
  
```  
static CWnd* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合に、クリップボードを所有しているウィンドウを識別します。 以外の場合は**NULL**です。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 クリップボードが現在所有していない場合でもデータがも含めることができます。  
  
##  <a name="getclipboardviewer"></a>  CWnd::GetClipboardViewer  
 クリップボード ビューアーのチェインの最初のウィンドウを取得します。  
  
```  
static CWnd* PASCAL GetClipboardViewer();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合に、クリップボードの表示を担当する現在のウィンドウを識別します。それ以外の場合**NULL** (たとえば、ビューアーが存在しない) 場合。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
##  <a name="getcontrolunknown"></a>  CWnd::GetControlUnknown  
 不明な OLE コントロールへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
LPUNKNOWN GetControlUnknown();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)これによって表される OLE コントロールのインターフェイス`CWnd`オブジェクト。 戻り値は、このオブジェクトが OLE コントロールを表していない場合は**NULL**です。  
  
### <a name="remarks"></a>コメント  
 これを解放する必要がありますいない**IUnknown**ポインター。 通常、コントロールの特定のインターフェイスを取得するを使用します。  
  
 によって返されたインターフェイス ポインター **GetControlUnknown**参照カウントがありません。 呼び出す必要はありません[iunknown::release](http://msdn.microsoft.com/library/windows/desktop/ms682317)ポインターを以前と呼ばれていない限り[:addref](http://msdn.microsoft.com/library/windows/desktop/ms691379)にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#96](../../mfc/reference/codesnippet/cpp/cwnd-class_35.cpp)]  
  
##  <a name="getcurrentmessage"></a>  CWnd::GetCurrentMessage  
 ウィンドウが現在処理しているメッセージへのポインターを返します。 必要がある場合にのみ呼び出す、**で * * * メッセージ*メッセージ ハンドラー メンバー関数。  
  
```  
static const MSG* PASCAL GetCurrentMessage();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返します、 [MSG](../../mfc/reference/msg-structure1.md)ウィンドウ メッセージを格納する構造体は、現在処理中です。 必要がある場合にのみ呼び出す、**で * * * メッセージ*ハンドラー。  
  
### <a name="example"></a>例  
  例を参照して[CMDIFrameWnd::MDICascade](../../mfc/reference/cmdiframewnd-class.md#mdicascade)です。  
  
##  <a name="getdc"></a>  CWnd::GetDC  
 一般的に使われるへのポインター、クラス、または指定されたクラス スタイルに応じたクライアント領域のプライベート デバイス コンテキストを取得、`CWnd`です。  
  
```  
CDC* GetDC();
```  
  
### <a name="return-value"></a>戻り値  
 デバイス コンテキストを識別、`CWnd`クライアント領域かどうか成功しなかった場合、戻り値は、 **NULL**です。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 共通のデバイス コンテキスト`GetDC`が取得されるたびに、コンテキストに既定の属性を割り当てます。 クラスとプライベートのコンテキストの`GetDC`変更せず、以前に割り当てられた属性のままにします。 デバイス コンテキストは、クライアント領域に描画する後続のグラフィック デバイス インターフェイス (GDI) の機能で使用できます。  
  
 デバイス コンテキストは、ウィンドウ クラスに属していない限り、 [ReleaseDC](#releasedc)描画後に、コンテキストを解放するメンバー関数を呼び出す必要があります。  
  
 デバイス コンテキストに属している、`CWnd`クラスは、によって返される、`GetDC`メンバー関数の場合は**CS_CLASSDC**、 **CS_OWNDC**、または**CS_PARENTDC**されましたスタイルで指定された、 **WNDCLASS**クラスが登録されたときにします。  
  
##  <a name="getdcex"></a>  CWnd::GetDCEx  
 デバイス コンテキストのハンドルを取得、`CWnd`ウィンドウです。  
  
```  
CDC* GetDCEx(
    CRgn* prgnClip,  
    DWORD flags);
```  
  
### <a name="parameters"></a>パラメーター  
 `prgnClip`  
 クライアント ウィンドウの表示領域と組み合わせることをクリッピング領域を識別します。  
  
 `flags`  
 既定値は次のいずれかを持つことができます。  
  
- **DCX_CACHE**キャッシュからデバイス コンテキストを返しますではなく、 **OWNDC**または**CLASSDC**ウィンドウです。 オーバーライド**CS_OWNDC**と**CS_CLASSDC**です。  
  
- **DCX_CLIPCHILDREN**下のすべての子ウィンドウの可視領域を除外、`CWnd`ウィンドウです。  
  
- **DCX_CLIPSIBLINGS**のすべての兄弟ウィンドウ上の可視領域を除外、`CWnd`ウィンドウです。  
  
- **DCX_EXCLUDERGN**で識別されるクリッピング領域を除外`prgnClip`返されるデバイス コンテキストの可視領域から。  
  
- **DCX_INTERSECTRGN**で識別されるクリッピング領域と交差する`prgnClip`返されるデバイス コンテキストの可視領域内で。  
  
- **DCX_LOCKWINDOWUPDATE**がある場合でも描画を許可、`LockWindowUpdate`このウィンドウを除外するそれ以外の場合は効果で呼び出します。 この値は、追跡の間の描画に使用されます。  
  
- **DCX_PARENTCLIP**親ウィンドウの表示領域を使用し、親ウィンドウを無視**WS_CLIPCHILDREN**と**WS_PARENTDC**ビットのスタイルを設定します。 この値に設定デバイス コンテキストの原点の左上隅に、`CWnd`ウィンドウです。  
  
- **DCX_WINDOW**クライアントの四角形ではなく、ウィンドウの四角形に対応するデバイス コンテキストを返します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、指定されたウィンドウのデバイス コンテキストそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストは、クライアント領域に描画する後続の GDI 関数で使用できます。  
  
 この関数は、拡張機能を[GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)関数では、ウィンドウのデバイス コンテキストがクリップされるかどうかおよびどのようにより詳細に制御をアプリケーションに提供します。  
  
 デバイス コンテキストは、ウィンドウ クラスに属していない限り、 [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920)描画後に、コンテキストを解放する関数を呼び出す必要があります。 5 つの一般的なデバイス コンテキストが、特定の時点で利用可能なためには、デバイス コンテキストを解放の失敗は、デバイス コンテキストへのアクセスを防ぐには、他のアプリケーションを防ぐことができます。  
  
 キャッシュされたデバイス コンテキストを取得するには、アプリケーションを指定する必要があります[DCX_CACHE](http://msdn.microsoft.com/library/windows/desktop/dd144873)です。 場合**DCX_CACHE**が指定されていないと、ウィンドウがどちらも**CS_OWNDC**も[CS_CLASSDC](http://msdn.microsoft.com/library/windows/desktop/ms633576)、この関数を返します**NULL**です。  
  
 特別な特性を持つデバイス コンテキストがによって返される、 [GetDCEx](http://msdn.microsoft.com/library/windows/desktop/dd144873)関数の場合、 **CS_CLASSDC**、 [CS_OWNDC](http://msdn.microsoft.com/library/windows/desktop/ms633576)、または[CS_PARENTDC](http://msdn.microsoft.com/library/windows/desktop/ms633576)スタイルがで指定された、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)クラスが登録されたときにします。  
  
 これらの特性の詳細については、の説明を参照して、 **WNDCLASS** Windows SDK 内の構造。  
  
##  <a name="getdcrendertarget"></a>  CWnd::GetDCRenderTarget  
 `CWnd` ウィンドウのデバイス コンテキスト (DC) レンダー ターゲットを取得します。  
  
```  
CDCRenderTarget* GetDCRenderTarget();
```  
  
### <a name="return-value"></a>戻り値  
 デバイス コンテキスト レンダー ターゲット、指定したウィンドウの関数が成功した場合それ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdescendantwindow"></a>  CWnd::GetDescendantWindow  
 指定された ID で指定された子孫ウィンドウを検索するには、このメンバー関数を呼び出す  
  
```  
CWnd* GetDescendantWindow(
    int nID,  
    BOOL bOnlyPerm = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 取得するコントロールまたは子ウィンドウの識別子を指定します。  
  
 `bOnlyPerm`  
 返されるウィンドウが一時的なできるかどうかを指定します。 場合**TRUE**場合、; 永続的なウィンドウのみを返すことが**false の場合、**関数は、一時的なウィンドウを返すことができます。 一時的なウィンドウの詳細については、次を参照してください。[テクニカル ノート 3:](../../mfc/tn003-mapping-of-windows-handles-to-objects.md)です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CWnd`オブジェクト、または**NULL**子ウィンドウが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、直接の子は、windows だけでなく、子ウィンドウのツリー全体を検索します。  
  
##  <a name="getdesktopwindow"></a>  揃える  
 Windows デスクトップ ウィンドウを返します。  
  
```  
static CWnd* PASCAL GetDesktopWindow();
```  
  
### <a name="return-value"></a>戻り値  
 Windows デスクトップ ウィンドウを識別します。 このポインターは、一時的な場合があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 デスクトップ ウィンドウ画面全体、その領域を上にすべてのアイコンと他のウィンドウを描画します。  
  
##  <a name="getdlgctrlid"></a>  CWnd::GetDlgCtrlID  
 任意の子ウィンドウのウィンドウまたはコントロールの ID 値を返します ダイアログ ボックスでコントロールのそれだけでなくです。  
  
```  
int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 数値識別子、`CWnd`子ウィンドウ関数が成功した。 それ以外の場合 0 の場合。  
  
### <a name="remarks"></a>コメント  
 この関数の戻り値が無効のトップレベルのウィンドウには、ID 値はありません、ため場合、`CWnd`トップレベル ウィンドウです。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::OnCtlColor](#onctlcolor)です。  
  
##  <a name="getdlgitem"></a>  CWnd::GetDlgItem  
 ダイアログ ボックスで指定されたコントロールまたは子ウィンドウまたはその他のウィンドウへのポインターを取得します。  
  
```  
CWnd* GetDlgItem(int nID) const;  
  
void GetDlgItem(
    int nID,  
    HWND* phWnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 取得するコントロールまたは子ウィンドウの識別子を指定します。  
  
 `phWnd`  
 子ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定されたコントロールまたは子ウィンドウへのポインター。 場合によって指定された整数の ID を持つコントロールなし、`nID`パラメーターが存在する、値は、 **NULL**です。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 返されるポインターは、通常で識別されるコントロールの種類にキャスト`nID`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#97](../../mfc/reference/codesnippet/cpp/cwnd-class_36.cpp)]  
  
##  <a name="getdlgitemint"></a>  CWnd::GetDlgItemInt  
 指定されたコントロールのテキストを取得`nID`です。  
  
```  
UINT GetDlgItemInt(
    int nID,  
    BOOL* lpTrans = NULL,  
    BOOL bSigned = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 変換する ダイアログ ボックス コントロールの整数識別子を指定します。  
  
 `lpTrans`  
 変換されたフラグを受信するブール値変数へのポインター。  
  
 `bSigned`  
 取得する値が署名されているかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの項目テキストの翻訳された値を指定します。 有効な戻り値の 0 から`lpTrans`エラーを検出するために使用する必要があります。 符号付きの戻り値を使用する場合は、キャスト、`int`型です。  
  
 関数は、変換された数値がより大きい INT_MAX (符号付き数値) か UINT_MAX (符号なし) の場合は 0 を返します。  
  
 エラーが発生した場合に、数値以外の文字を検出し、上記の最大数を超えるなど`GetDlgItemInt`が指す位置に 0 をコピー`lpTrans`です。 エラーがない場合`lpTrans`0 以外の値を受け取ります。 場合`lpTrans`は**NULL**、`GetDlgItemInt`エラーに関する警告を表示しません。  
  
### <a name="remarks"></a>コメント  
 テキストの先頭にある余分なスペースを削除して、小数点以下桁数を変換する、特定のダイアログ ボックスで指定されたコントロールのテキストを整数値に変換します。 テキストの末尾に達すると、数値以外の任意の文字を検出したときに、平行移動を停止します。  
  
 場合`bSigned`は**TRUE**、`GetDlgItemInt`テキストの先頭にマイナス記号 (-) をチェックし、テキストを符号付き数値に変換します。 それ以外の場合、符号なしの値を作成します。  
  
 送信、 [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627)コントロールするメッセージ。  
  
##  <a name="getdlgitemtext"></a>  CWnd::GetDlgItemText  
 タイトルまたは ダイアログ ボックス コントロールに関連付けられたテキストを取得するには、このメンバー関数を呼び出します。  
  
```  
int GetDlgItemText(
    int nID,  
    LPTSTR lpStr,  
    int nMaxCount) const;  
  
int GetDlgItemText(
    int nID,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 タイトルを取得するコントロールの整数識別子を指定します。  
  
 `lpStr`  
 コントロールのタイトルまたはテキストを受信するバッファーへのポインター。  
  
 `nMaxCount`  
 最大長を指定 (文字) にコピーする文字列の`lpStr`します。 文字列がより長い場合`nMaxCount`、切り捨てられます。  
  
 `rString`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)です。  
  
### <a name="return-value"></a>戻り値  
 実際の終端の null 文字を含まない、バッファーにコピーされた文字数を指定します。 テキストをコピーしていない場合、値は 0 です。  
  
### <a name="remarks"></a>コメント  
 `GetDlgItemText`メンバー関数が指す位置にテキストをコピー`lpStr`をコピーするバイト数のカウントを返します。  
  
##  <a name="getdsccursor"></a>  CWnd::GetDSCCursor  
 データ ソース コントロールのデータ ソース、ユーザー名、パスワード、および SQL プロパティで定義されている基になるカーソルへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
IUnknown* GetDSCCursor();
```  
  
### <a name="return-value"></a>戻り値  
 データ ソース コントロールで定義されているカーソルへのポインター。 MFC は呼び出し元の対処`AddRef`のポインター。  
  
### <a name="remarks"></a>コメント  
 返されたポインターを使用すると、データ バインド グリッド コントロールなど、複雑なデータ バインド コントロールの ICursor プロパティを設定できます。 最初のバインドされたコントロールは、そのカーソルを要求するまで、データ ソース コントロールはアクティブになりません。 呼び出しで明示的にいずれかの可能性が`GetDSCCursor`または MFC バインド マネージャーによって暗黙的にします。 どちらの場合は、呼び出すことによってアクティブになるデータ ソース コントロールを強制できます`GetDSCCursor`し、呼び出す**リリース**への返されたポインターに対して**IUnknown**です。 アクティブ化には、基になるデータ ソースに接続しようとするデータ ソース コントロールが発生します。 次のコンテキストでは、返されたポインターを使用する可能性があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_AxDataBinding#1](../../mfc/reference/codesnippet/cpp/cwnd-class_6.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#5](../../mfc/reference/codesnippet/cpp/cwnd-class_37.cpp)]  
[!code-cpp[NVC_MFC_AxDataBinding#3](../../mfc/reference/codesnippet/cpp/cwnd-class_8.cpp)]  
  
##  <a name="getdynamiclayout"></a>  CWnd::GetDynamicLayout  
 動的レイアウト マネージャー オブジェクトへのポインターを取得します。  
  
```  
CMFCDynamicLayout* GetDynamicLayout();
```  
  
### <a name="return-value"></a>戻り値  
 動的レイアウト マネージャー オブジェクトへのポインター、または動的レイアウトが有効でない場合は NULL。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ オブジェクトは、返されたポインターを所有し、その有効期間を管理します。そのため、ポインターはオブジェクトへのアクセスにのみ使用する必要があります。ポインターを削除したり、ポインターを永続的に格納したりしないでください。  
  
##  <a name="getexstyle"></a>  CWnd::GetExStyle  
 ウィンドウの拡張スタイルを返します。  
  
```  
DWORD GetExStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウのスタイルを拡張します。 MFC で使用される拡張ウィンドウ スタイルの詳細については、次を参照してください。[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)です。  
  
##  <a name="getfocus"></a>  CWnd::GetFocus  
 ポインターを取得、`CWnd`現在入力フォーカスがあること。  
  
```  
static CWnd* PASCAL GetFocus();
```  
  
### <a name="return-value"></a>戻り値  
 現在のフォーカスのあるウィンドウへのポインターまたは**NULL**フォーカス ウィンドウがない場合。  
  
 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
##  <a name="getfont"></a>  CWnd::GetFont  
 送信、`WM_GETFONT`ウィンドウにメッセージを現在のフォントを取得します。  
  
```  
CFont* GetFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CFont](../../mfc/reference/cfont-class.md)ウィンドウの現在のフォントにアタッチされているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドも何も起こりませんウィンドウを処理しない限り、`WM_GETFONT`メッセージ。 多くの MFC クラスから派生する`CWnd`用のメッセージ ハンドラーを含む定義済みのウィンドウ クラスにアタッチされているために、このメッセージを処理、`WM_GETFONT`メッセージ。 派生したクラスは、このメソッドを使用する`CWnd`のメソッドのハンドラーを定義する必要があります、`WM_GETFONT`メッセージ。  
  
##  <a name="getforegroundwindow"></a>  CWnd::GetForegroundWindow  
 フォア グラウンド ウィンドウへのポインターを返します (ユーザーが現在作業しているウィンドウ)。  
  
```  
static CWnd* PASCAL GetForegroundWindow();
```  
  
### <a name="return-value"></a>戻り値  
 前面のウィンドウへのポインター。 一時的な可能性があります`CWnd`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 前面のウィンドウは、最上位のウィンドウ (フレーム ウィンドウまたはダイアログ ボックス) にのみ適用されます。  
  
##  <a name="geticon"></a>  CWnd::GetIcon  
 によって示されるか、大規模な (32 x 32) へのハンドルまたは小さな (16 x 16) アイコンを識別するハンドルを取得するには、このメンバー関数を呼び出す`bBigIcon`です。  
  
```  
HICON GetIcon(BOOL bBigIcon) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `bBigIcon`  
 場合は、32 ピクセルのアイコンによって 32 ピクセルを指定**TRUE**; 場合は、16 ピクセルのアイコンで 16 ピクセルを指定**FALSE**です。  
  
### <a name="return-value"></a>戻り値  
 アイコンにへのハンドル。 失敗した場合、返します**NULL**です。  
  
##  <a name="getlastactivepopup"></a>  CWnd::GetLastActivePopup  
 `CWnd` が所有するポップアップ ウィンドウのうち、直前にアクティブだったウィンドウを調べます。  
  
```  
CWnd* GetLastActivePopup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最後にアクティブなポップアップ ウィンドウを識別します。 戻り値には、次の条件のいずれかが満たされた場合、ウィンドウ自体になります。  
  
-   ウィンドウ自体が最後にアクティブにします。  
  
-   ウィンドウは、すべてのポップアップ ウィンドウを所有していません。  
  
-   ウィンドウは、最上位レベルのウィンドウではないや、別のウィンドウが所有します。  
  
 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="example"></a>例  
  例を参照して[:findwindow](#findwindow)です。  
  
##  <a name="getlayeredwindowattributes"></a>  CWnd::GetLayeredWindowAttributes  
 レイヤード ウィンドウの不透明度および透明度のカラー キーを取得します。  
  
```  
BOOL GetLayeredWindowAttributes(
    COLORREF* pcrKey,  
    BYTE* pbAlpha,  
    DWORD* pdwFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pcrKey*  
 ポインター、 **COLORREF**レイヤード ウィンドウの作成に使用される透明色のキーを受信する値。 この色で、ウィンドウで描画されたすべてのピクセルは透過的になります。 これは、 **NULL**引数が必要ない場合。  
  
 `pbAlpha`  
 ポインター、**バイト**レイヤード ウィンドウの不透明度を記述するために使用するアルファ値を受け取る。 ときに変数によって参照される`pbAlpha`が 0 の場合、ウィンドウが完全に透過的です。 ときに変数によって参照される`pbAlpha`255 は、ウィンドウは非透過的です。 これは、 **NULL**引数が必要ない場合。  
  
 *pdwFlags*  
 ポインター、`DWORD`レイヤリング フラグを受け取る。 これは、 **NULL**引数が必要ない場合。 使用可能な値の完全な一覧は、次を参照してください。 [GetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633508)です。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633508)Windows SDK で説明されている。  
  
##  <a name="getmenu"></a>  とき  
 このウィンドウのメニューへのポインターを取得します。  
  
```  
CMenu* GetMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニューを識別します。 値が**NULL**場合`CWnd`メニューがありません。 戻り値が定義されていない場合は`CWnd`子ウィンドウします。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 メニューがあるないために、この関数を子ウィンドウを使用しない必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#98](../../mfc/reference/codesnippet/cpp/cwnd-class_38.cpp)]  
  
##  <a name="getmenubarinfo"></a>  CWnd::GetMenuBarInfo  
 指定されたメニュー バーの情報を取得します。  
  
```  
BOOL GetMenuBarInfo(
    LONG idObject,  
    LONG idItem,  
    PMENUBARINFO pmbi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `idObject`  
 メニュー オブジェクトを指定します。 使用可能な値の一覧は、次を参照してください。 [GetMenuBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms647833)です。  
  
 `idItem`  
 情報を取得する対象の項目を指定します。 このパラメーターが 0 の場合、関数は、メニュー自体に関する情報を取得します。 このパラメーターが 1 の場合、関数は、メニューの最初の項目に関する情報を取得します。  
  
 *pmbi*  
 ポインター、 [MENUBARINFO](http://msdn.microsoft.com/library/windows/desktop/ms647564)情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetMenuBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms647833)Windows SDK で説明されている。  
  
##  <a name="getnextdlggroupitem"></a>  CWnd::GetNextDlgGroupItem  
 ダイアログ ボックスのコントロールのグループ内の前または次のコントロールを検索します。  
  
```  
CWnd* GetNextDlgGroupItem(
    CWnd* pWndCtl,  
    BOOL bPrevious = FALSE) const;  
  
COleControlSiteOrWnd* GetNextDlgGroupItem(
    COleControlSiteOrWnd* pCurSiteOrWnd = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndCtl`  
 検索の開始点として使用するコントロールを識別します。  
  
 `bPrevious`  
 ダイアログ ボックスでコントロールのグループを検索する方法を指定します。 場合**TRUE**場合、に、関数が、グループ内の前のコントロールを検索**FALSE**グループ内の次のコントロールを検索します。  
  
 `pCurSiteOrWnd`  
 識別、 **COleControlSiteOrWnd**コントロール。 詳細については`COleControlSiteOrWnd`を参照してください**解説**です。  
  
### <a name="return-value"></a>戻り値  
 このメンバー関数が成功した場合、グループ内の前または次のコントロールへのポインター。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 使用して作成されたコントロールのコントロールのグループから始まり、 [WS_GROUP](styles-used-by-mfc.md#window-styles)スタイルとで作成された最後のコントロールで終わる、 **WS_GROUP**スタイル。  
  
 既定では、`GetNextDlgGroupItem`メンバー関数が、グループ内の次のコントロールへのポインターを返します。 場合`pWndCtl`、グループの最初のコントロールを識別および`bPrevious`は**TRUE**、`GetNextDlgGroupItem`グループの最後のコントロールへのポインターを返します。  
  
> [!NOTE]
>  MFC では、ウィンドウなしの ActiveX コントロール、標準的な ActiveX コントロール、および windows をサポートするため、HWND のみでコントロールを不要になった参照十分です。 `COleControlSiteOrWnd`オブジェクトには、次のようにウィンドウを持つ ActiveX コントロール、ウィンドウなしの ActiveX コントロール、またはウィンドウで、オブジェクトを識別する情報が含まれています。  
  
|コントロールまたはウィンドウの種類|識別情報|  
|----------------------------|-----------------------------|  
|ウィンドウを持つ ActiveX コントロール|HWND を含むし、関連付ける、[メンバー](../../mfc/reference/colecontrolsite-class.md)関連付けオブジェクト。 `m_hWnd`のメンバー `COleControlSiteOrWnd` 、コントロールの HWND に設定されていると、 **m_pSite**をコントロールのメンバーが指す`COleControlSite`です。|  
|ウィンドウなしの ActiveX コントロール|含まれていません`HWND`です。 **M_pSite**のメンバー`COleControlSiteOrWnd`コントロールの指す`COleControlSite`、および**m_hWnd**メンバーは**NULL**です。|  
|標準のウィンドウ|のみを含み、`HWND`です。 `m_hWnd`のメンバー`COleControlSiteOrWnd`に設定されている、 `HWND` 、ウィンドウの**m_pSite**メンバーは**NULL**です。|  
  
##  <a name="getnextdlgtabitem"></a>  CWnd::GetNextDlgTabItem  
 使用して作成された最初のコントロールへのポインターを取得、 [WS_TABSTOP](styles-used-by-mfc.md#window-styles)スタイルの前または指定したコントロールに依存します。  
  
```  
CWnd* GetNextDlgTabItem(
    CWnd* pWndCtl,  
    BOOL bPrevious = FALSE) const;  
  
COleControlSiteOrWnd* GetNextDlgTabItem(
    COleControlSiteOrWnd* pCurSiteOrWnd,  
    BOOL bPrevious) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndCtl`  
 検索の開始点として使用するコントロールを識別します。  
  
 `pCurSiteOrWnd`  
 識別、 **COleControlSiteOrWnd**コントロール。 詳細については`COleControlSiteOrWnd`を参照してください[CWnd::GetNextDlgGroupItem](#getnextdlggroupitem)です。  
  
 `bPrevious`  
 ダイアログ ボックスの検索方法を指定します。 場合**TRUE**場合、に、関数が、ダイアログ ボックスの前のコントロールを検索**FALSE**、次のコントロールを検索します。  
  
### <a name="return-value"></a>戻り値  
 前または次のコントロールへのポインター、 **WS_TABSTOP**スタイルをメンバー関数が成功した場合。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
 詳細については`COleControlSiteOrWnd`を参照してください[CWnd::GetNextDlgGroupItem](#getnextdlggroupitem)です。  
  
##  <a name="getnextwindow"></a>  CWnd::GetNextWindow  
 ウィンドウ マネージャーの一覧で [次へ] (または前) のウィンドウを検索します。  
  
```  
CWnd* GetNextWindow(UINT nFlag = GW_HWNDNEXT) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlag`  
 関数が次のウィンドウまたは前のウィンドウにポインターを返すかどうかを指定します。 いずれかになります**どちら**、依存しているウィンドウが返されます、`CWnd`ウィンドウ マネージャーの一覧で、オブジェクトまたは**指定**、ウィンドウ マネージャーの 前のウィンドウが返されます一覧です。  
  
### <a name="return-value"></a>戻り値  
 次 (または前) を識別、メンバー関数が成功した場合、ウィンドウ マネージャーの一覧のウィンドウ。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ マネージャーの一覧には、すべてのトップレベル ウィンドウ、その関連付けられている子ウィンドウ、および任意の子ウィンドウの子ウィンドウのエントリが含まれています。  
  
 場合`CWnd`場合は、最上位レベルのウィンドウで、関数を探して次 (または前) トップレベルのウィンドウです。`CWnd`関数次 (または前) の検索の子ウィンドウ、子ウィンドウ。  
  
##  <a name="getolecontrolsite"></a>  CWnd::GetOleControlSite  
 指定された ActiveX コントロールのカスタム サイトを取得します。  
  
```  
COleControlSite* GetOleControlSite(UINT idControl) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `idControl`  
 ActiveX コントロールの ID。  
  
##  <a name="getopenclipboardwindow"></a>  CWnd::GetOpenClipboardWindow  
 現在クリップボードが開いているウィンドウのハンドルを取得します。  
  
```  
static CWnd* PASCAL GetOpenClipboardWindow();
```  
  
### <a name="return-value"></a>戻り値  
 現在クリップボードを開いて、関数が成功した場合は、ウィンドウのハンドルそれ以外の場合**NULL**です。  
  
##  <a name="getowner"></a>  CWnd::GetOwner  
 ウィンドウのオーナーへのポインターを取得します。  
  
```  
CWnd* GetOwner() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CWnd`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 オーナー ウィンドウがない場合は、親ウィンドウ オブジェクトへのポインターが既定で返されます。 所有者と、所有されている間のリレーションシップが、いくつかの重要な側面で親と子の縦横比と異なることに注意してください。 たとえば、親を持つウィンドウは、親ウィンドウのクライアント領域に限定されます。 所有されている windows は、デスクトップ上の任意の場所で描画できます。  
  
 この関数の所有権の概念とは異なるの所有権の概念[GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms633515)です。  
  
##  <a name="getparent"></a>  CWnd::GetParent  
 この関数では、(存在する場合) の子ウィンドウの親ウィンドウへのポインターを取得します。  
  
```  
CWnd* GetParent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 戻り値のセクションを参照して[GetParent](http://msdn.microsoft.com/library/windows/desktop/ms633510) Windows SDK に含まれています。  
  
### <a name="remarks"></a>コメント  
 `GetParent` (存在する場合、関数が直接の親にポインターを返します。 これに対し、[最上位](#getparentowner)関数が子ウィンドウではない最もイミディ エイトの親またはオーナー ウィンドウへのポインターを返します (はありません、 **WS_CHILD**スタイル)。 子ウィンドウ内に子ウィンドウがあるかどうかは`GetParent`と`GetParentOwner`異なる結果を返します。  
  
##  <a name="getparentframe"></a>  CWnd::GetParentFrame  
 親フレーム ウィンドウを取得するには、このメンバー関数を呼び出します。  
  
```  
CFrameWnd* GetParentFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、フレーム ウィンドウへのポインターそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 までの親チェーンを検索し、メンバー関数、 [CFrameWnd](../../mfc/reference/cframewnd-class.md) (またはその派生クラス) オブジェクトを検出します。  
  
##  <a name="getparentowner"></a>  CWnd::GetParentOwner  
 子ウィンドウの親ウィンドウまたはオーナー ウィンドウへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
CWnd* GetParentOwner() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CWnd`オブジェクト。 `CWnd` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CWnd` オブジェクトが生成され、関連付けられます。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 `GetParentOwner` 子ウィンドウではない最もイミディ エイトの親または所有者ウィンドウへのポインターを返します (はありません、 **WS_CHILD**スタイル)。 現在のオーナー ウィンドウで設定できる[SetOwner](#setowner)です。 既定では、ウィンドウの親は、その所有者はします。  
  
 これに対し、 [GetParent](#getparent)が子ウィンドウであるかどうか、関数が直接の親にポインターを返します。 子ウィンドウ内に子ウィンドウがあるかどうかは`GetParent`と`GetParentOwner`異なる結果を返します。  
  
##  <a name="getproperty"></a>  CWnd::GetProperty  
 指定された ActiveX コントロールのプロパティを取得するには、このメンバー関数を呼び出す`dwDispID`です。  
  
```  
void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp)const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 取得するプロパティを識別します。  
  
 `vtProp`  
 取得するプロパティの型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 `pvProp`  
 変数のアドレス プロパティの値が表示されます。 指定された型に一致する必要があります`vtProp`です。  
  
### <a name="remarks"></a>コメント  
 **GetProperty**を使用して値を返します`pvProp`です。  
  
> [!NOTE]
>  この関数は、上でのみ呼び出す必要があります、 `CWnd` ActiveX コントロールを表すオブジェクト。  
  
 ActiveX コントロール コンテナーでこのメンバー関数を使用する方法の詳細については、記事を参照してください。 [ActiveX コントロール コンテナー: ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング](../../mfc/programming-activex-controls-in-a-activex-control-container.md)です。  
  
##  <a name="getrendertarget"></a>  CWnd::GetRenderTarget  
 このウィンドウに関連付けられているレンダー ターゲットを取得します。  
  
```  
CHwndRenderTarget* GetRenderTarget();
```  
  
### <a name="return-value"></a>戻り値  
 レンダー ターゲットまたは NULL へのポインター。  
  
##  <a name="getsafehwnd"></a>  CWnd::GetSafeHwnd  
 返します`m_hWnd`、または**NULL**場合、**この**ポインターが**NULL**です。  
  
```  
HWND GetSafeHwnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウのウィンドウ ハンドルを返します。 返します**NULL**場合、`CWnd`ウィンドウにアタッチされていないで使用されている場合や、 **NULL CWnd**ポインター。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::SubclassWindow](#subclasswindow)です。  
  
##  <a name="getsafeowner"></a>  CWnd::GetSafeOwner  
 ダイアログ ボックスを使用する必要がありますオーナー ウィンドウまたはその他のモーダル ウィンドウを取得するには、このメンバー関数を呼び出します。  
  
```  
static CWnd* GetSafeOwner(
    CWnd* pParent = NULL,  
    HWND* pWndTop = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParent`  
 親へのポインター`CWnd`ウィンドウです。 あります**NULL**です。  
  
 *pWndTop*  
 現在の上部にあるウィンドウへのポインター。 あります**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 指定されたウィンドウのセーフ オーナーへのポインター。  
  
### <a name="remarks"></a>コメント  
 セーフ オーナーの最初の子でない親ウィンドウは、`pParent`です。 場合`pParent`は**NULL**、スレッドのメイン ウィンドウ (を介して取得された[AfxGetMainWnd](../../mfc/reference/application-information-and-management.md#afxgetmainwnd))、所有者を見つけるために使用します。  
  
> [!NOTE]
>  Framework 自体では、この関数を使用して、所有者が指定されていません ダイアログ ボックスやプロパティ シートの正しいオーナー ウィンドウを確認します。  
  
##  <a name="getscrollbarctrl"></a>  Cwnd::getscrollbarctrl  
 指定した兄弟スクロール バーまたは分割へのポインターを取得するには、このメンバー関数を呼び出すウィンドウです。  
  
```  
virtual CScrollBar* GetScrollBarCtrl(int nBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 スクロール バーの種類を指定します。 パラメーターには、次の値のいずれかを実行できます。  
  
- **SB_HORZ**水平スクロール バーの位置を取得します。  
  
- **SB_VERT**垂直スクロール バーの位置を取得します。  
  
### <a name="return-value"></a>戻り値  
 兄弟スクロール バーのコントロールまたは**NULL**されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、スクロール バーの場合、作成するのには動作しません、 **WS_HSCROLL**または**WS_VSCROLL**のビットがウィンドウの作成時に設定されます。 `CWnd`この関数の実装を返すだけ**NULL**です。 など、クラスの派生`CView`、記載されている機能を実装します。  
  
##  <a name="getscrollbarinfo"></a>  CWnd::GetScrollBarInfo  
 指定されたスクロール バーの情報を取得します。  
  
```  
BOOL GetScrollBarInfo(
    LONG idObject,  
    PSCROLLBARINFO psbi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `idObject`  
 メニュー オブジェクトを指定します。 使用可能な値の一覧は、次を参照してください。 [GetScrollBarInfo](http://msdn.microsoft.com/library/windows/desktop/bb787581)です。  
  
 *psbi*  
 ポインター、 [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535)情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetScrollBarInfo](http://msdn.microsoft.com/library/windows/desktop/bb787581)Windows SDK で説明されている。  
  
##  <a name="getscrollinfo"></a>  CWnd::GetScrollInfo  
 情報を取得するには、このメンバー関数を呼び出すこと、`SCROLLINFO`構造体がスクロール バーについて保持します。  
  
```  
BOOL GetScrollInfo(
    int nBar,  
    LPSCROLLINFO lpScrollInfo,  
    UINT nMask = SIF_ALL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 スクロール バーのコントロールまたはウィンドウの非クライアント領域の一部であるかどうかを指定します。 非クライアント領域の一部である場合`nBar`かどうか、スクロール バーが水平、垂直方向に配置されているか、どちらも示します。 次のいずれかを指定する必要があります。  
  
- **SB_CTL**スクロール バー コントロールのパラメーターを取得します。 `m_hWnd`データ メンバーは、スクロール バー コントロールのハンドルをする必要があります。  
  
- **SB_HORZ**ウィンドウの標準の水平スクロール バーのパラメーターを取得します。  
  
- **SB_VERT**ウィンドウの標準の垂直スクロール バーのパラメーターを取得します。  
  
 `lpScrollInfo`  
 ポインター、 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造体。 この構造体の詳細については、Windows SDK を参照してください。  
  
 `nMask`  
 取得するスクロール バーのパラメーターを指定します。 既定値の組み合わせを指定する**SIF_PAGE**、 **SIF_POS**、 **SIF_TRACKPOS**、および**SIF_RANGE**です。 参照してください`SCROLLINFO`の詳細について、*いる*値。  
  
### <a name="return-value"></a>戻り値  
 メッセージには、任意の値が取得されると場合、戻り値は**TRUE**です。 以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 `GetScrollInfo` 32 ビットのスクロール位置を使用するアプリケーションを有効にします。  
  
 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造体には、スクロール バーの最小値と最大スクロール位置、ページ サイズおよびスクロール ボックス (つまみ) の位置を含むに関する情報が含まれています。 参照してください、`SCROLLINFO`構造の既定値の変更の詳細については、Windows SDK のトピックを構造体。  
  
 MFC のウィンドウ メッセージ ハンドラーをスクロール バーの位置を示す[CWnd::OnHScroll](#onhscroll)と[ために](#onvscroll)、位置データの 16 ビットのみを提供します。 `GetScrollInfo` および`SetScrollInfo`32 ビットのスクロール バーの位置のデータを提供します。 したがって、アプリケーションが呼び出すことができます`GetScrollInfo`いずれかの処理中に`CWnd::OnHScroll`または`CWnd::OnVScroll`32 ビットのスクロール バーの位置のデータを取得します。  
  
##  <a name="getscrolllimit"></a>  CWnd::GetScrollLimit  
 スクロール バーの最大のスクロール位置を取得するには、このメンバー関数を呼び出します。  
  
```  
int GetScrollLimit(int nBar);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 スクロール バーの種類を指定します。 パラメーターには、次の値のいずれかを実行できます。  
  
- **SB_HORZ**水平スクロール バーのスクロールの制限を取得します。  
  
- **SB_VERT**垂直スクロール バーのスクロールの制限を取得します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、スクロール バーの最大の位置を指定しますそれ以外の場合 0 を返します。  
  
##  <a name="getscrollpos"></a>  CWnd::GetScrollPos  
 スクロール バーのスクロール ボックスの現在位置を取得します。  
  
```  
int GetScrollPos(int nBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 検査するスクロール バーを指定します。 パラメーターには、次の値のいずれかを実行できます。  
  
- **SB_HORZ**水平スクロール バーの位置を取得します。  
  
- **SB_VERT**垂直スクロール バーの位置を取得します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、スクロール バーのスクロール ボックスの現在の位置を指定します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 現在の位置は、現在のスクロールの範囲に依存する相対値です。 たとえば、スクロールの範囲が 50 ~ 100 でスクロール ボックスは、バーの途中の場合、現在の位置が 75 です。  
  
##  <a name="getscrollrange"></a>  CWnd::GetScrollRange  
 指定されたスクロール バーの現在の最小値と最大のスクロール バーの位置で指定された場所にコピーして`lpMinPos`と`lpMaxPos`です。  
  
```  
void GetScrollRange(
    int nBar,  
    LPINT lpMinPos,  
    LPINT lpMaxPos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 検査するスクロール バーを指定します。 パラメーターには、次の値のいずれかを実行できます。  
  
- **SB_HORZ**水平スクロール バーの位置を取得します。  
  
- **SB_VERT**垂直スクロール バーの位置を取得します。  
  
 `lpMinPos`  
 最小の位置を受け取る整数変数へのポインター。  
  
 `lpMaxPos`  
 最大の位置を受け取る整数変数へのポインター。  
  
### <a name="remarks"></a>コメント  
 場合`CWnd`、スクロール バーがない、`GetScrollRange`メンバー関数をコピーする場合は 0`lpMinPos`と`lpMaxPos`です。  
  
 標準のスクロール バーの既定の範囲は、0 ~ 100 です。 スクロール バー コントロールの既定の範囲が空 (両方の値が 0) です。  
  
##  <a name="getstyle"></a>  CWnd::GetStyle  
 現在のウィンドウ スタイルを返します。  
  
```  
DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウのスタイルです。 MFC で使用されるウィンドウ スタイルの詳細については、次を参照してください。[ウィンドウ スタイル](styles-used-by-mfc.md#window-styles)です。  
  
##  <a name="getsystemmenu"></a>  CWnd::GetSystemMenu  
 アプリケーションがコピーおよび変更のためにコントロール メニューにアクセスできるようにします。  
  
```  
CMenu* GetSystemMenu(BOOL bRevert) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `bRevert`  
 実行するアクションを指定します。 場合`bRevert`は**FALSE**、`GetSystemMenu`現在使用されているコントロールのメニューのコピーへのハンドルを返します。 このコピーは、最初にコントロール メニューと同じですが、変更できます。 場合`bRevert`は**TRUE**、`GetSystemMenu`コントロール メニューを既定の状態にリセットします。 以前、変更された可能性があります] メニューの [場合制御は破棄します。 戻り値はここでは定義されません。  
  
### <a name="return-value"></a>戻り値  
 場合にコントロール メニューのコピーを識別`bRevert`は**FALSE**です。 場合`bRevert`は**TRUE**、戻り値が定義されていません。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 任意のウィンドウを使用しない`GetSystemMenu`メニューが標準コントロール メニューを受け取るコントロールの独自のコピーを作成します。  
  
 によって返されたポインター、`GetSystemMenu`でメンバー関数を使用できます、 [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)、 [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)、または[CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)関数コントロールのメニューを変更します。  
  
 コントロールのメニューが最初になどのさまざまな ID 値を持つ指定された項目を含む**SC_CLOSE**、**における**、および**初期状態**です。 コントロールのメニュー上の項目を生成[WM_SYSCOMMAND](#onsyscommand)メッセージ。 定義済みのすべてのコントロール メニュー項目では、0xF000 よりも大きい ID 番号を持っています。 アプリケーションは、コントロール メニュー項目を追加する場合は、F000 未満の ID 番号を使用してください。  
  
 Windows は、可能性がありますに自動的に項目の利用できないように、標準のコントロール メニュー。 `CWnd` 実行できますが使用できなくなる以上の独自の選択に応答することにより、 [WM_INITMENU](#oninitmenu)メッセージで、任意のメニューが表示される前に送信されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#99](../../mfc/reference/codesnippet/cpp/cwnd-class_39.cpp)]  
  
##  <a name="gettitlebarinfo"></a>  CWnd::GetTitleBarInfo  
 指定されたタイトル バーの情報を取得します。  
  
```  
BOOL GetTitleBarInfo(PTITLEBARINFO pti) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pti*  
 ポインター、 [TITLEBARINFO](http://msdn.microsoft.com/library/windows/desktop/ms632608)情報を受け取る構造体。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetTitleBarInfo](http://msdn.microsoft.com/library/windows/desktop/ms633513)Windows SDK で説明されている。  
  
##  <a name="gettoplevelframe"></a>  CWnd::GetTopLevelFrame  
 存在する場合は、ウィンドウの最上位レベルのフレーム ウィンドウを取得するには、このメンバー関数を呼び出します。  
  
```  
CFrameWnd* GetTopLevelFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウの最上位のフレーム ウィンドウを識別します。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 場合`CWnd`関連付けられているウィンドウがないか、最上位の親がありませんが、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)-派生オブジェクトをこの関数を返します**NULL**です。  
  
##  <a name="gettoplevelowner"></a>  CWnd::GetTopLevelOwner  
 トップレベル ウィンドウを取得するには、このメンバー関数を呼び出します。  
  
```  
CWnd* GetTopLevelOwner() const;  
```  
  
### <a name="return-value"></a>戻り値  
 トップレベル ウィンドウを識別します。 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 最上位のウィンドウは、デスクトップの子であるウィンドウです。 場合`CWnd`を持たない関連付けられているウィンドウは、この関数を返します**NULL**です。  
  
##  <a name="gettoplevelparent"></a>  CWnd::GetTopLevelParent  
 ウィンドウの最上位の親を取得するには、このメンバー関数を呼び出します。  
  
```  
CWnd* GetTopLevelParent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウの最上位の親ウィンドウを識別します。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 `GetTopLevelParent` ような[GetTopLevelFrame](#gettoplevelframe)と[GetTopLevelOwner](#gettoplevelowner)。 ただし、現在のオーナー ウィンドウとして設定された値は無視されます。  
  
##  <a name="gettopwindow"></a>  CWnd::GetTopWindow  
 属している最上位レベルの子ウィンドウの検索`CWnd`です。  
  
```  
CWnd* GetTopWindow() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最上位レベルの子ウィンドウを識別、`CWnd`子ウィンドウのリンク リストです。 子ウィンドウが存在しない場合、値は**NULL**です。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 場合`CWnd`子を持っていない、この関数を返します**NULL**です。  
  
##  <a name="getupdaterect"></a>  CWnd::GetUpdateRect  
 更新領域を完全に囲む最小の四角形の座標を取得します。  
  
```  
BOOL GetUpdateRect(
    LPRECT lpRect,  
    BOOL bErase = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`CRect`オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)更新領域が囲むされる更新プログラムのクライアント座標を受け取ることができます。  
  
 このパラメーターに設定**NULL**内更新領域に存在するかどうかを決定する、`CWnd`です。 場合`lpRect`は**NULL**、`GetUpdateRect`更新領域が存在し、1 つの場合は 0 がない場合、メンバー関数が 0 以外を返します。 これによりを決定するかどうか、`WM_PAINT`無効領域からメッセージが発生しました。 このパラメーターを設定しないで**NULL** 3.0 と以前のバージョンの Windows で。  
  
 `bErase`  
 更新領域の背景を消去するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 更新領域の状態を指定します。 値が更新領域が空でない場合は 0 以外です。それ以外の場合 0 を返します。  
  
 場合、`lpRect`にパラメーターが設定されている**NULL**、戻り値は更新領域が存在する場合は 0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 場合`CWnd`で作成された、 **CS_OWNDC**スタイルとのマッピング モードではありません`MM_TEXT`、`GetUpdateRect`メンバー関数は、論理座標で四角形を提供します。 それ以外の場合、`GetUpdateRect`クライアントの四角形の座標を提供します。 更新領域がない場合は`GetUpdateRect`四角形を空にすること (すべての座標は 0 に設定) を設定します。  
  
 `bErase`パラメーターを指定するかどうか`GetUpdateRect`更新領域の背景を消去する必要があります。 場合`bErase`は**TRUE**更新領域が空でないと、背景を消去します。 バック グラウンドを消去する`GetUpdateRect`送信、 [WM_ERASEBKGND](#onerasebkgnd)メッセージ。  
  
 によって取得された更新の四角形、 [BeginPaint](#beginpaint)メンバー関数はによって取得されたものと同じ、`GetUpdateRect`メンバー関数。  
  
 `BeginPaint`メンバー関数は、更新領域を自動的に検証ため、すべての呼び出しに`GetUpdateRect`への呼び出しの直後に行われた`BeginPaint`空更新領域を取得します。  
  
##  <a name="getupdatergn"></a>  CWnd::GetUpdateRgn  
 によって識別される領域の更新領域を取得`pRgn`です。  
  
```  
int GetUpdateRgn(
    CRgn* pRgn,  
    BOOL bErase = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 更新領域を識別します。  
  
 `bErase`  
 背景を消去して、子ウィンドウの非クライアント領域を描画するかどうかを指定します。 値が場合**FALSE**描画は実行されません。  
  
### <a name="return-value"></a>戻り値  
 結果として得られる領域の種類を示す short 型整数フラグを指定します。 値は、次のいずれかを実行できます。  
  
- **SIMPLEREGION**領域には、重複する境界がありません。  
  
- **COMPLEXREGION**境界が重複領域には、します。  
  
- **NULLREGION**領域が空です。  
  
- **エラー**領域は作成されませんでした。  
  
### <a name="remarks"></a>コメント  
 この領域の座標では、(クライアント座標) の左上隅に対して相対的です。  
  
 [BeginPaint](#beginpaint)メンバー関数は、更新領域を自動的に検証ため、すべての呼び出しに`GetUpdateRgn`への呼び出しの直後に行われた`BeginPaint`空更新領域を取得します。  
  
##  <a name="getwindow"></a>  CWnd::GetWindow  
 要求されると、ウィンドウへのポインターを返しますまたは**NULL**されていない場合。  
  
```  
CWnd* GetWindow(UINT nCmd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nCmd`  
 間のリレーションシップを指定`CWnd`と返されるウィンドウです。 値は次のいずれかを実行します。  
  
- **GW_CHILD**を識別、`CWnd`最初の子ウィンドウ。  
  
- **GW_HWNDFIRST**場合`CWnd`子ウィンドウは、最初の兄弟ウィンドウが返されます。 それ以外の場合、リストの最初のトップレベル ウィンドウを返します。  
  
- **GW_HWNDLAST**場合`CWnd`子ウィンドウは、最後の兄弟ウィンドウが返されます。 それ以外の場合、一覧で、最後のトップレベル ウィンドウを返します。  
  
- **どちら**ウィンドウ マネージャーの一覧で、[次へ] のウィンドウを返します。  
  
- **指定**ウィンドウ マネージャーの一覧の前のウィンドウを返します。  
  
- **GW_OWNER**を識別、`CWnd`所有者。  
  
### <a name="return-value"></a>戻り値  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
##  <a name="getwindowcontexthelpid"></a>  CWnd::GetWindowContextHelpId  
 ウィンドウに関連付けられている場合は、ヘルプ コンテキスト識別子を取得するには、このメンバー関数を呼び出します。  
  
```  
DWORD GetWindowContextHelpId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ヘルプ コンテキスト id。 ウィンドウがあるない場合は、0 を返します。  
  
##  <a name="getwindowedchildcount"></a>  CWnd::GetWindowedChildCount  
 関連付けられている子ウィンドウの数を取得するには、このメンバー関数を呼び出します。  
  
```  
long GetWindowedChildCount();
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられている子ウィンドウの数、`CWnd`オブジェクト。  
  
##  <a name="getwindowdc"></a>  CWnd::GetWindowDC  
 キャプション バー、メニューのおよびスクロール バーを含む、ウィンドウ全体のディスプレイ コンテキストを取得します。  
  
```  
CDC* GetWindowDC();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、指定されたウィンドウのディスプレイ コンテキストを識別します。それ以外の場合**NULL**です。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。 [ReleaseDC](#releasedc)成功した呼び出しごとに 1 回呼び出す必要があります`GetWindowDC`です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ表示のコンテキストにより、どこにでも描画`CWnd`コンテキストの原点の左上隅にあるのため、`CWnd`クライアント領域の代わりにします。  
  
 既定の属性は、コンテキストを取得するたびにディスプレイ コンテキストに割り当てられます。 以前の属性は失われます。  
  
 `GetWindowDC` 特殊な描画効果を使用するものでは、`CWnd`非クライアント領域。 すべてのウィンドウの非クライアント領域に描画は推奨されません。  
  
 [問題](http://msdn.microsoft.com/library/windows/desktop/ms724385)Windows 関数を使用して、非クライアント領域、キャプション バー、メニューのおよびスクロール バーなどのさまざまな部分のサイズを取得することができます。  
  
 ペイントが完了した後、 [ReleaseDC](#releasedc)ディスプレイ コンテキストを解放するメンバー関数を呼び出す必要があります。 ディスプレイ コンテキストを解放に失敗は、描画、同時に開くことができるデバイス コンテキストの数に制限のためのアプリケーションによって要求を真剣に影響します。  
  
##  <a name="getwindowinfo"></a>  CWnd::GetWindowInfo  
 ウィンドウに関する情報を取得します。  
  
```  
BOOL GetWindowInfo(PWINDOWINFO pwi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pwi*  
 ポインター、 [WINDOWINFO](http://msdn.microsoft.com/library/windows/desktop/ms632610)構造体。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[GetWindowInfo](http://msdn.microsoft.com/library/windows/desktop/ms633516)Windows SDK で説明されている。  
  
##  <a name="getwindowlesschildcount"></a>  CWnd::GetWindowlessChildCount  
 関連付けられているウィンドウなしの子ウィンドウの数を取得します。  
  
```  
long GetWindowlessChildCount();
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられているウィンドウなしの子ウィンドウの数、`CWnd`オブジェクト。  
  
##  <a name="getwindowplacement"></a>  CWnd::GetWindowPlacement  
 ウィンドウの表示状態、通常の位置 (復元された位置)、最小化された位置、および最大表示された位置を取得します。  
  
```  
BOOL GetWindowPlacement(WINDOWPLACEMENT* lpwndpl) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpwndpl`  
 指す、`WINDOWPLACEMENT`表示状態と位置情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **フラグ**のメンバー、 [WINDOWPLACEMENT](../../mfc/reference/windowplacement-structure.md)この関数によって取得された構造体は、常に 0 です。 場合`CWnd`が最大化、 **showCmd**のメンバー`WINDOWPLACEMENT`は**で**です。 ウィンドウを最小化されている場合は**SW_SHOWMINIMIZED です。** **SW_SHOWNORMAL**それ以外の場合。  
  
##  <a name="getwindowrect"></a>  CWnd::GetWindowRect  
 外接する四角形の寸法をコピー、`CWnd`構造にオブジェクトを指す`lpRect`です。  
  
```  
void GetWindowRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`CRect`オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)左と右下コーナーの画面座標を受信します。  
  
### <a name="remarks"></a>コメント  
 ディメンションは、ディスプレイ画面の左上隅を基準とした画面座標で表されます。 キャプション、罫線、およびスクロール バーのサイズ、存在する場合が含まれます。  
  
##  <a name="getwindowrgn"></a>  CWnd::GetWindowRgn  
 ウィンドウのウィンドウ領域を取得するには、このメンバー関数を呼び出します。  
  
```  
int GetWindowRgn(HRGN hRgn)const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `hRgn`  
 ウィンドウ領域へのハンドル。  
  
### <a name="return-value"></a>戻り値  
 戻り値は、この関数は取得される領域の種類を指定します。 次の値のいずれかを指定できます。  
  
- **NULLREGION**領域が空です。  
  
- **SIMPLEREGION**地域が 1 つの四角形。  
  
- **COMPLEXREGION**地域が 1 つ以上の四角形。  
  
- **エラー**エラーが発生しました; 領域には影響しません。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ領域では、オペレーティング システムが描画を許可されているウィンドウ内の領域を判断します。 オペレーティング システムでは、ウィンドウ領域の外部にあるウィンドウの任意の部分は表示されません。  
  
 ウィンドウのウィンドウ領域の座標では、ウィンドウのクライアント領域ではなく、ウィンドウの左上隅に対して相対的です。  
  
 ウィンドウのウィンドウ領域を設定するには、呼び出す[は](#setwindowrgn)します。  
  
##  <a name="getwindowtext"></a>  CWnd::GetWindowText  
 コピー、`CWnd`が指すバッファーにタイトル (ある場合) をキャプション`lpszStringBuf`または変換先の文字列に`rString`です。  
  
```  
int GetWindowText(
    LPTSTR lpszStringBuf,  
    int nMaxCount) const;  
  
void GetWindowText(
    CString& rString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszStringBuf`  
 ウィンドウのタイトルのコピーされた文字列を受け取るバッファーへのポインター。  
  
 `nMaxCount`  
 終端の null 文字を含む、バッファーにコピーする文字の最大数を指定します。 指定された文字数よりも長い場合は、文字列`nMaxCount`、切り捨てられます。  
  
 `rString`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)をウィンドウのタイトルのコピーされた文字列を受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 文字、終端の null 文字を含まない、コピーされた文字列の長さを指定します。 場合は 0 を`CWnd`キャプションを持たない場合またはキャプションが空です。  
  
### <a name="remarks"></a>コメント  
 場合、`CWnd`オブジェクトは、コントロール、`GetWindowText`メンバー関数は、キャプションをコピーする代わりに、コントロール内のテキストをコピーします。  
  
 このメンバー関数、 [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627)に送信されるメッセージ、`CWnd`オブジェクト。  
  
### <a name="example"></a>例  
  例を参照して[とき](#setwindowtext)です。  
  
##  <a name="getwindowtextlength"></a>  CWnd::GetWindowTextLength  
 長さを返します、`CWnd`オブジェクトのキャプションのタイトル。  
  
```  
int GetWindowTextLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 任意の null 終了文字を除く、文字でテキストの長さを指定します。 そのようなテキストが存在しない場合、値は 0 です。  
  
### <a name="remarks"></a>コメント  
 場合`CWnd`のコントロール、`GetWindowTextLength`メンバー関数は、キャプションの代わりに、コントロール内のテキストの長さを返します。  
  
 このメンバー関数、 [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628)に送信されるメッセージ、`CWnd`オブジェクト。  
  
### <a name="example"></a>例  
  例を参照して[とき](#setwindowtext)です。  
  
##  <a name="hidecaret"></a>  CWnd::HideCaret  
 ディスプレイ画面からキャレットを削除して非表示にします。  
  
```  
void HideCaret();
```  
  
### <a name="remarks"></a>コメント  
 キャレットは表示されませんが、再表示できますを使用して、 [ShowCaret](#showcaret)メンバー関数。 カレットを非表示、現在の形状を破棄しません。  
  
 非表示は累積されます。 場合`HideCaret`行で、5 回が呼び出されて、`ShowCaret`カレットを表示する前に、メンバー関数で 5 回する呼び出されなければなりません。  
  
##  <a name="hilitemenuitem"></a>  CWnd::HiliteMenuItem  
 強調表示または最上位レベル (メニュー バー) のメニュー項目の強調表示を削除します。  
  
```  
BOOL HiliteMenuItem(
    CMenu* pMenu,  
    UINT nIDHiliteItem,  
    UINT nHilite);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenu`  
 強調表示の項目を含むトップレベルのメニューを識別します。  
  
 `nIDHiliteItem`  
 値に応じて、強調表示するメニュー項目を指定します、`nHilite`パラメーター。  
  
 `nHilite`  
 メニュー項目が強調表示や、強調表示が削除されるかどうかを指定します。 組み合わせであることができます**MF_HILITE**または**MF_UNHILITE**で**とき**または**MF_BYPOSITION**です。 値は、ビットごとの OR 演算子を使用して結合できます。 これらの値には、次の意味があります。  
  
- **とき**Interprets`nIDHiliteItem`メニュー項目の ID (既定の解釈) として。  
  
- **MF_BYPOSITION** Interprets`nIDHiliteItem`としてのメニュー項目の 0 から始まるオフセット。  
  
- **MF_HILITE**項目を強調表示します。 この値が指定されていない場合は、強調表示が、項目から削除されます。  
  
- **MF_UNHILITE**強調表示項目から削除します。  
  
### <a name="return-value"></a>戻り値  
 メニュー項目が強調表示されたかどうかを指定します。 項目が強調表示される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **MF_HILITE**と**MF_UNHILITE**フラグは、このメンバー関数でのみ使用できます。 では使用できません、 [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)メンバー関数。  
  
##  <a name="htmlhelp"></a>  CWnd::HtmlHelp  
 Html ヘルプ アプリケーションを起動するには、このメンバー関数を呼び出します。  
  
```  
virtual void HtmlHelp(
    DWORD_PTR dwData,  
    UINT nCmd = 0x000F);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwData`  
 追加のデータを指定します。 使用される値は、の値によって異なります、`nCmd`パラメーター。  
  
 `nCmd`  
 要求されるヘルプの種類を指定します。 指定できる値とどのように影響の一覧については、`dwData`パラメーターを参照してください、`uCommand`パラメーターは、Windows SDK で HTML ヘルプ API リファレンスで説明します。  
  
### <a name="remarks"></a>コメント  
 参照してください[CWinApp::HtmlHelp](../../mfc/reference/cwinapp-class.md#htmlhelp)詳細についてはします。  
  
##  <a name="initdynamiclayout"></a>  CWnd::InitDynamicLayout  
 ウィンドウの動的レイアウトを初期化するために、フレームワークによって呼び出されます。  
  
```  
void InitDynamicLayout();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを直接呼び出さないでください。  
  
##  <a name="invalidate"></a>  CWnd::Invalidate  
 クライアント領域全体の無効化`CWnd`です。  
  
```  
void Invalidate(BOOL bErase = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bErase`  
 更新領域の背景を消去するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 クライアント領域対象となっているときに描画次[WM_PAINT](#onpaint)メッセージが表示されます。 前に、領域を検証することも、`WM_PAINT`によってメッセージが発生した、 [ValidateRect](#validaterect)または[ValidateRgn](#validatergn)メンバー関数。  
  
 `bErase`パラメーターは、バック グラウンド更新領域が更新領域の処理時に消去するかどうかを指定します。 場合`bErase`は**TRUE**、背景が消去されるときに、 [BeginPaint](#beginpaint)メンバー関数が呼び出されます場合`bErase`は**FALSE**、、背景がそのまま。変更されません。 場合`bErase`は**TRUE**更新領域の任意の部分では、特定の部分ではなく、領域全体の背景を消去します。  
  
 Windows の送信、 [WM_PAINT](#onpaint)されるたびにメッセージ、`CWnd`更新領域が空でないと、そのウィンドウで、アプリケーション キュー内の他のメッセージはありません。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::UpdateWindow](#updatewindow)です。  
  
##  <a name="invalidaterect"></a>  エディット  
 その四角形を追加することによって指定された四角形内のクライアント領域を無効になります、`CWnd`更新領域。  
  
```  
void InvalidateRect(
    LPCRECT lpRect,  
    BOOL bErase = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`CRect`オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)更新領域に追加する (クライアント座標) の四角形を格納しています。 場合`lpRect`は**NULL**、クライアント領域全体が、領域に追加します。  
  
 `bErase`  
 更新領域の背景を消去するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 無効化された四角形の更新領域内の他のすべての領域と対象となっているときに描画次[WM_PAINT](#onpaint)メッセージを送信します。 地域が処理されるまで更新領域に、無効化された領域が蓄積されるときに、次へ`WM_PAINT`呼び出しが発生すると、または地域はによって検証されるまで、 [ValidateRect](#validaterect)または[ValidateRgn](#validatergn)メンバー関数。  
  
 `bErase`パラメーターは、バック グラウンド更新領域が更新領域の処理時に消去するかどうかを指定します。 場合`bErase`は**TRUE**、背景が消去されるときに、 [BeginPaint](#beginpaint)メンバー関数が呼び出されます場合`bErase`は**FALSE**、、背景がそのまま。変更されません。 場合`bErase`は**TRUE**更新領域の任意の部分では、領域全体の背景が消去された、特定の部分ではなくです。  
  
 Windows の送信、 [WM_PAINT](#onpaint)されるたびにメッセージ、`CWnd`更新領域が空でないと、そのウィンドウで、アプリケーション キュー内の他のメッセージはありません。  
  
##  <a name="invalidatergn"></a>  CWnd::InvalidateRgn  
 現在の更新領域に追加することによって指定された領域内のクライアント領域を無効に`CWnd`です。  
  
```  
void InvalidateRgn(
    CRgn* pRgn,  
    BOOL bErase = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 ポインター、 [CRgn](../../mfc/reference/crgn-class.md)更新領域に追加する領域を識別するオブジェクト。 領域は、クライアント座標にあると見なされます。 このパラメーターが場合**NULL**、クライアント領域全体が更新領域に追加します。  
  
 `bErase`  
 更新領域の背景を消去するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 描画時に更新 領域で他のすべての領域と、無効化された領域がマークされている、 [WM_PAINT](#onpaint)メッセージが次に送信します。 領域が処理されるまで更新領域に、無効化された領域が蓄積されるときに、`WM_PAINT`メッセージが送信される次に、または地域はによって検証されるまで、 [ValidateRect](#validaterect)または[ValidateRgn](#validatergn)メンバー関数。  
  
 `bErase`パラメーターは、バック グラウンド更新領域が更新領域の処理時に消去するかどうかを指定します。 場合`bErase`は**TRUE**、背景が消去されるときに、 [BeginPaint](#beginpaint)メンバー関数が呼び出されます場合`bErase`は**FALSE**、、背景がそのまま。変更されません。 場合`bErase`は**TRUE**更新領域の任意の部分では、特定の部分ではなく、領域全体の背景を消去します。  
  
 Windows の送信、 [WM_PAINT](#onpaint)されるたびにメッセージ、`CWnd`更新領域が空でないと、そのウィンドウで、アプリケーション キュー内の他のメッセージはありません。  
  
 指定された領域必要がありますが以前に作成した領域関数のいずれかでします。  
  
##  <a name="invokehelper"></a>  CWnd::InvokeHelper  
 ActiveX コントロール メソッドまたはで指定されたプロパティを呼び出すには、このメンバー関数を呼び出す`dwDispID`で指定されたコンテキストで`wFlags`です。  
  
```  
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo,  
 ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 呼び出されるメソッドまたはプロパティを識別します。  
  
 `wFlags`  
 **IDispatch::Invoke**呼び出しのコンテキストを記述するフラグ。  
  
 `vtRet`  
 戻り値の型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 `pvRet`  
 変数のアドレスは、プロパティ値を受け取るまたは戻り値は。 これは、 `vtRet`によって指定される型と一致する必要があります。  
  
 `pbParamInfo`  
 `pbParamInfo`に従うパラメーターの型を指定するバイトの null で終わる文字列へのポインター。 使用可能な値は、「解説」セクションを参照して`COleDispatchDriver::InvokeHelper`です。  
  
 *...*  
 パラメーターで指定された型の変数一覧`pbParamInfo`です。  
  
### <a name="remarks"></a>コメント  
 `pbParamInfo` パラメーターは、メソッドまたはプロパティに渡されるパラメーターの型を指定します。 可変個引数リストとして表されます*しています.* 構文宣言でします。  
  
 この関数のパラメーターの変換**VARIANTARG**値、し、起動、 **idispatch::invoke** ActiveX コントロールのメソッドです。 場合に呼び出し**idispatch::invoke**失敗した場合、この関数には、例外がスローされます。 場合、 `SCODE` (状態コード) がによって返される**idispatch::invoke**は`DISP_E_EXCEPTION`、この関数のスロー、 [COleException](../../mfc/reference/coleexception-class.md)オブジェクトがスローされますが、それ以外の場合、 [COleDispatchException](../../mfc/reference/coledispatchexception-class.md)です。  
  
> [!NOTE]
>  この関数は、上でのみ呼び出す必要があります、 `CWnd` ActiveX コントロールを表すオブジェクト。  
  
 ActiveX コントロール コンテナーでこのメンバー関数を使用する方法の詳細については、記事を参照してください。 [ActiveX コントロール コンテナー: ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング](../../mfc/programming-activex-controls-in-a-activex-control-container.md)です。  
  
##  <a name="ischild"></a>  CWnd::IsChild  
 ウィンドウを指定するかどうかを示す`pWnd`が子ウィンドウか、別の直系の子孫の`CWnd`します。  
  
```  
BOOL IsChild(const CWnd* pWnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 テストするウィンドウを識別します。  
  
### <a name="return-value"></a>戻り値  
 関数の結果を指定します。 値は、ウィンドウがによって識別される場合は 0 以外`pWnd`の子ウィンドウは、 `CWnd`。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 子ウィンドウの直接の子孫である`CWnd`場合、`CWnd`オブジェクトが子ウィンドウを元のポップアップ ウィンドウから出ている親ウィンドウのチェインでします。  
  
##  <a name="isd2dsupportenabled"></a>  CWnd::IsD2DSupportEnabled  
 D2D のサポートが有効になっているかどうかを判断します。  
  
```  
BOOL IsD2DSupportEnabled();
```  
  
### <a name="return-value"></a>戻り値  
 この機能が有効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="isdialogmessage"></a>  CWnd::IsDialogMessage  
 指定されたメッセージがモードレス ダイアログ ボックスの目的として かどうかを決定するには、このメンバー関数を呼び出す場合は、この関数は、メッセージを処理します。  
  
```  
BOOL IsDialogMessage(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMsg`  
 指す、 [MSG](../../mfc/reference/msg-structure1.md)を確認するメッセージを含む構造体。  
  
### <a name="return-value"></a>戻り値  
 メンバー関数が指定されたメッセージを処理するかどうかを指定します。 メッセージが処理された場合は 0 以外それ以外の場合 0 を返します。 戻り値が 0 の場合は、呼び出し、 [cwnd::pretranslatemessage](#pretranslatemessage)メッセージを処理する基本クラスのメンバー関数。 オーバーライドで、`CWnd::PreTranslateMessage`メンバー関数は、次のようなコード。  
  
 [!code-cpp[NVC_MFCWindowing#100](../../mfc/reference/codesnippet/cpp/cwnd-class_40.cpp)]  
  
### <a name="remarks"></a>コメント  
 ときに、`IsDialogMessage`関数は、メッセージを処理することをチェック キーボード メッセージし、対応するダイアログ ボックスの選択コマンドに変換します。 たとえば、TAB キーは、[次へ] のコントロールまたはコントロールのグループを選択し、下矢印キーは、グループ内の次のコントロールを選択します。  
  
 によって処理されるメッセージを渡す必要がありますいない`IsDialogMessage`を[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)または[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)既に処理されているため、Windows の機能です。  
  
##  <a name="isdlgbuttonchecked"></a>  CWnd::IsDlgButtonChecked  
 ボタン コントロールの横のチェック マークかどうかを決定します。  
  
```  
UINT IsDlgButtonChecked(int nIDButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDButton`  
 ボタン コントロールの整数識別子を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定されたコントロールがオンになっている場合は 0 以外とチェックされていない場合は 0 です。 のみのラジオ ボタンおよびチェック ボックスをチェックすることができます。 3 つの状態のボタン、戻り値できます 2 場合は、ボタンが不定になります。 このメンバー関数は、プッシュ ボタンの場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、決定かどうか、淡色表示になり、チェックすると、ボタンが 3 つの状態コントロールの場合は、またはどちらもします。  
  
##  <a name="isdynamiclayoutenabled"></a>  CWnd::IsDynamicLayoutEnabled  
 このウィンドウで動的レイアウトが有効かどうかを判断します。 動的レイアウトが有効な場合は、ユーザーが親ウィンドウのサイズを変更したときに、子ウィンドウの位置とサイズを変更できます。  
  
```  
BOOL IsDynamicLayoutEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 動的レイアウトが有効である場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isiconic"></a>  CWnd::IsIconic  
 指定するかどうか`CWnd`が最小化 (アイコン化) します。  
  
```  
BOOL IsIconic() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`CWnd`最小限に抑えられます。 それ以外の場合に 0 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#101](../../mfc/reference/codesnippet/cpp/cwnd-class_41.cpp)]  
  
##  <a name="istouchwindow"></a>  CWnd::IsTouchWindow  
 `CWnd` でタッチ操作がサポートされているかどうかを示します。  
  
```  
BOOL IsTouchWindow() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合`CWnd`がタッチ操作がサポートされます。 それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="iswindowenabled"></a>  CWnd::IsWindowEnabled  
 指定するかどうか`CWnd`マウスおよびキーボード入力を有効にします。  
  
```  
BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`CWnd`が有効である場合は 0 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#102](../../mfc/reference/codesnippet/cpp/cwnd-class_42.cpp)]  
  
##  <a name="iswindowvisible"></a>  CWnd::IsWindowVisible  
 指定されたウィンドウの表示状態を判断します。  
  
```  
BOOL IsWindowVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`CWnd`が表示される (は、 [WS_VISIBLE](styles-used-by-mfc.md#window-styles)スタイル ビットが設定され、親ウィンドウが表示されます)。 戻り値の状態を反映するため、 **WS_VISIBLE**スタイル ビット戻り値可能性があります以外も`CWnd`が完全に他のウィンドウによって隠されます。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの所有によって示される可視性の状態、 **WS_VISIBLE**スタイル ビットです。 呼び出しにこのスタイルのビットを設定すると、 [ShowWindow](#showwindow)メンバー関数がウィンドウが表示され、ウィンドウはスタイル ビットが設定されている限り、後続の描画をウィンドウが表示されます。  
  
 あるウィンドウへのあらゆる描画、 **WS_VISIBLE**スタイルが表示されない場合、ウィンドウの他のウィンドウでカバーされるまたは、親ウィンドウによってクリップします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#103](../../mfc/reference/codesnippet/cpp/cwnd-class_43.cpp)]  
  
##  <a name="iszoomed"></a>  CWnd::IsZoomed  
 決定するかどうか`CWnd`最大表示されています。  
  
```  
BOOL IsZoomed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`CWnd`が最大化します。 それ以外の場合に 0 です。  
  
##  <a name="killtimer"></a>  メイン フレーム ウィンドウ  
 によって識別されるタイマー イベントを強制終了`nIDEvent`以前の呼び出しから`SetTimer`です。  
  
```  
BOOL KillTimer(UINT_PTR nIDEvent);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDEvent`  
 タイマー イベントの値が渡される[SetTimer](#settimer)です。  
  
### <a name="return-value"></a>戻り値  
 関数の結果を指定します。 値は、イベントが取り消された場合は 0 以外です。 場合は 0、`KillTimer`メンバー関数は、指定されたタイマー イベントが見つかりませんでした。  
  
### <a name="remarks"></a>コメント  
 保留中[WM_TIMER](#ontimer)タイマーに関連付けられたメッセージは、メッセージ キューから削除されません。  
  
### <a name="example"></a>例  
  例を参照して[で](#settimer)です。  
  
##  <a name="loaddynamiclayoutresource"></a>  CWnd::LoadDynamicLayoutResource  
 リソース ファイルから動的レイアウト情報を読み込むために、フレームワークによって呼び出されます。  
  
```  
BOOL LoadDynamicLayoutResource(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 このウィンドウの目的の動的レイアウト情報が含まれているリソースの名前。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。 エラーが発生した場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを直接呼び出さないでください。  
  
##  <a name="lockwindowupdate"></a>  CWnd::LockWindowUpdate  
 指定されたウィンドウでの描画を無効にします。  
  
```  
BOOL LockWindowUpdate();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。 障害が発生した場合、または場合は 0、`LockWindowUpdate`別のウィンドウをロックする関数が使用されています。  
  
### <a name="remarks"></a>コメント  
 ロックされたウィンドウを移動することはできません。 一度に 1 つのウィンドウをロックできます。 ロックがウィンドウのロックを解除する`LockWindowUpdate`、呼び出す[UnlockWindowUpdate](#unlockwindowupdate)です。  
  
 場合、ロックされたウィンドウ (または、ロックされている子ウィンドウ) でアプリケーションの呼び出し、 [GetDC、](http://msdn.microsoft.com/library/windows/desktop/dd144871) [GetDCEx、](http://msdn.microsoft.com/library/windows/desktop/dd144873)または[BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362) Windows 関数は、呼び出された関数がデバイスを返します。コンテキストの可視領域が空です。 これは、アプリケーションを呼び出して、ウィンドウのロックを解除するまで、発生、`UnlockWindowUpdate`メンバー関数。  
  
 ウィンドウの更新がロックされているときに、システムの追跡の描画操作ロックされたウィンドウに関連付けられているデバイス コンテキストへの外接する四角形。 描画が再度有効に、この外接する四角形がロックされているウィンドウとその子ウィンドウを強制的に無効化[WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)画面を更新するメッセージ。 描画発生していない場合、ウィンドウが更新されたロック中に、領域は無効です。  
  
 `LockWindowUpdate`メンバー関数は行いません指定されたウィンドウ非表示とはクリアされません、 [WS_VISIBLE](styles-used-by-mfc.md#window-styles)スタイル ビットです。  
  
##  <a name="m_hwnd"></a>  CWnd::m_hWnd  
 これに接続されている Windows のウィンドウのハンドル`CWnd`です。  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hWnd`データ メンバーは型のパブリック変数`HWND`です。  
  
##  <a name="mapwindowpoints"></a>  CWnd::MapWindowPoints  
 複数の点を `CWnd` の座標空間から他のウィンドウの座標空間へ変換 (マップ) します。  
  
```  
void MapWindowPoints(
    CWnd* pwndTo,  
    LPRECT lpRect) const;  
  
void MapWindowPoints(
    CWnd* pwndTo,  
    LPPOINT lpPoint,  
    UINT nCount) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pwndTo*  
 ポイントが変換されるウィンドウを識別します。 このパラメーターが場合**NULL**点を画面座標に変換されます。  
  
 `lpRect`  
 変換する点を持つは、四角形を指定します。 この関数の最初のバージョンは、および後で Windows 3.1 に対してのみ使用できます。  
  
 `lpPoint`  
 配列へのポインター [POINT 構造体](../../mfc/reference/point-structure1.md)変換する点のセットが含まれています。  
  
 `nCount`  
 数を指定**ポイント**配列内の構造体を指す`lpPoint`です。  
  
##  <a name="messagebox"></a>  CWnd::MessageBox  
 作成し、アプリケーションによって提供されるメッセージ、キャプション、および定義済みのアイコンと」に記載のプッシュ ボタンの組み合わせを含んでいるウィンドウを表示、[メッセージ ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#message-box-styles) ボックスの一覧です。  
  
```  
int MessageBox(
    LPCTSTR lpszText,  
    LPCTSTR lpszCaption = NULL,  
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 指す、`CString`オブジェクトまたは null で終わる文字列を含むメッセージが表示されます。  
  
 `lpszCaption`  
 指す、`CString`オブジェクトまたはメッセージ ボックスのキャプションに使用する null で終わる文字列。 場合`lpszCaption`は**NULL**、「エラー」が使用される既定のキャプション。  
  
 `nType`  
 メッセージ ボックスの動作と内容を指定します。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは、 [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) Windows SDK で定義されているとおりに機能します。 このメソッドは、この関数の呼び出しの結果を返します。  
  
### <a name="remarks"></a>コメント  
 グローバル関数を使用して[AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox)アプリケーションでメッセージ ボックスを実装するには、このメンバー関数の代わりにします。  
  
 メッセージ ボックスに使用できるさまざまなシステムのアイコンを次に示します。  
  
|||  
|-|-|  
|![停止&#40;x&#41;アイコン](../../mfc/reference/media/vc364f1.gif "vc364f1")|**MB_ICONHAND**、 **MB_ICONSTOP**、および**MB_ICONERROR**|  
|![ヘルプ&#40;&#41;アイコン](../../mfc/reference/media/vc364f2.gif "vc364f2")|**MB_ICONQUESTION**|  
|![重要な&#40; &#33; &#41;アイコン](../../mfc/reference/media/vc364f3.gif "vc364f3")|**MB_ICONEXCLAMATION**と**MB_ICONWARNING**|  
|![情報&#40;すれば&#41;アイコン](../../mfc/reference/media/vc364f4.gif "vc364f4")|**MB_ICONASTERISK**と**MB_ICONINFORMATION**|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#104](../../mfc/reference/codesnippet/cpp/cwnd-class_44.cpp)]  
  
##  <a name="modifystyle"></a>  CWnd::ModifyStyle  
 ウィンドウのスタイルを変更するには、このメンバー関数を呼び出します。  
  
```  
BOOL ModifyStyle(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwRemove`  
 スタイルの変更時に削除するウィンドウのスタイルを指定します。  
  
 `dwAdd`  
 スタイルの変更時に追加するウィンドウのスタイルを指定します。  
  
 `nFlags`  
 渡されるフラグ[SetWindowPos](#setwindowpos)、または場合は 0`SetWindowPos`呼び出すことはできません。 既定値は 0 です。 事前設定されたフラグの一覧については、「解説」セクションを参照してください。  
  
### <a name="return-value"></a>戻り値  
 スタイルの変更が成功した場合は 0 以外。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 ビットごとの OR を使用してスタイルを追加または削除を組み合わせることができます (&#124;) 演算子。 トピックを参照して[ウィンドウ スタイル](http://msdn.microsoft.com/library/windows/desktop/ms632600)と[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)について使用可能なウィンドウのスタイルは Windows SDK に含まれています。  
  
 場合`nFlags`がゼロ以外、 `ModifyStyle` Windows API 関数を呼び出す[SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545)し、結合することで、ウィンドウを再描画`nFlags`の次の 4 つの事前設定されたフラグを使用。  
  
- `SWP_NOSIZE` 現在のサイズを保持します。  
  
- `SWP_NOMOVE` 現在の位置を保持します。  
  
- `SWP_NOZORDER` 現在の Z オーダーを保持します。  
  
- `SWP_NOACTIVATE` ウィンドウをアクティブにしません。  
  
 拡張スタイルにウィンドウを変更しを参照してください[は](#modifystyleex)します。  
  
> [!NOTE]
>  内の特定のコントロールのスタイル (、 **ES_READONLY**エディット コントロールのスタイルをなど)、**は**が正しくので変更できませんスタイル コントロールは、特殊な内部を実行する必要があります処理しています。 このような場合は、スタイルを変更する、対応するメッセージがあります ( **EM_SETREADONLY**記載されている例では)。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#105](../../mfc/reference/codesnippet/cpp/cwnd-class_45.cpp)]  
  
##  <a name="modifystyleex"></a>  CWnd::ModifyStyleEx  
 ウィンドウの拡張スタイルを変更するには、このメンバー関数を呼び出します。  
  
```  
BOOL ModifyStyleEx(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwRemove`  
 スタイルの変更時に削除する拡張スタイルを指定します。  
  
 `dwAdd`  
 スタイルの変更時に追加する拡張スタイルを指定します。  
  
 `nFlags`  
 渡されるフラグ[SetWindowPos](#setwindowpos)、または場合は 0`SetWindowPos`呼び出すことはできません。 既定値は 0 です。 事前設定されたフラグの一覧については、「解説」セクションを参照してください。  
  
### <a name="return-value"></a>戻り値  
 スタイルの変更が成功した場合は 0 以外。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 ビットごとの OR を使用してスタイルを追加または削除を組み合わせることができます (&#124;) 演算子。 トピックを参照して[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)本書でと[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)については、使用可能な Windows SDK では、拡張スタイル  
  
 場合`nFlags`がゼロ以外、 `ModifyStyleEx` Windows API 関数を呼び出す[SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545)し、結合することで、ウィンドウを再描画`nFlags`の次の 4 つの事前設定されたフラグを使用。  
  
- `SWP_NOSIZE` 現在のサイズを保持します。  
  
- `SWP_NOMOVE` 現在の位置を保持します。  
  
- `SWP_NOZORDER` 現在の Z オーダーを保持します。  
  
- `SWP_NOACTIVATE` ウィンドウをアクティブにしません。  
  
 通常のウィンドウ スタイルを使用して windows を変更するを参照してください。[は](#modifystyle)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#106](../../mfc/reference/codesnippet/cpp/cwnd-class_46.cpp)]  
  
##  <a name="movewindow"></a>  CWnd::MoveWindow  
 位置とサイズを変更します。  
  
```  
void MoveWindow(
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    BOOL bRepaint = TRUE);

 
void MoveWindow(
    LPCRECT lpRect,
    BOOL bRepaint = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左側の新しい位置を示す、`CWnd`です。  
  
 *y*  
 一番上の新しい位置を示す、`CWnd`です。  
  
 `nWidth`  
 新しい幅を指定します、`CWnd`です。  
  
 `nHeight`  
 新しい高さを指定、`CWnd`です。  
  
 `bRepaint`  
 指定するかどうか`CWnd`に再描画されます。 場合**TRUE**、`CWnd`を受け取る、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)でメッセージの[OnPaint](#onpaint)メッセージ ハンドラーは通常どおりです。 このパラメーターが場合**FALSE**、任意の種類の再描画するは行われません。 これは、クライアント領域に、(タイトルやスクロール バーを含む)、非クライアント領域、および対象の結果として検出された親ウィンドウの任意の部分に`CWnd`に移動します。 このパラメーターが場合**FALSE**、アプリケーションの無効にしたりの任意の部分を再描画する必要があります明示的に`CWnd`と親ウィンドウに再描画する必要があります。  
  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)新しいサイズと位置を指定します。  
  
### <a name="remarks"></a>コメント  
 最上位の`CWnd`オブジェクト、 *x*と*y*パラメーターは、画面の左上隅に対する相対パスです。 子の`CWnd`オブジェクトの親ウィンドウのクライアント領域の左上隅に対して相対的にします。  
  
 `MoveWindow`関数の送信、 [WM_GETMINMAXINFO](#ongetminmaxinfo)メッセージ。 このメッセージの処理は、`CWnd`最大および最小の windows の既定値を変更することです。 場合のパラメーター、`MoveWindow`メンバー関数は、これらの値を超える、値は最小値または最大値で置き換えることが、`WM_GETMINMAXINFO`ハンドラー。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::ClientToScreen](#clienttoscreen)です。  
  
##  <a name="notifywinevent"></a>  CWnd::NotifyWinEvent  
 定義済みイベントが発生したことをシステムに通知します。 クライアント アプリケーションはすべてのイベントのフック関数を登録すると、システムは、クライアントのフック関数を呼び出します。  
  
```  
void NotifyWinEvent(
    DWORD event,  
    LONG idObjectType,  
    LONG idObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `event`  
 発生したイベントを指定します。 この値は、のいずれかを指定する必要があります、[イベント定数](http://msdn.microsoft.com/library/windows/desktop/dd318066)です。  
  
 *idObjectType*  
 イベントを生成したオブジェクトの種類を識別します。 この値は、定義済みの 1 つ[オブジェクトの識別子](http://msdn.microsoft.com/library/windows/desktop/dd373606)またはカスタム オブジェクトの ID 値です。  
  
 `idObject`  
 オブジェクトまたはオブジェクトの子要素によってイベントが生成されたかどうかを識別します。 この値が場合**CHILDID_SELF**イベントは、オブジェクト自体によって生成されました。 それ以外の場合は、この値は、イベントを生成した要素の子の ID。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[NotifyWinEvent](http://msdn.microsoft.com/library/windows/desktop/dd373603)Windows SDK で説明されている。  
  
##  <a name="onactivate"></a>  CWnd::OnActivate  
 フレームワークはこのメンバー関数を呼び出すときに、`CWnd`は対象のオブジェクトがアクティブまたは非アクティブ化します。  
  
```  
afx_msg void OnActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>パラメーター  
 `nState`  
 指定するかどうか、`CWnd`がアクティブまたは非アクティブ化します。 次の値のいずれかを指定できます。  
  
- **WA_INACTIVE**ウィンドウを非アクティブ化します。  
  
- **WA_ACTIVE**ウィンドウがアクティブ化されているいくつかの方法で (たとえば、ウィンドウを選択するキーボード インターフェイスの使用) して、マウスのクリックしてではないです。  
  
- **WA_CLICKACTIVE**ウィンドウをマウスのクリックによってアクティブ化します。  
  
 *pWndOther*  
 ポインター、`CWnd`アクティブまたは非アクティブ化します。 マウス ポインターを指定できます**NULL**、一時的な可能性があるとします。  
  
 *bMinimized*  
 最小化された状態を指定します、`CWnd`アクティブまたは非アクティブ化します。 値**TRUE**ウィンドウが最小化することを示します。  
  
 場合**TRUE**、`CWnd`をアクティブ化します。 それ以外の場合に非アクティブ化します。  
  
### <a name="remarks"></a>コメント  
 場合、`CWnd`オブジェクトは、マウスのクリックでアクティブ化も受け取ります、 [OnMouseActivate](#onmouseactivate)メンバー関数の呼び出しです。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onactivateapp"></a>  CWnd::OnActivateApp  
 フレームワークとの非アクティブ化タスクのすべてのトップ レベル ウィンドウに対してアクティブ化されているタスクのすべての最上位ウィンドウにこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnActivateApp(
    BOOL bActive,  
    DWORD dwThreadID);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActive`  
 指定するかどうか、`CWnd`がアクティブまたは非アクティブ化します。 **TRUE**意味、`CWnd`をアクティブ化します。 **FALSE**意味、`CWnd`を非アクティブ化します。  
  
 *dwThreadID*  
 スレッド ID の値を指定します 場合`bActive`は**TRUE**、 *dwThreadID*を所有するスレッドを識別、`CWnd`の非アクティブ化します。 場合`bActive`は**FALSE**、 *dwThreadID*を所有するスレッドを識別、`CWnd`アクティブ化します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onambientproperty"></a>  CWnd::OnAmbientProperty  
 フレームワークは、OLE コントロールを含むウィンドウからアンビエント プロパティの値を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL OnAmbientProperty(
    COleControlSite* pSite,  
    DISPID dispid,  
    VARIANT* pvar);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSite`  
 アンビエント プロパティを要求したコントロールのサイトへのポインター。  
  
 `dispid`  
 要求されたアンビエント プロパティのディスパッチ ID。  
  
 `pvar`  
 呼び出し元が割り当てたへのポインター`VARIANT`をアンビエント プロパティの値を返される構造体します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、アンビエント プロパティがサポートされています。**FALSE**しない場合。  
  
### <a name="remarks"></a>コメント  
 アンビエント プロパティの値がそのコントロールを OLE コントロール コンテナーによって返される既定値を変更するには、この関数をオーバーライドします。 オーバーライド関数で処理されない任意のアンビエント プロパティ要求は、基本クラスの実装に転送する必要があります。  
  
##  <a name="onappcommand"></a>  CWnd::OnAppCommand  
 ユーザーがアプリケーション コマンド イベントを生成するときに、フレームワークはこのメンバー関数を呼び出します。 このようなイベントは、ユーザーがアプリケーション コマンド ボタンまたは型アプリケーション コマンド キーに発生します。  
  
```  
afx_msg void OnAppCommand(
    CWnd* pWnd,  
    UINT nCmd,  
    UINT nDevice,  
    UINT nKey);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pWnd`|ポインター、`CWnd`をユーザーが押したり をクリックします。 または、コマンド キーを押してウィンドウを表すオブジェクト。 このウィンドウは、メッセージの受信ウィンドウの子ウィンドウであることができます。|  
|[入力] `nCmd`|アプリケーション コマンドを示します。 使用可能な値の一覧は、下にあるコマンドを参照してください、 *cmd*のセクションで、`lParam`のパラメーター [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275)です。|  
|[入力] `nDevice`|入力イベントを生成する入力デバイス。 使用可能な値の一覧は、下にあるデバイスを参照してください、 *uDevice*のセクションで、`lParam`のパラメーター [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275)です。|  
|[入力] `nKey`|CTRL キーまたはマウスの左ボタンなど、ダウンしているすべての仮想キーを示します。 使用可能な値の一覧は、下のキーを参照してください、 *dwKeys*のセクションで、`lParam`のパラメーター [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275)です。 詳細についてを参照してくださいで「メッセージのパラメーター」subheading[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)です。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_APPCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646275)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onaskcbformatname"></a>  CWnd::OnAskCbFormatName  
 クリップボードにデータへのハンドルが含まれている場合、フレームワークがこのメンバー関数を呼び出す、 `CF_OWNERDISPLAY` (つまり、ときに、クリップボード所有者クリップボードの内容が表示されます) を書式設定します。  
  
```  
afx_msg void OnAskCbFormatName(
    UINT nMaxCount,  
    LPTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMaxCount`  
 コピーするバイトの最大数を指定します。  
  
 `lpszString`  
 形式名のコピーを格納するバッファーへのポインター。  
  
### <a name="remarks"></a>コメント  
 クリップボード所有者は、その形式の名前を指定する必要があります。  
  
 このメンバー関数をオーバーライドし、コピーの名前、`CF_OWNERDISPLAY`指定されたバイト数の最大数を超えない、指定されたバッファーに書式設定します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oncancelmode"></a>  CWnd::OnCancelMode  
 フレームワークに通知するには、このメンバー関数を呼び出します`CWnd`内部モードをキャンセルします。  
  
```  
afx_msg void OnCancelMode();
```  
  
### <a name="remarks"></a>コメント  
 場合、`CWnd`オブジェクトにフォーカスをその`OnCancelMode` ダイアログ ボックスまたはメッセージ ボックスが表示されるときに、メンバー関数が呼び出されます。 これにより、`CWnd`など、マウスのキャプチャ モードをキャンセルすることです。  
  
 既定の実装を呼び出すことによって応答、 [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261) Windows の機能です。 その他のモードを処理する、派生クラスでこのメンバー関数をオーバーライドします。  
  
##  <a name="oncapturechanged"></a>  CWnd::OnCaptureChanged  
 フレームワークがマウス キャプチャを失うウィンドウに通知するには、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnCaptureChanged(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 マウスのキャプチャを取得するためにウィンドウへのポインター  
  
### <a name="remarks"></a>コメント  
 呼び出す場合でも、ウィンドウがこのメッセージを受け取る[ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261)自体です。 アプリケーションがこのメッセージに応答でマウスのキャプチャを設定しないようにします。 このメッセージを受信したときに、ウィンドウ自体を再描画、必要に応じて、新しいマウス キャプチャ状態を反映するようにします。  
  
 情報の Windows SDK を参照してください、 `ReleaseCapture` Windows の機能です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onchangecbchain"></a>  CWnd::OnChangeCbChain  
 フレームワークは、各ウィンドウのウィンドウをチェーンから削除してに通知するクリップボード ビューアーのチェインでこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnChangeCbChain(
    HWND hWndRemove,  
    HWND hWndAfter);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndRemove`  
 クリップボード ビューアーのチェインから削除されるウィンドウ ハンドルを指定します。  
  
 `hWndAfter`  
 クリップボード ビューアーのチェインから削除されているウィンドウの次のウィンドウ ハンドルを指定します。  
  
### <a name="remarks"></a>コメント  
 各`CWnd`を受け取るオブジェクト、`OnChangeCbChain`呼び出しを使用する必要があります、 [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950)を送信する Windows の機能、 [WM_CHANGECBCHAIN](http://msdn.microsoft.com/library/windows/desktop/ms649019)クリップボード ビューアーに次のウィンドウにメッセージチェーン (によって返されたハンドル`SetClipboardViewer`)。 場合`hWndRemove`で指定されたウィンドウのチェーン内の次のウィンドウ`hWndAfter`次のウィンドウになり、クリップボードのメッセージは、に渡されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onchangeuistate"></a>  CWnd::OnChangeUIState  
 ユーザー インターフェイス (UI) 状態を変更する必要があるときに呼び出されます。  
  
```  
afx_msg void OnChangeUIState(
    UINT nAction,  
    UINT nUIElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAction`  
 実行するアクションを指定します。 次のいずれかの値になります。  
  
- **UIS_CLEAR** UI 状態要素 (で指定した`nUIElement`) 非表示にする必要があります。  
  
- **UIS_INITIALIZE** UI 状態要素 (で指定した`nUIElement`) 最後の入力イベントに基づいて変更する必要があります。 詳細については、次を参照してください。、**解説**のセクション[WM_CHANGEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646342)です。  
  
- **UIS_SET** UI 状態要素 (で指定した`nUIElement`) が表示されます。  
  
 `nUIElement`  
 UI 状態の要素が影響を受けるか、コントロールのスタイルを指定します。 次のいずれかの値になります。  
  
- **UISF_HIDEACCEL**キーボード アクセラレータです。  
  
- **UISF_HIDEFOCUS**インジケーターに注目します。  
  
- **UISF_ACTIVE Windows XP:** コントロールは、アクティブなコントロールで使用されるスタイルで描画する必要があります。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [WM_CHANGEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646342)メッセージ、Windows SDK で説明します。  
  
##  <a name="onchar"></a>  CWnd::OnChar  
 キーストロークが非システム文字に変換されるときに、フレームワークはこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnChar(
    UINT nChar,  
    UINT nRepCnt,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 キーの文字のコード値が含まれています。  
  
 `nRepCnt`  
 繰り返し回数、キーを押したときに、キーストロークが繰り返される回数が含まれています。  
  
 `nFlags`  
 次の一覧に示すようにスキャン コード、キー遷移コード、前のキーの状態、およびコンテキストのコードが含まれています。  
  
|[値]|説明|  
|-----------|-------------|  
|0-15|繰り返し回数を指定します。 値は、キーを押しながら、ユーザーの結果として、キーストロークが繰り返される回数です。|  
|16-23|スキャン コードを指定します。 値は、製造元 (OEM) によって異なります。|  
|24|キーが拡張 101 または 102 key キーボードに表示される右 ALT および CTRL キーなどの拡張キーであるかどうかを指定します。 拡張キーである場合、値は 1それ以外の場合は 0 です。|  
|25-28|Windows によって内部的に使用します。|  
|29|コンテキストのコードを指定します。 ALT キーを押した状態でキーを押した場合、値は 1それ以外の場合、値は 0 です。|  
|30|以前のキーの状態を指定します。 メッセージを送信すると、またはキーが稼働している場合は 0 を前に、キーがダウンした場合、値は 1 です。|  
|31|遷移の状態を指定します。 場合は、キーが離されたされている、または押されている場合は 0 を値は 1 です。|  
  
### <a name="remarks"></a>コメント  
 この関数は、前に呼び出されます、 [OnKeyUp](#onkeyup)メンバー関数と後、 [OnKeyDown](#onkeydown)メンバー関数が呼び出されます。 `OnChar` キーボードのキーが押されたまたはリリースの値が含まれています。  
  
 ないため必ずしも 1 対 1 の対応間押されたキーと`OnChar`の呼び出しの生成の情報は、`nFlags`は通常、アプリケーションに役に立ちません。 情報は、`nFlags`を最新の呼び出しにのみ適用されます、`OnKeyUp`メンバー関数または`OnKeyDown`メンバー関数への呼び出しの前にある`OnChar`です。  
  
 IBM エンハンス 101 および 102 key キーボード、強化されたキーには右 ALT および右 CTRL キーを押し、キーボードのメイン セクションにアドイン、DEL、HOME、END、PAGEUP、PAGEDOWN、および; テンキーの左側に、クラスター内の矢印キースラッシュ (/) およびテンキーで ENTER キー。 その他の一部のキーボード可能性があります、拡張キー ビット サポートで`nFlags`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onchartoitem"></a>  CWnd::OnCharToItem  
 リスト ボックスときに呼び出されます、 [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルの所有者に送信する[WM_CHARTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761358)への応答メッセージ、 [WM_CHAR](#onchar)メッセージ。  
  
```  
afx_msg int OnCharToItem(
    UINT nChar,  
    CListBox* pListBox,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 ユーザーによって押されたキーの値を指定します。  
  
 `pListBox`  
 リスト ボックスへのポインターを指定します。 一時的な場合があります。  
  
 `nIndex`  
 現在のカレット位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 フレームワークは、アプリケーションの呼び出しに応答して実行するアクションを指定するには、このメンバー関数を呼び出します。 戻り値が-2 は、アプリケーションが項目の選択のすべての側面を処理し、リスト ボックスで、これ以上の操作を必要としないことを示します。 戻り値-1 は、キー操作への応答に、リスト ボックスが既定のアクションを実行することを示します。 0 以上の戻り値は、リスト ボックスで、項目の 0 から始まるインデックスを指定し、リスト ボックスがで指定したアイテムのキーストロークの既定のアクションを実行する必要がありますを示します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onchildactivate"></a>  CWnd::OnChildActivate  
 場合、`CWnd`オブジェクトは、複数ドキュメント インターフェイス (MDI) 子ウィンドウ`OnChildActivate`は、ユーザーがウィンドウのタイトル バーをクリックしたときに、フレームワークによって呼び出されますまたはウィンドウがアクティブな場合、移動またはサイズが変更されます。  
  
```  
afx_msg void OnChildActivate();
```  
  
##  <a name="onchildnotify"></a>  CWnd::OnChildNotify  
 このメンバー関数は、このウィンドウに適用される通知メッセージを受信したときに、このウィンドウの親ウィンドウによって呼び出されます。  
  
```  
virtual BOOL OnChildNotify(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 親ウィンドウに送信する Windows メッセージ番号。  
  
 `wParam`  
 **Wparam**メッセージに関連付けられています。  
  
 `lParam`  
 **Lparam**メッセージに関連付けられています。  
  
 `pLResult`  
 親のウィンドウ プロシージャから返される値へのポインター。 このポインター **NULL**場合、戻り値が予期されていません。  
  
### <a name="return-value"></a>戻り値  
 このウィンドウはその親に送信されるメッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を直接呼び出すことはありません。  
  
 このメンバー関数の既定の実装では、親が、メッセージを処理することを意味する 0 を返します。  
  
 コントロール通知メッセージに応答するように拡張するには、このメンバー関数をオーバーライドします。  
  
##  <a name="onclipboardupdate"></a>  CWnd::OnClipboardUpdate  
 フレームワークは、クリップボードの内容が変更されたときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnClipboardUpdate();
```  
  
##  <a name="onclose"></a>  CWnd::OnClose  
 シグナルとして、フレームワークがこのメンバー関数を呼び出す、`CWnd`またはアプリケーションが終了にします。  
  
```  
afx_msg void OnClose();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装`DestroyWindow`です。  
  
##  <a name="oncolorizationcolorchanged"></a>  CWnd::OnColorizationColorChanged  
 フレームワークは、非クライアント領域のレンダリングのポリシーが変更されたときに、このメンバーを呼び出します。  
  
```  
afx_msg void OnColorizationColorChanged(
    DWORD dwColorizationColor,   
    BOOL bOpacity);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwColorizationColor`|新しい彩色の色を指定します。<br /><br /> 色の書式は、4 つのコンポーネントの各範囲 0x00 ~ 0 xff フォーム 0xAARRGGBB の 16 進数です。 AA コンポーネントは、アルファ値、RR は色が赤、GG が緑、および BB は青で表示します。|  
|[入力] `bOpacity`|`true` 不透明度; に新しい色を適用する場合`false`されていない場合。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_DWMNCRENDERINGCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388198)通知メッセージは、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oncommand"></a>  CWnd::OnCommand  
 子コントロールは、通知メッセージを送信するとき、またはアクセラレータのキーストロークを変換するとき、ユーザーが、メニューから項目を選択すると、フレームワークはこのメンバー関数を呼び出します。  
  
```  
virtual BOOL OnCommand(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `wParam`  
 下位ワード`wParam`メニュー項目、コントロール、またはアクセラレータのコマンド ID を識別します。 上位ワード`wParam`場合は、メッセージがコントロールから通知メッセージを指定します。 メッセージは、アクセラレータからは、上位ワードは 1 です。 メニューからのメッセージの場合は、上位ワードは 0 です。  
  
 `lParam`  
 メッセージがコントロールからの場合は、メッセージを送信するコントロールを識別します。 それ以外の場合、`lParam`は 0 です。  
  
### <a name="return-value"></a>戻り値  
 アプリケーションがこのメッセージを処理する場合は 0 以外を返しますそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `OnCommand` コントロールの通知のメッセージ マップを処理し、`ON_COMMAND`エントリ、適切なメンバー関数を呼び出します。  
  
 このメンバー関数を処理する派生クラスでオーバーライド、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージ。 上書きがないメッセージ マップが処理しない限り、基本クラス`OnCommand`と呼びます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oncompacting"></a>  CWnd::OnCompacting  
 フレームワークは、メモリを圧縮すること、30 から 60 秒間隔でのシステム時刻の 12.5% 以上を要していることを検出したときに、すべてのトップ レベル ウィンドウに対してこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnCompacting(UINT nCpuTime);
```  
  
### <a name="parameters"></a>パラメーター  
 *nCpuTime*  
 現在 Windows CPU 時間に対する圧縮のメモリは、その他の操作の実行に費やさによって費やされた CPU 時間の比率を指定します。 たとえば、8000 h では、CPU 時間の圧縮メモリの 50% を表します。  
  
### <a name="remarks"></a>コメント  
 これは、システム メモリが不足していることを示します。  
  
 ときに、`CWnd`オブジェクトはこの呼び出しを受け取る、そのアプリケーションと Windows で実行されているアプリケーションの合計数のアクティビティの現在のレベルを考慮に入れて、可能な量のメモリを解放する必要があります。 アプリケーションでは、実行しているアプリケーションの数を決定する Windows 関数を呼び出すことができます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oncompareitem"></a>  CWnd::OnCompareItem  
 フレームワークは、並べ替えられたオーナー描画コンボ ボックスまたはリスト ボックスで、新しい項目の相対位置を指定するには、このメンバー関数を呼び出します。  
  
```  
afx_msg int OnCompareItem(
    int nIDCtl,  
    LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDCtl`  
 送信したコントロールの識別子、`WM_COMPAREITEM`メッセージ。  
  
 `lpCompareItemStruct`  
 Long ポインターが含まれています、 [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md)識別子と、コンボ ボックスまたはリスト ボックス内の 2 つの項目のアプリケーションによって提供されるデータを格納するデータ構造です。  
  
### <a name="return-value"></a>戻り値  
 2 つのアイテムの相対位置を示します。 次の値のいずれかがある可能性があります。  
  
|[値]|説明|  
|-----------|-------------|  
|-1|項目 1 は項目 2 の前に並べ替えます。|  
|0|アイテム 1 と 2 のアイテムは、同じを並べ替えます。|  
|1|項目 1 は項目 2 の後に並べ替えられます。|  
  
### <a name="remarks"></a>コメント  
 コンボ ボックスまたはリスト ボックスが作成された場合、 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル、Windows の送信、コンボ ボックスまたはリスト ボックスの所有者、`WM_COMPAREITEM`メッセージのアプリケーションは、新しい項目を追加するたびにします。  
  
 コンボ ボックスまたはリスト ボックス内の 2 つの項目が再形成、`COMPAREITEMSTRUCT`構造体を指す`lpCompareItemStruct`です。 `OnCompareItem` 前に、他の表示の項目を示す値を返す必要があります。 通常、Windows では、この呼び出し何回か判断する、新しい項目の正確な位置までです。  
  
 場合、 **hwndItem**のメンバー、`COMPAREITEMSTRUCT`構造が属する、 [CListBox](../../mfc/reference/clistbox-class.md)または[CComboBox](../../mfc/reference/ccombobox-class.md)オブジェクト、`CompareItem`の仮想関数、適切なクラスが呼び出されます。 オーバーライド`CComboBox::CompareItem`または`CListBox::CompareItem`、派生で`CListBox`または`CComboBox`項目の比較を実行するクラス。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oncompositionchanged"></a>  CWnd::OnCompositionChanged  
 フレームワークは、デスクトップ ウィンドウ マネージャー (DWM) コンポジションを有効または無効になっているときに、すべてのトップ レベル ウィンドウに対してこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnCompositionChanged();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_DWMCOMPOSITIONCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388199)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oncontextmenu"></a>  CWnd::OnContextMenu  
 ユーザーがウィンドウで (右クリック)、マウスの右ボタンをクリックしたときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnContextMenu(
    CWnd* pWnd,  
    CPoint pos);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ユーザーがマウスをクリックして右ウィンドウへのハンドルします。 メッセージの受信ウィンドウの子ウィンドウを指定できます。 このメッセージの処理の詳細については、「解説」セクションを参照してください。  
  
 `pos`  
 画面座標時、マウスのカーソルの位置をクリックします。  
  
### <a name="remarks"></a>コメント  
 使用してコンテキスト メニューを表示することによってこのメッセージを処理することができます、 [TrackPopupMenu](../../mfc/reference/cmenu-class.md#trackpopupmenu)です。  
  
 コンテキスト メニューが表示されない場合に、このメッセージを渡す必要があります、 [DefWindowProc](#defwindowproc)関数。 場合は、ウィンドウは、子ウィンドウ、`DefWindowProc`親にメッセージを送信します。 それ以外の場合、`DefWindowProc`ウィンドウのキャプションが指定した位置の場合、既定のコンテキスト メニューが表示されます。  
  
##  <a name="oncopydata"></a>  CWnd::OnCopyData  
 このメンバー関数は、別の 1 つのアプリケーションからデータをコピーするためにフレームワークによって呼び出されます。  
  
```  
afx_msg BOOL OnCopyData(
    CWnd* pWnd,  
    COPYDATASTRUCT* pCopyDataStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ポインター、`CWnd`データを送信しているオブジェクト。  
  
 `pCopyDataStruct`  
 ポインター、 [COPYDATASTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms649010)送信されるデータを格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**受信側のアプリケーションが正常にデータを受け入れる場合。 返しますそれ以外の場合、 **FALSE**です。  
  
### <a name="remarks"></a>コメント  
 ポインターまたは他の参照データを受信するアプリケーションにアクセスできないオブジェクトを渡されるデータを含めないでください。  
  
 データのコピー中に、送信プロセスの別のスレッドによって変更されません必要があります。  
  
 読み取り専用では、受信側のアプリケーションがデータを検討してください。 構造体が、パラメーターが指す`pCopyDataStruct`が有効ではデータの転送中にのみただし、受信側のアプリケーションは、構造に関連付けられているメモリを解放する必要があります。  
  
 受信側のアプリケーションは、この関数が返された後に、データへのアクセスを必要とする場合は、ローカル バッファーを受信したデータをコピーが必要があります。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oncreate"></a>  CWnd::OnCreate  
 アプリケーションが呼び出すことによって、Windows のウィンドウを作成することを要求したときに、フレームワークがこのメンバー関数を呼び出す、[作成](#create)または[CreateEx](#createex)メンバー関数。  
  
```  
afx_msg int OnCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCreateStruct`  
 指す、 [CREATESTRUCT](../../mfc/reference/createstruct-structure.md)に関する情報を格納する構造体、`CWnd`オブジェクトの作成中です。  
  
### <a name="return-value"></a>戻り値  
 `OnCreate` 作成を続行する場合は 0 を返す必要があります、`CWnd`オブジェクト。 アプリケーションでは、-1 が返された場合は、ウィンドウが破棄されます。  
  
### <a name="remarks"></a>コメント  
 `CWnd`ウィンドウの作成後は、表示になるまでに、オブジェクトがこの呼び出しを受け取ります。 `OnCreate` 前に呼び出されます、**作成**または`CreateEx`メンバー関数を返します。  
  
 派生クラスの必要な初期化を実行するには、このメンバー関数をオーバーライドします。  
  
 `CREATESTRUCT`構造には、ウィンドウを作成するためのパラメーターのコピーが含まれています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onctlcolor"></a>  CWnd::OnCtlColor  
 フレームワークは、子コントロールが描画されるときに、このメンバー関数を呼び出します。  
  
```  
afx_msg HBRUSH OnCtlColor(
    CDC* pDC,  
    CWnd* pWnd,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 子ウィンドウのディスプレイ コンテキストへのポインターが含まれています。 一時があります。  
  
 `pWnd`  
 色を求めるコントロールへのポインターが含まれています。 一時があります。  
  
 `nCtlColor`  
 コントロールの種類を指定する、次の値のいずれかが含まれます。  
  
- **CTLCOLOR_BTN**ボタン コントロール  
  
- **CTLCOLOR_DLG**  ダイアログ ボックス  
  
- **CTLCOLOR_EDIT**エディット コントロール  
  
- **CTLCOLOR_LISTBOX**リスト ボックス コントロール  
  
- **CTLCOLOR_MSGBOX**メッセージ ボックス  
  
- **CTLCOLOR_SCROLLBAR**スクロール バー コントロール  
  
- **CTLCOLOR_STATIC**スタティック コントロール  
  
### <a name="return-value"></a>戻り値  
 `OnCtlColor` 使用してコントロールの背景を描画するブラシをハンドルを返す必要があります。  
  
### <a name="remarks"></a>コメント  
 ほとんどのコントロールを準備するのには、親 (通常はダイアログ ボックス) をこのメッセージを送信する、`pDC`正しい色を使用して、コントロールを描画するためです。  
  
 テキストの色を変更するには、呼び出し、`SetTextColor`希望する赤、緑、および青 (RGB) の値のメンバー関数。  
  
 単一行エディット コントロールの背景色を変更するには、両方でブラシのハンドルを設定、 **CTLCOLOR_EDIT**と**CTLCOLOR_MSGBOX**メッセージ コード、および呼び出し、 [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor)関数への応答、 **CTLCOLOR_EDIT**コード。  
  
 `OnCtlColor` 呼び出さないドロップダウン コンボ ボックスのリスト ボックスのドロップダウン リスト ボックスが実際には、コンボ ボックスの子で、ウィンドウの子ではありません。 ドロップダウン リスト ボックスの色を変更するには、作成、`CComboBox`のオーバーライドを含む`OnCtlColor`をチェックする**CTLCOLOR_LISTBOX**で、`nCtlColor`パラメーター。 このハンドラーで、`SetBkColor`テキストの背景色を設定するメンバー関数を使用する必要があります。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。 ダイアログ クラスに次のメソッドを追加するには、WM_CTLCOLOR メッセージ ハンドラーを追加するのに Visual Studio のプロパティ ペインを使用します。 また、メッセージ マップに ON_WM_CTLCOLOR() エントリを手動で追加することができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#107](../../mfc/reference/codesnippet/cpp/cwnd-class_47.cpp)]  
  
##  <a name="ondeadchar"></a>  CWnd::OnDeadChar  
 フレームワークはこのメンバー関数を呼び出すときに、 [OnKeyUp](#onkeyup)メンバー関数および[OnKeyDown](#onkeydown)メンバー関数が呼び出されます。  
  
```  
afx_msg void OnDeadChar(
    UINT nChar,  
    UINT nRepCnt,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 配信不能キーの文字の値を指定します。  
  
 `nRepCnt`  
 繰り返し回数を指定します。  
  
 `nFlags`  
 次の一覧に示すように、スキャン コード、キー遷移コード、前のキーの状態、およびコンテキストのコードを指定します。  
  
|[値]|説明|  
|-----------|-----------------|  
|0-7|コード (OEM に依存する値) をスキャンします。 上位ワードの下位バイトをします。|  
|8|ファンクション キーまたはテンキー (拡張キーである場合は 1。 それ以外の場合 0) のキーなどの拡張キー。|  
|9-10|使用しません。|  
|11-12|Windows によって内部的に使用します。|  
|13|コンテキストのコード (キーが押された、ALT キーが保持されている場合は 1。 それ以外の場合 0) です。|  
|14|以前のキー状態 (1 上のキーが 0 の場合、呼び出しの前に、キーがダウンしている場合)。|  
|16|(キーが解放されている場合は 1、押されている場合は 0) の状態に移行します。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は配信不能キーの文字の値を指定するためにことができます。 配信不能キーは、複合文字を形成する他の文字と組み合わせた、ウムラウト (ダブル ピリオド) 文字などのキーです。 たとえば、ウムラウト-o 文字は、配信不能キー、ウムラウト、および O キーで構成されます。  
  
 アプリケーションは`OnDeadChar`に押されたキーに関するユーザー フィードバックを提供します。 たとえば、アプリケーションは、カレットを移動せず、現在の文字位置に、アクセントを表示できます。  
  
 ないため必ずしも 1 対 1 の対応間押されたキーと`OnDeadChar`を呼び出すと、情報`nFlags`は通常、アプリケーションに役に立ちません。 情報は、`nFlags`を最新の呼び出しにのみ適用されます、 [OnKeyUp](#onkeyup)メンバー関数または[OnKeyDown](#onkeydown)前にあるメンバー関数、`OnDeadChar`呼び出します。  
  
 IBM エンハンス 101 および 102 key キーボード、強化されたキーには右 ALT および右 CTRL キーを押し、キーボードのメイン セクションにアドイン、DEL、HOME、END、PAGEUP、PAGEDOWN、および; テンキーの左側に、クラスター内の矢印キースラッシュ (/) およびテンキーで ENTER キー。 その他の一部のキーボード可能性があります、拡張キー ビット サポートで`nFlags`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="ondeleteitem"></a>  CWnd::OnDeleteItem  
 フレームワーク リスト ボックスまたはコンボ ボックスが破棄されることや項目が削除されているオーナー描画リスト ボックスまたはコンボ ボックスの所有者に通知するには、このメンバー関数を呼び出します[オーナー](../../mfc/reference/ccombobox-class.md#deletestring)、 [CListBox::DeleteString](../../mfc/reference/clistbox-class.md#deletestring)、 [CComboBox::ResetContent](../../mfc/reference/ccombobox-class.md#resetcontent)、または[中](../../mfc/reference/clistbox-class.md#resetcontent)です。  
  
```  
afx_msg void OnDeleteItem(
    int nIDCtl,  
    LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDCtl`  
 送信したコントロールの識別子、`WM_DELETEITEM`メッセージ。  
  
 `lpDeleteItemStruct`  
 Long ポインターを指定します、 [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md)削除したリスト ボックス項目に関する情報を格納するデータ構造です。  
  
### <a name="remarks"></a>コメント  
 場合、 **hwndItem**のメンバー、`DELETEITEMSTRUCT`構造が属しているコンボ ボックスまたはリスト ボックスで、次に、`DeleteItem`適切なクラスの仮想関数が呼び出されます。 上書き、`DeleteItem`アイテムに固有のデータを削除する適切なコントロールのクラスのメンバー関数。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="ondestroy"></a>  CWnd::OnDestroy  
 フレームワークに通知するには、このメンバー関数、`CWnd`オブジェクトが破棄されていること。  
  
```  
afx_msg void OnDestroy();
```  
  
### <a name="remarks"></a>コメント  
 `OnDestroy` 後に呼び出されます、`CWnd`オブジェクトは、画面から削除します。  
  
 `OnDestroy` 最初に呼び出されますが、`CWnd`破棄されており、次の子ウィンドウの`CWnd`が破棄されるとします。 すべての子ウィンドウがまだ存在するいると想定することができます、`OnDestroy`を実行します。  
  
 場合、`CWnd`オブジェクト、クリップボード ビューアー チェーンの一部は、破棄されている (を呼び出して設定、 [SetClipboardViewer](#setclipboardviewer)メンバー関数) では、`CWnd`自体から削除クリップボード ビューアーのチェインを呼び出して、[ウィンドウ](#changeclipboardchain)メンバー関数から戻る前に、`OnDestroy`関数。  
  
##  <a name="ondestroyclipboard"></a>  CWnd::OnDestroyClipboard  
 呼び出すことによって、クリップボードが空になるときに、フレームワークで、クリップボード オーナーに対してこのメンバー関数が呼び出さ、 [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) Windows の機能です。  
  
```  
afx_msg void OnDestroyClipboard();
```  
  
##  <a name="ondevicechange"></a>  CWnd::OnDeviceChange  
 フレームワークは、アプリケーションまたはデバイスまたはコンピューターのハードウェア構成の変更のデバイス ドライバーに通知するには、このメンバー関数を呼び出します。  
  
```  
afx_msg BOOL OnDeviceChange(
    UINT nEventType,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>パラメーター  
 *nEventType*  
 イベントの種類。 使用可能な値の詳細については「解説」セクションを参照してください。  
  
 `dwData`  
 イベントに固有のデータを格納する構造体のアドレス。 その意味は、指定したイベントによって異なります。  
  
### <a name="remarks"></a>コメント  
 オペレーティング システムの通常の送信の取り出しと、ロックなどのソフトウェアで制御可能な機能を提供しているデバイスの場合、**できるよ**アプリケーションし、デバイスのデバイス ドライバーに終了正常にします。  
  
 デバイスのオペレーティング システムを強制的に削除した場合、送信することはできません、**行われた**これを行う前にメッセージ。  
  
 *%1%n*パラメーターには、これらの値のいずれかを指定できます。  
  
- [DBT_DEVICEARRIVAL](http://msdn.microsoft.com/library/windows/desktop/aa363205)デバイスが挿入されていても使用できます。  
  
- [行われた](http://msdn.microsoft.com/library/windows/desktop/aa363206)デバイスを削除するアクセス許可を要求します。 任意のアプリケーションでは、この要求を拒否でき、削除をキャンセルすることができます。  
  
- [DBT_DEVICEQUERYREMOVEFAILED](http://msdn.microsoft.com/library/windows/desktop/aa363207)デバイスを削除する要求は取り消されました。  
  
- [できるよ](http://msdn.microsoft.com/library/windows/desktop/aa363209)デバイスを削除します。 拒否することはできません。  
  
- [DBT_DEVICEREMOVECOMPLETE](http://msdn.microsoft.com/library/windows/desktop/aa363208)デバイスが削除されました。  
  
- [DBT_DEVICETYPESPECIFIC](http://msdn.microsoft.com/library/windows/desktop/aa363210)デバイス固有のイベントです。  
  
- [DBT_CONFIGCHANGED](http://msdn.microsoft.com/library/windows/desktop/aa363203)現在の構成が変更されました。  
  
- **DBT_DEVNODES_CHANGED**デバイス ノードが変更されました。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="ondevmodechange"></a>  CWnd::OnDevModeChange  
 フレームワークでは、すべての最上位の場合は、このメンバー関数が呼び出さ`CWnd`オブジェクトをユーザーがデバイス モードの設定を変更するとします。  
  
```  
afx_msg void OnDevModeChange(LPTSTR lpDeviceName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDeviceName*  
 WIN Windows 初期化ファイルで指定された名前のデバイスへのポインター。INI です。  
  
### <a name="remarks"></a>コメント  
 処理するアプリケーション、`WM_DEVMODECHANGE`メッセージでのデバイス モードの設定を再初期化できます。 Windows を使用するアプリケーション**復元するため**を保存し、デバイスの復元の設定は通常この関数を処理しません。  
  
 ユーザーがコントロール パネルから既定のプリンターを変更した場合、この関数は呼び出されません。 ここで、`OnWinIniChange`関数が呼び出されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="ondrawclipboard"></a>  CWnd::OnDrawClipboard  
 フレームワークでは、クリップボードの内容を変更するときに、クリップボード ビューアー チェーン内の各ウィンドウのこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnDrawClipboard();
```  
  
### <a name="remarks"></a>コメント  
 呼び出すことによりクリップボード ビューアーのチェインに参加しているアプリケーションのみ、 [SetClipboardViewer](#setclipboardviewer)メンバー関数は、この呼び出しに応答する必要があります。  
  
 受信する各ウィンドウ、`OnDrawClipboard`呼び出しを呼び出す必要があります、 [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950) Windows 関数に渡す、 [WM_DRAWCLIPBOARD](http://msdn.microsoft.com/library/windows/desktop/ms649025)クリップボード ビューアーのチェインで次のウィンドウにメッセージ。 次のウィンドウのハンドルがによって返される、 [SetClipboardViewer](#setclipboardviewer)メンバー関数への応答で変更される可能性があります、 [OnChangeCbChain](#onchangecbchain)メンバー関数の呼び出しです。  
  
##  <a name="ondrawiconicthumbnailorlivepreview"></a>  CWnd::OnDrawIconicThumbnailOrLivePreview  
 Windows 7 のタブのサムネイルに表示する、またはアプリケーションのピーク用にクライアントで表示するビットマップを取得する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDrawIconicThumbnailOrLivePreview(
    CDC& dc,  
    CRect rect,  
    CSize szRequiredThumbnailSize,  
    BOOL bIsThumbnail,  
    BOOL& bAlphaChannelSet);
```  
  
### <a name="parameters"></a>パラメーター  
 `dc`  
 デバイス コンテキストを指定します。  
  
 `rect`  
 表示するために、領域に外接する四角形を指定します。  
  
 `szRequiredThumbnailSize`  
 対象となるサムネイルのサイズを指定します。 場合無視するか`bIsThumbnail`は`FALSE`します。  
  
 `bIsThumbnail`  
 このメソッドがアイコン サムネイルまたはライブ プレビュー (ピーク) と呼ばれるかどうかを指定します。  
  
 `bAlphaChannelSet`  
 [out]設定`TRUE`場合は、実装で選択されているビットマップのアルファ チャネルを初期化する`dc`です。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドをオーバーライドし、縮小版およびピークをカスタマイズするために、指定したデバイス コンテキストで描画します。 場合`bThumbnail`は`TRUE`、`szRequiredThumbnailSize`は無視できます。 ここで (クライアント領域全体をカバーするビットマップ) フル サイズのビットマップを描画することに注意する必要があります。 デバイス コンテキスト ( `dc`) 選択した 32 ビットのビットマップが付属します。 既定の実装では、WM_PRINT を PRF_CLIENT、PRF_CHILDREN、および PRF_NONCLIENT フラグでは、このウィンドウに送信します。  
  
##  <a name="ondrawitem"></a>  CWnd::OnDrawItem  
 メニューが変更されたまたは、フレームワークがオーナー描画ボタン コントロール、コンボ ボックス コントロール、リスト ボックス コントロールまたはメニュー コントロールのビジュアルな部分の所有者をこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnDrawItem(
    int nIDCtl,  
    LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDCtl`  
 送信したコントロールの識別子を含む、`WM_DRAWITEM`メッセージ。 メニューには、メッセージが送信される場合`nIDCtl`0 が含まれています。  
  
 `lpDrawItemStruct`  
 Long ポインターを指定します、`DRAWITEMSTRUCT`描画される項目および必要な図面の種類に関する情報を格納するデータ構造です。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**のメンバー、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)構造体を描画な操作を実行するを定義します。 このメンバーのデータでは、コントロールの所有者がどのような描画の動作が必要かを判断できるようにします。  
  
 このメッセージを処理してから、戻る前にアプリケーションがいることを確認で識別されるデバイス コンテキスト、`hDC`のメンバー、`DRAWITEMSTRUCT`構造が既定の状態に復元します。  
  
 場合、 **hwndItem**メンバーが所属する、 [CButton](../../mfc/reference/cbutton-class.md)、 [CMenu](../../mfc/reference/cmenu-class.md)、 [CListBox](../../mfc/reference/clistbox-class.md)、または[CComboBox](../../mfc/reference/ccombobox-class.md)オブジェクト続いて、`DrawItem`適切なクラスの仮想関数が呼び出されます。 上書き、`DrawItem`項目の描画に適切なコントロールのクラスのメンバー関数。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="ondropfiles"></a>  CWnd::OnDropFiles  
 フレームワークは、ユーザーがドロップされたファイルを受け取るように登録したウィンドウ上でマウスの左ボタンを離したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnDropFiles(HDROP hDropInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *hDropInfo*  
 ドロップされたファイルを記述する内部データ構造へのポインター。 このハンドルを使用して、 **DragFinish**、 **DragQueryFile**と**ドロップ**Windows 関数をドロップされたファイルに関する情報を取得します。  
  
### <a name="remarks"></a>コメント  
 通常、派生クラスが削除されたファイルをサポートするように設計して、ウィンドウの作成中に登録されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onenable"></a>  CWnd::OnEnable  
 アプリケーションの有効な状態を変更するときに、フレームワークがこのメンバー関数を呼び出す、`CWnd`オブジェクト。  
  
```  
afx_msg void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 指定するかどうか、`CWnd`オブジェクトを有効になっているか、無効になっています。 このパラメーターは**TRUE**場合、 `CWnd` ; 有効になっていることが**FALSE**場合、`CWnd`無効になっています。  
  
### <a name="remarks"></a>コメント  
 `OnEnable` 前に呼び出されます、 [EnableWindow](#enablewindow)メンバー関数を返しますが有効になっているウィンドウの状態の後 ( [WS_DISABLED](styles-used-by-mfc.md#window-styles)スタイル ビット) が変更されました。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onendsession"></a>  CWnd::OnEndSession  
 フレームワークは、このメンバー関数の後、`CWnd`オブジェクトには、0 以外の値からが返される、[はす](#onqueryendsession)メンバー関数の呼び出しです。  
  
```  
afx_msg void OnEndSession(BOOL bEnding);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnding`  
 セッションが終了されているかどうかを指定します。 **TRUE**セッションがそれ以外の終了されている場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 `OnEndSession`呼び出しの通知、`CWnd`オブジェクトの実際には、セッションが終了するかどうか。  
  
 場合`bEnding`は**TRUE**、すべてのアプリケーションがこの呼び出しの処理から返された後、いつでも終了できます。 その結果で終了に必要なすべてのタスクを実行するアプリケーションがある`OnEndSession`です。  
  
 呼び出す必要はありません、 [DestroyWindow](#destroywindow)メンバー関数または[PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) Windows セッションが終了するときに機能します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onenteridle"></a>  CWnd::OnEnterIdle  
 フレームワークは、モーダル ダイアログ ボックスまたはメニューがアイドル状態を入力することをアプリケーションのメイン ウィンドウ プロシージャに通知するためにこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnEnterIdle(
    UINT nWhy,  
    CWnd* pWho);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWhy`  
 メッセージが表示されたメニューまたはダイアログの結果であるかどうかを指定します。 このパラメーターには、次の値のいずれかを指定できます。  
  
- **MSGF_DIALOGBOX**  ダイアログ ボックスが表示されているため、システムがアイドル状態です。  
  
- **MSGF_MENU**メニューが表示されているため、システムがアイドル状態です。  
  
 *pWho*  
 ダイアログ ボックスへのポインターを指定します (場合`nWhy`は**MSGF_DIALOGBOX**)、または表示されたメニューが含まれるウィンドウ (場合`nWhy`は**MSGF_MENU**)。 このポインターは、一時的な場合があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 モーダル ダイアログ ボックスまたはメニューは、アイドル状態と状態メッセージがなくなるキューに 1 つまたは複数の以前のメッセージを処理した後です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onentermenuloop"></a>  CWnd::OnEnterMenuLoop  
 フレームワークは、メニュー モーダル ループに入ったときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnEnterMenuLoop(BOOL bIsTrackPopupMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `bIsTrackPopupMenu`  
 関連するメニューがポップアップ メニューであるかどうかを指定します。 関数が成功した場合に 0 以外の値それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onentersizemove"></a>  CWnd::OnEnterSizeMove  
 フレームワークは、影響を受けるウィンドウが移動またはサイズ変更モーダル ループに入る後に 1 回、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnEnterSizeMove();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_ENTERSIZEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms632622)通知で、Windows SDK に記載されています。  
  
 ウィンドウが移動またはウィンドウのタイトル バーまたはサイズ変更境界の場合は、ユーザーがクリックしたとき、またはウィンドウが成功したときにモーダル ループをサイズ変更、 [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360)メッセージごとに、 [CWnd::DefWindowProc](#defwindowproc)関数と`wParam`そのメッセージのパラメーターを指定`SC_MOVE`または`SC_SIZE`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onerasebkgnd"></a>  CWnd::OnEraseBkgnd  
 フレームワークは、このメンバー関数を呼び出すときに、`CWnd`オブジェクトの背景を削除しなければならない (たとえば、ときにサイズ変更)。  
  
```  
afx_msg BOOL OnEraseBkgnd(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキスト オブジェクトを指定します。  
  
### <a name="return-value"></a>戻り値  
 バック グラウンド; を消去する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 描画するための無効な領域の準備に呼び出されます。  
  
 既定の実装で指定されたウィンドウ クラスの背景ブラシを使用してバック グラウンドの消去、 **hbrBackground**ウィンドウ クラス構造体のメンバーです。  
  
 場合、 **hbrBackground**メンバーは**NULL**、オーバーライドされたバージョンの`OnEraseBkgnd`背景色を消去する必要があります。 バージョンで目的のブラシの原点を揃える必要がありますも、`CWnd`最初の呼び出しによって座標[か](http://msdn.microsoft.com/library/windows/desktop/dd145164)ブラシ、およびブラシを選択します。  
  
 オーバーライドされた`OnEraseBkgnd`への応答に 0 以外を返します`WM_ERASEBKGND`消去それ以上が必要ですを示すこのメッセージを処理し、背景が消去します。 0 を返します、ウィンドウは、消去する対象としてマークされたままです。 (通常、これは、 **fErase**のメンバー、`PAINTSTRUCT`される構造**TRUE**)。  
  
 Windows では、バック グラウンドの計算が前提としています、`MM_TEXT`マッピング モード。 デバイス コンテキストは、他のマッピング モードで使用されている場合、領域を消去できない可能性がありますクライアント領域の表示領域内で。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onexitmenuloop"></a>  CWnd::OnExitMenuLoop  
 フレームワークは、メニュー モーダル ループが終了したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnExitMenuLoop(BOOL bIsTrackPopupMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `bIsTrackPopupMenu`  
 関連するメニューがポップアップ メニューであるかどうかを指定します。 関数が成功した場合に 0 以外の値それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onexitsizemove"></a>  CWnd::OnExitSizeMove  
 フレームワークは、影響を受けるウィンドウが移動またはサイズ変更モーダル ループを終了後に 1 回、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnExitSizeMove();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_EXITSIZEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms632623)通知で、Windows SDK に記載されています。  
  
 ウィンドウが移動またはウィンドウのタイトル バーまたはサイズ変更境界の場合は、ユーザーがクリックしたとき、またはウィンドウが成功したときにモーダル ループをサイズ変更、 [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360)メッセージごとに、 [CWnd::DefWindowProc](#defwindowproc)関数と`wParam`そのメッセージのパラメーターを指定`SC_MOVE`または`SC_SIZE`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onfontchange"></a>  CWnd::OnFontChange  
 システムのすべてのトップ レベル ウィンドウ、`OnFontChange`アプリケーションは、フォント リソースのプールを変更した後に、フレームワークから呼び出します。  
  
```  
afx_msg void OnFontChange();
```  
  
### <a name="remarks"></a>コメント  
 追加したり、システム フォントを削除するアプリケーションを (を使用して、 [AddFontResource](http://msdn.microsoft.com/library/windows/desktop/dd183326)または[RemoveFontResource](http://msdn.microsoft.com/library/windows/desktop/dd162922) Windows 関数) を送信する必要があります、 [WM_FONTCHANGE](http://msdn.microsoft.com/library/windows/desktop/dd145211)すべての最上位ウィンドウにメッセージ。  
  
 このメッセージを送信するを使用して、 [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950)で Windows の機能、`hWnd`パラメーターに設定**HWND_BROADCAST**です。  
  
##  <a name="ongetdlgcode"></a>  CWnd::OnGetDlgCode  
 方向キーおよび Tab キーによる入力そのものをコントロールが処理できるように、そのコントロールに対して呼び出されます。  
  
```  
afx_msg UINT OnGetDlgCode();
```  
  
### <a name="return-value"></a>戻り値  
 1 つ以上のアプリケーション プロセスの入力の種類を示す、次の値。  
  
- **示すため**(汎用) ボタンをクリックします。  
  
- **DLGC_DEFPUSHBUTTON**プッシュ ボタンの既定値です。  
  
- **DLGC_HASSETSEL EM_SETSEL**メッセージ。  
  
- **DLGC_UNDEFPUSHBUTTON**既定プッシュ ボタン処理はありません。 (このフラグを使用して**示すため**ボタンの入力を処理が、プッシュ ボタンの処理の既定のシステムに依存していることを示すことです)。  
  
- **DLGC_RADIOBUTTON**ラジオ ボタンをクリックします。  
  
- **DLGC_STATIC**スタティック コントロール。  
  
- **DLGC_WANTALLKEYS**すべてのキーボード入力です。  
  
- **DLGC_WANTARROWS**方向キー。  
  
- **DLGC_WANTCHARS** `WM_CHAR`メッセージ。  
  
- **DLGC_WANTMESSAGE**すべてのキーボード入力です。 アプリケーションでは、コントロールには、このメッセージを渡します。  
  
- **DLGC_WANTTAB** TAB キー。  
  
### <a name="remarks"></a>コメント  
 通常、Windows がへのすべての方向キーおよび TAB キー入力を処理する`CWnd`コントロール。 オーバーライドすることで`OnGetDlgCode`、`CWnd`コントロール自体を処理する入力の特定の種類を選択できます。  
  
 既定値`OnGetDlgCode`は定義済みのコントロール クラス コードが返される各クラスの適切なためです。  
  
##  <a name="ongetminmaxinfo"></a>  CWnd::OnGetMinMaxInfo  
 フレームワークは、Windows を最大化された位置、またはディメンション、または最小値と最大のトラッキング サイズを知る必要があるたびに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnGetMinMaxInfo(MINMAXINFO* lpMMI);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMMI*  
 指す、`MINMAXINFO`ウィンドウに関する情報を格納する構造体サイズと位置、および追跡の最小値と最大サイズを最大表示します。 この構造体の詳細についてを参照してください。、 [MINMAXINFO](../../mfc/reference/minmaxinfo-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 最大化のサイズは、境界が完全に拡張するときに、ウィンドウのサイズです。 最大のトラッキング ウィンドウのサイズは、ウィンドウのサイズを境界線を使用して実現可能な最大ウィンドウ サイズです。 最小のトラッキング ウィンドウのサイズは、ウィンドウのサイズを境界線を使用して実現可能な最も小さいウィンドウ サイズです。  
  
 Windows は、さまざまな位置とディメンションの既定値を指定する点の配列に格納します。 アプリケーションでこれらの値を変更することがあります`OnGetMinMaxInfo`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onhelp"></a>  CWnd::OnHelp  
 アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。  
  
```  
afx_msg void OnHelp();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[:onhelp](../../mfc/reference/cwinapp-class.md#onhelp)詳細についてはします。  
  
##  <a name="onhelpfinder"></a>  CWnd::OnHelpFinder  
 処理、 **ID_HELP_FINDER**と**ID_DEFAULT_HELP**コマンド。  
  
```  
afx_msg void OnHelpFinder();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[CWinApp::OnHelpFinder](../../mfc/reference/cwinapp-class.md#onhelpfinder)詳細についてはします。  
  
##  <a name="onhelpindex"></a>  CWnd::OnHelpIndex  
 処理、 **ID_HELP_INDEX**コマンドし、既定のヘルプ トピックを提供します。  
  
```  
afx_msg void OnHelpIndex();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[CWinApp::OnHelpIndex](../../mfc/reference/cwinapp-class.md#onhelpindex)詳細についてはします。  
  
##  <a name="onhelpinfo"></a>  CWnd::OnHelpInfo  
 ユーザーが F1 キーを押したときに、フレームワークによって呼び出されます。  
  
```  
afx_msg BOOL OnHelpInfo(HELPINFO* lpHelpInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpHelpInfo*  
 ポインター、 [HELPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773313)メニュー項目、コントロール、ダイアログ ボックスで、またはウィンドウのヘルプが要求された情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウにキーボード フォーカスがある場合、またはメニューが、ウィンドウ内でアクティブな場合は、TRUE を返します。 ウィンドウにキーボード フォーカスされていない場合は、FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 F1 キーが押されたときに、メニューがアクティブな場合**WM_HELP**は、メニューに関連付けられたウィンドウへの送信、それ以外の**WM_HELP**がキーボード フォーカスがあるウィンドウに送信します。 ウィンドウで、キーボード フォーカスされていない場合**WM_HELP**が現在アクティブなウィンドウに送信します。  
  
##  <a name="onhelpusing"></a>  CWnd::OnHelpUsing  
 処理、 **ID_HELP_USING**コマンド。  
  
```  
afx_msg void OnHelpUsing();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[CWinApp::OnHelpUsing](../../mfc/reference/cwinapp-class.md#onhelpusing)詳細についてはします。  
  
##  <a name="onhotkey"></a>  CWnd::OnHotKey  
 フレームワークは、システム全体のホット キーを押したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnHotKey(
    UINT nHotKeyId,   
    UINT nKey1,   
    UINT nKey2);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nHotKeyId`|メッセージを生成したホット キーの識別子。 メッセージがシステム定義のホット キーによって生成された場合、次の値のいずれかをこのパラメーターになります。<br /><br /> - `IDHOT_SNAPDESKTOP` -スナップイン デスクトップ ホット キーが押されました。<br />- `IDHOT_SNAPWINDOW` -スナップイン ウィンドウ ホット キーが押されました。|  
|[入力] `nKey1`|指定したキーの組み合わせで押されたキーを示すフラグのビットごとの組み合わせ (OR)、`nKey2`パラメーター。 次の値を指定できます。<br /><br /> - `MOD_ALT` いずれかの ALT キーを押してをいた。<br />- `MOD_CONTROL` CTRL キーを押してをいた。<br />- `MOD_SHIFT` -か SHIFT キーを押してをいた。<br />- `MOD_WIN` いずれかの WINDOWS キーを押してをいた。 これらのキーには、Microsoft Windows ロゴが付いています。|  
|[入力] `nKey2`|ホット キーの仮想キー コード。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279)通知で、Windows SDK に記載されています。 このメッセージは、ホット キーを使って登録されているスレッドに関連付けられているメッセージ キューの先頭に配置されます。 使用して、 [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309)システム全体のホット キーを登録します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onhscroll"></a>  CWnd::OnHScroll  
 フレームワークは、ユーザーがウィンドウの水平スクロール バーをクリックしたときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnHScroll(
    UINT nSBCode,  
    UINT nPos,  
    CScrollBar* pScrollBar);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSBCode`  
 スクロール バーのコードをユーザーを示すには要求のスクロールを指定します。 このパラメーターには、次のいずれかを指定できます。  
  
- **SB_LEFT**一番左にスクロールします。  
  
- **SB_ENDSCROLL**スクロール終了します。  
  
- **SB_LINELEFT**スクロールのままです。  
  
- **SB_LINERIGHT**右にスクロールします。  
  
- **SB_PAGELEFT** 1 ページ左にスクロールします。  
  
- **SB_PAGERIGHT**スクロール 1 ページ右。  
  
- **SB_RIGHT**一番右にスクロールします。  
  
- **SB_THUMBPOSITION**絶対位置までスクロールします。 によって現在の位置が指定されて、`nPos`パラメーター。  
  
- **SB_THUMBTRACK**指定した位置にスクロール ボックスをドラッグします。 によって現在の位置が指定されて、`nPos`パラメーター。  
  
 `nPos`  
 スクロール バーのコードがある場合、スクロール ボックスの位置を示す**SB_THUMBPOSITION**または**SB_THUMBTRACK**。 それ以外の場合は使用しません。 初期のスクロールの範囲に応じて`nPos`が負の数およびにキャストする必要があります、`int`必要な場合です。  
  
 `pScrollBar`  
 スクロール バー コントロールからスクロール メッセージが送信された場合に、コントロールへのポインターが含まれています。 このパラメーターは、ユーザーがウィンドウのスクロール バーをクリックした場合**NULL**です。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 **SB_THUMBTRACK**スクロール バー コード通常はアプリケーションで使用されるスクロール ボックスにドラッグしているときに、いくつかのフィードバックを提供します。  
  
 スクロール ボックスの位置にリセットする必要がありますもアプリケーションは、スクロール バーで制御される内容をスクロールする場合、 [SetScrollPos](#setscrollpos)メンバー関数。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#108](../../mfc/reference/codesnippet/cpp/cwnd-class_48.cpp)]  
  
##  <a name="onhscrollclipboard"></a>  CWnd::OnHScrollClipboard  
 クリップボード所有者の`OnHScrollClipboard`クリップボード データがあるときに、クリップボード ビューアーによってメンバー関数が呼び出されます、`CF_OWNERDISPLAY`書式設定し、クリップボード ビューアーの水平スクロール バーで、イベントがあります。  
  
```  
afx_msg void OnHScrollClipboard(
    CWnd* pClipAppWnd,  
    UINT nSBCode,  
    UINT nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `pClipAppWnd`  
 クリップボード ビューアー ウィンドウへのポインターを指定します。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
 `nSBCode`  
 下位ワードでスクロール バーの次のコードのいずれかを指定します。  
  
- **SB_BOTTOM**右下へスクロールします。  
  
- **SB_ENDSCROLL**スクロール終了します。  
  
- **SB_LINEDOWN** 1 行下へスクロールします。  
  
- **SB_LINEUP** 1 行を上にスクロールします。  
  
- **SB_PAGEDOWN** 1 ページ下へスクロールします。  
  
- **SB_PAGEUP**を 1 つのページをスクロールします。  
  
- **SB_THUMBPOSITION**絶対位置にスクロールします。 現在の位置がで提供される`nPos`です。  
  
- **SB_TOP**左上にスクロールします。  
  
 `nPos`  
 スクロール バーのコードがある場合は、スクロール ボックスの位置を含む**SB_THUMBPOSITION**です。 それ以外の場合は使用されません。  
  
### <a name="remarks"></a>コメント  
 所有者をクリップボードのイメージをスクロール、適切なセクションが無効にし、スクロール バーの値を更新します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oniconerasebkgnd"></a>  CWnd::OnIconEraseBkgnd  
 フレームワークでは、(アイコン化) の最小化状態の場合は、このメンバー関数が呼び出さ`CWnd`オブジェクトのアイコンの背景は、アイコンを描画する前にいっぱいになる必要があります。  
  
```  
afx_msg void OnIconEraseBkgnd(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 アイコンのデバイス コンテキスト オブジェクトを指定します。 一時的な場合があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 `CWnd` クラスのアイコンがウィンドウ既定の実装です。 定義されている場合にのみ、この呼び出しを受け取るそれ以外の場合[OnEraseBkgnd](#onerasebkgnd)と呼びます。  
  
 [DefWindowProc](#defwindowproc)メンバー関数は、親ウィンドウの背景のブラシのアイコンの背景を塗りつぶします。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oninitmenu"></a>  CWnd::OnInitMenu  
 メニューがアクティブになるときに、フレームワークはこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnInitMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenu`  
 初期化するのには、メニューを指定します。 一時的な場合があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 `OnInitMenu` ユーザーがメニュー バーの項目をクリックするか、メニュー キーを押したときに呼び出されます。 表示される前に、メニューを変更するには、このメンバー関数をオーバーライドします。  
  
 `OnInitMenu` メニューが最初にアクセスされるとき (たとえば、ユーザーがクリックすると、メニュー バーの項目) に 1 回のみ呼び出します。 このメソッドは、メニュー項目に関する情報を提供していません。 ユーザーが (たとえば、いくつかのメニュー項目間で、マウスを移動) して、メニュー内の項目に移動すると、関数は再度呼び出されません。 ユーザーは、(たとえば、アプリケーションのクライアント領域をクリック) して、メニューを終了し、メニュー バーで項目をクリックした後で、関数が再度呼び出されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oninitmenupopup"></a>  CWnd::OnInitMenuPopup  
 ポップアップ メニューがアクティブになるときに、フレームワークはこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnInitMenuPopup(
    CMenu* pPopupMenu,  
    UINT nIndex,  
    BOOL bSysMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 *pPopupMenu*  
 ポップアップ メニューのメニュー オブジェクトを指定します。 一時的な場合があり、後で使用するために格納する必要があります。  
  
 `nIndex`  
 メイン メニューのポップアップ メニューのインデックスを指定します。  
  
 *bSysMenu*  
 **TRUE**ポップアップ メニューがメニューの場合、コントロールです。 それ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 これにより、アプリケーション全体のメニューを変更することがなく表示されるまでに、ポップアップ メニューを変更できます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oninputdevicechange"></a>  CWnd::OnInputDeviceChange  
 I/O デバイスが追加またはシステムから削除されたときに、フレームワークはこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnInputDeviceChange(unsigned short uFlag);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `uFlag`|このフラグは、次の値を含めることができます。<br /><br /> - `GIDC_ARRIVAL` -新しいデバイスがシステムに追加されました。<br />- `GIDC_REMOVAL` は、デバイスは、システムから削除されました。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_INPUT_DEVICE_CHANGE](http://msdn.microsoft.com/library/windows/desktop/ms645591)通知で、Windows SDK に記載されています。 汎用の入力デバイス メッセージです。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oninputlangchange"></a>  CWnd::OnInputLangChange  
 フレームワークは、アプリケーションの入力言語を変更した後に、最上位の影響を受けるウィンドウのこのメンバーを呼び出します。  
  
```  
afx_msg void OnInputLangChange(
    UINT nCharSet,   
    UINT nLocaleId);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nCharSet`|新しいロケールの文字セット。 詳細については、次を参照してください。、`lfCharSet`のパラメーター、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。|  
|[入力] `nLocaleId`|入力ロケール識別子です。 詳細については、次を参照してください。[言語識別子の定数と文字列](http://msdn.microsoft.com/library/windows/desktop/dd318693)です。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_INPUTLANGCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms632629)通知メッセージは、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="oninputlangchangerequest"></a>  CWnd::OnInputLangChangeRequest  
 フレームワークは、新しい入力言語を選択すると、フォーカスがあるウィンドウのこのメンバーを呼び出します。  
  
```  
afx_msg void OnInputLangChangeRequest(
    UINT nFlags,   
    UINT nLocaleId);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nFlags`|新しいロケールがインストールされているロケールでは、一連の前または次のロケールから選択されたか、システムの文字セットに新しい入力ロケールのキーボード レイアウトを使用できることを示すフラグのビットごと (OR) の組み合わせ。<br /><br /> 指定できる値は`INPUTLANGCHANGE_BACKWARD`、 `INPUTLANGCHANGE_FORWARD`、および`INPUTLANGCHANGE_SYSCHARSET`です。|  
|[入力] `nLocaleId`|入力ロケール識別子です。 詳細については、次を参照してください。[言語識別子の定数と文字列](http://msdn.microsoft.com/library/windows/desktop/dd318693)です。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_INPUTLANGCHANGEREQUEST](http://msdn.microsoft.com/library/windows/desktop/ms632630)通知メッセージは、Windows SDK に記載されています。 このメッセージは、ユーザーまたはシステムのタスク バー、インジケーターからキーボード コントロール パネルのアプリケーションで指定されているホットキーによって新しい入力言語を選択したときに通知されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onkeydown"></a>  CWnd::OnKeyDown  
 非システム キーが押されたときに、フレームワークはこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnKeyDown(
    UINT nChar,  
    UINT nRepCnt,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 指定したキーの仮想キー コードを指定します。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nRepCnt`  
 繰り返し回数 (回数、キーを押しながら、ユーザーの結果として、キーストロークが繰り返されます)。  
  
 `nFlags`  
 次の一覧に示すように、スキャン コード、キー遷移コード、前のキーの状態、およびコンテキストのコードを指定します。  
  
|[値]|説明|  
|-----------|-----------------|  
|0-7|コード (OEM に依存する値) をスキャンします。|  
|8|ファンクション キーまたはテンキー (拡張キーである場合は 1) キーなどの拡張キー。|  
|9-10|使用しません。|  
|11-12|Windows によって内部的に使用します。|  
|13|コンテキストのコード (キーが押された、ALT キーが保持されている場合は 1。 それ以外の場合 0) です。|  
|14|以前のキー状態 (1 上のキーが 0 の場合、呼び出しの前に、キーがダウンしている場合)。|  
|16|(キーが解放されている場合は 1、押されている場合は 0) の状態に移行します。|  
  
 `WM_KEYDOWN`メッセージ キー遷移ビット (bit 15) が 0 でコンテキスト コード ビット (bit 13) が 0 です。  
  
### <a name="remarks"></a>コメント  
 非システム キーは、キーボードのキー、ALT キーが押されていないときに押された状態またはキーボードのキーを押したときに`CWnd`入力フォーカスがあります。  
  
 自動繰り返し、1 つ以上のため`OnKeyDown`呼び出しにする前に発生する可能性があります、 [OnKeyUp](#onkeyup)メンバー関数の呼び出しが行われます。 以前のキーの状態を示すビットは、決定に使用できるかどうか、`OnKeyDown`呼び出しが最初に押さかダウン繰り返される遷移します。  
  
 IBM エンハンス 101 および 102 key キーボード、強化されたキーには右 ALT および右 CTRL キーを押し、キーボードのメイン セクションにアドイン、DEL、HOME、END、PAGEUP、PAGEDOWN、および; テンキーの左側に、クラスター内の矢印キースラッシュ (/) およびテンキーで ENTER キー。 その他の一部のキーボード可能性があります、拡張キー ビット サポートで`nFlags`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onkeyup"></a>  CWnd::OnKeyUp  
 非システム キーが離されると、フレームワークはこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnKeyUp(
    UINT nChar,  
    UINT nRepCnt,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 指定したキーの仮想キー コードを指定します。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nRepCnt`  
 繰り返し回数 (回数、キーを押しながら、ユーザーの結果として、キーストロークが繰り返されます)。  
  
 `nFlags`  
 次の一覧に示すように、スキャン コード、キー遷移コード、前のキーの状態、およびコンテキストのコードを指定します。  
  
|[値]|説明|  
|-----------|-----------------|  
|0-7|コード (OEM に依存する値) をスキャンします。 上位ワードの下位バイトをします。|  
|8|ファンクション キーまたはテンキー (拡張キーである場合は 1。 それ以外の場合 0) のキーなどの拡張キー。|  
|9-10|使用しません。|  
|11-12|Windows によって内部的に使用します。|  
|13|コンテキストのコード (キーが押された、ALT キーが保持されている場合は 1。 それ以外の場合 0) です。|  
|14|以前のキー状態 (1 上のキーが 0 の場合、呼び出しの前に、キーがダウンしている場合)。|  
|16|(キーが解放されている場合は 1、押されている場合は 0) の状態に移行します。|  
  
 `WM_KEYUP`メッセージ キー遷移ビット (bit 15) が 1 でコンテキスト コード ビット (bit 13) が 0 です。  
  
### <a name="remarks"></a>コメント  
 非システム キーは、キーボードのキー、ALT キーが押されていないときに押された状態またはキーボードのキーを押したときに、`CWnd`入力フォーカスがあります。  
  
 IBM エンハンス 101 および 102 key キーボード、強化されたキーには右 ALT および右 CTRL キーを押し、キーボードのメイン セクションにアドイン、DEL、HOME、END、PAGEUP、PAGEDOWN、および; テンキーの左側に、クラスター内の矢印キースラッシュ (/) およびテンキーで ENTER キー。 その他の一部のキーボード可能性があります、拡張キー ビット サポートで`nFlags`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onkillfocus"></a>  CWnd::OnKillFocus  
 フレームワークは、入力フォーカスを失う直前に、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnKillFocus(CWnd* pNewWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pNewWnd*  
 入力フォーカスを受け取るウィンドウへのポインターを指定します (あります**NULL**か一時的な可能性があります)。  
  
### <a name="remarks"></a>コメント  
 場合、`CWnd`オブジェクトが、カレットを表示する、キャレットをこの時点で破棄する必要があります。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onlbuttondblclk"></a>  CWnd::OnLButtonDblClk  
 フレームワークは、ユーザーがマウスの左ボタンをダブルクリックすると、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnLButtonDblClk(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 カーソルの x 座標と y 座標を指定します。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 持つ windows のみ、 **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)形式の受信は`OnLButtonDblClk`呼び出しです。 これは、Microsoft Foundation Class の windows の既定値です。 Windows 呼び出し`OnLButtonDblClk`ユーザー押し続けたときに、リリースでは、システムの以内に再度マウスの左ボタンを押した制限時間をダブルクリックします。 マウスの左ボタンをダブルクリックすると、実際に 4 つのイベントを生成: [WM_LBUTTONDOWN](#onlbuttondown)、[した](#onlbuttonup)、メッセージ、`WM_LBUTTONDBLCLK`呼び出し、および別`WM_LBUTTONUP`ボタンとメッセージ解放されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onlbuttondown"></a>  CWnd::OnLButtonDown  
 フレームワークは、ユーザーがマウスの左ボタンを押したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnLButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 カーソルの x 座標と y 座標を指定します。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onlbuttonup"></a>  CWnd::OnLButtonUp  
 フレームワークは、ユーザーがマウスの左ボタンを離したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 カーソルの x 座標と y 座標を指定します。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmbuttondblclk"></a>  CWnd::OnMButtonDblClk  
 フレームワークは、ユーザーがマウスの中央ボタンをダブルクリックすると、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnMButtonDblClk(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 カーソルの x 座標と y 座標を指定します。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 持つ windows のみ、 **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)形式の受信は`OnMButtonDblClk`呼び出しです。 これは、Microsoft Foundation Class のすべてのウィンドウの既定値です。 Windows が生成され、`OnMButtonDblClk`制限時間をダブルクリック、ユーザーが、リリース、およびし、システム内でマウスの中央ボタンをもう一度押すときに呼び出します。 マウスの中央ボタンをダブルクリックすると、実際に 4 つのイベントを生成: [WM_MBUTTONDOWN](#onmbuttondown)と[WM_MBUTTONUP](#onmbuttonup) 、メッセージ、`WM_MBUTTONDBLCLK`呼び出し、および別`WM_MBUTTONUP`メッセージ。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmbuttondown"></a>  CWnd::OnMButtonDown  
 フレームワークは、ユーザーがマウスの中央ボタンを押したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnMButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 カーソルの x 座標と y 座標を指定します。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmbuttonup"></a>  CWnd::OnMButtonUp  
 フレームワークは、ユーザーがマウスの中央ボタンを離したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnMButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 カーソルの x 座標と y 座標を指定します。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmdiactivate"></a>  CWnd::OnMDIActivate  
 フレームワークは、子ウィンドウの非アクティブ化とアクティブ化されている子ウィンドウのこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnMDIActivate(
    BOOL bActivate,  
    CWnd* pActivateWnd,  
    CWnd* pDeactivateWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActivate`  
 **TRUE**子プロセスがアクティブ化された場合と**FALSE**を非アクティブ化する場合。  
  
 `pActivateWnd`  
 アクティブ化する MDI 子ウィンドウへのポインターが含まれています。 MDI 子ウィンドウで受信したときに`pActivateWnd`アクティブ化されている子ウィンドウへのポインターが含まれています。 このポインターは、一時的な場合があり、後で使用するために格納する必要があります。  
  
 *pDeactivateWnd*  
 非アクティブ化されている MDI 子ウィンドウへのポインターが含まれています。 このポインターは、一時的な場合があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 MDI フレーム ウィンドウとは無関係に、MDI 子ウィンドウがアクティブ化されます。 フレームがアクティブになった、最後にアクティブになった子ウィンドウ、`OnMDIActivate`呼び出しが、[ため](#onncactivate)をアクティブなウィンドウ フレームおよびキャプション バーが描画メッセージを受け取りません別`OnMDIActivate`呼び出します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmeasureitem"></a>  CWnd::OnMeasureItem  
 フレームワークは、コントロールの作成時にこのメンバー関数をフレームワークによって、オーナー描画ボタン、コンボ ボックス、リスト ボックスまたはメニュー項目の所有者を呼び出します。  
  
```  
afx_msg void OnMeasureItem(
    int nIDCtl, LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDCtl`  
 コントロールの ID。  
  
 `lpMeasureItemStruct`  
 指す、 [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md)オーナー描画コントロールの大きさを格納するデータ構造です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`データ構造体を指す`lpMeasureItemStruct`および戻り値です。 このコントロールの大きさを Windows に通知および Windows コントロールでのユーザー操作を正しく処理できるようにします。  
  
 リスト ボックスまたはコンボ ボックスがで作成された場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)または[CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、フレームワーク、コントロール内の各項目の所有者のそれ以外の場合この関数は 1 回呼び出されます。  
  
 Windows への呼び出しを開始する`OnMeasureItem`で作成されたコンボ ボックスやリスト ボックスの所有者を**OWNERDRAWFIXED**送信する前にスタイル、 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428)メッセージ。 その結果、所有者は、この呼び出しを受信すると Windows がまだ決定されていないコントロールで使用するフォントの幅と高さ関数呼び出しとこれらの値を必要とする計算は、アプリケーションまたはライブラリの主な機能で発生する必要があります。  
  
 計測される項目がある場合、 `CMenu`、`CListBox`または`CComboBox`オブジェクト、`MeasureItem`適切なクラスの仮想関数が呼び出されます。 上書き、`MeasureItem`を計算して各アイテムのサイズを設定する適切なコントロールのクラスのメンバー関数。  
  
 `OnMeasureItem` コントロールのクラスが、実行時に作成されるか、使用して作成された場合にのみ呼び出される、 **LBS_OWNERDRAWVARIABLE**または**CBS_OWNERDRAWVARIABLE**スタイル。 ダイアログ エディターで、コントロールが作成される場合`OnMeasureItem`は呼び出されません。 これは、ため、[よう](http://msdn.microsoft.com/library/windows/desktop/bb775925)コントロールの作成プロセスの早い段階でメッセージを送信します。 場合を使用してサブクラス`DDX_Control`、 `SubclassDlgItem`、または`SubclassWindow`のサブクラス化作成プロセスの後に、通常に発生します。 そのため、処理する方法はありません、[よう](http://msdn.microsoft.com/library/windows/desktop/bb775925)、コントロールのメッセージ`OnChildNotify`関数と MFC を使用して実装機構**ON_WM_MEASUREITEM_REFLECT**です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmenuchar"></a>  CWnd::OnMenuChar  
 フレームワークは、ユーザーが現在のメニューのニーモニックのいずれかと一致しませんメニューのニーモニック文字を押したときにこのメンバー関数を呼び出します。  
  
```  
afx_msg LRESULT OnMenuChar(
    UINT nChar,  
    UINT nFlags,  
    CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 ビルドの設定によって、ユーザーが押された ANSI または Unicode の文字を指定します。  
  
 `nFlags`  
 含まれています、**ならば**場合は、メニューがポップアップ メニューにフラグを設定します。 含まれている、**ならば**場合は、メニューは、コントロール メニューにフラグを設定します。  
  
 `pMenu`  
 選択したへのポインターを含む`CMenu`です。 ポインターは、一時的な場合があり、保存されません。  
  
### <a name="return-value"></a>戻り値  
 戻り値の上位ワードには、次のコマンドのコードのいずれかを含める必要があります。  
  
|[値]|説明|  
|-----------|-----------------|  
|0|Windows ユーザーが押され、システムのスピーカーの短いビープ音を作成する文字を破棄するように指示します。|  
|1|現在のメニューを閉じる Windows に指示します。|  
|2|戻り値の下位ワードに数式が含まれているか、または特定の項目の項目数を Windows に通知します。 この項目は、Windows で選択されます。|  
  
 下位ワードには、上位ワードには、0 または 1 が含まれている場合は無視されます。 アプリケーションは、アクセラレータ (ショートカット) キーを使用してメニュー内に配置されたビットマップを選択する場合、このメッセージを処理する必要があります。  
  
### <a name="remarks"></a>コメント  
 送信される、`CWnd`メニューを所有しています。 `OnMenuChar` 呼び出されます alt キーとその他の任意のキーを押す場合でも、キーがニーモニック文字に対応していません。 ここでは、`pMenu`が所有するメニューを指す、 `CWnd`、および`nFlags`は 0 です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmenudrag"></a>  CWnd::OnMenuDrag  
 フレームワークは、ユーザーがメニュー項目のドラッグを開始すると、現在のドラッグ アンド ドロップ メニューのこのメンバー関数を呼び出します。  
  
```  
afx_msg UINT OnMenuDrag(
    UINT nPos,   
    CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nPos`|ドラッグ操作の開始時にメニュー項目のインデックス位置。|  
|[入力] `pMenu`|ポインター、 [CMenu](../../mfc/reference/cmenu-class.md)メニュー項目を含むオブジェクトです。|  
  
### <a name="return-value"></a>戻り値  
  
|戻り値|説明|  
|------------------|-------------|  
|`MND_CONTINUE`|メニューをアクティブのままです。 マウスが解放された場合は無視する必要があります。|  
|`MND_ENDMENU`|メニューを終了する必要があります。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_MENUDRAG](http://msdn.microsoft.com/library/windows/desktop/ms647606)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmenugetobject"></a>  CWnd::OnMenuGetObject  
 マウス カーソルをメニュー項目に置くか、アイテムの中央から項目の上下に移動すると、フレームワークは、現在のドラッグ アンド ドロップ メニューのこのメンバー関数を呼び出します。  
  
```  
afx_msg UINT OnMenuGetObject(MENUGETOBJECTINFO* pMenuGetObjectInfo);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pMenu`|ポインター、 [MENUGETOBJECTINFO](http://msdn.microsoft.com/library/windows/desktop/ms647572)では、ドラッグ アンド ドロップ メニュー、マウスのカーソルに関する情報を格納する構造体。|  
  
### <a name="return-value"></a>戻り値  
  
|戻り値|説明|  
|------------------|-------------|  
|`MNGO_NOERROR`|ドラッグ アンド ドロップ操作をサポートするインターフェイス ポインターが返される、`pvObj`のメンバー、 [MENUGETOBJECTINFO](http://msdn.microsoft.com/library/windows/desktop/ms647572)構造体。 現時点では、のみ、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)インターフェイスはサポートされています。|  
|`MNGO_NOINTERFACE`|ドラッグ アンド ドロップ インターフェイスがサポートされていません。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_MENUGETOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms647607)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmenurbuttonup"></a>  CWnd::OnMenuRButtonUp  
 フレームワークは、カーソルがメニュー項目がある状態でマウスの右ボタンを離したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnMenuRButtonUp(
    UINT nPos,  
    CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nPos`|マウスの右ボタンが離されたときにメニュー項目のインデックス位置。|  
|[入力] `pMenu`|ポインター、 [CMenu](../../mfc/reference/cmenu-class.md)メニュー項目を含むオブジェクトです。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_MENURBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms647610)通知で、Windows SDK に記載されています。 [WM_MENURBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms647610)メッセージにより、アプリケーションをメッセージに指定された項目、メニューの状況依存のメニューを提供します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmenuselect"></a>  CWnd::OnMenuSelect  
 場合、`CWnd`オブジェクトは、メニューと関連付け`OnMenuSelect`は、ユーザーがメニュー項目を選択したときにフレームワークによって呼び出されます。  
  
```  
afx_msg void OnMenuSelect(
    UINT nItemID,  
    UINT nFlags,  
    HMENU hSysMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItemID`  
 選択された項目を識別します。 選択したアイテムがメニュー項目である場合`nItemID`メニュー項目の ID が含まれています 選択した項目には、ポップアップ メニューが含まれている場合`nItemID`ポップアップ メニューのインデックスが含まれていますと*hSysMenu*メイン (クリックして) メニューのハンドルが含まれています。  
  
 `nFlags`  
 次のメニュー フラグの組み合わせが含まれます。  
  
- **MF_BITMAP**項目はビットマップ。  
  
- **MF_CHECKED**項目をチェックします。  
  
- **MF_DISABLED**項目が無効になっています。  
  
- **MF_GRAYED**項目が淡色表示にします。  
  
- **MF_MOUSESELECT**マウスでアイテムが選択されています。  
  
- `MF_OWNERDRAW` 項目がオーナー描画項目。  
  
- **ならば**項目には、ポップアップ メニューが含まれています。  
  
- **MF_SEPARATOR**項目がメニュー項目の区切り記号。  
  
- **ならば**コントロール メニュー項目が含まれています。  
  
 `hSysMenu`  
 場合`nFlags`含む**ならば**メッセージに関連付けられたメニューを識別します。 場合`nFlags`含む**ならば**、メイン メニューのハンドルを識別します。 場合`nFlags`がどちらも含まれています**ならば**も**ならば**は使用されません。  
  
### <a name="remarks"></a>コメント  
 場合`nFlags`0 xffff が含まれていますと`hSysMenu`0 を含む Windows で、メニューが閉じられた場合、ユーザーが ESC キーを押したか、メニューの外をクリックします。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmouseactivate"></a>  CWnd::OnMouseActivate  
 フレームワークは、非アクティブなウィンドウに、カーソルがあり、ユーザーがマウス ボタンを押したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg int OnMouseActivate(
    CWnd* pDesktopWnd,  
    UINT nHitTest,  
    UINT message);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDesktopWnd*  
 アクティブ化されているウィンドウの最上位の親ウィンドウへのポインターを指定します。 ポインターは、一時的な場合があり、保存されません。  
  
 `nHitTest`  
 指定します、[ヒット テスト](#onnchittest)市外局番します。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `message`  
 マウスのメッセージ番号を指定します。  
  
### <a name="return-value"></a>戻り値  
 アクティブ化するかどうかを指定します、`CWnd`マウス イベントを破棄するかどうか。 次の値のいずれかを指定する必要があります。  
  
- **MA_ACTIVATE** Activate`CWnd`オブジェクト。  
  
- **MA_NOACTIVATE**をアクティブにしない`CWnd`オブジェクト。  
  
- **MA_ACTIVATEANDEAT** Activate`CWnd`オブジェクトし、マウス イベントを破棄します。  
  
- **MA_NOACTIVATEANDEAT**をアクティブにしない`CWnd`オブジェクトし、マウス イベントを破棄します。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、任意の処理が行われる前に、親ウィンドウにこのメッセージを渡します。 親ウィンドウに返されます場合**TRUE**処理が停止します。  
  
 個々 のヒット テスト領域コードの説明は、次を参照してください、 [OnNcHitTest](#onnchittest)メンバー関数。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl#9](../../mfc/reference/codesnippet/cpp/cwnd-class_49.cpp)]  
  
##  <a name="onmousehover"></a>  CWnd::OnMouseHover  
 呼び出す前に指定された期間、ウィンドウのクライアント領域にカーソルを合わせると、フレームワークはこのメンバー関数を呼び出します[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)です。  
  
```  
afx_msg void OnMouseHover(
    UINT nFlags,   
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nFlags`|どの修飾子キーが押されたかを示すフラグのビットごとの組み合わせ (OR)。 たとえば、`MK_CONTROL`フラグは、CTRL キーが押されたことを示します。|  
|[入力] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)を指定するオブジェクト、 *x*と*y*クライアント領域の左上隅を基準としたカーソルの座標。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_MOUSEHOVER](http://msdn.microsoft.com/library/windows/desktop/ms645613)通知で、Windows SDK に記載されています。  
  
 `nFlags`パラメーターは、次の表に記載されている修飾子キーの組み合わせを指定できます。 詳細については、次を参照してください。[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)です。  
  
|修飾キー|説明|  
|------------------|-----------------|  
|MK_CONTROL|CTRL キーが押されるとします。|  
|MK_LBUTTON|マウスの左ボタンが押されるとします。|  
|MK_MBUTTON|マウスの中央ボタンが押されるとします。|  
|MK_RBUTTON|マウスの右ボタンが押されるとします。|  
|MK_SHIFT|SHIFT キーが押されるとします。|  
|MK_XBUTTON1|IntelliMouse のマウスの XBUTTON1 ボタンが押されるとします。|  
|MK_XBUTTON2|Microsoft IntelliMouse の XBUTTON2 マウス ボタンが押されたとします。|  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmousehwheel"></a>  CWnd::OnMouseHWheel  
 フレームワークは、現在のウィンドウがデスクトップ ウィンドウ マネージャー (DWM) で構成され、そのウィンドウを最大化するときにこのメンバーを呼び出します。  
  
```  
afx_msg void OnMouseHWheel(
    UINT nFlags,   
    short zDelta,   
    CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nFlags`|どの修飾子キーが押されたかを示すフラグのビットごとの組み合わせ (OR)。 たとえば、`MK_CONTROL`フラグは、CTRL キーが押されたことを示します。<br /><br /> フラグの一覧を参照してくださいで「メッセージのパラメーター」subheading[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)です。|  
|[入力] `zDelta`|ホイールを回転すると、倍数またはの区分線で表現された距離を示す`WHEEL_DELTA`120 であります。 正の値は、右、ホイールを回転したことを示します負の値は、ホイールを左に回転したことを示します。|  
|[入力] `pt`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)を指定するオブジェクト、 *x*と*y*クライアント領域の左上隅を基準としたカーソルの座標。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_MOUSEHWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645614)通知メッセージは、Windows SDK に記載されています。 このメッセージは、マウスの水平スクロール ホイールが傾いたときまたは回転したときに、フォーカスのあるウィンドウに送信されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmouseleave"></a>  CWnd::OnMouseLeave  
 呼び出す前に指定されたウィンドウのクライアント領域をカーソルが離れるときに、フレームワークはこのメンバー関数を呼び出します[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)です。  
  
```  
afx_msg void OnMouseLeave();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_MOUSELEAVE](http://msdn.microsoft.com/library/windows/desktop/ms645615)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmousemove"></a>  CWnd::OnMouseMove  
 マウス カーソルを移動すると、フレームワークはこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 カーソルの x 座標と y 座標を指定します。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 マウスがキャプチャされていない場合、`WM_MOUSEMOVE`メッセージを受信した、`CWnd`マウス カーソルの下にあるオブジェクトをマウスのキャプチャがウィンドウには、メッセージはそれ以外の場合。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmousewheel"></a>  CWnd::OnMouseWheel  
 フレームワークは、ユーザーがマウス ホイールを回転し、ホイールの次のノッチを検出すると、このメンバー関数を呼び出します。  
  
```  
afx_msg BOOL OnMouseWheel(
    UINT nFlags,  
    short zDelta,  
    CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `zDelta`  
 回転距離を示します。 `zDelta`値は倍数またはの区分線で表現**WHEEL_DELTA**120 であります。 0 より小さい値は 0 (ゼロ) を前方 (奥ユーザー) の回転を指定よりも大きい値の中に (ユーザー) に向かって回転を表す背面を示します。 ユーザーは、ソフトウェアのマウス ホイールの設定を変更することで、この応答を取り消すことができます。 このパラメーターの詳細については、「解説」を参照してください。  
  
 `pt`  
 カーソルの x 座標と y 座標を指定します。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="return-value"></a>戻り値  
 マウス ホイール スクロールが有効な場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オーバーライドされない限り、`OnMouseWheel`の既定値を呼び出す[WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617)です。 Windows は、自動的にフォーカスがあるコントロールまたは子ウィンドウにメッセージをルーティングします。 Win32 関数[DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572)がそれを処理するウィンドウへの親チェーンの上のメッセージを伝達します。  
  
 `zDelta`パラメーターがの倍数**WHEEL_DELTA**120 に設定されています。 この値は、操作を実行するのには、しきい値と各デルタのような 1 つのアクション (たとえば、スクロール前方 1 目盛り) が発生する必要があります。  
  
 **WHEEL_DELTA**ありませんノッチ自由に回転ホイールなどの高解像度のホイールを許可する 120 に設定されています。 高解像度のホイールが回転、あたり複数のメッセージを送信しますが、各メッセージがデルタ値を小さくします。 受信を追加するか、このようなホイールを使用する`zDelta`までの値**WHEEL_DELTA** (ようにするための特定のデルタ回転を同じ応答を得る) に達すると、またはより頻繁にメッセージに応答の一部の行をスクロールします。 スクロール粒度を選択し、までデルタ値を累積**WHEEL_DELTA**に到達します。  
  
 独自のマウス ホイール スクロール動作を提供するには、このメンバー関数をオーバーライドします。  
  
> [!NOTE]
> `OnMouseWheel` Windows NT 4.0 およびそれ以降のバージョンのメッセージを処理します。 Windows 95/98 または Windows NT 3.51 メッセージの処理を使用して[OnRegisteredMouseWheel](#onregisteredmousewheel)です。  
  
##  <a name="onmove"></a>  CWnd::OnMove  
 フレームワークは、このメンバー関数の後、`CWnd`オブジェクトは移動されました。  
  
```  
afx_msg void OnMove(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 クライアント領域の左上隅の x 座標場所を指定します。 この新しい場所がオーバー ラップ、ポップアップ ウィンドウを画面座標で指定され、親クライアントが子ウィンドウの座標します。  
  
 *y*  
 クライアント領域の左上隅の y 座標場所を指定します。 この新しい場所がオーバー ラップ、ポップアップ ウィンドウを画面座標で指定され、親クライアントが子ウィンドウの座標します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onmoving"></a>  CWnd::OnMoving  
 ユーザーが移動中に、フレームワークがこのメンバー関数を呼び出して、`CWnd`オブジェクト。  
  
```  
afx_msg void OnMoving(
    UINT nSide,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSide`  
 移動するウィンドウの端。  
  
 `lpRect`  
 アドレス、 [CRect](../../atl-mfc-shared/reference/crect-class.md)または[RECT 構造体](../../mfc/reference/rect-structure1.md)アイテムの座標が含まれる。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncactivate"></a>  CWnd::OnNcActivate  
 フレームワークは、非クライアント領域をアクティブまたは非アクティブな状態を示すために変更する必要がある場合に、このメンバー関数を呼び出します。  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActive`  
 キャプション バーまたはアイコンが必要な場合、アクティブまたは非アクティブの状態を示すために変更するように指定します。 `bActive`パラメーターは**TRUE**アクティブなキャプションまたはアイコンが描画される場合。 **FALSE**の非アクティブなキャプションまたはアイコン。  
  
### <a name="return-value"></a>戻り値  
 Windows が既定の処理を続ける場合は 0 以外。キャプション バーまたはアイコンが非アクティブ化されるようにするのには 0。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、タイトル バー、タイトル バーを描画のアクティブなカラーでテキスト場合`bActive`は**TRUE**との非アクティブなカラーで場合`bActive`は**FALSE**です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onnccalcsize"></a>  CWnd::OnNcCalcSize  
 フレームワークは、クライアント領域の位置とサイズを計算する必要がある場合に、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcCalcSize(
    BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS* lpncsp);
```  
  
### <a name="parameters"></a>パラメーター  
 `bCalcValidRects`  
 アプリケーションがクライアント領域のどの部分には、有効な情報が含まれています。 を指定する必要があるかどうかを指定します。 Windows は、有効な情報を新しいクライアント領域内の指定した領域にコピーされます。 このパラメーターが場合**TRUE**、クライアント領域のどの部分が有効では、アプリケーションで指定する必要があります。  
  
 `lpncsp`  
 指す、 [NCCALCSIZE_PARAMS](../../mfc/reference/nccalcsize-params-structure.md)アプリケーションは、新しいサイズと位置の計算に使用できる情報を格納するデータ構造、`CWnd`四角形 (クライアント領域、罫線、キャプション、スクロール バー、およびなどを含む).  
  
### <a name="remarks"></a>コメント  
 このメッセージを処理することで、アプリケーションは、サイズまたはウィンドウの位置が変更されたときに、ウィンドウのクライアント領域の内容を制御できます。  
  
 値に関係なく`bCalcValidRects`、によって指定された配列内の最初の四角形、 **rgrc**の構造体のメンバー、`NCCALCSIZE_PARAMS`構造には、ウィンドウの座標が含まれています。 子ウィンドウの座標は、親ウィンドウのクライアント領域と相対的はします。 最上位のウィンドウの座標は、画面の座標です。 アプリケーションを変更する必要があります、 **rgrc [0]** クライアント領域の位置とサイズを反映するように四角形。  
  
 **Rgrc [1]** と**rgrc [2]** 四角形は有効な場合にのみ、`bCalcValidRects`は**TRUE**です。 ここで、 **rgrc [1]** が移動またはサイズを変更する前に、四角形は、ウィンドウの座標を格納します。 **Rgrc [2]** ウィンドウが移動する前に、四角形がウィンドウのクライアント領域の座標を格納します。 すべての座標は、親ウィンドウまたは画面です。  
  
 既定の実装 (スクロール バー、メニューのおよびなどの立ち会いの下)、ウィンドウの特性に基づくクライアント領域のサイズが計算され、結果`lpncsp`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onnccreate"></a>  CWnd::OnNcCreate  
 フレームワークより前のバージョンには、このメンバー関数、 [WM_CREATE](#oncreate)メッセージ、`CWnd`オブジェクトが最初に作成します。  
  
```  
afx_msg BOOL OnNcCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCreateStruct`  
 指す、 [CREATESTRUCT](../../mfc/reference/createstruct-structure.md)のデータが構造体`CWnd`です。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、非クライアント領域を作成します。 エラーが発生した場合は 0**作成**関数が返す**エラー**ここでします。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncdestroy"></a>  CWnd::OnNcDestroy  
 非クライアント領域が破棄されるとは、最後のメンバー関数と呼ばれる Windows のウィンドウが破棄されるときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnNcDestroy();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装がいくつかのクリーンアップを実行し、仮想メンバー関数を呼び出す[PostNcDestroy](#postncdestroy)です。  
  
 オーバーライド`PostNcDestroy`など、独自のクリーンアップを実行するかどうか、**削除**操作します。 オーバーライドする場合`OnNcDestroy`、呼び出す必要があります`OnNcDestroy`基底クラスに、ウィンドウが解放されるを内部的に割り当てられたメモリを確認してください。  
  
##  <a name="onnchittest"></a>  CWnd::OnNcHitTest  
 フレームワークの場合は、このメンバー関数を呼び出します、`CWnd`カーソルを格納しているオブジェクト (または`CWnd`オブジェクトの使用、 [SetCapture](#setcapture)マウス入力をキャプチャするメンバー関数を)、マウスを移動するたびにします。  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 カーソルの x 座標と y 座標が含まれています。 これらの座標は、常に、画面の座標です。  
  
### <a name="return-value"></a>戻り値  
 マウスのヒット テストのいずれかにより、以下に示す値が列挙されます。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onnclbuttondblclk"></a>  CWnd::OnNcLButtonDblClk  
 非クライアント領域内にカーソルが中に、ユーザーがマウスの左ボタンをダブルクリックすると、フレームワークはこのメンバー関数を呼び出します`CWnd`です。  
  
```  
afx_msg void OnNcLButtonDblClk(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 該当する場合、 [WM_SYSCOMMAND](#onsyscommand)メッセージを送信します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onnclbuttondown"></a>  CWnd::OnNcLButtonDown  
 非クライアント領域内にカーソルが中に、ユーザーがマウスの左ボタンを押したときに、フレームワークはこのメンバー関数を呼び出す、`CWnd`オブジェクト。  
  
```  
afx_msg void OnNcLButtonDown(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 該当する場合、[位置である](#onsyscommand)が送信されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、フレームワークが受信したメッセージを受信したときにパラメーターを反映します。この関数の基本クラスの実装を呼び出すと、その実装は、関数を指定するパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onnclbuttonup"></a>  CWnd::OnNcLButtonUp  
 フレームワークは、非クライアント領域内にカーソルが中に、ユーザーがマウスの左ボタンを離すと、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcLButtonUp(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、 [WM_SYSCOMMAND](#onsyscommand)が送信されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncmbuttondblclk"></a>  CWnd::OnNcMButtonDblClk  
 フレームワークは、非クライアント領域内にカーソルが中に、ユーザーがマウスの中央ボタンをダブルクリックすると、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcMButtonDblClk(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncmbuttondown"></a>  CWnd::OnNcMButtonDown  
 フレームワークは、非クライアント領域内にカーソルが中に、ユーザーがマウスの中央ボタンを押したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcMButtonDown(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncmbuttonup"></a>  CWnd::OnNcMButtonUp  
 フレームワークは、非クライアント領域内では、カーソルがある状態でマウスの中央ボタンを離したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcMButtonUp(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncmousehover"></a>  CWnd::OnNcMouseHover  
 呼び出す前に指定された期間のウィンドウの非クライアント領域にカーソルを合わせると、フレームワークはこのメンバー関数を呼び出します[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)です。  
  
```  
afx_msg void OnNcMouseHover(
    UINT nHitTest,   
    CPoint point);  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nHitTest`|によって返されるヒット テスト値、 [CWnd::DefWindowProc](#defwindowproc)関数の処理の結果として、 [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618)メッセージ。|  
|[入力] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)を指定するオブジェクト、 *x*と*y*画面の左上隅を基準としたカーソルの座標。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_NCMOUSEHOVER](http://msdn.microsoft.com/library/windows/desktop/ms645625)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncmouseleave"></a>  CWnd::OnNcMouseLeave  
 呼び出す前に指定されたウィンドウの非クライアント領域をカーソルが離れるときに、フレームワークはこのメンバー関数を呼び出します[TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265)です。  
  
```  
afx_msg void OnNcMouseLeave();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_NCMOUSELEAVE](http://msdn.microsoft.com/library/windows/desktop/ms645626)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncmousemove"></a>  CWnd::OnNcMouseMove  
 フレームワークは、非クライアント領域内でカーソルが移動したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcMouseMove(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 該当する場合、 [WM_SYSCOMMAND](#onsyscommand)メッセージを送信します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncpaint"></a>  CWnd::OnNcPaint  
 フレームワークは、非クライアント領域を描画する必要があるときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcPaint();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装では、ウィンドウ フレームを描画します。  
  
 アプリケーションでは、この関数をオーバーライドでき、独自のカスタム ウィンドウ フレームを描画することができます。 フレームの図形が変更される場合でも、クリッピング領域が長方形で、常にします。  
  
##  <a name="onncrbuttondblclk"></a>  CWnd::OnNcRButtonDblClk  
 非クライアント領域内にカーソルが中に、ユーザーがマウスの右ボタンをダブルクリックすると、フレームワークはこのメンバー関数を呼び出します`CWnd`です。  
  
```  
afx_msg void OnNcRButtonDblClk(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncrbuttondown"></a>  CWnd::OnNcRButtonDown  
 フレームワークは、非クライアント領域内にカーソルが中に、ユーザーがマウスの右ボタンを押したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcRButtonDown(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncrbuttonup"></a>  CWnd::OnNcRButtonUp  
 フレームワークは、非クライアント領域内にカーソルが中に、ユーザーがマウスの右ボタンを離すと、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcRButtonUp(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHitTest`  
 指定します、[ヒット テスト コード](#onnchittest)です。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 `point`  
 指定します、 `CPoint` x と y を含むオブジェクトのカーソル位置の画面座標。 これらの座標は、常に、画面の左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncrenderingchanged"></a>  CWnd::OnNcRenderingChanged  
 フレームワークは、非クライアント領域のレンダリングのポリシーが変更されたときに、このメンバーを呼び出します。  
  
```  
afx_msg void OnNcRenderingChanged(BOOL bIsRendering);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `bIsRendering`|`true` ウィンドウの非クライアント領域のデスクトップ ウィンドウ マネージャー (DWM) のレンダリングが有効になっている場合`false`レンダリングが無効になっている場合。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_DWMNCRENDERINGCHANGED](http://msdn.microsoft.com/library/windows/desktop/dd388200)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncxbuttondblclk"></a>  CWnd::OnNcXButtonDblClk  
 カーソルがウィンドウの非クライアント領域の間 XBUTTON1 または XBUTTON2 をユーザーがダブルクリックすると、フレームワークはこのメンバー関数を呼び出します。  
  
```  
void OnNcXButtonDblClk(
    short nHitTest,   
    UINT nButton,   
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nHitTest`|によって返されるヒット テスト値、 [CWnd::DefWindowProc](#defwindowproc)関数の処理の結果として、 [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618)メッセージ。|  
|[入力] `nButton`|値`XBUTTON1`場合は、最初の Microsoft Intellimouse X ボタンがダブルクリックされたときに、または`XBUTTON2`場合、2 つ目の X ボタンがダブルクリックされました。|  
|[入力] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)を指定するオブジェクト、 *x*と*y*クライアント領域の左上隅を基準としたカーソルの座標。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_XBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms646244)通知で、Windows SDK に記載されています。 このメッセージは、カーソルを含むウィンドウに通知されます。 ウィンドウがマウスをキャプチャしていた場合、このメッセージは送信されません。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncxbuttondown"></a>  CWnd::OnNcXButtonDown  
 フレームワークは、カーソルがウィンドウの非クライアント領域であり、マウスの XBUTTON1 または XBUTTON2 をユーザーが押したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcXButtonDown(
    short nHitTest,   
    UINT nButton,   
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nHitTest`|によって返されるヒット テスト値、 [CWnd::DefWindowProc](#defwindowproc)関数の処理の結果として、 [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618)メッセージ。|  
|[入力] `nButton`|値`XBUTTON1`最初のマウスの X ボタンが押された場合または`XBUTTON2`場合、2 つ目の X ボタンが押されました。|  
|[入力] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)を指定するオブジェクト、 *x*と*y*画面の左上隅を基準としたカーソルの座標。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_NCXBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645632)通知で、Windows SDK に記載されています。 このメッセージは、カーソルを含むウィンドウに通知されます。 ウィンドウがマウスをキャプチャしていた場合、このメッセージは送信されません。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onncxbuttonup"></a>  CWnd::OnNcXButtonUp  
 カーソルがウィンドウの非クライアント領域であり、マウスの XBUTTON1 または XBUTTON2 をユーザーが離したときに、フレームワークはこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnNcXButtonUp(
    short nHitTest,   
    UINT nButton,   
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nHitTest`|によって返されるヒット テスト値、 [CWnd::DefWindowProc](#defwindowproc)関数の処理の結果として、 [WM_NCHITTEST](http://msdn.microsoft.com/library/windows/desktop/ms645618)メッセージ。|  
|[入力] `nButton`|値`XBUTTON1`最初のマウスの X ボタンを放した場合は、または`XBUTTON2`場合、2 つ目 X ボタンが離されます。|  
|[入力] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)を指定するオブジェクト、 *x*と*y*画面の左上隅を基準としたカーソルの座標。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_NCXBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646240)通知で、Windows SDK に記載されています。 このメッセージは、カーソルを含むウィンドウに通知されます。 ウィンドウがマウスをキャプチャしていた場合、このメッセージは送信されません。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onnextmenu"></a>  CWnd::OnNextMenu  
 フレームワークはこのメンバー関数を呼び出して、メニュー バーとシステム メニュー間を切り替えるに右または左方向キーを使用する場合にするとします。  
  
```  
afx_msg void OnNextMenu(
    UINT nKey,  
    LPMDINEXTMENU lpMdiNextMenu);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nKey`|どの修飾子キーが押されたかを示すフラグのビットごとの組み合わせ (OR)。 たとえば、`MK_CONTROL`フラグは、CTRL キーが押されたことを示します。<br /><br /> フラグの一覧を参照してくださいで「メッセージのパラメーター」subheading[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)です。|  
|[入力] `lpMdiNextMenu`|ポインター、 [MDINEXTMENU](http://msdn.microsoft.com/library/windows/desktop/ms647561)アクティブにするのには、メニューに関する情報を格納する構造体。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_UNINITMENUPOPUP](http://msdn.microsoft.com/library/windows/desktop/ms647614)通知で、Windows SDK に記載されています。 このメッセージに応答してで、アプリケーションを設定できます、`hmenuNext`のメンバー、 [MDINEXTMENU](http://msdn.microsoft.com/library/windows/desktop/ms647561)に切り替えるには、メニューを指定する構造体および`hwndNext`] メニューの [通知メッセージを受信するウィンドウを指定するにはメンバー.  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onnotify"></a>  CWnd::OnNotify  
 フレームワークは、コントロールのイベントが発生したこと、またはコントロールには、ある種の情報が必要なコントロールの親ウィンドウに通知するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL OnNotify(
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `wParam`  
 メッセージがコントロールからの場合は、メッセージを送信するコントロールを識別します。 それ以外の場合、`wParam`は 0 です。  
  
 `lParam`  
 通知メッセージへのポインター ( **NMHDR**) 通知コードおよびその他の情報を含む構造体。 このパラメーターを持つより大きな構造体をポイントするいくつかの通知メッセージについて、 **NMHDR**構造はその最初のメンバーとして。  
  
 `pResult`  
 ポインター、 **LRESULT**メッセージが処理される場合、結果コードを格納する変数。  
  
### <a name="return-value"></a>戻り値  
 アプリケーションがこのメッセージを処理する場合は 0 以外を返しますそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `OnNotify` コントロールの通知のメッセージ マップを処理します。  
  
 このメンバー関数を処理する派生クラスでオーバーライド、 **WM_NOTIFY**メッセージ。 上書きがないメッセージ マップが処理しない限り、基本クラス`OnNotify`と呼びます。  
  
 WM_NOTIFY メッセージの詳細については、テクニカル ノート 61 (TN061) を参照してください。 [ON_NOTIFY メッセージと WM_NOTIFY メッセージ](../../mfc/tn061-on-notify-and-wm-notify-messages.md)です。 目的に関連するトピックが記載されている場合もあります。[制御トピック](../../mfc/controls-mfc.md)、および TN062 [Windows コントロールへのメッセージ リフレクション](../../mfc/tn062-message-reflection-for-windows-controls.md)です。  
  
##  <a name="onnotifyformat"></a>  CWnd::OnNotifyFormat  
 フレームワークは、現在のウィンドウが WM_NOTIFY 通知メッセージで ANSI または Unicode 構造体を受け入れるかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
afx_msg UINT OnNotifyFormat(
    CWnd* pWnd,   
    UINT nCommand);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pWnd`|ポインター、`CWnd`を送信するウィンドウを表すオブジェクト、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージ。<br /><br /> このパラメーターには、コントロールへのポインターがある場合、`nCommand`パラメーターは`NF_QUERY`、またはコントロールの親ウィンドウへのポインター場合`nCommand`は`NF_REQUERY`します。|  
|[入力] `nCommand`|特殊化したコマンドの値、 **WM_NOTIFY**メッセージ。 次の値を指定できます。<br /><br /> - `NF_QUERY` -<br />     メッセージは、クエリで ANSI または Unicode 構造体を使用するかどうかを決定する**WM_NOTIFY**メッセージ。 このメッセージは送信コントロールから親ウィンドウに、コントロール、およびへの応答の作成時に、`NF_REQUERY`このメッセージの形式です。<br />- `NF_REQUERY` -<br />     メッセージが要求を送信するコントロールを`NF_QUERY`親ウィンドウには、このメッセージの形式です。 この要求は、親ウィンドウから送信され、クエリを再実行で使用する構造体の型は、親コントロールを要求する**WM_NOTIFY**メッセージ。 場合、`nCommand`パラメーターは`NF_REQUERY`、戻り値は、再クエリ操作の結果。|  
  
### <a name="return-value"></a>戻り値  
  
|戻り値|説明|  
|------------------|-------------|  
|`NFR_ANSI`|ANSI 構造体を使用する必要があります**WM_NOTIFY**コントロールによって送信されるメッセージ。|  
|`NFR_UNICODE`|使用する必要があります構造体は Unicode **WM_NOTIFY**コントロールによって送信されるメッセージ。|  
|0|エラーが発生しました。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_NOTIFYFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb775584)通知で、Windows SDK に記載されています。 **WM_NOTIFY**メッセージが、共通のコントロールを親ウィンドウから、その親ウィンドウへのコモン コントロールから送信されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onpaint"></a>  CWnd::OnPaint  
 フレームワークは、Windows またはアプリケーションは、アプリケーションのウィンドウの一部を再描画する要求を行うときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnPaint();
```  
  
### <a name="remarks"></a>コメント  
 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145137)メッセージが送信されるときに、[と](#updatewindow)または[RedrawWindow](#redrawwindow)メンバー関数が呼び出されます。  
  
 ウィンドウには、呼び出しの結果の内部ペイント メッセージが表示される、`RedrawWindow`メンバー関数が、 **RDW_INTERNALPAINT**フラグが設定されます。 この場合、ウィンドウは更新領域を持たない場合があります。 アプリケーションを呼び出す必要があります、 [GetUpdateRect](#getupdaterect)ウィンドウが更新領域を持つかどうかを調べます。 場合`GetUpdateRect`アプリケーションは、0 を返します呼び出す必要はありません、 [BeginPaint](#beginpaint)と[EndPaint](#endpaint)メンバー関数。  
  
 必要な内部再描画するかを探してその内部データ構造で各更新を確認するアプリケーションの責任である`WM_PAINT`ために、メッセージ、`WM_PAINT`を呼び出すと、無効な領域の両方でメッセージが原因として可能性がありますが、`RedrawWindow`メンバー関数が、 **RDW_INTERNALPAINT**フラグが設定されます。  
  
 内部`WM_PAINT`メッセージは、Windows を一度だけ送信されます。 内部の後に`WM_PAINT`によってウィンドウにメッセージが送信される、`UpdateWindow`メンバー関数をそれ以上`WM_PAINT`メッセージが送信または、まで、またはウィンドウが無効になるまでのポスト、`RedrawWindow`メンバー関数は、でもう一度呼び出されます。**RDW_INTERNALPAINT**フラグが設定されます。  
  
 ドキュメント/ビュー アプリケーションのイメージのレンダリングについては、次を参照してください。[詳細](../../mfc/reference/cview-class.md#ondraw)です。  
  
 使用しての詳細については**WM_Paint**、Windows SDK の次のトピックを参照してください。  
  
- [WM_PAINT メッセージ](http://msdn.microsoft.com/library/windows/desktop/dd145137)  
  
- [WM_PAINT メッセージを使用してください。](http://msdn.microsoft.com/library/windows/desktop/dd145193)  
  
##  <a name="onpaintclipboard"></a>  CWnd::OnPaintClipboard  
 クリップボード所有者の `OnPaintClipboard` メンバー関数は、クリップボード所有者がクリップボードに `CF_OWNERDISPLAY` 形式でデータを格納したことによりクリップボード ビューアーのクライアント領域を再描画する必要があるときにクリップボード ビューアーによって呼び出されます。  
  
```  
afx_msg void OnPaintClipboard(
    CWnd* pClipAppWnd,  
    HGLOBAL hPaintStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `pClipAppWnd`  
 クリップボード アプリケーション ウィンドウへのポインターを指定します。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
 *hPaintStruct*  
 識別、 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)を描画するクライアント領域のどの部分を定義するデータ構造です。  
  
### <a name="remarks"></a>コメント  
 クライアント領域全体またはその一部だけが必要か再描画するためには、クリップボード所有者がで指定された描画領域の寸法を比較する必要があります、 **rcpaint**のメンバー、`PAINTSTRUCT`ディメンションに構造体最新で指定された[OnSizeClipboard](#onsizeclipboard)メンバー関数の呼び出しです。  
  
 `OnPaintClipboard` 使用する必要があります、 [GlobalLock](http://msdn.microsoft.com/library/windows/desktop/aa366584) Windows 関数を含むメモリをロックする、`PAINTSTRUCT`データ構造体およびそのメモリをロック解除、 [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows 関数が終了する前にします。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onpalettechanged"></a>  CWnd::OnPaletteChanged  
 フレームワークは、入力フォーカスがあるウィンドウが、システム パレットを変更され、論理パレットを認識した後に、すべてのトップ レベル ウィンドウに対してこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnPaletteChanged(CWnd* pFocusWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFocusWnd`  
 変更するシステム パレットの原因となったウィンドウへのポインターを指定します。 ポインターは、一時的な場合があり、保存されません。  
  
### <a name="remarks"></a>コメント  
 この呼び出しでは、ウィンドウをその論理パレットを認識し、クライアント領域を更新するカラー パレットを使用する入力フォーカスを持たない。  
  
 `OnPaletteChanged`メンバー関数はすべての最上位レベルとオーバー ラップ ウィンドウ、システム パレットを変更し、発生した 1 つを含む、`WM_PALETTECHANGED`メッセージを送信します。 任意の子ウィンドウは、カラー パレットを使用している場合、このメッセージを渡す必要があります。  
  
 無限ループを避けるためには、ウィンドウはならないことに注意してパレットが判断した場合を除き、`pFocusWnd`自体へのポインターが含まれていません。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onpaletteischanging"></a>  CWnd::OnPaletteIsChanging  
 フレームワークは、アプリケーションが論理パレットを実現しようとしていることをアプリケーションに通知するためにこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnPaletteIsChanging(CWnd* pRealizeWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRealizeWnd*  
 論理パレットを実現しようとしているウィンドウを指定します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onparentnotify"></a>  CWnd::OnParentNotify  
 親の`OnParentNotify`メンバー関数は、フレームワークによって子ウィンドウが作成または破棄されるとき、またはカーソルが子ウィンドウの上があり、ユーザーがマウス ボタンをクリックします。  
  
```  
afx_msg void OnParentNotify(
    UINT message,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 イベントを示す、親、通知を送信して、子ウィンドウの識別子。 イベントは、の下位ワード`message`です。 場合、イベントは`WM_CREATE`または`WM_DESTROY`の上位ワード`message`; の子ウィンドウの識別子は、それ以外の場合、高位の単語は定義されていません。 イベント (の下位ワード`message`) これらの値のいずれかを指定できます。  
  
- `WM_CREATE` 子ウィンドウを作成しています。  
  
- `WM_DESTROY` 子ウィンドウを破棄しています。  
  
- `WM_LBUTTONDOWN` ユーザーが子ウィンドウの上にマウス カーソルを配置し、マウスの左ボタンをクリックします。  
  
- `WM_MBUTTONDOWN` ユーザーが子ウィンドウの上にマウス カーソルを配置し、マウスの中央ボタンをクリックします。  
  
- `WM_RBUTTONDOWN` ユーザーが子ウィンドウの上にマウス カーソルを配置し、マウスの右ボタンをクリックします。  
  
 `lParam`  
 場合のイベント (下位ワード)`message`は`WM_CREATE`または`WM_DESTROY`、`lParam`子ウィンドウのウィンドウ ハンドルを指定以外の場合`lParam`x と y を含む、カーソルの座標。 X 座標が下位ワードであり、高位の word では y 座標。  
  
### <a name="remarks"></a>コメント  
 子ウィンドウが作成されるとき、システムは`OnParentNotify`直前に、[作成](#create)ウィンドウを作成するメンバー関数を返します。 子ウィンドウが破棄されるときに、システム コール`OnParentNotify`処理を行う、ウィンドウを破棄する前にします。  
  
 `OnParentNotify` トップレベル ウィンドウを含む子ウィンドウのすべての先祖のウィンドウに対して呼び出されます。  
  
 すべての子ウィンドウがあるものを除く、 [WS_EX_NOPARENTNOTIFY](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)スタイルは親ウィンドウにこのメッセージを送信します。 既定では、ダイアログ ボックスの子ウィンドウがある、 **WS_EX_NOPARENTNOTIFY**子ウィンドウは、このスタイルを呼び出して作成された場合を除き、スタイルを設定、 [CreateEx](#createex)メンバー関数。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onpowerbroadcast"></a>  CWnd::OnPowerBroadcast  
 フレームワークは、電源管理イベントが発生したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg UINT OnPowerBroadcast(
    UINT nPowerEvent,   
    UINT nEventData);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nPowerEvent`|電源管理イベントです。|  
|[入力] `nEventData`|イベントに固有のデータ。|  
  
### <a name="return-value"></a>戻り値  
 イベントが、要求の場合は、返す`true`、要求を許可または`BROADCAST_QUERY_DENY`要求を拒否します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) Windows SDK で説明するメッセージ。  
  
 `nPowerEvent`など、バッテリの電力が少ない、電源の状態が変更された、操作を中断するアクセス許可を要求または拒否されると、操作が自動的に再開イベント、システムが、操作を中断またはパラメーターにイベントを指定します中断後で操作を再開します。 `nEventData`パラメーターは通常使用されません。 詳細については、次を参照してください。、`wParam`と`lParam`のパラメーター、 [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247)メッセージ。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onquerydragicon"></a>  CWnd::OnQueryDragIcon  
 フレームワークは、そのクラスに対して定義されているアイコンがない最小化 (アイコン化) ウィンドウでこのメンバー関数を呼び出します。  
  
```  
afx_msg HCURSOR OnQueryDragIcon();
```  
  
### <a name="return-value"></a>戻り値  
 下位ワードにカーソルまたはアイコンのハンドルを含むダブルワード値です。 カーソルまたはアイコン ディスプレイ ドライバーの解像度と互換性がある必要があります。 アプリケーションが返された場合**NULL**既定のカーソルが表示されます。 既定の戻り値は**NULL**です。  
  
### <a name="remarks"></a>コメント  
 システムでは、ユーザーが最小化されたウィンドウをドラッグ中に表示されるカーソルを取得するには、この呼び出しを使用します。 アプリケーションでは、アイコンまたはカーソルのハンドルを返します、システムにより白黒に変換します。 アプリケーションがハンドルを返す場合、ハンドル モノクロ カーソルまたはディスプレイ ドライバーの解像度と互換性のあるアイコンを識別する必要があります。 アプリケーションが呼び出すことができます、 [CWinApp::LoadCursor](../../mfc/reference/cwinapp-class.md#loadcursor)または[CWinApp::LoadIcon](../../mfc/reference/cwinapp-class.md#loadicon)メンバー関数の実行可能ファイル内のリソースからカーソルまたはアイコンを読み込むと、このハンドルを取得します。  
  
##  <a name="onqueryendsession"></a>  CWnd::OnQueryEndSession  
 ユーザーが Windows セッションまたはアプリケーションを呼び出すときに終了するときに、フレームワークがこのメンバー関数を呼び出す、[したとき](http://msdn.microsoft.com/library/windows/desktop/aa376867)Windows の機能です。  
  
```  
afx_msg BOOL OnQueryEndSession();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションで簡単にシャット ダウンできます; 場合 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 任意のアプリケーションでは、0 が返された場合、Windows セッションは終了しません。 Windows には、呼び出し元が停止する`OnQueryEndSession`1 つのアプリケーションは 0 を返しますを送信すると、すぐ、 [WM_ENDSESSION](#onendsession)のパラメーター値を持つメッセージ**FALSE**返したするあらゆるアプリケーション用。  
  
##  <a name="onquerynewpalette"></a>  CWnd::OnQueryNewPalette  
 フレームワークは、このメンバー関数を呼び出すときに、`CWnd`オブジェクトが入力フォーカスを受け取るが提供、`CWnd`フォーカスを受け取ると、論理パレットを実現すること。  
  
```  
afx_msg BOOL OnQueryNewPalette();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CWnd`気付きますその論理パレット以外の場合は 0 です。  
  
##  <a name="onqueryopen"></a>  CWnd::OnQueryOpen  
 フレームワークは、このメンバー関数を呼び出すときに、`CWnd`オブジェクトが最小化され、ユーザーからの要求、`CWnd`元のサイズと位置に復元します。  
  
```  
afx_msg BOOL OnQueryOpen();
```  
  
### <a name="return-value"></a>戻り値  
 アイコンを開くには場合は、0 以外をアイコンが開かれていることを防ぐためには 0 です。  
  
### <a name="remarks"></a>コメント  
 `OnQueryOpen`、`CWnd`必要があります (たとえば、ダイアログ ボックスの作成など) のアクティブ化またはフォーカス変更が原因となるアクションを実行しません。  
  
##  <a name="onqueryuistate"></a>  CWnd::OnQueryUIState  
 ウィンドウのユーザー インターフェイス (UI) 状態を取得するために呼び出されます。  
  
```  
afx_msg UINT OnQueryUIState();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値は**NULL**フォーカス インジケーターとキーボード アクセラレータが可視の場合。 それ以外の場合、戻り値には、次の値の 1 つ以上ができます。  
  
- **UISF_HIDEFOCUS**フォーカス インジケーターは表示されません。  
  
- **UISF_HIDEACCEL**キーボード アクセラレータは非表示にします。  
  
- **UISF_ACTIVE Windows XP:** コントロールは、アクティブなコントロールで使用されるスタイルで描画する必要があります。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [WM_QUERYUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646355)メッセージ、Windows SDK で説明します。  
  
##  <a name="onrawinput"></a>  CWnd::OnRawInput  
 フレームワークは、現在のウィンドウが生の入力を取得したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnRawInput(
    UINT nInputCode,  
    HRAWINPUT hRawInput);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nInputCode`|入力がアプリケーションの中に発生したかどうかを示す入力のコードであるか、フォア グラウンドでします。 どちらの場合、アプリケーションを呼び出す必要があります[CWnd::DefWindowProc](#defwindowproc)システムは、クリーンアップを実行できるようにします。<br /><br /> このパラメーターには、次の値のいずれかを指定できます。<br /><br /> - `RIM_INPUT` 入力は、アプリケーションのフォア グラウンド処理中に発生しました。<br />- `RIM_INPUTSINK` のアプリケーションがフォア グラウンドで入力が発生しました。|  
|[入力] `hRawInput`|ハンドル、 [RAWINPUT](http://msdn.microsoft.com/library/windows/desktop/ms645562)デバイスから生の入力を格納する構造体。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_INPUT](http://msdn.microsoft.com/library/windows/desktop/ms646275)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onrbuttondblclk"></a>  CWnd::OnRButtonDblClk  
 フレームワークは、ユーザーがマウスの右ボタンをダブルクリックすると、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnRButtonDblClk(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 X と y を指定する、カーソルの座標。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 持つ windows のみ、 **CS_DBLCLKS** [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)スタイルを受信できる`OnRButtonDblClk`呼び出しです。 これは、Microsoft Foundation Class ライブラリ内の windows の既定値です。 Windows 呼び出し`OnRButtonDblClk`ユーザー押し続けたときに、リリースでは、もう一度ボタンを押す、マウスの右、システム内で時間制限をダブルクリックします。 マウスの右ボタンをダブルクリックすると、実際に 4 つのイベントを生成: [WM_RBUTTONDOWN](#onrbuttondown)と[WM_RBUTTONUP](#onrbuttonup) 、メッセージ、`OnRButtonDblClk`呼び出し、および別`WM_RBUTTONUP`メッセージの場合に、ボタン解放されます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onrbuttondown"></a>  CWnd::OnRButtonDown  
 フレームワークは、ユーザーがマウスの右ボタンを押したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnRButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_RBUTTON**マウスの右ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 X と y を指定する、カーソルの座標。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onrbuttonup"></a>  CWnd::OnRButtonUp  
 フレームワークは、ユーザーがマウスの右ボタンを離したときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnRButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 各種の仮想キーがダウンしているかどうかを示します。 このパラメーターは、次の値の任意の組み合わせを指定できます。  
  
- **MK_CONTROL** CTRL キーが押された場合に設定します。  
  
- **MK_LBUTTON**マウスの左ボタンがダウンした場合に設定します。  
  
- **MK_MBUTTON**マウスの中央ボタンがダウンした場合に設定します。  
  
- **MK_SHIFT** SHIFT キーを押した場合に設定します。  
  
 `point`  
 X と y を指定する、カーソルの座標。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onregisteredmousewheel"></a>  CWnd::OnRegisteredMouseWheel  
 フレームワークは、ユーザーがマウス ホイールを回転し、ホイールの次のノッチを検出すると、このメンバー関数を呼び出します。  
  
```  
afx_msg LRESULT OnRegisteredMouseWheel(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `wParam`  
 ポインターの水平方向の位置。  
  
 `lParam`  
 ポインターの垂直方向の位置。  
  
### <a name="return-value"></a>戻り値  
 この時点で意味のないです。 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オーバーライドされない限り、`OnRegisteredMouseWheel`への呼び出し、適切なウィンドウ (フォーカスを持つ親ウィンドウ) に、メッセージをルーティング、 [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617)そのウィンドウのハンドラー。  
  
 独自のメッセージのルーティングを提供するか、マウス ホイールの動作を変更するのには、このメンバー関数をオーバーライドします。  
  
> [!NOTE]
> `OnRegisteredMouseWheel` Windows 95/98 および Windows NT 3.51 メッセージを処理します。 Windows NT 4.0 メッセージ処理では、使用[OnMouseWheel](#onmousewheel)です。  
  
##  <a name="onrenderallformats"></a>  CWnd::OnRenderAllFormats  
 クリップボード所有者の`OnRenderAllFormats`オーナー アプリケーションが破棄されるときに、メンバー関数が、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnRenderAllFormats();
```  
  
### <a name="remarks"></a>コメント  
 クリップボード オーナーが、すべての形式を生成できるは、クリップボードに呼び出すことによって各形式のデータ ハンドルを渡すデータを表示する必要があります、[受け取り](http://msdn.microsoft.com/library/windows/desktop/ms649051)Windows の機能です。 これにより、データを描画するアプリケーションが破棄される場合でも、クリップボードにはで有効なデータが含まれています。 アプリケーションを呼び出す必要があります、 [OpenClipboard](#openclipboard)メンバー関数は呼び出しの前に、[受け取り](http://msdn.microsoft.com/library/windows/desktop/ms649051)Windows 関数と呼び出し、 [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Windowsその後の関数。  
  
##  <a name="onrenderformat"></a>  CWnd::OnRenderFormat  
 クリップボード所有者の`OnRenderFormat`遅延レンダリングされた固有フォーマットを描画する必要がある場合、メンバー関数が、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnRenderFormat(UINT nFormat);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFormat`  
 クリップボードの形式を指定します。  
  
### <a name="remarks"></a>コメント  
 受信者がその形式でデータを表示され、呼び出すことによって、クリップボードに渡すこと必要があります、[受け取り](http://msdn.microsoft.com/library/windows/desktop/ms649051)Windows の機能です。  
  
 呼び出す必要はありません、`OpenClipboard`メンバー関数または**CloseClipboard**内からの Windows 関数`OnRenderFormat`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsessionchange"></a>  CWnd::OnSessionChange  
 フレームワークは、セッション状態が変更されたアプリケーションに通知するには、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnSessionChange(
    UINT nSessionState,   
    UINT nId);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nSessionState`|ステータス コードでは、セッション状態の変更について説明します。|  
|[入力] `nId`|セッション識別子です。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_WTSSESSION_CHANGE](http://msdn.microsoft.com/library/aa383828)通知で、Windows SDK に記載されています。  
  
 `nSessionState`パラメーターを指定する、セッションが接続されているか、コンソールまたはリモート ターミナルから切断されている、ユーザーがログオンまたはログオフ、セッションがロックまたはロック解除、またはセッションがリモート制御状態を変更します。 詳細については、次を参照してください。、`wParam`のパラメーターは、 [WM_WTSSESSION_CHANGE](http://msdn.microsoft.com/library/aa383828)メッセージ。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsetcursor"></a>  CWnd::OnSetCursor  
 マウス入力がキャプチャされていないと、マウスのカーソルの移動が原因でこのメンバー関数をフレームワーク、`CWnd`オブジェクト。  
  
```  
afx_msg BOOL OnSetCursor(
    CWnd* pWnd,  
    UINT nHitTest,  
    UINT message);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを含むウィンドウへのポインターを指定します。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
 `nHitTest`  
 指定します、[ヒット テスト](#onnchittest)市外局番します。 ヒット テストでは、カーソルの位置を決定します。  
  
 `message`  
 マウスのメッセージ番号を指定します。  
  
### <a name="return-value"></a>戻り値  
 さらに処理、または続行する場合は 0 を停止するように 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 既定の実装を呼び出す親ウィンドウの`OnSetCursor`処理する前にします。 親ウィンドウに返されます場合**TRUE**、さらに処理が停止します。 親ウィンドウを呼び出して、親ウィンドウを制御、子ウィンドウで、カーソルの設定。  
  
 既定の実装設定カーソル矢印がクライアント領域にない場合に、またはクラスが登録されているカーソルにである場合。  
  
 場合`nHitTest`は**HTERROR**と`message`マウスのボタンダウン メッセージ、 **MessageBeep**メンバー関数が呼び出されます。  
  
 `message`パラメーターが 0 と`CWnd`メニュー モードに入ります。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsetfocus"></a>  CWnd::OnSetFocus  
 フレームワークは、入力フォーカスを受け取った後にこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnSetFocus(CWnd* pOldWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pOldWnd*  
 含まれています、`CWnd`が入力フォーカスを失ったオブジェクト (あります**NULL**)。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 カレットを表示する`CWnd`この時点で、適切なカーソル関数を呼び出す必要があります。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsettingchange"></a>  CWnd::OnSettingChange  
 フレームワークによって`OnSettingChange`Win32 次の関数は、システム全体の設定を変更したときにすべてのトップ レベル ウィンドウに対してです。  
  
```  
afx_msg void OnSettingChange(
    UINT uFlags,  
    LPCTSTR lpszSection);
```  
  
### <a name="parameters"></a>パラメーター  
 `uFlags`  
 システムがの結果としてメッセージを送信すると、**次**呼び出し、このパラメーターは、system パラメーターが変更されたことを示すフラグ。 値の一覧は、次を参照してください。[次](http://msdn.microsoft.com/library/windows/desktop/ms724947)Windows SDK に含まれています。 アプリケーションでは、メッセージを送信するときに、このパラメーターは 0 を指定する必要があります。  
  
 `lpszSection`  
 変更されたセクションの名前を指定する文字列へのポインター。 (文字列は含まれませんセクション名を囲む角かっこ。)  
  
### <a name="remarks"></a>コメント  
 アプリケーションは、システム パラメーターを変更があったときと Windows のコントロール パネルで設定を変更した場合、メッセージが送信されます、すべての最上位ウィンドウにメッセージを送信する必要があります。  
  
 **ON_WM_SETTINGCHANGE**メッセージがに似ていますが、 **ON_WM_WININICHANGE**メッセージと、次の相違点。  
  
-   使用して**ON_WM_SETTINGCHANGE** Windows NT 4.0 以降を実行している場合、または Windows 95/98 です。  
  
-   使用して**ON_WININICHANGE** 3.51 または古い Windows NT を実行する場合。 このメッセージは廃止されました。  
  
 これらのマクロの 1 つだけは、マップには、メッセージが必要です。 Windows 95/98 と Windows NT 4.0 の両方に対して機能するプログラムを作成するには、書き込みのハンドラーを**ON_WM_SETTINGCHANGE**です。 Windows NT 3.51 の下で、ハンドラーが呼び出されます`OnSettingChange`と`uFlags`し、常に 0 になります。  
  
##  <a name="onshowwindow"></a>  CWnd::OnShowWindow  
 フレームワークは、このメンバー関数を呼び出すときに、`CWnd`オブジェクトが非表示または表示します。  
  
```  
afx_msg void OnShowWindow(
    BOOL bShow,  
    UINT nStatus);
```  
  
### <a name="parameters"></a>パラメーター  
 `bShow`  
 ウィンドウが表示されているかどうかを指定します。 **TRUE**ウィンドウが表示されている場合は**FALSE**場合は、ウィンドウが非表示にします。  
  
 `nStatus`  
 表示されているウィンドウの状態を指定します。 ため、メッセージが送信される場合は 0、`ShowWindow`メンバー関数の呼び出し以外の場合`nStatus`は、次のいずれか。  
  
- **SW_PARENTCLOSING** (アイコン化される) 親ウィンドウを閉じるか、ポップアップ ウィンドウが非表示にします。  
  
- **SW_PARENTOPENING** (表示されている) 親ウィンドウを開くか、ポップアップ ウィンドウが表示されています。  
  
### <a name="remarks"></a>コメント  
 ウィンドウを非表示または時に表示、`ShowWindow`オーバー ラップ ウィンドウを最大化または復元時に、または、オーバー ラップまたはポップアップ ウィンドウが閉じられたときに、メンバー関数が呼び出されます (アイコン化) または開いた (画面に表示されます)。 オーバー ラップ ウィンドウが閉じている場合は、そのウィンドウに関連付けられているすべてのポップアップ ウィンドウが表示されません。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsize"></a>  CWnd::OnSize  
 フレームワークは、ウィンドウのサイズが変更された後に、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnSize(
    UINT nType,  
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>パラメーター  
 `nType`  
 要求されたサイズ変更の種類を指定します。 このパラメーターには、次の値のいずれかを指定できます。  
  
- **SIZE_MAXIMIZED**ウィンドウを最大化されています。  
  
- **SIZE_MINIMIZED**ウィンドウを最小化されています。  
  
- **SIZE_RESTORED**ウィンドウのサイズが変更された、どちらが**SIZE_MINIMIZED**も**SIZE_MAXIMIZED**適用されます。  
  
- **SIZE_MAXHIDE**他のいくつかのウィンドウが最大化されている場合、すべてのポップアップ ウィンドウにメッセージが送信されます。  
  
- **SIZE_MAXSHOW**他のいくつかのウィンドウが元のサイズに復元された場合、メッセージがすべてのポップアップ ウィンドウに送信します。  
  
 `cx`  
 クライアント領域の新しい幅を指定します。  
  
 `cy`  
 クライアント領域の新しい高さを指定します。  
  
### <a name="remarks"></a>コメント  
 場合、 [SetScrollPos](#setscrollpos)または[MoveWindow](#movewindow)から子ウィンドウのメンバー関数が呼び出される`OnSize`、`bRedraw`のパラメーター`SetScrollPos`または`MoveWindow`0 以外に設定する必要があります発生する、`CWnd`に再描画します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#109](../../mfc/reference/codesnippet/cpp/cwnd-class_50.cpp)]  
  
##  <a name="onsizeclipboard"></a>  CWnd::OnSizeClipboard  
 クリップボード所有者の`OnSizeClipboard`メンバー関数は、クリップボード ビューアーによって、クリップボードにデータが含まれている場合、`CF_OWNERDISPLAY`属性と、クリップボード ビューアー ウィンドウのクライアント領域のサイズが変更されました。  
  
```  
afx_msg void OnSizeClipboard(
    CWnd* pClipAppWnd,  
    HGLOBAL hRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pClipAppWnd`  
 クリップボード アプリケーション ウィンドウを識別します。 ポインターは、一時的な場合があり、保存されません。  
  
 *hRect*  
 グローバル メモリ オブジェクトを識別します。 メモリ オブジェクトには、クリップボード オーナーが描画するための領域を指定する RECT データ構造体が含まれています。  
  
### <a name="remarks"></a>コメント  
 `OnSizeClipboard`メンバー関数は null の四角形 (0,0,0,0) を持つ新しいサイズとしてクリップボード アプリケーションがときに破棄されるか、最小化します。 これにより、ディスプレイのリソースを解放する、クリップボード所有者です。  
  
 内で`OnSizeClipboard`、アプリケーションを使用する必要があります、 [GlobalLock](http://msdn.microsoft.com/library/windows/desktop/aa366584) RECT データ構造体を含むメモリをロックする Windows の機能です。 アプリケーションをそのメモリをロック解除、 [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows 関数を生成またはコントロールを返します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsizing"></a>  CWnd::OnSizing  
 フレームワークは、ユーザーには、四角形がサイズ変更を示すためにこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnSizing(
    UINT nSide,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSide`  
 移動するウィンドウの端。  
  
 `lpRect`  
 アドレス、 [CRect](../../atl-mfc-shared/reference/crect-class.md)または[RECT 構造体](../../mfc/reference/rect-structure1.md)アイテムの座標が含まれる。  
  
### <a name="remarks"></a>コメント  
 このメッセージを処理することでアプリケーションをドラッグ四角形の位置とサイズを監視し、必要に応じて、そのサイズや位置を変更します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#110](../../mfc/reference/codesnippet/cpp/cwnd-class_51.cpp)]  
  
##  <a name="onspoolerstatus"></a>  CWnd::OnSpoolerStatus  
 フレームワークは、ジョブが追加またはプリント マネージャーのキューから削除されるたびに、プリント マネージャーからこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnSpoolerStatus(
    UINT nStatus,  
    UINT nJobs);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStatus`  
 指定します、 **SP_JOBSTATUS**フラグ。  
  
 *nJobs*  
 プリント マネージャーのキューに残っているジョブの数を指定します。  
  
### <a name="remarks"></a>コメント  
 この呼び出しでは、参考情報としてのみです。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onstylechanged"></a>  CWnd::OnStyleChanged  
 フレームワークは、このメンバー関数の後、 [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591)関数は、1 つまたは複数のウィンドウのスタイルが変更されます。  
  
```  
afx_msg void OnStyleChanged(
    int nStyleType,  
    LPSTYLESTRUCT lpStyleStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStyleType`  
 ウィンドウの拡張または非拡張スタイルが変更されたかどうかを指定します。 このパラメーターは、次の値の組み合わせを指定できます。  
  
- **GWL_EXSTYLE**ウィンドウの拡張スタイルが変更されました。  
  
- **GWL_STYLE**ウィンドウの非拡張スタイルが変更されました。  
  
 `lpStyleStruct`  
 指す、[持つ](http://msdn.microsoft.com/library/windows/desktop/ms632607)ウィンドウの新しいスタイルを格納する構造体。 アプリケーションは、スタイルを調べることができますが、変更できます。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onstylechanging"></a>  CWnd::OnStyleChanging  
 フレームワークは、このメンバー関数を呼び出すときに、 [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591)関数が 1 つまたは複数のウィンドウのスタイルを変更しようとしています。  
  
```  
afx_msg void OnStyleChanging(
    int nStyleType,  
    LPSTYLESTRUCT lpStyleStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStyleType`  
 ウィンドウの拡張または非拡張スタイルが変更されたかどうかを指定します。 このパラメーターは、次の値の組み合わせを指定できます。  
  
- **GWL_EXSTYLE**ウィンドウの拡張スタイルが変更されました。  
  
- **GWL_STYLE**ウィンドウの非拡張スタイルが変更されました。  
  
 `lpStyleStruct`  
 指す、[持つ](http://msdn.microsoft.com/library/windows/desktop/ms632607)ウィンドウの新しいスタイルを格納する構造体。 アプリケーションでは、スタイルを調べるでき、それらを変更することができます。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsyschar"></a>  CWnd::OnSysChar  
 場合、フレームワークはこのメンバー関数を呼び出します`CWnd`入力フォーカスがあると、 [WM_SYSKEYUP](#onsyskeyup)と[WM_SYSKEYDOWN](#onsyskeydown)メッセージに変換されます。  
  
```  
afx_msg void OnSysChar(
    UINT nChar,  
    UINT nRepCnt,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 コントロール メニュー キーの ASCII 文字のキー コードを指定します。  
  
 `nRepCnt`  
 繰り返し回数 (回数、キーを押しながら、ユーザーの結果として、キーストロークが繰り返されます) を指定します。  
  
 `nFlags`  
 `nFlags`パラメーターは、これらの値を持つことができます。  
  
|[値]|説明|  
|-----------|-------------|  
|0-15|繰り返し回数を指定します。 キーを押しながら、ユーザーの結果として、キーストロークが繰り返される回数を値には.|  
|16-23|スキャン コードを指定します。 値は、製造元 (OEM) によって異なります。|  
|24|キーが拡張 101 または 102 key キーボードに表示される右 ALT および CTRL キーなどの拡張キーであるかどうかを指定します。 拡張キーである場合、値は 1それ以外の場合は 0 です。|  
|25-28|Windows によって内部的に使用します。|  
|29|コンテキストのコードを指定します。 ALT キーを押した状態でキーを押した場合、値は 1それ以外の場合、値は 0 です。|  
|30|以前のキーの状態を指定します。 メッセージを送信すると、またはキーが稼働している場合は 0 を前に、キーがダウンした場合、値は 1 です。|  
|31|遷移の状態を指定します。 場合は、キーが離されたされている、または押されている場合は 0 を値は 1 です。|  
  
### <a name="remarks"></a>コメント  
 コントロール メニュー キーの仮想キー コードを指定します。 (標準の仮想キー コードの一覧は、の Winuser.h を参照してください)  
  
 コンテキストのコードが 0、`WM_SYSCHAR`渡すことができます、 [wm_syschar です](http://msdn.microsoft.com/library/windows/desktop/ms646357)メッセージごとに、 [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows の機能は、システムではなく通常のキー メッセージと同様に処理されます文字のキー。 これにより、アクティブなウィンドウが入力フォーカスを持っていない場合でも、作業中のウィンドウで使用するアクセラレータ キー。  
  
 IBM エンハンス 101 および 102 key キーボード、強化されたキーには右 ALT および右 CTRL キーを押し、キーボードのメイン セクションにアドイン、DEL、HOME、END、PAGEUP、PAGEDOWN、および; テンキーの左側に、クラスター内の矢印キースラッシュ (/) およびテンキーで ENTER キー。 その他の一部のキーボード可能性があります、拡張キー ビット サポートで`nFlags`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsyscolorchange"></a>  CWnd::OnSysColorChange  
 フレームワークは、システム カラーの設定の変更が加えられたときに、すべてのトップ レベル ウィンドウに対してこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnSysColorChange();
```  
  
### <a name="remarks"></a>コメント  
 Windows 呼び出し`OnSysColorChange`システム カラーが変更の影響を受けるすべてのウィンドウ。  
  
 既存のシステム カラーを使用しているブラシを持つアプリケーションをそれらのブラシを削除し、新しいシステム カラーを使用して再作成します。  
  
##  <a name="onsyscommand"></a>  CWnd::OnSysCommand  
 フレームワークは、ユーザーがコントロール メニューからコマンドを選択したときに、またはユーザーが、最大化または最小化ボタンを選択すると、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnSysCommand(
    UINT nID,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 要求されたシステム コマンドの種類を指定します。 このパラメーターは、次の値のいずれかを指定できます。  
  
- **SC_CLOSE**閉じる、`CWnd`オブジェクト。  
  
- **SC_HOTKEY**アクティブ化、`CWnd`アプリケーションで指定されたホット キーに関連付けられているオブジェクト。 下位ワード`lParam`を識別、`HWND`のウィンドウをアクティブにします。  
  
- **SC_HSCROLL**水平方向にスクロールします。  
  
- **SC_KEYMENU**キーストロークによりメニューを取得します。  
  
- **SC_MAXIMIZE** (または**SC_ZOOM**) 最大化、`CWnd`オブジェクト。  
  
- **SC_MINIMIZE** (または**SC_ICON**) 最小化、`CWnd`オブジェクト。  
  
- **SC_MOUSEMENU**取得 メニューの マウス をクリックします。  
  
- **における**移動、`CWnd`オブジェクト。  
  
- **SC_NEXTWINDOW**次のウィンドウに移動します。  
  
- **SC_PREVWINDOW**前のウィンドウに移動します。  
  
- **SC_RESTORE**通常の位置とサイズをウィンドウを復元します。  
  
- **SC_SCREENSAVE**システムの [ブート] セクションで指定されたスクリーン セーバーのアプリケーションを実行します。INI ファイルです。  
  
- **初期状態**サイズ、`CWnd`オブジェクト。  
  
- **SC_TASKLIST** Execute または Windows タスク マネージャーのアプリケーションをアクティブ化します。  
  
- **SC_VSCROLL**垂直方向にスクロールします。  
  
 `lParam`  
 マウスを使用して、コントロール メニュー コマンドが選択されている場合`lParam`カーソルの座標が含まれています。 下位ワードに x 座標が含まれており、高位の単語には、y 座標が含まれています。 それ以外の場合、このパラメーターは使用されません。  
  
- **SC_HOTKEY**アプリケーションで指定されたホット キーに関連付けられているウィンドウをアクティブ化します。 下位ワード`lParam`をアクティブ化するウィンドウを識別します。  
  
- **SC_SCREENSAVE**コントロール パネルの [デスクトップ] セクションで指定されたスクリーン セーバーのアプリケーションを実行します。  
  
### <a name="remarks"></a>コメント  
 既定では、`OnSysCommand`定義済みのアクションの前の表で指定されたコントロール メニュー要求を実行します。  
  
 `WM_SYSCOMMAND`メッセージの 4 つの下位ビット、`nID`パラメーターは、Windows によって内部的に使用されます。 アプリケーションがの値をテストするときに`nID`を持つ値 0xFFF0 を組み合わせる必要があります、`nID`演算を使用して値- と演算子は、正しい結果を取得します。  
  
 コントロールのメニューにメニュー項目を変更できますが、 `GetSystemMenu`、 `AppendMenu`、 `InsertMenu`、および`ModifyMenu`メンバー関数。 コントロールのメニューを変更するアプリケーションを処理する必要があります`WM_SYSCOMMAND`メッセージ、および任意`WM_SYSCOMMAND`にアプリケーションで処理されないメッセージを渡す必要があります`OnSysCommand`です。 コマンドの値がアプリケーションによって追加された任意のアプリケーションで処理する必要がありますに渡されることはできません`OnSysCommand`です。  
  
 渡すことによっていつでも、アプリケーションをシステム コマンドを実行できる、`WM_SYSCOMMAND`メッセージごとに`OnSysCommand`です。  
  
 変換されます (ショートカット) キーの組み合わせ、コントロールのメニュー項目の選択が定義されている`OnSysCommand`呼び出し; キーストロークに変換された他のすべてのアクセラレータ[WM_COMMAND](#oncommand)メッセージ。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsysdeadchar"></a>  CWnd::OnSysDeadChar  
 場合、フレームワークはこのメンバー関数を呼び出して、`CWnd`オブジェクトには、入力フォーカス、 [OnSysKeyUp](#onsyskeyup)または[持つ](#onsyskeydown)メンバー関数が呼び出されます。  
  
```  
afx_msg void OnSysDeadChar(
    UINT nChar,  
    UINT nRepCnt,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 配信不能キーの文字の値を指定します。  
  
 `nRepCnt`  
 繰り返し回数を指定します。  
  
 `nFlags`  
 次の一覧に示すように、スキャン コード、キー遷移コード、前のキーの状態、およびコンテキストのコードを指定します。  
  
|[値]|説明|  
|-----------|-------------|  
|0-7|コード (OEM に依存する値) をスキャンします。 上位ワードの下位バイトをします。|  
|8|ファンクション キーまたはテンキー (拡張キーである場合は 1。 それ以外の場合 0) のキーなどの拡張キー。|  
|9-10|使用しません。|  
|11-12|Windows によって内部的に使用します。|  
|13|コンテキストのコード (キーが押された、ALT キーが保持されている場合は 1。 それ以外の場合 0) です。|  
|14|以前のキー状態 (1 上のキーが 0 の場合、呼び出しの前に、キーがダウンしている場合)。|  
|16|(キーが解放されている場合は 1、押されている場合は 0) の状態に移行します。|  
  
### <a name="remarks"></a>コメント  
 配信不能キーの文字の値を指定します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsyskeydown"></a>  CWnd::OnSysKeyDown  
 場合、`CWnd`オブジェクトが入力フォーカスを`OnSysKeyDown`ユーザーが、ALT キーを押したまま、別のキーを押したときに、メンバー関数が、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnSysKeyDown(
    UINT nChar,  
    UINT nRepCnt,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 押されているキーの仮想キー コードを指定します。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nRepCnt`  
 繰り返し回数を指定します。  
  
 `nFlags`  
 次の一覧に示すように、スキャン コード、キー遷移コード、前のキーの状態、およびコンテキストのコードを指定します。  
  
|[値]|説明|  
|-----------|-------------|  
|0-7|コード (OEM に依存する値) をスキャンします。 上位ワードの下位バイトをします。|  
|8|ファンクション キーまたはテンキー (拡張キーである場合は 1。 それ以外の場合 0) のキーなどの拡張キー。|  
|9-10|使用しません。|  
|11-12|Windows によって内部的に使用します。|  
|13|コンテキストのコード (1、キーが押されている間、0 それ以外の場合、、ALT キーが保持されている場合)。|  
|14|以前のキー状態 (1、メッセージが送信される前に、0 キーの場合、キーがダウンした場合)。|  
|16|(キーが解放されている場合は 1、押されている場合は 0) の状態に移行します。|  
  
 `OnSysKeyDown`キー遷移ビット (bit 15) の呼び出しは 0 です。 ALT キーの作成中は、キーが押された; 場合、コンテキスト コード ビット (bit 13) は 1ウィンドウに入力フォーカスされていないために、アクティブなウィンドウにメッセージが送信された場合は 0 になります。  
  
### <a name="remarks"></a>コメント  
 ウィンドウに入力フォーカスをアクティブなウィンドウのされていない場合`OnSysKeyDown`メンバー関数が呼び出されます。 `CWnd`メッセージを受信するオブジェクトは、コンテキストのコードをチェックインしてこれらの 2 つのコンテキストを区別できる`nFlags`です。  
  
 コンテキストのコードは 0、ときに、`WM_SYSKEYDOWN`によって受信されたメッセージ`OnSysKeyDown`に渡すことができます、 [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows の機能は、システム キー メッセージではなく通常のキー メッセージと同様に処理されます. これにより、アクティブなウィンドウが入力フォーカスを持っていない場合でも、作業中のウィンドウで使用するアクセラレータ キー。  
  
 自動繰り返し、1 つ以上のため`OnSysKeyDown`呼び出しにする前に発生する可能性があります、 [WM_SYSKEYUP](#onsyskeyup)メッセージを受信します。 以前のキーの状態 (ビット 14) を決定に使用できるかどうか、`OnSysKeyDown`呼び出しは、最初に押さかダウン繰り返しの遷移を示します。  
  
 IBM エンハンス 101 および 102 key キーボード、強化されたキーには右 ALT および右 CTRL キーを押し、キーボードのメイン セクションにアドイン、DEL、HOME、END、PAGEUP、PAGEDOWN、および; テンキーの左側に、クラスター内の矢印キースラッシュ (/) およびテンキーで ENTER キー。 その他の一部のキーボード可能性があります、拡張キー ビット サポートで`nFlags`です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onsyskeyup"></a>  CWnd::OnSysKeyUp  
 場合、`CWnd`オブジェクトにフォーカスを`OnSysKeyUp`押した、ALT キーが押されたキーを離したときに、メンバー関数が、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnSysKeyUp(
    UINT nChar,  
    UINT nRepCnt,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 押されているキーの仮想キー コードを指定します。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nRepCnt`  
 繰り返し回数を指定します。  
  
 `nFlags`  
 次の一覧に示すように、スキャン コード、キー遷移コード、前のキーの状態、およびコンテキストのコードを指定します。  
  
|[値]|説明|  
|-----------|-------------|  
|0-7|コード (OEM に依存する値) をスキャンします。 上位ワードの下位バイトをします。|  
|8|ファンクション キーまたはテンキー (拡張キーである場合は 1。 それ以外の場合 0) のキーなどの拡張キー。|  
|9-10|使用しません。|  
|11-12|Windows によって内部的に使用します。|  
|13|コンテキストのコード (1、キーが押されている間、0 それ以外の場合、、ALT キーが保持されている場合)。|  
|14|以前のキー状態 (1、メッセージが送信される前に、0 キーの場合、キーがダウンした場合)。|  
|16|(キーが解放されている場合は 1、押されている場合は 0) の状態に移行します。|  
  
 `OnSysKeyUp`キー遷移ビット (bit 15) の呼び出しは 1 です。 ALT キーの作成中は、キーが押された; 場合、コンテキスト コード ビット (bit 13) は 1ウィンドウに入力フォーカスされていないために、アクティブなウィンドウにメッセージが送信された場合は 0 になります。  
  
### <a name="remarks"></a>コメント  
 ウィンドウに入力フォーカスをアクティブなウィンドウのされていない場合`OnSysKeyUp`メンバー関数が呼び出されます。 `CWnd` 、通話を受けるオブジェクトは、コンテキストのコードをチェックインしてこれらの 2 つのコンテキストを区別できる`nFlags`です。  
  
 コンテキストのコードは 0、ときに、`WM_SYSKEYUP`によって受信されたメッセージ`OnSysKeyUp`に渡すことができます、 [TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms646373) Windows の機能は、システム キー メッセージではなく通常のキー メッセージと同様に処理されます. これにより、アクセラレータは、アクティブなウィンドウが入力フォーカスを持っていない場合でも、作業中のウィンドウで使用する (ショートカット) キー。  
  
 IBM エンハンス 101 および 102 key キーボード、強化されたキーには右 ALT および右 CTRL キーを押し、キーボードのメイン セクションにアドイン、DEL、HOME、END、PAGEUP、PAGEDOWN、および; テンキーの左側に、クラスター内の矢印キースラッシュ (/) およびテンキーで ENTER キー。 その他の一部のキーボード可能性があります、拡張キー ビット サポートで`nFlags`です。  
  
 英語 (米国) 以外の強化された 102 key キーボード、右 ALT キーは、CTRL キーと ALT キーの組み合わせとして処理されます。 メッセージと、ユーザーがこのキーを押して離したときに発生する呼び出しのシーケンスを次に示します。  
  
|シーケンス|アクセスされる関数|渡されたメッセージ|  
|--------------|-----------------------|--------------------|  
|1.|[WM_KEYDOWN](#onkeydown)|**VK_CONTROL**|  
|2.|[WM_KEYDOWN](#onkeydown)|**VK_MENU**|  
|3.|[WM_KEYUP](#onkeyup)|**VK_CONTROL**|  
|4.|[WM_SYSKEYUP](http://msdn.microsoft.com/library/windows/desktop/ms646287)|**VK_MENU**|  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="ontcard"></a>  CWnd::OnTCard  
 フレームワークは、ユーザーが編集可能なボタンをクリックしたときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnTCard(
    UINT idAction,  
    DWORD dwActionData);
```  
  
### <a name="parameters"></a>パラメーター  
 `idAction`  
 ユーザーの動作が実行されることを示します。 このパラメーターには、これらの値のいずれかを指定できます。  
  
- **IDABORT**ユーザーが編集可能な中止ボタンをクリックします。  
  
- **IDCANCEL**ユーザーが編集可能な [キャンセル] ボタンをクリックします。  
  
- **IDCLOSE**ユーザーがトレーニング カードをクローズします。  
  
- **IDHELP**ユーザーが編集可能な Windows のヘルプ ボタンをクリックします。  
  
- **IDIGNORE**ユーザーが編集可能なを無視するボタンをクリックしました。  
  
- **IDOK**ユーザーが編集可能な [ok] ボタンをクリックします。  
  
- **IDNO**ボタンをクリックして、編集可能ありません。  
  
- **IDRETRY**ユーザーが編集可能な [再試行] ボタンをクリックします。  
  
- **HELP_TCARD_DATA**ユーザーが編集可能なボタンをクリックします。 `dwActionData`パラメーターには、ヘルプの作成者によって指定された長整数型が含まれています。  
  
- **HELP_TCARD_NEXT**ユーザーが編集可能な [次へ] ボタンをクリックします。  
  
- **HELP_TCARD_OTHER_CALLER**別のアプリケーションがトレーニングのカードを要求します。  
  
- **IDYES**ユーザーが編集可能な [はい] ボタンをクリックします。  
  
 `dwActionData`  
 場合`idAction`指定**HELP_TCARD_DATA**、このパラメーターは、ヘルプの作成者によって指定された長整数。 それ以外の場合、このパラメーターは 0 です。  
  
### <a name="remarks"></a>コメント  
 アプリケーションには、Windows のヘルプでトレーニング カードが開始した場合にのみ、この関数が呼び出されます。 アプリケーションを指定して、トレーニングのカードを開始する、 **HELP_TCARD**コマンドへの呼び出しを[WinHelp](../../mfc/reference/cwinapp-class.md#winhelp)関数。  
  
##  <a name="ontimechange"></a>  CWnd::OnTimeChange  
 フレームワークは、システム時刻が変更された後に、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnTimeChange();
```  
  
### <a name="remarks"></a>コメント  
 変更、システム時刻メッセージが送信されるこのすべての最上位ウィンドウに、アプリケーションがあります。 送信する、`WM_TIMECHANGE`メッセージをすべての最上位 windows アプリケーションで使用できる、 [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950)で Windows の機能、 *hwnd*パラメーターに設定**HWND_BROADCAST**.  
  
##  <a name="ontimer"></a>  CWnd::OnTimer  
 フレームワークは、後で指定された間隔ごとに、このメンバー関数、 [SetTimer](#settimer)メンバー関数は、タイマーをインストールするために使用します。  
  
```  
afx_msg void OnTimer(UINT_PTR nIDEvent);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDEvent`  
 タイマーの識別子を指定します。  
  
### <a name="remarks"></a>コメント  
 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数の送信、 [WM_TIMER](http://msdn.microsoft.com/library/windows/desktop/ms644902)メッセージが表示されるその他のメッセージがアプリケーションのメッセージ キューではありません。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
### <a name="example"></a>例  
  例を参照してください[で](#settimer)です。  
  
##  <a name="ontoolhittest"></a>  CWnd::OnToolHitTest  
 フレームワークは、ポイントが指定されたツールの外接する四角形であるかどうかを確認するには、このメンバー関数を呼び出します。  
  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 カーソルの x 座標と y 座標を指定します。 これらの座標は、常に、ウィンドウの左上隅を基準としました。  
  
 `pTI`  
 ポインター、 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)構造体。 既定では、次の構造体の値を設定します。  
  
- *hwnd*  =  `m_hWnd`ウィンドウへのハンドル  
  
- `uId` = **(UINT) hWndChild**子ウィンドウへのハンドル  
  
- `uFlags` &#124;= **TTF_IDISHWND**ツールのハンドル  
  
- `lpszText` = **保持するようにする**指定されたウィンドウで表示される文字列へのポインター  
  
### <a name="return-value"></a>戻り値  
 ツール ヒント コントロールが見つかった場合は、window コントロール id です。 ツール ヒント コントロールが見つからなかった場合、-1。  
  
### <a name="remarks"></a>コメント  
 ポイントが四角形内にある場合は、ツールに関する情報を取得します。  
  
 ツールヒントが関連付けられている領域は、ボタンではない場合`OnToolHitTest`構造フラグ**TTF_NOTBUTTON**と**ない場合**です。  
  
 オーバーライド`OnToolHitTest`既定で提供されるさまざまな情報を提供します。  
  
 参照してください[TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)、構造体の詳細については、Windows SDK に含まれています。  
  
##  <a name="ontouchinput"></a>  CWnd::OnTouchInput  
 Windows タッチからの 1 つの入力を処理します。  
  
```  
virtual BOOL OnTouchInput(
    CPoint pt,  
    int nInputNumber,  
    int nInputsCount,  
    PTOUCHINPUT pInput);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 画面が (クライアント座標) でタッチされた場所をポイントします。  
  
 `nInputNumber`  
 タッチ入力の数です。  
  
 `nInputsCount`  
 タッチ入力の合計数。  
  
 `pInput`  
 TOUCHINPUT 構造へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` アプリケーションは、Windows タッチ入力を処理する場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ontouchinputs"></a>  CWnd::OnTouchInputs  
 Windows タッチからの入力を処理します。  
  
```  
virtual BOOL OnTouchInputs(
    UINT nInputsCount,  
    PTOUCHINPUT pInputs);
```  
  
### <a name="parameters"></a>パラメーター  
 `nInputsCount`  
 Windows の合計数はタッチ入力です。  
  
 `pInputs`  
 TOUCHINPUT の配列です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` アプリケーション プロセス Windows タッチ入力; 場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onunichar"></a>  CWnd::OnUniChar  
 フレームワークは、キーが押されたときに、このメンバー関数を呼び出します。 現在のウィンドウは、キーボード フォーカス、および[WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280)によってメッセージを変換、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)関数。  
  
```  
afx_msg void OnUniChar(
    UINT nChar,   
    UINT nRepCnt,   
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nChar`|押されたキーの文字コードを指定します。|  
|[入力] `nRepCnt`|現在のメッセージの繰り返し回数を指定します。 値は、キーストロークが、キーを押しながら、ユーザーの結果として autorepeated 回数です。 キーストロークが保持される十分に長い場合は、複数のメッセージが送信されます。 ただし、繰り返し回数は、累積的ではありません。|  
|[入力] `nFlags`|次の表に示すように、スキャン コード、拡張キー、コンテキストのコード、前のキーの状態および遷移の状態を指定するフラグ。<br /><br /> **0-7:** スキャン コードを指定します。 値は、製造元 (OEM) に依存します。<br /><br /> **8:** 拡張 101 または 102 key キーボードに表示される右 alt キーや CTRL キーなどの拡張キーを指定します。 キーが拡張キー以外の場合、フラグは 1それ以外の場合は 0 です。<br /><br /> **9 ~ 12:** Windows によって内部的に使用します。<br /><br /> **13:** コンテキストのコードを指定します。 ALT キーを押した状態でキーを押した場合、このフラグは 1それ以外の場合、値は 0 です。<br /><br /> **14:** 前のキーの状態を指定します。 フラグは、キーがの場合は、メッセージを送信する前に、キーが押されている場合は 1 または 0 です。<br /><br /> **15:** 遷移の状態を指定します。 フラグは、押されている場合は、キーが解放されている場合は 1 または 0 です。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_UNICHAR](http://msdn.microsoft.com/library/windows/desktop/ms646288)通知で、Windows SDK に記載されています。 [WM_UNICHAR](http://msdn.microsoft.com/library/windows/desktop/ms646288)メッセージが送信または Unicode 文字を ANSI windows にポストするように設計されています。 等価である、 [WM_CHAR](http://msdn.microsoft.com/library/windows/desktop/ms646276) 、メッセージしますが、Unicode 変換形式 32 エンコード (utf-32) を使用する一方、 [WM_CHAR](http://msdn.microsoft.com/library/windows/desktop/ms646276)メッセージで utf-16 を使用します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onuninitmenupopup"></a>  CWnd::OnUnInitMenuPopup  
 フレームワークは、このメンバー関数とドロップダウン メニューまたはサブメニューが破棄されたします。  
  
```  
afx_msg void OnUnInitMenuPopup(
    CMenu* pPopupMenu,   
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pMenu`|ポインター、 [CMenu](../../mfc/reference/cmenu-class.md)メニューまたはサブメニューを表すオブジェクト。|  
|[入力] `nFlags`|破棄されたメニューです。 現時点では、[ウィンドウ] メニューに指定できるのみ`MF_SYSMENU`です。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_UNINITMENUPOPUP](http://msdn.microsoft.com/library/windows/desktop/ms647614)通知で、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onupdateuistate"></a>  CWnd::OnUpdateUIState  
 指定したウィンドウとそのすべての子ウィンドウのユーザー インターフェイス (UI) 状態を変更するのと呼ばれます。  
  
```  
afx_msg void OnUpdateUIState(
    UINT nAction,  
    UINT nUIElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAction`  
 実行するアクションを指定します。 次のいずれかの値になります。  
  
- **UIS_CLEAR** UI 状態要素 (で指定した`nUIElement`) 非表示にする必要があります。  
  
- **UIS_INITIALIZE** UI 状態要素 (で指定した`nUIElement`) 最後の入力イベントに基づいて変更する必要があります。 詳細については、次を参照してください。、**解説**のセクション[WM_UPDATEISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646361)です。  
  
- **UIS_SET** UI 状態要素 (で指定した`nUIElement`) が表示されます。  
  
 `nUIElement`  
 UI 状態の要素が影響を受けるか、コントロールのスタイルを指定します。 次のいずれかの値になります。  
  
- **UISF_HIDEACCEL**キーボード アクセラレータです。  
  
- **UISF_HIDEFOCUS**インジケーターに注目します。  
  
- **UISF_ACTIVE Windows XP:** コントロールは、アクティブなコントロールで使用されるスタイルで描画する必要があります。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [WM_UPDATEUISTATE](http://msdn.microsoft.com/library/windows/desktop/ms646361)メッセージ、Windows SDK で説明します。  
  
##  <a name="onuserchanged"></a>  CWnd::OnUserChanged  
 フレームワークでは、ユーザーがログオンまたはログオフした後に、すべてのウィンドウでこのメンバーを呼び出します。  
  
```  
afx_msg void OnUserChanged();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_USERCHANGED](http://msdn.microsoft.com/library/windows/desktop/ms632651)通知メッセージは、Windows SDK に記載されています。 ユーザーがログオンまたはログオフ、オペレーティング システムは、ユーザーに固有の設定を更新します。 システムでは、設定を更新した後すぐにこのメッセージを送信します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onvkeytoitem"></a>  CWnd::OnVKeyToItem  
 場合、`CWnd`オブジェクトでリスト ボックスを所有している、 [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルをリスト ボックスの送信は、`WM_VKEYTOITEM`への応答メッセージ、`WM_KEYDOWN`メッセージ。  
  
```  
afx_msg int OnVKeyToItem(
    UINT nKey,  
    CListBox* pListBox,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nKey`  
 ユーザーが押されたキーの仮想キー コードを指定します。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `pListBox`  
 リスト ボックスへのポインターを指定します。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
 `nIndex`  
 現在のカレット位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 アプリケーション メッセージに応答して実行するアクションを指定します。 戻り値が-2 は、アプリケーションが、項目の選択のすべての側面を処理、リスト ボックスで、これ以上の操作を必要としないことを示します。 戻り値-1 は、キー操作への応答に、リスト ボックスが既定のアクションを実行することを示します。 0 以上の戻り値は、リスト ボックスで、項目の 0 から始まるインデックスを指定し、リスト ボックスがで指定したアイテムのキーストロークの既定のアクションを実行する必要がありますを示します。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスに対してのみ、フレームワークによって呼び出されます、 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onvscroll"></a>  CWnd::OnVScroll  
 フレームワークは、ユーザーがウィンドウの垂直スクロール バーをクリックしたときに、このメンバー関数を呼び出します。  
  
```  
afx_msg void OnVScroll(
    UINT nSBCode,  
    UINT nPos,  
    CScrollBar* pScrollBar);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSBCode`  
 スクロール バーのコードをユーザーを示すには要求のスクロールを指定します。 このパラメーターには、次のいずれかを指定できます。  
  
- **SB_BOTTOM**一番下までスクロールします。  
  
- **SB_ENDSCROLL**スクロール終了します。  
  
- **SB_LINEDOWN** 1 行下へスクロールします。  
  
- **SB_LINEUP** 1 行を上にスクロールします。  
  
- **SB_PAGEDOWN** 1 ページ下へスクロールします。  
  
- **SB_PAGEUP**を 1 つのページをスクロールします。  
  
- **SB_THUMBPOSITION**絶対位置にスクロールします。 現在の位置がで提供される`nPos`です。  
  
- **SB_THUMBTRACK**指定した位置にスクロール ボックスをドラッグします。 現在の位置がで提供される`nPos`です。  
  
- **SB_TOP**の上端へスクロールします。  
  
 `nPos`  
 スクロール バーのコードがある場合、現在のスクロール ボックスの位置を含む**SB_THUMBPOSITION**または**SB_THUMBTRACK**です。 それ以外の場合は使用されません。 初期のスクロールの範囲に応じて`nPos`が負の数およびにキャストする必要があります、`int`必要な場合です。  
  
 `pScrollBar`  
 スクロール バー コントロールからスクロール メッセージが送信された場合に、コントロールへのポインターが含まれています。 このパラメーターは、ユーザーがウィンドウのスクロール バーをクリックした場合**NULL**です。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 `OnVScroll` 通常は、スクロール ボックスにドラッグしているときに、いくつかのフィードバックを提供するアプリケーションによって使用されます。  
  
 場合`OnVScroll`の内容をスクロール、`CWnd`オブジェクトを使用してスクロール ボックスの位置をリセットする必要がありますも、 [SetScrollPos](#setscrollpos)メンバー関数。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onvscrollclipboard"></a>  CWnd::OnVScrollClipboard  
 クリップボード所有者の`OnVScrollClipboard`クリップボード データがあるときに、クリップボード ビューアーによってメンバー関数が呼び出されます、`CF_OWNERDISPLAY`書式設定し、クリップボード ビューアーの垂直スクロール バーで、イベントがあります。  
  
```  
afx_msg void OnVScrollClipboard(
    CWnd* pClipAppWnd,  
    UINT nSBCode,  
    UINT nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `pClipAppWnd`  
 クリップボード ビューアー ウィンドウへのポインターを指定します。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
 `nSBCode`  
 スクロール バーの値は次のいずれかを指定します。  
  
- **SB_BOTTOM**一番下までスクロールします。  
  
- **SB_ENDSCROLL**スクロール終了します。  
  
- **SB_LINEDOWN** 1 行下へスクロールします。  
  
- **SB_LINEUP** 1 行を上にスクロールします。  
  
- **SB_PAGEDOWN** 1 ページ下へスクロールします。  
  
- **SB_PAGEUP**を 1 つのページをスクロールします。  
  
- **SB_THUMBPOSITION**絶対位置にスクロールします。 現在の位置がで提供される`nPos`です。  
  
- **SB_TOP**の上端へスクロールします。  
  
 `nPos`  
 スクロール バーのコードがある場合は、スクロール ボックスの位置を含む**SB_THUMBPOSITION**それ以外の`nPos`は使用されません。  
  
### <a name="remarks"></a>コメント  
 所有者をクリップボードのイメージをスクロール、適切なセクションが無効にし、スクロール バーの値を更新します。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onwindowmaximizedchanged"></a>  CWnd::OnWindowMaximizedChanged  
 現在のウィンドウを最大表示しているし、ウィンドウがデスクトップ ウィンドウ マネージャー (DWM) によってで構成されるときに、フレームワークはこのメンバーを呼び出します。  
  
```  
afx_msg void OnWindowMaximizedChanged(BOOL bIsMaximized);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `bIsMaximized`|`true` 現在のウィンドウを最大表示している場合と`false`されていない場合。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_DWMWINDOWMAXIMIZEDCHANGE](http://msdn.microsoft.com/library/windows/desktop/dd388201)通知メッセージは、Windows SDK に記載されています。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onwindowposchanged"></a>  CWnd::OnWindowPosChanged  
 呼び出しの結果として、サイズ、位置、または Z オーダーが変わったときに、フレームワークがこのメンバー関数を呼び出す、 [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545)メンバー関数または他のウィンドウ管理関数です。  
  
```  
afx_msg void OnWindowPosChanged(WINDOWPOS* lpwndpos);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpwndpos`  
 指す、 [WINDOWPOS](../../mfc/reference/windowpos-structure1.md)ウィンドウの新しいサイズと位置に関する情報を格納するデータ構造です。  
  
### <a name="remarks"></a>コメント  
 既定の実装、 [WM_SIZE](http://msdn.microsoft.com/library/windows/desktop/ms632646)と[WM_MOVE](http://msdn.microsoft.com/library/windows/desktop/ms632631)メッセージ ウィンドウにします。 アプリケーションが処理する場合、これらのメッセージは送信されませんが、`OnWindowPosChanged`呼び出さずに、基本クラスを呼び出します。 呼び出し中に変更の処理のサイズを変更または移動してもを実行する方が効率的である`OnWindowPosChanged`呼び出さずに、基本クラスです。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onwindowposchanging"></a>  CWnd::OnWindowPosChanging  
 サイズ、位置、または Z オーダーはへの呼び出しの結果として変更するときに、フレームワークがこのメンバー関数を呼び出す、 [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545)メンバー関数または他のウィンドウ管理関数です。  
  
```  
afx_msg void OnWindowPosChanging(WINDOWPOS* lpwndpos);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpwndpos`  
 指す、`WINDOWPOS`ウィンドウの新しいサイズと位置に関する情報を格納するデータ構造です。  
  
### <a name="remarks"></a>コメント  
 アプリケーション変更されないようにする、ウィンドウの設定や、該当するビットをオフにすると、**フラグ**のメンバー、 [WINDOWPOS](../../mfc/reference/windowpos-structure1.md)構造体。  
  
 使ってウィンドウに、 [WS_OVERLAPPED](styles-used-by-mfc.md#window-styles)または[WS_THICKFRAME](styles-used-by-mfc.md#window-styles)スタイルを既定の実装、 [WM_GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626)ウィンドウにメッセージ。 これは、新しいサイズとウィンドウの位置を検証し、適用する、**により**と**なり**クライアント スタイル。 アプリケーションは、その基本クラスを呼び出していないでこの機能をオーバーライドできます。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onwininichange"></a>  CWnd::OnWinIniChange  
 フレームワークこのメンバー関数が呼び出さ Windows 初期化ファイルが変更された後に契約を獲得します。INI です。  
  
```  
afx_msg void OnWinIniChange(LPCTSTR lpszSection);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSection`  
 変更されたセクションの名前を指定する文字列へのポインター。 (文字列は含まれませんセクション名を囲む角かっこ。)  
  
### <a name="remarks"></a>コメント  
 [次](http://msdn.microsoft.com/library/windows/desktop/ms724947)Windows 関数呼び出し`OnWinIniChange`後、アプリケーションでは、関数を使用して、WIN で設定を変更します。INI ファイルです。  
  
 送信する、`WM_WININICHANGE`メッセージをすべての最上位 windows アプリケーションで使用できる、 [SendMessage](http://msdn.microsoft.com/library/windows/desktop/ms644950)で Windows の機能、 *hwnd*パラメーターに設定**HWND_BROADCAST**.  
  
 アプリケーションには、多くのさまざまなセクションが変更された場合は、次の勝ちです。同時に INI、アプリケーションで送信する 1 つ`WM_WININICHANGE`メッセージを`lpszSection`'éý' **NULL**です。 それ以外の場合、アプリケーションを送信する必要があります`WM_WININICHANGE`たび WIN に変更を加えることです。INI です。  
  
 アプリケーションが受信した場合、`OnWinIniChange`で呼び出す`lpszSection`'éý' **NULL**アプリケーションは、WIN のすべてのセクションを確認する必要があります。アプリケーションに影響を与える INI です。  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onwndmsg"></a>  CWnd::OnWndMsg  
 によって呼び出されます`WindowProc`、またはメッセージ リフレクション中に呼び出されます。  
  
```  
virtual BOOL OnWndMsg(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `pResult`  
 戻り値[WindowProc](#windowproc)です。 メッセージに依存します。あります**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**メッセージが処理されるそれ以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 `OnWndMsg` メッセージの種類といずれかの呼び出し、適切な framework の関数を決定 (たとえば、 [OnCommand](#oncommand)の**WM_COMMAND**) とメッセージ マップで適切なメッセージを検索します。  
  
 メッセージ リフレクションの詳細については、次を参照してください。[反映されたメッセージの処理](../../mfc/handling-reflected-messages.md)です。  
  
##  <a name="onxbuttondblclk"></a>  CWnd::OnXButtonDblClk  
 カーソルがウィンドウのクライアント領域内 XBUTTON1 または XBUTTON2 をユーザーがダブルクリックすると、フレームワークはこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnXButtonDblClk(
    UINT nFlags,   
    UINT nButton,   
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nFlags`|どの修飾子キーが押されたかを示すフラグのビットごとの組み合わせ (OR)。 たとえば、`MK_CONTROL`フラグは、CTRL キーが押されたことを示します。|  
|[入力] `nButton`|値`XBUTTON1`場合は、最初の Microsoft Intellimouse X ボタンがダブルクリックされたときに、または`XBUTTON2`場合、2 つ目の X ボタンがダブルクリックされました。|  
|[入力] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)を指定するオブジェクト、 *x*と*y*クライアント領域の左上隅を基準としたカーソルの座標。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_XBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms646244)通知で、Windows SDK に記載されています。 マウスがキャプチャされていない場合、メッセージは、カーソルの下にあるウィンドウに通知されます。 それ以外の場合、メッセージは、マウスをキャプチャするウィンドウに通知されます。  
  
 `nFlags`パラメーターは、次の表に記載されている修飾子キーの組み合わせを指定できます。 詳細については、次を参照してください。[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)です。  
  
|修飾キー|説明|  
|------------------|-----------------|  
|MK_CONTROL|CTRL キーが押されるとします。|  
|MK_LBUTTON|マウスの左ボタンが押されるとします。|  
|MK_MBUTTON|マウスの中央ボタンが押されるとします。|  
|MK_RBUTTON|マウスの右ボタンが押されるとします。|  
|MK_SHIFT|SHIFT キーが押されるとします。|  
|MK_XBUTTON1|IntelliMouse のマウスの XBUTTON1 ボタンが押されるとします。|  
|MK_XBUTTON2|Microsoft IntelliMouse の XBUTTON2 マウス ボタンが押されたとします。|  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onxbuttondown"></a>  CWnd::OnXButtonDown  
 フレームワークは、ユーザーが押す XBUTTON1 または XBUTTON2 カーソルがウィンドウのクライアント領域内にこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnXButtonDown(
    UINT nFlags,   
    UINT nButton,   
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nFlags`|どの修飾子キーが押されたかを示すフラグのビットごとの組み合わせ (OR)。 たとえば、`MK_CONTROL`フラグは、CTRL キーが押されたことを示します。|  
|[入力] `nButton`|値`XBUTTON1`Microsoft Intellimouse X の最初のボタンがクリックされた場合または`XBUTTON2`場合、2 つ目 X button がクリックしてされました。|  
|[入力] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)を指定するオブジェクト、 *x*と*y*クライアント領域の左上隅を基準としたカーソルの座標。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_XBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646245)通知で、Windows SDK に記載されています。 マウスがキャプチャされていない場合、メッセージは、カーソルの下にあるウィンドウに通知されます。 それ以外の場合、メッセージは、マウスをキャプチャするウィンドウに通知されます。  
  
 `nFlags`パラメーターは、次の表に記載されている修飾子キーの組み合わせを指定できます。 詳細については、次を参照してください。[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)です。  
  
|修飾キー|説明|  
|------------------|-----------------|  
|MK_CONTROL|CTRL キーが押されるとします。|  
|MK_LBUTTON|マウスの左ボタンが押されるとします。|  
|MK_MBUTTON|マウスの中央ボタンが押されるとします。|  
|MK_RBUTTON|マウスの右ボタンが押されるとします。|  
|MK_SHIFT|SHIFT キーが押されるとします。|  
|MK_XBUTTON1|IntelliMouse のマウスの XBUTTON1 ボタンが押されるとします。|  
|MK_XBUTTON2|Microsoft IntelliMouse の XBUTTON2 マウス ボタンが押されたとします。|  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="onxbuttonup"></a>  CWnd::OnXButtonUp  
 フレームワークは、ユーザーを離す XBUTTON1 または XBUTTON2 カーソルがウィンドウのクライアント領域内にこのメンバー関数を呼び出します。  
  
```  
afx_msg void OnXButtonUp(
    UINT nFlags,   
    UINT nButton,   
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nFlags`|どの修飾子キーが押されたかを示すフラグのビットごとの組み合わせ (OR)。 たとえば、`MK_CONTROL`フラグは、CTRL キーが押されたことを示します。|  
|[入力] `nButton`|値`XBUTTON1`場合は、最初の Microsoft Intellimouse X ボタンがダブルクリックされたときに、または`XBUTTON2`場合、2 つ目の X ボタンがダブルクリックされました。|  
|[入力] `point`|A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)を指定するオブジェクト、 *x*と*y*クライアント領域の左上隅を基準としたカーソルの座標。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは受信、 [WM_XBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646246)通知で、Windows SDK に記載されています。 マウスがキャプチャされていない場合、メッセージは、カーソルの下にあるウィンドウに通知されます。 それ以外の場合、メッセージは、マウスをキャプチャするウィンドウに通知されます。  
  
 `nFlags`パラメーターは、次の表に記載されている修飾子キーの組み合わせを指定できます。 詳細については、次を参照してください。[マウス入力に関する](http://msdn.microsoft.com/library/windows/desktop/ms645601)です。  
  
|修飾キー|説明|  
|------------------|-----------------|  
|MK_CONTROL|CTRL キーが押されるとします。|  
|MK_LBUTTON|マウスの左ボタンが押されるとします。|  
|MK_MBUTTON|マウスの中央ボタンが押されるとします。|  
|MK_RBUTTON|マウスの右ボタンが押されるとします。|  
|MK_SHIFT|SHIFT キーが押されるとします。|  
|MK_XBUTTON1|IntelliMouse のマウスの XBUTTON1 ボタンが押されるとします。|  
|MK_XBUTTON2|Microsoft IntelliMouse の XBUTTON2 マウス ボタンが押されたとします。|  
  
> [!NOTE]
>  このメンバー関数は、アプリケーションで Windows メッセージを処理できるようにするためにフレームワークによって呼び出されます。 関数に渡されるパラメーターは、メッセージを受信したときにフレームワークが受信したパラメーターを反映します。 この関数の基底クラス実装を呼び出す場合、その実装は、関数に指定したパラメーターではなく、メッセージと共に渡されたパラメーターを使用します。  
  
##  <a name="openclipboard"></a>  CWnd::OpenClipboard  
 クリップボードを開きます。  
  
```  
BOOL OpenClipboard();
```  
  
### <a name="return-value"></a>戻り値  
 使用して、クリップボードを開いた場合は 0 以外`CWnd`、または別のアプリケーションまたはウィンドウがクリップボードを持つ場合は 0 を開きます。  
  
### <a name="remarks"></a>コメント  
 他のアプリケーションをまでクリップボードを変更することにすることはできません、 [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Windows 関数が呼び出されます。  
  
 現在`CWnd`オブジェクトはまでクリップボードの所有者にならない、 [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) Windows 関数が呼び出されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#111](../../mfc/reference/codesnippet/cpp/cwnd-class_52.cpp)]  
  
##  <a name="operator_hwnd"></a>  CWnd::operator HWND  
 ハンドルを取得するこの演算子を使用して、`CWnd`オブジェクト。  
  
```  
operator HWND() const;  
```  
  
##  <a name="operator_neq"></a>  CWnd::operator! =  
 比較する 2 つ`CWnd`オブジェクトはありませんが存在するか、同じを[m_hWnd](#m_hwnd)です。  
  
```  
BOOL operator!=(const CWnd& wnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `wnd`  
 `CWnd` オブジェクトへの参照。  
  
### <a name="return-value"></a>戻り値  
 等しい場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="operator_eq_eq"></a>  CWnd::operator = =  
 比較する 2 つ`CWnd`オブジェクトを同じが存在するか[m_hWnd](#m_hwnd)です。  
  
```  
BOOL operator==(const CWnd& wnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `wnd`  
 `CWnd` オブジェクトへの参照。  
  
### <a name="return-value"></a>戻り値  
 等しい場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="paintwindowlesscontrols"></a>  CWnd::PaintWindowlessControls  
 コントロール コンテナーのウィンドウなしのコントロールを描画します。  
  
```  
BOOL PaintWindowlessControls(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ウィンドウなしのコントロールを描画するためにデバイス コンテキスト。  
  
### <a name="return-value"></a>戻り値  
 コントロール コンテナーとウィンドウなしのコントロールがある場合は TRUE を返しますとは、正常に描画された、それ以外の場合は FALSE です。  
  
##  <a name="postmessage"></a>  CWnd::PostMessage  
 ウィンドウのメッセージ キューにメッセージを格納し、対応するウィンドウ メッセージを処理するを待機することがなくを返します。  
  
```  
BOOL PostMessage(
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 メッセージをポストを指定します。  
  
 `wParam`  
 追加のメッセージの情報を指定します。 このパラメーターの内容は、ポストされたメッセージに依存します。  
  
 `lParam`  
 追加のメッセージの情報を指定します。 このパラメーターの内容は、ポストされたメッセージに依存します。  
  
### <a name="return-value"></a>戻り値  
 メッセージが送られた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メッセージ キューにメッセージがへの呼び出しによって取得される、 [GetMessage](http://msdn.microsoft.com/library/windows/desktop/ms644936)または[PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Windows の機能です。  
  
 Windows [PostMessage](http://msdn.microsoft.com/library/windows/desktop/ms644944)別のアプリケーションにアクセスする関数を使用できます。  
  
### <a name="example"></a>例  
  例を参照して[AfxGetMainWnd](../../mfc/reference/application-information-and-management.md#afxgetmainwnd)です。  
  
##  <a name="postncdestroy"></a>  CWnd::PostNcDestroy  
 既定と呼ばれる[OnNcDestroy](#onncdestroy)メンバー関数は、ウィンドウが破棄された後にします。  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、この関数がの削除などのカスタム クリーンアップを使用できます、**この**ポインター。  
  
##  <a name="precreatewindow"></a>  CWnd::PreCreateWindow  
 これにアタッチされた Windows ウィンドウを作成する前にフレームワークによって呼び出されます`CWnd`オブジェクト。  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>パラメーター  
 *cs*  
 A [CREATESTRUCT](../../mfc/reference/createstruct-structure.md)構造体。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウの作成を続行する必要があります。 場合は 0 以外。作成エラーを示すために 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!WARNING]
> `CWnd::PreCreateWindow` hMenu メンバーを割り当てるようになりました`cs`を`this`ポインターの場合は、メニュー`NULL`スタイルが含まれています`WS_CHILD`です。 適切に機能をダイアログ コントロールにではない ID があることを確認してください`NULL`です。  
>   
>  この変更は、マネージ/ネイティブの相互運用シナリオで、クラッシュを修正します。 A`TRACE`ステートメントで`CWnd::Create`問題の開発者に警告します。  
  
 この関数を直接呼び出すことはありません。  
  
 この関数の既定の実装、 **NULL**ウィンドウ クラス名を適切な既定値を置き換えます。 変更するには、このメンバー関数をオーバーライドします`CREATESTRUCT`ウィンドウが作成される前に構造体します。  
  
 各クラスから派生した`CWnd`そのオーバーライドの独自の機能が追加`PreCreateWindow`です。 仕様では、これらの派生`PreCreateWindow`記載されていません。 各クラスとスタイルの間の相互依存関係に適切なスタイルを決定するには、アプリケーションの基本クラスの MFC ソース コードを調べることができます。 オーバーライドする場合**PreCreateWindow、**アプリケーションの基本クラスで使用するスタイルが MFC のソース コードから収集された情報を使用して、必要な機能を提供するかどうかを判断できます。  
  
 ウィンドウ スタイルを変更する方法の詳細については、次を参照してください。、 [MFC で作成したウィンドウのスタイルを変更する](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#112](../../mfc/reference/codesnippet/cpp/cwnd-class_53.cpp)]  
  
##  <a name="presubclasswindow"></a>  CWnd::PreSubclassWindow  
 このメンバー関数は、ウィンドウがサブクラス化する前に発生する他の必要なサブクラス化を許可するためにフレームワークによって呼び出されます。  
  
```  
virtual void PreSubclassWindow();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数をオーバーライドする場合は、コントロールの動的なサブクラス化をできます。 高度なオーバーライド可能です。  
  
##  <a name="pretranslatemessage"></a>  CWnd::PreTranslateMessage  
 [TranslateMessage](../../mfc/reference/cwinapp-class.md) および [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) の各 Windows 関数にディスパッチされる前に、ウィンドウ メッセージを変換するためにクラス [CWinApp](http://msdn.microsoft.com/library/windows/desktop/ms644934) で使用されます。  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 指す、 [MSG](../../mfc/reference/msg-structure1.md)を処理するメッセージを含む構造体。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、メッセージが変換されていて、ディスパッチいない必要があります。メッセージが変換されていないと、ディスパッチする必要がある場合は 0 を返します。  
  
##  <a name="print"></a>  CWnd::Print  
 プリンター デバイス コンテキストで最も一般的には、指定したデバイス コンテキストで現在のウィンドウを描画するには、このメンバー関数を呼び出します。  
  
```  
void Print(
    CDC* pDC,  
    DWORD dwFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストへのポインター。  
  
 `dwFlags`  
 描画のオプションを指定します。 このパラメーターには、これらのフラグの 1 つ以上を指定できます。  
  
- `PRF_CHECKVISIBLE` 表示されている場合にのみ、ウィンドウを描画します。  
  
- `PRF_CHILDREN` すべての表示されている子ウィンドウを描画します。  
  
- `PRF_CLIENT` ウィンドウのクライアント領域を描画します。  
  
- `PRF_ERASEBKGND` ウィンドウを描画する前に、背景を消去します。  
  
- `PRF_NONCLIENT` ウィンドウの非クライアント領域を描画します。  
  
- `PRF_OWNED` 所有しているすべての windows を描画します。  
  
### <a name="remarks"></a>コメント  
 [CWnd::DefWindowProc](#defwindowproc)関数がどの描画オプションが指定されたに基づいてメッセージを処理します。  
  
-   場合`PRF_CHECKVISIBLE`が指定されていると、ウィンドウが表示されない、何もしません。  
  
-   場合`PRF_NONCLIENT`が指定すると、特定のデバイス コンテキストで、非クライアント領域を描画します。  
  
-   場合`PRF_ERASEBKGND`は、ウィンドウを指定すると、送信、 [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)メッセージ。  
  
-   場合`PRF_CLIENT`は、ウィンドウを指定すると、送信、 [WM_PRINTCLIENT](http://msdn.microsoft.com/library/windows/desktop/dd145217)メッセージ。  
  
-   場合`PRF_CHILDREN`設定値が、各表示されている子ウィンドウの送信、 [WM_PRINT](http://msdn.microsoft.com/library/windows/desktop/dd145216)メッセージ。  
  
-   場合`PRF_OWNED`設定値が、表示されている各所有されているウィンドウの送信、`WM_PRINT`メッセージ。  
  
##  <a name="printclient"></a>  CWnd::PrintClient  
 指定したデバイス コンテキスト (通常はプリンター デバイス コンテキスト) のいずれかのウィンドウを描画するには、このメンバー関数を呼び出します。  
  
```  
void PrintClient(
    CDC* pDC,  
    DWORD dwFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストへのポインター。  
  
 `dwFlags`  
 描画のオプションを指定します。 このパラメーターには、これらのフラグの 1 つ以上を指定できます。  
  
- `PRF_CHECKVISIBLE` 表示されている場合にのみ、ウィンドウを描画します。  
  
- `PRF_CHILDREN` すべての表示されている子ウィンドウを描画します。  
  
- `PRF_CLIENT` ウィンドウのクライアント領域を描画します。  
  
- `PRF_ERASEBKGND` ウィンドウを描画する前に、背景を消去します。  
  
- `PRF_NONCLIENT` ウィンドウの非クライアント領域を描画します。  
  
- `PRF_OWNED` 所有しているすべての windows を描画します。  
  
##  <a name="printwindow"></a>  CWnd::PrintWindow  
 表示されているウィンドウを指定されたデバイス コンテキスト (通常はプリンター DC) にコピーします。  
  
```  
BOOL PrintWindow(
    CDC* pDC,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 印刷するようにデバイス コンテキストへのポインター。  
  
 `nFlags`  
 描画のオプションを指定します。 使用可能な値の一覧は、次を参照してください。 [PrintWindow](http://msdn.microsoft.com/library/windows/desktop/dd162869)です。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[PrintWindow](http://msdn.microsoft.com/library/windows/desktop/dd162869)Windows SDK で説明されている。  
  
##  <a name="redrawwindow"></a>  CWnd::RedrawWindow  
 指定された四角形または指定されたウィンドウのクライアント領域内の領域を更新します。  
  
```  
BOOL RedrawWindow(
    LPCRECT lpRectUpdate = NULL,  
    CRgn* prgnUpdate = NULL,  
    UINT flags = RDW_INVALIDATE | RDW_UPDATENOW | RDW_ERASE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRectUpdate`  
 指す、 [RECT 構造体](../../mfc/reference/rect-structure1.md)更新四角形の座標を格納しています。 場合、このパラメーターは無視されます*prgnUpdate*正しい領域ハンドルが含まれています。  
  
 *prgnUpdate*  
 更新領域を識別します。 両方*prgnUpdate*と`lpRectUpdate`は**NULL**、クライアント領域全体が更新領域に追加します。  
  
 `flags`  
 次のフラグを使用するには、ウィンドウを無効にします。  
  
- **RDW_ERASE**によって受信する、ウィンドウ、 [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)メッセージが表示されるウィンドウが再描画します。 **RDW_INVALIDATE**指定されている場合がありますフラグ**RDW_ERASE**も何も起こりません。  
  
- **RDW_FRAME**を受信する更新領域と交差するウィンドウの非クライアント領域の任意の部分、 [WM_NCPAINT](http://msdn.microsoft.com/library/windows/desktop/dd145212)メッセージ。 **RDW_INVALIDATE**指定されている場合がありますフラグ**RDW_FRAME**も何も起こりません。  
  
- **RDW_INTERNALPAINT**により、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)ウィンドウが無効な領域を含むかどうかに関係なく、ウィンドウにポストするメッセージ。  
  
- **RDW_INVALIDATE** Invalidate`lpRectUpdate`または*prgnUpdate* (1 つしかない可能性があります**NULL**)。 両方とも場合**NULL**、ウィンドウ全体が無効になります。  
  
 次のフラグは、ウィンドウの検証に使用されます。  
  
- **RDW_NOERASE**保留中の抑制`WM_ERASEBKGND`メッセージ。  
  
- **RDW_NOFRAME**保留中の抑制`WM_NCPAINT`メッセージ。 このフラグはと共に使用する必要があります**RDW_VALIDATE**は通常使用と**RDW_NOCHILDREN**です。 正しく描画がウィンドウの各部を防ぐことがこれには注意は、このオプションを使用してください。  
  
- **RDW_NOINTERNALPAINT**保留中の内部を抑制`WM_PAINT`メッセージ。 このフラグには影響しません`WM_PAINT`無効領域からのメッセージ。  
  
- **RDW_VALIDATE**検証`lpRectUpdate`または*prgnUpdate* (1 つしかない可能性があります**NULL**)。 両方とも場合**NULL**、ウィンドウ全体を検証します。 このフラグには影響しません内部`WM_PAINT`メッセージ。  
  
 次のフラグ コントロールが再描画するときに発生します。 ペイントがで実行されていない、`RedrawWindow`これらのビットのいずれかを指定しない限り、機能します。  
  
- **RDW_ERASENOW**が原因で影響を受ける windows (で指定されたとおり、 **RDW_ALLCHILDREN**と**RDW_NOCHILDREN**フラグ) を受信する`WM_NCPAINT`と`WM_ERASEBKGND`場合にメッセージを前に、必要、関数を返します。 `WM_PAINT` メッセージが遅延されます。  
  
- **RDW_UPDATENOW**が原因で影響を受ける windows (で指定されたとおり、 **RDW_ALLCHILDREN**と**RDW_NOCHILDREN**フラグ) を受信する`WM_NCPAINT`、 `WM_ERASEBKGND`、および`WM_PAINT`メッセージ、必要に応じて、前に、この関数を返します。  
  
 既定では、windows の影響を受けた、`RedrawWindow`関数は、指定されたウィンドウがあるかどうかによって異なります、 **WS_CLIPCHILDREN**スタイル。 子ウィンドウ**WS_CLIPCHILDREN** windows には影響しません。 ただし、これらのウィンドウはできない**WS_CLIPCHILDREN**ウィンドウは、検証またはまで無効な場合は、再帰的に、 **WS_CLIPCHILDREN**ウィンドウが発生しました。 次で windows が影響を受けるコントロールのフラグ、`RedrawWindow`関数。  
  
- **RDW_ALLCHILDREN**再描画操作である場合、子ウィンドウが含まれています。  
  
- **RDW_NOCHILDREN**再描画操作から、子ウィンドウを除外します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが正常に再描画される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ときに、`RedrawWindow`デスクトップ ウィンドウの一部を無効にするメンバー関数が使用されるそのウィンドウが受信しません、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージ。 デスクトップを再描画するアプリケーションを使用する必要があります[CWnd::ValidateRgn](#validatergn)、 [CWnd::InvalidateRgn](#invalidatergn)、 [CWnd::UpdateWindow](#updatewindow)、または[RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911)  
  
##  <a name="reflectchildnotify"></a>  CWnd::ReflectChildNotify  
 このメッセージの関数がからフレームワークによって呼び出されます[OnChildNotify](#onchildnotify)です。  
  
```  
BOOL ReflectChildNotify(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 返送されるメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `pResult`  
 親ウィンドウによって返される子ウィンドウによって生成された結果です。 指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**メッセージがリフレクションされたそれ以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 反映するヘルパー関数は`message`のソースにします。  
  
 メッセージの送信に直接反映[返送](#onwndmsg)または[CCmdTarget::OnCmdMsg](../../mfc/reference/ccmdtarget-class.md#oncmdmsg)です。  
  
 メッセージ リフレクションの詳細については、次を参照してください。[反映されたメッセージの処理](../../mfc/handling-reflected-messages.md)です。  
  
##  <a name="reflectlastmsg"></a>  CWnd::ReflectLastMsg  
 このメンバー関数は、子ウィンドウへの最後のメッセージを反映するように、フレームワークによって呼び出されます。  
  
```  
static BOOL PASCAL ReflectLastMsg(
    HWND hWndChild,  
    LRESULT* pResult = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndChild`  
 子ウィンドウへのハンドル。  
  
 `pResult`  
 親ウィンドウによって返される子ウィンドウによって生成された結果です。 指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が呼び出す[SendChildNotifyLastMsg](#sendchildnotifylastmsg)でウィンドウが識別される場合`hWndChild`OLE コントロールまたはパーマネント マップ内のウィンドウ。  
  
 メッセージ リフレクションの詳細については、次を参照してください。[反映されたメッセージの処理](../../mfc/handling-reflected-messages.md)です。  
  
##  <a name="releasedc"></a>  CWnd::ReleaseDC  
 他のアプリケーションで使用して解放することをデバイス コンテキストを解放します。  
  
```  
int ReleaseDC(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 解放するためにデバイス コンテキストを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 効果、`ReleaseDC`メンバー関数は、デバイス コンテキストの種類によって異なります。  
  
 アプリケーションを呼び出す必要があります、`ReleaseDC`呼び出しごとにメンバー関数、 [GetWindowDC](#getwindowdc)メンバー関数と呼び出しごとに、 [GetDC](#getdc)メンバー関数。  
  
##  <a name="repositionbars"></a>  CWnd::RepositionBars  
 位置し、サイズは、ウィンドウのクライアント領域内のコントロール バーに呼び出されます。  
  
```  
void RepositionBars(UINT nIDFirst,
    UINT nIDLast,
    UINT nIDLeftOver,
    UINT nFlag = reposDefault,
    LPRECT lpRectParam = NULL,
    LPCRECT lpRectClient = NULL,
    BOOL bStretch = TRUE) ;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFirst`  
 最初の ID 範囲の位置とサイズのコントロール バーです。  
  
 `nIDLast`  
 コントロール バーの範囲内の最後の位置とサイズの ID。  
  
 `nIDLeftOver`  
 クライアント領域の残りの部分ペインの ID を指定します。  
  
 `nFlag`  
 次の値のいずれかを持つことができます。  
  
- **CWnd::reposDefault**コントロール バーのレイアウトを実行します。 `lpRectParam` 使用されず、できる**NULL**です。  
  
- **CWnd::reposQuery**コントロール バーのレイアウトは実行しません。 代わりに`lpRectParam`レイアウトが実際に行われた場合には、クライアント領域のサイズで初期化します。  
  
- **CWnd::reposExtra**の値を加算`lpRectParam`のクライアント領域に`nIDLast`レイアウトによっても実行します。  
  
 `lpRectParam`  
 指す、 [RECT 構造体](../../mfc/reference/rect-structure1.md); うち使用量は、の値によって決まります。`nFlag`です。  
  
 *lpRectClient*  
 指す、 [RECT 構造体](../../mfc/reference/rect-structure1.md)使用可能なクライアント領域を含んでいます。 場合**NULL**ウィンドウのクライアント領域が使用されます。  
  
 `bStretch`  
 フレームのサイズ、バーを拡大するかどうかを示します。  
  
### <a name="remarks"></a>コメント  
 `nIDFirst`と`nIDLast`パラメーターがクライアント領域内の位置を変更するコントロール バー Id の範囲を定義します。 `nIDLeftOver`パラメーターは再配置され、クライアント領域のコントロール バーの残りの部分を満たすようサイズ変更、子ウィンドウ (通常のビュー) の ID を指定します。  
  
##  <a name="runmodalloop"></a>  CWnd::RunModalLoop  
 取得、変換、またはまでメッセージをディスパッチする場合は、このメンバー関数を呼び出す[ContinueModal](#continuemodal)返します**FALSE**です。  
  
```  
int RunModalLoop(DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 Windows メッセージを送信するを指定します。 次のいずれかの値になります。  
  
- **MLF_NOIDLEMSG**送信しない[WM_ENTERIDLE](http://msdn.microsoft.com/library/windows/desktop/ms645422)親へのメッセージ。  
  
- **MLF_NOKICKIDLE**送信しない**WM_KICKIDLE**メッセージ ウィンドウにします。  
  
- **MLF_SHOWONIDLE**メッセージ キューがアイドル状態になったときに、ウィンドウを表示します。  
  
### <a name="return-value"></a>戻り値  
 値を指定します、`nResult`に渡されたパラメーター、[は](#endmodalloop)メンバー関数は、これはモーダル ループの最後に使用されます。  
  
### <a name="remarks"></a>コメント  
 既定では、`ContinueModal`返します**FALSE**後`EndModalLoop`と呼びます。 として指定された値を返します`nResult`に`EndModalLoop`です。  
  
##  <a name="screentoclient"></a>  CWnd::ScreenToClient  
 ディスプレイ上の指定された点または四角形の画面座標をクライアント座標に変換します。  
  
```  
void ScreenToClient(LPPOINT lpPoint) const;  void ScreenToClient(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoint`  
 指す、 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトまたは[POINT 構造体](../../mfc/reference/point-structure1.md)変換する画面座標を格納しています。  
  
 `lpRect`  
 指す、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)変換する画面座標を格納しています。  
  
### <a name="remarks"></a>コメント  
 `ScreenToClient`メンバー関数で指定した画面座標が置き換えられます`lpPoint`または`lpRect`クライアント座標を使用しています。 新しい座標の左上隅に対する相対パス、`CWnd`クライアント領域。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetItemRect](../../mfc/reference/clistctrl-class.md#getitemrect)です。  
  
##  <a name="scrollwindow"></a>  CWnd::ScrollWindow  
 現在のクライアント領域の内容をスクロール`CWnd`オブジェクト。  
  
```  
void ScrollWindow(
    int xAmount,  
    int yAmount,  
    LPCRECT lpRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `xAmount`  
 デバイス単位では、水平方向のスクロール、金額を指定します。 このパラメーターは、左にスクロールする負の値を指定する必要があります。  
  
 `yAmount`  
 デバイス単位では、垂直方向のスクロール、金額を指定します。 このパラメーターは、上にスクロールする負の値を指定する必要があります。  
  
 `lpRect`  
 指す、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)方向にスクロールするクライアント領域の部分を指定します。 場合`lpRect`は**NULL**、クライアント領域全体をスクロールします。 カーソルの四角形には、スクロールする四角形と交差している場合、カレットの位置を変更します。  
  
 `lpClipRect`  
 指す、`CRect`オブジェクトまたは`RECT`スクロールにクリッピング四角形を指定します。 この四角形の内部ビットだけがスクロールします。 この四角形の外側のビットである場合でも、`lpRect`四角形。 場合`lpClipRect`は**NULL**、スクロール四角形の領域は実行されません。  
  
### <a name="remarks"></a>コメント  
 カレットの場合、`CWnd`スクロールされる`ScrollWindow`を消去して、防ぐためにキャレットを自動的に隠されており、スクロールが完了したら、キャレットを復元します。 カレット位置を調整します。  
  
 領域がで検出された、`ScrollWindow`メンバー関数が再描画されませんが、現在に結合が`CWnd`オブジェクトの更新領域。 アプリケーションが最終的に表示される、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)領域が再描画する必要があることを通知するメッセージ。 スクロール終了、同時にカバーされていない領域を再描画呼び出し、[と](#updatewindow)メンバー関数は呼び出し直後後`ScrollWindow`です。  
  
 場合`lpRect`は**NULL**、ウィンドウで、子ウィンドウの位置のオフセットで指定された量`xAmount`と`yAmount`、および任意の無効なされていない領域で、`CWnd`ものオフセットします。 `ScrollWindow` ときに、高速`lpRect`は**NULL**です。  
  
 場合`lpRect`は**NULL**、子ウィンドウの位置での変更、および無効な領域ではない`CWnd`はオフセット排出されません。 防ぐために更新に関する問題と`lpRect`は**NULL**を呼び出す、`UpdateWindow`メンバー関数を再描画を`CWnd`呼び出す前に`ScrollWindow`です。  
  
##  <a name="scrollwindowex"></a>  CWnd::ScrollWindowEx  
 ウィンドウのクライアント領域の内容をスクロールします。  
  
```  
int ScrollWindowEx(
    int dx,  
    int dy,  
    LPCRECT lpRectScroll,  
    LPCRECT lpRectClip,  
    CRgn* prgnUpdate,  
    LPRECT lpRectUpdate,  
    UINT flags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dx`  
 デバイス単位では、水平方向のスクロール、金額を指定します。 このパラメーターには、負の値を左にスクロールする必要があります。  
  
 *dy*  
 デバイス単位では、垂直方向のスクロール、金額を指定します。 このパラメーターを上にスクロールする負の値が必要です。  
  
 `lpRectScroll`  
 指す、 [RECT 構造体](../../mfc/reference/rect-structure1.md)方向にスクロールするクライアント領域の部分を指定します。 このパラメーターが場合**NULL**、クライアント領域全体をスクロールします。  
  
 `lpRectClip`  
 指す、`RECT`スクロールにクリッピング四角形を指定します。 この構造体を指す四角形よりも優先`lpRectScroll`です。 この四角形の内部ビットだけがスクロールします。 この四角形の外側のビットである場合でも、`lpRectScroll`四角形。 このパラメーターが場合**NULL**、スクロール四角形の領域は実行されません。  
  
 *prgnUpdate*  
 スクロールによって無効となる領域を保持するために、修正される領域を識別します。 このパラメーターがあります**NULL**です。  
  
 `lpRectUpdate`  
 指す、`RECT`スクロールによって無効にする四角形の境界を受け取る。 このパラメーターがあります**NULL**です。  
  
 `flags`  
 次の値のいずれかを持つことができます。  
  
- **SW_ERASE**と共に指定すると**SW_INVALIDATE**、送信することによって、新しく無効化された領域を消去する[WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)ウィンドウにメッセージ。  
  
- **SW_INVALIDATE**で識別される領域を無効に*prgnUpdate*スクロール後します。  
  
- **SW_SCROLLCHILDREN**交差する四角形によって示されるすべての子ウィンドウをスクロール`lpRectScroll`ピクセル単位で指定された数だけ`dx`と*dy*です。 Windows の送信、 [WM_MOVE](http://msdn.microsoft.com/library/windows/desktop/ms632631)と交差するすべての子ウィンドウにメッセージ`lpRectScroll`移動しない場合でも、します。 子ウィンドウをスクロールし、カーソルの四角形には、スクロールする四角形と交差しているときにカーソルの位置を変更します。  
  
### <a name="return-value"></a>戻り値  
 戻り値は**SIMPLEREGION** (四角形の無効化された領域) **COMPLEXREGION** (四角形以外の無効化された領域、四角形の重複)、または**NULLREGION**(無効化された領域がありません)、関数が成功した場合、それ以外の場合、戻り値は**エラー**です。  
  
### <a name="remarks"></a>コメント  
 この関数がに似ていますが、 [ScrollWindow](http://msdn.microsoft.com/library/windows/desktop/bb787591)いくつかの機能での関数。  
  
 場合[SW_INVALIDATE](http://msdn.microsoft.com/library/windows/desktop/bb787593)と[SW_ERASE](http://msdn.microsoft.com/library/windows/desktop/bb787593)指定しない場合は、`ScrollWindowEx`メンバー関数は、領域の外にスクロールされて、無効です。 これらのフラグのいずれかを設定すると場合、`ScrollWindowEx`この領域を無効にします。 アプリケーションの呼び出しまでの領域は更新されません、[と](http://msdn.microsoft.com/library/windows/desktop/dd145167)メンバー関数を呼び出して、 [RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911)メンバー関数 (を指定する[RDW_UPDATENOW](http://msdn.microsoft.com/library/windows/desktop/dd162911)または[RDW_ERASENOW](http://msdn.microsoft.com/library/windows/desktop/dd162911))、または取得、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)アプリケーション キューからのメッセージ。  
  
 ウィンドウがある場合、 [WS_CLIPCHILDREN](http://msdn.microsoft.com/library/windows/desktop/ms632679)スタイル、返される領域で指定された*prgnUpdate*と`lpRectUpdate`更新する必要があります内の任意の領域を含むスクロール ウィンドウの合計領域を表す更新の必要な子ウィンドウ。  
  
 場合、 [SW_SCROLLCHILDREN](http://msdn.microsoft.com/library/windows/desktop/bb787593)フラグを指定すると、Windows は正しく更新されません画面子ウィンドウの一部がスクロール可能な場合です。 元の四角形の外側にあるスクロールした子ウィンドウの一部は削除されませんしが再描画されません正しく新しい送信先にします。 使用して、 [DeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632681) Windows の機能は完全に内に配置されていない移行の子ウィンドウ、`lpRectScroll`四角形。 場合、カーソル位置が、 **SW_SCROLLCHILDREN**フラグが設定され、カレット四角形には、スクロールする四角形が交差します。  
  
 すべての入力と出力の座標 (の`lpRectScroll`、 `lpRectClip`、 `lpRectUpdate`、および*prgnUpdate*) ウィンドウがあるかどうかに関係なく、クライアント座標であると見なされます、 **CS_OWNDC**または**CS_CLASSDC**クラスのスタイル。 使用して、 [LPtoDP](http://msdn.microsoft.com/library/windows/desktop/dd145042)と[行うには](http://msdn.microsoft.com/library/windows/desktop/dd162474)必要な場合、論理座標との間の変換をします。  
  
##  <a name="sendchildnotifylastmsg"></a>  CWnd::SendChildNotifyLastMsg  
 このメンバー関数は、子ウィンドウがタスクを処理できるように、親ウィンドウから子ウィンドウへ通知メッセージを提供するためにフレームワークによって呼び出されます。  
  
```  
BOOL SendChildNotifyLastMsg(LRESULT* pResult = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResult`  
 親ウィンドウによって返される子ウィンドウによって生成された結果です。  
  
### <a name="return-value"></a>戻り値  
 子ウィンドウの親に送信するメッセージが処理される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `SendChildNotifyLastMsg` リフレクションされたメッセージである場合は、現在のメッセージを元に送信します。  
  
 メッセージ リフレクションの詳細については、次を参照してください。[反映されたメッセージの処理](../../mfc/handling-reflected-messages.md)です。  
  
##  <a name="senddlgitemmessage"></a>  CWnd::SendDlgItemMessage  
 コントロールにメッセージを送信します。  
  
```  
LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 メッセージを受信するダイアログ コントロールの識別子を指定します。  
  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 コントロールが見つからなかった場合に、コントロールのウィンドウ プロシージャ、または 0 で返される値を指定します。  
  
### <a name="remarks"></a>コメント  
 `SendDlgItemMessage`メンバー関数は、メッセージが処理されるまでを返しません。  
  
 使用して`SendDlgItemMessage`を取得するのと同じでは、 `CWnd`* 指定されたコントロールと呼び出し元に、 [SendMessage](#sendmessage)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#113](../../mfc/reference/codesnippet/cpp/cwnd-class_54.cpp)]  
  
##  <a name="sendmessage"></a>  CWnd::SendMessage  
 このウィンドウに、指定したメッセージを送信します。  
  
```  
LRESULT SendMessage(
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 メッセージを処理の結果その値は、送信されたメッセージに依存します。  
  
### <a name="remarks"></a>コメント  
 **SendMessage**メンバー関数はウィンドウ プロシージャを直接呼び出し、そのウィンドウ プロシージャには、メッセージが処理されるまでは返しません。 これは、対照的に、 [PostMessage](#postmessage)メンバー関数がウィンドウのメッセージ キューにメッセージが配置され、すぐに返されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#101](../../mfc/reference/codesnippet/cpp/cwnd-class_41.cpp)]  
  
##  <a name="sendmessagetodescendants"></a>  ハンドラー  
 すべての子孫ウィンドウに指定された Windows メッセージを送信するには、このメンバー関数を呼び出します。  
  
```  
void SendMessageToDescendants(
    UINT message,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0,  
    BOOL bDeep = TRUE,  
    BOOL bOnlyPerm = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `bDeep`  
 検索するレベルを指定します。 場合**TRUE**、再帰的に場合、すべての子を検索する**FALSE**、直接の子のみを検索します。  
  
 `bOnlyPerm`  
 一時 windows でメッセージが発生するかどうかを指定します。 場合**TRUE**場合、一時 windows はメッセージを受信できます**FALSE**、永続的な windows には、メッセージが表示されるのみです。 一時的なウィンドウの詳細については、次を参照してください。[テクニカル ノート 3:](../../mfc/tn003-mapping-of-windows-handles-to-objects.md)です。  
  
### <a name="remarks"></a>コメント  
 場合`bDeep`は**FALSE**ウィンドウの直下の子にのみ、メッセージは送信以外のすべての子孫ウィンドウにメッセージを送信するそれ以外の場合。  
  
 場合`bDeep`と`bOnlyPerm`は**TRUE**、一時的なウィンドウの下に検索が続行されます。 ここでは、検索中に発生した永続的な windows だけでは、メッセージが表示されます。 場合`bDeep`は**FALSE**ウィンドウの直下の子にのみ、メッセージを送信します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#114](../../mfc/reference/codesnippet/cpp/cwnd-class_55.cpp)]  
  
##  <a name="sendnotifymessage"></a>  CWnd::SendNotifyMessage  
 ウィンドウに、指定したメッセージを送信します。  
  
```  
BOOL SendNotifyMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のスレッドによって、ウィンドウが作成された場合`SendNotifyMessage`ウィンドウのウィンドウ プロシージャを呼び出し、ウィンドウ プロシージャには、メッセージが処理されるまでは返しません。 ウィンドウを別のスレッドで作成した場合`SendNotifyMessage`ウィンドウ プロシージャにメッセージを渡すしを返します直ちに待機しませんが、メッセージの処理を終了するウィンドウ プロシージャ。  
  
##  <a name="setactivewindow"></a>  CWnd::SetActiveWindow  
 により、`CWnd`アクティブなウィンドウ。  
  
```  
CWnd* SetActiveWindow();
```  
  
### <a name="return-value"></a>戻り値  
 アクティブだったウィンドウです。  
  
 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 `SetActiveWindow`アプリケーション任意にアクティブなウィンドウや入力フォーカスを有効にすることができるので、注意してメンバー関数を使用する必要があります。 通常、Windows は、すべてのアクティブ化の行われます。  
  
##  <a name="setcapture"></a>  CWnd::SetCapture  
 後続のすべてのマウスが現在に送信される入力`CWnd`カーソルの位置に関係なくオブジェクト。  
  
```  
CWnd* SetCapture();
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウ オブジェクトへのポインターは、すべてのマウス入力を受け取っていた。 `NULL`そのようなウィンドウがない場合。 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 ときに`CWnd`必要なくなるとすべてのマウス入力をアプリケーションを呼び出す必要があります、 [ReleaseCapture](http://msdn.microsoft.com/library/windows/desktop/ms646261)関数の他のウィンドウでマウス入力を受信できるようにします。  
  
 マウス入力をキャプチャ中にない`WM_NCHITTEST`または`WM_SETCURSOR`作業中のウィンドウにメッセージが送信されます。  
  
##  <a name="setcaretpos"></a>  CWnd::SetCaretPos  
 カーソルの位置を設定します。  
  
```  
static void PASCAL SetCaretPos(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 新しい x と y を指定します (クライアント座標) で、そのキャレットの座標。  
  
### <a name="remarks"></a>コメント  
 `SetCaretPos`メンバー関数は、現在のタスク ウィンドウによって所有されている場合にのみにキャレットを移動します。 `SetCaretPos` カーソルが非表示かどうかは、カレットを移動します。  
  
 キャレットは、共有リソースです。 カレットを所有していない場合、ウィンドウは、カレットを移動できません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#115](../../mfc/reference/codesnippet/cpp/cwnd-class_56.cpp)]  
  
##  <a name="setclipboardviewer"></a>  CWnd::SetClipboardViewer  
 通知を受けるウィンドウのチェーンをこのウィンドウを追加します (により、`WM_DRAWCLIPBOARD`メッセージ)、クリップボードの内容が変更されるたびにします。  
  
```  
HWND SetClipboardViewer();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合、クリップボード ビューアー チェーンで次のウィンドウへのハンドル。 アプリケーションはこのハンドルを (メンバー変数とその格納できます) を保存する必要がありますクリップボード ビューアーのチェイン メッセージに応答してときに使用します。  
  
### <a name="remarks"></a>コメント  
 クリップボード ビューアーのチェーンの一部であるウィンドウに応答する必要があります[WM_DRAWCLIPBOARD](#ondrawclipboard)、 [WM_CHANGECBCHAIN](#onchangecbchain)、および[WM_DESTROY](#ondestroy)メッセージおよびメッセージを次に渡すチェーン内のウィンドウです。  
  
 このメンバー関数は、`WM_DRAWCLIPBOARD`ウィンドウにメッセージ。 クリップボード ビューアーのチェインで次のウィンドウのハンドルが返されていないため、アプリケーションを渡さないでください、`WM_DRAWCLIPBOARD`への呼び出し中に受信したメッセージ`SetClipboardViewer`です。  
  
 クリップボード ビューアーのチェインからそれ自体を削除するにアプリケーションを呼び出す必要があります、[ウィンドウ](#changeclipboardchain)メンバー関数。  
  
##  <a name="setdlgctrlid"></a>  CWnd::SetDlgCtrlID  
 ウィンドウ ID またはウィンドウのコントロール ID を新しい値に設定します。  
  
```  
int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コントロールの識別子に設定する新しい値。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、ウィンドウの以前の識別子それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウには、ダイアログ ボックス内のコントロールだけでなく、任意の子ウィンドウを指定できます。 ウィンドウには、トップレベル ウィンドウをすることはできません。  
  
##  <a name="setdlgitemint"></a>  CWnd::SetDlgItemInt  
 指定した整数値の文字列形式にダイアログ ボックスで、指定されたコントロールのテキストを設定します。  
  
```  
void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 変更するコントロールの整数の ID を指定します。  
  
 `nValue`  
 項目のテキストを生成するために使用する整数値を指定します。  
  
 `bSigned`  
 整数値が符号付きまたは符号なしかどうかを指定します。 このパラメーターは場合**TRUE**、`nValue`が署名されています。 このパラメーターは、する場合**TRUE**と`nValue`記号は、文字列の最初の桁の前に配置マイナス、0 より小さい。 このパラメーターが場合**FALSE**、`nValue`が署名されていません。  
  
### <a name="remarks"></a>コメント  
 `SetDlgItemInt` 送信、[によって](http://msdn.microsoft.com/library/windows/desktop/ms632644)指定されたコントロールするメッセージ。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::SetDlgItemText](#setdlgitemtext)です。  
  
##  <a name="setdlgitemtext"></a>  CWnd::SetDlgItemText  
 キャプションまたはウィンドウまたはダイアログ ボックスが所有するコントロールのテキストを設定します。  
  
```  
void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 設定するのには、テキストがコントロールを識別します。  
  
 `lpszString`  
 指す、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトまたはコントロールにコピーするテキストを表す null で終わる文字列。  
  
### <a name="remarks"></a>コメント  
 `SetDlgItemText` 送信、[によって](http://msdn.microsoft.com/library/windows/desktop/ms632644)指定されたコントロールするメッセージ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#116](../../mfc/reference/codesnippet/cpp/cwnd-class_57.cpp)]  
  
##  <a name="setforegroundwindow"></a>  CWnd::SetForegroundWindow  
 ウィンドウを作成したスレッドをフォアグラウンドに置き、そのウィンドウをアクティブにします。  
  
```  
BOOL SetForegroundWindow();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 キーボード入力は、ウィンドウに送られます、ユーザーのさまざまな視覚的な手掛かりが変更されています。 フォア グラウンド ウィンドウは、ユーザーが現在作業しているウィンドウです。 前面のウィンドウは、最上位のウィンドウ (フレーム ウィンドウまたはダイアログ ボックス) にのみ適用されます。  
  
### <a name="example"></a>例  
  例を参照して[:findwindow](#findwindow)です。  
  
##  <a name="setfocus"></a>  CWnd::SetFocus  
 入力フォーカスを要求します。  
  
```  
CWnd* SetFocus();
```  
  
### <a name="return-value"></a>戻り値  
 入力フォーカスを持っていたウィンドウ オブジェクトへのポインター。 **NULL**そのようなウィンドウがない場合。 返されたポインターは、一時的なと格納されません。  
  
### <a name="remarks"></a>コメント  
 入力フォーカスは、このウィンドウにすべての後続のキーボード入力を指示します。 入力フォーカスを持っていた任意のウィンドウでは、それが失われます。  
  
 `SetFocus`メンバー関数は、送信、 [WM_KILLFOCUS](http://msdn.microsoft.com/library/windows/desktop/ms646282)入力フォーカスを失うウィンドウにメッセージと[WM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/ms646283)ウィンドウへの入力フォーカスを受け取るメッセージ。 また、ウィンドウまたはその親のいずれかをアクティブになります。  
  
 現在のウィンドウはアクティブですが、フォーカスを持っていないかどうか (つまり、ウィンドウのフォーカスなし)、任意のキーが押されたが、メッセージを生成[wm_syschar です](#onsyschar)、 [WM_SYSKEYDOWN](#onsyskeydown)、または[WM_SYSKEYUP](#onsyskeyup).  
  
##  <a name="setfont"></a>  CWnd::SetFont  
 送信、`WM_SETFONT`ウィンドウにメッセージを指定したフォントを使用します。  
  
```  
void SetFont(
    CFont* pFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 ポインター、`CFont`オブジェクト。  
  
 `bRedraw`  
 `TRUE` その後すぐに再描画するウィンドウを処理、`WM_SETFONT`メッセージです。 それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドも何も起こりませんウィンドウを処理しない限り、`WM_SETFONT`メッセージ。 多くの MFC クラスから派生する`CWnd`用のメッセージ ハンドラーを含む定義済みのウィンドウ クラスにアタッチされているために、このメッセージを処理、`WM_SETFONT`メッセージ。 派生したクラスは、このメソッドを使用する`CWnd`のメソッドのハンドラーを定義する必要があります、`WM_SETFONT`メッセージ。  
  
##  <a name="seticon"></a>  CWnd::SetIcon  
 識別される特定のアイコンへのハンドルを設定するには、このメンバー関数を呼び出す`hIcon`です。  
  
```  
HICON SetIcon(
    HICON hIcon,  
    BOOL bBigIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 `hIcon`  
 以前のアイコンへのハンドル。  
  
 `bBigIcon`  
 場合は、32 ピクセルのアイコンによって 32 ピクセルを指定**TRUE**; 場合は、16 ピクセルのアイコンで 16 ピクセルを指定**FALSE**です。  
  
### <a name="return-value"></a>戻り値  
 アイコンにへのハンドル。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ クラスが登録されると、アイコンを選択します。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::GetSystemMenu](#getsystemmenu)です。  
  
##  <a name="setlayeredwindowattributes"></a>  CWnd::SetLayeredWindowAttributes  
 レイヤード ウィンドウの不透明度および透明度のカラー キーを設定します。  
  
```  
BOOL SetLayeredWindowAttributes(
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `crKey`  
 ポインター、 **COLORREF**レイヤード ウィンドウの作成に使用される透明色のキーを指定する値。 この色で、ウィンドウで描画されたすべてのピクセルは透過的になります。 生成する、 **COLORREF**、RGB マクロを使用します。  
  
 `bAlpha`  
 アルファ値がレイヤード ウィンドウの不透明度を記述するために使用します。 詳細については、次を参照してください。、 **SourceConstantAlpha**のメンバー、 [BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393)構造体。 ときに`bAlpha`が 0 の場合、ウィンドウが完全に透過的です。 ときに`bAlpha`255 は、ウィンドウは非透過的です。  
  
 `dwFlags`  
 実行するアクションを指定します。 このパラメーターには、次の値の 1 つ以上を指定できます。 使用可能な値の一覧は、次を参照してください。 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)です。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)Windows SDK で説明されている。  
  
##  <a name="setmenu"></a>  CWnd::SetMenu  
 指定されたメニューには、現在のメニューを設定します。  
  
```  
BOOL SetMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenu`  
 新しいメニューを識別します。 このパラメーターは、する場合**NULL**、現在のメニューを削除します。  
  
### <a name="return-value"></a>戻り値  
 メニューが変更された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューの変更を反映するように再描画されるウィンドウをによりします。  
  
 `SetMenu` 前のメニューは破棄されません。 アプリケーションを呼び出す必要があります、[メニューを破棄](../../mfc/reference/cmenu-class.md#destroymenu)このタスクを実行するメンバー関数。  
  
### <a name="example"></a>例  
  例を参照して[CMenu::LoadMenu](../../mfc/reference/cmenu-class.md#loadmenu)です。  
  
##  <a name="setowner"></a>  CWnd::SetOwner  
 指定されたウィンドウのオブジェクトを現在のウィンドウの所有者を設定します。  
  
```  
void SetOwner(CWnd* pOwnerWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pOwnerWnd*  
 ウィンドウ オブジェクトの新しい所有者を識別します。 このパラメーターは、する場合**NULL**ウィンドウのオブジェクトに所有者がありません。  
  
### <a name="remarks"></a>コメント  
 この所有者は、現在のウィンドウからコマンド メッセージを受け取ることができます。 既定では、現在のウィンドウの親は、その所有者はします。  
  
 ウィンドウの階層構造に関連しないウィンドウ オブジェクト間の接続を確立するために便利です。 たとえば、 [CToolBar](../../mfc/reference/ctoolbar-class.md)はその親の代わりにその所有者に通知を送信します。 これにより、ツールバー (埋め込み先フレーム ウィンドウに) などの別のウィンドウに通知を送信中に 1 つのウィンドウ (OLE コンテナー アプリケーションのウィンドウ) などの子になります。 さらに、[サーバー] ウィンドウが非アクティブ化またはインプレース中にアクティブ化時に編集するには、フレーム ウィンドウが所有するすべてのウィンドウが非表示または表示します。 この所有権が呼び出しを明示的に設定されて`SetOwner`です。  
  
 この関数の所有権の概念とは異なるの所有権の概念[GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms633515)です。  
  
##  <a name="setparent"></a>  CWnd::SetParent  
 子ウィンドウの親ウィンドウを変更します。  
  
```  
CWnd* SetParent(CWnd* pWndNewParent);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndNewParent*  
 新しい親ウィンドウを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合、以前親ウィンドウ オブジェクトへのポインター。 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 子ウィンドウが表示されている場合、Windows は、適切な再描画し、再描画を実行します。  
  
##  <a name="setproperty"></a>  CWnd::SetProperty  
 指定された OLE コントロール プロパティを設定するには、このメンバー関数を呼び出す`dwDispID`です。  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 設定するプロパティを識別します。  
  
 `vtProp`  
 設定するプロパティの型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 *...*  
 `vtProp`によって指定された型の 1 つのパラメーターです。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  この関数は、上でのみ呼び出す必要があります、 `CWnd` OLE コントロールを表すオブジェクト。  
  
 OLE コントロールのコンテナーでこのメンバー関数を使用する方法の詳細については、記事を参照してください。 [ActiveX コントロール コンテナー: ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング](../../mfc/programming-activex-controls-in-a-activex-control-container.md)です。  
  
##  <a name="setredraw"></a>  CWnd::SetRedraw  
 アプリケーションが呼び出す`SetRedraw`を再描画または変更が再描画されるようにするのには変更を許可します。  
  
```  
void SetRedraw(BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRedraw`  
 再描画フラグの状態を指定します。 場合、このパラメーターは**TRUE**、再描画フラグが設定されている場合は**FALSE**フラグをクリアします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、設定または再描画フラグをクリアします。 再描画フラグを消去すると、ときにコンテンツが変更するたびに更新されません、再描画フラグが設定されるまで再描画されません。 たとえば、リスト ボックスにいくつかの項目を追加する必要があるアプリケーション再描画フラグをオフに、項目を追加でき再描画フラグを設定できます。 最後に、アプリケーションが呼び出すことができます、 [Invalidate](#invalidate)または[InvalidateRect](#invalidaterect)メンバー関数をリスト ボックスに再描画が発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#117](../../mfc/reference/codesnippet/cpp/cwnd-class_58.cpp)]  
  
##  <a name="setscrollinfo"></a>  CWnd::SetScrollInfo  
 このメンバー関数の情報を設定、`SCROLLINFO`構造体がスクロール バーについて保持します。  
  
```  
BOOL SetScrollInfo(
    int nBar,  
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 スクロール バーのコントロールまたはウィンドウの非クライアント領域の一部であるかどうかを指定します。 非クライアント領域の一部では場合、れるは、水平、垂直にスクロール バーを配置するかどうかまたは両方にも示します。 次のいずれかを指定する必要があります。  
  
- **SB_CTL**スクロール バー コントロールのパラメーターが含まれています。 `m_hWnd`データ メンバーは、スクロール バー コントロールのハンドルをする必要があります。  
  
- **SB_HORZ**ウィンドウが水平スクロール バーをことを指定します。  
  
- **SB_VERT**ウィンドウが垂直スクロール バーをことを指定します。  
  
 `lpScrollInfo`  
 ポインター、 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造体。 この構造体の詳細については、Windows SDK を参照してください。  
  
 `bRedraw`  
 新しい位置を反映するように、スクロール バーを再描画されるかどうかを指定します。 場合`bRedraw`は**TRUE**、スクロール バーを再描画します。 場合は**FALSE**が再描画されません。 スクロール バーは、既定では再描画されます。  
  
### <a name="return-value"></a>戻り値  
 成功すると、戻り値が**TRUE**です。 以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537)構造体には、スクロール バーの最小値と最大スクロール位置、ページ サイズおよびスクロール ボックス (つまみ) の位置を含むに関する情報が含まれています。 参照してください、`SCROLLINFO`構造の既定値の変更の詳細については、Windows SDK のトピックを構造体。  
  
 MFC のウィンドウ メッセージ ハンドラーをスクロール バーの位置を示す[CWnd::OnHScroll](#onhscroll)と[ために](#onvscroll)、位置データの 16 ビットのみを提供します。 [GetScrollInfo](#getscrollinfo)と`SetScrollInfo`32 ビットのスクロール バーの位置のデータを提供します。 したがって、アプリケーションが呼び出すことができます`GetScrollInfo`いずれかの処理中に`CWnd::OnHScroll`または`CWnd::OnVScroll`32 ビットのスクロール バーの位置のデータを取得します。  
  
> [!NOTE]
> [CWnd::GetScrollInfo](#getscrollinfo)アプリケーションを 32 ビットのスクロール バーの位置を使用できます。  
  
##  <a name="setscrollpos"></a>  CWnd::SetScrollPos  
 スクロール ボックスの現在の位置を設定しは、要求された場合は、スクロール ボックスの新しい位置を反映するように、スクロール バーを再描画します。  
  
```  
int SetScrollPos(
    int nBar,  
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 設定するスクロール バーを指定します。 このパラメーターは、次のいずれかを指定できます。  
  
- **SB_HORZ**ウィンドウの水平スクロール バーのスクロール ボックスの位置を設定します。  
  
- **SB_VERT**ウィンドウの垂直スクロール バーのスクロール ボックスの位置を設定します。  
  
 `nPos`  
 スクロール ボックスの新しい位置を指定します。 スクロールの範囲でなければなりません。  
  
 `bRedraw`  
 スクロール ボックスの新しい位置を反映するように、スクロール バーを再描画するかどうかを指定します。 場合、このパラメーターは**TRUE**、スクロール バーが再描画される; 場合**FALSE**、スクロール バーが再描画されません。  
  
### <a name="return-value"></a>戻り値  
 スクロール ボックスの前の位置。  
  
### <a name="remarks"></a>コメント  
 設定`bRedraw`に**FALSE**は別の関数への後続の呼び出しによって、スクロール バーが再描画される場合に役立ちます。  
  
##  <a name="setscrollrange"></a>  CWnd::SetScrollRange  
 指定されたスクロール バーの最小位置と最大位置の値を設定します。  
  
```  
void SetScrollRange(
    int nBar,  
    int nMinPos,  
    int nMaxPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 設定するスクロール バーを指定します。 このパラメーターは、次の値のいずれかを指定できます。  
  
- **SB_HORZ**ウィンドウの水平スクロール バーの範囲を設定します。  
  
- **SB_VERT**ウィンドウの垂直スクロール バーの範囲を設定します。  
  
 `nMinPos`  
 最小スクロール位置を指定します。  
  
 `nMaxPos`  
 最大スクロール位置を指定します。  
  
 `bRedraw`  
 変更を反映するように、スクロール バーを再描画されるかどうかを指定します。 場合`bRedraw`は**TRUE**、スクロール バーが再描画される; 場合**FALSE**、スクロール バーが再描画されません。  
  
### <a name="remarks"></a>コメント  
 標準のスクロール バーを表示または非表示にも使用できます。  
  
 アプリケーションは、スクロール バーの通知メッセージの処理中に、スクロール バーを非表示にするには、この関数を呼び出さないでください。  
  
 場合への呼び出し`SetScrollRange`への呼び出しの直後に、 [SetScrollPos](#setscrollpos)メンバー関数の場合、`bRedraw`内のパラメーター、`SetScrollPos`メンバー関数が、スクロール バーが 2 回描画されていることを防止する場合は 0 にする必要があります。  
  
 標準のスクロール バーの既定の範囲は、0 ~ 100 です。 スクロール バー コントロールの既定の範囲が空 (両方、`nMinPos`と`nMaxPos`値は 0) です。 指定された値の差`nMinPos`と`nMaxPos`より大きくする必要がありますいない**INT_MAX**です。  
  
##  <a name="settimer"></a>  CWnd::SetTimer  
 システム タイマーをインストールします。  
  
```  
UINT_PTR SetTimer(
    UINT_PTR nIDEvent,  
    UINT nElapse,  
    void (CALLBACK* lpfnTimer)(HWND,  
    UINT, 
    UINT_PTR, 
    DWORD));
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDEvent`  
 0 以外のタイマーの識別子を指定します。 タイマーの識別子が一意の場合、この同じ値が `SetTimer` によって返されます。 一意でない場合、`SetTimer` は、新しい一意の値を指定して返します。 ウィンドウ タイマー (NULL コールバック関数を持つ) の場合、値は現在のウィンドウに関連付けられている他のウィンドウ タイマーについてのみ一意である必要があります。 コールバックのタイマーの場合、値はすべてのプロセスのすべてのタイマーで一意である必要があります。 したがって、コールバック タイマーを作成すると、戻り値が指定した値と異なる可能性が高くなります。  
  
 `nElapse`  
 タイムアウト値 (間隔) をミリ秒単位で指定します。  
  
 `lpfnTimer`  
 アプリケーションによって提供されるアドレス指定`TimerProc`を処理するコールバック関数、 [WM_TIMER](http://msdn.microsoft.com/library/windows/desktop/ms644902)メッセージ。 このパラメーターが `NULL` の場合、`WM_TIMER` メッセージはアプリケーションのメッセージ キューに登録され、`CWnd` オブジェクトによって処理されます。  
  
### <a name="return-value"></a>戻り値  
 関数が正常に完了した場合の、新しいタイマーのタイマー識別子。 この値は `nIDEvent` パラメーター経由で渡された値と一致する場合も異なる場合もあります。 アプリケーションは、戻り値を常に渡す必要があります、 [KillTimer](#killtimer)メンバー関数をタイマーを終了します。 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 間隔の値を指定すると、システムは間隔が経過するたびに、インストール アプリケーションのインストール メッセージ キューに `WM_TIMER` メッセージをポストするか、アプリケーション定義された `TimerProc` コールバック関数にメッセージを渡します。  
  
 `lpfnTimer` コールバック関数は `TimerProc` という名前である必要はありませんが、静的として宣言し、次のように定義する必要があります。  
  
```  
void CALLBACK TimerProc(
    HWND hWnd,   // handle of CWnd that called SetTimer  
    UINT nMsg,   // WM_TIMER  
    UINT_PTR nIDEvent,   // timer identification  
    DWORD dwTime    // system time);
```  
  
### <a name="example"></a>例  
 この例では、`CWnd::SetTimer`、`CWnd::OnTimer`、および `CWnd::KillTimer` を使用して、`WM_TIMER` メッセージを処理しています。 最初のタイマーは、`WM_TIMER` で 2 秒ごとにメイン フレーム ウィンドウに `OnStartTimer` メッセージを送信するように設定されます。 `OnTimer` イベント ハンドラーは、メイン フレーム ウィンドウ用に `WM_TIMER` メッセージを処理します。 このメソッドにより、PC スピーカーは 2 秒ごとにビープ音を鳴らします。 2 番目のタイマーは、3.75 秒ごとにコールバック関数にメッセージを送信します。 `OnStopTimer` は、各タイマー ID の `CWnd::KillTimer` を呼び出して、両方のタイマーを停止します。  
  
 [!code-cpp[NVC_MFCWindowing#118](../../mfc/reference/codesnippet/cpp/cwnd-class_59.cpp)]  
  
##  <a name="setwindowcontexthelpid"></a>  CWnd::SetWindowContextHelpId  
 ヘルプ コンテキスト識別子を指定したウィンドウに関連付けるには、このメンバー関数を呼び出します。  
  
```  
BOOL SetWindowContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwContextHelpId`  
 ヘルプ コンテキスト id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 子ウィンドウがヘルプ コンテキスト id を持たない場合、親ウィンドウの識別子を継承します。 同様に、所有されているウィンドウがヘルプ コンテキスト id を持たない場合は、そのオーナー ウィンドウの識別子を継承します。 この継承のヘルプ コンテキスト識別子には、ダイアログ ボックスの 1 つの識別子とそのすべてのコントロールを設定するアプリケーションができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#119](../../mfc/reference/codesnippet/cpp/cwnd-class_60.cpp)]  
  
##  <a name="setwindowplacement"></a>  CWnd::SetWindowPlacement  
 ウィンドウの表示状態、通常の位置 (復元された位置)、最小化された位置、および最大表示された位置を設定します。  
  
```  
BOOL SetWindowPlacement(const WINDOWPLACEMENT* lpwndpl);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpwndpl`  
 指す、 [WINDOWPLACEMENT](../../mfc/reference/windowplacement-structure.md)新しい表示状態と位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="setwindowpos"></a>  CWnd::SetWindowPos  
 サイズ、位置、および子、ポップアップ ウィンドウ、およびトップレベル ウィンドウの Z オーダーを変更します。  
  
```  
BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndInsertAfter`  
 識別、`CWnd`は前にあるオブジェクト (よりも高くなければ) この`CWnd`Z オーダー内のオブジェクト。 このパラメーターへのポインターを指定できます、`CWnd`または**ポインター**値は次のいずれかに。  
  
- **wndBottom**ウィンドウを Z オーダーの一番下に置きます。 この場合`CWnd`最上位のウィンドウは、ウィンドウが最上位の状態を失った以外の場合は、システムが他のすべてのウィンドウの下部にあるウィンドウを置きます。  
  
- **wndTop**ウィンドウを Z オーダーの一番上に置きます。  
  
- **wndTopMost**なる最上位すべて windows ウィンドウを置きます。 非アクティブ化する場合でも、ウィンドウは最上位の位置を保持します。  
  
- **wndNoTopMost**すべての非最上位のウィンドウの上部にウィンドウの位置を変更 (つまり、すべての最上位のウィンドウの背後にある)。 ウィンドウが非最上位のウィンドウで既に場合は、このフラグを指定しても効果はありません。  
  
 このパラメーターを使用する方法に関する規則は、このトピックの「解説」セクションを参照してください。  
  
 *x*  
 新しいウィンドウの左側の位置を指定します。  
  
 *y*  
 ウィンドウの上部の新しい位置を指定します。  
  
 `cx`  
 ウィンドウの新しい幅を指定します。  
  
 `cy`  
 ウィンドウの新しい高さを指定します。  
  
 `nFlags`  
 サイズ変更や配置オプションを指定します。 このパラメーターは、次のフラグの組み合わせを指定できます。  
  
- **SWP_DRAWFRAME**ウィンドウの周囲 (ウィンドウの作成時に定義されている) にフレームを描画します。  
  
- **SWP_FRAMECHANGED**送信、`WM_NCCALCSIZE`ウィンドウのサイズが変更されない場合でも、ウィンドウに表示するメッセージします。 このフラグが指定されていない場合`WM_NCCALCSIZE`ウィンドウのサイズが変更されるときにのみ送信されます。  
  
- **SWP_HIDEWINDOW**ウィンドウを非表示にします。  
  
- `SWP_NOACTIVATE` ウィンドウをアクティブにしません。 ウィンドウがアクティブ化し、最上位または最上位のないグループの先頭に移動このフラグが設定されていない場合 (の設定に応じて、`pWndInsertAfter`パラメーター)。  
  
- **SWP_NOCOPYBITS**クライアント領域の内容全体を破棄します。 このフラグが指定されていない場合、クライアント領域の有効な内容が保存され、ウィンドウのサイズまたは位置を変更した後、クライアント領域にコピーします。  
  
- `SWP_NOMOVE` 現在の位置を保持 (は無視、 *x*と*y*パラメーター)。  
  
- **SWP_NOOWNERZORDER** Z オーダーのオーナー ウィンドウの位置は変更されません。  
  
- **SWP_NOREDRAW**変更が再描画されません。 このフラグを設定すると、任意の種類の再描画する行われません。 これは、クライアント区分、(タイトルやスクロール バーを含む)、非クライアント領域およびウィンドウが移動した結果として検出された親ウィンドウの任意の部分に適用されます。 このフラグが設定されている場合、アプリケーション必要があります明示的が無効化または再描画する必要がある親ウィンドウとウィンドウの任意の部分を再描画します。  
  
- **SWP_NOREPOSITION**と同じ**SWP_NOOWNERZORDER**です。  
  
- **SWP_NOSENDCHANGING**受信できなくなります、ウィンドウ、`WM_WINDOWPOSCHANGING`メッセージ。  
  
- `SWP_NOSIZE` 現在のサイズを保持 (は無視、`cx`と`cy`パラメーター)。  
  
- `SWP_NOZORDER` 現在の順序が保持されます (無視`pWndInsertAfter`)。  
  
- **SWP_SHOWWINDOW**ウィンドウが表示されます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 Windows が画面で、Z オーダー; に従って順序付け順序で他のすべてのウィンドウの上に Z オーダーの上部にウィンドウが表示されます。  
  
 子ウィンドウのすべての座標は、(親ウィンドウのクライアント領域の左上隅) への相対クライアント座標です。  
  
 Z オーダーの最上部にウィンドウを移動できる設定するか、`pWndInsertAfter`パラメーターを **& wndTopMost**ことを確認して、`SWP_NOZORDER`フラグがありません設定かを設定して、ウィンドウの Z オーダーできるように、既存のすべてを超えていること最上位のウィンドウ。 非最上位のウィンドウは、最上位で行われたが、ときに、所有しているウィンドウは最上位でも行われます。 その所有者は変更されません。  
  
 最上位のウィンドウが最上位は、一番下に再配置される場合不要になった ( **& wndBottom**) Z オーダーの以降の任意の非最上位ウィンドウです。 最上位のウィンドウが行われる非最上位とすべての所有者に、および所有されるウィンドウも行われます非最上位ウィンドウです。  
  
 どちらの場合`SWP_NOACTIVATE`も`SWP_NOZORDER`を指定 (つまり、要求すると、アプリケーション ウィンドウで同時にアクティブ化され、配置される指定の Z オーダーで) で指定された値`pWndInsertAfter`は、次の状況でのみ使用します。  
  
-   どちらも **& wndTopMost**も **& wndNoTopMost**で指定された、`pWndInsertAfter`パラメーター。  
  
-   このウィンドウは、作業中のウィンドウではありません。  
  
 アプリケーションも Z オーダーの最上位に取り込むせず、非アクティブなウィンドウをアクティブにすることはできません。 アプリケーションでは、制限なしのアクティブ ウィンドウの Z オーダーを変更できます。  
  
 非最上位のウィンドウが最上位のウィンドウを所有できますが、その逆は不可能です。 行われたため、windows は、その所有者の上に所有されているすべての最上位ウィンドウ自体は、最上位のウィンドウが所有するウィンドウ (たとえば、ダイアログ ボックス)。  
  
 バージョン 3.1 以降では、Windows と共に windows Z オーダーの先頭に移動してそこでロックを設定して、 **WS_EX_TOPMOST**スタイル。 このような最上位ウィンドウは、非アクティブ化する場合でも最上位の位置を保持します。 たとえば、WinHelp Always On Top コマンドを選択することにより、最上位の [ヘルプ] ウィンドウやそのですし、アプリケーションに返す場合に表示されたままします。  
  
 最上位のウィンドウを作成するには`SetWindowPos`で、`pWndInsertAfter`パラメーターと等しい **& wndTopMost**、設定または、 **WS_EX_TOPMOST**ウィンドウを作成するときにスタイルを設定します。  
  
 Z オーダーで任意の windows に含まれる場合、 **WS_EX_TOPMOST**スタイル、と一緒に移動ウィンドウ、 **& wndTopMost**のすべての非最上位ウィンドウですが、最上位の上部にある値が格納されます。 アプリケーションがなしの非アクティブなウィンドウをアクティブにすると、 **WS_EX_TOPMOST** bit で、ウィンドウは移動上すべての非最上位のウィンドウが、最上位です。  
  
 場合`SetWindowPos`時に呼び出される、`pWndInsertAfter`パラメーターは **(& a) wndBottom**と`CWnd`最上位のウィンドウは、ウィンドウが最上位の状態を失った ( **WS_EX_TOPMOST**がオフになって)、およびシステムは、ウィンドウを Z オーダーの一番下に配置されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#120](../../mfc/reference/codesnippet/cpp/cwnd-class_61.cpp)]  
  
##  <a name="setwindowrgn"></a>  CWnd::SetWindowRgn  
 ウィンドウの領域を設定するには、このメンバー関数を呼び出します。  
  
```  
int SetWindowRgn(
    HRGN hRgn,  
    BOOL bRedraw);
```  
  
### <a name="parameters"></a>パラメーター  
 `hRgn`  
 領域へのハンドル。  
  
 `bRedraw`  
 場合**TRUE**、オペレーティング システムの地域を設定した後、ウィンドウを再描画です。 それ以外の場合はありません。 通常、設定`bRedraw`に**TRUE**ウィンドウが表示されている場合。 場合に設定**TRUE**、システムは、送信、`WM_WINDOWPOSCHANGING`と`WM_WINDOWPOSCHANGED`メッセージ ウィンドウにします。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は 0 以外の値です。 関数が失敗した場合は、0 を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのウィンドウ領域の座標では、ウィンドウのクライアント領域ではなく、ウィンドウの左上隅に対して相対的です。  
  
 呼び出しに成功した後`SetWindowRgn`、オペレーティング システムを領域ハンドルによって指定された領域を所有している`hRgn`です。 オペレーティング システムが、領域のコピーを作成できません、ので行わないと、さらに、この領域ハンドルを持つ関数呼び出しと、この領域ハンドルを終了しないでください。  
  
##  <a name="setwindowtext"></a>  CWnd::SetWindowText  
 指定したテキストをウィンドウのタイトルを設定します。  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 指す、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトまたは null で終わる文字列を新しいタイトルまたはコントロールのテキストとして使用できます。  
  
### <a name="remarks"></a>コメント  
 コントロールをウィンドウには、コントロール内のテキストが設定されます。  
  
 この関数により、[によって](http://msdn.microsoft.com/library/windows/desktop/ms632644)このウィンドウに送信されるメッセージにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#121](../../mfc/reference/codesnippet/cpp/cwnd-class_62.cpp)]  
  
##  <a name="showcaret"></a>  CWnd::ShowCaret  
 キャレットの現在位置にある画面にキャレットを表示します。  
  
```  
void ShowCaret();
```  
  
### <a name="remarks"></a>コメント  
 キャレットは、表示されると自動的に点滅します。  
  
 `ShowCaret`メンバー関数は、形状が現在していない非表示になって 2 回以上連続したかどうかにのみキャレットを表示します。 キャレットは、このウィンドウによって所有されていない、カーソルは表示されません。  
  
 カレットを非表示は、累積されます。 場合、 [HideCaret](#hidecaret)メンバー関数が呼び出された 5 回、連続して`ShowCaret`カレットを表示する 5 回を呼び出す必要があります。  
  
 キャレットは、共有リソースです。 ウィンドウは、入力フォーカスがある、またはアクティブな場合にのみ、カレットを表示する必要があります。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::CreateCaret](#createcaret)です。  
  
##  <a name="showownedpopups"></a>  CWnd::ShowOwnedPopups  
 このウィンドウが所有するすべてのポップアップ ウィンドウの表示と非表示を切り替えます。  
  
```  
void ShowOwnedPopups(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bShow`  
 ポップアップ ウィンドウを表示するか非表示にするかどうかを指定します。 このパラメーターは、する場合**TRUE**、すべての非表示のポップアップ ウィンドウが表示されます。 このパラメーターは場合**FALSE**、表示されているすべてのポップアップ ウィンドウが非表示になります。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::SetWindowPos](#setwindowpos)です。  
  
##  <a name="showscrollbar"></a>  CWnd::ShowScrollBar  
 スクロール バーの表示と非表示を切り替えます。  
  
```  
void ShowScrollBar(
    UINT nBar,  
    BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBar`  
 スクロール バーのコントロールまたはウィンドウの非クライアント領域の一部であるかどうかを指定します。 非クライアント領域の一部である場合`nBar`かどうか、スクロール バーが水平、垂直方向に配置されているか、どちらも示します。 次のいずれかを指定する必要があります。  
  
- **SB_BOTH**ウィンドウの水平方向および垂直のスクロール バーを指定します。  
  
- **SB_HORZ**ウィンドウが水平スクロール バーをことを指定します。  
  
- **SB_VERT**ウィンドウが垂直スクロール バーをことを指定します。  
  
 `bShow`  
 Windows を示していますまたは、スクロール バーを非表示にするかどうかを指定します。 このパラメーターは、する場合**TRUE**、スクロール バーが表示されます。 それ以外の場合、スクロール バーが非表示になります。  
  
### <a name="remarks"></a>コメント  
 アプリケーションを呼び出す必要がありますいない`ShowScrollBar`スクロール バーの通知メッセージの処理中に、スクロール バーを非表示にします。  
  
##  <a name="showwindow"></a>  また  
 ウィンドウの可視性の状態を設定します。  
  
```  
BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCmdShow`  
 指定方法、`CWnd`表示します。 次の値のいずれかを指定する必要があります。  
  
- **SW_HIDE**このウィンドウを非表示にし、別のウィンドウをアクティブ化を渡します。  
  
- **SW_MINIMIZE**ウィンドウを最小化し、システムの一覧にあるトップレベル ウィンドウをアクティブにします。  
  
- **SW_RESTORE**にアクティブし、ウィンドウを表示します。 ウィンドウが最小化、または最大化、Windows を元のサイズと位置に復元します。  
  
- **SW_SHOW**ウィンドウをアクティブにし、現在のサイズと位置で表示します。  
  
- **SW_SHOWMAXIMIZED**ウィンドウをアクティブにし、最大化されたウィンドウとして表示します。  
  
- **このメンバーは**ウィンドウをアクティブにし、アイコンとして表示します。  
  
- **SW_SHOWMINNOACTIVE**ウィンドウをアイコンとして表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNA**現在の状態で、ウィンドウが表示されます。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNOACTIVATE**最新サイズと位置でウィンドウを表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNORMAL**にアクティブし、ウィンドウを表示します。 ウィンドウが最小化、または最大化、Windows を元のサイズと位置に復元します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが表示されていた場合は 0 以外。0 の場合、`CWnd`非表示であった。  
  
### <a name="remarks"></a>コメント  
 `ShowWindow` 含むメイン ウィンドウをアプリケーションごとに 1 回だけ呼び出す必要があります[CWinApp::m_nCmdShow](../../mfc/reference/cwinapp-class.md#m_ncmdshow)です。 後続の呼び出し`ShowWindow`で指定された 1 つではなく上記の値のいずれかを使用する必要があります`CWinApp::m_nCmdShow`です。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::CalcWindowRect](#calcwindowrect)です。  
  
##  <a name="subclassdlgitem"></a>  CWnd::SubclassDlgItem  
 ダイアログ テンプレートから作成されたコントロールの「動的サブクラス化」には、このメンバー関数を呼び出すし、これにアタッチ`CWnd`オブジェクト。  
  
```  
BOOL SubclassDlgItem(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コントロールの id。  
  
 `pParent`  
 コントロールの親 (通常はダイアログ ボックス) です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 を通じて windows メッセージをルーティングはコントロールが動的にサブクラス化されたとき、`CWnd`のマップをメッセージし、メッセージのハンドラーを呼び出します、 `CWnd`'s クラスの最初。 基本クラスに渡されるメッセージは、コントロールの既定のメッセージ ハンドラーに渡されます。  
  
 このメンバー関数をアタッチする Windows のコントロール、`CWnd`オブジェクトを置き換えるコントロールの**WndProc**と**プロシージャ。**関数。 関数は、古いを格納**WndProc**によって返される場所に、`GetSuperWndProcAddr`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#122](../../mfc/reference/codesnippet/cpp/cwnd-class_63.cpp)]  
  
##  <a name="subclasswindow"></a>  CWnd::SubclassWindow  
 ウィンドウ「動的サブクラス化」には、このメンバー関数を呼び出すし、これにアタッチ`CWnd`オブジェクト。  
  
```  
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 ウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Windows メッセージのルーティングでウィンドウが動的にサブクラス化されたとき、`CWnd`のマップをメッセージし、メッセージのハンドラーを呼び出します、 `CWnd`'s クラスの最初。 基本クラスに渡されるメッセージは、ウィンドウの既定のメッセージ ハンドラーに渡されます。  
  
 このメンバー関数をアタッチする Windows のコントロール、`CWnd`オブジェクトし、ウィンドウ**WndProc**と**プロシージャ。**関数。 関数は、古いへのポインターを格納**WndProc**で、`CWnd`オブジェクト。  
  
> [!NOTE]
>  ウィンドウ必要があります既に接続できません、MFC オブジェクトをこの関数が呼び出されたとき。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#123](../../mfc/reference/codesnippet/cpp/cwnd-class_64.cpp)]  
  
##  <a name="unlockwindowupdate"></a>  CWnd::UnlockWindowUpdate  
 ロックされているウィンドウのロックを解除するには、このメンバー関数を呼び出す`CWnd::LockWindowUpdate`です。  
  
```  
void UnlockWindowUpdate();
```  
  
### <a name="remarks"></a>コメント  
 使用して、一度に 1 つのウィンドウをロックできる`LockWindowUpdate`です。 参照してください[CWnd::LockWindowUpdate](#lockwindowupdate)または Win32 関数[LockWindowUpdate](http://msdn.microsoft.com/library/windows/desktop/dd145034)ウィンドウのロックの詳細についてはします。  
  
##  <a name="unsubclasswindow"></a>  CWnd::UnsubclassWindow  
 設定するには、このメンバー関数を呼び出す**WndProc**元の値にバックアップし、デタッチによって識別されるウィンドウ`HWND`から、 **CWnd**オブジェクト。  
  
```  
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>戻り値  
 非サブクラス化されたウィンドウへのハンドル。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::SubclassWindow](#subclasswindow)です。  
  
##  <a name="updatedata"></a>  :Updatedata  
 このメンバー関数 ダイアログ ボックスでは、データの初期化または取得し、ダイアログ データ検証を呼び出します。  
  
```  
BOOL UpdateData(BOOL bSaveAndValidate = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bSaveAndValidate`  
 ダイアログ ボックスが初期化されているかどうかを示すフラグ ( **FALSE**) データを取得するか ( **TRUE**)。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。 場合*bSaveAndValidat*e は**TRUE**、し、戻り値のデータを正常に検証する 0 以外の場合。  
  
### <a name="remarks"></a>コメント  
 フレームワークが自動的に呼び出します`UpdateData`で`bSaveAndValidate`'éý' **FALSE**の既定の実装でモーダル ダイアログ ボックスを作成するときに[CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)です。 呼び出しは、ダイアログ ボックスが表示される前に発生します。 既定の実装[CDialog::OnOK](../../mfc/reference/cdialog-class.md#onok)でこのメンバー関数が呼び出さ`bSaveAndValidate`に設定**TRUE**データの取得に成功した場合は、ダイアログ ボックスを閉じます。 (ダイアログ ボックスで [キャンセル] ボタンをクリックすると、ダイアログ ボックスがされずに閉じ取得されるデータです。)  
  
##  <a name="updatedialogcontrols"></a>  ダイアログ  
 ダイアログ ボックスまたはを使用するウィンドウの他のコントロールやダイアログ ボタンの状態を更新するには、このメンバー関数を呼び出す、 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui)コールバック機構です。  
  
```  
void UpdateDialogControls(
    CCmdTarget* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTarget`  
 アプリケーションのメイン フレーム ウィンドウにポイントし、更新メッセージのルーティングのために使用します。  
  
 `bDisableIfNoHndler`  
 更新ハンドラーがないコントロールが無効として自動的に表示されるかどうかを示すフラグです。  
  
### <a name="remarks"></a>コメント  
 子コントロールには、ハンドラーがない場合および`bDisableIfNoHndler`は**TRUE**、子コントロールは無効になります。  
  
 フレームワークはこのメンバー関数ダイアログ バーまたはツールバーでのコントロールのアプリケーションの一部としてアイドル処理  
  
##  <a name="updatelayeredwindow"></a>  CWnd::UpdateLayeredWindow  
 レイヤード ウィンドウの位置、サイズ、形状、内容、および透明度を更新します。  
  
```  
BOOL UpdateLayeredWindow(
    CDC* pDCDst,  
    POINT* pptDst,  
    SIZE* psize,  
    CDC* pDCSrc,  
    POINT* pptSrc,  
    COLORREF crKey,  
    BLENDFUNCTION* pblend,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDCDst`  
 画面のデバイス コンテキストへのポインター。 ウィンドウの内容を更新する場合、パレットのカラー マッチングに使用されます。 場合`pDCDst`は**NULL**既定のパレットが使用されます。  
  
 場合`pDCSrc`は**NULL**、`pDCDst`する必要があります**NULL**です。  
  
 `pptDst`  
 ポインター、**ポイント**レイヤード ウィンドウの新しい画面上の位置を指定する構造体。 場合は、現在の位置は変化がない、`pptDst`できます**NULL**です。  
  
 *psize*  
 ポインター、**サイズ**レイヤード ウィンドウの新しいサイズを指定する構造体。 場合は、ウィンドウのサイズに変化がない、 *psize*できます**NULL**です。  
  
 場合`pDCSrc`は**NULL**、 *psize*する必要があります**NULL**です。  
  
 `pDCSrc`  
 レイヤード ウィンドウを定義するためのサーフェイスの DC へのポインター。 図形と、ウィンドウの表示のコンテキストを変更しない場合`pDCSrc`できます**NULL**です。  
  
 `pptSrc`  
 ポインター、**ポイント**デバイス コンテキストで、レイヤーの場所を指定します。  
  
 場合`pDCSrc`は**NULL**、`pptSrc`する必要があります**NULL**です。  
  
 `crKey`  
 ポインター、 **COLORREF**レイヤード ウィンドウの作成に使用される透明色のキーを指定する値。 この色で、ウィンドウで描画されたすべてのピクセルは透過的になります。 生成する、 **COLORREF**、RGB マクロを使用します。  
  
 *pblend*  
 ポインター、 [BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393)レイヤード ウィンドウの作成に使用される透明度の値を指定する構造体。  
  
 `dwFlags`  
 実行するアクションを指定します。 このパラメーターには、次の値の 1 つ以上を指定できます。 使用可能な値の一覧は、次を参照してください。 [UpdateLayeredWindow](http://msdn.microsoft.com/library/windows/desktop/ms633556)です。  
  
### <a name="return-value"></a>戻り値  
 関数が正常終了した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、関数の機能をエミュレート[UpdateLayeredWindow](http://msdn.microsoft.com/library/windows/desktop/ms633556)Windows SDK で説明されている。  
  
##  <a name="updatewindow"></a>  CWnd::UpdateWindow  
 送信することによってクライアント領域を更新、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージ更新領域が空でない場合。  
  
```  
void UpdateWindow();
```  
  
### <a name="remarks"></a>コメント  
 `UpdateWindow`メンバー関数は、送信、`WM_PAINT`アプリケーション キューをバイパスして、直接メッセージします。 更新領域が空の場合、`WM_PAINT`は送信されません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#124](../../mfc/reference/codesnippet/cpp/cwnd-class_65.cpp)]  
  
##  <a name="validaterect"></a>  CWnd::ValidateRect  
 ウィンドウの更新領域から四角形を削除することで、指定した四角形内のクライアント領域を検証します。  
  
```  
void ValidateRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)更新領域から削除する四角形のクライアント座標を格納しています。 場合`lpRect`は**NULL**、ウィンドウ全体を検証します。  
  
### <a name="remarks"></a>コメント  
 [BeginPaint](#beginpaint)メンバー関数は、クライアント領域全体を自動的に検証します。 どちらも、`ValidateRect`も[ValidateRgn](#validatergn)更新領域の一部は、前に検証する必要がある場合、メンバー関数を呼び出す必要があります[WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)は、次に生成します。  
  
 Windows が生成する継続`WM_PAINT`メッセージの現在の更新領域が検証されるまでです。  
  
##  <a name="validatergn"></a>  CWnd::ValidateRgn  
 ウィンドウの現在の更新領域から、領域を削除することによって指定された領域内のクライアント領域を検証します。  
  
```  
void ValidateRgn(CRgn* pRgn);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 ポインター、 [CRgn](../../mfc/reference/crgn-class.md)更新領域から削除するのには、領域を定義する領域を識別するオブジェクト。 このパラメーターが場合**NULL**、クライアント領域全体を削除します。  
  
### <a name="remarks"></a>コメント  
 指定された領域必要がありますによって作成された以前領域関数。 領域の座標は、クライアント座標であると見なされます。  
  
 [BeginPaint](#beginpaint)メンバー関数は、クライアント領域全体を自動的に検証します。 どちらも、 [ValidateRect](#validaterect)も`ValidateRgn`更新領域の一部を次の前に検証する必要がある場合、メンバー関数を呼び出す必要があります[WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージが生成されます。  
  
##  <a name="windowfrompoint"></a>  CWnd::WindowFromPoint  
 指定したポイントを含むウィンドウを取得します`point`画面上のポイントの画面座標を指定する必要があります。  
  
```  
static CWnd* PASCAL WindowFromPoint(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 指定します、 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトまたは[ポイント](../../mfc/reference/point-structure1.md)チェックするポイントを定義するデータ構造です。  
  
### <a name="return-value"></a>戻り値  
 ポイントにあるウィンドウ オブジェクトへのポインター。 **NULL**ウィンドウを特定の時点が存在しない場合。 返されるポインターは一時的である可能性があり、後で使用するために格納する必要があります。  
  
### <a name="remarks"></a>コメント  
 `WindowFromPoint` ポイントが、ウィンドウ内にある場合でも、非表示または無効になっているウィンドウを取得しません。 アプリケーションを使用する必要があります、[行いたいとき](#childwindowfrompoint)検索の制限のないメンバー関数。  
  
##  <a name="windowproc"></a>  CWnd::WindowProc  
 Windows の手順を示します ( `WindowProc`) の`CWnd`オブジェクト。  
  
```  
virtual LRESULT WindowProc(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 処理する Windows メッセージを指定します。  
  
 `wParam`  
 メッセージの処理で使用される追加情報を提供します。 パラメーターの値は、メッセージに依存します。  
  
 `lParam`  
 メッセージの処理で使用される追加情報を提供します。 パラメーターの値は、メッセージに依存します。  
  
### <a name="return-value"></a>戻り値  
 戻り値は、メッセージに依存します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのメッセージ マップを通じてメッセージをディスパッチします。  
  
##  <a name="winhelp"></a>  CWnd::WinHelp  
 WinHelp アプリケーションを起動します。  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwData`  
 追加のデータを指定します。 使用される値は、の値によって異なります、`nCmd`パラメーター。  
  
 `nCmd`  
 要求されるヘルプの種類を指定します。 指定できる値とどのように影響の一覧については、`dwData`パラメーターを参照してください、 [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) Windows SDK の Windows の機能です。  
  
### <a name="remarks"></a>コメント  
 参照してください[cwinapp::winhelp](../../mfc/reference/cwinapp-class.md#winhelp)詳細についてはします。  
  
##  <a name="registertouchwindow"></a>  CWnd::RegisterTouchWindow  
 登録するか、Windows タッチのサポートの登録を解除します。  
  
```  
BOOL RegisterTouchWindow(
    BOOL bRegister = TRUE,  
    ULONG ulFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegister`  
 `TRUE` レジスタを示す Windows のタッチ サポートです。`FALSE`それ以外の場合。  
  
 `ulFlags`  
 省略可能な変更を指定するビット フラグのセット。 このフィールドは、0 または値は次のいずれかを含めることがあります: TWF_FINETOUCH、TWF_WANTPALM です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resizedynamiclayout"></a>  CWnd::ResizeDynamicLayout  
 ウィンドウで動的レイアウトが有効な場合、子ウィンドウのレイアウトを調整するためにウィンドウのサイズが変更されると、フレームワークによって呼び出されます。  
  
```  
virtual void ResizeDynamicLayout();
```  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)
