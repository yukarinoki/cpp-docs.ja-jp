---
title: CComPolyObject クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec995026b0142fc30470836b29697457be91937e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764811"
---
# <a name="ccompolyobject-class"></a>CComPolyObject クラス

このクラスは実装`IUnknown`集計または非集約オブジェクト。

## <a name="syntax"></a>構文

```
template<class contained>  
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>パラメーター

*含まれています。*  
派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のすべてのインターフェイスからも、します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComPolyObject::CComPolyObject](#ccompolyobject)|コンストラクターです。|
|[CComPolyObject:: ~ CComPolyObject](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComPolyObject::AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|
|[CComPolyObject::CreateInstance](#createinstance)|(静的)新しいを作成することができます**CComPolyObject <** `contained` **>** のオーバーヘッドなしオブジェクト[CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)します。|
|[CComPolyObject::FinalConstruct](#finalconstruct)|最終初期化を実行します。`m_contained`します。|
|[CComPolyObject::FinalRelease](#finalrelease)|最終的な破棄を実行します。`m_contained`します。|
|[CComPolyObject::QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[CComPolyObject::Release](#release)|オブジェクトの参照カウントをデクリメントします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComPolyObject::m_contained](#m_contained)|デリゲート`IUnknown`集約オブジェクトの場合、またはに不明な外部への呼び出し、`IUnknown`オブジェクトが集計されない場合は、オブジェクトの。|

## <a name="remarks"></a>Remarks

`CComPolyObject` 実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)集計または非集約オブジェクト。

インスタンス`CComPolyObject`作成は、外側の値が"不明"のチェックします。 NULL の場合`IUnknown`の非集計オブジェクトに実装されます。 不明な外部が NULL でない場合`IUnknown`集約オブジェクトに実装されます。

使用する利点`CComPolyObject`は両方を持つように[CComAggObject](../../atl/reference/ccomaggobject-class.md)と[CComObject](../../atl/reference/ccomobject-class.md)集計データおよび非集計のケースを処理するモジュールでします。 1 つ`CComPolyObject`オブジェクトは両方のケースを処理します。 つまり、モジュールで、vtable の 1 つだけのコピーと、関数の 1 つのコピーが存在します。 Vtable が大きい場合、モジュールのサイズが大幅に減りこのことができます。 ただし、vtable が小さい場合を使用して`CComPolyObject`には、集計または非集約オブジェクトは、最適化されていないために、モジュールのサイズを少し大きめにつながるは`CComAggObject`と`CComObject`します。

DECLARE_POLY_AGGREGATABLE マクロは、オブジェクトのクラス定義で指定されている場合`CComPolyObject`オブジェクトを作成するために使用されます。 ATL プロジェクト ウィザードを使用して、フル コントロールまたは Internet Explorer のコントロールを作成する場合、DECLARE_POLY_AGGREGATABLE が自動的に宣言されます。

で集計される場合、`CComPolyObject`オブジェクトが、独自`IUnknown`、外側のオブジェクトから別`IUnknown`、および参照カウントを管理します。 `CComPolyObject` 使用して[CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)を不明な外部に委任します。

集計の詳細については、記事を参照してください。 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h

##  <a name="addref"></a>  CComPolyObject::AddRef

オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

テストや診断に使用する値。

##  <a name="ccompolyobject"></a>  CComPolyObject::CComPolyObject

コンストラクターです。

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*現在価値*  
[in]外部の不明な場合、オブジェクトを集計する場合は NULL をへのポインター オブジェクトが集計されない場合は、オブジェクト。

### <a name="remarks"></a>Remarks

初期化します、`CComContainedObject`データ メンバー、[で呼び出され](#m_contained)、およびモジュールのロック カウントをインクリメントします。

モジュールのロック カウントをデストラクター デクリメントします。

##  <a name="dtor"></a>  CComPolyObject:: ~ CComPolyObject

デストラクターです。

```
~CComPolyObject();
```

### <a name="remarks"></a>Remarks

呼び出し、割り当てられているすべてのリソースを解放[FinalRelease](#finalrelease)、およびモジュールのロック カウントをデクリメントします。

##  <a name="createinstance"></a>  CComPolyObject::CreateInstance

新しいを作成することができます**CComPolyObject <** `contained` **>** のオーバーヘッドなしオブジェクト[CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)します。

```
static HRESULT WINAPI CreateInstance(  
    LPUNKNOWN pUnkOuter, 
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>パラメーター

*pp*  
[out]ポインターを**CComPolyObject <** `contained` **>** ポインター。 場合`CreateInstance`が成功すると、 *pp* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

返されるオブジェクトが参照カウントを 0、ためコール`AddRef`しを使用して、すぐに`Release`完了すると、オブジェクトへのポインターの参照を解放します。

直接オブジェクトへのアクセスが引き続きのオーバーヘッドなしの新しいオブジェクトを作成する場合`CoCreateInstance`を使用して、[あって](../../atl/reference/ccomcoclass-class.md#createinstance)代わりにします。

##  <a name="finalconstruct"></a>  CComPolyObject::FinalConstruct

オブジェクトの構築の最終段階で呼び出されると、このメソッドの最終初期化を実行します、[で呼び出され](#m_contained)データ メンバー。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="finalrelease"></a>  CComPolyObject::FinalRelease

オブジェクトの破棄中に呼び出されると、このメソッドは、解放、[で呼び出され](#m_contained)データ メンバー。

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComPolyObject::m_contained

A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)クラスから派生したオブジェクト。

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>パラメーター

*含まれています。*  
[in]派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のすべてのインターフェイスからも、します。

### <a name="remarks"></a>Remarks

`IUnknown` 呼び出す`m_contained`集約オブジェクトの場合は、不明な外部に委任、`IUnknown`オブジェクトが集計されない場合は、このオブジェクトの。

##  <a name="queryinterface"></a>  CComPolyObject::QueryInterface

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>  
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>パラメーター

*Q*  
COM インターフェイスです。

*iid*  
[in]要求されているインターフェイスの識別子。

*ppvObject*  
[out]によって識別されるインターフェイス ポインターへのポインター *iid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObject* NULL に設定されます。

*pp*  
[out]識別されるインターフェイスへのポインター`__uuidof(Q)`します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

要求されたインターフェイスがある場合、集約オブジェクトの`IUnknown`、`QueryInterface`集計オブジェクトの独自のポインターを返します`IUnknown`し、参照カウントをインクリメントします。 それ以外の場合、このメソッド クエリ インターフェイスを介して、`CComContainedObject`データ メンバー、[で呼び出され](#m_contained)します。

##  <a name="release"></a>  CComPolyObject::Release

オブジェクトの参照カウントをデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグ ビルドで`Release`テストや診断に使用する値を返します。 非デバッグ ビルドで`Release`常に 0 を返します。

## <a name="see-also"></a>関連項目

[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)   
[クラスの概要](../../atl/atl-class-overview.md)
