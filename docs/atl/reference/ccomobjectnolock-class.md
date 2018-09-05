---
title: CComObjectNoLock クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5af4f2ce063c817ee4bf0c9f8ee4fea3beffb075
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762906"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock クラス

このクラスは実装`IUnknown`の集約オブジェクトは、モジュールのロック数をコンス トラクターでインクリメントされません。

## <a name="syntax"></a>構文

```
template<class Base>  
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*  
派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)オブジェクトでサポートするその他のインターフェイスからも、します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|コンストラクターです。|
|[CComObjectNoLock:: ~ CComObjectNoLock](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|オブジェクトの参照カウントをインクリメントします。|
|[CComObjectNoLock::QueryInterface](#queryinterface)|要求されたインターフェイス ポインターを返します。|
|[CComObjectNoLock::Release](#release)|オブジェクトの参照カウントをデクリメントします。|

## <a name="remarks"></a>Remarks

`CComObjectNoLock` 似ています[CComObject](../../atl/reference/ccomobject-class.md)実装で[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)非集約オブジェクトです。 ただし、`CComObjectNoLock`増分値はモジュールのロックは、コンス トラクター内で数。

ATL を使用して`CComObjectNoLock`のクラス ファクトリを内部的にします。 一般に、このクラスを直接使用するはありません。

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h

##  <a name="addref"></a>  CComObjectNoLock::AddRef

オブジェクトの参照カウントをインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

テストや診断に使用する値。

##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock

コンストラクターです。 異なり[CComObject](../../atl/reference/ccomobject-class.md)モジュールのロック カウントを増分されません。

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>パラメーター

<em>void\*</em>  
[in]この名前のないパラメーターは使用されません。 他の対称性が存在する`CComXXXObjectXXX`コンス トラクター。

##  <a name="dtor"></a>  CComObjectNoLock:: ~ CComObjectNoLock

デストラクターです。

```
~CComObjectNoLock();
```

### <a name="remarks"></a>Remarks

割り当てられているすべてのリソースを解放[FinalRelease](ccomobjectrootex-class.md#finalrelease)します。  

##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*iid*  
[in]要求されているインターフェイスの識別子。

*ppvObject*  
[out]によって識別されるインターフェイス ポインターへのポインター *iid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObject* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="release"></a>  CComObjectNoLock::Release

オブジェクトの参照カウントをデクリメントします。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>戻り値

デバッグ ビルドで`Release`テストや診断に使用する値を返します。 非デバッグ ビルドで`Release`常に 0 を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
