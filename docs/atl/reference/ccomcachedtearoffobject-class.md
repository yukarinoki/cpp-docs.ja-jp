---
title: クラスをキャッシュします。
ms.date: 11/04/2016
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
ms.openlocfilehash: 43f914a52666788fc0bf394d9d14830b28f5adc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321037"
---
# <a name="ccomcachedtearoffobject-class"></a>クラスをキャッシュします。

このクラスは、ティアオフ インターフェイスの[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装します。

## <a name="syntax"></a>構文

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>パラメーター

*含ま れる*<br/>
ティアオフ クラスの派生`CComTearOffObjectBase`クラスと、ティアオフ オブジェクトでサポートするインターフェイス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[オブジェクト::CComキャッシュティアオフオブジェクト](#ccomcachedtearoffobject)|コンストラクターです。|
|[オブジェクト::~CComキャッシュティアオフオブジェクト](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトをキャッシュします。](#addref)|オブジェクトの参照カウントを`CComCachedTearOffObject`インクリメントします。|
|[オブジェクト::ファイナルコンストラクト](#finalconstruct)|を呼`m_contained::FinalConstruct`び出します (ティアオフ クラスのメソッド)。|
|[オブジェクト::最終リリース](#finalrelease)|を呼`m_contained::FinalRelease`び出します (ティアオフ クラスのメソッド)。|
|[オブジェクト::クエリインターフェイス](#queryinterface)|オブジェクトの を`IUnknown`指すポインター、またはティアオフ クラス (クラス`contained`) の要求されたインターフェイスへのポインターを返します。 `CComCachedTearOffObject`|
|[オブジェクト::リリース](#release)|`CComCachedTearOffObject`オブジェクトの参照カウントを減算し、参照カウントが 0 の場合は破棄します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[オブジェクト::m_contained](#m_contained)|ティア`CComContainedObject`オフ クラス (クラス`contained`) から派生したオブジェクト。|

## <a name="remarks"></a>解説

`CComCachedTearOffObject`ティアオフ インターフェイスの[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装します。 `CComTearOffObject`このクラス`CComCachedTearOffObject`は、所有者オブジェクトとは別に`IUnknown`独自の`IUnknown`のクラス (所有者はティアオフを作成するオブジェクト) を持つクラスとは異なります。 `CComCachedTearOffObject`は、その参照カウントを保持`IUnknown`し、参照カウントがゼロになると、それ自体を削除します。 ただし、そのティアオフ インターフェイスのいずれかを照会すると、所有者オブジェクトの参照カウント`IUnknown`がインクリメントされます。

ティアオフ`CComCachedTearOffObject`を実装するオブジェクトが既にインスタンス化されている場合、ティアオフ インターフェイスが再び照会されると、同じ`CComCachedTearOffObject`オブジェクトが再利用されます。 これに対し、a によって実装されたティアオフ インターフェイス`CComTearOffObject`が、所有者オブジェクトを通じて再びクエリを`CComTearOffObject`実行した場合、別のインターフェイスがインスタンス化されます。

owner クラスは、`FinalRelease`その参照`Release`カウントを`IUnknown`減らすキャッシュされた`CComCachedTearOffObject`を実装して呼び出す必要があります。 これにより`CComCachedTearOffObject`、's`FinalRelease`が呼び出され、ティアオフが削除されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[ココムオブジェクトルート](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomcachedtearoffobjectaddref"></a><a name="addref"></a>オブジェクトをキャッシュします。

オブジェクトの参照カウントを`CComCachedTearOffObject`1 ずつインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断とテストに役立つ値。

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a>オブジェクト::CComキャッシュティアオフオブジェクト

コンストラクターです。

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
[in]の への`IUnknown`ポインター `CComCachedTearOffObject`。

### <a name="remarks"></a>解説

メンバを`CComContainedObject`初期化[m_containedします](#m_contained)。

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a>オブジェクト::~CComキャッシュティアオフオブジェクト

デストラクターです。

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し[、FinalRelease](#finalrelease)を呼び出します。

## <a name="ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a>オブジェクト::ファイナルコンストラクト

を`m_contained::FinalConstruct`作成`m_contained`する呼び`CComContainedObject`< `contained`出し、ティアオフ クラスによって実装されるインターフェイスにアクセスするために使用される> オブジェクト。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a>オブジェクト::最終リリース

free`m_contained::FinalRelease``m_contained`を呼び`CComContainedObject`< `contained`出して、>オブジェクトを呼び出します。

```
void FinalRelease();
```

## <a name="ccomcachedtearoffobjectm_contained"></a><a name="m_contained"></a>オブジェクト::m_contained

ティアオフ クラスから派生した[CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)オブジェクト。

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>パラメーター

*含ま れる*<br/>
[in]ティアオフ クラスの派生`CComTearOffObjectBase`クラスと、ティアオフ オブジェクトでサポートするインターフェイス。

### <a name="remarks"></a>解説

メソッド`m_contained`の継承は、キャッシュされたティアオフ オブジェクト 、 `QueryInterface`、、`FinalConstruct`および`FinalRelease`を通じて、ティアオフ クラスのティアオフ インターフェイスにアクセスするために使用されます。

## <a name="ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a>オブジェクト::クエリインターフェイス

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]要求されているインターフェイスの GUID。

*オブジェクト*<br/>
[アウト]*iid*で識別されるインターフェイス ポインタへのポインタ、 またはインターフェイスが見つからない場合は NULL。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

要求されたインターフェイスが`IUnknown`の場合は、自身`IUnknown`の`CComCachedTearOffObject`ポインタを返し、参照カウントをインクリメントします。 それ以外の場合は、から継承された[InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface)メソッドを使用して、ティアオフ`CComObjectRootEx`クラスのインターフェイスのクエリを実行します。

## <a name="ccomcachedtearoffobjectrelease"></a><a name="release"></a>オブジェクト::リリース

参照カウントを 1 減算し、参照カウントが 0 の場合はオブジェクトを`CComCachedTearOffObject`削除します。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

非デバッグ ビルドでは、常に 0 を返します。 デバッグ ビルドでは、診断やテストに役立つ値を返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomtearoffobject-class.md)<br/>
[クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
