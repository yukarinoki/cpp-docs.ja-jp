---
description: '詳細情報: IOleObjectImpl クラス'
title: IOleObjectImpl クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
ms.openlocfilehash: a8e9fd7dc370ee3f0861ab152061e4a0b96465ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158180"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl クラス

このクラス `IUnknown` はを実装し、はコンテナーがコントロールと通信するときに使用するプリンシパルインターフェイスです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IOleObjectImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IOleObjectImpl:: Advise](#advise)|コントロールとのアドバイザリコネクションを確立します。|
|[IOleObjectImpl:: Close](#close)|コントロールの状態を "実行中" から "読み込み済み" に変更します。|
|[IOleObjectImpl::D oVerb](#doverb)|列挙されたアクションのいずれかを実行するようコントロールに指示します。|
|[IOleObjectImpl::D oVerbDiscardUndo](#doverbdiscardundo)|保持している取り消し状態を破棄するようにコントロールに指示します。|
|[IOleObjectImpl::D オーバー Bhide](#doverbhide)|コントロールに対して、そのユーザーインターフェイスをビューから削除するように指示します。|
|[IOleObjectImpl::D Overbinplace Activate](#doverbinplaceactivate)|コントロールを実行し、そのウィンドウをインストールします。ただし、コントロールのユーザーインターフェイスはインストールしません。|
|[IOleObjectImpl::D オーバーペン](#doverbopen)|コントロールを別のウィンドウで開いて編集します。|
|[IOleObjectImpl::D oVerbPrimary](#doverbprimary)|ユーザーがコントロールをダブルクリックしたときに、指定されたアクションを実行します。 コントロールは、通常、コントロールを適切にアクティブ化するために、アクションを定義します。|
|[IOleObjectImpl::D oVerbShow](#doverbshow)|新しく挿入されたコントロールをユーザーに表示します。|
|[IOleObjectImpl::D oVerbUIActivate](#doverbuiactivate)|コントロールをその場でアクティブにし、メニューやツールバーなどのコントロールのユーザーインターフェイスを表示します。|
|[IOleObjectImpl:: EnumAdvise](#enumadvise)|コントロールのアドバイザリコネクションを列挙します。|
|[IOleObjectImpl:: EnumVerbs](#enumverbs)|コントロールのアクションを列挙します。|
|[IOleObjectImpl:: GetClientSite](#getclientsite)|コントロールのクライアントサイトを取得します。|
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|クリップボードからデータを取得します。 ATL 実装は E_NOTIMPL を返します。|
|[IOleObjectImpl:: GetExtent](#getextent)|コントロールの表示領域の範囲を取得します。|
|[IOleObjectImpl:: Get誤 Cstatus](#getmiscstatus)|コントロールの状態を取得します。|
|[IOleObjectImpl:: GetMoniker](#getmoniker)|コントロールのモニカーを取得します。 ATL 実装は E_NOTIMPL を返します。|
|[IOleObjectImpl:: GetUserClassID](#getuserclassid)|コントロールのクラス id を取得します。|
|[IOleObjectImpl:: GetUserType](#getusertype)|コントロールのユーザー型名を取得します。|
|[IOleObjectImpl:: InitFromData](#initfromdata)|選択したデータからコントロールを初期化します。 ATL 実装は E_NOTIMPL を返します。|
|[IOleObjectImpl:: IsUpToDate](#isuptodate)|コントロールが最新かどうかを確認します。 ATL 実装は S_OK を返します。|
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|元に戻す状態が破棄された後に [DoVerbDiscardUndo](#doverbdiscardundo) によって呼び出されます。|
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|コントロールが非表示にされた後、 [DoVerbHide](#doverbhide) によって呼び出されます。|
|[IOleObjectImpl:: Onpostverbinplace Activate](#onpostverbinplaceactivate)|コントロールが所定の位置でアクティブ化された後に、 [DoVerbInPlaceActivate](#doverbinplaceactivate) によって呼び出されます。|
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|別のウィンドウで編集するためにコントロールが開かれた後に、 [DoVerbOpen](#doverbopen) によって呼び出されます。|
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|コントロールが参照可能になった後に [DoVerbShow](#doverbshow) によって呼び出されます。|
|[IOleObjectImpl:: OnPostVerbUIActivate](#onpostverbuiactivate)|コントロールのユーザーインターフェイスがアクティブになった後に、 [DoVerbUIActivate](#doverbuiactivate) によって呼び出されます。|
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|元に戻す状態が破棄される前に、 [DoVerbDiscardUndo](#doverbdiscardundo) によって呼び出されます。|
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|コントロールが非表示になる前に、 [DoVerbHide](#doverbhide) によって呼び出されます。|
|[IOleObjectImpl:: Onpreverbinplace Activate](#onpreverbinplaceactivate)|コントロールが所定の位置でアクティブ化される前に、 [DoVerbInPlaceActivate](#doverbinplaceactivate) によって呼び出されます。|
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|別のウィンドウで編集するためにコントロールが開かれる前に、 [DoVerbOpen](#doverbopen) によって呼び出されます。|
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|コントロールが表示される前に、 [DoVerbShow](#doverbshow) によって呼び出されます。|
|[IOleObjectImpl:: OnPreVerbUIActivate](#onpreverbuiactivate)|コントロールのユーザーインターフェイスがアクティブ化される前に、 [DoVerbUIActivate](#doverbuiactivate) によって呼び出されます。|
|[IOleObjectImpl:: SetClientSite](#setclientsite)|コンテナー内のクライアントサイトについてコントロールに指示します。|
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|コントロールのアプリケーションの配色を推奨します (存在する場合)。 ATL 実装は E_NOTIMPL を返します。|
|[IOleObjectImpl:: SetExtent](#setextent)|コントロールの表示領域の範囲を設定します。|
|[IOleObjectImpl:: SetHostNames](#sethostnames)|コンテナーアプリケーションとコンテナードキュメントの名前をコントロールに指示します。|
|[IOleObjectImpl:: SetMoniker](#setmoniker)|モニカーをコントロールに指示します。 ATL 実装は E_NOTIMPL を返します。|
|[IOleObjectImpl:: アドバイズ](#unadvise)|コントロールとのアドバイザリコネクションを削除します。|
|[IOleObjectImpl:: Update](#update)|コントロールを更新します。 ATL 実装は S_OK を返します。|

## <a name="remarks"></a>解説

[IOleObject](/windows/win32/api/oleidl/nn-oleidl-ioleobject)インターフェイスは、コンテナーがコントロールと通信するときに使用するプリンシパルインターフェイスです。 クラス `IOleObjectImpl` は、このインターフェイスの既定の実装を提供し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="ioleobjectimpladvise"></a><a name="advise"></a> IOleObjectImpl:: Advise

コントロールとのアドバイザリコネクションを確立します。

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: Advise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) 」を参照してください。

## <a name="ioleobjectimplclose"></a><a name="close"></a> IOleObjectImpl:: Close

コントロールの状態を "実行中" から "読み込み済み" に変更します。

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>解説

コントロールを非アクティブにし、コントロールウィンドウが存在する場合は破棄します。 コントロールクラスのデータメンバー [CComControlBase:: m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) が TRUE で、 *dwsaveoption* パラメーターが OLECLOSE_SAVEIFDIRTY または OLECLOSE_PROMPTSAVE の場合、閉じる前にコントロールのプロパティが保存されます。

コントロールクラスのデータメンバー [CComControlBase:: m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) と [CComControlBase:: m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) に保持されているポインターが解放され、データメンバー [CComControlBase:: m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd)、 [CComControlBase:: m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless)、および [CComControlBase:: m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) が FALSE に設定されます。

Windows SDK の「 [IOleObject:: Close](/windows/win32/api/oleidl/nf-oleidl-ioleobject-close) 」を参照してください。

## <a name="ioleobjectimpldoverb"></a><a name="doverb"></a> IOleObjectImpl::D oVerb

列挙されたアクションのいずれかを実行するようコントロールに指示します。

```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```

### <a name="remarks"></a>解説

の値に応じて `iVerb` 、ATL ヘルパー関数の1つが次のように `DoVerb` 呼び出されます。

|*Iverb* 数値|DoVerb ヘルパー関数が呼び出されました|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[DoVerbDiscardUndo](#doverbdiscardundo)|
|OLEIVERB_HIDE|[DoVerbHide](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[DoVerbInPlaceActivate](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::D oVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[DoVerbShow](#doverbshow)|
|OLEIVERB_UIACTIVATE|[DoVerbUIActivate](#doverbuiactivate)|

Windows SDK の「 [IOleObject::D oVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) 」を参照してください。

## <a name="ioleobjectimpldoverbdiscardundo"></a><a name="doverbdiscardundo"></a> IOleObjectImpl::D oVerbDiscardUndo

保持している取り消し状態を破棄するようにコントロールに指示します。

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*prcPosRec*<br/>
からコンテナーがコントロールを描画する四角形へのポインター。

*hwndParent*<br/>
からコントロールを格納しているウィンドウのハンドル。

### <a name="return-value"></a>戻り値

S_OK を返します。

## <a name="ioleobjectimpldoverbhide"></a><a name="doverbhide"></a> IOleObjectImpl::D オーバー Bhide

コントロールのユーザーインターフェイスを非アクティブ化して削除し、コントロールを非表示にします。

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*prcPosRec*<br/>
からコンテナーがコントロールを描画する四角形へのポインター。

*hwndParent*<br/>
からコントロールを格納しているウィンドウのハンドル。 ATL の実装では使用されません。

### <a name="return-value"></a>戻り値

S_OK を返します。

## <a name="ioleobjectimpldoverbinplaceactivate"></a><a name="doverbinplaceactivate"></a> IOleObjectImpl::D Overbinplace Activate

コントロールを実行し、そのウィンドウをインストールします。ただし、コントロールのユーザーインターフェイスはインストールしません。

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*prcPosRec*<br/>
からコンテナーがコントロールを描画する四角形へのポインター。

*hwndParent*<br/>
からコントロールを格納しているウィンドウのハンドル。 ATL の実装では使用されません。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

[CComControlBase:: Inplace activate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate)を呼び出して、その場でコントロールをアクティブにします。 コントロールクラスのデータメンバーが TRUE でない限り `m_bWindowOnly` 、は `DoVerbInPlaceActivate` まず、コントロールをウィンドウなしのコントロールとしてアクティブ化しようとします (コンテナーが [IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)をサポートしている場合に限ります)。 失敗した場合、関数は拡張された機能を使用してコントロールをアクティブ化しようとします (コンテナーが [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)をサポートしている場合に限ります)。 このエラーが発生した場合、関数は拡張機能を使用せずにコントロールをアクティブ化しようとします (コンテナーが [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)をサポートしている場合に限ります)。 アクティブ化が成功した場合、関数は、コントロールがアクティブ化されたことをコンテナーに通知します。

## <a name="ioleobjectimpldoverbopen"></a><a name="doverbopen"></a> IOleObjectImpl::D オーバーペン

コントロールを別のウィンドウで開いて編集します。

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*prcPosRec*<br/>
からコンテナーがコントロールを描画する四角形へのポインター。

*hwndParent*<br/>
からコントロールを格納しているウィンドウのハンドル。

### <a name="return-value"></a>戻り値

S_OK を返します。

## <a name="ioleobjectimpldoverbprimary"></a><a name="doverbprimary"></a> IOleObjectImpl::D oVerbPrimary

ユーザーがコントロールをダブルクリックしたときに実行されるアクションを定義します。

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>パラメーター

*prcPosRec*<br/>
からコンテナーがコントロールを描画する四角形へのポインター。

*hwndParent*<br/>
からコントロールを格納しているウィンドウのハンドル。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

既定では、プロパティページを表示するようにを設定します。 コントロールクラスでこれをオーバーライドして、ダブルクリック時に別の動作を呼び出すことができます。たとえば、ビデオを再生するか、アクティブな場所に移動します。

## <a name="ioleobjectimpldoverbshow"></a><a name="doverbshow"></a> IOleObjectImpl::D oVerbShow

コントロールを表示するようにコンテナーに指示します。

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*prcPosRec*<br/>
からコンテナーがコントロールを描画する四角形へのポインター。

*hwndParent*<br/>
からコントロールを格納しているウィンドウのハンドル。 ATL の実装では使用されません。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

## <a name="ioleobjectimpldoverbuiactivate"></a><a name="doverbuiactivate"></a> IOleObjectImpl::D oVerbUIActivate

コントロールのユーザーインターフェイスをアクティブにし、メニューが複合メニューに置き換えられていることをコンテナーに通知します。

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*prcPosRec*<br/>
からコンテナーがコントロールを描画する四角形へのポインター。

*hwndParent*<br/>
からコントロールを格納しているウィンドウのハンドル。 ATL の実装では使用されません。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

## <a name="ioleobjectimplenumadvise"></a><a name="enumadvise"></a> IOleObjectImpl:: EnumAdvise

このコントロールに対して登録されているアドバイザリコネクションの列挙体を提供します。

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: EnumAdvise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumadvise) 」を参照してください。

## <a name="ioleobjectimplenumverbs"></a><a name="enumverbs"></a> IOleObjectImpl:: EnumVerbs

を呼び出して、このコントロールに対して登録されているアクション (動詞) の列挙体を提供 `OleRegEnumVerbs` します。

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>解説

プロジェクトの .rgs ファイルに動詞を追加できます。 例については、「CIRCCTL」を参照してください。 [CIRC](../../overview/visual-cpp-samples.md) サンプルの RGS。

Windows SDK の「 [IOleObject:: EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs) 」を参照してください。

## <a name="ioleobjectimplgetclientsite"></a><a name="getclientsite"></a> IOleObjectImpl:: GetClientSite

コントロールクラスのデータメンバー [CComControlBase:: m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) 内のポインターを *ppclientsite* に配置し、ポインターの参照カウントをインクリメントします。

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: GetClientSite](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclientsite) 」を参照してください。

## <a name="ioleobjectimplgetclipboarddata"></a><a name="getclipboarddata"></a> IOleObjectImpl::GetClipboardData

クリップボードからデータを取得します。

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: GetClipboardData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) 」を参照してください。

## <a name="ioleobjectimplgetextent"></a><a name="getextent"></a> IOleObjectImpl:: GetExtent

実行中のコントロールの表示サイズを HIMETRIC 単位 (1 ユニットあたり0.01 ミリメートル) で取得します。

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>解説

このサイズは、コントロールクラスのデータメンバー [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)に格納されます。

Windows SDK の「 [IOleObject:: GetExtent](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getextent) 」を参照してください。

## <a name="ioleobjectimplgetmiscstatus"></a><a name="getmiscstatus"></a> IOleObjectImpl:: Get誤 Cstatus

を呼び出して、コントロールに登録されている状態情報へのポインターを返し `OleRegGetMiscStatus` ます。

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>解説

状態情報には、コントロールとプレゼンテーションデータでサポートされる動作が含まれます。 プロジェクトの .rgs ファイルにステータス情報を追加できます。

Windows SDK の「 [IOleObject:: Get誤 Cstatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) 」を参照してください。

## <a name="ioleobjectimplgetmoniker"></a><a name="getmoniker"></a> IOleObjectImpl:: GetMoniker

コントロールのモニカーを取得します。

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: GetMoniker](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmoniker) 」を参照してください。

## <a name="ioleobjectimplgetuserclassid"></a><a name="getuserclassid"></a> IOleObjectImpl:: GetUserClassID

コントロールのクラス識別子を返します。

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: GetUserClassID](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getuserclassid) 」を参照してください。

## <a name="ioleobjectimplgetusertype"></a><a name="getusertype"></a> IOleObjectImpl:: GetUserType

を呼び出して、コントロールのユーザー型名を返し `OleRegGetUserType` ます。

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>解説

ユーザータイプ名は、メニューやダイアログボックスなどのユーザーインターフェイス要素の表示に使用されます。 プロジェクトの .rgs ファイルでユーザーの種類の名前を変更できます。

Windows SDK の「 [IOleObject:: GetUserType](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getusertype) 」を参照してください。

## <a name="ioleobjectimplinitfromdata"></a><a name="initfromdata"></a> IOleObjectImpl:: InitFromData

選択したデータからコントロールを初期化します。

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: InitFromData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) 」を参照してください。

## <a name="ioleobjectimplisuptodate"></a><a name="isuptodate"></a> IOleObjectImpl:: IsUpToDate

コントロールが最新かどうかを確認します。

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: IsUpToDate 累計](/windows/win32/api/oleidl/nf-oleidl-ioleobject-isuptodate) 」を参照してください。

## <a name="ioleobjectimplonpostverbdiscardundo"></a><a name="onpostverbdiscardundo"></a> IOleObjectImpl::OnPostVerbDiscardUndo

元に戻す状態が破棄された後に [DoVerbDiscardUndo](#doverbdiscardundo) によって呼び出されます。

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

このメソッドを、元に戻す状態を破棄した後に実行するコードでオーバーライドします。

## <a name="ioleobjectimplonpostverbhide"></a><a name="onpostverbhide"></a> IOleObjectImpl::OnPostVerbHide

コントロールが非表示にされた後、 [DoVerbHide](#doverbhide) によって呼び出されます。

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

コントロールを非表示にした後に実行するコードを使用して、このメソッドをオーバーライドします。

## <a name="ioleobjectimplonpostverbinplaceactivate"></a><a name="onpostverbinplaceactivate"></a> IOleObjectImpl:: Onpostverbinplace Activate

コントロールが所定の位置でアクティブ化された後に、 [DoVerbInPlaceActivate](#doverbinplaceactivate) によって呼び出されます。

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

このメソッドを、コントロールが適切にアクティブ化された後に実行するコードでオーバーライドします。

## <a name="ioleobjectimplonpostverbopen"></a><a name="onpostverbopen"></a> IOleObjectImpl::OnPostVerbOpen

別のウィンドウで編集するためにコントロールが開かれた後に、 [DoVerbOpen](#doverbopen) によって呼び出されます。

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

別のウィンドウで編集するためにコントロールを開いた後に実行するコードで、このメソッドをオーバーライドします。

## <a name="ioleobjectimplonpostverbshow"></a><a name="onpostverbshow"></a> IOleObjectImpl::OnPostVerbShow

コントロールが参照可能になった後に [DoVerbShow](#doverbshow) によって呼び出されます。

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

このメソッドを、コントロールが表示された後に実行するコードでオーバーライドします。

## <a name="ioleobjectimplonpostverbuiactivate"></a><a name="onpostverbuiactivate"></a> IOleObjectImpl:: OnPostVerbUIActivate

コントロールのユーザーインターフェイスがアクティブになった後に、 [DoVerbUIActivate](#doverbuiactivate) によって呼び出されます。

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

このメソッドを、コントロールのユーザーインターフェイスがアクティブ化された後に実行するコードでオーバーライドします。

## <a name="ioleobjectimplonpreverbdiscardundo"></a><a name="onpreverbdiscardundo"></a> IOleObjectImpl::OnPreVerbDiscardUndo

元に戻す状態が破棄される前に、 [DoVerbDiscardUndo](#doverbdiscardundo) によって呼び出されます。

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

元に戻す状態が破棄されないようにするには、このメソッドをオーバーライドして、エラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbhide"></a><a name="onpreverbhide"></a> IOleObjectImpl::OnPreVerbHide

コントロールが非表示になる前に、 [DoVerbHide](#doverbhide) によって呼び出されます。

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

コントロールが非表示にならないようにするには、このメソッドをオーバーライドして、エラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbinplaceactivate"></a><a name="onpreverbinplaceactivate"></a> IOleObjectImpl:: Onpreverbinplace Activate

コントロールが所定の位置でアクティブ化される前に、 [DoVerbInPlaceActivate](#doverbinplaceactivate) によって呼び出されます。

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

コントロールが適切にアクティブ化されないようにするには、このメソッドをオーバーライドして、エラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbopen"></a><a name="onpreverbopen"></a> IOleObjectImpl::OnPreVerbOpen

別のウィンドウで編集するためにコントロールが開かれる前に、 [DoVerbOpen](#doverbopen) によって呼び出されます。

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

コントロールを別のウィンドウで編集するために開かないようにするには、このメソッドをオーバーライドして、エラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbshow"></a><a name="onpreverbshow"></a> IOleObjectImpl::OnPreVerbShow

コントロールが表示される前に、 [DoVerbShow](#doverbshow) によって呼び出されます。

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

コントロールが表示されないようにするには、このメソッドをオーバーライドして、エラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbuiactivate"></a><a name="onpreverbuiactivate"></a> IOleObjectImpl:: OnPreVerbUIActivate

コントロールのユーザーインターフェイスがアクティブ化される前に、 [DoVerbUIActivate](#doverbuiactivate) によって呼び出されます。

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

コントロールのユーザーインターフェイスがアクティブ化されないようにするには、このメソッドをオーバーライドして、エラー HRESULT を返します。

## <a name="ioleobjectimplsetclientsite"></a><a name="setclientsite"></a> IOleObjectImpl:: SetClientSite

コンテナー内のクライアントサイトについてコントロールに指示します。

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>解説

メソッドは S_OK を返します。

Windows SDK の「 [IOleObject:: SetClientSite](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setclientsite) 」を参照してください。

## <a name="ioleobjectimplsetcolorscheme"></a><a name="setcolorscheme"></a> IOleObjectImpl::SetColorScheme

コントロールのアプリケーションの配色を推奨します (存在する場合)。

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) 」を参照してください。

## <a name="ioleobjectimplsetextent"></a><a name="setextent"></a> IOleObjectImpl:: SetExtent

コントロールの表示領域の範囲を設定します。

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>解説

それ以外の場合は、に `SetExtent` よってポイントされた値が、 `psizel` コントロールクラスのデータメンバー [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)に格納されます。 この値は、HIMETRIC 単位 (1 ユニットあたり0.01 ミリメートル) です。

コントロールクラスのデータメンバー [CComControlBase:: m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) が TRUE の場合、は、が `SetExtent` 指す値を `psizel` コントロールクラスのデータメンバー [CComControlBase:: m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)に格納します。

コントロールクラスのデータメンバー [CComControlBase:: m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) が TRUE の場合、はを `SetExtent` 呼び出し、 `SendOnDataChange` `SendOnViewChange` アドバイズ所有者に登録されているすべてのアドバイズシンクにコントロールサイズが変更されたことを通知します。

Windows SDK の「 [IOleObject:: SetExtent](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setextent) 」を参照してください。

## <a name="ioleobjectimplsethostnames"></a><a name="sethostnames"></a> IOleObjectImpl:: SetHostNames

コンテナーアプリケーションとコンテナードキュメントの名前をコントロールに指示します。

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: SetHostNames](/windows/win32/api/oleidl/nf-oleidl-ioleobject-sethostnames) 」を参照してください。

## <a name="ioleobjectimplsetmoniker"></a><a name="setmoniker"></a> IOleObjectImpl:: SetMoniker

モニカーをコントロールに指示します。

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: SetMoniker](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setmoniker) 」を参照してください。

## <a name="ioleobjectimplunadvise"></a><a name="unadvise"></a> IOleObjectImpl:: アドバイズ

コントロールクラスのデータメンバーに格納されているアドバイザリコネクションを削除し `m_spOleAdviseHolder` ます。

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: アドバイズ](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) 」を参照してください。

## <a name="ioleobjectimplupdate"></a><a name="update"></a> IOleObjectImpl:: Update

コントロールを更新します。

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleObject:: Update](/windows/win32/api/oleidl/nf-oleidl-ioleobject-update) 」を参照してください。

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX コントロールインターフェイス](/windows/win32/com/activex-controls-interfaces)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
