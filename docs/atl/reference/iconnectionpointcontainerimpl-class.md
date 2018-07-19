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
ms.openlocfilehash: d70989be8e8535336c831cb59fb9422c6e2c63e0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886233"
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
 *T*  
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
 参照してください[IConnectionPointContainer::EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460) Windows SDK にします。  
  
##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint  
 指定の IID をサポートするコネクション ポイントへのインターフェイス ポインターを取得します。  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [クラスの概要](../../atl/atl-class-overview.md)
