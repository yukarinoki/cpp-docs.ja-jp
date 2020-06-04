---
title: クラスの数
ms.date: 11/04/2016
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
ms.openlocfilehash: 9a784584179186cdf1e63c1ec43cad4d59391ec3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327635"
---
# <a name="ccomobjectglobal-class"></a>クラスの数

このクラスは、オブジェクトを含むモジュールの参照カウント`Base`を管理します。

## <a name="syntax"></a>構文

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
[CComObjectRoot または CComObjectRootEx](../../atl/reference/ccomobjectroot-class.md)から派生したクラス、およびオブジェクトでサポートする他のインターフェイスから派生したクラス。 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[グローバルなオブジェクト::CComオブジェクトグローバル](#ccomobjectglobal)|コンストラクターです。|
|[オブジェクトグローバル::~CComオブジェクトグローバル](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクトグローバル::AddRef](#addref)|グローバル`AddRef`を実装します。|
|[インターフェイスの種類](#queryinterface)|グローバル`QueryInterface`を実装します。|
|[オブジェクトグローバル::リリース](#release)|グローバル`Release`を実装します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コムオブジェクトグローバル::m_hResFinalConstruct](#m_hresfinalconstruct)|オブジェクトの構築中に返される HRESULT を`CComObjectGlobal`格納します。|

## <a name="remarks"></a>解説

`CComObjectGlobal`は、オブジェクトを含むモジュールの参照カウント`Base`を管理します。 `CComObjectGlobal`モジュールが解放されない限り、オブジェクトが削除されないことを確認します。 モジュール全体の参照カウントがゼロになった場合にのみ、オブジェクトが削除されます。

たとえば、 を`CComObjectGlobal`使用すると、クラス ファクトリは、すべてのクライアントで共有される共通のグローバル オブジェクトを保持できます。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomobjectglobaladdref"></a><a name="addref"></a>オブジェクトグローバル::AddRef

オブジェクトの参照カウントを 1 ずつインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断とテストに役立つ値。

### <a name="remarks"></a>解説

既定では`AddRef`[、CComModule](../../atl/reference/ccommodule-class.md)のグローバル インスタンスまたはそこから派生したクラス`_Module::Lock``_Module`は、 を呼び出します。

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="ccomobjectglobal"></a>グローバルなオブジェクト::CComオブジェクトグローバル

コンストラクターです。 m_hResFinalConstruct`FinalConstruct`を呼び出し`HRESULT`、[次に、](#m_hresfinalconstruct)によって返される`FinalConstruct`値に設定します。

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>解説

[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)から基本クラスを派生していない場合は、独自`FinalConstruct`のメソッドを指定する必要があります。 このデストラクターは `FinalRelease` を呼び出します。

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="dtor"></a>オブジェクトグローバル::~CComオブジェクトグローバル

デストラクターです。

```
CComObjectGlobal();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し[、FinalRelease](ccomobjectrootex-class.md#finalrelease)を呼び出します。

## <a name="ccomobjectglobalm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>コムオブジェクトグローバル::m_hResFinalConstruct

オブジェクトの構築中に呼`FinalConstruct`び出しを`CComObjectGlobal`行った HRESULT を格納します。

```
HRESULT m_hResFinalConstruct;
```

## <a name="ccomobjectglobalqueryinterface"></a><a name="queryinterface"></a>インターフェイスの種類

要求されたインターフェイス ポインターへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]要求されているインターフェイスの GUID。

*オブジェクト*<br/>
[アウト]iid で識別されるインターフェイス ポインタへのポインタ。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`QueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。

## <a name="ccomobjectglobalrelease"></a><a name="release"></a>オブジェクトグローバル::リリース

オブジェクトの参照カウントを 1 で減算します。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグ ビルドでは`Release`、診断とテストに役立つ値を返します。 非デバッグ ビルドでは、`Release`常に 0 を返します。

### <a name="remarks"></a>解説

既定では`Release`[、CComModule](../../atl/reference/ccommodule-class.md)のグローバル インスタンスまたはそこから派生したクラス`_Module::Unlock``_Module`は、 を呼び出します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomobjectstack-class.md)<br/>
[クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[クラス](../../atl/reference/ccomobject-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
