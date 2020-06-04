---
title: クラスを表示します。
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
ms.openlocfilehash: 59c5657dcd892544f7e790b52325cb9ecba0dd56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326340"
---
# <a name="iviewobjecteximpl-class"></a>クラスを表示します。

このクラスは、`IUnknown`実装し、既定の実装を提供します、 IViewObject、IViewObject2、および[IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex)インターフェイス。 [IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject) [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)

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
から派生したクラス`IViewObjectExImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトエクスプル::Dロー](#draw)|コントロールの表現をデバイス コンテキストに描画します。|
|[IView オブジェクトエクスプル::フリーズ](#freeze)|描画されたコントロールの表現を固定し、 が表示されるまでは変化しません`Unfreeze`。 ATL の実装はE_NOTIMPL返します。|
|[オブジェクトエクスプル::GetAdvise](#getadvise)|コントロール上に既存のアドバイザリ シンク接続がある場合は、その接続を取得します。|
|[オブジェクトエクスプル::ゲットカラーセット](#getcolorset)|描画用のコントロールで使用される論理パレットを返します。 ATL の実装はE_NOTIMPL返します。|
|[オブジェクトエクスプル::ゲットエクステント](#getextent)|コントロール クラスのデータ メンバー [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)から、コントロールの表示サイズを HIMETRIC 単位 (単位あたり 0.01 ミリメートル) で取得します。|
|[オブジェクトエクスプル::ゲットナチュラルエクステント](#getnaturalextent)|ユーザーがサイズ変更を行う場合に使用するオブジェクトのサイズ変更ヒントをコンテナーから提供します。|
|[IView オブジェクトエクスプル::ゲットレック](#getrect)|要求された描画の側面を示す四角形を返します。 ATL の実装はE_NOTIMPL返します。|
|[オブジェクトを追加するオブジェクトのインプル::取得状態](#getviewstatus)|オブジェクトの不透明度、およびサポートされている描画の側面に関する情報を返します。|
|[IView オブジェクトエクスプル::クエリヒットポイント](#queryhitpoint)|指定した点が指定された四角形内にあるかどうかを確認し、 に`pHitResult`[HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult)値を返します。|
|[IView オブジェクトエクスプル::クエリヒットレクト](#queryhitrect)|コントロールの表示四角形が、指定した位置の四角形内の任意のポイントと重なっているかどうかを確認`pHitResult`し、HITRESULT 値を返します。|
|[オブジェクトエクスプル::セットアアドバイス](#setadvise)|コントロールとアアドバイス シンクの間の接続を設定し、コントロールのビューの変更をシンクに通知できるようにします。|
|[IView オブジェクトエクスプル::フリーズ解除](#unfreeze)|描画されたコントロールの表現をフリーズ解除します。 ATL の実装はE_NOTIMPL返します。|

## <a name="remarks"></a>解説

[IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject) [、IViewObject2、](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)および[IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex)インターフェイスを使用すると、コントロール自体を直接表示し、コントロール表示の変更をコンテナーに通知するアアドバイス シンクを作成および管理できます。 この`IViewObjectEx`インターフェイスは、ちらつきのない描画、四角形以外の透明なコントロール、ヒット テスト (たとえば、コントロール上でマウス クリックを考慮する必要がある程度) などの拡張コントロール機能をサポートします。 Class`IViewObjectExImpl`は、デバッグ ビルドでダンプ デバイス`IUnknown`に情報を送信することで、これらのインターフェイスと実装の既定の実装を提供します。

## <a name="inheritance-hierarchy"></a>継承階層

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="iviewobjecteximpldraw"></a><a name="draw"></a>オブジェクトエクスプル::Dロー

コントロールの表現をデバイス コンテキストに描画します。

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

このメソッドは`CComControl::OnDrawAdvanced`、コントロール クラスの`OnDraw`メソッドを呼び出す呼び出しを行います。 ATL コントロール ウィザードを使用してコントロールを作成すると、`OnDraw`メソッドがコントロール クラスに自動的に追加されます。 ウィザードの既定`OnDraw`では、ラベル "ATL 3.0" の四角形が描画されます。

Windows SDK[の「iView オブジェクト::Draw」](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw)を参照してください。

## <a name="iviewobjecteximplfreeze"></a><a name="freeze"></a>IView オブジェクトエクスプル::フリーズ

描画されたコントロールの表現を固定し、 が表示されるまでは変化しません`Unfreeze`。 ATL の実装はE_NOTIMPL返します。

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>解説

「ウィンドウ[SDK の IView オブジェクト::フリーズ](/windows/win32/api/oleidl/nf-oleidl-iviewobject-freeze)」を参照してください。

## <a name="iviewobjecteximplgetadvise"></a><a name="getadvise"></a>オブジェクトエクスプル::GetAdvise

コントロール上に既存のアドバイザリ シンク接続がある場合は、その接続を取得します。

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>解説

アドバイザリ シンクは、コントロール クラス のデータ メンバー [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)に格納されます。

Windows SDK[の「IView オブジェクト::GetAdvise」](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getadvise)を参照してください。

## <a name="iviewobjecteximplgetcolorset"></a><a name="getcolorset"></a>オブジェクトエクスプル::ゲットカラーセット

描画用のコントロールで使用される論理パレットを返します。 ATL の実装はE_NOTIMPL返します。

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

「ウィンドウズ SDK の[IView オブジェクト::GetColorSet」](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getcolorset)を参照してください。

## <a name="iviewobjecteximplgetextent"></a><a name="getextent"></a>オブジェクトエクスプル::ゲットエクステント

コントロール クラスのデータ メンバー [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)から、コントロールの表示サイズを HIMETRIC 単位 (単位あたり 0.01 ミリメートル) で取得します。

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>解説

Windows SDK[の「IView オブジェクト2::GetExtent」](/windows/win32/api/oleidl/nf-oleidl-iviewobject2-getextent)を参照してください。

## <a name="iviewobjecteximplgetnaturalextent"></a><a name="getnaturalextent"></a>オブジェクトエクスプル::ゲットナチュラルエクステント

ユーザーがサイズ変更を行う場合に使用するオブジェクトのサイズ変更ヒントをコンテナーから提供します。

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

DVASPECT_CONTENT`dwAspect`され *、>dwExtentMode*がDVEXTENT_CONTENTされている場合は、 *`psizel`をコントロール クラスのデータ メンバー [CComControlBase::m_sizeNatural に](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)設定します。 それ以外の場合は、エラー HRESULT を返します。

Windows SDK[の「IViewObjectEx::取得自然範囲](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent)」を参照してください。

## <a name="iviewobjecteximplgetrect"></a><a name="getrect"></a>IView オブジェクトエクスプル::ゲットレック

要求された描画の側面を示す四角形を返します。 ATL の実装はE_NOTIMPL返します。

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>解説

Windows SDK[の「IViewObjectEx::GetRect」](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getrect)を参照してください。

## <a name="iviewobjecteximplgetviewstatus"></a><a name="getviewstatus"></a>オブジェクトを追加するオブジェクトのインプル::取得状態

オブジェクトの不透明度、およびサポートされている描画の側面に関する情報を返します。

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>解説

既定では、ATL`pdwStatus`はコントロールがVIEWSTATUS_OPAQUEをサポートしていることを示すために設定します (可能な値は[VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus)列挙体にあります)。

Windows SDK[の「IView オブジェクトの種類::GetView ステータス」](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus)を参照してください。

## <a name="iviewobjecteximplqueryhitpoint"></a><a name="queryhitpoint"></a>IView オブジェクトエクスプル::クエリヒットポイント

指定した点が指定された四角形内にあるかどうかを確認し、 に`pHitResult`[HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult)値を返します。

```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>解説

