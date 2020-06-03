---
title: クラス
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
ms.openlocfilehash: de6ffb45fe5c6f73ab656d5c6185b70d9f5edd38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327644"
---
# <a name="ccomobject-class"></a>クラス

このクラスは、`IUnknown`非集約オブジェクトを実装します。

## <a name="syntax"></a>構文

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
[CComObjectRoot または CComObjectRootEx](../../atl/reference/ccomobjectroot-class.md)から派生したクラス、およびオブジェクトでサポートするその他のインターフェイスから派生したクラス。 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::CComオブジェクト](#ccomobject)|コンストラクターです。|
|[オブジェクト::~CComオブジェクト](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクト::AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|
|[オブジェクト::インスタンスの作成](#createinstance)|(静的)新しい`CComObject`オブジェクトを作成します。|
|[次のクエリインターフェイス](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[CComオブジェクト::リリース](#release)|オブジェクトの参照カウントを減算します。|

## <a name="remarks"></a>解説

`CComObject`は、非集約オブジェクトの[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装します。 `QueryInterface`ただし、 、、`AddRef`および`Release`への呼び出`CComObjectRootEx`しは に委任されます。

の使用方法`CComObject`の詳細については、「 [ATL COM オブジェクトの基礎 」](../../atl/fundamentals-of-atl-com-objects.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomobjectaddref"></a><a name="addref"></a>オブジェクト::AddRef

オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

この関数は、オブジェクトの新しいインクリメントされた参照カウントを返します。 この値は、診断やテストに役立ちます。

## <a name="ccomobjectccomobject"></a><a name="ccomobject"></a>::CComオブジェクト

コンストラクターは、モジュールのロックカウントをインクリメントします。

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>パラメーター

<em>void\*</em><br/>
[in]この名前のないパラメーターは使用されません。 他`CComXXXObjectXXX`のコンストラクタとの対称性のために存在します。

### <a name="remarks"></a>解説

デストラクタはそれをデクリメントします。

new`CComObject`演算子を使用して派生オブジェクトが正常に**new**構築された場合、初期参照カウントは 0 になります。 参照カウントを適切な値 (1) に設定するには[、AddRef](#addref)関数を呼び出します。

## <a name="ccomobjectccomobject"></a><a name="dtor"></a>オブジェクト::~CComオブジェクト

デストラクターです。

```
CComObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し[、FinalRelease](ccomobjectrootex-class.md#finalrelease)を呼び出し、モジュールロックカウントをデクリメントします。

## <a name="ccomobjectcreateinstance"></a><a name="createinstance"></a>オブジェクト::インスタンスの作成

この静的関数を使用すると[、CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)のオーバーヘッドを伴わずに、新しい**CComObject<**`Base`**>** オブジェクトを作成できます。

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>パラメーター

*頁*<br/>
[アウト]ポインターを **<**`Base`**>** 指すポインターを返します。 失敗`CreateInstance`した場合 *、pp*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

返されるオブジェクトの参照カウントは 0 なので、`AddRef`すぐに呼び出`Release`し、完了したらオブジェクト ポインターの参照を解放するために使用します。

オブジェクトに直接アクセスする必要はありませんが、`CoCreateInstance`のオーバーヘッドを伴わずに新しいオブジェクトを作成する必要がある場合は、代わりに[CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

## <a name="ccomobjectqueryinterface"></a><a name="queryinterface"></a>次のクエリインターフェイス

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]要求されているインターフェイスの識別子。

*オブジェクト*<br/>
[アウト]*iid*で識別されるインターフェイス ポインタへのポインタ。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppvObject*は NULL に設定されます。

*頁*<br/>
[アウト]type`Q`で識別されるインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合 *、pp*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomobjectrelease"></a><a name="release"></a>CComオブジェクト::リリース

オブジェクトの参照カウントを減算します。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

この関数は、オブジェクトの新しいデクリメントされた参照カウントを返します。 デバッグ ビルドでは、戻り値は診断やテストに役立ちます。 非デバッグ ビルドでは、`Release`常に 0 を返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
