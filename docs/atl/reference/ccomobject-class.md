---
description: '詳細情報: CComObject クラス'
title: CComObject クラス
ms.date: 11/04/2016
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
ms.openlocfilehash: 086383172d5bb239bbac8ed90e9118838aea1254
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146524"
---
# <a name="ccomobject-class"></a>CComObject クラス

このクラス `IUnknown` は、非集計オブジェクトに対してを実装します。

## <a name="syntax"></a>構文

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>パラメーター

*常用*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラス、およびオブジェクトでサポートする他のインターフェイスから派生したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComObject:: CComObject](#ccomobject)|コンストラクターです。|
|[CComObject:: ~ CComObject](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComObject:: AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|
|[CComObject:: CreateInstance](#createinstance)|雑音新しいオブジェクトを作成し `CComObject` ます。|
|[CComObject:: QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[CComObject:: Release](#release)|オブジェクトの参照カウントをデクリメントします。|

## <a name="remarks"></a>解説

`CComObject` 非集計オブジェクトの [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) を実装します。 ただし、、、およびへの呼び出し `QueryInterface` `AddRef` `Release` はに委任され `CComObjectRootEx` ます。

の使用方法の詳細については `CComObject` 、「 [ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComObject`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomobjectaddref"></a><a name="addref"></a> CComObject:: AddRef

オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

この関数は、オブジェクトに対してインクリメントされた新しい参照カウントを返します。 この値は、診断またはテストに便利な場合があります。

## <a name="ccomobjectccomobject"></a><a name="ccomobject"></a> CComObject:: CComObject

コンストラクターは、モジュールのロックカウントをインクリメントします。

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>パラメーター

<em>void\*</em><br/>
からこの無名パラメーターは使用されません。 これは、他のコンストラクターとの対称のために存在し `CComXXXObjectXXX` ます。

### <a name="remarks"></a>解説

デストラクターはこれをデクリメントします。

`CComObject`派生オブジェクトが演算子を使用して正常に構築された場合 **`new`** 、最初の参照カウントは0になります。 参照カウントを適切な値 (1) に設定するには、 [AddRef](#addref) 関数を呼び出します。

## <a name="ccomobjectccomobject"></a><a name="dtor"></a> CComObject:: ~ CComObject

デストラクターです。

```
CComObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し、 [FinalRelease](ccomobjectrootex-class.md#finalrelease)を呼び出して、モジュールのロックカウントをデクリメントします。

## <a name="ccomobjectcreateinstance"></a><a name="createinstance"></a> CComObject:: CreateInstance

この静的関数を使用すると `Base` **>** 、 [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)のオーバーヘッドを発生させることなく、新しい CComObject<オブジェクトを作成できます。

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
入出力 **CComObject<** ポインターへのポインター `Base` **>** 。 `CreateInstance`が失敗した場合、 *PP* は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

返されるオブジェクトは、参照カウントが0であるため、をすぐに呼び出し、を使用して `AddRef` `Release` オブジェクトポインターの参照を解放します。

オブジェクトへの直接アクセスが不要でも、のオーバーヘッドなしで新しいオブジェクトを作成する場合は `CoCreateInstance` 、代わりに [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

## <a name="ccomobjectqueryinterface"></a><a name="queryinterface"></a> CComObject:: QueryInterface

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

## <a name="ccomobjectrelease"></a><a name="release"></a> CComObject:: Release

オブジェクトの参照カウントをデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

この関数は、オブジェクトの新しいデクリメントされた参照カウントを返します。 デバッグビルドでは、診断またはテストに戻り値が役立つ場合があります。 非デバッグビルドでは、は `Release` 常に0を返します。

## <a name="see-also"></a>関連項目

[CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
