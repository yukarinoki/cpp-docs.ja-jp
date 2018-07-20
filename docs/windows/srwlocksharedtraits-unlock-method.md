---
title: Srwlocksharedtraits::unlock メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 33cdead9-1900-4094-b18e-38fcf1a0bd28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 95be5ae4c9db7bff4ecbfb4705904f4e48c160e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889359"
---
# <a name="srwlocksharedtraitsunlock-method"></a>SRWLockSharedTraits::Unlock メソッド
指定した SRWLock オブジェクトの排他的に制御を解放します。  
  
## <a name="syntax"></a>構文  
  
```  
inline static void Unlock(  
   _In_ Type srwlock  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `srwlock`  
 SRWLock オブジェクトへのハンドル。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [SRWLockSharedTraits 構造体](../windows/srwlocksharedtraits-structure.md)