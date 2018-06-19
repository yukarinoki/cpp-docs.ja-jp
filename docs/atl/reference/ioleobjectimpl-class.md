---
title: IOleObjectImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a98d3e0ad75d2eaa0325699369bfe4473182049
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366196"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl クラス
このクラスは実装**IUnknown**コンテナーがコントロールとの通信に使用するプリンシパルのインターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IOleObjectImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IOleObjectImpl::Advise](#advise)|コントロールとのアドバイザリ コネクションを設定します。|  
|[IOleObjectImpl::Close](#close)|読み込まれたを実行してから、コントロールの状態を変更します。|  
|[IOleObjectImpl::DoVerb](#doverb)|列挙されるアクションのいずれかを実行するコントロールに指示します。|  
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|コントロールは保守すべて元に戻す状態を破棄するように指示します。|  
|[IOleObjectImpl::DoVerbHide](#doverbhide)|ビューからそのユーザー インターフェイスを削除するコントロールに指示します。|  
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|コントロールを実行し、そのウィンドウをインストールしますがコントロールのユーザー インターフェイスではインストールされません。|  
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|別のウィンドウで開いて編集をするコントロールがされます。|  
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|ユーザーがコントロールをダブルクリックすると、指定されたアクションを実行します。 コントロールでは、インプレース コントロールをアクティブ化するには、通常、アクションを定義します。|  
|[IOleObjectImpl::DoVerbShow](#doverbshow)|新しく挿入されるコントロールをユーザーに表示します。|  
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|インプレース コントロールをアクティブにし、メニューやツールバーなどのコントロールのユーザー インターフェイスを表示します。|  
|[IOleObjectImpl::EnumAdvise](#enumadvise)|コントロールのアドバイザリ コネクションを列挙します。|  
|[IOleObjectImpl::EnumVerbs](#enumverbs)|コントロールのアクションを列挙します。|  
|[IOleObjectImpl::GetClientSite](#getclientsite)|コントロールのクライアントのサイトを取得します。|  
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|クリップボードからデータを取得します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IOleObjectImpl::GetExtent](#getextent)|コントロールの表示領域の範囲を取得します。|  
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|コントロールの状態を取得します。|  
|[IOleObjectImpl::GetMoniker](#getmoniker)|コントロールのモニカーを取得します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|コントロールのクラス識別子を取得します。|  
|[IOleObjectImpl::GetUserType](#getusertype)|コントロールのユーザーの種類の名前を取得します。|  
|[IOleObjectImpl::InitFromData](#initfromdata)|選択したデータからコントロールを初期化します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IOleObjectImpl::IsUpToDate](#isuptodate)|コントロールの最新の状態を確認します。 ATL の実装を返します`S_OK`です。|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|によって呼び出されます[アンドゥ](#doverbdiscardundo)後、元に戻す状態は破棄されます。|  
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|によって呼び出されます[DoVerbHide](#doverbhide)コントロールを非表示後します。|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|によって呼び出されます[埋め込み](#doverbinplaceactivate)コントロールは、インプレース アクティブ化した後です。|  
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|によって呼び出されます[DoVerbOpen](#doverbopen)コントロールを開いた後に別のウィンドウで編集するためです。|  
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|によって呼び出されます[DoVerbShow](#doverbshow)コントロールが行われて表示されます。|  
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|によって呼び出されます[DoVerbUIActivate](#doverbuiactivate)コントロールのユーザー インターフェイスが起動された後です。|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|によって呼び出されます[アンドゥ](#doverbdiscardundo)が元に戻す前に、状態は破棄されます。|  
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|によって呼び出されます[DoVerbHide](#doverbhide)コントロールが非表示にします。|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|によって呼び出されます[埋め込み](#doverbinplaceactivate)場所でコントロールがアクティブ化する前にします。|  
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|によって呼び出されます[DoVerbOpen](#doverbopen)コントロールを別のウィンドウで編集用に開く前にします。|  
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|によって呼び出されます[DoVerbShow](#doverbshow)コントロールが表示される前にします。|  
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|によって呼び出されます[DoVerbUIActivate](#doverbuiactivate)コントロールのユーザー インターフェイスがアクティブ化する前にします。|  
|[IOleObjectImpl::SetClientSite](#setclientsite)|コンテナー内のクライアント サイトのコントロールに指示します。|  
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|存在する場合は、画面の配色、コントロールのアプリケーションをお勧めします。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IOleObjectImpl::SetExtent](#setextent)|コントロールの表示領域の範囲を設定します。|  
|[IOleObjectImpl::SetHostNames](#sethostnames)|アプリケーションのコンテナーおよびコンテナー ドキュメントの名前をコントロールに指示します。|  
|[IOleObjectImpl::SetMoniker](#setmoniker)|そのモニカーをコントロールに指示します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IOleObjectImpl::Unadvise](#unadvise)|コントロールとのアドバイザリ コネクションを削除します。|  
|[IOleObjectImpl::Update](#update)|コントロールを更新します。 ATL の実装を返します`S_OK`です。|  
  
## <a name="remarks"></a>コメント  
 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709)インターフェイスは、コンテナーがコントロールとの通信に使用するプリンシパルのインターフェイスです。 クラス`IOleObjectImpl`このインターフェイスの既定の実装を提供し、実装**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="advise"></a>  IOleObjectImpl::Advise  
 コントロールとのアドバイザリ コネクションを設定します。  
  
```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) Windows SDK にします。  
  
##  <a name="close"></a>  IOleObjectImpl::Close  
 読み込まれたを実行してから、コントロールの状態を変更します。  
  
```
STDMETHOD(Close)(DWORD dwSaveOption);
```  
  
### <a name="remarks"></a>コメント  
 コントロールが非アクティブ化し、存在する場合は、コントロールのウィンドウを破棄します。 場合は、コントロールがデータ メンバーをクラス[CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave)は**TRUE**と`dwSaveOption`パラメーターは、いずれかの`OLECLOSE_SAVEIFDIRTY`または`OLECLOSE_PROMPTSAVE`コントロールのプロパティが保存されます閉じる前に。  
  
 コントロール クラスのデータ メンバーでは、ポインターを保持[は](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite)と[アドバイズ](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)リリースされると、およびデータ メンバー [CComControlBase:。m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd)、 [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless)、および[CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex)に設定されている**FALSE**です。  
  
 参照してください[IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) Windows SDK にします。  
  
##  <a name="doverb"></a>  IOleObjectImpl::DoVerb  
 列挙されるアクションのいずれかを実行するコントロールに指示します。  
  
```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```  
  
### <a name="remarks"></a>コメント  
 値に応じて`iVerb`、ATL のいずれかの`DoVerb`ヘルパー関数は、次のように呼び出されます。  
  
|*iVerb*値|呼び出される DoVerb ヘルパー関数|  
|-------------------|-----------------------------------|  
|**OLEIVERB_DISCARDUNDOSTATE**|[アンドゥ](#doverbdiscardundo)|  
|`OLEIVERB_HIDE`|[DoVerbHide](#doverbhide)|  
|**OLEIVERB_INPLACEACTIVATE**|[埋め込み](#doverbinplaceactivate)|  
|`OLEIVERB_OPEN`|[DoVerbOpen](#doverbopen)|  
|`OLEIVERB_PRIMARY`|[DoVerbPrimary](#doverbprimary)|  
|**OLEIVERB_PROPERTIES**|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|  
|`OLEIVERB_SHOW`|[DoVerbShow](#doverbshow)|  
|`OLEIVERB_UIACTIVATE`|[DoVerbUIActivate](#doverbuiactivate)|  
  
 参照してください[IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK にします。  
  
##  <a name="doverbdiscardundo"></a>  IOleObjectImpl::DoVerbDiscardUndo  
 コントロールは保守すべて元に戻す状態を破棄するように指示します。  
  
```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="doverbhide"></a>  IOleObjectImpl::DoVerbHide  
 非アクティブ化しコントロールのユーザー インターフェイスを削除し、コントロールを非表示にします。  
  
```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドルです。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="doverbinplaceactivate"></a>  IOleObjectImpl::DoVerbInPlaceActivate  
 コントロールを実行し、そのウィンドウをインストールしますがコントロールのユーザー インターフェイスではインストールされません。  
  
```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドルです。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 場所でコントロールをアクティブに呼び出して[CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate)です。 しない限り、コントロール クラスのデータ メンバー`m_bWindowOnly`は**TRUE**、`DoVerbInPlaceActivate`最初ウィンドウなしのコントロールとしてコントロールをアクティブ化を試みます (可能なコンテナーをサポートしている場合にのみ[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)). 関数が拡張機能を持つコントロールをアクティブ化しようとしたが失敗した場合 (可能なコンテナーをサポートしている場合にのみ[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461))。 関数がない拡張機能を持つコントロールをアクティブ化しようとしたが失敗した場合 (可能なコンテナーをサポートしている場合にのみ[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586))。 アクティブ化に成功した場合、関数は、コントロールがアクティブ化されて、コンテナーを通知します。  
  
##  <a name="doverbopen"></a>  IOleObjectImpl::DoVerbOpen  
 別のウィンドウで開いて編集をするコントロールがされます。  
  
```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="doverbprimary"></a>  IOleObjectImpl::DoVerbPrimary  
 ユーザー コントロールをダブルクリックしたときに実行されるアクションを定義します。  
  
```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 既定では、プロパティ ページを表示する設定します。 これがダブルクリックされたときに異なる動作を呼び出すコントロール クラスでオーバーライドすることができます。たとえば、ビデオの再生や、インプレース アクティブです。  
  
##  <a name="doverbshow"></a>  IOleObjectImpl::DoVerbShow  
 コンテナー コントロールを表示するように指示します。  
  
```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドルです。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
##  <a name="doverbuiactivate"></a>  IOleObjectImpl::DoVerbUIActivate  
 コントロールのユーザー インターフェイスをアクティブにし、コンテナーにコンポジット メニューにメニューが置き換えられることを通知します。  
  
```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドルです。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
##  <a name="enumadvise"></a>  IOleObjectImpl::EnumAdvise  
 このコントロールの登録済みのアドバイザリ コネクションの列挙子を提供します。  
  
```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::EnumAdvise](http://msdn.microsoft.com/library/windows/desktop/ms682355) Windows SDK にします。  
  
##  <a name="enumverbs"></a>  IOleObjectImpl::EnumVerbs  
 このコントロールの登録されたアクション (動詞) の列挙子を呼び出すことによって提供**OleRegEnumVerbs**です。  
  
```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```  
  
### <a name="remarks"></a>コメント  
 プロジェクトの .rgs ファイルには、動詞を追加できます。 たとえば、サンプルを参照してください。RGS、 [CIRC](../../visual-cpp-samples.md)サンプルです。  
  
 参照してください[IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781) Windows SDK にします。  
  
##  <a name="getclientsite"></a>  IOleObjectImpl::GetClientSite  
 コントロール クラスのデータ メンバーにカーソルを置きます[CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite)に*ppClientSite*し、ポインターの参照カウントをインクリメントします。  
  
```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::GetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms692603) Windows SDK にします。  
  
##  <a name="getclipboarddata"></a>  IOleObjectImpl::GetClipboardData  
 クリップボードからデータを取得します。  
  
```
STDMETHOD(GetClipboardData)(    
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms682288) Windows SDK にします。  
  
##  <a name="getextent"></a>  IOleObjectImpl::GetExtent  
 HIMETRIC 単位 (0.01 ミリメートル単位) で実行中のコントロールの表示サイズを取得します。  
  
```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>コメント  
 コントロール クラスのデータ メンバーに、サイズが格納されている[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)です。  
  
 参照してください[IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) Windows SDK にします。  
  
##  <a name="getmiscstatus"></a>  IOleObjectImpl::GetMiscStatus  
 呼び出して、コントロールの登録済みの状態に関する情報へのポインターを返します**OleRegGetMiscStatus**です。  
  
```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>コメント  
 状態情報には、コントロールとプレゼンテーション データでサポートされている動作が含まれています。 ステータス情報は、プロジェクトの .rgs ファイルに追加できます。  
  
 参照してください[IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) Windows SDK にします。  
  
##  <a name="getmoniker"></a>  IOleObjectImpl::GetMoniker  
 コントロールのモニカーを取得します。  
  
```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::GetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms686576) Windows SDK にします。  
  
##  <a name="getuserclassid"></a>  IOleObjectImpl::GetUserClassID  
 コントロールのクラス識別子を返します。  
  
```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::GetUserClassID](http://msdn.microsoft.com/library/windows/desktop/ms682313) Windows SDK にします。  
  
##  <a name="getusertype"></a>  IOleObjectImpl::GetUserType  
 呼び出して、コントロールのユーザー タイプ名を返します**OleRegGetUserType**です。  
  
```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```  
  
### <a name="remarks"></a>コメント  
 ユーザーの種類名は、メニューおよびダイアログ ボックスなどのユーザー インターフェイス要素での表示に使用されます。 プロジェクトの .rgs ファイル内のユーザー型名を変更することができます。  
  
 参照してください[IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) Windows SDK にします。  
  
##  <a name="initfromdata"></a>  IOleObjectImpl::InitFromData  
 選択したデータからコントロールを初期化します。  
  
```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) Windows SDK にします。  
  
##  <a name="isuptodate"></a>  IOleObjectImpl::IsUpToDate  
 コントロールの最新の状態を確認します。  
  
```
STDMETHOD(IsUpToDate)(void);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[:isuptodate](http://msdn.microsoft.com/library/windows/desktop/ms686624) Windows SDK にします。  
  
##  <a name="onpostverbdiscardundo"></a>  IOleObjectImpl::OnPostVerbDiscardUndo  
 によって呼び出されます[アンドゥ](#doverbdiscardundo)後、元に戻す状態は破棄されます。  
  
```
HRESULT OnPostVerbDiscardUndo();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 元に戻す状態を破棄した後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="onpostverbhide"></a>  IOleObjectImpl::OnPostVerbHide  
 によって呼び出されます[DoVerbHide](#doverbhide)コントロールを非表示後します。  
  
```
HRESULT OnPostVerbHide();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが非表示にした後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="onpostverbinplaceactivate"></a>  IOleObjectImpl::OnPostVerbInPlaceActivate  
 によって呼び出されます[埋め込み](#doverbinplaceactivate)コントロールは、インプレース アクティブ化した後です。  
  
```
HRESULT OnPostVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがインプレース アクティブ化した後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="onpostverbopen"></a>  IOleObjectImpl::OnPostVerbOpen  
 によって呼び出されます[DoVerbOpen](#doverbopen)コントロールを開いた後に別のウィンドウで編集するためです。  
  
```
HRESULT OnPostVerbOpen();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールを開いた後に別のウィンドウで編集するために実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="onpostverbshow"></a>  IOleObjectImpl::OnPostVerbShow  
 によって呼び出されます[DoVerbShow](#doverbshow)コントロールが行われて表示されます。  
  
```
HRESULT OnPostVerbShow();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが表示される後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="onpostverbuiactivate"></a>  IOleObjectImpl::OnPostVerbUIActivate  
 によって呼び出されます[DoVerbUIActivate](#doverbuiactivate)コントロールのユーザー インターフェイスが起動された後です。  
  
```
HRESULT OnPostVerbUIActivate();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールのユーザー インターフェイスがアクティブ化した後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="onpreverbdiscardundo"></a>  IOleObjectImpl::OnPreVerbDiscardUndo  
 によって呼び出されます[アンドゥ](#doverbdiscardundo)が元に戻す前に、状態は破棄されます。  
  
```
HRESULT OnPreVerbDiscardUndo();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 元に戻す状態が破棄されることを防ぐために、エラーの hresult 値を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbhide"></a>  IOleObjectImpl::OnPreVerbHide  
 によって呼び出されます[DoVerbHide](#doverbhide)コントロールが非表示にします。  
  
```
HRESULT OnPreVerbHide();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが非表示にされていることを防ぐために、エラーの hresult 値を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbinplaceactivate"></a>  IOleObjectImpl::OnPreVerbInPlaceActivate  
 によって呼び出されます[埋め込み](#doverbinplaceactivate)場所でコントロールがアクティブ化する前にします。  
  
```
HRESULT OnPreVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがインプレース アクティブ化されていることを防ぐために、エラーの hresult 値を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbopen"></a>  IOleObjectImpl::OnPreVerbOpen  
 によって呼び出されます[DoVerbOpen](#doverbopen)コントロールを別のウィンドウで編集用に開く前にします。  
  
```
HRESULT OnPreVerbOpen();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが別のウィンドウで編集するために開かれるようにするのには、エラーの hresult 値を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbshow"></a>  IOleObjectImpl::OnPreVerbShow  
 によって呼び出されます[DoVerbShow](#doverbshow)コントロールが表示される前にします。  
  
```
HRESULT OnPreVerbShow();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが認識されるようにするのには、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbuiactivate"></a>  IOleObjectImpl::OnPreVerbUIActivate  
 によって呼び出されます[DoVerbUIActivate](#doverbuiactivate)コントロールのユーザー インターフェイスがアクティブ化する前にします。  
  
```
HRESULT OnPreVerbUIActivate();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールのユーザー インターフェイスがアクティブ化されていることを防ぐために、エラーの hresult 値を返すには、このメソッドをオーバーライドします。  
  
##  <a name="setclientsite"></a>  IOleObjectImpl::SetClientSite  
 コンテナー内のクライアント サイトのコントロールに指示します。  
  
```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```  
  
### <a name="remarks"></a>コメント  
 メソッドが戻ります`S_OK`です。  
  
 参照してください[IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) Windows SDK にします。  
  
##  <a name="setcolorscheme"></a>  IOleObjectImpl::SetColorScheme  
 存在する場合は、画面の配色、コントロールのアプリケーションをお勧めします。  
  
```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) Windows SDK にします。  
  
##  <a name="setextent"></a>  IOleObjectImpl::SetExtent  
 コントロールの表示領域の範囲を設定します。  
  
```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>コメント  
 それ以外の場合、`SetExtent`によって示される値を格納`psizel`コントロール クラスのデータ メンバーに[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)です。 この値は、HIMETRIC 単位 (0.01 ミリメートル単位)。  
  
 場合は、コントロールがデータ メンバーをクラス[CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural)は**TRUE**、`SetExtent`によって示される値にも格納`psizel`コントロール クラスのデータ メンバー [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)です。  
  
 コントロールがデータ メンバーをクラスする場合[CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize)は**TRUE**、`SetExtent`呼び出し`SendOnDataChange`と`SendOnViewChange`に登録されているすべてのアドバイズ シンクに通知する、コントロールのサイズが変更されたことを所有者にアドバイスします。  
  
 参照してください[IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) Windows SDK にします。  
  
##  <a name="sethostnames"></a>  IOleObjectImpl::SetHostNames  
 アプリケーションのコンテナーおよびコンテナー ドキュメントの名前をコントロールに指示します。  
  
```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) Windows SDK にします。  
  
##  <a name="setmoniker"></a>  IOleObjectImpl::SetMoniker  
 そのモニカーをコントロールに指示します。  
  
```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::SetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679671) Windows SDK にします。  
  
##  <a name="unadvise"></a>  IOleObjectImpl::Unadvise  
 コントロールのクラスに格納されているアドバイザリ コネクションを削除`m_spOleAdviseHolder`データ メンバーです。  
  
```
STDMETHOD(Unadvise)(DWORD dwConnection);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) Windows SDK にします。  
  
##  <a name="update"></a>  IOleObjectImpl::Update  
 コントロールを更新します。  
  
```
STDMETHOD(Update)(void);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::Update](http://msdn.microsoft.com/library/windows/desktop/ms679699) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [クラスの概要](../../atl/atl-class-overview.md)
