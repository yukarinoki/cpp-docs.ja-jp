---
title: SyncLockT クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f6b27f45d3a9b9b308a56e1ac8f945969f8c49e2
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643427"
---
# <a name="synclockt-class"></a>SyncLockT クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
### <a name="parameters"></a>パラメーター  
 *SyncTraits*  
 この型は、リソースの所有権を取得できます。  
  
## <a name="remarks"></a>Remarks  
 排他的に使用できる型を表すか、リソースの所有権を共有します。  
  
 **SyncLockT**クラスの使用などの実装に役立つ、 [SRWLock](../windows/srwlock-class.md)クラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockT::SyncLockT コンストラクター](../windows/synclockt-synclockt-constructor.md)|新しいインスタンスを初期化、 **SyncLockT**クラス。|  
|[SyncLockT::~SyncLockT デストラクター](../windows/synclockt-tilde-synclockt-destructor.md)|インスタンスを初期化解除、 **SyncLockT**クラス。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockT::SyncLockT コンストラクター](../windows/synclockt-synclockt-constructor.md)|新しいインスタンスを初期化、 **SyncLockT**クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockT::IsLocked メソッド](../windows/synclockt-islocked-method.md)|示すかどうか、現在**SyncLockT**リソースを所有するオブジェクトです。 つまり、 **SyncLockT**オブジェクトが*ロック*します。|  
|[SyncLockT::Unlock メソッド](../windows/synclockt-unlock-method.md)|現在保持されているリソースの制御を解放**SyncLockT**オブジェクトが存在する場合。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[SyncLockT::sync_ データ メンバー](../windows/synclockt-sync-data-member.md)|によって表される、基になるリソースを保持、 **SyncLockT**クラス。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SyncLockT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::Details Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock クラス](../windows/srwlock-class.md)