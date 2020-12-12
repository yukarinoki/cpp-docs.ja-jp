---
description: '詳細情報: CComContainedObject クラス'
title: CComContainedObject クラス
ms.date: 11/04/2016
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
ms.openlocfilehash: 9c0993d5ce71a557b71939f60a7019d3c062bac3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152205"
---
# <a name="ccomcontainedobject-class"></a>CComContainedObject クラス

このクラスは、所有者オブジェクトのに委任することによって [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) を実装し `IUnknown` ます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>パラメーター

*常用*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|コンストラクターです。 所有者オブジェクトのに対するメンバーポインターを初期化し `IUnknown` ます。|
|[CComContainedObject:: ~ CComContainedObject](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComContainedObject:: AddRef](#addref)|所有者オブジェクトの参照カウントをインクリメントします。|
|[CComContainedObject:: Getcontrol Unknown](#getcontrollingunknown)|所有者オブジェクトのを取得し `IUnknown` ます。|
|[CComContainedObject:: QueryInterface](#queryinterface)|所有者オブジェクトで要求されたインターフェイスへのポインターを取得します。|
|[CComContainedObject:: Release](#release)|所有者オブジェクトの参照カウントをデクリメントします。|

## <a name="remarks"></a>解説

ATL `CComContainedObject` では、 [CComAggObject](../../atl/reference/ccomaggobject-class.md)、 [CComPolyObject](../../atl/reference/ccompolyobject-class.md)、および [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)クラスでを使用します。 `CComContainedObject` 所有者オブジェクトのに委任することによって、 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) を実装し `IUnknown` ます。 (所有者は、集計の外部オブジェクト、またはティアオフインターフェイスを作成する対象のオブジェクトのいずれかです)。 `CComContainedObject` `CComObjectRootEx` `OuterQueryInterface` は、、 `OuterAddRef` 、および `OuterRelease` を呼び出します。すべてを通じて継承さ `Base` れます。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComContainedObject`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomcontainedobjectaddref"></a><a name="addref"></a> CComContainedObject:: AddRef

所有者オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断またはテストに役立つ可能性のある値。

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a> CComContainedObject::CComContainedObject

コンストラクターです。

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
から所有者オブジェクトの `IUnknown` です。

### <a name="remarks"></a>解説

`m_pOuterUnknown`(クラスを通じて継承される `Base` ) メンバーポインターを *pv* に設定します。

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a> CComContainedObject:: ~ CComContainedObject

デストラクターです。

```
~CComContainedObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a> CComContainedObject:: Getcontrol Unknown

`m_pOuterUnknown`所有者オブジェクトのを保持するメンバーポインター (*基本* クラスを通じて継承) を返し `IUnknown` ます。

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>戻り値

所有者オブジェクトの `IUnknown` です。

### <a name="remarks"></a>解説

`Base`が[DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown)マクロを宣言している場合、このメソッドは仮想である可能性があります。

## <a name="ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a> CComContainedObject:: QueryInterface

所有者オブジェクトで要求されたインターフェイスへのポインターを取得します。

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

## <a name="ccomcontainedobjectrelease"></a><a name="release"></a> CComContainedObject:: Release

所有者オブジェクトの参照カウントをデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグビルドでは、 `Release` 診断またはテストに役立つ値が返されます。 非デバッグビルドでは、は `Release` 常に0を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
