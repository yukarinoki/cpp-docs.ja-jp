---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
ms.openlocfilehash: c880d170a03196d0e15ea8741c786e560d90ddc4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747773"
---
# <a name="ccompolyobject-class"></a>クラス

このクラスは、`IUnknown`集約オブジェクトまたは非集約オブジェクトを実装します。

## <a name="syntax"></a>構文

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>パラメーター

*含ま れる*<br/>
[CComObjectRoot または CComObjectRootEx](../../atl/reference/ccomobjectroot-class.md)から派生したクラス、およびオブジェクトでサポートするその他のインターフェイスから派生したクラス。 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::CComポリオブジェクト](#ccompolyobject)|コンストラクターです。|
|[オブジェクト::~CComポリオブジェクト](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトの追加](#addref)|オブジェクトの参照カウントをインクリメントします。|
|[オブジェクトを作成します。](#createinstance)|(静的)[新](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)しい**CComPolyObject<**`contained`**>** オブジェクトを作成できます。|
|[CComPolyオブジェクト::ファイナルコンストラクト](#finalconstruct)|の最終初期化を`m_contained`実行します。|
|[CComPolyオブジェクト::最終リリース](#finalrelease)|の最終破棄を`m_contained`実行します。|
|[次のオブジェクトを使用します。](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[CComポリオブジェクト::リリース](#release)|オブジェクトの参照カウントをデクリメントします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[オブジェクト::m_contained](#m_contained)|オブジェクト`IUnknown`が集約されていない場合は、オブジェクトが不明な外部への呼び`IUnknown`出しをデリゲートします。|

## <a name="remarks"></a>解説

`CComPolyObject`は、集約オブジェクトまたは非集約オブジェクトに対して[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装します。

のインスタンス`CComPolyObject`が作成されると、外部不明の値がチェックされます。 NULL の場合`IUnknown`、非集約オブジェクトに対して実装されます。 外側の不明な値が NULL`IUnknown`でない場合は、集約オブジェクトに対して実装されます。

使用`CComPolyObject`の利点は、集約されたケースと非集約型のケースを処理するために[、CComAggObject](../../atl/reference/ccomaggobject-class.md)と[CComObject](../../atl/reference/ccomobject-class.md)の両方をモジュールに含めないようにすることです。 1`CComPolyObject`つのオブジェクトが両方のケースを処理します。 つまり、モジュール内に vtable のコピーが 1 つだけ、関数のコピーが 1 つだけ存在します。 vtable が大きい場合、モジュールのサイズが大幅に減少する可能性があります。 ただし、vtable が小さい場合は`CComPolyObject`、モジュールサイズが少し大きくなる可能性があります`CComAggObject``CComObject`。

DECLARE_POLY_AGGREGATABLEマクロがオブジェクトのクラス定義で指定されている場合は、`CComPolyObject`オブジェクトの作成に使用されます。 ATL プロジェクト ウィザードを使用してフル コントロールまたは Internet Explorer コントロールを作成すると、DECLARE_POLY_AGGREGATABLEが自動的に宣言されます。

集約された場合、オブジェクト`CComPolyObject`は外側のオブジェクト`IUnknown`とは別に独自の を`IUnknown`持ち、それ自体の参照カウントを保持します。 `CComPolyObject`[は、外部不明](../../atl/reference/ccomcontainedobject-class.md)にデリゲートするために CComContained オブジェクトを使用します。

集約の詳細については[、「ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[ココムオブジェクトルート](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccompolyobjectaddref"></a><a name="addref"></a>オブジェクトの追加

オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断やテストに役立つ値。

## <a name="ccompolyobjectccompolyobject"></a><a name="ccompolyobject"></a>::CComポリオブジェクト

コンストラクターです。

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
[in]オブジェクトが集約される場合は外部不明へのポインター、 オブジェクトが集約されていない場合は NULL。

### <a name="remarks"></a>解説

データ メンバ`CComContainedObject`を初期化し[、m_contained](#m_contained)し、モジュール ロックカウントをインクリメントします。

デストラクターは、モジュールのロックカウントをデクリメントします。

## <a name="ccompolyobjectccompolyobject"></a><a name="dtor"></a>オブジェクト::~CComポリオブジェクト

デストラクターです。

```
~CComPolyObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し[、FinalRelease](#finalrelease)を呼び出し、モジュールロックカウントをデクリメントします。

## <a name="ccompolyobjectcreateinstance"></a><a name="createinstance"></a>オブジェクトを作成します。

[新](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)しい**CComPolyObject<**`contained`**>** オブジェクトを作成できます。

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>パラメーター

*頁*<br/>
[アウト]ポインターを<する**CComPolyObject**`contained`**>** へのポインター。 失敗`CreateInstance`した場合 *、pp*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

返されるオブジェクトの参照カウントは 0 なので、`AddRef`すぐに呼び出`Release`し、完了したらオブジェクト ポインターの参照を解放するために使用します。

オブジェクトに直接アクセスする必要がなく、`CoCreateInstance`のオーバーヘッドを伴わずに新しいオブジェクトを作成する必要がある場合は、代わりに[CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance)を使用します。

## <a name="ccompolyobjectfinalconstruct"></a><a name="finalconstruct"></a>CComPolyオブジェクト::ファイナルコンストラクト

オブジェクト構築の最終段階で呼び出されたこのメソッドは[、m_contained](#m_contained)データ メンバーに対して最終的な初期化を実行します。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccompolyobjectfinalrelease"></a><a name="finalrelease"></a>CComPolyオブジェクト::最終リリース

オブジェクトの破棄中に呼び出されるこのメソッドは[、m_contained](#m_contained)データ メンバーを解放します。

```cpp
void FinalRelease();
```

## <a name="ccompolyobjectm_contained"></a><a name="m_contained"></a>オブジェクト::m_contained

クラスから派生[したオブジェクト。](../../atl/reference/ccomcontainedobject-class.md)

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>パラメーター

*含ま れる*<br/>
[in][CComObjectRoot または CComObjectRootEx](../../atl/reference/ccomobjectroot-class.md)から派生したクラス、およびオブジェクトでサポートするその他のインターフェイスから派生したクラス。 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

### <a name="remarks"></a>解説

`IUnknown`オブジェクト`m_contained`が集約されている場合は、呼び出しが外部不明に、オブジェクトが集約`IUnknown`されていない場合はこのオブジェクトの に委譲されます。

## <a name="ccompolyobjectqueryinterface"></a><a name="queryinterface"></a>次のオブジェクトを使用します。

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>パラメーター

*Q*<br/>
COM インターフェイス。

*Iid*<br/>
[in]要求されているインターフェイスの識別子。

*オブジェクト*<br/>
[アウト]*iid*で識別されるインターフェイス ポインタへのポインタ。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppvObject*は NULL に設定されます。

*頁*<br/>
[アウト]によって`__uuidof(Q)`識別されるインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

集約オブジェクトの場合、要求されたインターフェイスが が`IUnknown``QueryInterface`の場合、集約オブジェクト自身`IUnknown`へのポインターを返し、参照カウントをインクリメントします。 それ以外の場合、このメソッドは、データ`CComContainedObject`メンバーを介してインターフェイスを照会[m_contained。](#m_contained)

## <a name="ccompolyobjectrelease"></a><a name="release"></a>CComポリオブジェクト::リリース

オブジェクトの参照カウントを減算します。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグ ビルドでは`Release`、診断やテストに役立つ値を返します。 非デバッグ ビルドでは`Release`、常に 0 を返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
