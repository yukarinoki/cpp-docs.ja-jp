---
title: CPaneDialog クラス |Microsoft Docs
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
ms.openlocfilehash: cc74f89708132b0895c8980538b852c15087b5e6
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43682328"
---
# <a name="cpanedialog-class"></a>CPaneDialog クラス
`CPaneDialog`クラスは、モードレスでドッキング可能なダイアログ ボックスをサポートしています。  
  
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
|[CPaneDialog::Create](#create)|ドッキング可能なダイアログ ボックスを作成しにアタッチします、`CPaneDialog`オブジェクト。|  
|`CPaneDialog::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CPaneDialog::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|処理、 [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog)メッセージ。 (再定義`CBasePane::HandleInitDialog`)。|  
|`CPaneDialog::OnEraseBkgnd`|処理、 [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd)メッセージ。 (再定義[CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd))。|  
|`CPaneDialog::OnLButtonDblClk`|処理、[した](/windows/desktop/inputdev/wm-lbuttondblclk)メッセージ。 (再定義[CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk))。|  
|`CPaneDialog::OnLButtonDown`|処理、 [WM_LBUTTONDOWN](/windows/desktop/inputdev/wm-lbuttondown)メッセージ。 (再定義[CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown))。|  
|`CPaneDialog::OnUpdateCmdUI`|ダイアログ ボックスのウィンドウを更新するためにフレームワークによって呼び出されます。 (上書き[cdockablepane::onupdatecmdui](cdockablepane-class.md))。|  
|`CPaneDialog::OnWindowPosChanging`|処理、 [WM_WINDOWPOSCHANGING](/windows/desktop/winmsg/wm-windowposchanging)メッセージ。 (再定義[CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging))。|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|OLE コントロール コンテナーは、ダイアログ ボックスのテンプレートを指定します。|  
  
## <a name="remarks"></a>Remarks  
 構築、 `CPaneDialog` 2 つのステップ内のオブジェクト。 最初に、コード内のオブジェクトを構築します。 次に、呼び出す[CPaneDialog::Create](#create)します。 有効なリソースのテンプレートの名前またはテンプレートの ID を指定して、親ウィンドウへのポインターを渡す必要があります。 それ以外の場合、作成プロセスは失敗します。 ダイアログ ボックスでは、WS_CHILD と WS_VISIBLE スタイルを指定する必要があります。 WS_CLIPCHILDREN と WS_CLIPSIBLINGS スタイルを指定することをお勧めします。 詳細については、次を参照してください。[ウィンドウ スタイル](styles-used-by-mfc.md#window-styles)します。  
  
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
 ドッキングのダイアログ ボックスを作成しにアタッチします、`CPaneDialog`オブジェクト。  
  
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
 [in]*したとき*  
 ドッキングのダイアログ ボックスの名前。  
  
 [in]*pParentWnd*  
 親ウィンドウへのポインター。  
  
 [in]*bHasGripper*  
 キャプション (グリップ); とドッキングのダイアログ ボックスを作成する場合は TRUEそれ以外の場合、FALSE です。  
  
 [in]*lpszTemplateName*  
 リソース ダイアログ テンプレートの名前。  
  
 [in]*nStyle*  
 Windows スタイルです。  
  
 [in]*nID*  
 コントロールの id。  
  
 [in]*nIDTemplate*  
 ダイアログ テンプレートのリソース ID。  
  
 [in]*dwTabbedStyle*  
 ユーザーがこのコントロールのウィンドウのキャプションに別のコントロール ペインをドラッグすると生成されるタブ付きウィンドウのスタイル。 既定値は、AFX_CBRS_REGULAR_TABS です。 詳細については、の「解説」を参照してください、 [cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)メソッド。  
  
 [in]*dwControlBarStyle*  
 追加のスタイル属性。 既定値は、AFX_DEFAULT_DOCKING_PANE_STYLE です。 詳細については、の「解説」を参照してください、 [cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex)メソッド。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
  
### <a name="example"></a>例  
 次の例では、使用する方法、`Create`メソッドで、`CPaneDialog`クラス。 この例は、[ウィンドウのサイズを設定サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog  
 処理、 [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog)メッセージ。  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*wParam*  
 既定のキーボード フォーカスを受け取るコントロールへのハンドルします。  
  
 [in]*lParam*  
 追加の初期化データを指定します。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。 さらに、TRUE がで指定されたコントロールにキーボード フォーカスを設定、 *wParam*パラメーターです。FALSE は、既定のキーボード フォーカスを設定できないようにします。  
  
### <a name="remarks"></a>Remarks  
 フレームワークでは、このメソッドを使用して、コントロールとダイアログ ボックスの外観を初期化します。 フレームワークは、ダイアログ ボックスを表示する前に、このメソッドを呼び出します。  
  
##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo  
 OLE コントロール コンテナーは、ダイアログ ボックスのテンプレートを指定します。  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pOccDialogInfo*  
 ダイアログ ボックスのオブジェクトを作成するために使用されるダイアログ ボックス テンプレートへのポインター。 このパラメーターの値が渡された後、 [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols)メソッド。  
  
### <a name="return-value"></a>戻り値  
 常に TRUE です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、サポート、 [COccManager](../../mfc/reference/coccmanager-class.md)クラスは、OLE コントロールのサイトと ActiveX コントロールを管理します。 _AFX_OCC_DIALOG_INFO 構造体は、afxocc.h ヘッダー ファイルで定義されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)



