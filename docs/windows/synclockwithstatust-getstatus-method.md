---
title: Synclockwithstatust::getstatus メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4677239bbcaff0c72eb11ade259f47531a616f19
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649637"
---
# <a name="synclockwithstatustgetstatus-method"></a>SyncLockWithStatusT::GetStatus メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>戻り値  
 基づくオブジェクトの待機操作の結果、 **SyncLockWithStatusT**クラスなど、[ミュー テックス](../windows/mutex-class1.md)または[セマフォ](../windows/semaphore-class.md)します。 ゼロ (0) では、待機操作にはシグナルの状態が返されることを示しますそれ以外の場合、別の状態が発生しました、タイムアウト値が経過した場合など。  
  
## <a name="remarks"></a>Remarks  
 現在の待機状態を取得**SyncLockWithStatusT**オブジェクト。  
  
 GetStatus() 関数は、基になる値を取得[status _](../windows/synclockwithstatust-status-data-member.md)データ メンバー。 基づくオブジェクト、 **SyncLockWithStatusT**クラスは、ロック操作を実行、使用可能になるオブジェクトのオブジェクトが最初に待機します。 待機操作の結果は、`status_`データ メンバー。 可能な値、`status_`データ メンバーは、待機操作の戻り値。 詳細については、の戻り値を参照してください、 `WaitForSingleObjectEx()` MSDN ライブラリ内の関数。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)