---
title: Synclockwithstatust::getstatus メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 03addd8d89c54eddb5deb721ab47d46e8b945edd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889763"
---
# <a name="synclockwithstatustgetstatus-method"></a>SyncLockWithStatusT::GetStatus メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>戻り値  
 オブジェクトに基づいている SyncLockWithStatusT クラスなどの待機操作の結果、[ミュー テックス](../windows/mutex-class1.md)または[セマフォ](../windows/semaphore-class.md)です。 ゼロ (0) では、待機操作によって返されたシグナルの状態であることを示しますそれ以外の場合、別の状態が発生しました、タイムアウト値が経過した場合などです。  
  
## <a name="remarks"></a>コメント  
 SyncLockWithStatusT、現在の待機の状態を取得します。  
  
 GetStatus() 関数が、基になる値を取得[status _](../windows/synclockwithstatust-status-data-member.md)データ メンバーです。 SyncLockWithStatusT クラスに基づいてオブジェクトは、ロック操作を実行するときに使用可能になるオブジェクトのオブジェクトが最初に待機します。 待機操作の結果が格納されている、`status_`データ メンバーです。 有効な値、`status_`データ メンバーは、待機操作の戻り値。 詳細については、の戻り値を参照してください、 **WaitForSingleObjectEx()** MSDN ライブラリ内の関数。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)