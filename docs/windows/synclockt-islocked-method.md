---
title: Synclockt::islocked メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 067b3763e10b2bbb310b213f7d748e953ba2a902
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888476"
---
# <a name="synclocktislocked-method"></a>SyncLockT::IsLocked メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
bool IsLocked() const;  
```  
  
## <a name="return-value"></a>戻り値  
 **true** SyncLockT オブジェクトがロックされている、それ以外の場合は**false**です。  
  
## <a name="remarks"></a>コメント  
 SyncLockT、現在、リソースを所有しているかどうかを示しますSyncLockT オブジェクトは、つまり、*ロック*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [SyncLockT クラス](../windows/synclockt-class.md)