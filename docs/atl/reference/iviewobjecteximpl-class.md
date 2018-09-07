---
title: IViewObjectExImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d47c017a178d0a222780532b74db4135447f062
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760449"
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl クラス

このクラスは実装`IUnknown`の既定の実装を提供し、 [IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject)、 [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2)、および[IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex)インターフェイス。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```

#### <a name="parameters"></a>パラメーター

*T*  
派生したクラス、`IViewObjectExImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IViewObjectExImpl::Draw](#draw)|デバイス コンテキストにコントロールの表現を描画します。|
|[IViewObjectExImpl::Freeze](#freeze)|コントロールの描画の表現がフリーズするまで変更できないように、`Unfreeze`します。 ATL の実装では、E_NOTIMPL を返します。|
|[IViewObjectExImpl::GetAdvise](#getadvise)|1 つを使用する必要がある場合は、コントロールで、既存のアドバイズ シンクの接続を取得します。|
|[IViewObjectExImpl::GetColorSet](#getcolorset)|コントロールによって描画に使用する論理パレットを返します。 ATL の実装では、E_NOTIMPL を返します。|
|[IViewObjectExImpl::GetExtent](#getextent)|コントロール クラスのデータ メンバーから、コントロールの表示サイズを HIMETRIC 単位 (0.01 ミリメートル単位) を取得します。[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。|
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|ユーザーがサイズを変更とを使用するオブジェクトのコンテナーからサイズ変更に関するヒントを提供します。|
|[IViewObjectExImpl::GetRect](#getrect)|要求された描画の外観を示す四角形を返します。 ATL の実装では、E_NOTIMPL を返します。|
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|オブジェクトとどのような描画の側面がサポートされているの不透明度についての情報を返します。|
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|チェックのかどうか、指定したポイントは指定した四角形では、し、返します、[中](/windows/desktop/api/ocidl/ne-ocidl-taghitresult)値`pHitResult`します。|
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|コントロールの表示の四角形が任意の時点で、指定した場所の四角形が重複しの中の値を返すかどうかを確認します。`pHitResult`します。|
|[IViewObjectExImpl::SetAdvise](#setadvise)|コントロールとアドバイズ シンク間の接続設定、シンクにコントロールのビューステートの変化について通知することができます。|
|[IViewObjectExImpl::Unfreeze](#unfreeze)|コントロールの描画の表示を解除します。 ATL の実装では、E_NOTIMPL を返します。|

## <a name="remarks"></a>Remarks

[IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject)、 [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2)、および[IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex)インターフェイス自体を直接表示および作成および管理に通知するアドバイズ シンクするコントロールを有効にしますコントロールの表示の変更のコンテナーです。 `IViewObjectEx`インターフェイスは、描画のちらつきのない、四角形以外と透過的なコントロール、ヒット テスト (たとえば、閉じる方法マウスをクリックする必要があります、コントロールと見なされる) などのコントロール拡張機能のサポートを提供します。 クラス`IViewObjectExImpl`これらのインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

## <a name="inheritance-hierarchy"></a>継承階層

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl.h

##  <a name="draw"></a>  IViewObjectExImpl::Draw

デバイス コンテキストにコントロールの表現を描画します。

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

### <a name="remarks"></a>Remarks

このメソッドを呼び出す`CComControl::OnDrawAdvanced`コントロール クラスのさらに呼び出す`OnDraw`メソッド。 `OnDraw`メソッドは、ATL コントロール ウィザードを使用して、コントロールを作成するときに、自動的に、コントロール クラスに追加します。 ウィザードの既定`OnDraw`ラベル"ATL 3.0"四角形を描画します。

参照してください[IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw) Windows SDK にします。

##  <a name="freeze"></a>  IViewObjectExImpl::Freeze

コントロールの描画の表現がフリーズするまで変更できないように、`Unfreeze`します。 ATL の実装では、E_NOTIMPL を返します。

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>Remarks

参照してください[IViewObject::Freeze](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-freeze) Windows SDK にします。

##  <a name="getadvise"></a>  IViewObjectExImpl::GetAdvise

1 つを使用する必要がある場合は、コントロールで、既存のアドバイズ シンクの接続を取得します。

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>Remarks

アドバイズ シンクがコントロールのクラスのデータ メンバーに格納されている[アドバイズ](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)します。

参照してください[IViewObject::GetAdvise](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-getadvise) Windows SDK にします。

##  <a name="getcolorset"></a>  IViewObjectExImpl::GetColorSet

コントロールによって描画に使用する論理パレットを返します。 ATL の実装では、E_NOTIMPL を返します。

```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```

### <a name="remarks"></a>Remarks

参照してください[IViewObject::GetColorSet](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-getcolorset) Windows SDK にします。

##  <a name="getextent"></a>  IViewObjectExImpl::GetExtent

コントロール クラスのデータ メンバーから、コントロールの表示サイズを HIMETRIC 単位 (0.01 ミリメートル単位) を取得します。[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>Remarks

参照してください[IViewObject2::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-iviewobject2-getextent) Windows SDK にします。

##  <a name="getnaturalextent"></a>  IViewObjectExImpl::GetNaturalExtent

ユーザーがサイズを変更とを使用するオブジェクトのコンテナーからサイズ変更に関するヒントを提供します。

```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```

### <a name="remarks"></a>Remarks

場合`dwAspect`は DVASPECT_CONTENT と*pExtentInfo dwExtentMode]-> [* DVEXTENT_CONTENT 設定は、*`psizel`コントロール クラスのデータ メンバーに[CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)します。 それ以外の場合、エラーの hresult 値を返します。

参照してください[IViewObjectEx::GetNaturalExtent](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) Windows SDK にします。

##  <a name="getrect"></a>  IViewObjectExImpl::GetRect

要求された描画の外観を示す四角形を返します。 ATL の実装では、E_NOTIMPL を返します。

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>Remarks

参照してください[IViewObjectEx::GetRect](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getrect) Windows SDK にします。

##  <a name="getviewstatus"></a>  IViewObjectExImpl::GetViewStatus

オブジェクトとどのような描画の側面がサポートされているの不透明度についての情報を返します。

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>Remarks

既定では、ATL の設定`pdwStatus`をコントロールが VIEWSTATUS_OPAQUE をサポートすることを示すために (使用できる値は、[な VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus)列挙型)。

参照してください[IViewObjectEx::GetViewStatus](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus) Windows SDK にします。

##  <a name="queryhitpoint"></a>  IViewObjectExImpl::QueryHitPoint

チェックのかどうか、指定したポイントは指定した四角形では、し、返します、[中](/windows/desktop/api/ocidl/ne-ocidl-taghitresult)値`pHitResult`します。

```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Remarks

値には、このまたは値のいずれかを指定できます。

場合`dwAspect`equals [DVASPECT_CONTENT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect)S_OK が返されます。 それ以外の場合、メソッドは、E_FAIL を返します。

参照してください[IViewObjectEx::QueryHitPoint](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint) Windows SDK にします。

##  <a name="queryhitrect"></a>  IViewObjectExImpl::QueryHitRect

コントロールの表示の四角形が任意の時点で、指定した場所の四角形が重複し、返すかどうかを確認します、[中](/windows/desktop/api/ocidl/ne-ocidl-taghitresult)値`pHitResult`します。

```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Remarks

値には、このまたは値のいずれかを指定できます。

場合`dwAspect`equals [DVASPECT_CONTENT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect)S_OK が返されます。 それ以外の場合、メソッドは、E_FAIL を返します。

参照してください[IViewObjectEx::QueryHitRect](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) Windows SDK にします。

##  <a name="setadvise"></a>  IViewObjectExImpl::SetAdvise

コントロールとアドバイズ シンク間の接続設定、シンクにコントロールのビューステートの変化について通知することができます。

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>Remarks

ポインター、 [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink)アドバイズ シンク上のインターフェイスがコントロールのクラスのデータ メンバーに格納されている[アドバイズ](ccomcontrolbase-class.md#m_spadvisesink)します。  

参照してください[IViewObject::SetAdvise](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-setadvise) Windows SDK にします。

##  <a name="unfreeze"></a>  IViewObjectExImpl::Unfreeze

コントロールの描画の表示を解除します。 ATL の実装では、E_NOTIMPL を返します。

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>Remarks

参照してください[IViewObject::Unfreeze](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-unfreeze) Windows SDK にします。

##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle

このオブジェクトに関連付けられたハンドルを終了するには、このメソッドを実装します。

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>パラメーター

*hHandle*  
終了するハンドル。

### <a name="return-value"></a>戻り値

成功した場合、またはエラー発生時のエラー HRESULT が S_OK を返します。

### <a name="remarks"></a>Remarks

このメソッドに渡されたハンドルが既に関連付けられているこのオブジェクトへの呼び出しによって[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。

### <a name="example"></a>例

次のコードの単純な実装を示しています。`IWorkerThreadClient::CloseHandle`します。

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

##  <a name="execute"></a>  IWorkerThreadClient::Execute

このオブジェクトに関連付けられたハンドルがシグナル状態コードを実行するには、このメソッドを実装します。

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>パラメーター

*について*  
ユーザー パラメーター。

*hObject*  
このハンドルがシグナル状態になります。

### <a name="return-value"></a>戻り値

成功した場合、またはエラー発生時のエラー HRESULT が S_OK を返します。

### <a name="remarks"></a>Remarks

このメソッドに渡された DWORD/ポインター、ハンドルがへの呼び出しでこのオブジェクトに既に関連付け[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。

### <a name="example"></a>例

次のコードの単純な実装を示しています。`IWorkerThreadClient::Execute`します。

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
[ActiveX コントロールのインターフェイス](/windows/desktop/com/activex-controls-interfaces)   
[チュートリアル](../../atl/active-template-library-atl-tutorial.md)   
[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
[クラスの概要](../../atl/atl-class-overview.md)
