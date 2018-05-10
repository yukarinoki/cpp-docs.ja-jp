---
title: メンバー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
dev_langs:
- C++
helpviewer_keywords:
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4dcb17c2650bf8b56702241a0ab4e77a3e2fc48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="colecontrolsite-class"></a>メンバー クラス
クライアント側のカスタム コントロール インターフェイスをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlSite::COleControlSite](#colecontrolsite)|`COleControlSite` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|ホストされるコントロールの既定のプロパティをデータ ソースにバインドします。|  
|[COleControlSite::BindProperty](#bindproperty)|ホストされるコントロールのプロパティをデータ ソースにバインドします。|  
|[COleControlSite::CreateControl](#createcontrol)|ホストされている ActiveX コントロールを作成します。|  
|[COleControlSite::DestroyControl](#destroycontrol)|ホストされるコントロールを破棄します。|  
|[COleControlSite::DoVerb](#doverb)|ホストされるコントロールの特定の動詞を実行します。|  
|[COleControlSite::EnableDSC](#enabledsc)|コントロール サイトをソースとなるデータを有効にします。|  
|[COleControlSite::EnableWindow](#enablewindow)|コントロール サイトを有効にします。|  
|[COleControlSite::FreezeEvents](#freezeevents)|コントロール サイトがイベントを受け入れるかどうかを指定します。|  
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|ホストされるコントロールの既定のボタンのコードを取得します。|  
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|コントロールの識別子を取得します。|  
|[COleControlSite::GetEventIID](#geteventiid)|ホストされるコントロールのイベント インターフェイスの ID を取得します。|  
|[COleControlSite::GetExStyle](#getexstyle)|コントロール サイトの拡張スタイルを取得します。|  
|[COleControlSite::GetProperty](#getproperty)|ホストされるコントロールの特定のプロパティを取得します。|  
|[COleControlSite::GetStyle](#getstyle)|コントロール サイトのスタイルを取得します。|  
|[COleControlSite::GetWindowText](#getwindowtext)|ホストされるコントロールのテキストを取得します。|  
|[COleControlSite::InvokeHelper](#invokehelper)|ホストされるコントロールの特定のメソッドを呼び出します。|  
|[COleControlSite::InvokeHelperV](#invokehelperv)|可変個引数リストでホストされるコントロールの特定のメソッドを呼び出します。|  
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|コントロールが、ウィンドウの既定のボタンであるかどうかを判断します。|  
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|コントロール サイトの表示の状態を確認します。|  
|[COleControlSite::ModifyStyle](#modifystyle)|現在の拡張コントロール サイトのスタイルを変更します。|  
|[COleControlSite::ModifyStyleEx](#modifystyleex)|コントロール サイトの現在のスタイルを変更します。|  
|[COleControlSite::MoveWindow](#movewindow)|コントロール サイトの位置を変更します。|  
|[COleControlSite::QuickActivate](#quickactivate)|クイックには、ホストされるコントロールがアクティブにします。|  
|[COleControlSite::SafeSetProperty](#safesetproperty)|プロパティまたはメソッドの例外をスローせず、コントロールを設定します。|  
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|ウィンドウの既定のボタンを設定します。|  
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|コントロールの識別子を取得します。|  
|[COleControlSite::SetFocus](#setfocus)|コントロール サイトへのフォーカスを設定します。|  
|[COleControlSite::SetProperty](#setproperty)|ホストされるコントロールの特定のプロパティを設定します。|  
|[COleControlSite::SetPropertyV](#setpropertyv)|可変個引数リストでホストされるコントロールの特定のプロパティを設定します。|  
|[COleControlSite::SetWindowPos](#setwindowpos)|コントロール サイトの位置を設定します。|  
|[COleControlSite::SetWindowText](#setwindowtext)|ホストされるコントロールのテキストを設定します。|  
|[COleControlSite::ShowWindow](#showwindow)|コントロール サイトの表示と非表示を切り替えます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](#getcontrolinfo)|キーボードの情報と、ホストされるコントロールのニーモニックを取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|ホストされるコントロールはウィンドウなしのコントロールであるかどうかを判断します。|  
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|キーボード コントロールの処理についてを説明します。|  
|[COleControlSite::m_dwEventSink](#m_dweventsink)|コントロールの接続ポイントのクッキー。|  
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|ホストされるコントロールの他の状態。|  
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|`IPropertyNotifySink`コントロールの cookie。|  
|[COleControlSite::m_dwStyle](#m_dwstyle)|ホストされるコントロールのスタイルです。|  
|[COleControlSite::m_hWnd](#m_hwnd)|コントロール サイトのハンドルです。|  
|[COleControlSite::m_iidEvents](#m_iidevents)|ホストされるコントロールのイベント インターフェイスの ID。|  
|[COleControlSite::m_nID](#m_nid)|ホストされるコントロールの ID。|  
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|ポインター、`IOleInPlaceActiveObject`ホストされるコントロールのオブジェクト。|  
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|ホストされるコントロールのコンテナーです。|  
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|ポインター、`IOleInPlaceObject`ホストされるコントロールのオブジェクト。|  
|[COleControlSite::m_pObject](#m_pobject)|ポインター、`IOleObjectInterface`コントロールのインターフェイスです。|  
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|ポインター、`IOleInPlaceObjectWindowless`コントロールのインターフェイスです。|  
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|ホストされるコントロールのウィンドウのオブジェクトへのポインター。|  
|[COleControlSite::m_rect](#m_rect)|コントロール サイトの寸法。|  
  
## <a name="remarks"></a>コメント  
 このサポートは、埋め込みの ActiveX コントロールが表示サイトのそのモニカー、そのユーザー インターフェイス、アンビエント プロパティ、およびコンテナーによって提供される他のリソースのエクステントと場所に関する情報を取得するための主要な手段です。 `COleControlSite` 完全に実装する、 [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502)、[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[していること](http://msdn.microsoft.com/library/windows/desktop/ms693706)、 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)、 **IBoundObjectSite**、 **INotifyDBEvents**、 [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md)インターフェイスです。 さらに、(アンビエント プロパティとイベント シンクのサポートを提供) の IDispatch インターフェイスも実装します。  
  
 ActiveX コントロール サイトを使用してを作成する`COleControlSite`からクラスを派生`COleControlSite`です。 `CWnd`-コンテナー (たとえば、ダイアログ ボックス) の派生クラスでオーバーライド、 **CWnd::CreateControlSite**関数。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxocc.h  
  
##  <a name="binddefaultproperty"></a>  COleControlSite::BindDefaultProperty  
 呼び出し元のオブジェクトの既定単純バインド プロパティをタイプ ライブラリでマークされたを基になるデータ ソース コントロールのデータ ソース、ユーザー名、パスワード、および SQL プロパティで定義されているカーソルにバインドします。  
  
```  
virtual void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 指定します、 **DISPID**のデータ ソース コントロールにバインドするのにはデータ バインド コントロールのプロパティです。  
  
 `vtProp`  
 バインドするプロパティの種類を指定 — たとえば、 `VT_BSTR`、 **VT_VARIANT**のようにします。  
  
 `szFieldName`  
 プロパティをバインドする、データ ソース コントロールによって提供されたカーソルで、列の名前を指定します。  
  
 `pDSCWnd`  
 ポインター、 `CWnd`-派生オブジェクトのプロパティをバインドするデータ ソース コントロールをホストします。  
  
### <a name="remarks"></a>コメント  
 `CWnd`この関数を呼び出すオブジェクトは、データ バインド コントロールである必要があります。  
  
##  <a name="bindproperty"></a>  COleControlSite::BindProperty  
 呼び出し元のオブジェクトの単純バインド プロパティをタイプ ライブラリでマークされたを基になるデータ ソース コントロールのデータ ソース、ユーザー名、パスワード、および SQL プロパティで定義されているカーソルにバインドします。  
  
```  
virtual void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispId*  
 指定します、 **DISPID**のデータ ソース コントロールにバインドするのにはデータ バインド コントロールのプロパティです。  
  
 `pWndDSC`  
 ポインター、 `CWnd`-派生オブジェクトのプロパティをバインドするデータ ソース コントロールをホストします。  
  
### <a name="remarks"></a>コメント  
 `CWnd`この関数を呼び出すオブジェクトは、データ バインド コントロールである必要があります。  
  
##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite  
 新しい `COleControlSite` オブジェクトを構築します。  
  
```  
explicit COleControlSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCtrlCont`  
 コントロールのコンテナー (AtiveX コントロールをホストするウィンドウを表す) へのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数は、 [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer)関数。 コンテナーの作成をカスタマイズする方法の詳細については、次を参照してください。 [COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite)です。  
  
##  <a name="createcontrol"></a>  COleControlSite::CreateControl  
 によってホストされている、ActiveX コントロールを作成、`COleControlSite`オブジェクト。  
  
```  
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);

 
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const POINT* ppt,  
    const SIZE* psize,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndCtrl`  
 コントロールを表す window オブジェクトへのポインター。  
  
 `clsid`  
 コントロールの一意のクラス ID。  
  
 `lpszWindowName`  
 コントロールに表示されるテキストへのポインター。 (該当する場合) は、winodw のキャプションまたはテキストのプロパティの値を設定します。  
  
 `dwStyle`  
 Windows のスタイルです。 使用できるスタイルは、下に表示されます、**解説**セクションです。  
  
 `rect`  
 コントロールのサイズと位置を指定します。 いずれかになります、`CRect`オブジェクトまたは`RECT`構造体。  
  
 `nID`  
 コントロールの子ウィンドウ ID を指定します  
  
 `pPersist`  
 ポインター、`CFile`コントロールの永続的な状態を格納します。 既定値は**NULL**、コントロール自体の初期化を永続的な記憶域からの状態を復元することがなくすることを示すです。 ない場合**NULL**へのポインターである必要があります、 `CFile`-、ストリームとストレージのどちらかの形式でのコントロールの永続的なデータを含むオブジェクトを派生します。 このデータは、クライアントの以前のライセンス認証で保存されている可能性があります。 `CFile`他のデータを含めることができますが、読み取り/書き込みを指すポインターへの呼び出し時に永続的なデータの最初のバイトに設定する必要があります`CreateControl`です。  
  
 `bStorage`  
 示すかどうかのデータ`pPersist`として解釈する必要があります`IStorage`または`IStream`データ。 場合内のデータ`pPersist`、記憶域は、`bStorage`する必要があります**TRUE**です。 場合内のデータ`pPersist`ストリーム、`bStorage`する必要があります**FALSE**です。 既定値は**FALSE**です。  
  
 `bstrLicKey`  
 省略可能なライセンス キー データ。 このデータは、実行時ライセンス キーが必要なコントロールを作成するためにのみ必要です。 コントロールは、ライセンスをサポートする場合を正常にコントロールを作成するためのライセンス キーを指定する必要があります。 既定値は**NULL**です。  
  
 `ppt`  
 ポインター、**ポイント**コントロールの左上隅を格納する構造体。 コントロールのサイズの値によって決まります*psize*です。 `ppt`と*psize*値のサイズを指定するオプションのメソッドは、および使用して、コントロールを配置します。  
  
 *psize*  
 ポインター、**サイズ**コントロールのサイズを格納する構造体。 左上隅の値によって決まります`ppt`です。 `ppt`と*psize*値のサイズを指定するオプションのメソッドは、および使用して、コントロールを配置します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 Windows のサブセットのみ`dwStyle`はフラグによって`CreateControl`:  
  
- **WS_VISIBLE**が最初に表示するウィンドウを作成します。 通常のウィンドウと同様に、すぐに表示するコントロールをするかどうかに必要です。  
  
- **WS_DISABLED**最初に無効になっているウィンドウを作成します。 無効になっているウィンドウは、ユーザーから入力を受け取ることはできません。 コントロールは Enabled プロパティを持つ場合、設定できます。  
  
- `WS_BORDER` 細い境界線でウィンドウを作成します。 コントロールに BorderStyle プロパティが設定されている場合、設定できます。  
  
- **WS_GROUP**コントロールのグループの最初のコントロールを指定します。 ユーザーを変更できますキーボード フォーカス、グループ内の 1 つのコントロールから、次への方向キーを使用しています。 定義されているすべてのコントロール、 **WS_GROUP**後、同じグループに属している、最初のコントロールのスタイルを設定します。 [次へ] のコントロールに、 **WS_GROUP**スタイルは、グループを終了し、[次へ] のグループを開始します。  
  
- **WS_TABSTOP**ユーザーが TAB キーを押すと、キーボード フォーカスを受信できるコントロールを指定します。 次のコントロールにキーボード フォーカスを移した TAB キーを押して、 **WS_TABSTOP**スタイル。  
  
 コントロールの既定のサイズを作成するのにには、2 番目のオーバー ロードを使用します。  
  
##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl  
 `COleControlSite` オブジェクトを破棄します。  
  
```  
virtual BOOL DestroyControl();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 完了すると、オブジェクトがメモリから解放すると、オブジェクトへのポインターは無効になります。  
  
##  <a name="doverb"></a>  COleControlSite::DoVerb  
 指定された動詞を実行します。  
  
```  
virtual HRESULT DoVerb(
    LONG nVerb,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nVerb`  
 実行する動詞を指定します。 これは、次のいずれかを含めることができます。  
  
|[値]|説明|シンボル|  
|-----------|-------------|------------|  
|0|主動詞|`OLEIVERB_PRIMARY`|  
|-1|セカンダリの動詞|(なし)|  
|1|編集するオブジェクトを表示します。|`OLEIVERB_SHOW`|  
|-2|別のウィンドウで項目を編集します。|`OLEIVERB_OPEN`|  
|-3|オブジェクトを非表示にします。|`OLEIVERB_HIDE`|  
|-4|場所でコントロールをアクティブにします。|`OLEIVERB_UIACTIVATE`|  
|-5|コントロール、インプレース、追加のユーザー インターフェイス要素を使用せずにアクティブにします。|**OLEIVERB_INPLACEACTIVATE**|  
|-7|コントロールのプロパティを表示します。|**OLEIVERB_PROPERTIES**|  
  
 `lpMsg`  
 アクティブ化する項目を原因となったメッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 この関数は、コントロールの`IOleObject`インターフェイスを指定した動詞を実行します。 この関数呼び出しの結果として例外がスローされた場合、`HRESULT`エラー コードが返されます。  
  
 詳細については、次を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK に含まれています。  
  
##  <a name="enabledsc"></a>  COleControlSite::EnableDSC  
 コントロール サイトのソースとなるデータを有効にします。  
  
```  
virtual void EnableDSC();
```  
  
### <a name="remarks"></a>コメント  
 有効にして、コントロールのサイトのソースとなるデータを初期化するためにフレームワークによって呼び出されます。 カスタマイズされた動作を提供するには、この関数をオーバーライドします。  
  
##  <a name="enablewindow"></a>  COleControlSite::EnableWindow  
 有効またはマウスおよびキーボード コントロール サイトへの入力を無効にします。  
  
```  
virtual BOOL EnableWindow(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 有効にするにまたはウィンドウを無効にするかどうかを指定します: **TRUE**ウィンドウの入力がそれ以外の場合、有効にする場合**FALSE**です。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが無効だった場合は 0 以外。 それ以外の場合に 0 です。  
  
##  <a name="freezeevents"></a>  COleControlSite::FreezeEvents  
 コントロール サイトを処理またはコントロールから発生したイベントを無視するかどうかを指定します。  
  
```  
void FreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>パラメーター  
 `bFreeze`  
 コントロール サイトにおけるイベントの受け取りを中止するかどうかを指定します。 コントロールがイベントを受け取らない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`bFreeze`は**TRUE**、コントロール サイト、コントロールにイベントを停止するように要求します。 場合`bFreeze`は**FALSE**、コントロール サイト コントロールのイベントの発生を続行するように要求します。  
  
> [!NOTE]
>  コントロールは、コントロールのサイトで要求されている場合は、イベントを発生させるを停止する必要はありません。 起動処理を続行できますが、コントロールのサイトですべての後続のイベントは無視されます。  
  
##  <a name="getcontrolinfo"></a>  COleControlSite::GetControlInfo  
 コントロールのニーモニックとキーボードの動作に関する情報を取得します。  
  
```  
void GetControlInfo();
```  
  
### <a name="remarks"></a>コメント  
 情報が格納されている[COleControlSite::m_ctlInfo](#m_ctlinfo)です。  
  
##  <a name="getdefbtncode"></a>  COleControlSite::GetDefBtnCode  
 コントロールが既定のプッシュ ボタンであるかどうかを判断します。  
  
```  
DWORD GetDefBtnCode();
```  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値になります。  
  
- **DLGC_DEFPUSHBUTTON**コントロールがダイアログ ボックスで既定のボタンです。  
  
- **DLGC_UNDEFPUSHBUTTON**コントロールはダイアログ ボックスで既定のボタンではありません。  
  
- **0**コントロールがボタンではありません。  
  
##  <a name="getdlgctrlid"></a>  COleControlSite::GetDlgCtrlID  
 コントロールの識別子を取得します。  
  
```  
virtual int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのダイアログの項目識別子です。  
  
##  <a name="geteventiid"></a>  COleControlSite::GetEventIID  
 コントロールの既定のイベント インターフェイスへのポインターを取得します。  
  
```  
BOOL GetEventIID(IID* piid);
```  
  
### <a name="parameters"></a>パラメーター  
 `piid`  
 インターフェイス ID へのポインター  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。 成功した場合、`piid`コントロールの既定のイベント インターフェイスのインターフェイス ID が含まれています。  
  
##  <a name="getexstyle"></a>  COleControlSite::GetExStyle  
 ウィンドウの拡張スタイルを取得します。  
  
```  
virtual DWORD GetExStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール ウィンドウのスタイルを拡張します。  
  
### <a name="remarks"></a>コメント  
 正規のスタイルを取得する[COleControlSite::GetStyle](#getstyle)です。  
  
##  <a name="getproperty"></a>  COleControlSite::GetProperty  
 指定されたコントロール プロパティを取得`dwDispID`です。  
  
```  
virtual void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 コントロールの既定のプロパティのディスパッチ ID を識別`IDispatch`インターフェイスを取得します。  
  
 `vtProp`  
 取得するプロパティの型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 `pvProp`  
 プロパティの値を受け取る変数のアドレスです。 指定された型に一致する必要があります`vtProp`です。  
  
### <a name="remarks"></a>コメント  
 値がによって返される`pvProp`です。  
  
##  <a name="getstyle"></a>  COleControlSite::GetStyle  
 コントロール サイトのスタイルを取得します。  
  
```  
virtual DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウのスタイルです。  
  
### <a name="remarks"></a>コメント  
 使用可能な値の一覧は、次を参照してください。 [Windows スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。 コントロール サイトの拡張スタイルを取得する[COleControlSite::GetExStyle](#getexstyle)です。  
  
##  <a name="getwindowtext"></a>  COleControlSite::GetWindowText  
 コントロールの現在のテキストを取得します。  
  
```  
virtual void GetWindowText(CString& str) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 参照、`CString`コントロールの現在のテキストを含むオブジェクトです。  
  
### <a name="remarks"></a>コメント  
 コントロールは、キャプションのストック プロパティをサポートする場合は、この値が返されます。 キャプションのストック プロパティがサポートされていない場合は、Text プロパティの値が返されます。  
  
##  <a name="invokehelper"></a>  COleControlSite::InvokeHelper  
 メソッドまたはプロパティで指定された呼び出します`dwDispID`で指定されたコンテキストで`wFlags`です。  
  
```  
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 プロパティまたはコントロールの メソッドのディスパッチ ID を識別`IDispatch`インターフェイスを起動します。  
  
 `wFlags`  
 Idispatch::invoke への呼び出しのコンテキストを記述するフラグ。 可能性がある`wFlags`値を参照してください`IDispatch::Invoke`Windows SDK に含まれています。  
  
 `vtRet`  
 戻り値の型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 `pvRet`  
 プロパティ値または戻り値を受け取る変数のアドレス。 これは、 `vtRet`によって指定される型と一致する必要があります。  
  
 `pbParamInfo`  
 `pbParamInfo`に従うパラメーターの型を指定するバイトの null で終わる文字列へのポインター。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 *...*  
 `pbParamInfo`で指定される型の、パラメーターの変数一覧。  
  
### <a name="remarks"></a>コメント  
 `pbParamInfo` パラメーターは、メソッドまたはプロパティに渡されるパラメーターの型を指定します。 可変個引数リストは、構文宣言で... で表されます。  
  
 この関数のパラメーターの変換**VARIANTARG**値、し、起動、 **idispatch::invoke**コントロールのメソッドです。 場合に呼び出し**idispatch::invoke**失敗した場合、この関数には、例外がスローされます。 によって、状態コードが返される場合**idispatch::invoke**は`DISP_E_EXCEPTION`、この関数がスローされます、 **COleDispatchException**オブジェクトがスローされますが、それ以外の場合、`COleException`です。  
  
##  <a name="invokehelperv"></a>  COleControlSite::InvokeHelperV  
 メソッドまたはプロパティで指定された呼び出します`dwDispID`で指定されたコンテキストで`wFlags`です。  
  
```  
virtual void InvokeHelperV(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo,  
    va_list argList);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 プロパティまたはコントロールの メソッドのディスパッチ ID を識別`IDispatch`インターフェイスを起動します。  
  
 `wFlags`  
 Idispatch::invoke への呼び出しのコンテキストを記述するフラグ。  
  
 `vtRet`  
 戻り値の型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 `pvRet`  
 プロパティ値または戻り値を受け取る変数のアドレス。 これは、 `vtRet`によって指定される型と一致する必要があります。  
  
 `pbParamInfo`  
 `pbParamInfo`に従うパラメーターの型を指定するバイトの null で終わる文字列へのポインター。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 `argList`  
 可変個引数リストへのポインター。  
  
### <a name="remarks"></a>コメント  
 `pbParamInfo` パラメーターは、メソッドまたはプロパティに渡されるパラメーターの型を指定します。 使用して、メソッドまたはプロパティが呼び出されている追加パラメーターを渡すことができます、 *va_list*パラメーター。  
  
 通常、この関数は`COleControlSite::InvokeHelper`します。  
  
##  <a name="isdefaultbutton"></a>  COleControlSite::IsDefaultButton  
 コントロールが既定のボタンであるかどうかを判断します。  
  
```  
BOOL IsDefaultButton();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールがある場合は 0 以外のウィンドウで、既定のボタンそれ以外の場合は 0 します。  
  
##  <a name="iswindowenabled"></a>  COleControlSite::IsWindowEnabled  
 コントロール サイトが有効になっているかどうかを判断します。  
  
```  
virtual BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、コントロールが有効になっている場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 値は、コントロールの Enabled のストック プロパティから取得されます。  
  
##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless  
 オブジェクトがウィンドウなしのコントロールであるかどうかを判断します。  
  
```  
BOOL m_bIsWindowless;  
```  
  
### <a name="remarks"></a>コメント  
 0 以外の値、コントロールがウィンドウを持たない場合は 0 です。  
  
##  <a name="m_ctlinfo"></a>  COleControlSite::m_ctlInfo  
 コントロールがキーボード入力を処理する方法について説明します。  
  
```  
CONTROLINFO m_ctlInfo;  
```  
  
### <a name="remarks"></a>コメント  
 この情報は、 [CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734)構造体。  
  
##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink  
 コントロールのイベント シンクの接続ポイントの cookie が含まれています。  
  
```  
DWORD m_dwEventSink;  
```  
  
##  <a name="m_dwmiscstatus"></a>  COleControlSite::m_dwMiscStatus  
 コントロールに関するその他の情報が含まれています。  
  
```  
DWORD m_dwMiscStatus;  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[入ります](http://msdn.microsoft.com/library/windows/desktop/ms678497)Windows SDK に含まれています。  
  
##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink  
 含まれています、 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)クッキー。  
  
```  
DWORD m_dwPropNotifySink;  
```  
  
##  <a name="m_dwstyle"></a>  COleControlSite::m_dwStyle  
 コントロールのウィンドウ スタイルが含まれています。  
  
```  
DWORD m_dwStyle;  
```  
  
##  <a name="m_hwnd"></a>  COleControlSite::m_hWnd  
 含まれています、 `HWND` 、コントロールのまたは**NULL**場合は、コントロールはウィンドウなしです。  
  
```  
HWND m_hWnd;  
```  
  
##  <a name="m_iidevents"></a>  COleControlSite::m_iidEvents  
 コントロールの既定のイベント シンク インターフェイスのインターフェイス ID が含まれています。  
  
```  
IID m_iidEvents;  
```  
  
##  <a name="m_nid"></a>  COleControlSite::m_nID  
 コントロールのダイアログの項目の ID が含まれています  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_pactiveobject"></a>  COleControlSite::m_pActiveObject  
 含まれています、 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299)コントロールのインターフェイスです。  
  
```  
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;  
```  
  
##  <a name="m_pctrlcont"></a>  COleControlSite::m_pCtrlCont  
 コントロールのコンテナー (フォームを表す) が含まれています。  
  
```  
COleControlContainer* m_pCtrlCont;  
```  
  
##  <a name="m_pinplaceobject"></a>  COleControlSite::m_pInPlaceObject  
 含まれています、 `IOleInPlaceObject` [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646)コントロールのインターフェイスです。  
  
```  
LPOLEINPLACEOBJECT m_pInPlaceObject;  
```  
  
##  <a name="m_pobject"></a>  COleControlSite::m_pObject  
 含まれています、 **IOleObjectInterface**コントロールのインターフェイスです。  
  
```  
LPOLEOBJECT m_pObject;  
```  
  
##  <a name="m_pwindowlessobject"></a>  COleControlSite::m_pWindowlessObject  
 含まれています、 `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304)コントロールのインターフェイスです。  
  
```  
IOleInPlaceObjectWindowless* m_pWindowlessObject;  
```  
  
##  <a name="m_pwndctrl"></a>  COleControlSite::m_pWndCtrl  
 ポインターが含まれています、`CWnd`コントロール自体を表すオブジェクト。  
  
```  
CWnd* m_pWndCtrl;  
```  
  
##  <a name="m_rect"></a>  COleControlSite::m_rect  
 コンテナーのウィンドウの基準とした、コントロールの境界が含まれています。  
  
```  
CRect m_rect;  
```  
  
##  <a name="modifystyle"></a>  COleControlSite::ModifyStyle  
 コントロールのスタイルを変更します。  
  
```  
virtual BOOL ModifyStyle(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwRemove`  
 現在のウィンドウ スタイルから削除されるスタイルです。  
  
 `dwAdd`  
 現在のウィンドウ スタイルを追加するスタイルです。  
  
 `nFlags`  
 ウィンドウ配置フラグ。 使用可能な値の一覧は、次を参照してください。、 [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Windows SDK 内の関数。  
  
### <a name="return-value"></a>戻り値  
 スタイルが変更された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 コントロールのストック Enabled プロパティは、の設定と一致するように変更が**WS_DISABLED**です。 要求された設定と一致するコントロールの境界線のスタイルのストック プロパティが変更されます`WS_BORDER`です。 他のすべてのスタイルは、いずれかが存在する場合、コントロールのウィンドウ ハンドルに直接適用されます。  
  
 コントロールのウィンドウ スタイルを変更します。 ビットごとの OR を使用してスタイルを追加または削除を組み合わせることができます ( &#124; ) 演算子。 参照してください、 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)について使用可能なウィンドウのスタイルは、Windows SDK 内の関数。  
  
 場合`nFlags`がゼロ以外、 `ModifyStyle` Win32 関数を呼び出す`SetWindowPos`、し、結合することで、ウィンドウを再描画`nFlags`の次の 4 つのフラグを使用。  
  
- `SWP_NOSIZE` 現在のサイズを保持します。  
  
- `SWP_NOMOVE` 現在の位置を保持します。  
  
- `SWP_NOZORDER` 現在の Z オーダーを保持します。  
  
- `SWP_NOACTIVATE` ウィンドウをアクティブにしません。  
  
 ウィンドウを変更するのスタイルを拡張[は](#modifystyleex)します。  
  
##  <a name="modifystyleex"></a>  COleControlSite::ModifyStyleEx  
 コントロールの拡張スタイルを変更します。  
  
```  
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwRemove`  
 現在のウィンドウ スタイルから削除する拡張スタイル。  
  
 `dwAdd`  
 現在のウィンドウ スタイルを追加する拡張スタイル。  
  
 `nFlags`  
 ウィンドウ配置フラグ。 使用可能な値の一覧は、次を参照してください。、 [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Windows SDK 内の関数。  
  
### <a name="return-value"></a>戻り値  
 スタイルが変更された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 設定と一致するコントロールの外観のストック プロパティが変更されます**WS_EX_CLIENTEDGE**です。 他のすべての拡張ウィンドウ スタイルは、いずれかが存在する場合、コントロールのウィンドウ ハンドルに直接適用されます。  
  
 ウィンドウの拡張コントロールのサイト オブジェクトのスタイルを変更します。 ビットごとの OR を使用してスタイルを追加または削除を組み合わせることができます ( &#124; ) 演算子。 参照してください、[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)について使用可能なウィンドウのスタイルは、Windows SDK 内の関数。  
  
 場合`nFlags`がゼロ以外、 `ModifyStyleEx` Win32 関数を呼び出す`SetWindowPos`、し、結合することで、ウィンドウを再描画`nFlags`の次の 4 つのフラグを使用。  
  
- `SWP_NOSIZE` 現在のサイズを保持します。  
  
- `SWP_NOMOVE` 現在の位置を保持します。  
  
- `SWP_NOZORDER` 現在の Z オーダーを保持します。  
  
- `SWP_NOACTIVATE` ウィンドウをアクティブにしません。  
  
 ウィンドウを変更するのスタイルを拡張[は](#modifystyle)します。  
  
##  <a name="movewindow"></a>  COleControlSite::MoveWindow  
 コントロールの位置を変更します。  
  
```  
virtual void MoveWindow(
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 新しいウィンドウの左側の位置。  
  
 *y*  
 ウィンドウの上部の新しい位置。  
  
 `nWidth`  
 新しいウィンドウの幅  
  
 `nHeight`  
 ウィンドウの新しい高さ。  
  
##  <a name="quickactivate"></a>  COleControlSite::QuickActivate  
 クイックには、コンテナー内のコントロールがアクティブにします。  
  
```  
virtual BOOL QuickActivate();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、コントロールのサイトがアクティブ化された場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 この関数は、ユーザーがコントロールの作成処理をオーバーライドする場合にのみ呼び出す必要があります。  
  
 `IPersist*::Load`と`IPersist*::InitNew`迅速なアクティブ化が発生した後、メソッドを呼び出す必要があります。 コントロールは、迅速なアクティブ化中に、コンテナーのシンクへの接続を確立する必要があります。 ただし、これらの接続は、ライブまで`IPersist*::Load`または`IPersist*::InitNew`が呼び出されています。  
  
##  <a name="safesetproperty"></a>  COleControlSite::SafeSetProperty  
 指定されたコントロール プロパティを設定`dwDispID`です。  
  
```  
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 プロパティまたはコントロールの メソッドのディスパッチ ID を識別`IDispatch`インターフェイスを設定します。  
  
 `vtProp`  
 設定するプロパティの型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 *...*  
 `vtProp`によって指定された型の 1 つのパラメーターです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  異なり`SetProperty`と`SetPropertyV`エラーが発生した場合 (存在しないプロパティを設定しようとしています) など、例外はスローされません。  
  
##  <a name="setdefaultbutton"></a>  COleControlSite::SetDefaultButton  
 コントロールは、既定のボタンとして設定します。  
  
```  
void SetDefaultButton(BOOL bDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDefault`  
 以外の場合は、コントロールが既定のボタンになる必要があります。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロールがあります、 **OLEMISC_ACTSLIKEBUTTON**ステータス ビットが設定されます。  
  
##  <a name="setdlgctrlid"></a>  COleControlSite::SetDlgCtrlID  
 コントロールのダイアログの項目識別子の値を変更します。  
  
```  
virtual int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 新しい識別子の値。  
  
### <a name="return-value"></a>戻り値  
 以前のダイアログがウィンドウの識別子をアイテム成功した場合、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setfocus"></a>  COleControlSite::SetFocus  
 コントロールにフォーカスを設定します。  
  
```  
virtual CWnd* SetFocus();  
virtual CWnd* SetFocus(LPMSG lpmsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpmsg*  
 ポインター、 [MSG 構造体](../../mfc/reference/msg-structure1.md)です。 この構造体を含む、Windows メッセージをトリガーする、`SetFocus`コントロールの現在のサイトに含まれているコントロールを要求します。  
  
### <a name="return-value"></a>戻り値  
 フォーカスを持っていたウィンドウへのポインター。  
  
##  <a name="setproperty"></a>  COleControlSite::SetProperty  
 指定されたコントロール プロパティを設定`dwDispID`です。  
  
```  
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 プロパティまたはコントロールの メソッドのディスパッチ ID を識別`IDispatch`インターフェイスを設定します。  
  
 `vtProp`  
 設定するプロパティの型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 *...*  
 `vtProp`によって指定された型の 1 つのパラメーターです。  
  
### <a name="remarks"></a>コメント  
 場合`SetProperty`エラーを検出すると、例外がスローされます。  
  
 例外の種類は、メソッドまたはプロパティを設定しようとするの戻り値によって決まります。 場合は、戻り値は`DISP_E_EXCEPTION`、 **COleDispatchExcpetion**がスローされた場合、`COleException`です。  
  
##  <a name="setpropertyv"></a>  COleControlSite::SetPropertyV  
 指定されたコントロール プロパティを設定`dwDispID`です。  
  
```  
virtual void SetPropertyV(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    va_list argList);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 プロパティまたはコントロールの メソッドのディスパッチ ID を識別`IDispatch`インターフェイスを設定します。  
  
 `vtProp`  
 設定するプロパティの型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)です。  
  
 `argList`  
 引数リストへのポインター。  
  
### <a name="remarks"></a>コメント  
 補足の余分なパラメーターのメソッドまたはプロパティが呼び出されているのできますを使用して、*補足*パラメーター。 場合`SetProperty`エラーを検出すると、例外がスローされます。  
  
 例外の種類は、メソッドまたはプロパティを設定しようとするの戻り値によって決まります。 場合は、戻り値は`DISP_E_EXCEPTION`、 **COleDispatchExcpetion**がスローされた場合、`COleException`です。  
  
##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos  
 サイズ、位置、およびコントロール サイトの Z オーダーを設定します。  
  
```  
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndInsertAfter`  
 ウィンドウへのポインター。  
  
 *x*  
 新しいウィンドウの左側の位置。  
  
 *y*  
 ウィンドウの上部の新しい位置。  
  
 `cx`  
 新しいウィンドウの幅  
  
 `cy`  
 ウィンドウの新しい高さ。  
  
 `nFlags`  
 ウィンドウ サイズ変更や配置フラグを指定します。 使用可能な値は、「解説」セクションを参照して[SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 ゼロ以外、成功した場合は 0 です。  
  
##  <a name="setwindowtext"></a>  COleControlSite::SetWindowText  
 コントロール サイトのテキストを設定します。  
  
```  
virtual void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszString`  
 新しいタイトルまたはコントロールのテキストとして使用する null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数は、まず、キャプションのストック プロパティを設定しようとします。 キャプションのストック プロパティがサポートされていない場合、テキスト プロパティが代わりにします。  
  
##  <a name="showwindow"></a>  COleControlSite::ShowWindow  
 ウィンドウの表示状態を設定します。  
  
```  
virtual BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCmdShow`  
 コントロール サイトを表示する方法を指定します。 次の値のいずれかを指定する必要があります。  
  
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
 ウィンドウが表示されていた場合は 0 以外。ウィンドウが非表示であった場合は 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleControlContainer クラス](../../mfc/reference/colecontrolcontainer-class.md)
