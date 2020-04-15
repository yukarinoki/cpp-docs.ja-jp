---
title: クラスを含む
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
ms.openlocfilehash: 72ba27c3be6576621995ffb8c98995c6abc9324c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320796"
---
# <a name="ccomcontainedobject-class"></a>クラスを含む

このクラスは、所有者オブジェクトの に委任することによって[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装`IUnknown`します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
クラスは[、CCom オブジェクト ルート](../../atl/reference/ccomobjectroot-class.md)または[CCom オブジェクト ルート Ex](../../atl/reference/ccomobjectrootex-class.md)から派生します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[オブジェクトを含むオブジェクト](#ccomcontainedobject)|コンストラクターです。 所有者オブジェクトのメンバー ポインターを初期化`IUnknown`します。|
|[オブジェクトを含みます。](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトを追加します。](#addref)|所有者オブジェクトの参照カウントをインクリメントします。|
|[オブジェクトを取得します。](#getcontrollingunknown)|所有者オブジェクトの`IUnknown`を取得します。|
|[オブジェクト::クエリインターフェイス](#queryinterface)|所有者オブジェクトで要求されたインターフェイスへのポインターを取得します。|
|[オブジェクト::リリース](#release)|所有者オブジェクトの参照カウントを減算します。|

## <a name="remarks"></a>解説

ATL`CComContainedObject`[は](../../atl/reference/ccompolyobject-class.md)クラス[で使用します](../../atl/reference/ccomaggobject-class.md)[。](../../atl/reference/ccomcachedtearoffobject-class.md) `CComContainedObject`は、所有者オブジェクトの に委任することによって[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装`IUnknown`します。 (所有者は、集約の外部オブジェクトか、ティアオフ インターフェイスが作成されるオブジェクトのいずれかです)。`CComContainedObject`を`CComObjectRootEx`呼び`OuterQueryInterface`出`OuterAddRef`す`OuterRelease`、 、および`Base`のすべてが を通じて継承されます。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComContainedObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomcontainedobjectaddref"></a><a name="addref"></a>オブジェクトを追加します。

所有者オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断やテストに役立つ値。

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a>オブジェクトを含むオブジェクト

コンストラクターです。

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
[in]所有者オブジェクトの`IUnknown`.

### <a name="remarks"></a>解説

`m_pOuterUnknown`メンバー ポインター (クラスを通`Base`じて継承された) を*pv*に設定します。

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a>オブジェクトを含みます。

デストラクターです。

```
~CComContainedObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a>オブジェクトを取得します。

所有者オブジェクト`m_pOuterUnknown`の を保持するメンバー ポインター *(Base*クラスを通じて`IUnknown`継承された) を返します。

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>戻り値

所有者オブジェクトの`IUnknown`.

### <a name="remarks"></a>解説

このメソッドは[、DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) `Base`マクロを宣言している場合は仮想である可能性があります。

## <a name="ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a>オブジェクト::クエリインターフェイス

所有者オブジェクトで要求されたインターフェイスへのポインターを取得します。

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

## <a name="ccomcontainedobjectrelease"></a><a name="release"></a>オブジェクト::リリース

所有者オブジェクトの参照カウントを減算します。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグ ビルドでは`Release`、診断やテストに役立つ値を返します。 非デバッグ ビルドでは、`Release`常に 0 を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
