---
title: SyncLockWithStatusT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 51e5a66358890fc20731fb5cb657616484e19db4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890981"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `SyncTraits`  
 排他的に実行できる型またはリソースの所有権を共有します。  
  
## <a name="remarks"></a>コメント  
 排他的に実行できる型を表すまたはリソースの所有権を共有します。  
  
 SyncLockWithStatusT クラスが実装に使用される、[ミュー テックス](../windows/mutex-class1.md)と[セマフォ](../windows/semaphore-class.md)クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT コンストラクター](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|SyncLockWithStatusT クラスの新しいインスタンスを初期化します。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT コンストラクター](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|SyncLockWithStatusT クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::GetStatus メソッド](../windows/synclockwithstatust-getstatus-method.md)|SyncLockWithStatusT、現在の待機の状態を取得します。|  
|[SyncLockWithStatusT::IsLocked メソッド](../windows/synclockwithstatust-islocked-method.md)|SyncLockWithStatusT、現在、リソースを所有しているかどうかを示しますSyncLockWithStatusT オブジェクトは、つまり、*ロック*です。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::status_ データ メンバー](../windows/synclockwithstatust-status-data-member.md)|保持しますが、基になる結果にロック操作の後に操作を待機するオブジェクトは、現在の SyncLockWithStatusT オブジェクトに基づいています。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)