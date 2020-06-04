---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: de7528d3972991c233ee4b9037f609b89d0f7434
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327320"
---
# <a name="ccomtearoffobject-class"></a>クラス

このクラスは、ティアオフ インターフェイスを実装します。

## <a name="syntax"></a>構文

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
ティアオフ クラスの派生`CComTearOffObjectBase`クラスと、ティアオフ オブジェクトでサポートするインターフェイス。

ATL は、そのティアオフ インターフェイスを 2 つの`CComTearOffObjectBase`フェーズで実装します。 `QueryInterface` `CComTearOffObject` [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[オブジェクト::コムティアオフオブジェクト](#ccomtearoffobject)|コンストラクターです。|
|[オブジェクト::~コムティテオフオブジェクト](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクト::AddRef](#addref)|オブジェクトの参照カウントを`CComTearOffObject`インクリメントします。|
|[オブジェクト::クエリインターフェイス](#queryinterface)|ティアオフ クラスまたは所有者クラスで要求されたインターフェイスへのポインターを返します。|
|[オブジェクト::リリース](#release)|オブジェクトの参照カウントを`CComTearOffObject`減算し、破棄します。|

### <a name="ccomtearoffobjectbase-methods"></a>メソッド

|||
|-|-|
|[オブジェクトベース](#ccomtearoffobjectbase)|コンストラクターです。|

### <a name="ccomtearoffobjectbase-data-members"></a>データ メンバー

|||
|-|-|
|[m_pOwner](#m_powner)|所有者クラスから`CComObject`派生したポインター。|

## <a name="remarks"></a>解説

`CComTearOffObject`は、そのインターフェイスが照会されるときにのみインスタンス化される個別のオブジェクトとして、ティアオフ インターフェイスを実装します。 ティアオフは、参照カウントが 0 になると削除されます。 通常、ティアオフを使用するとメイン オブジェクトのすべてのインスタンスで vtable ポインターが保存されるため、使用されないインターフェイスのティアオフ インターフェイスを構築します。

ティアオフ オブジェクトでサポートするインターフェイスから、および`CComTearOffObjectBase`ティアオフ オブジェクトがサポートするインターフェイスからティアオフを実装するクラスを派生させる必要があります。 `CComTearOffObjectBase`は、所有者クラスとスレッド モデルでテンプレート化されます。 オーナー クラスは、ティアオフが実装されているオブジェクトのクラスです。 スレッド モデルを指定しない場合は、既定のスレッド モデルが使用されます。

ティアオフ クラスの COM マップを作成する必要があります。 ATL がティアオフをインスタンス化すると、 または`CComTearOffObject<CYourTearOffClass>``CComCachedTearOffObject<CYourTearOffClass>`が作成されます。

たとえば、BEEPER サンプルでは、`CBeeper2`クラスはティアオフ クラスで、`CBeeper`クラスは所有者クラスです。

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`Base`

`CComTearOffObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomtearoffobjectaddref"></a><a name="addref"></a>オブジェクト::AddRef

オブジェクトの参照カウントを`CComTearOffObject`1 ずつインクリメントします。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>戻り値

診断とテストに役立つ値。

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="ccomtearoffobject"></a>オブジェクト::コムティアオフオブジェクト

コンストラクターです。

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
[in]`CComObject<Owner>`オブジェクトへのポインターに変換されるポインター。

### <a name="remarks"></a>解説

所有者の参照カウントを 1 ずつインクリメントします。

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="dtor"></a>オブジェクト::~コムティテオフオブジェクト

デストラクターです。

```
~CComTearOffObject();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放し、FinalRelease を呼び出し、モジュールロックカウントをデクリメントします。

## <a name="ccomtearoffobjectccomtearoffobjectbase"></a><a name="ccomtearoffobjectbase"></a>オブジェクト:::コムティアオフオブジェクトベース

コンストラクターです。

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>解説

[m_pOwner](#m_powner)メンバーを NULL に初期化します。

## <a name="ccomtearoffobjectm_powner"></a><a name="m_powner"></a>コムティアオフオブジェクト::m_pOwner

*所有者*から派生した[CComObject](../../atl/reference/ccomobject-class.md)オブジェクトへのポインター。

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>パラメーター

*所有者*<br/>
[in]ティアオフが実装されているクラス。

### <a name="remarks"></a>解説

構築中にポインターが NULL に初期化されます。

## <a name="ccomtearoffobjectqueryinterface"></a><a name="queryinterface"></a>オブジェクト::クエリインターフェイス

要求されたインターフェイスへのポインターを取得します。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]要求されているインターフェイスの IID。

*オブジェクト*<br/>
[アウト]*iid*で識別されるインターフェイス ポインタへのポインタ、 またはインターフェイスが見つからない場合は NULL。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

最初にティアオフ クラスのインターフェイスを照会します。 インターフェイスが存在しない場合は、所有者オブジェクトのインターフェイスを照会します。 要求されたインターフェイスが`IUnknown`の場合は`IUnknown`、 所有者の を返します。

## <a name="ccomtearoffobjectrelease"></a><a name="release"></a>オブジェクト::リリース

参照カウントを 1 つ減算し、参照カウントが 0 の場合は`CComTearOffObject`を削除します。

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>戻り値

非デバッグ ビルドでは、常にゼロを返します。 デバッグ ビルドでは、診断やテストに役立つ値を返します。

## <a name="see-also"></a>関連項目

[クラスをキャッシュします。](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
