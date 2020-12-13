---
description: '詳細情報: Iviewの Teximpl クラス'
title: Iviewの Teximpl クラス
ms.date: 11/04/2016
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
ms.openlocfilehash: 16b6f4a94635410f777e5c34e794ca425d38c466
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139101"
---
# <a name="iviewobjecteximpl-class"></a>Iviewの Teximpl クラス

このクラス `IUnknown` はを実装し、 [Iviewobject](/windows/win32/api/oleidl/nn-oleidl-iviewobject)、 [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)、および [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) インターフェイスの既定の実装を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class ATL_NO_VTABLE IViewObjectExImpl
   : public IViewObjectEx
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IViewObjectExImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Iviewの Teximpl::D raw](#draw)|コントロールの表現をデバイスコンテキストに描画します。|
|[Iview: Teximpl:: Freeze](#freeze)|コントロールの描画された表現を固定して、が変更されないように `Unfreeze` します。 ATL 実装は E_NOTIMPL を返します。|
|[Iviewの Teximpl:: GetAdvise](#getadvise)|コントロール上の既存のアドバイザリシンク接続がある場合は、それを取得します。|
|[Iviewの Teximpl:: GetColorSet](#getcolorset)|コントロールが描画に使用する論理パレットを返します。 ATL 実装は E_NOTIMPL を返します。|
|[Iviewの Teximpl:: GetExtent](#getextent)|コントロールクラスのデータメンバー [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)から、コントロールの表示サイズを HIMETRIC 単位 (1 ユニットあたり0.01 ミリメートル) で取得します。|
|[IviewGetNaturalExtent Teximpl::](#getnaturalextent)|ユーザーがオブジェクトのサイズを変更するときに使用するオブジェクトのコンテナーからサイズ変更のヒントを提供します。|
|[Iviewの Teximpl:: GetRect](#getrect)|要求された描画の側面を記述する四角形を返します。 ATL 実装は E_NOTIMPL を返します。|
|[Iviewの Teximpl:: GetViewStatus](#getviewstatus)|オブジェクトの不透明度とサポートされている描画の側面に関する情報を返します。|
|[Iview: Teximpl:: Queryヒットポイント](#queryhitpoint)|指定した点が指定した四角形内にあるかどうかを確認し、で [ヒット結果](/windows/win32/api/ocidl/ne-ocidl-hitresult) の値を返し `pHitResult` ます。|
|[Iview: Teximpl:: Queryヒット Rect](#queryhitrect)|コントロールの表示領域が、指定された位置の四角形内の任意の点と重なっているかどうかをチェックし、でのヒット結果の値を返し `pHitResult` ます。|
|[Iviewの Teximpl:: SetAdvise](#setadvise)|コントロールとアドバイズシンク間の接続を設定して、コントロールのビューの変更についてシンクに通知できるようにします。|
|[Iviewの Teximpl:: 凍結解除](#unfreeze)|コントロールの描画された表現を Unfreezes します。 ATL 実装は E_NOTIMPL を返します。|

## <a name="remarks"></a>解説

[Iviewobject](/windows/win32/api/oleidl/nn-oleidl-iviewobject)、 [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)、および[IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex)インターフェイスを使用すると、コントロールを直接表示し、アドバイズシンクを作成および管理して、コントロールの表示で変更をコンテナーに通知することができます。 `IViewObjectEx`このインターフェイスでは、ちらつきなしの描画、四角形でない透明なコントロール、およびヒットテスト (コントロールでマウスクリックを閉じる方法など) の拡張コントロール機能がサポートされています。 クラス `IViewObjectExImpl` は、これらのインターフェイスの既定の実装を提供し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

## <a name="inheritance-hierarchy"></a>継承階層

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="iviewobjecteximpldraw"></a><a name="draw"></a> Iviewの Teximpl::D raw

コントロールの表現をデバイスコンテキストに描画します。

```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```

### <a name="remarks"></a>解説

このメソッドは、このメソッドを呼び出し `CComControl::OnDrawAdvanced` て、コントロールクラスのメソッドを呼び出します `OnDraw` 。 `OnDraw`ATL コントロールウィザードを使用してコントロールを作成すると、コントロールクラスにメソッドが自動的に追加されます。 ウィザードの既定では、 `OnDraw` "ATL 3.0" というラベルの四角形が描画されます。

Windows SDK の「 [Iviewobject::D raw](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw) 」を参照してください。

## <a name="iviewobjecteximplfreeze"></a><a name="freeze"></a> Iview: Teximpl:: Freeze

コントロールの描画された表現を固定して、が変更されないように `Unfreeze` します。 ATL 実装は E_NOTIMPL を返します。

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>解説

Windows SDK の「 [Iviewobject:: Freeze](/windows/win32/api/oleidl/nf-oleidl-iviewobject-freeze) 」を参照してください。

## <a name="iviewobjecteximplgetadvise"></a><a name="getadvise"></a> Iviewの Teximpl:: GetAdvise

コントロール上の既存のアドバイザリシンク接続がある場合は、それを取得します。

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>解説

アドバイザリシンクは、コントロールクラスのデータメンバー [CComControlBase:: m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)に格納されます。

Windows SDK の「 [Iviewobject:: GetAdvise](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getadvise) 」を参照してください。

## <a name="iviewobjecteximplgetcolorset"></a><a name="getcolorset"></a> Iviewの Teximpl:: GetColorSet

コントロールが描画に使用する論理パレットを返します。 ATL 実装は E_NOTIMPL を返します。

```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```

### <a name="remarks"></a>解説

Windows SDK の「 [Iviewobject:: GetColorSet](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getcolorset) 」を参照してください。

## <a name="iviewobjecteximplgetextent"></a><a name="getextent"></a> Iviewの Teximpl:: GetExtent

コントロールクラスのデータメンバー [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)から、コントロールの表示サイズを HIMETRIC 単位 (1 ユニットあたり0.01 ミリメートル) で取得します。

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IViewObject2:: GetExtent](/windows/win32/api/oleidl/nf-oleidl-iviewobject2-getextent) 」を参照してください。

## <a name="iviewobjecteximplgetnaturalextent"></a><a name="getnaturalextent"></a> IviewGetNaturalExtent Teximpl::

ユーザーがオブジェクトのサイズを変更するときに使用するオブジェクトのコンテナーからサイズ変更のヒントを提供します。

```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```

### <a name="remarks"></a>解説

`dwAspect`が DVASPECT_CONTENT で、 *pExtentInfo->dwExtentMode* が DVEXTENT_CONTENT の場合、は * `psizel` をコントロールクラスのデータメンバー [CComControlBase:: m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)に設定します。 それ以外の場合は、エラー HRESULT を返します。

Windows SDK の「 [IViewObjectEx:: GetNaturalExtent](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) 」を参照してください。

## <a name="iviewobjecteximplgetrect"></a><a name="getrect"></a> Iviewの Teximpl:: GetRect

要求された描画の側面を記述する四角形を返します。 ATL 実装は E_NOTIMPL を返します。

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IViewObjectEx:: GetRect](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getrect) 」を参照してください。

## <a name="iviewobjecteximplgetviewstatus"></a><a name="getviewstatus"></a> Iviewの Teximpl:: GetViewStatus

オブジェクトの不透明度とサポートされている描画の側面に関する情報を返します。

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>解説

既定では、ATL は、 `pdwStatus` コントロールが VIEWSTATUS_OPAQUE をサポートしていることを示すを設定します (可能な値は [viewstatus](/windows/win32/api/ocidl/ne-ocidl-viewstatus) 列挙体にあります)。

Windows SDK の「 [IViewObjectEx:: GetViewStatus](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus) 」を参照してください。

## <a name="iviewobjecteximplqueryhitpoint"></a><a name="queryhitpoint"></a> Iview: Teximpl:: Queryヒットポイント

指定した点が指定した四角形内にあるかどうかを確認し、で [ヒット結果](/windows/win32/api/ocidl/ne-ocidl-hitresult) の値を返し `pHitResult` ます。

```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>解説

値は HITRESULT_HIT または HITRESULT_OUTSIDE のいずれかになります。

が `dwAspect` [DVASPECT_CONTENT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)の場合、メソッドは S_OK を返します。 それ以外の場合、メソッドは E_FAIL を返します。

Windows SDK の「 [IViewObjectEx:: Queryヒットポイント](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint) 」を参照してください。

## <a name="iviewobjecteximplqueryhitrect"></a><a name="queryhitrect"></a> Iview: Teximpl:: Queryヒット Rect

コントロールの表示領域が、指定された位置の四角形内の任意の点と重なっているかどうかをチェックし、での [ヒット結果](/windows/win32/api/ocidl/ne-ocidl-hitresult) の値を返し `pHitResult` ます。

```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>解説

値は HITRESULT_HIT または HITRESULT_OUTSIDE のいずれかになります。

が `dwAspect` [DVASPECT_CONTENT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)の場合、メソッドは S_OK を返します。 それ以外の場合、メソッドは E_FAIL を返します。

Windows SDK の「 [IViewObjectEx:: Queryヒット長方形](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) 」を参照してください。

## <a name="iviewobjecteximplsetadvise"></a><a name="setadvise"></a> Iviewの Teximpl:: SetAdvise

コントロールとアドバイズシンク間の接続を設定して、コントロールのビューの変更についてシンクに通知できるようにします。

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>解説

アドバイズシンクの [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) インターフェイスへのポインターは、コントロールクラスのデータメンバー [CComControlBase:: m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink)に格納されます。

Windows SDK の「 [Iviewobject:: SetAdvise](/windows/win32/api/oleidl/nf-oleidl-iviewobject-setadvise) 」を参照してください。

## <a name="iviewobjecteximplunfreeze"></a><a name="unfreeze"></a> Iviewの Teximpl:: 凍結解除

コントロールの描画された表現を Unfreezes します。 ATL 実装は E_NOTIMPL を返します。

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>解説

Windows SDK の「 [Iviewobject:: 凍結解除](/windows/win32/api/oleidl/nf-oleidl-iviewobject-unfreeze) 」を参照してください。

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a> IWorkerThreadClient:: CloseHandle

このオブジェクトに関連付けられているハンドルを閉じるには、このメソッドを実装します。

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>パラメーター

*hHandle*<br/>
閉じるハンドル。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このメソッドに渡されたハンドルは、 [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)を呼び出すことによって、以前にこのオブジェクトに関連付けられていました。

### <a name="example"></a>例

次のコードは、の単純な実装を示して `IWorkerThreadClient::CloseHandle` います。

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a> IWorkerThreadClient:: Execute

このオブジェクトに関連付けられたハンドルがシグナル状態になったときにコードを実行するには、このメソッドを実装します。

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>パラメーター

*dwParam*<br/>
ユーザーパラメーター。

*hObject*<br/>
がシグナル状態になったハンドル。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このメソッドに渡されたハンドルと DWORD/ポインターは、 [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)を呼び出すことによって、以前にこのオブジェクトに関連付けられていました。

### <a name="example"></a>例

次のコードは、の単純な実装を示して `IWorkerThreadClient::Execute` います。

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX コントロールインターフェイス](/windows/win32/com/activex-controls-interfaces)<br/>
[チュートリアル](../../atl/active-template-library-atl-tutorial.md)<br/>
[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
