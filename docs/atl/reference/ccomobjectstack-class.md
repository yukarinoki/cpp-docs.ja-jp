---
description: '詳細情報: CComObjectStack クラス'
title: CComObjectStack クラス
ms.date: 11/04/2016
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
ms.openlocfilehash: 5713601a765ad9ff1c32992d1f9c517dd86affca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142416"
---
# <a name="ccomobjectstack-class"></a>CComObjectStack クラス

このクラスは、一時 COM オブジェクトを作成し、のスケルトン実装を提供し `IUnknown` ます。

## <a name="syntax"></a>構文

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>パラメーター

*常用*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラス、およびオブジェクトでサポートする他のインターフェイスから派生したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|コンストラクターです。|
|[CComObjectStack:: ~ CComObjectStack](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComObjectStack:: AddRef](#addref)|ゼロを返します。 デバッグモードでは、はを呼び出し `_ASSERTE` ます。|
|[CComObjectStack:: QueryInterface](#queryinterface)|E_NOINTERFACE を返します。 デバッグモードでは、はを呼び出し `_ASSERTE` ます。|
|[CComObjectStack:: Release](#release)|ゼロを返します。 デバッグモードでは、はを呼び出し `_ASSERTE` ます。 ~|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComObjectStack:: m_hResFinalConstruct](#m_hresfinalconstruct)|オブジェクトの構築中に返される HRESULT を格納 `CComObjectStack` します。|

## <a name="remarks"></a>解説

`CComObjectStack` は、一時的な COM オブジェクトを作成し、オブジェクトにのスケルトンの実装を提供するために使用され `IUnknown` ます。 通常、オブジェクトは1つの関数内でローカル変数として使用されます (つまり、スタックにプッシュされます)。 関数の終了時にオブジェクトが破棄されるため、参照カウントは効率向上のためには実行されません。

次の例は、関数内で使用される COM オブジェクトを作成する方法を示しています。

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

一時オブジェクト `Tempobj` はスタックにプッシュされ、関数が終了すると自動的に消えます。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComObjectStack`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomobjectstackaddref"></a><a name="addref"></a> CComObjectStack:: AddRef

ゼロを返します。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

ゼロを返します。

### <a name="remarks"></a>解説

デバッグモードでは、はを呼び出し `_ASSERTE` ます。

## <a name="ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a> CComObjectStack::CComObjectStack

コンストラクターです。

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>解説

を呼び出し `FinalConstruct` 、 [m_hResFinalConstruct](#m_hresfinalconstruct) をによって返される HRESULT に設定し `FinalConstruct` ます。 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)から基底クラスを派生していない場合は、独自のメソッドを指定する必要があり `FinalConstruct` ます。 このデストラクターは `FinalRelease` を呼び出します。

## <a name="ccomobjectstackccomobjectstack"></a><a name="dtor"></a> CComObjectStack:: ~ CComObjectStack

デストラクターです。

```
CComObjectStack();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し、 [FinalRelease](ccomobjectrootex-class.md#finalrelease)を呼び出します。

## <a name="ccomobjectstackm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a> CComObjectStack:: m_hResFinalConstruct

オブジェクトの作成時にを呼び出すことによって返される HRESULT を格納 `FinalConstruct` `CComObjectStack` します。

```
HRESULT    m_hResFinalConstruct;
```

## <a name="ccomobjectstackqueryinterface"></a><a name="queryinterface"></a> CComObjectStack:: QueryInterface

E_NOINTERFACE を返します。

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>戻り値

E_NOINTERFACE を返します。

### <a name="remarks"></a>解説

デバッグモードでは、はを呼び出し `_ASSERTE` ます。

## <a name="ccomobjectstackrelease"></a><a name="release"></a> CComObjectStack:: Release

ゼロを返します。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

ゼロを返します。

### <a name="remarks"></a>解説

デバッグモードでは、はを呼び出し `_ASSERTE` ます。

## <a name="see-also"></a>関連項目

[CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject クラス](../../atl/reference/ccomobject-class.md)<br/>
[CComObjectGlobal クラス](../../atl/reference/ccomobjectglobal-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
