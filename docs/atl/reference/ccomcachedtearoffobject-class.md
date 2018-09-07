---
title: CComCachedTearOffObject クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a6835cb1f8fb6365149b91c30881b4966b4b644
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765659"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject クラス

このクラスは実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)ティアオフ インターフェイス。

## <a name="syntax"></a>構文

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>パラメーター

`contained`  
ティアオフ クラスから派生した`CComTearOffObjectBase`ティアオフ オブジェクトをサポートする場合、インターフェイスです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|コンストラクターです。|
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComCachedTearOffObject::AddRef](#addref)|参照カウントをインクリメントする`CComCachedTearOffObject`オブジェクト。|
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|呼び出し、 `m_contained::FinalConstruct` (ティアオフ クラスのメソッド)。|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|呼び出し、 `m_contained::FinalRelease` (ティアオフ クラスのメソッド)。|
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|ポインターを返します、`IUnknown`の`CComCachedTearOffObject`オブジェクト、または、ティアオフ クラスで要求されたインターフェイス (クラス`contained`)。|
|[CComCachedTearOffObject::Release](#release)|参照カウントをデクリメントを`CComCachedTearOffObject`オブジェクトし、参照カウントが 0 の場合は、破棄されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComCachedTearOffObject::m_contained](#m_contained)|A`CComContainedObject`ティアオフ クラスから派生したオブジェクト (クラス`contained`)。|

## <a name="remarks"></a>Remarks

`CComCachedTearOffObject` 実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)ティアオフ インターフェイス。 このクラスとは異なります`CComTearOffObject`で`CComCachedTearOffObject`独自`IUnknown`所有者オブジェクトの別、 `IUnknown` (所有者は、ティアオフが作成される対象のオブジェクト)。 `CComCachedTearOffObject` 独自に維持で参照カウントの`IUnknown`し、参照カウントがゼロ自体を削除します。 ただし、そのティアオフのいずれかを照会する場合は、インターフェイス、所有者オブジェクトの参照カウント`IUnknown`が増分されます。

場合、`CComCachedTearOffObject`オブジェクト、ティアオフを実装することを既にインスタンス化、およびティアオフ インターフェイスは、ここでも、同じクエリ`CComCachedTearOffObject`オブジェクトが再利用します。 これに対して、ティアオフ インターフェイスによって実装を`CComTearOffObject`、所有者オブジェクトを通じてをもう一度照会別`CComTearOffObject`がインスタンス化されます。

所有者クラスを実装する必要があります`FinalRelease`と呼び出し`Release`でキャッシュされた`IUnknown`の`CComCachedTearOffObject`、参照カウントがデクリメントされます。 これにより、`CComCachedTearOffObject`の`FinalRelease`に呼び出され、ティアオフを削除します。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h

##  <a name="addref"></a>  CComCachedTearOffObject::AddRef

参照カウントをインクリメント、`CComCachedTearOffObject`を 1 つのオブジェクト。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断に役立ちますし、テスト可能性のある値。

##  <a name="ccomcachedtearoffobject"></a>  CComCachedTearOffObject::CComCachedTearOffObject

コンストラクターです。

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*現在価値*  
[in]ポインター、`IUnknown`の`CComCachedTearOffObject`します。

### <a name="remarks"></a>Remarks

初期化します、`CComContainedObject`メンバー、[で呼び出され](#m_contained)します。

##  <a name="dtor"></a>  CComCachedTearOffObject:: ~ CComCachedTearOffObject

デストラクターです。

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>Remarks

割り当てられているすべてのリソースを解放[FinalRelease](#finalrelease)します。

##  <a name="finalconstruct"></a>  CComCachedTearOffObject::FinalConstruct

呼び出し`m_contained::FinalConstruct`を作成する`m_contained`、 `CComContainedObject` <  `contained`> ティアオフ クラスによって実装されるインターフェイスへのアクセスに使用されるオブジェクト。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="finalrelease"></a>  CComCachedTearOffObject::FinalRelease

呼び出し`m_contained::FinalRelease`を解放する`m_contained`、 `CComContainedObject` <  `contained`> オブジェクト。

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComCachedTearOffObject::m_contained

A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)ティアオフ クラスから派生したオブジェクト。

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>パラメーター

*含まれています。*  
[in]ティアオフ クラスから派生した`CComTearOffObjectBase`ティアオフ オブジェクトをサポートする場合、インターフェイスです。

### <a name="remarks"></a>Remarks

メソッド`m_contained`継承ではキャッシュされたティアオフ オブジェクトのティアオフ クラスで、ティアオフ インターフェイスにアクセスするため`QueryInterface`、 `FinalConstruct`、および`FinalRelease`します。

##  <a name="queryinterface"></a>  CComCachedTearOffObject::QueryInterface

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*iid*  
[in]要求されているインターフェイスの GUID です。

*ppvObject*  
[out]によって識別されるインターフェイス ポインターへのポインター *iid*インターフェイスが見つからない場合は null です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

要求されたインターフェイスがある場合`IUnknown`へのポインターを返します、`CComCachedTearOffObject`の独自`IUnknown`し、参照カウントをインクリメントします。 それ以外の場合、ティアオフ クラスを使用してインターフェイスを照会、 [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface)から継承されたメソッド`CComObjectRootEx`します。  

##  <a name="release"></a>  CComCachedTearOffObject::Release

参照カウントを 1 デクリメントし、参照カウントが 0 の場合は、削除、`CComCachedTearOffObject`オブジェクト。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

非デバッグ ビルドで常に 0 を返します。 デバッグ ビルドでは、テストや診断に使用する値を返します。

## <a name="see-also"></a>関連項目

[CComTearOffObject クラス](../../atl/reference/ccomtearoffobject-class.md)   
[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
