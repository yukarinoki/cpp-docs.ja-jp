---
title: クラス
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
ms.openlocfilehash: 8c3fd56635da8b80c84f6151009586b7bd2b4341
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327572"
---
# <a name="ccomobjectstack-class"></a>クラス

このクラスは、一時的な COM オブジェクトを作成し、 のスケルトン`IUnknown`実装を提供します。

## <a name="syntax"></a>構文

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
[CComObjectRoot または CComObjectRootEx](../../atl/reference/ccomobjectroot-class.md)から派生したクラス、およびオブジェクトでサポートする他のインターフェイスから派生したクラス。 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[スタック::CComオブジェクトスタック](#ccomobjectstack)|コンストラクターです。|
|[スタック:~CComオブジェクトスタック](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[スタック::AddRef](#addref)|ゼロを返します。 デバッグ モードでは、`_ASSERTE`を呼び出します。|
|[クエリインターフェイス](#queryinterface)|E_NOINTERFACEを返します。 デバッグ モードでは、`_ASSERTE`を呼び出します。|
|[CComオブジェクトスタック::リリース](#release)|ゼロを返します。 デバッグ モードでは、`_ASSERTE`を呼び出します。 ~|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[スタック:m_hResFinalConstruct](#m_hresfinalconstruct)|オブジェクトの構築中に返される HRESULT を`CComObjectStack`格納します。|

## <a name="remarks"></a>解説

`CComObjectStack`は、一時的な COM オブジェクトを作成し、オブジェクトに`IUnknown`のスケルトン実装を提供するために使用されます。 通常、オブジェクトは 1 つの関数内のローカル変数として使用されます (つまり、スタックにプッシュされます)。 関数が終了するとオブジェクトが破棄されるため、参照カウントは実行されず、効率が向上します。

関数内で使用される COM オブジェクトを作成する方法を次の例に示します。

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

一時オブジェクト`Tempobj`はスタックにプッシュされ、関数が終了すると自動的に消えます。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComObjectStack`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomobjectstackaddref"></a><a name="addref"></a>スタック::AddRef

ゼロを返します。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

ゼロを返します。

### <a name="remarks"></a>解説

デバッグ モードでは、`_ASSERTE`を呼び出します。

## <a name="ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a>スタック::CComオブジェクトスタック

コンストラクターです。

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>解説

m_hResFinalConstruct`FinalConstruct`を呼び出し、その後、m_hResFinalConstruct`FinalConstruct`が返す HRESULT[に設定](#m_hresfinalconstruct)します。 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)から基本クラスを派生していない場合は、独自`FinalConstruct`のメソッドを指定する必要があります。 このデストラクターは `FinalRelease` を呼び出します。

## <a name="ccomobjectstackccomobjectstack"></a><a name="dtor"></a>スタック:~CComオブジェクトスタック

デストラクターです。

```
CComObjectStack();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し[、FinalRelease](ccomobjectrootex-class.md#finalrelease)を呼び出します。

## <a name="ccomobjectstackm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>スタック:m_hResFinalConstruct

オブジェクトの構築中に呼び`FinalConstruct`出しから返`CComObjectStack`される HRESULT を格納します。

```
HRESULT    m_hResFinalConstruct;
```

## <a name="ccomobjectstackqueryinterface"></a><a name="queryinterface"></a>クエリインターフェイス

E_NOINTERFACEを返します。

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>戻り値

E_NOINTERFACEを返します。

### <a name="remarks"></a>解説

デバッグ モードでは、`_ASSERTE`を呼び出します。

## <a name="ccomobjectstackrelease"></a><a name="release"></a>CComオブジェクトスタック::リリース

ゼロを返します。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

ゼロを返します。

### <a name="remarks"></a>解説

デバッグ モードでは、`_ASSERTE`を呼び出します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[クラス](../../atl/reference/ccomobject-class.md)<br/>
[クラスの数](../../atl/reference/ccomobjectglobal-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
