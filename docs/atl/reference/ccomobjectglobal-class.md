---
description: '詳細情報: CComObjectGlobal クラス'
title: CComObjectGlobal クラス
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
ms.openlocfilehash: 0f79acb0fdbb43f9456e08f26875d45eec9904c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151984"
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal クラス

このクラスは、オブジェクトを含むモジュールの参照カウントを管理し `Base` ます。

## <a name="syntax"></a>構文

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>パラメーター

*常用*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラス、およびオブジェクトでサポートする他のインターフェイスから派生したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|コンストラクターです。|
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComObjectGlobal:: AddRef](#addref)|グローバルを実装 `AddRef` します。|
|[CComObjectGlobal:: QueryInterface](#queryinterface)|グローバルを実装 `QueryInterface` します。|
|[CComObjectGlobal:: Release](#release)|グローバルを実装 `Release` します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComObjectGlobal:: m_hResFinalConstruct](#m_hresfinalconstruct)|オブジェクトの構築中に返される HRESULT を格納 `CComObjectGlobal` します。|

## <a name="remarks"></a>解説

`CComObjectGlobal` オブジェクトを含むモジュールの参照カウントを管理し `Base` ます。 `CComObjectGlobal` モジュールが解放されていない限り、オブジェクトが削除されないようにします。 オブジェクトは、モジュール全体の参照カウントがゼロになった場合にのみ削除されます。

たとえば、を使用すると、 `CComObjectGlobal` クラスファクトリは、すべてのクライアントによって共有される共通のグローバルオブジェクトを保持できます。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomobjectglobaladdref"></a><a name="addref"></a> CComObjectGlobal:: AddRef

オブジェクトの参照カウントを1だけインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断とテストに役立つ可能性のある値。

### <a name="remarks"></a>解説

既定では `AddRef` 、 `_Module::Lock` はを呼び出します。ここで、 `_Module` は [CComModule](../../atl/reference/ccommodule-class.md) のグローバルインスタンス、またはそれから派生したクラスです。

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="ccomobjectglobal"></a> CComObjectGlobal::CComObjectGlobal

コンストラクターです。 を呼び出し `FinalConstruct` 、 [m_hResFinalConstruct](#m_hresfinalconstruct) をに `HRESULT` よって返されるに設定し `FinalConstruct` ます。

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>解説

[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)から基底クラスを派生していない場合は、独自のメソッドを指定する必要があり `FinalConstruct` ます。 このデストラクターは `FinalRelease` を呼び出します。

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="dtor"></a> CComObjectGlobal:: ~ CComObjectGlobal

デストラクターです。

```
CComObjectGlobal();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し、 [FinalRelease](ccomobjectrootex-class.md#finalrelease)を呼び出します。

## <a name="ccomobjectglobalm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a> CComObjectGlobal:: m_hResFinalConstruct

オブジェクトの作成時にを呼び出すことができない HRESULT を格納 `FinalConstruct` `CComObjectGlobal` します。

```
HRESULT m_hResFinalConstruct;
```

## <a name="ccomobjectglobalqueryinterface"></a><a name="queryinterface"></a> CComObjectGlobal:: QueryInterface

要求されたインターフェイスポインターへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
から要求されているインターフェイスの GUID。

*ppvObject*<br/>
入出力Iid によって識別されるインターフェイスポインターへのポインター。インターフェイスが見つからない場合は NULL。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`QueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。

## <a name="ccomobjectglobalrelease"></a><a name="release"></a> CComObjectGlobal:: Release

オブジェクトの参照カウントを1だけデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグビルドでは、 `Release` 診断とテストに役立つ可能性のある値を返します。 非デバッグビルドでは、は `Release` 常に0を返します。

### <a name="remarks"></a>解説

既定では `Release` 、 `_Module::Unlock` はを呼び出します。ここで、 `_Module` は [CComModule](../../atl/reference/ccommodule-class.md) のグローバルインスタンス、またはそれから派生したクラスです。

## <a name="see-also"></a>関連項目

[CComObjectStack クラス](../../atl/reference/ccomobjectstack-class.md)<br/>
[CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject クラス](../../atl/reference/ccomobject-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