値は、HITRESULT_HITまたはHITRESULT_OUTSIDEのいずれかです。

DVASPECT_CONTENT`dwAspect`[等しい場合](/windows/win32/api/wtypes/ne-wtypes-dvaspect)、メソッドはS_OKを返します。 それ以外の場合、メソッドはE_FAIL返します。

Windows SDK[の「IViewObjectEx::クエリヒットポイント](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint)」を参照してください。

## <a name="iviewobjecteximplqueryhitrect"></a><a name="queryhitrect"></a>IView オブジェクトエクスプル::クエリヒットレクト

コントロールの表示四角形が、指定した位置の四角形内の任意のポイントと重なっているかどうかを確認`pHitResult`し[、HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult)値を返します。

```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>解説

値は、HITRESULT_HITまたはHITRESULT_OUTSIDEのいずれかです。

DVASPECT_CONTENT`dwAspect`[等しい場合](/windows/win32/api/wtypes/ne-wtypes-dvaspect)、メソッドはS_OKを返します。 それ以外の場合、メソッドはE_FAIL返します。

Windows SDK[の「IViewObjectEx::クエリヒットレクト](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect)」を参照してください。

## <a name="iviewobjecteximplsetadvise"></a><a name="setadvise"></a>オブジェクトエクスプル::セットアアドバイス

コントロールとアアドバイス シンクの間の接続を設定し、コントロールのビューの変更をシンクに通知できるようにします。

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>解説

アアドバイス シンクの[IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink)インターフェイスへのポインターは、コントロール クラス のデータ メンバー [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink)に格納されます。

Windows SDK[の「IView オブジェクト::セットアアドバイス](/windows/win32/api/oleidl/nf-oleidl-iviewobject-setadvise)」を参照してください。

## <a name="iviewobjecteximplunfreeze"></a><a name="unfreeze"></a>IView オブジェクトエクスプル::フリーズ解除

描画されたコントロールの表現をフリーズ解除します。 ATL の実装はE_NOTIMPL返します。

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>解説

「Windows SDK[で IView オブジェクト::フリーズ解除](/windows/win32/api/oleidl/nf-oleidl-iviewobject-unfreeze)」を参照してください。

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a>を閉じる

このメソッドを実装して、このオブジェクトに関連付けられているハンドルを閉じます。

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>パラメーター

*hハンドル*<br/>
閉じるハンドル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドに渡されたハンドルは、以前は[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)への呼び出しによってこのオブジェクトに関連付けられていた。

### <a name="example"></a>例

次のコードは、 の簡単`IWorkerThreadClient::CloseHandle`な実装を示しています。

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a>を実行します。

このオブジェクトに関連付けられたハンドルがシグナル状態になったときにコードを実行するには、このメソッドを実装します。

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>パラメーター

*ドウパラム*<br/>
ユーザー パラメーター。

*hオブジェクト*<br/>
シグナル状態になったハンドル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドに渡されたハンドルと DWORD/ポインターは、以前は[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)への呼び出しによってこのオブジェクトに関連付けされていました。

### <a name="example"></a>例

次のコードは、 の簡単`IWorkerThreadClient::Execute`な実装を示しています。

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>関連項目

[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX コントロール インターフェイス](/windows/win32/com/activex-controls-interfaces)<br/>
[チュートリアル](../../atl/active-template-library-atl-tutorial.md)<br/>
[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
