---
title: IConnectionPointContainerImpl クラス
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
ms.openlocfilehash: 06baa4dac3248d783648b8ce37e51250e0de2498
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275517"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl クラス

このクラスのコレクションを管理する接続ポイント コンテナー [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)オブジェクト。

## <a name="syntax"></a>構文

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IConnectionPointContainerImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|接続可能オブジェクトでサポートされている接続ポイントを反復処理する列挙子を作成します。|
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|指定の IID をサポートするコネクション ポイントへのインターフェイス ポインターを取得します。|

## <a name="remarks"></a>Remarks

`IConnectionPointContainerImpl` コレクションを管理する接続ポイント コンテナーを実装する[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)オブジェクト。 `IConnectionPointContainerImpl` 接続可能なオブジェクトに関する詳細を取得するクライアントが呼び出すことができる 2 つの方法があります。

- `EnumConnectionPoints` クライアントは、オブジェクトがサポートをどの送信インターフェイスを決定できます。

- `FindConnectionPoint` クライアントは、オブジェクトが特定の送信インターフェイスをサポートしているかどうかを判断できます。

ATL でコネクション ポイントの使用方法の詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints

接続可能オブジェクトでサポートされている接続ポイントを反復処理する列挙子を作成します。

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>Remarks

参照してください[IConnectionPointContainer::EnumConnectionPoints](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) Windows SDK にします。

##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint

指定の IID をサポートするコネクション ポイントへのインターフェイス ポインターを取得します。

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>Remarks

参照してください[IConnectionPointContainer::FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) Windows SDK にします。

## <a name="see-also"></a>関連項目

[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
