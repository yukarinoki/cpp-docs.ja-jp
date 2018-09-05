---
title: CComTearOffObject クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3814dacff2861bf78800adb8a019b696ce2756b7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752763"
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject クラス

このクラスは、ティアオフ インターフェイスを実装します。

## <a name="syntax"></a>構文

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*  
ティアオフ クラスから派生した`CComTearOffObjectBase`ティアオフ オブジェクトをサポートする場合、インターフェイスです。

ATL は、2 つのフェーズでそのティアオフ インターフェイスを実装する —、`CComTearOffObjectBase`メソッドは、参照カウントを処理および`QueryInterface`、中に`CComTearOffObject`実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|コンストラクターです。|
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComTearOffObject::AddRef](#addref)|参照カウントをインクリメントする`CComTearOffObject`オブジェクト。|
|[CComTearOffObject::QueryInterface](#queryinterface)|ティアオフ クラスまたは所有者クラスのいずれかで要求されたインターフェイスへのポインターを返します。|
|[CComTearOffObject::Release](#release)|参照カウントをデクリメントを`CComTearOffObject`オブジェクトし、それを破棄します。|

### <a name="ccomtearoffobjectbase-methods"></a>ティアオフ メソッド

|||
|-|-|
|[ティアオフ](#ccomtearoffobjectbase)|コンストラクターです。|

### <a name="ccomtearoffobjectbase-data-members"></a>ティアオフ データ メンバー

|||
|-|-|
|[m_pOwner](#m_powner)|ポインター、`CComObject`所有者クラスから派生します。|

## <a name="remarks"></a>Remarks

`CComTearOffObject` そのインターフェイスがクエリされるときにのみインスタンス化される個別のオブジェクトとしてティアオフ インターフェイスを実装します。 参照カウントが 0 になるときに、ティアオフは削除されます。 通常、使用頻度は、ティアオフを使用して、主要なオブジェクトのすべてのインスタンスで vtable のポインターが節約されるため、インターフェイスのため、ティアオフ インターフェイスを作成します。

ティアオフから実装するクラスを派生させる必要があります`CComTearOffObjectBase`とどのインターフェイスをサポートする、ティアオフ オブジェクトをするからです。 `CComTearOffObjectBase` 所有者クラスおよびスレッド モデルでテンプレート化されます。 所有者クラスは、対象のティアオフが実装されているオブジェクトのクラスです。 スレッド モデルを指定しない場合は、既定のスレッド モデルが使用されます。

ティアオフ クラスの COM マップを作成する必要があります。 ティアオフ ATL がインスタンス化、ときに作成されます`CComTearOffObject<CYourTearOffClass>`または`CComCachedTearOffObject<CYourTearOffClass>`します。

たとえば、サンプルでは、BEEPER、`CBeeper2`クラスは、ティアオフ クラスと`CBeeper`クラスは、所有者クラス。

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComTearOffObject`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h

##  <a name="addref"></a>  CComTearOffObject::AddRef

参照カウントをインクリメント、`CComTearOffObject`を 1 つのオブジェクト。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断に役立ちますし、テスト可能性のある値。

##  <a name="ccomtearoffobject"></a>  CComTearOffObject::CComTearOffObject

コンストラクターです。

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*現在価値*  
[in]ポインターへのポインターに変換される、`CComObject<Owner>`オブジェクト。

### <a name="remarks"></a>Remarks

いずれかで所有者の参照カウントをインクリメントします。

##  <a name="dtor"></a>  CComTearOffObject:: ~ CComTearOffObject

デストラクターです。

```
~CComTearOffObject();
```

### <a name="remarks"></a>Remarks

割り当てられているすべてのリソースを解放、デクリメントし、FinalRelease モジュールを呼び出してロック カウントします。

##  <a name="ccomtearoffobjectbase"></a>  CComTearOffObject::CComTearOffObjectBase

コンストラクターです。

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Remarks

初期化します、 [m_pOwner](#m_powner)メンバーを NULL にします。

##  <a name="m_powner"></a>  CComTearOffObject::m_pOwner

ポインターを[CComObject](../../atl/reference/ccomobject-class.md)から派生したオブジェクト*所有者*します。

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>パラメーター

*所有者*  
[in]ティアオフが実装されているクラスです。

### <a name="remarks"></a>Remarks

ポインターは、構築時に NULL に初期化されます。

##  <a name="queryinterface"></a>  CComTearOffObject::QueryInterface

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*iid*  
[in]要求されているインターフェイスの IID。

*ppvObject*  
[out]によって識別されるインターフェイス ポインターへのポインター *iid*インターフェイスが見つからない場合は null です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

まず、ティアオフ クラスでインターフェイスを照会します。 インターフェイスがない場合は、所有者オブジェクトのインターフェイスをクエリします。 要求されたインターフェイスがある場合`IUnknown`を返します、`IUnknown`所有者のです。

##  <a name="release"></a>  CComTearOffObject::Release

参照カウントを 1 つデクリメントし、参照カウントがゼロの場合は、削除、`CComTearOffObject`します。

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>戻り値

非デバッグ ビルドで常に 0 を返します。 デバッグ ビルドでは、テストや診断に使用する値を返します。

## <a name="see-also"></a>関連項目

[CComCachedTearOffObject クラス](../../atl/reference/ccomcachedtearoffobject-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
