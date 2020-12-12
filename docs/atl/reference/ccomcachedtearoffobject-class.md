---
description: '詳細情報: CComCachedTearOffObject クラス'
title: CComCachedTearOffObject クラス
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
ms.openlocfilehash: 321e92b6bdf59834cd6c74b417a1788beefbdcb8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146914"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject クラス

このクラスは、ティアオフインターフェイスの [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) を実装します。

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

*格納*<br/>
から派生したティアオフクラス、 `CComTearOffObjectBase` およびティアオフオブジェクトがサポートするインターフェイスです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|コンストラクターです。|
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComCachedTearOffObject:: AddRef](#addref)|オブジェクトの参照カウントをインクリメントし `CComCachedTearOffObject` ます。|
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|`m_contained::FinalConstruct`(ティアオフクラス ' method) を呼び出します。|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|`m_contained::FinalRelease`(ティアオフクラス ' method) を呼び出します。|
|[CComCachedTearOffObject:: QueryInterface](#queryinterface)|オブジェクトのへのポインター、 `IUnknown` `CComCachedTearOffObject` またはティアオフクラス (クラス) 上の要求されたインターフェイスへのポインターを返し `contained` ます。|
|[CComCachedTearOffObject:: Release](#release)|オブジェクトの参照カウントをデクリメント `CComCachedTearOffObject` し、参照カウントが0の場合はオブジェクトを破棄します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComCachedTearOffObject:: m_contained](#m_contained)|`CComContainedObject`ティアオフクラス (クラス) から派生したオブジェクト `contained` 。|

## <a name="remarks"></a>解説

`CComCachedTearOffObject` ティアオフインターフェイスに [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) を実装します。 このクラス `CComTearOffObject` `CComCachedTearOffObject` は、所有者オブジェクトのとは別の独自のを持つとは異なり `IUnknown` `IUnknown` ます (所有者は、ティアオフを作成する対象のオブジェクトです)。 `CComCachedTearOffObject` に対して独自の参照カウント `IUnknown` を保持し、参照カウントが0になるとそれ自体を削除します。 ただし、そのいずれかのティアオフインターフェイスに対してクエリを実行すると、所有者オブジェクトの参照カウント `IUnknown` がインクリメントされます。

ティアオフを実装している `CComCachedTearOffObject` オブジェクトが既にインスタンス化されている場合に、ティアオフインターフェイスに対してもう一度クエリを実行すると、同じ `CComCachedTearOffObject` オブジェクトが再利用されます。 これに対して、によって実装されたティアオフインターフェイス `CComTearOffObject` が owner オブジェクトを介して再びクエリされる場合、別の `CComTearOffObject` がインスタンス化されます。

Owner クラスはを実装 `FinalRelease` し、に対してキャッシュされたでを呼び出す必要があり `Release` `IUnknown` `CComCachedTearOffObject` ます。これにより、参照カウントが減少します。 これにより、が `CComCachedTearOffObject` `FinalRelease` 呼び出され、ティアオフが削除されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomcachedtearoffobjectaddref"></a><a name="addref"></a> CComCachedTearOffObject:: AddRef

オブジェクトの参照カウントを `CComCachedTearOffObject` 1 だけインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断とテストに役立つ可能性のある値。

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a> CComCachedTearOffObject::CComCachedTearOffObject

コンストラクターです。

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
から `IUnknown` のへのポインター `CComCachedTearOffObject` 。

### <a name="remarks"></a>解説

`CComContainedObject` [M_contained](#m_contained)メンバーを初期化します。

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a> CComCachedTearOffObject:: ~ CComCachedTearOffObject

デストラクターです。

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し、 [FinalRelease](#finalrelease)を呼び出します。

## <a name="ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a> CComCachedTearOffObject::FinalConstruct

を呼び出して `m_contained::FinalConstruct` `m_contained` 、 `CComContainedObject` <  `contained` ティアオフクラスによって実装されたインターフェイスにアクセスするために使用する> オブジェクトを作成します。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a> CComCachedTearOffObject::FinalRelease

`m_contained::FinalRelease`を呼び出し `m_contained` て、> オブジェクトを解放し `CComContainedObject` <  `contained` ます。

```cpp
void FinalRelease();
```

## <a name="ccomcachedtearoffobjectm_contained"></a><a name="m_contained"></a> CComCachedTearOffObject:: m_contained

ティアオフクラスから派生した [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) オブジェクト。

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>パラメーター

*格納*<br/>
からから派生したティアオフクラス、 `CComTearOffObjectBase` およびティアオフオブジェクトがサポートするインターフェイスです。

### <a name="remarks"></a>解説

継承されたメソッドは、キャッシュされた `m_contained` ティアオフオブジェクトの、、およびを使用して、ティアオフクラスのティアオフインターフェイスにアクセスするために使用され `QueryInterface` `FinalConstruct` `FinalRelease` ます。

## <a name="ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a> CComCachedTearOffObject:: QueryInterface

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
から要求されているインターフェイスの GUID。

*ppvObject*<br/>
入出力 *Iid* によって識別されるインターフェイスポインターへのポインター。インターフェイスが見つからない場合は NULL。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

要求されたインターフェイスがの場合 `IUnknown` 、自体へのポインターを返し、 `CComCachedTearOffObject` `IUnknown` 参照カウントをインクリメントします。 それ以外の場合は、から継承された [Internalqueryinterface](ccomobjectrootex-class.md#internalqueryinterface) メソッドを使用して、ティアオフクラスのインターフェイスに対してクエリを `CComObjectRootEx` 行います。

## <a name="ccomcachedtearoffobjectrelease"></a><a name="release"></a> CComCachedTearOffObject:: Release

参照カウントを1だけデクリメントし、参照カウントが0の場合はオブジェクトを削除し `CComCachedTearOffObject` ます。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

非デバッグビルドでは、は常に0を返します。 デバッグビルドでは、診断またはテストに役立つ値が返されます。

## <a name="see-also"></a>関連項目

[CComTearOffObject クラス](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
