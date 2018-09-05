---
title: COleControlSite クラス |Microsoft Docs
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
ms.openlocfilehash: 1c1d483f6ba532a6d8eeee1a8ec831cfd1d94b62
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766166"
---
# <a name="colecontrolsite-class"></a>COleControlSite クラス
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
|[COleControlSite::EnableDSC](#enabledsc)|コントロールのサイトのソースとなるデータを有効にします。|  
|[COleControlSite::EnableWindow](#enablewindow)|コントロール サイトを有効にします。|  
|[COleControlSite::FreezeEvents](#freezeevents)|コントロールのサイトがイベントを受け入れるかどうかを指定します。|  
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|ホストされるコントロールの既定のボタン コードを取得します。|  
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|コントロールの識別子を取得します。|  
|[COleControlSite::GetEventIID](#geteventiid)|ホストされるコントロールのイベント インターフェイスの ID を取得します。|  
|[COleControlSite::GetExStyle](#getexstyle)|コントロールのサイトの拡張スタイルを取得します。|  
|[COleControlSite::GetProperty](#getproperty)|ホストされるコントロールの特定のプロパティを取得します。|  
|[COleControlSite::GetStyle](#getstyle)|コントロール サイトのスタイルを取得します。|  
|[COleControlSite::GetWindowText](#getwindowtext)|ホストされるコントロールのテキストを取得します。|  
|[COleControlSite::InvokeHelper](#invokehelper)|ホストされるコントロールの特定のメソッドを呼び出します。|  
|[COleControlSite::InvokeHelperV](#invokehelperv)|可変個引数リストでホストされるコントロールの特定のメソッドを呼び出します。|  
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|コントロールがウィンドウの既定のボタンであるかどうかを判断します。|  
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|コントロールのサイトの表示状態を確認します。|  
|[COleControlSite::ModifyStyle](#modifystyle)|現在の拡張コントロールのサイトのスタイルを変更します。|  
|[COleControlSite::ModifyStyleEx](#modifystyleex)|コントロールのサイトの現在のスタイルを変更します。|  
|[COleControlSite::MoveWindow](#movewindow)|コントロールのサイトの位置を変更します。|  
|[COleControlSite::QuickActivate](#quickactivate)|クイックには、ホストされるコントロールがアクティブにします。|  
|[COleControlSite::SafeSetProperty](#safesetproperty)|プロパティまたはメソッドの例外をスローせず、コントロールを設定します。|  
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|ウィンドウの既定のボタンに設定します。|  
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|コントロールの識別子を取得します。|  
|[COleControlSite::SetFocus](#setfocus)|コントロール サイトへのフォーカスを設定します。|  
|[COleControlSite::SetProperty](#setproperty)|ホストされるコントロールの特定のプロパティを設定します。|  
|[COleControlSite::SetPropertyV](#setpropertyv)|可変個引数リストでホストされるコントロールの特定のプロパティを設定します。|  
|[COleControlSite::SetWindowPos](#setwindowpos)|コントロールのサイトの位置を設定します。|  
|[COleControlSite::SetWindowText](#setwindowtext)|ホストされるコントロールのテキストを設定します。|  
|[COleControlSite::ShowWindow](#showwindow)|コントロールのサイトの表示と非表示を切り替えます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](#getcontrolinfo)|キーボードの情報およびホストされるコントロールのニーモニックを取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|ホストされるコントロールがウィンドウなしのコントロールであるかどうかを判断します。|  
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|キーボード コントロールの処理についてを説明します。|  
|[COleControlSite::m_dwEventSink](#m_dweventsink)|コントロールの接続ポイントのクッキー。|  
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|ホストされるコントロールの他の状態。|  
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|`IPropertyNotifySink`コントロールのクッキー。|  
|[COleControlSite::m_dwStyle](#m_dwstyle)|ホストされるコントロールのスタイルです。|  
|[COleControlSite::m_hWnd](#m_hwnd)|コントロールのサイトのハンドル。|  
|[COleControlSite::m_iidEvents](#m_iidevents)|ホストされるコントロールのイベント インターフェイスの ID。|  
|[COleControlSite::m_nID](#m_nid)|ホストされるコントロールの ID。|  
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|ポインター、`IOleInPlaceActiveObject`ホストされるコントロールのオブジェクト。|  
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|ホストされるコントロールのコンテナーです。|  
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|ポインター、`IOleInPlaceObject`ホストされるコントロールのオブジェクト。|  
|[COleControlSite::m_pObject](#m_pobject)|ポインター、`IOleObjectInterface`コントロールのインターフェイス。|  
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|ポインター、`IOleInPlaceObjectWindowless`コントロールのインターフェイス。|  
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|ホストされるコントロールのウィンドウ オブジェクトへのポインター。|  
|[COleControlSite::m_rect](#m_rect)|コントロールのサイトのサイズ。|  
  
## <a name="remarks"></a>Remarks  
 このサポートは、埋め込みの ActiveX コントロールの場所とその表示サイト、そのモニカー、そのユーザー インターフェイス、アンビエント プロパティ、およびコンテナーによって提供されるその他のリソースの範囲に関する情報を取得するための主要な手段です。 `COleControlSite` 完全に実装、 [IOleControlSite](/windows/desktop/api/ocidl/nn-ocidl-iolecontrolsite)、[ビュー](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite)、[していること](/windows/desktop/api/oleidl/nn-oleidl-ioleclientsite)、 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)、 `IBoundObjectSite`、`INotifyDBEvents`、 [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md)インターフェイス。 さらに、(アンビエント プロパティとイベント シンクのサポートを提供する)、IDispatch インターフェイスが実装されてもします。  
  
 使用して ActiveX コントロール サイトを作成する`COleControlSite`からクラスを派生`COleControlSite`します。 `CWnd`-コンテナー (たとえば、ダイアログ ボックス) の派生クラスでオーバーライド、`CWnd::CreateControlSite`関数。  
  
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
 *dwDispID*  
 データ ソース コントロールにバインドするデータ バインド コントロールのプロパティの DISPID を指定します。  
  
 *vtProp*  
 バインドされるプロパティの種類を指定します: VT_BSTR、VT_VARIANT、およびなど。  
  
 *szFieldName*  
 プロパティのバインド先のデータ ソース コントロールによって提供される、カーソル内の列の名前を指定します。  
  
 *pDSCWnd*  
 ポインター、 `CWnd`-プロパティのバインド先のデータ ソース コントロールをホストする派生オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 `CWnd`オブジェクトがこの関数を呼び出すことは、データ バインド コントロールである必要があります。  
  
##  <a name="bindproperty"></a>  COleControlSite::BindProperty  
 基になるデータ ソース コントロールのデータ ソース、ユーザー名、パスワード、および SQL プロパティで定義されているカーソルを呼び出し元のオブジェクトの単純なバインド プロパティをタイプ ライブラリでマークされたをバインドします。  
  
```  
virtual void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispId*  
 データ ソース コントロールにバインドするデータ バインド コントロールのプロパティの DISPID を指定します。  
  
 *pWndDSC*  
 ポインター、 `CWnd`-プロパティのバインド先のデータ ソース コントロールをホストする派生オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 `CWnd`オブジェクトがこの関数を呼び出すことは、データ バインド コントロールである必要があります。  
  
##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite  
 新しい `COleControlSite` オブジェクトを構築します。  
  
```  
explicit COleControlSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>パラメーター  
 *pCtrlCont*  
 コントロールのコンテナー (を AtiveX コントロールをホストするウィンドウを表す) へのポインター。  
  
### <a name="remarks"></a>Remarks  
 この関数を呼び出して、 [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer)関数。 コンテナーの作成のカスタマイズの詳細については、次を参照してください。 [COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite)します。  
  
##  <a name="createcontrol"></a>  COleControlSite::CreateControl  
 によってホストされている ActiveX コントロールを作成、`COleControlSite`オブジェクト。  
  
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
 *pWndCtrl*  
 コントロールを表す window オブジェクトへのポインター。  
  
 *clsid*  
 コントロールの一意のクラス ID。  
  
 *したとき*  
 コントロールに表示されるテキストへのポインター。 (ある場合)、winodw のキャプションまたはテキストのプロパティの値を設定します。  
  
 *dwStyle*  
 Windows のスタイル。 使用可能なスタイルは、下に表示されます、**解説**セクション。  
  
 *rect*  
 コントロールのサイズと位置を指定します。 いずれかのことができます、`CRect`オブジェクトまたは`RECT`構造体。  
  
 *nID*  
 コントロールの子ウィンドウ ID を指定します  
  
 *pPersist*  
 ポインターを`CFile`コントロールの永続的な状態を格納します。 既定値は、null の場合、コントロール自体の初期化を任意の永続的なストレージからの状態を復元しないことを示すです。 ポインターである必要があります、NULL でない場合、 `CFile`-ストリームまたはストレージのいずれかの形式で、コントロールの永続的なデータを格納しているオブジェクトを派生します。 クライアントの以前のライセンス認証でこのデータが保存された可能性があります。 `CFile` 、他のデータを含めることができますが、読み取り/書き込みを指すポインターへの呼び出し時に永続的なデータの最初のバイトに設定する必要がありますがある`CreateControl`します。  
  
 *bStorage*  
 示すかどうかのデータ*pPersist*として解釈する必要があります`IStorage`または`IStream`データ。 場合内のデータ*pPersist* 、ストレージには、 *bStorage* TRUE にする必要があります。 場合内のデータ*pPersist*ストリーム、 *bStorage* FALSE にする必要があります。 既定値は FALSE です。  
  
 *bstrLicKey*  
 省略可能なライセンス キーのデータ。 このデータは、ランタイム ライセンス キーが必要なコントロールの作成にのみ必要です。 コントロールでは、ライセンスをサポートする場合を正常にコントロールを作成するためのライセンス キーを提供する必要があります。 既定値は、NULL です。  
  
 *ppt*  
 ポインターを`POINT`コントロールの左上隅を含む構造体。 コントロールのサイズの値によって決まります*psize*します。 *Ppt*と*psize*値のサイズを指定するオプションのメソッド、使用して、コントロールを配置します。  
  
 *psize*  
 ポインターを`SIZE`コントロールのサイズを含む構造体。 左上隅の値によって決まります*ppt*します。 *Ppt*と*psize*値のサイズを指定するオプションのメソッド、使用して、コントロールを配置します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 Windows のサブセットのみ*dwStyle*でフラグがサポートされる`CreateControl`:  
  
- WS_VISIBLE は、最初に表示されているウィンドウを作成します。 通常のウィンドウと同様に、すぐに表示されるコントロールをするかどうかに必要です。  
  
- WS_DISABLED は、最初に無効になっているウィンドウを作成します。 無効のウィンドウでは、ユーザーから入力を受け取ることはできません。 コントロールは、Enabled プロパティに設定できます。  
  
- WS_BORDER では、細い境界線でウィンドウを作成します。 コントロールが BorderStyle プロパティに設定できます。  
  
- WS_GROUP では、コントロールのグループの最初のコントロールを指定します。 ユーザーに変更できますキーボード フォーカス グループ内の 1 つのコントロールから、次の方向キーを使用しています。 最初のコントロールが同じグループに属している後に WS_GROUP スタイルで定義されたすべてのコントロール。 WS_GROUP スタイルでは、次のコントロールは、グループを終了し、[次へ] のグループを開始します。  
  
- WS_TABSTOP は、コントロール、ユーザーが TAB キーを押したときにキーボード フォーカスを受け取ることができますを指定します。 TAB キーを押して WS_TABSTOP スタイルの次のコントロールにキーボード フォーカスを変更します。  
  
 コントロールの既定のサイズを作成するのにには、2 番目のオーバー ロードを使用します。  
  
##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl  
 `COleControlSite` オブジェクトを破棄します。  
  
```  
virtual BOOL DestroyControl();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 完了すると、オブジェクトがメモリから解放され、オブジェクトへのポインターは無効になります。  
  
##  <a name="doverb"></a>  COleControlSite::DoVerb  
 指定した動詞を実行します。  
  
```  
virtual HRESULT DoVerb(
    LONG nVerb,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *nVerb*  
 実行する動詞を指定します。 次のいずれかを指定できます。  
  
|[値]|説明|シンボル|  
|-----------|-------------|------------|  
|0|主動詞|OLEIVERB_PRIMARY|  
|-1|セカンダリの動詞|(なし)|  
|1|編集するためのオブジェクトを表示します。|で|  
|-2|別のウィンドウで項目を編集します。|OLEIVERB_OPEN|  
|-3|オブジェクトを非表示にします。|OLEIVERB_HIDE|  
|-4|場所でコントロールをアクティブにします。|OLEIVERB_UIACTIVATE|  
|-5|コントロールでの場所、追加のユーザー インターフェイス要素を使用せずにアクティブにします。|OLEIVERB_INPLACEACTIVATE|  
|-7|コントロールのプロパティを表示します。|OLEIVERB_PROPERTIES|  
  
 *lpMsg*  
 アクティブ化する項目を原因となったメッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 この関数は、コントロールの直接呼び出し`IOleObject`インターフェイスを指定した動詞を実行します。 この関数呼び出しの結果として、例外がスローされた場合は、HRESULT エラー コードが返されます。  
  
 詳細については、次を参照してください。 [IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK に含まれています。  
  
##  <a name="enabledsc"></a>  COleControlSite::EnableDSC  
 コントロール サイトのソースとなるデータを有効にします。  
  
```  
virtual void EnableDSC();
```  
  
### <a name="remarks"></a>Remarks  
 有効にして、コントロールのサイトのソースとなるデータを初期化するためにフレームワークによって呼び出されます。 カスタマイズされた動作を提供するには、この関数をオーバーライドします。  
  
##  <a name="enablewindow"></a>  COleControlSite::EnableWindow  
 有効または、マウスとキーボード コントロール サイトへの入力を無効にします。  
  
```  
virtual BOOL EnableWindow(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnable*  
 有効または、ウィンドウを無効にするかどうかを指定します。 ウィンドウの入力が有効になっている、それ以外の場合は FALSE を指定する場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが無効だった場合は 0 以外。 それ以外の場合 0。  
  
##  <a name="freezeevents"></a>  COleControlSite::FreezeEvents  
 コントロールのサイトが処理またはコントロールから発生したイベントを無視するかどうかを指定します。  
  
```  
void FreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>パラメーター  
 *bFreeze*  
 コントロール サイトにおけるイベントの受け取りを中止するかどうかを指定します。 コントロールがイベントを受け取らない場合、0 以外の場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 場合*bFreeze*が true の場合、コントロールのサイトにイベントを停止するコントロールを要求します。 場合*bFreeze* false で、コントロールのサイトが引き続きイベントを発生させるコントロールを要求します。  
  
> [!NOTE]
>  コントロールは、コントロールのサイトによって要求された場合のイベントの発生を停止する必要はありません。 起動処理を続行できますが、後続のすべてのイベントは、コントロールのサイトで無視されます。  
  
##  <a name="getcontrolinfo"></a>  COleControlSite::GetControlInfo  
 コントロールのニーモニックのキーボードおよびキーボードの動作に関する情報を取得します。  
  
```  
void GetControlInfo();
```  
  
### <a name="remarks"></a>Remarks  
 情報が格納されている[COleControlSite::m_ctlInfo](#m_ctlinfo)します。  
  
##  <a name="getdefbtncode"></a>  COleControlSite::GetDefBtnCode  
 コントロールが既定のプッシュ ボタンであるかどうかを判断します。  
  
```  
DWORD GetDefBtnCode();
```  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値になります。  
  
- DLGC_DEFPUSHBUTTON コントロールは、ダイアログ ボックスで既定のボタンです。  
  
- DLGC_UNDEFPUSHBUTTON コントロールは、ダイアログ ボックスで既定のボタンではありません。  
  
- **0**コントロールがボタンではありません。  
  
##  <a name="getdlgctrlid"></a>  COleControlSite::GetDlgCtrlID  
 コントロールの識別子を取得します。  
  
```  
virtual int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのダイアログの項目の識別子です。  
  
##  <a name="geteventiid"></a>  COleControlSite::GetEventIID  
 コントロールの既定のイベント インターフェイスへのポインターを取得します。  
  
```  
BOOL GetEventIID(IID* piid);
```  
  
### <a name="parameters"></a>パラメーター  
 *piid*  
 インターフェイス ID へのポインター  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。 成功した場合、 *piid*コントロールの既定のイベント インターフェイスのインターフェイス ID が含まれています。  
  
##  <a name="getexstyle"></a>  COleControlSite::GetExStyle  
 ウィンドウの拡張スタイルを取得します。  
  
```  
virtual DWORD GetExStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール ウィンドウのスタイルを拡張します。  
  
### <a name="remarks"></a>Remarks  
 通常のスタイルを取得する[COleControlSite::GetStyle](#getstyle)します。  
  
##  <a name="getproperty"></a>  COleControlSite::GetProperty  
 指定されたコントロール プロパティを取得*dwDispID*します。  
  
```  
virtual void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispID*  
 コントロールの既定の検索、プロパティのディスパッチ ID を識別する`IDispatch`インターフェイスを取得します。  
  
 *vtProp*  
 取得するプロパティの型を指定します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)します。  
  
 *pvProp*  
 プロパティの値を受け取る変数のアドレス。 指定された型に一致する必要があります*vtProp*します。  
  
### <a name="remarks"></a>Remarks  
 値がによって返される*pvProp*します。  
  
##  <a name="getstyle"></a>  COleControlSite::GetStyle  
 コントロール サイトのスタイルを取得します。  
  
```  
virtual DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウのスタイル。  
  
### <a name="remarks"></a>Remarks  
 使用可能な値の一覧は、次を参照してください。 [Windows スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。 コントロールのサイトの拡張スタイルを取得する[COleControlSite::GetExStyle](#getexstyle)します。  
  
##  <a name="getwindowtext"></a>  COleControlSite::GetWindowText  
 コントロールの現在のテキストを取得します。  
  
```  
virtual void GetWindowText(CString& str) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *str*  
 参照を`CString`コントロールの現在のテキストを格納しているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 コントロールは、キャプションのストック プロパティをサポートする場合は、この値が返されます。 キャプションのストック プロパティがサポートされていない場合は、Text プロパティの値が返されます。  
  
##  <a name="invokehelper"></a>  COleControlSite::InvokeHelper  
 メソッドまたはプロパティで指定された呼び出します*dwDispID*で指定されたコンテキストで*wFlags*します。  
  
```  
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispID*  
 プロパティまたはコントロールのメソッドのディスパッチ ID を識別`IDispatch`インターフェイスを呼び出すことができます。  
  
 *wflags が*  
 Idispatch::invoke への呼び出しのコンテキストを記述するフラグ。 可能性があるのため*wflags が*値を参照してください`IDispatch::Invoke`Windows SDK に含まれています。  
  
 *変数*  
 戻り値の型を指定します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)します。  
  
 *pvRet*  
 プロパティ値または戻り値を受け取る変数のアドレス。 指定された型に一致する必要があります*変数*します。  
  
 *pbParamInfo*  
 次のパラメーターの型を指定するバイトの null で終わる文字列へのポインター *pbParamInfo*します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)します。  
  
 *...*  
 パラメーターで指定された型の変数一覧*pbParamInfo*します。  
  
### <a name="remarks"></a>Remarks  
 *PbParamInfo*パラメーターがメソッドまたはプロパティに渡されるパラメーターの型を指定します。 可変個引数リストは、構文宣言で... によってを表されます。  
  
 この関数は VARIANTARG 値にパラメーターを変換し、呼び出す、`IDispatch::Invoke`コントロールのメソッド。 場合に呼び出し`IDispatch::Invoke`失敗した場合、この関数には、例外がスローされます。 によって、状態コードが返される場合`IDispatch::Invoke`は`DISP_E_EXCEPTION`、この関数がスローされます、`COleDispatchException`オブジェクトがスローされますが、それ以外の場合、 `COleException`。  
  
##  <a name="invokehelperv"></a>  COleControlSite::InvokeHelperV  
 メソッドまたはプロパティで指定された呼び出します*dwDispID*で指定されたコンテキストで*wFlags*します。  
  
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
 *dwDispID*  
 プロパティまたはコントロールのメソッドのディスパッチ ID を識別`IDispatch`インターフェイスを呼び出すことができます。  
  
 *wflags が*  
 Idispatch::invoke への呼び出しのコンテキストを記述するフラグ。  
  
 *変数*  
 戻り値の型を指定します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)します。  
  
 *pvRet*  
 プロパティ値または戻り値を受け取る変数のアドレス。 指定された型に一致する必要があります*変数*します。  
  
 *pbParamInfo*  
 次のパラメーターの型を指定するバイトの null で終わる文字列へのポインター *pbParamInfo*します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)します。  
  
 *argList*  
 可変個引数リストへのポインター。  
  
### <a name="remarks"></a>Remarks  
 *PbParamInfo*パラメーターがメソッドまたはプロパティに渡されるパラメーターの型を指定します。 使用してメソッドまたはプロパティが呼び出される追加のパラメーターを渡すことができます、 *va_list*パラメーター。  
  
 通常、この関数は`COleControlSite::InvokeHelper`します。  
  
##  <a name="isdefaultbutton"></a>  COleControlSite::IsDefaultButton  
 コントロールが既定のボタンであるかどうかを判断します。  
  
```  
BOOL IsDefaultButton();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールの場合、0 以外の場合、ウィンドウの既定のボタンは 0 します。  
  
##  <a name="iswindowenabled"></a>  COleControlSite::IsWindowEnabled  
 コントロールのサイトが有効になっているかどうかを決定します。  
  
```  
virtual BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、コントロールが有効になっている場合は 0。  
  
### <a name="remarks"></a>Remarks  
 値は、コントロールの Enabled のストック プロパティから取得されます。  
  
##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless  
 オブジェクトがウィンドウなしのコントロールであるかどうかを判断します。  
  
```  
BOOL m_bIsWindowless;  
```  
  
### <a name="remarks"></a>Remarks  
 0 以外の場合、コントロールにウィンドウがあるない場合は 0。  
  
##  <a name="m_ctlinfo"></a>  COleControlSite::m_ctlInfo  
 コントロールによってキーボード入力を処理する方法について説明します。  
  
```  
CONTROLINFO m_ctlInfo;  
```  
  
### <a name="remarks"></a>Remarks  
 この情報が格納されている、 [CONTROLINFO](/windows/desktop/api/ocidl/ns-ocidl-tagcontrolinfo)構造体。  
  
##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink  
 コントロールのイベント シンクからの接続ポイントのクッキーを格納します。  
  
```  
DWORD m_dwEventSink;  
```  
  
##  <a name="m_dwmiscstatus"></a>  COleControlSite::m_dwMiscStatus  
 コントロールに関するその他の情報が含まれています。  
  
```  
DWORD m_dwMiscStatus;  
```  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。[入ります](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc)Windows SDK に含まれています。  
  
##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink  
 含まれています、 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)クッキー。  
  
```  
DWORD m_dwPropNotifySink;  
```  
  
##  <a name="m_dwstyle"></a>  COleControlSite::m_dwStyle  
 コントロールのウィンドウ スタイルが含まれています。  
  
```  
DWORD m_dwStyle;  
```  
  
##  <a name="m_hwnd"></a>  COleControlSite::m_hWnd  
 コントロールがウィンドウなしの場合、コントロールの HWND または NULL が含まれています。  
  
```  
HWND m_hWnd;  
```  
  
##  <a name="m_iidevents"></a>  COleControlSite::m_iidEvents  
 コントロールの既定のイベント シンク インターフェイスのインターフェイス ID を表します。  
  
```  
IID m_iidEvents;  
```  
  
##  <a name="m_nid"></a>  COleControlSite::m_nID  
 コントロールのダイアログの項目 ID が含まれています  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_pactiveobject"></a>  COleControlSite::m_pActiveObject  
 含まれています、 [IOleInPlaceActiveObject](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceactiveobject)コントロールのインターフェイス。  
  
```  
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;  
```  
  
##  <a name="m_pctrlcont"></a>  COleControlSite::m_pCtrlCont  
 (フォームを表す) コントロールのコンテナーが含まれています。  
  
```  
COleControlContainer* m_pCtrlCont;  
```  
  
##  <a name="m_pinplaceobject"></a>  COleControlSite::m_pInPlaceObject  
 含まれています、 `IOleInPlaceObject` [IOleInPlaceObject](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceobject)コントロールのインターフェイス。  
  
```  
LPOLEINPLACEOBJECT m_pInPlaceObject;  
```  
  
##  <a name="m_pobject"></a>  COleControlSite::m_pObject  
 含まれています、`IOleObjectInterface`コントロールのインターフェイス。  
  
```  
LPOLEOBJECT m_pObject;  
```  
  
##  <a name="m_pwindowlessobject"></a>  COleControlSite::m_pWindowlessObject  
 含まれています、 `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless)コントロールのインターフェイス。  
  
```  
IOleInPlaceObjectWindowless* m_pWindowlessObject;  
```  
  
##  <a name="m_pwndctrl"></a>  COleControlSite::m_pWndCtrl  
 ポインターが含まれています、`CWnd`コントロール自体を表すオブジェクト。  
  
```  
CWnd* m_pWndCtrl;  
```  
  
##  <a name="m_rect"></a>  COleControlSite::m_rect  
 コンテナーのウィンドウを基準とした、コントロールの境界が含まれています。  
  
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
 *dwRemove*  
 現在のウィンドウ スタイルから削除するスタイル。  
  
 *dwAdd*  
 現在のウィンドウ スタイルを追加するスタイル。  
  
 *nFlags*  
 ウィンドウの配置フラグ。 使用可能な値の一覧は、次を参照してください。、 [SetWindowPos](/windows/desktop/api/winuser/nf-winuser-setwindowpos) Windows SDK 内の関数。  
  
### <a name="return-value"></a>戻り値  
 スタイルが変更された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 WS_DISABLED の設定と一致するコントロールの在庫 Enabled プロパティが変更されます。 WS_BORDER の要求された設定と一致するコントロールの株価の罫線のスタイル プロパティが変更されます。 その他のすべてのスタイルは、1 つが存在する場合、コントロールのウィンドウのハンドルに直接適用されます。  
  
 コントロールのウィンドウ スタイルを変更します。 ビットごとの OR を使用してスタイルを追加または削除を組み合わせることができます ( &#124; ) 演算子。 参照してください、 [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa)使用可能なウィンドウのスタイルについては、Windows SDK 内の関数。  
  
 場合*nFlags* 0 以外の場合、 `ModifyStyle` Win32 関数を呼び出す`SetWindowPos`、し、結合することで、ウィンドウを再描画*nFlags*で次の 4 つのフラグ。  
  
- SWP_NOSIZE では、現在のサイズを保持します。  
  
- SWP_NOMOVE には、現在の位置が保持されます。  
  
- SWP_NOZORDER には、現在の Z オーダーが保持されます。  
  
- ウィンドウをアクティブに SWP_NOACTIVATE しません。  
  
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
 *dwRemove*  
 現在のウィンドウ スタイルから削除する拡張スタイル。  
  
 *dwAdd*  
 現在のウィンドウ スタイルを追加する拡張スタイル。  
  
 *nFlags*  
 ウィンドウの配置フラグ。 使用可能な値の一覧は、次を参照してください。、 [SetWindowPos](/windows/desktop/api/winuser/nf-winuser-setwindowpos) Windows SDK 内の関数。  
  
### <a name="return-value"></a>戻り値  
 スタイルが変更された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 WS_EX_CLIENTEDGE の設定と一致するコントロールのストック外観プロパティが変更されます。 1 つが存在する場合、他のすべての拡張ウィンドウ スタイルがコントロールのウィンドウのハンドルに直接適用されます。  
  
 ウィンドウの拡張コントロールのサイト オブジェクトのスタイルを変更します。 ビットごとの OR を使用してスタイルを追加または削除を組み合わせることができます ( &#124; ) 演算子。 参照してください、 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa)使用可能なウィンドウのスタイルについては、Windows SDK 内の関数。  
  
 場合*nFlags* 0 以外の場合、 `ModifyStyleEx` Win32 関数を呼び出す`SetWindowPos`、し、結合することで、ウィンドウを再描画*nFlags*で次の 4 つのフラグ。  
  
- SWP_NOSIZE では、現在のサイズを保持します。  
  
- SWP_NOMOVE には、現在の位置が保持されます。  
  
- SWP_NOZORDER には、現在の Z オーダーが保持されます。  
  
- ウィンドウをアクティブに SWP_NOACTIVATE しません。  
  
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
 ウィンドウの左側にあるの新しい位置。  
  
 *y*  
 ウィンドウの上部の新しい位置。  
  
 *nWidth*  
 新しいウィンドウの幅  
  
 *パラメーター nHeight*  
 ウィンドウの新しい高さ。  
  
##  <a name="quickactivate"></a>  COleControlSite::QuickActivate  
 クイックには、コンテナー内のコントロールがアクティブにします。  
  
```  
virtual BOOL QuickActivate();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、コントロールのサイトがアクティブ化された場合は 0。  
  
### <a name="remarks"></a>Remarks  
 ユーザーがコントロールの作成プロセスを上書きする場合にのみ、この関数を呼び出す必要があります。  
  
 `IPersist*::Load`と`IPersist*::InitNew`迅速なアクティブ化が行われた後、メソッドを呼び出す必要があります。 コントロールは、迅速なアクティブ化中に、コンテナーのシンクへの接続を確立する必要があります。 ただし、これらの接続は、ライブまで`IPersist*::Load`または`IPersist*::InitNew`が呼び出されました。  
  
##  <a name="safesetproperty"></a>  COleControlSite::SafeSetProperty  
 指定されたコントロール プロパティを設定*dwDispID*します。  
  
```  
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispID*  
 プロパティまたはコントロールのメソッドのディスパッチ ID を識別`IDispatch`インターフェイスを設定します。  
  
 *vtProp*  
 設定するプロパティの型を指定します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)します。  
  
 *...*  
 1 つのパラメーターで指定された型の*vtProp*します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  異なり`SetProperty`と`SetPropertyV`エラーが発生した場合 (存在しないプロパティを設定しようとしています) など、例外はスローされません。  
  
##  <a name="setdefaultbutton"></a>  COleControlSite::SetDefaultButton  
 既定のボタンとして設定します。  
  
```  
void SetDefaultButton(BOOL bDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 *bDefault*  
 以外の場合は、コントロールが既定のボタンになる必要があります。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  コントロールには、OLEMISC_ACTSLIKEBUTTON ステータス ビット セットが必要です。  
  
##  <a name="setdlgctrlid"></a>  COleControlSite::SetDlgCtrlID  
 コントロールのダイアログの項目の識別子の値を変更します。  
  
```  
virtual int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 新しい識別子の値。  
  
### <a name="return-value"></a>戻り値  
 前のダイアログ項目ウィンドウの識別子で成功した場合、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setfocus"></a>  COleControlSite::SetFocus  
 コントロールにフォーカスを設定します。  
  
```  
virtual CWnd* SetFocus();  
virtual CWnd* SetFocus(LPMSG lpmsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpmsg*  
 ポインターを[MSG 構造体](../../mfc/reference/msg-structure1.md)します。 この構造体を含む、Windows メッセージをトリガーする、`SetFocus`コントロールの現在のサイトに含まれるコントロールを要求します。  
  
### <a name="return-value"></a>戻り値  
 以前フォーカスがあったウィンドウへのポインター。  
  
##  <a name="setproperty"></a>  COleControlSite::SetProperty  
 指定されたコントロール プロパティを設定*dwDispID*します。  
  
```  
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispID*  
 プロパティまたはコントロールのメソッドのディスパッチ ID を識別`IDispatch`インターフェイスを設定します。  
  
 *vtProp*  
 設定するプロパティの型を指定します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)します。  
  
 *...*  
 1 つのパラメーターで指定された型の*vtProp*します。  
  
### <a name="remarks"></a>Remarks  
 場合`SetProperty`エラー検出すると、例外がスローされます。  
  
 例外の種類については、メソッドまたはプロパティを設定しようとするの戻り値によって決まります。 戻り値が場合`DISP_E_EXCEPTION`、`COleDispatchExcpetion`がスローされます。 それ以外の場合、 `COleException`。  
  
##  <a name="setpropertyv"></a>  COleControlSite::SetPropertyV  
 指定されたコントロール プロパティを設定*dwDispID*します。  
  
```  
virtual void SetPropertyV(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    va_list argList);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispID*  
 プロパティまたはコントロールのメソッドのディスパッチ ID を識別`IDispatch`インターフェイスを設定します。  
  
 *vtProp*  
 設定するプロパティの型を指定します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)します。  
  
 *argList*  
 引数リストへのポインター。  
  
### <a name="remarks"></a>Remarks  
 メソッドまたはプロパティが呼び出される追加のパラメーターは、補足を使用して、*補足*パラメーター。 場合`SetProperty`エラー検出すると、例外がスローされます。  
  
 例外の種類については、メソッドまたはプロパティを設定しようとするの戻り値によって決まります。 戻り値が場合`DISP_E_EXCEPTION`、`COleDispatchExcpetion`がスローされます。 それ以外の場合、 `COleException`。  
  
##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos  
 サイズ、位置、およびコントロールのサイトの Z オーダーを設定します。  
  
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
 *pWndInsertAfter*  
 ウィンドウへのポインター。  
  
 *x*  
 ウィンドウの左側にあるの新しい位置。  
  
 *y*  
 ウィンドウの上部の新しい位置。  
  
 *cx*  
 新しいウィンドウの幅  
  
 *cy*  
 ウィンドウの新しい高さ。  
  
 *nFlags*  
 ウィンドウのサイズ変更や配置フラグを指定します。 使用可能な値は、「解説」を参照してください。 [SetWindowPos](/windows/desktop/api/winuser/nf-winuser-setwindowpos) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、成功した場合は 0。  
  
##  <a name="setwindowtext"></a>  COleControlSite::SetWindowText  
 コントロール サイトのテキストを設定します。  
  
```  
virtual void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszString*  
 新しいタイトルまたはコントロールのテキストとして使用される null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>Remarks  
 この関数は、まずキャプションのストック プロパティを設定しようとします。 キャプションのストック プロパティがサポートされていない場合は、テキスト プロパティが代わりに設定されます。  
  
##  <a name="showwindow"></a>  COleControlSite::ShowWindow  
 ウィンドウの表示状態を設定します。  
  
```  
virtual BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>パラメーター  
 *nCmdShow*  
 コントロールのサイトの表示方法を指定します。 値は次のいずれかを指定する必要があります。  
  
- SW_HIDE では、このウィンドウを非表示にし、別のウィンドウをアクティブ化を渡します。  
  
- SW_MINIMIZE は、ウィンドウを最小化し、システムの一覧の最上位ウィンドウを表示します。  
  
- SW_RESTORE をアクティブにし、ウィンドウを表示します。 ウィンドウが最小化または最大化されている場合、Windows を元のサイズと位置に復元します。  
  
- SW_SHOW は、ウィンドウをアクティブにし、現在のサイズと位置に表示されます。  
  
- SW_SHOWMAXIMIZED は、ウィンドウをアクティブにし、最大化されたウィンドウとして表示されます。  
  
- このメンバーは、ウィンドウをアクティブにし、アイコンとして表示されます。  
  
- SW_SHOWMINNOACTIVE ウィンドウをアイコンとして表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- SW_SHOWNA では、現在の状態で、ウィンドウが表示されます。 現在アクティブなウィンドウは、アクティブなままです。  
  
- SW_SHOWNOACTIVATE では、最新のサイズと位置で、ウィンドウが表示されます。 現在アクティブなウィンドウは、アクティブなままです。  
  
- SW_SHOWNORMAL をアクティブにし、ウィンドウを表示します。 ウィンドウが最小化または最大化されている場合、Windows を元のサイズと位置に復元します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが表示されていた場合は 0 以外。ウィンドウが非表示であった場合は 0。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleControlContainer クラス](../../mfc/reference/colecontrolcontainer-class.md)
