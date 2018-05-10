---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
dev_langs:
- C++
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b292196eb6ac8178ba43f0e66bd4814368c916fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="coccmanager-class"></a>関数クラス
`COleControlContainer` オブジェクトと `COleControlSite` オブジェクトによって実装されるさまざまなカスタム コントロール サイトを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COccManager::CreateContainer](#createcontainer)|作成、 **COleContainer**オブジェクト。|  
|[COccManager::CreateDlgControls](#createdlgcontrols)|関連付けられたによってホストされている ActiveX コントロールを作成`COleContainer`オブジェクト。|  
|[COccManager::CreateSite](#createsite)|`COleClientSite` オブジェクトを作成します。|  
|[COccManager::GetDefBtnCode](#getdefbtncode)|既定のボタンのコードを取得します。|  
|[COccManager::IsDialogMessage](#isdialogmessage)|ダイアログ メッセージの対象を決定します。|  
|[COccManager::IsLabelControl](#islabelcontrol)|指定されたコントロールがラベル コントロールであるかどうかを判断します。|  
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|現在のアクセラレータ キーが指定されたコントロールのニーモニックと一致するかどうかを判断します。|  
|[COccManager::OnEvent](#onevent)|指定したイベントを処理しようとしています。|  
|[COccManager::PostCreateDialog](#postcreatedialog)|ダイアログの作成時に割り当てられているリソースを解放します。|  
|[COccManager::PreCreateDialog](#precreatedialog)|ActiveX コントロール用のダイアログ テンプレートを処理します。|  
|[COccManager::SetDefaultButton](#setdefaultbutton)|指定したコントロールの既定の状態を切り替えます。|  
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|指定したダイアログ テンプレートでのコモン コントロールから、既存の ActiveX コントロールを区切ります。|  
  
## <a name="remarks"></a>コメント  
 基本クラス、**ラップ**、(AFXTLS にありますドキュメントに未記載の基本クラスです。H)。 MFC フレームワークによっては、使用するために設計されたから派生したクラス、**ラップ**クラスは、メモリ リークの検出から除外されます。 直接派生させることはお勧めできません**ラップ**です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CNoTrackObject`  
  
 `COccManager`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxocc.h  
  
##  <a name="createcontainer"></a>  COccManager::CreateContainer  
 コントロールのコンテナーを作成するためにフレームワークによって呼び出されます。  
  
```  
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カスタムのサイト コンテナーに関連付けられたウィンドウ オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたコンテナーへのポインターそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 カスタムのサイトを作成する方法の詳細については、次を参照してください。 [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite)です。  
  
##  <a name="createdlgcontrols"></a>  COccManager::CreateDlgControls  
 指定された ActiveX コントロールを作成するには、この関数を呼び出して、`pOccDialogInfo`パラメーター。  
  
```  
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    LPCTSTR lpszResourceName,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

 
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    void* lpResource,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndParent*  
 ダイアログ オブジェクトの親へのポインター。  
  
 `lpszResourceName`  
 作成するリソースの名前。  
  
 `pOccDialogInfo`  
 ダイアログ オブジェクトの作成に使用するダイアログ テンプレートへのポインター。  
  
 `lpResource`  
 リソースへのポインター。  
  
### <a name="return-value"></a>戻り値  
 コントロールが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="createsite"></a>  COccManager::CreateSite  
 によって示されるコンテナーによってホストされるコントロール サイトを作成するためにフレームワークによって呼び出されます`pCtrlCont`です。  
  
```  
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCtrlCont`  
 新しいコントロール サイトをホストするコントロールのコンテナーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたコントロール サイトへのポインター。  
  
### <a name="remarks"></a>コメント  
 カスタム コントロールを作成するには、この関数をオーバーライドしてサイトを使用して、[メンバー](../../mfc/reference/colecontrolsite-class.md)-クラスを派生します。  
  
 各コントロールのコンテナーには、複数のサイトをホストできます。 複数の呼び出しで追加サイトを作成`CreateSite`です。  
  
##  <a name="getdefbtncode"></a>  COccManager::GetDefBtnCode  
 この関数では、コントロールが既定のプッシュ ボタンかどうかを決定します。  
  
```  
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ボタン コントロールを含むウィンドウのオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
- **DLGC_DEFPUSHBUTTON**コントロールがダイアログ ボックスで既定のボタンです。  
  
- **DLGC_UNDEFPUSHBUTTON**コントロールはダイアログ ボックスで既定のボタンではありません。  
  
- **0**コントロールがボタンではありません。  
  
##  <a name="isdialogmessage"></a>  COccManager::IsDialogMessage  
 かどうか、メッセージとを決定指定のダイアログ ボックスのためのものである場合は、メッセージを処理するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndDlg*  
 メッセージの対象となるダイアログへのポインター。  
  
 `lpMsg`  
 ポインター、`MSG`確認するメッセージを格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の動作`IsDialogMessage`はキーボード メッセージを確認し、対応するダイアログ ボックスの選択項目に変換します。 たとえば、TAB キーを押すと、[次へ] のコントロールまたはコントロールのグループを選択します。  
  
 指定されたダイアログに送信されるメッセージのカスタム動作を提供するには、この関数をオーバーライドします。  
  
##  <a name="islabelcontrol"></a>  COccManager::IsLabelControl  
 この関数では、指定されたコントロールがラベル コントロールかどうかを決定します。  
  
```  
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);  
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 コントロールを含むウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 コントロールのラベルである場合は 0 以外。それ以外の場合 0  
  
### <a name="remarks"></a>コメント  
 ラベル コントロールは、任意のコントロールは、順序付けにおける次のラベルのように機能する 1 つです。  
  
##  <a name="ismatchingmnemonic"></a>  COccManager::IsMatchingMnemonic  
 現在のアクセラレータ キーがコントロールによって表されると一致するかどうかを判断するには、この関数を呼び出します。  
  
```  
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,  
    LPMSG lpMsg);

 
static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 コントロールを含むウィンドウへのポインター。  
  
 `lpMsg`  
 ニーモニックを含むメッセージと一致するへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ニーモニック コントロールに一致する場合は 0 以外。それ以外の場合 0  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onevent"></a>  COccManager::OnEvent  
 指定したイベントを処理するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,  
    UINT idCtrl,  
    AFX_EVENT* pEvent,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *pCmdTarget*  
 ポインター、`CCmdTarget`オブジェクト、イベントを処理しようとしています。  
  
 `idCtrl`  
 コントロールのリソース ID です。  
  
 `pEvent`  
 処理されるイベント。  
  
 `pHandlerInfo`  
 ない場合**NULL**、`OnEvent`を入力、 **pTarget**と**pmf**のメンバー、 **AFX_CMDHANDLERINFO**の代わりに構造体コマンドをディスパッチします。 通常、このパラメーターを指定する必要があります**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 イベントが処理された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 イベント処理の既定のプロセスをカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="precreatedialog"></a>  COccManager::PreCreateDialog  
 実際のダイアログ ボックスを作成する前に ActiveX コントロールのダイアログ テンプレートを処理するためにフレームワークによって呼び出されます。  
  
```  
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,  
    const DLGTEMPLATE* pOrigTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 `pOccDialogInfo`  
 **_AFX_OCC_DIALOG_INFO**ダイアログ テンプレートと、ダイアログによってホストされているすべての ActiveX コントロールに関する情報を含む構造体。  
  
 *pOrigTemplate*  
 ダイアログ ボックスの作成に使用するダイアログ テンプレートへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスを作成するために使用するダイアログ テンプレート構造体へのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の動作への呼び出しは、`SplitDialogTemplate`任意 ActiveX がある場合は、存在制御を決定する、および、表示されるダイアログ テンプレートを返します。  
  
 ActiveX コントロールをホストしているダイアログ ボックスの作成のプロセスをカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="postcreatedialog"></a>  COccManager::PostCreateDialog  
 ダイアログ テンプレートに割り当てられたメモリを解放するためにフレームワークによって呼び出されます。  
  
```  
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pOccDialogInfo`  
 **_AFX_OCC_DIALOG_INFO**ダイアログ テンプレートと、ダイアログによってホストされているすべての ActiveX コントロールに関する情報を含む構造体。  
  
### <a name="remarks"></a>コメント  
 呼び出しでこのメモリが割り当てられた`SplitDialogTemplate`、すべてのホストされている ActiveX コントロール ダイアログ ボックスで使用されたとします。  
  
 ダイアログ ボックスのオブジェクトによって使用されているリソースをクリーンアップするプロセスをカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="setdefaultbutton"></a>  COccManager::SetDefaultButton  
 この関数では、既定のボタンとして設定します。  
  
```  
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,  
    BOOL bDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 コントロールを含むウィンドウへのポインター。  
  
 `bDefault`  
 以外の場合は、コントロールが既定のボタンになる必要があります。それ以外の場合 0 を返します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロールがあります、 **OLEMISC_ACTSLIKEBUTTON**ステータス ビットが設定されます。 詳細については**入ります**フラグを参照してください、[入ります](http://msdn.microsoft.com/library/windows/desktop/ms678497)Windows SDK のトピックです。  
  
##  <a name="splitdialogtemplate"></a>  COccManager::SplitDialogTemplate  
 コモン ダイアログ コントロールからの ActiveX コントロールを分割するためにフレームワークによって呼び出されます。  
  
```  
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,  
    DLGITEMTEMPLATE** ppOleDlgItems);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTemplate`  
 調査するダイアログ テンプレートへのポインター。  
  
 `ppOleDlgItems`  
 ActiveX コントロールは、ダイアログ ボックスの項目へのポインターのリスト。  
  
### <a name="return-value"></a>戻り値  
 非 ActiveX コントロールのみを含むダイアログ テンプレート構造体へのポインター。 ActiveX コントロールが、存在しない場合**NULL**が返されます。  
  
### <a name="remarks"></a>コメント  
 すべての ActiveX コントロールが見つからない場合は、テンプレートが分析され、非 ActiveX コントロールのみを含む、新しいテンプレートを作成します。 このプロセス中に見つかった任意の ActiveX コントロールに追加する`ppOleDlgItems`です。  
  
 テンプレートで、ActiveX コントロールがない場合**NULL**が返されます*です。*  
  
> [!NOTE]
>  新しいテンプレートが解放されるを割り当てられたメモリ、`PostCreateDialog`関数。  
  
 このプロセスをカスタマイズするには、この関数をオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [メンバー クラス](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer クラス](../../mfc/reference/colecontrolcontainer-class.md)
