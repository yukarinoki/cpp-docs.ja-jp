---
title: SyncLockWithStatusT クラス |Microsoft Docs
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
ms.openlocfilehash: 66fd02ff9af4f7a5c1cb85b58e966622bed0060a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648692"
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
  
### <a name="parameters"></a>パラメーター  
 *SyncTraits*  
 排他的に使用できる型またはリソースの所有権を共有します。  
  
## <a name="remarks"></a>Remarks  
 排他的に使用できる型を表すか、リソースの所有権を共有します。  
  
 **SyncLockWithStatusT**クラスが実装するために使用される、[ミュー テックス](../windows/mutex-class1.md)と[セマフォ](../windows/semaphore-class.md)クラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT コンストラクター](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|新しいインスタンスを初期化、 **SyncLockWithStatusT**クラス。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT コンストラクター](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|新しいインスタンスを初期化、 **SyncLockWithStatusT**クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::GetStatus メソッド](../windows/synclockwithstatust-getstatus-method.md)|現在の待機状態を取得**SyncLockWithStatusT**オブジェクト。|  
|[SyncLockWithStatusT::IsLocked メソッド](../windows/synclockwithstatust-islocked-method.md)|示すかどうか、現在**SyncLockWithStatusT**リソースを所有するオブジェクトです。 つまり、 **SyncLockWithStatusT**オブジェクトが*ロック*します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[SyncLockWithStatusT::status_ データ メンバー](../windows/synclockwithstatust-status-data-member.md)|基になる待機操作の結果を保持するオブジェクトのロック操作が現在に基づいて後**SyncLockWithStatusT**オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)