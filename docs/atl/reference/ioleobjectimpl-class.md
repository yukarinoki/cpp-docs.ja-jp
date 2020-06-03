---
title: クラス
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
ms.openlocfilehash: 86d82aea2e92eb99903284abe4ac03478369616c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326523"
---
# <a name="ioleobjectimpl-class"></a>クラス

このクラスは、`IUnknown`コンテナーがコントロールと通信するプリンシパル インターフェイスを実装し、そのインターフェイスです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IOleObjectImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IOleObjectImpl::アドバイス](#advise)|コントロールとのアドバイザリ接続を確立します。|
|[オブジェクトのインプル::閉じる](#close)|コントロールの状態を実行から読み込み状態に変更します。|
|[オブジェクトのインプレッブ::DoVerb](#doverb)|列挙されたアクションのいずれかを実行するようにコントロールに指示します。|
|[オブジェクトのインプル::D動詞破棄元](#doverbdiscardundo)|コントロールが維持している元に戻す状態を破棄するようにコントロールに指示します。|
|[オブジェクトのインプル::DoVerbHide](#doverbhide)|コントロールに対して、ユーザー インターフェイスをビューから削除するように指示します。|
|[オブジェクトのインプル::D動詞のインプレースアクティブ](#doverbinplaceactivate)|コントロールを実行し、そのウィンドウをインストールしますが、コントロールのユーザー インターフェイスはインストールしません。|
|[オブジェクトのインプル::DoVerbを開く](#doverbopen)|コントロールを別のウィンドウで開いて編集します。|
|[オブジェクトのインプル::Do動詞プライマリ](#doverbprimary)|ユーザーがコントロールをダブルクリックしたときに、指定されたアクションを実行します。 コントロールは、通常、コントロールをインプレースでアクティブにするために、アクションを定義します。|
|[オブジェクトのインプル::Do動詞ショー](#doverbshow)|新しく挿入されたコントロールをユーザーに表示します。|
|[オブジェクトの種類::D動詞UI アクティブ化](#doverbuiactivate)|コントロールをインプレースでアクティブにし、メニューやツールバーなどのコントロールのユーザー インターフェイスを表示します。|
|[IOleObjectImpl::列挙アアドバイス](#enumadvise)|コントロールのアドバイザリ接続を列挙します。|
|[IOle オブジェクト インプル::列挙動詞](#enumverbs)|コントロールのアクションを列挙します。|
|[オブジェクトのインプル::クライアント サイトを取得します。](#getclientsite)|コントロールのクライアント サイトを取得します。|
|[オブジェクトのインプル::クリップボードデータを取得します。](#getclipboarddata)|クリップボードからデータを取得します。 ATL の実装はE_NOTIMPL返します。|
|[オブジェクトのインプル::取得範囲](#getextent)|コントロールの表示領域の範囲を取得します。|
|[オブジェクトのインプレルク::取得ミスタブ](#getmiscstatus)|コントロールの状態を取得します。|
|[IOleObjectImpl::ゲットモニカー](#getmoniker)|コントロールのモニカーを取得します。 ATL の実装はE_NOTIMPL返します。|
|[オブジェクトの割り込み::ユーザー クラス ID を取得します。](#getuserclassid)|コントロールのクラス識別子を取得します。|
|[オブジェクトの種類を取得します。](#getusertype)|コントロールのユーザー型名を取得します。|
|[オブジェクトインプル::イニトフロルデータ](#initfromdata)|選択したデータからコントロールを初期化します。 ATL の実装はE_NOTIMPL返します。|
|[IOleObjectImpl::イサプトーデート](#isuptodate)|コントロールが最新かどうかを確認します。 ATL 実装はS_OKを返します。|
|[オブジェクトのインプル::オンポストヴェルブ破棄元](#onpostverbdiscardundo)|元に戻す状態が破棄された後[に、DoVerbDiscardUndo](#doverbdiscardundo)によって呼び出されます。|
|[オブジェクトインプル::オンポストヴェルブハイド](#onpostverbhide)|コントロールが非表示にされた後に[DoVerbHide](#doverbhide)によって呼び出されます。|
|[オブジェクトインプル::オンポストヴェルブインプレイスアクティベート](#onpostverbinplaceactivate)|コントロール[が所定の位置で](#doverbinplaceactivate)アクティブ化された後に呼び出されます。|
|[オブジェクトのインプル::オンポストヴェルブオープン](#onpostverbopen)|コントロールが別のウィンドウで編集用に開かれた後に[、DoVerbOpen](#doverbopen)によって呼び出されます。|
|[オブジェクトのインプル::オンポストヴェルブショー](#onpostverbshow)|コントロールが表示された後に[DoVerbShow](#doverbshow)によって呼び出されます。|
|[オブジェクトのインプル::オンポスト動詞UIアクティブ化](#onpostverbuiactivate)|コントロールのユーザー インターフェイスがアクティブ化された後に[、DoVerbUIActivate](#doverbuiactivate)によって呼び出されます。|
|[オブジェクトのプル::オンプレブヴェルブ破棄元](#onpreverbdiscardundo)|元に戻す状態が破棄される前に[、DoVerbDiscardUndo](#doverbdiscardundo)によって呼び出されます。|
|[オブジェクトインプル::オンプレブブハイド](#onpreverbhide)|コントロールが非表示になる前に[、DoVerbHide](#doverbhide)によって呼び出されます。|
|[オブジェクトインプル::オンプレバーブインプレイスアクティベート](#onpreverbinplaceactivate)|コントロールが所定の位置でアクティブになる前に[、DoVerbInPlaceActivate](#doverbinplaceactivate)によって呼び出されます。|
|[オブジェクトインプル::オンプレブブオープン](#onpreverbopen)|コントロールが別のウィンドウで編集用に開かれる前に[、DoVerbOpen](#doverbopen)によって呼び出されます。|
|[オブジェクトインプル::オンプレブブショー](#onpreverbshow)|コントロールが表示される前に[、DoVerbShow](#doverbshow)によって呼び出されます。|
|[オブジェクトのインプル::オンプレブブUIアクティブ化](#onpreverbuiactivate)|コントロールのユーザー インターフェイスがアクティブ化される前に[、DoVerbUIActivate](#doverbuiactivate)によって呼び出されます。|
|[オブジェクトのインプル::クライアントサイトを設定します。](#setclientsite)|コンテナー内のクライアント サイトについてコントロールに通知します。|
|[オブジェクトインプル::セットカラースキーム](#setcolorscheme)|コントロールのアプリケーションに配色を推奨します (存在する場合)。 ATL の実装はE_NOTIMPL返します。|
|[オブジェクトのインプル::セットエクステント](#setextent)|コントロールの表示領域の範囲を設定します。|
|[オブジェクトのインプル::ホスト名を設定します。](#sethostnames)|コンテナー アプリケーションとコンテナー ドキュメントの名前をコントロールに通知します。|
|[IOle オブジェクト インプル::セットモニカー](#setmoniker)|モニカーが何であるかをコントロールに通知します。 ATL の実装はE_NOTIMPL返します。|
|[IOleObjectImpl::アアドバイスなし](#unadvise)|コントロールとのアドバイザリ接続を削除します。|
|[IOleObjectImpl::更新](#update)|コントロールを更新します。 ATL 実装はS_OKを返します。|

## <a name="remarks"></a>解説

[IOleObject](/windows/win32/api/oleidl/nn-oleidl-ioleobject)インターフェイスは、コンテナーがコントロールと通信するプリンシパル インターフェイスです。 Class`IOleObjectImpl`は、このインターフェイスの既定の実装を`IUnknown`提供し、デバッグ ビルドでダンプ デバイスに情報を送信することによって実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="ioleobjectimpladvise"></a><a name="advise"></a>IOleObjectImpl::アドバイス

コントロールとのアドバイザリ接続を確立します。

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>解説

詳細については、Windows SDK の[「IOleObject::アドバイス](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise)」を参照してください。

## <a name="ioleobjectimplclose"></a><a name="close"></a>オブジェクトのインプル::閉じる

コントロールの状態を実行から読み込み状態に変更します。

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>解説

コントロールを非アクティブにし、存在する場合はコントロール ウィンドウを破棄します。 コントロール クラス のデータ メンバー [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave)が TRUE で *、dwSaveOption*パラメーターがOLECLOSE_SAVEIFDIRTYまたはOLECLOSE_PROMPTSAVEの場合、コントロールのプロパティは閉じる前に保存されます。

コントロール クラス データ メンバー [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite)と[CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)に保持されているポインターが解放され、データ メンバー [CComControlBase::m_bNegotiatedWnd、CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd)、および[CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex)が FALSE に設定されます。 [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless)

「Windows SDK[で IOleObject::閉じる](/windows/win32/api/oleidl/nf-oleidl-ioleobject-close)」を参照してください。

## <a name="ioleobjectimpldoverb"></a><a name="doverb"></a>オブジェクトのインプレッブ::DoVerb

列挙されたアクションのいずれかを実行するようにコントロールに指示します。

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

`iVerb`の値に応じて、ATL`DoVerb`ヘルパー関数の 1 つが次のように呼び出されます。

|*i動詞*値|呼び出された DoVerb ヘルパー関数|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[元に戻す](#doverbdiscardundo)|
|OLEIVERB_HIDE|[ドリバーブハイド](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[ドブブインプレースアクティブ化](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[ドブブオープン](#doverbopen)|
|OLEIVERB_PRIMARY|[ドリバーブプライマリ](#doverbprimary)|
|OLEIVERB_PROPERTIES|[:Dプロパティ](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[ドブブショー](#doverbshow)|
|OLEIVERB_UIACTIVATE|[ドリバーブUIアクティブ化](#doverbuiactivate)|

Windows SDK[の「IOleObject::DoVerb」](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb)を参照してください。

## <a name="ioleobjectimpldoverbdiscardundo"></a><a name="doverbdiscardundo"></a>オブジェクトのインプル::D動詞破棄元

コントロールが維持している元に戻す状態を破棄するようにコントロールに指示します。

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*プルポスレック*<br/>
[in]コンテナーが描画する四角形へのポインター。

*hwndParent*<br/>
[in]コントロールを含むウィンドウのハンドル。

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="ioleobjectimpldoverbhide"></a><a name="doverbhide"></a>オブジェクトのインプル::DoVerbHide

コントロールのユーザー インターフェイスを非アクティブ化および削除し、コントロールを非表示にします。

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*プルポスレック*<br/>
[in]コンテナーが描画する四角形へのポインター。

*hwndParent*<br/>
[in]コントロールを含むウィンドウのハンドル。 ATL 実装では使用されません。

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="ioleobjectimpldoverbinplaceactivate"></a><a name="doverbinplaceactivate"></a>オブジェクトのインプル::D動詞のインプレースアクティブ

コントロールを実行し、そのウィンドウをインストールしますが、コントロールのユーザー インターフェイスはインストールしません。

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*プルポスレック*<br/>
[in]コンテナーが描画する四角形へのポインター。

*hwndParent*<br/>
[in]コントロールを含むウィンドウのハンドル。 ATL 実装では使用されません。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

コントロールをアクティブにするには[、CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate)を呼び出します。 コントロール クラスのデータ メンバー`m_bWindowOnly`が TRUE`DoVerbInPlaceActivate`でない限り、まずコントロールをウィンドウなしのコントロールとしてアクティブにしようとします (コンテナーが[IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)をサポートしている場合にのみ可能)。 それが失敗した場合、関数は拡張された機能を持つコントロールをアクティブにしようとします (コンテナーが[IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)をサポートしている場合にのみ可能)。 それが失敗した場合、関数は拡張された機能を持たないコントロールをアクティブにしようとします (コンテナが[IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)をサポートしている場合にのみ可能)。 アクティブ化が成功すると、コントロールがアクティブ化されたことをコンテナーに通知します。

## <a name="ioleobjectimpldoverbopen"></a><a name="doverbopen"></a>オブジェクトのインプル::DoVerbを開く

コントロールを別のウィンドウで開いて編集します。

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*プルポスレック*<br/>
[in]コンテナーが描画する四角形へのポインター。

*hwndParent*<br/>
[in]コントロールを含むウィンドウのハンドル。

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="ioleobjectimpldoverbprimary"></a><a name="doverbprimary"></a>オブジェクトのインプル::Do動詞プライマリ

ユーザーがコントロールをダブルクリックしたときに実行されるアクションを定義します。

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>パラメーター

*プルポスレック*<br/>
[in]コンテナーが描画する四角形へのポインター。

*hwndParent*<br/>
[in]コントロールを含むウィンドウのハンドル。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

既定では、プロパティ ページを表示するように設定します。 コントロール クラスでこれをオーバーライドして、ダブルクリック時に別の動作を呼び出すことができます。たとえば、ビデオを再生したり、インプレースアクティブにします。

## <a name="ioleobjectimpldoverbshow"></a><a name="doverbshow"></a>オブジェクトのインプル::Do動詞ショー

コントロールを表示できるようにコンテナーに指示します。

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*プルポスレック*<br/>
[in]コンテナーが描画する四角形へのポインター。

*hwndParent*<br/>
[in]コントロールを含むウィンドウのハンドル。 ATL 実装では使用されません。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ioleobjectimpldoverbuiactivate"></a><a name="doverbuiactivate"></a>オブジェクトの種類::D動詞UI アクティブ化

コントロールのユーザー インターフェイスをアクティブにし、そのメニューが複合メニューに置き換えられることをコンテナーに通知します。

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>パラメーター

*プルポスレック*<br/>
[in]コンテナーが描画する四角形へのポインター。

*hwndParent*<br/>
[in]コントロールを含むウィンドウのハンドル。 ATL 実装では使用されません。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ioleobjectimplenumadvise"></a><a name="enumadvise"></a>IOleObjectImpl::列挙アアドバイス

このコントロールに登録されているアドバイザリ接続の列挙体を提供します。

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>解説

Windows SDK[の「IOleObject::列挙アダアドバイス](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumadvise)」を参照してください。

## <a name="ioleobjectimplenumverbs"></a><a name="enumverbs"></a>IOle オブジェクト インプル::列挙動詞

を呼び出`OleRegEnumVerbs`すことによって、このコントロールに登録されているアクション (動詞) の列挙体を提供します。

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>解説

プロジェクトの .rgs ファイルに動詞を追加できます。 たとえば、CIRCCTL を参照してください。[CIRC](../../overview/visual-cpp-samples.md)サンプルの RGS。

Windows SDK[の「IOleObject::列挙動詞」](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs)を参照してください。

## <a name="ioleobjectimplgetclientsite"></a><a name="getclientsite"></a>オブジェクトのインプル::クライアント サイトを取得します。

コントロール クラス のデータ メンバー [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite)に*ポインターを置*き、ポインターの参照カウントをインクリメントします。

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>解説

Windows SDK[の「IOleObject::クライアントサイトを取得](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclientsite)する」を参照してください。

## <a name="ioleobjectimplgetclipboarddata"></a><a name="getclipboarddata"></a>オブジェクトのインプル::クリップボードデータを取得します。

クリップボードからデータを取得します。

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

「Windows SDK[の IOleObject::クリップボードデータを取得](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclipboarddata)する」を参照してください。

## <a name="ioleobjectimplgetextent"></a><a name="getextent"></a>オブジェクトのインプル::取得範囲

HIMETRIC 単位 (単位あたり 0.01 ミリメートル) 単位で実行中のコントロールの表示サイズを取得します。

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>解説

サイズはコントロール クラス のデータ メンバー [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)に格納されます。

「Windows SDK[の IOleObject::取得範囲](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getextent)」を参照してください。

## <a name="ioleobjectimplgetmiscstatus"></a><a name="getmiscstatus"></a>オブジェクトのインプレルク::取得ミスタブ

を呼び出`OleRegGetMiscStatus`すことによって、コントロールの登録済み状態情報へのポインターを返します。

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>解説

ステータス情報には、コントロールおよびプレゼンテーション データでサポートされている動作が含まれます。 プロジェクトの .rgs ファイルに状態情報を追加できます。

Windows SDK[の「IOleObject::GetMiscStatus」](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus)を参照してください。

## <a name="ioleobjectimplgetmoniker"></a><a name="getmoniker"></a>IOleObjectImpl::ゲットモニカー

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

Windows SDK[の「IOleObject::GetMoniker」](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmoniker)を参照してください。

## <a name="ioleobjectimplgetuserclassid"></a><a name="getuserclassid"></a>オブジェクトの割り込み::ユーザー クラス ID を取得します。

コントロールのクラス識別子を返します。

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>解説

Windows SDK[の「IOleObject::GetUser クラス ID」](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getuserclassid)を参照してください。

## <a name="ioleobjectimplgetusertype"></a><a name="getusertype"></a>オブジェクトの種類を取得します。

を呼び出して、コントロールのユーザー型名`OleRegGetUserType`を返します。

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>解説

ユーザータイプ名は、メニューやダイアログボックスなどのユーザーインタフェース要素での表示に使用されます。 プロジェクトの .rgs ファイルでユーザーの種類の名前を変更できます。

Windows SDK[の「IOleObject::GetUserType」](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getusertype)を参照してください。

## <a name="ioleobjectimplinitfromdata"></a><a name="initfromdata"></a>オブジェクトインプル::イニトフロルデータ

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

次[を参照してください](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata)。

## <a name="ioleobjectimplisuptodate"></a><a name="isuptodate"></a>IOleObjectImpl::イサプトーデート

コントロールが最新かどうかを確認します。

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

Windows SDK[の「IOleObject::IsUpToDate」](/windows/win32/api/oleidl/nf-oleidl-ioleobject-isuptodate)を参照してください。

## <a name="ioleobjectimplonpostverbdiscardundo"></a><a name="onpostverbdiscardundo"></a>オブジェクトのインプル::オンポストヴェルブ破棄元

元に戻す状態が破棄された後[に、DoVerbDiscardUndo](#doverbdiscardundo)によって呼び出されます。

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

元に戻す状態が破棄された後に実行するコードでこのメソッドをオーバーライドします。

## <a name="ioleobjectimplonpostverbhide"></a><a name="onpostverbhide"></a>オブジェクトインプル::オンポストヴェルブハイド

コントロールが非表示にされた後に[DoVerbHide](#doverbhide)によって呼び出されます。

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

このメソッドを、コントロールが非表示にした後に実行するコードでオーバーライドします。

## <a name="ioleobjectimplonpostverbinplaceactivate"></a><a name="onpostverbinplaceactivate"></a>オブジェクトインプル::オンポストヴェルブインプレイスアクティベート

コントロール[が所定の位置で](#doverbinplaceactivate)アクティブ化された後に呼び出されます。

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

コントロールが有効にされた後に実行するコードでこのメソッドをオーバーライドします。

## <a name="ioleobjectimplonpostverbopen"></a><a name="onpostverbopen"></a>オブジェクトのインプル::オンポストヴェルブオープン

コントロールが別のウィンドウで編集用に開かれた後に[、DoVerbOpen](#doverbopen)によって呼び出されます。

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

コントロールを別のウィンドウで編集するために開いた後に実行するコードでこのメソッドをオーバーライドします。

## <a name="ioleobjectimplonpostverbshow"></a><a name="onpostverbshow"></a>オブジェクトのインプル::オンポストヴェルブショー

コントロールが表示された後に[DoVerbShow](#doverbshow)によって呼び出されます。

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

コントロールが表示された後に実行するコードでこのメソッドをオーバーライドします。

## <a name="ioleobjectimplonpostverbuiactivate"></a><a name="onpostverbuiactivate"></a>オブジェクトのインプル::オンポスト動詞UIアクティブ化

コントロールのユーザー インターフェイスがアクティブ化された後に[、DoVerbUIActivate](#doverbuiactivate)によって呼び出されます。

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

コントロールのユーザー インターフェイスがアクティブ化された後に実行するコードでこのメソッドをオーバーライドします。

## <a name="ioleobjectimplonpreverbdiscardundo"></a><a name="onpreverbdiscardundo"></a>オブジェクトのプル::オンプレブヴェルブ破棄元

元に戻す状態が破棄される前に[、DoVerbDiscardUndo](#doverbdiscardundo)によって呼び出されます。

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

元に戻す状態が破棄されないようにするには、このメソッドをオーバーライドしてエラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbhide"></a><a name="onpreverbhide"></a>オブジェクトインプル::オンプレブブハイド

コントロールが非表示になる前に[、DoVerbHide](#doverbhide)によって呼び出されます。

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

コントロールが非表示にならないようにするには、このメソッドをオーバーライドしてエラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbinplaceactivate"></a><a name="onpreverbinplaceactivate"></a>オブジェクトインプル::オンプレバーブインプレイスアクティベート

コントロールが所定の位置でアクティブになる前に[、DoVerbInPlaceActivate](#doverbinplaceactivate)によって呼び出されます。

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

コントロールがアクティブ化されないようにするには、このメソッドをオーバーライドしてエラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbopen"></a><a name="onpreverbopen"></a>オブジェクトインプル::オンプレブブオープン

コントロールが別のウィンドウで編集用に開かれる前に[、DoVerbOpen](#doverbopen)によって呼び出されます。

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

コントロールを別のウィンドウで編集するために開かれないようにするには、このメソッドをオーバーライドしてエラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbshow"></a><a name="onpreverbshow"></a>オブジェクトインプル::オンプレブブショー

コントロールが表示される前に[、DoVerbShow](#doverbshow)によって呼び出されます。

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

コントロールが表示されないようにするには、このメソッドをオーバーライドしてエラー HRESULT を返します。

## <a name="ioleobjectimplonpreverbuiactivate"></a><a name="onpreverbuiactivate"></a>オブジェクトのインプル::オンプレブブUIアクティブ化

コントロールのユーザー インターフェイスがアクティブ化される前に[、DoVerbUIActivate](#doverbuiactivate)によって呼び出されます。

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

コントロールのユーザー インターフェイスがアクティブ化されないようにするには、このメソッドをオーバーライドしてエラー HRESULT を返します。

## <a name="ioleobjectimplsetclientsite"></a><a name="setclientsite"></a>オブジェクトのインプル::クライアントサイトを設定します。

コンテナー内のクライアント サイトについてコントロールに通知します。

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>解説

次に、メソッドはS_OKを返します。

Windows SDK[の「IOleObject::クライアントサイトの設定](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setclientsite)」を参照してください。

## <a name="ioleobjectimplsetcolorscheme"></a><a name="setcolorscheme"></a>オブジェクトインプル::セットカラースキーム

コントロールのアプリケーションに配色を推奨します (存在する場合)。

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK[の「IOleObject::セットカラースキーム](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme)」を参照してください。

## <a name="ioleobjectimplsetextent"></a><a name="setextent"></a>オブジェクトのインプル::セットエクステント

コントロールの表示領域の範囲を設定します。

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>解説

それ以外`SetExtent`の場合は、コントロール`psizel`クラスのデータ メンバー [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)に指す値を格納します。 この値は HIMETRIC 単位 (単位当たり 0.01 ミリメートル) です。

コントロール クラス データ メンバー [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) `SetExtent`が TRUE の場合は`psizel`、コントロール クラス のデータ メンバー [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)に指定された値も格納されます。

コントロール クラス のデータ メンバー [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize)が TRUE の場合は、`SetExtent`コントロールのサイズが変更されたことを通知するホルダーに登録されているすべてのアドバイザリ シンクを呼び出`SendOnDataChange`し`SendOnViewChange`、通知します。

「Windows SDK[の IOleObject::セットエクステント](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setextent)」を参照してください。

## <a name="ioleobjectimplsethostnames"></a><a name="sethostnames"></a>オブジェクトのインプル::ホスト名を設定します。

コンテナー アプリケーションとコンテナー ドキュメントの名前をコントロールに通知します。

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

Windows SDK[の「IOle オブジェクト::ホスト名の設定](/windows/win32/api/oleidl/nf-oleidl-ioleobject-sethostnames)」を参照してください。

## <a name="ioleobjectimplsetmoniker"></a><a name="setmoniker"></a>IOle オブジェクト インプル::セットモニカー

モニカーが何であるかをコントロールに通知します。

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK[の「IOleObject::セットモニカー](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setmoniker) 」を参照してください。

## <a name="ioleobjectimplunadvise"></a><a name="unadvise"></a>IOleObjectImpl::アアドバイスなし

コントロール クラスの`m_spOleAdviseHolder`データ メンバーに格納されているアドバイザリコネクションを削除します。

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>解説

「Windows SDK[の IOleObject::アアドバイスなし](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise)」を参照してください。

## <a name="ioleobjectimplupdate"></a><a name="update"></a>IOleObjectImpl::更新

コントロールを更新します。

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

Windows SDK[の「IOleObject::更新」](/windows/win32/api/oleidl/nf-oleidl-ioleobject-update)を参照してください。

## <a name="see-also"></a>関連項目

[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX コントロール インターフェイス](/windows/win32/com/activex-controls-interfaces)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
