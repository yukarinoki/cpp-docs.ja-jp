---
title: IConnectionPointContainerImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5931d12acfead0a3832e84c3008bfde2ffd4a8d6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077674"
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
