---
title: クラス
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
ms.openlocfilehash: b9200c9c396fc16b6df3f4c2f4c66fb7976316d4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748169"
---
# <a name="ccomaggobject-class"></a>クラス

このクラスは、集約オブジェクトの[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)インターフェイスを実装します。 定義上、集約オブジェクトは外部オブジェクト内に含まれます。 クラス`CComAggObject`は[CComObject クラス](../../atl/reference/ccomobject-class.md)に似ていますが、外部クライアントから直接アクセスできるインターフェイスを公開する点が異なっています。

## <a name="syntax"></a>構文

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>パラメーター

*含ま れる*<br/>
[CComObjectRoot または CComObjectRootEx](../../atl/reference/ccomobjectroot-class.md)から派生したクラス、およびオブジェクトでサポートするその他のインターフェイスから派生したクラス。 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コムアグオブジェクト::コムアグオブジェクト](#ccomaggobject)|コンストラクターです。|
|[コムガグオブジェクト::~コマッグオブジェクト](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コマグオブジェクト::AddRef](#addref)|集約されたオブジェクトの参照カウントをインクリメントします。|
|[オブジェクトを作成します。](#createinstance)|この静的関数を使用すると、新しい**CComAggObject<**`contained`**>** オブジェクトを[作成](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)できます。|
|[コムガグオブジェクト::ファイナルコンストラクト](#finalconstruct)|の最終初期化を`m_contained`実行します。|
|[コムガグオブジェクト::ファイナルリリース](#finalrelease)|の最終破棄を`m_contained`実行します。|
|[コムガグオブジェクト::クエリインターフェイス](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[ココモグオブジェクト::リリース](#release)|集約されたオブジェクトの参照カウントをデクリメントします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コムガグオブジェクト::m_contained](#m_contained)|外部`IUnknown`不明へのデリゲート呼び出し。|

## <a name="remarks"></a>解説

`CComAggObject`は、集約オブジェクトの[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装します。 `CComAggObject`は、外部`IUnknown`オブジェクトのインタフェースとは別に独自の`IUnknown`インタフェースを持ち、独自の参照カウントを保持します。

集約の詳細については[、「ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[ココムオブジェクトルート](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomaggobjectaddref"></a><a name="addref"></a>コマグオブジェクト::AddRef

集約されたオブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断やテストに役立つ値。

## <a name="ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a>コムアグオブジェクト::コムアグオブジェクト

コンストラクターです。

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
[in]外側の未知。

### <a name="remarks"></a>解説

メンバーを`CComContainedObject`初期化[し、m_contained](#m_contained)し、モジュール ロックカウントをインクリメントします。

デストラクターは、モジュールのロックカウントをデクリメントします。

## <a name="ccomaggobjectccomaggobject"></a><a name="dtor"></a>コムガグオブジェクト::~コマッグオブジェクト

デストラクターです。

```
~CComAggObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し[、FinalRelease](#finalrelease)を呼び出し、モジュールロックカウントをデクリメントします。

## <a name="ccomaggobjectcreateinstance"></a><a name="createinstance"></a>オブジェクトを作成します。

この静的関数を使用すると、新しい**CComAggObject<**`contained`**>** オブジェクトを[作成](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)できます。

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>パラメーター

*頁*<br/>
[アウト]**CComAgg オブジェクト\<** へのポインターにポインター<em>が含まれていました</em>**>**。 失敗`CreateInstance`した場合 *、pp*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

返されるオブジェクトの参照カウントは 0 なので、`AddRef`すぐに呼び出`Release`し、完了したらオブジェクト ポインターの参照を解放するために使用します。

オブジェクトに直接アクセスする必要はありませんが、`CoCreateInstance`のオーバーヘッドを伴わずに新しいオブジェクトを作成する必要がある場合は、代わりに[CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance)を使用します。

## <a name="ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a>コムガグオブジェクト::ファイナルコンストラクト

オブジェクト構築の最終段階で呼び出されたこのメソッドは[、m_contained](#m_contained)メンバーに対して最終的な初期化を実行します。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomaggobjectfinalrelease"></a><a name="finalrelease"></a>コムガグオブジェクト::ファイナルリリース

オブジェクトの破棄中に呼び出されたこのメソッドは[、m_contained](#m_contained)メンバーを解放します。

```cpp
void FinalRelease();
```

## <a name="ccomaggobjectm_contained"></a><a name="m_contained"></a>コムガグオブジェクト::m_contained

クラスから派生[したオブジェクト。](../../atl/reference/ccomcontainedobject-class.md)

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>パラメーター

*含ま れる*<br/>
[in][CComObjectRoot または CComObjectRootEx](../../atl/reference/ccomobjectroot-class.md)から派生したクラス、およびオブジェクトでサポートするその他のインターフェイスから派生したクラス。 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

### <a name="remarks"></a>解説

すべての`IUnknown`呼び`m_contained`出しは、外部不明にデリゲートされます。

## <a name="ccomaggobjectqueryinterface"></a><a name="queryinterface"></a>コムガグオブジェクト::クエリインターフェイス

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

### <a name="remarks"></a>解説

要求されたインターフェイスが`IUnknown`の`QueryInterface`場合は、集約オブジェクト自身`IUnknown`へのポインタを返し、参照カウントをインクリメントします。 それ以外の場合、このメソッドは、メンバー `CComContainedObject` [m_contained](#m_contained)を介してインターフェイスを照会します。

## <a name="ccomaggobjectrelease"></a><a name="release"></a>ココモグオブジェクト::リリース

集約されたオブジェクトの参照カウントをデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグ ビルドでは`Release`、診断やテストに役立つ値を返します。 非デバッグ ビルドでは、`Release`常に 0 を返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomobject-class.md)<br/>
[クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
