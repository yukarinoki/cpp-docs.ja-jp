---
title: IOleObjectImpl クラス |Microsoft Docs
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
ms.openlocfilehash: aec4de071df8dcca960a0f1cb802375e5553ceb3
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880305"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl クラス
このクラスは実装`IUnknown`とは、コンテナーがコントロールでの通信に使用するプリンシパルのインターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IOleObjectImpl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IOleObjectImpl::Advise](#advise)|コントロールにアドバイザリ コネクションを確立します。|  
|[IOleObjectImpl::Close](#close)|アンロードを実行してから、コントロールの状態を変更します。|  
|[IOleObjectImpl::DoVerb](#doverb)|列挙されるアクションのいずれかを実行するコントロールに指示します。|  
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|保持されているすべての元に戻す状態を破棄するコントロールに指示します。|  
|[IOleObjectImpl::DoVerbHide](#doverbhide)|ビューからそのユーザー インターフェイスを削除するコントロールに指示します。|  
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|コントロールを実行し、そのウィンドウしますが、コントロールのユーザー インターフェイスではインストールされません。|  
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|別のウィンドウで開いて編集をするコントロールがされます。|  
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|ユーザー コントロールをダブルクリックすると、指定したアクションを実行します。 コントロールは、コントロール、インプレース アクティブ化するには、通常、アクションを定義します。|  
|[IOleObjectImpl::DoVerbShow](#doverbshow)|新しく挿入されたコントロールをユーザーに表示します。|  
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|インプレース コントロールをアクティブにし、メニューやツールバーなどのコントロールのユーザー インターフェイスを示しています。|  
|[IOleObjectImpl::EnumAdvise](#enumadvise)|コントロールのアドバイザリ コネクションを列挙します。|  
|[IOleObjectImpl::EnumVerbs](#enumverbs)|コントロールのアクションを列挙します。|  
|[IOleObjectImpl::GetClientSite](#getclientsite)|コントロールのクライアントのサイトを取得します。|  
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|クリップボードからデータを取得します。 ATL の実装では、E_NOTIMPL を返します。|  
|[IOleObjectImpl::GetExtent](#getextent)|コントロールの表示領域の範囲を取得します。|  
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|コントロールの状態を取得します。|  
|[IOleObjectImpl::GetMoniker](#getmoniker)|コントロールのモニカーを取得します。 ATL の実装では、E_NOTIMPL を返します。|  
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|コントロールのクラス識別子を取得します。|  
|[IOleObjectImpl::GetUserType](#getusertype)|コントロールのユーザーの種類の名前を取得します。|  
|[IOleObjectImpl::InitFromData](#initfromdata)|選択したデータからコントロールを初期化します。 ATL の実装では、E_NOTIMPL を返します。|  
|[IOleObjectImpl::IsUpToDate](#isuptodate)|コントロールの最新の状態を確認します。 ATL の実装では、S_OK を返します。|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|によって呼び出される[アンドゥ](#doverbdiscardundo)後、元に戻す状態は破棄されます。|  
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|によって呼び出される[DoVerbHide](#doverbhide)コントロールを非表示後します。|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|によって呼び出される[埋め込み](#doverbinplaceactivate)インプレース コントロールをアクティブにします。|  
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|によって呼び出される[DoVerbOpen](#doverbopen)コントロールを開いた後に別のウィンドウで、編集します。|  
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|によって呼び出される[DoVerbShow](#doverbshow)後、コントロールが表示されます。|  
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|によって呼び出される[DoVerbUIActivate](#doverbuiactivate)コントロールのユーザー インターフェイスを有効にしたら。|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|によって呼び出される[アンドゥ](#doverbdiscardundo)元に戻す前に、状態は破棄されます。|  
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|によって呼び出される[DoVerbHide](#doverbhide)コントロールが非表示にします。|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|によって呼び出される[埋め込み](#doverbinplaceactivate)インプレース コントロールがアクティブ化される前にします。|  
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|によって呼び出される[DoVerbOpen](#doverbopen)コントロールを別のウィンドウで、編集用に開く前にします。|  
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|によって呼び出される[DoVerbShow](#doverbshow)コントロールが表示される前にします。|  
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|によって呼び出される[DoVerbUIActivate](#doverbuiactivate)前に、コントロールのユーザー インターフェイスがアクティブ化されました。|  
|[IOleObjectImpl::SetClientSite](#setclientsite)|コンテナー内のクライアント サイトのコントロールに指示します。|  
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|存在する場合は、配色をコントロールのアプリケーションをお勧めします。 ATL の実装では、E_NOTIMPL を返します。|  
|[IOleObjectImpl::SetExtent](#setextent)|コントロールの表示領域の範囲を設定します。|  
|[IOleObjectImpl::SetHostNames](#sethostnames)|アプリケーションのコンテナーおよびコンテナー ドキュメントの名前をコントロールに指示します。|  
|[IOleObjectImpl::SetMoniker](#setmoniker)|そのモニカーは、コントロールに指示します。 ATL の実装では、E_NOTIMPL を返します。|  
|[IOleObjectImpl::Unadvise](#unadvise)|コントロールにアドバイザリ コネクションを削除します。|  
|[IOleObjectImpl::Update](#update)|コントロールを更新します。 ATL の実装では、S_OK を返します。|  
  
## <a name="remarks"></a>Remarks  
 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709)インターフェイスは、コンテナーがコントロールでの通信に使用するプリンシパルのインターフェイスです。 クラス`IOleObjectImpl`このインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlctl.h  
  
##  <a name="advise"></a>  IOleObjectImpl::Advise  
 コントロールにアドバイザリ コネクションを確立します。  
  
```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) Windows SDK にします。  
  
##  <a name="close"></a>  IOleObjectImpl::Close  
 アンロードを実行してから、コントロールの状態を変更します。  
  
```
STDMETHOD(Close)(DWORD dwSaveOption);
```  
  
### <a name="remarks"></a>Remarks  
 コントロールを非アクティブ化し、存在する場合は、コントロールのウィンドウを破棄します。 場合は、コントロールがデータ メンバーをクラス[CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) true と*dwSaveOption*パラメーターが OLECLOSE_SAVEIFDIRTY または OLECLOSE_PROMPTSAVE、コントロールのプロパティが閉じる前に保存されます。  
  
 コントロール クラスのデータ メンバーに、ポインターが保持されている[は](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite)と[アドバイズ](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)がリリースされたら、およびデータ メンバー [CComControlBase:。m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd)、 [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless)、および[CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex)が FALSE に設定します。  
  
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
  
### <a name="remarks"></a>Remarks  
 値に応じて`iVerb`、ATL の 1 つ`DoVerb`ヘルパー関数は次のように呼び出されます。  
  
|*iVerb*値|DoVerb ヘルパー関数が呼び出されます|  
|-------------------|-----------------------------------|  
|OLEIVERB_DISCARDUNDOSTATE|[アンドゥ](#doverbdiscardundo)|  
|OLEIVERB_HIDE|[DoVerbHide](#doverbhide)|  
|OLEIVERB_INPLACEACTIVATE|[埋め込み](#doverbinplaceactivate)|  
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|  
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|  
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|  
|で|[DoVerbShow](#doverbshow)|  
|OLEIVERB_UIACTIVATE|[DoVerbUIActivate](#doverbuiactivate)|  
  
 参照してください[IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK にします。  
  
##  <a name="doverbdiscardundo"></a>  IOleObjectImpl::DoVerbDiscardUndo  
 保持されているすべての元に戻す状態を破棄するコントロールに指示します。  
  
```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 *prcPosRec*  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="doverbhide"></a>  IOleObjectImpl::DoVerbHide  
 非アクティブ化しコントロールのユーザー インターフェイスを削除し、コントロールを非表示にします。  
  
```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 *prcPosRec*  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="doverbinplaceactivate"></a>  IOleObjectImpl::DoVerbInPlaceActivate  
 コントロールを実行し、そのウィンドウしますが、コントロールのユーザー インターフェイスではインストールされません。  
  
```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 *prcPosRec*  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 呼び出す場所でコントロールをアクティブに[CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate)します。 しない限り、コントロール クラスのデータ メンバー`m_bWindowOnly`が true の場合、`DoVerbInPlaceActivate`ウィンドウなしのコントロールとしてコントロールをアクティブ化をまず試みます (可能なコンテナーがサポートしている場合にのみ[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300))。 関数が拡張機能を持つコントロールをアクティブ化しようとした、失敗した場合は (コンテナーがサポートしている場合にのみ可能な限り[この](http://msdn.microsoft.com/library/windows/desktop/ms693461))。 関数が拡張機能がないコントロールをアクティブ化しようとした、失敗した場合は (コンテナーがサポートしている場合にのみ可能な限り[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586))。 アクティブ化に成功した場合、関数は、コントロールがアクティブ化されて、コンテナーを通知します。  
  
##  <a name="doverbopen"></a>  IOleObjectImpl::DoVerbOpen  
 別のウィンドウで開いて編集をするコントロールがされます。  
  
```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 *prcPosRec*  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="doverbprimary"></a>  IOleObjectImpl::DoVerbPrimary  
 ユーザー コントロールをダブルクリックしたときの動作を定義します。  
  
```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 *prcPosRec*  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 既定では、プロパティ ページを表示する設定します。 これがダブルクリックされたときに異なる動作を呼び出すコントロール クラスでオーバーライドすることができます。たとえば、ビデオを再生またはインプレース アクティブを参照してください。  
  
##  <a name="doverbshow"></a>  IOleObjectImpl::DoVerbShow  
 コントロールを表示するコンテナーに指示します。  
  
```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 *prcPosRec*  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
##  <a name="doverbuiactivate"></a>  IOleObjectImpl::DoVerbUIActivate  
 コントロールのユーザー インターフェイスをアクティブにし、コンテナーにコンポジット メニューにメニューが置き換えられることを通知します。  
  
```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 *prcPosRec*  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
##  <a name="enumadvise"></a>  IOleObjectImpl::EnumAdvise  
 このコントロールの登録済みのアドバイザリ コネクションの列挙体を提供します。  
  
```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::EnumAdvise](http://msdn.microsoft.com/library/windows/desktop/ms682355) Windows SDK にします。  
  
##  <a name="enumverbs"></a>  IOleObjectImpl::EnumVerbs  
 このコントロールの登録済みのアクション (動詞) の列挙子を呼び出すことによって提供`OleRegEnumVerbs`します。  
  
```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```  
  
### <a name="remarks"></a>Remarks  
 動詞は、プロジェクトの .rgs ファイルに追加できます。 たとえば、サンプルを参照してください。RGS の[円](../../visual-cpp-samples.md)サンプル。  
  
 参照してください[:enumverbs](http://msdn.microsoft.com/library/windows/desktop/ms692781) Windows SDK にします。  
  
##  <a name="getclientsite"></a>  IOleObjectImpl::GetClientSite  
 コントロール クラスのデータ メンバーにカーソルを置きます[CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite)に*ppClientSite*し、ポインター、参照カウントをインクリメントします。  
  
```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::GetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms692603) Windows SDK にします。  
  
##  <a name="getclipboarddata"></a>  IOleObjectImpl::GetClipboardData  
 クリップボードからデータを取得します。  
  
```
STDMETHOD(GetClipboardData)(    
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms682288) Windows SDK にします。  
  
##  <a name="getextent"></a>  IOleObjectImpl::GetExtent  
 HIMETRIC 単位 (0.01 ミリメートル単位) の実行中のコントロールの表示サイズを取得します。  
  
```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Remarks  
 コントロール クラスのデータ メンバーに、サイズが格納されている[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。  
  
 参照してください[IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) Windows SDK にします。  
  
##  <a name="getmiscstatus"></a>  IOleObjectImpl::GetMiscStatus  
 呼び出すことによって、コントロールの登録済みの状態情報へのポインターを返します`OleRegGetMiscStatus`します。  
  
```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Remarks  
 状態情報には、コントロールおよびプレゼンテーションのデータでサポートされている動作が含まれています。 プロジェクトの .rgs ファイルには、状態情報を追加できます。  
  
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
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::GetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms686576) Windows SDK にします。  
  
##  <a name="getuserclassid"></a>  IOleObjectImpl::GetUserClassID  
 コントロールのクラス識別子を返します。  
  
```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::GetUserClassID](http://msdn.microsoft.com/library/windows/desktop/ms682313) Windows SDK にします。  
  
##  <a name="getusertype"></a>  IOleObjectImpl::GetUserType  
 呼び出すことによって、コントロールのユーザーの種類の名前を返します`OleRegGetUserType`します。  
  
```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```  
  
### <a name="remarks"></a>Remarks  
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
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) Windows SDK にします。  
  
##  <a name="isuptodate"></a>  IOleObjectImpl::IsUpToDate  
 コントロールの最新の状態を確認します。  
  
```
STDMETHOD(IsUpToDate)(void);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[:isuptodate](http://msdn.microsoft.com/library/windows/desktop/ms686624) Windows SDK にします。  
  
##  <a name="onpostverbdiscardundo"></a>  IOleObjectImpl::OnPostVerbDiscardUndo  
 によって呼び出される[アンドゥ](#doverbdiscardundo)後、元に戻す状態は破棄されます。  
  
```
HRESULT OnPostVerbDiscardUndo();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 元に戻す状態が破棄された後に実行するコードでは、このメソッドをオーバーライドします。  
  
##  <a name="onpostverbhide"></a>  IOleObjectImpl::OnPostVerbHide  
 によって呼び出される[DoVerbHide](#doverbhide)コントロールを非表示後します。  
  
```
HRESULT OnPostVerbHide();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 コントロールが非表示にした後に実行するコードでは、このメソッドをオーバーライドします。  
  
##  <a name="onpostverbinplaceactivate"></a>  IOleObjectImpl::OnPostVerbInPlaceActivate  
 によって呼び出される[埋め込み](#doverbinplaceactivate)インプレース コントロールをアクティブにします。  
  
```
HRESULT OnPostVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 場所でコントロールがアクティブ化した後に実行するコードでは、このメソッドをオーバーライドします。  
  
##  <a name="onpostverbopen"></a>  IOleObjectImpl::OnPostVerbOpen  
 によって呼び出される[DoVerbOpen](#doverbopen)コントロールを開いた後に別のウィンドウで、編集します。  
  
```
HRESULT OnPostVerbOpen();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 別のウィンドウで編集するため、コントロールが開いた後に実行するコードでは、このメソッドをオーバーライドします。  
  
##  <a name="onpostverbshow"></a>  IOleObjectImpl::OnPostVerbShow  
 によって呼び出される[DoVerbShow](#doverbshow)後、コントロールが表示されます。  
  
```
HRESULT OnPostVerbShow();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 コントロールが表示される後に実行するコードでは、このメソッドをオーバーライドします。  
  
##  <a name="onpostverbuiactivate"></a>  IOleObjectImpl::OnPostVerbUIActivate  
 によって呼び出される[DoVerbUIActivate](#doverbuiactivate)コントロールのユーザー インターフェイスを有効にしたら。  
  
```
HRESULT OnPostVerbUIActivate();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 コントロールのユーザー インターフェイスが起動された後に実行するコードでは、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbdiscardundo"></a>  IOleObjectImpl::OnPreVerbDiscardUndo  
 によって呼び出される[アンドゥ](#doverbdiscardundo)元に戻す前に、状態は破棄されます。  
  
```
HRESULT OnPreVerbDiscardUndo();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 元に戻す状態が破棄されることを防ぐために、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbhide"></a>  IOleObjectImpl::OnPreVerbHide  
 によって呼び出される[DoVerbHide](#doverbhide)コントロールが非表示にします。  
  
```
HRESULT OnPreVerbHide();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 コントロールが非表示にされていることを防ぐためには、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbinplaceactivate"></a>  IOleObjectImpl::OnPreVerbInPlaceActivate  
 によって呼び出される[埋め込み](#doverbinplaceactivate)インプレース コントロールがアクティブ化される前にします。  
  
```
HRESULT OnPreVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 コントロールのインプレース アクティブ化を防ぐために、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbopen"></a>  IOleObjectImpl::OnPreVerbOpen  
 によって呼び出される[DoVerbOpen](#doverbopen)コントロールを別のウィンドウで、編集用に開く前にします。  
  
```
HRESULT OnPreVerbOpen();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 コントロールが別のウィンドウで編集するために開かれていることを防ぐためには、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbshow"></a>  IOleObjectImpl::OnPreVerbShow  
 によって呼び出される[DoVerbShow](#doverbshow)コントロールが表示される前にします。  
  
```
HRESULT OnPreVerbShow();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 コントロールが認識されることを防ぐためには、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="onpreverbuiactivate"></a>  IOleObjectImpl::OnPreVerbUIActivate  
 によって呼び出される[DoVerbUIActivate](#doverbuiactivate)前に、コントロールのユーザー インターフェイスがアクティブ化されました。  
  
```
HRESULT OnPreVerbUIActivate();
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 コントロールのユーザー インターフェイスがアクティブ化されていることを防ぐためには、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="setclientsite"></a>  IOleObjectImpl::SetClientSite  
 コンテナー内のクライアント サイトのコントロールに指示します。  
  
```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```  
  
### <a name="remarks"></a>Remarks  
 メソッドは、S_OK を返します。  
  
 参照してください[IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) Windows SDK にします。  
  
##  <a name="setcolorscheme"></a>  IOleObjectImpl::SetColorScheme  
 存在する場合は、配色をコントロールのアプリケーションをお勧めします。  
  
```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) Windows SDK にします。  
  
##  <a name="setextent"></a>  IOleObjectImpl::SetExtent  
 コントロールの表示領域の範囲を設定します。  
  
```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Remarks  
 それ以外の場合、`SetExtent`によって示される値を格納`psizel`コントロール クラスのデータ メンバー[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。 この値では、HIMETRIC 単位 (0.01 ミリメートル単位) です。  
  
 コントロールがデータ メンバーをクラスする場合[CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural)が true の場合、`SetExtent`も指す値を格納`psizel`コントロール クラスのデータ メンバー [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).  
  
 場合は、コントロールがデータ メンバーをクラス[CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize)が true の場合、`SetExtent`呼び出し`SendOnDataChange`と`SendOnViewChange`アドバイズ ホルダー コントロールのサイズに登録されているすべてのアドバイズ シンクに通知するには変更されました。  
  
 参照してください[IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) Windows SDK にします。  
  
##  <a name="sethostnames"></a>  IOleObjectImpl::SetHostNames  
 アプリケーションのコンテナーおよびコンテナー ドキュメントの名前をコントロールに指示します。  
  
```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) Windows SDK にします。  
  
##  <a name="setmoniker"></a>  IOleObjectImpl::SetMoniker  
 そのモニカーは、コントロールに指示します。  
  
```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::SetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679671) Windows SDK にします。  
  
##  <a name="unadvise"></a>  IOleObjectImpl::Unadvise  
 コントロールのクラスに格納されている、アドバイザリ コネクションを削除します。`m_spOleAdviseHolder`データ メンバー。  
  
```
STDMETHOD(Unadvise)(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) Windows SDK にします。  
  
##  <a name="update"></a>  IOleObjectImpl::Update  
 コントロールを更新します。  
  
```
STDMETHOD(Update)(void);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleObject::Update](http://msdn.microsoft.com/library/windows/desktop/ms679699) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [クラスの概要](../../atl/atl-class-overview.md)
