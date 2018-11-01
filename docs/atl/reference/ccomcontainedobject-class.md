---
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
ms.openlocfilehash: 289174fbfc61b0bbca65233fe24d93537627e17d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492574"
---
# <a name="ccomcontainedobject-class"></a>CComContainedObject クラス

このクラスは実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)所有者オブジェクトの委任することによって`IUnknown`します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|コンストラクターです。 所有者のオブジェクトのメンバーのポインターを初期化します`IUnknown`します。|
|[CComContainedObject:: ~ CComContainedObject](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComContainedObject::AddRef](#addref)|所有者オブジェクトの参照カウントをインクリメントします。|
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|所有者オブジェクトの取得`IUnknown`します。|
|[CComContainedObject::QueryInterface](#queryinterface)|所有者オブジェクトの要求されたインターフェイスへのポインターを取得します。|
|[CComContainedObject::Release](#release)|所有者オブジェクトの参照カウントをデクリメントします。|

## <a name="remarks"></a>Remarks

ATL を使用して`CComContainedObject`クラスで[CComAggObject](../../atl/reference/ccomaggobject-class.md)、 [CComPolyObject](../../atl/reference/ccompolyobject-class.md)、および[CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)します。 `CComContainedObject` 実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)所有者オブジェクトの委任することによって`IUnknown`します。 (所有者は、集計の外側のオブジェクトまたはティアオフ インターフェイスが作成される対象のオブジェクトのいずれか)。`CComContainedObject`呼び出し`CComObjectRootEx`の`OuterQueryInterface`、 `OuterAddRef`、および`OuterRelease`から継承されたすべて、`Base`します。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComContainedObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="addref"></a>  CComContainedObject::AddRef

所有者オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

テストや診断に使用する値。

##  <a name="ccomcontainedobject"></a>  CComContainedObject::CComContainedObject

コンストラクターです。

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*現在価値*<br/>
[in]所有者オブジェクトの`IUnknown`します。

### <a name="remarks"></a>Remarks

セット、`m_pOuterUnknown`メンバー ポインター (から継承、`Base`クラス) に*pv*します。

##  <a name="dtor"></a>  CComContainedObject:: ~ CComContainedObject

デストラクターです。

```
~CComContainedObject();
```

### <a name="remarks"></a>Remarks

割り当てられているすべてのリソースを解放します。

##  <a name="getcontrollingunknown"></a>  CComContainedObject::GetControllingUnknown

返します、`m_pOuterUnknown`メンバー ポインター (から継承、*ベース*クラス)、所有者オブジェクトの格納されている`IUnknown`します。

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>戻り値

所有者オブジェクトの`IUnknown`します。

### <a name="remarks"></a>Remarks

このメソッドが仮想にする場合は`Base`が宣言されている、 [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown)マクロ。

##  <a name="queryinterface"></a>  CComContainedObject::QueryInterface

所有者オブジェクトの要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
[in]要求されているインターフェイスの識別子。

*ppvObject*<br/>
[out]によって識別されるインターフェイス ポインターへのポインター *iid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObject* NULL に設定されます。

*pp*<br/>
[out]型によって識別されるインターフェイス ポインターへのポインター`Q`します。 オブジェクトは、このインターフェイスをサポートしていない場合*pp* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="release"></a>  CComContainedObject::Release

所有者オブジェクトの参照カウントをデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグ ビルドで`Release`テストや診断に使用する値を返します。 非デバッグ ビルドで`Release`常に 0 を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
