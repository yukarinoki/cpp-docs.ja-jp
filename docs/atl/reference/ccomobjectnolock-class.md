---
description: '詳細情報: CComObjectNoLock クラス'
title: CComObjectNoLock クラス
ms.date: 11/04/2016
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
ms.openlocfilehash: 97708250ecd9637c52daf5db82f39d1a12565399
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142494"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock クラス

このクラスは、 `IUnknown` 非集計オブジェクトに対してを実装しますが、コンストラクターのモジュールロック数をインクリメントしません。

## <a name="syntax"></a>構文

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>パラメーター

*常用*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラス、およびオブジェクトでサポートする他のインターフェイスから派生したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|コンストラクターです。|
|[CComObjectNoLock:: ~ CComObjectNoLock](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComObjectNoLock:: AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|
|[CComObjectNoLock:: QueryInterface](#queryinterface)|要求されたインターフェイスへのポインターを返します。|
|[CComObjectNoLock:: Release](#release)|オブジェクトの参照カウントをデクリメントします。|

## <a name="remarks"></a>解説

`CComObjectNoLock`は、非集計オブジェクトに対して[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装するという点で、 [CComObject](../../atl/reference/ccomobject-class.md)に似ています。ただし、で `CComObjectNoLock` は、コンストラクターのモジュールロックカウントはインクリメントされません。

ATL では `CComObjectNoLock` 、クラスファクトリに対して内部的にを使用します。 一般に、このクラスは直接使用しません。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomobjectnolockaddref"></a><a name="addref"></a> CComObjectNoLock:: AddRef

オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断またはテストに役立つ可能性のある値。

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="ccomobjectnolock"></a> CComObjectNoLock::CComObjectNoLock

コンストラクターです。 [CComObject](../../atl/reference/ccomobject-class.md)とは異なり、はモジュールのロックカウントをインクリメントしません。

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>パラメーター

<em>void\*</em><br/>
からこの無名パラメーターは使用されません。 これは、他のコンストラクターとの対称のために存在し `CComXXXObjectXXX` ます。

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="dtor"></a> CComObjectNoLock:: ~ CComObjectNoLock

デストラクターです。

```
~CComObjectNoLock();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し、 [FinalRelease](ccomobjectrootex-class.md#finalrelease)を呼び出します。

## <a name="ccomobjectnolockqueryinterface"></a><a name="queryinterface"></a> CComObjectNoLock:: QueryInterface

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
から要求されているインターフェイスの識別子。

*ppvObject*<br/>
入出力 *Iid* によって識別されるインターフェイスポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合、 *ppvObject* は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomobjectnolockrelease"></a><a name="release"></a> CComObjectNoLock:: Release

オブジェクトの参照カウントをデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグビルドでは、 `Release` 診断またはテストに役立つ値が返されます。 非デバッグビルドでは、は `Release` 常に0を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
