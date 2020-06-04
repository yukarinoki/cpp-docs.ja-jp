---
title: クラスをコンテナーします。
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
ms.openlocfilehash: f6009a1341d6715d6d2f170d3ff2aa1aa4ffcb96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329863"
---
# <a name="iconnectionpointcontainerimpl-class"></a>クラスをコンテナーします。

このクラスは[、IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)オブジェクトのコレクションを管理するためのコネクション ポイント コンテナーを実装します。

## <a name="syntax"></a>構文

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IConnectionPointContainerImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#enumconnectionpoints)|接続可能オブジェクトでサポートされているコネクション ポイントを反復処理する列挙子を作成します。|
|[をクリックします。](#findconnectionpoint)|指定された IID をサポートするコネクション ポイントへのインターフェイス ポインターを取得します。|

## <a name="remarks"></a>解説

`IConnectionPointContainerImpl`オブジェクトのコレクションを管理するためのコネクション ポイント コンテナー[を](../../atl/reference/iconnectionpointimpl-class.md)実装します。 `IConnectionPointContainerImpl`には、接続可能オブジェクトに関する詳細情報を取得するためにクライアントが呼び出すことができる 2 つのメソッドがあります。

- `EnumConnectionPoints`クライアントは、オブジェクトがサポートする発信インターフェイスを決定できます。

- `FindConnectionPoint`クライアントは、オブジェクトが特定の発信インターフェイスをサポートしているかどうかを判断できます。

ATL でのコネクション ポイントの使用については、記事「[接続ポイント](../../atl/atl-connection-points.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="iconnectionpointcontainerimplenumconnectionpoints"></a><a name="enumconnectionpoints"></a>をクリックします。

接続可能オブジェクトでサポートされているコネクション ポイントを反復処理する列挙子を作成します。

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>解説

「Windows SDK の I[接続ポイントコンテナ::列挙接続ポイント](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints)」を参照してください。

## <a name="iconnectionpointcontainerimplfindconnectionpoint"></a><a name="findconnectionpoint"></a>をクリックします。

指定された IID をサポートするコネクション ポイントへのインターフェイス ポインターを取得します。

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>解説

次[を](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint)参照してください。

## <a name="see-also"></a>関連項目

[コンテナ](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
