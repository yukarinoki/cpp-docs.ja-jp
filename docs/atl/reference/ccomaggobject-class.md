---
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
ms.openlocfilehash: 3598e625351f80a1a183b3128bf46a72143a02f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626838"
---
# <a name="ccomaggobject-class"></a>CComAggObject クラス

このクラスは、実装、 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)集計オブジェクトのインターフェイス。 定義上、集約オブジェクトは外側のオブジェクト内に含まれます。 `CComAggObject`クラスと似ています、 [CComObject クラス](../../atl/reference/ccomobject-class.md)、外部クライアントに直接アクセスできるインターフェイスを公開する点が異なります。

## <a name="syntax"></a>構文

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>パラメーター

*含まれています。*<br/>
派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のすべてのインターフェイスからも、します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComAggObject::CComAggObject](#ccomaggobject)|コンストラクターです。|
|[CComAggObject:: ~ CComAggObject](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComAggObject::AddRef](#addref)|集約オブジェクトの参照カウントをインクリメントします。|
|[CComAggObject::CreateInstance](#createinstance)|この静的関数では、新たに作成することができます**CComAggObject <** `contained` **>** のオーバーヘッドなしオブジェクト[CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)します。|
|[CComAggObject::FinalConstruct](#finalconstruct)|最終初期化を実行します。`m_contained`します。|
|[CComAggObject::FinalRelease](#finalrelease)|最終的な破棄を実行します。`m_contained`します。|
|[CComAggObject::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[CComAggObject::Release](#release)|集約オブジェクトの参照カウントをデクリメントします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComAggObject::m_contained](#m_contained)|デリゲート`IUnknown`不明な外部への呼び出し。|

## <a name="remarks"></a>Remarks

`CComAggObject` 実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)集約オブジェクト。 `CComAggObject` 独自`IUnknown`インターフェイス、外側のオブジェクトから個別`IUnknown`インターフェイス、および参照カウントを保持します。

集計の詳細については、記事を参照してください。 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="addref"></a>  CComAggObject::AddRef

集約オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

テストや診断に使用する値。

##  <a name="ccomaggobject"></a>  CComAggObject::CComAggObject

コンストラクターです。

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*現在価値*<br/>
[in]不明な外部です。

### <a name="remarks"></a>Remarks

初期化します、`CComContainedObject`メンバー、[で呼び出され](#m_contained)、およびモジュールのロック カウントをインクリメントします。

モジュールのロック カウントをデストラクター デクリメントします。

##  <a name="dtor"></a>  CComAggObject:: ~ CComAggObject

デストラクターです。

```
~CComAggObject();
```

### <a name="remarks"></a>Remarks

呼び出し、割り当てられているすべてのリソースを解放[FinalRelease](#finalrelease)、およびモジュールのロック カウントをデクリメントします。

##  <a name="createinstance"></a>  CComAggObject::CreateInstance

この静的関数では、新たに作成することができます**CComAggObject <** `contained` **>** のオーバーヘッドなしオブジェクト[CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)します。

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>パラメーター

*pp*<br/>
[out]ポインターを**CComAggObject\<**<em>に含まれている</em>**>** ポインター。 場合`CreateInstance`が成功すると、 *pp* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

返されるオブジェクトが参照カウントを 0、ためコール`AddRef`しを使用して、すぐに`Release`完了すると、オブジェクトへのポインターの参照を解放します。

オブジェクトへのアクセスが直接必要ありませんが、引き続きのオーバーヘッドなしの新しいオブジェクトを作成する場合`CoCreateInstance`を使用して、[あって](../../atl/reference/ccomcoclass-class.md#createinstance)代わりにします。

##  <a name="finalconstruct"></a>  CComAggObject::FinalConstruct

オブジェクトの構築の最終段階で呼び出されると、このメソッドの最終初期化を実行します、[で呼び出され](#m_contained)メンバー。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="finalrelease"></a>  CComAggObject::FinalRelease

オブジェクトの破棄中に呼び出されると、このメソッドは、解放、[で呼び出され](#m_contained)メンバー。

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComAggObject::m_contained

A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)クラスから派生したオブジェクト。

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>パラメーター

*含まれています。*<br/>
[in]派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のすべてのインターフェイスからも、します。

### <a name="remarks"></a>Remarks

すべて`IUnknown`を通じて呼び出す`m_contained`不明な外部に委任されます。

##  <a name="queryinterface"></a>  CComAggObject::QueryInterface

要求されたインターフェイスへのポインターを取得します。

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

### <a name="remarks"></a>Remarks

要求されたインターフェイスがある場合`IUnknown`、`QueryInterface`集計オブジェクトの独自のポインターを返します`IUnknown`し、参照カウントをインクリメントします。 それ以外の場合、このメソッド クエリ インターフェイスを介して、`CComContainedObject`メンバー、[で呼び出され](#m_contained)します。

##  <a name="release"></a>  CComAggObject::Release

集約オブジェクトの参照カウントをデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグ ビルドで`Release`テストや診断に使用する値を返します。 非デバッグ ビルドで`Release`常に 0 を返します。

## <a name="see-also"></a>関連項目

[CComObject クラス](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[集約](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
