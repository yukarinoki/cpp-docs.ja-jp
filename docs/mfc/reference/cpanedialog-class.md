---
title: CPaneDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
dev_langs:
- C++
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36f620f0a29e7d1715e7cb5bfb83c0685f97f643
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cpanedialog-class"></a>CPaneDialog クラス
`CPaneDialog`クラスは、モードレスでドッキング可能なダイアログ ボックスをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|既定のコンストラクター|  
|`CPaneDialog::~CPaneDialog`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneDialog::Create](#create)|ドッキング可能なダイアログ ボックスを作成しにアタッチ、`CPaneDialog`オブジェクト。|  
|`CPaneDialog::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CPaneDialog::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|処理、 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428)メッセージ。 (再定義`CBasePane::HandleInitDialog`)。|  
|`CPaneDialog::OnEraseBkgnd`|処理、 [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)メッセージ。 (再定義[CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd))。|  
|`CPaneDialog::OnLButtonDblClk`|処理、[した](http://msdn.microsoft.com/library/windows/desktop/ms645606)メッセージ。 (再定義[CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk))。|  
|`CPaneDialog::OnLButtonDown`|処理、 [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607)メッセージ。 (再定義[CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown))。|  
|`CPaneDialog::OnUpdateCmdUI`|ダイアログ ボックス ウィンドウを更新するためにフレームワークによって呼び出されます。 (上書き[cdockablepane::onupdatecmdui](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0))。|  
|`CPaneDialog::OnWindowPosChanging`|処理、 [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653)メッセージ。 (再定義[CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging))。|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|OLE コントロール コンテナーである ダイアログ ボックスのテンプレートを指定します。|  
  
## <a name="remarks"></a>コメント  
 構築、 `CPaneDialog` 2 つのステップ内のオブジェクト。 最初に、コード内のオブジェクトを構築します。 次に、呼び出す[CPaneDialog::Create](#create)です。 有効なリソースのテンプレートの名前またはテンプレートの ID を指定し、親ウィンドウへのポインターを渡す必要があります。 それ以外の場合、作成プロセスは失敗します。 ダイアログ ボックスでは、WS_CHILD と WS_VISIBLE スタイルを指定する必要があります。 WS_CLIPCHILDREN と WS_CLIPSIBLINGS のスタイルを指定することをお勧めします。 詳細については、次を参照してください。[ウィンドウ スタイル](styles-used-by-mfc.md#window-styles)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpanedialog.h  
  
##  <a name="create"></a>  CPaneDialog::Create  
 ドッキング ダイアログ ボックスを作成しにアタッチ、`CPaneDialog`オブジェクト。  
  
```  
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID,  
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

 
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszWindowName`  
 ドッキングのダイアログ ボックスの名前。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。  
  
 [入力] `bHasGripper`  
 `TRUE` キャプション (グリップ); をドッキング ダイアログ ボックスを作成するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `lpszTemplateName`  
 リソースのダイアログ テンプレートの名前。  
  
 [入力] `nStyle`  
 ウィンドウ スタイル。  
  
 [入力] `nID`  
 コントロールの id。  
  
 [入力] `nIDTemplate`  
 ダイアログ テンプレートのリソース ID です。  
  
 [入力] `dwTabbedStyle`  
 ユーザーがこのコントロールのウィンドウのキャプションにコントロールの別のウィンドウをドラッグしたときに結果をタブ付きウィンドウのスタイルです。 既定値は `AFX_CBRS_REGULAR_TABS` です。 詳細については、の「解説」セクションを参照してください、 [cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)メソッドです。  
  
 [入力] `dwControlBarStyle`  
 追加のスタイル属性。 既定値は `AFX_DEFAULT_DOCKING_PANE_STYLE` です。 詳細については、の「解説」セクションを参照してください、 [cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)メソッドです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
### <a name="example"></a>例  
 次の例で使用する方法、`Create`メソッドで、`CPaneDialog`クラスです。 この例の一部である、[ウィンドウのサイズを設定サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog  
 処理、 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428)メッセージ。  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wParam`  
 既定のキーボード フォーカスを受け取るコントロールへのハンドルします。  
  
 [入力] `lParam`  
 追加の初期化データを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このメソッドが成功した場合それ以外の場合、`FALSE`です。 さらに、`TRUE`で指定されたコントロールにキーボード フォーカスを設定、`wParam`パラメーターです。`FALSE`既定のキーボード フォーカスを設定できないようにします。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、このメソッドを使用して、コントロールとダイアログ ボックスの外観を初期化します。 フレームワークは、ダイアログ ボックスが表示される前に、このメソッドを呼び出します。  
  
##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo  
 OLE コントロール コンテナーである ダイアログ ボックスのテンプレートを指定します。  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOccDialogInfo`  
 ダイアログ ボックスのオブジェクトの作成に使用されるダイアログ ボックス テンプレートへのポインター。 このパラメーターの値が渡された後で、 [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols)メソッドです。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE`。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、サポート、[関数](../../mfc/reference/coccmanager-class.md)OLE コントロールのサイトと ActiveX コントロールを管理するクラス。 _AFX_OCC_DIALOG_INFO 構造は、afxocc.h ヘッダー ファイルで定義されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)



