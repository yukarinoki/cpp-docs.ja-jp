---
description: '詳細情報: CComAggObject クラス'
title: CComAggObject クラス
ms.date: 11/04/2016
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
ms.openlocfilehash: 84af79678221ae74a151a4821039ff1d7a743cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152361"
---
# <a name="ccomaggobject-class"></a>CComAggObject クラス

このクラスは、集計されたオブジェクトの [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) インターフェイスを実装します。 定義上、集計されたオブジェクトは、外側のオブジェクトに含まれています。 クラスは、 `CComAggObject` 外部クライアントから直接アクセスできるインターフェイスを公開する点を除いて、 [CComObject クラス](../../atl/reference/ccomobject-class.md)に似ています。

## <a name="syntax"></a>構文

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>パラメーター

*格納*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラス、およびオブジェクトでサポートする他のインターフェイスから派生したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComAggObject:: CComAggObject](#ccomaggobject)|コンストラクターです。|
|[CComAggObject:: ~ CComAggObject](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComAggObject:: AddRef](#addref)|集計されたオブジェクトの参照カウントをインクリメントします。|
|[CComAggObject:: CreateInstance](#createinstance)|この静的関数を使用すると、  `contained` **>** [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)のオーバーヘッドを発生させずに、新しい CComAggObject<オブジェクトを作成できます。|
|[CComAggObject:: FinalConstruct](#finalconstruct)|の最終初期化を実行 `m_contained` します。|
|[CComAggObject:: FinalRelease](#finalrelease)|の最終的な破棄を実行 `m_contained` します。|
|[CComAggObject:: QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[CComAggObject:: Release](#release)|集計されたオブジェクトの参照カウントをデクリメントします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComAggObject:: m_contained](#m_contained)|`IUnknown`外側の不明なへの呼び出しをデリゲートします。|

## <a name="remarks"></a>解説

`CComAggObject` 集計されたオブジェクトに対して [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) を実装します。 `CComAggObject` は `IUnknown` 、外側のオブジェクトのインターフェイスとは別に独自のインターフェイスを持ち、 `IUnknown` 独自の参照カウントを保持します。

集計の詳細については、「 [ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomaggobjectaddref"></a><a name="addref"></a> CComAggObject:: AddRef

集計されたオブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断またはテストに役立つ可能性のある値。

## <a name="ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a> CComAggObject:: CComAggObject

コンストラクターです。

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
から外側の不明な。

### <a name="remarks"></a>解説

メンバーを初期化し、 `CComContainedObject` [m_contained](#m_contained)して、モジュールのロックカウントをインクリメントします。

デストラクターは、モジュールのロックカウントをデクリメントします。

## <a name="ccomaggobjectccomaggobject"></a><a name="dtor"></a> CComAggObject:: ~ CComAggObject

デストラクターです。

```
~CComAggObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し、 [FinalRelease](#finalrelease)を呼び出して、モジュールのロックカウントをデクリメントします。

## <a name="ccomaggobjectcreateinstance"></a><a name="createinstance"></a> CComAggObject:: CreateInstance

この静的関数を使用すると、  `contained` **>** [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)のオーバーヘッドを発生させずに、新しい CComAggObject<オブジェクトを作成できます。

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
入出力CComAggObject へのポインターに> * * ポインターが **\<**<em> 含ま </em>** れています。 `CreateInstance`が失敗した場合、 *PP* は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

返されるオブジェクトは、参照カウントが0であるため、をすぐに呼び出し、を使用して `AddRef` `Release` オブジェクトポインターの参照を解放します。

オブジェクトへの直接アクセスが不要でも、のオーバーヘッドなしで新しいオブジェクトを作成する場合は `CoCreateInstance` 、代わりに [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) を使用します。

## <a name="ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a> CComAggObject:: FinalConstruct

オブジェクト構築の最終段階で呼び出され、このメソッドは [m_contained](#m_contained) メンバーに対して最終的な初期化を実行します。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomaggobjectfinalrelease"></a><a name="finalrelease"></a> CComAggObject:: FinalRelease

このメソッドは、オブジェクトの破棄中に呼び出され、 [m_contained](#m_contained) メンバーを解放します。

```cpp
void FinalRelease();
```

## <a name="ccomaggobjectm_contained"></a><a name="m_contained"></a> CComAggObject:: m_contained

クラスから派生した [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) オブジェクト。

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>パラメーター

*格納*<br/>
から [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) または [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラス、およびオブジェクトでサポートする他のインターフェイスから派生したクラス。

### <a name="remarks"></a>解説

`IUnknown`経由のすべて `m_contained` の呼び出しは、外側の不明なに委任されます。

## <a name="ccomaggobjectqueryinterface"></a><a name="queryinterface"></a> CComAggObject:: QueryInterface

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
から要求されているインターフェイスの識別子。

*ppvObject*<br/>
入出力 *Iid* によって識別されるインターフェイスポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合、 *ppvObject* は NULL に設定されます。

*ページ*<br/>
入出力型によって識別されるインターフェイスポインターへのポインター `Q` 。 オブジェクトがこのインターフェイスをサポートしていない場合、 *pp* は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

要求されたインターフェイスがの場合、は、集計された `IUnknown` `QueryInterface` オブジェクト自体へのポインターを返し、 `IUnknown` 参照カウントをインクリメントします。 それ以外の場合、このメソッドは、m_contained メンバーを介してインターフェイスを照会 `CComContainedObject` します。 [](#m_contained)

## <a name="ccomaggobjectrelease"></a><a name="release"></a> CComAggObject:: Release

集計されたオブジェクトの参照カウントをデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグビルドでは、 `Release` 診断またはテストに役立つ値が返されます。 非デバッグビルドでは、は `Release` 常に0を返します。

## <a name="see-also"></a>関連項目

[CComObject クラス](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
