---
title: Semaphore::semaphore コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore, constructor
ms.assetid: 91c22ae7-181e-460d-ad40-70c3a53b26fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 13c0ded165e7c1510f0112d9b3b9e93f2e356775
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015599"
---
# <a name="semaphoresemaphore-constructor"></a>Semaphore::Semaphore コンストラクター
新しいインスタンスを初期化、**セマフォ**クラス。  
  
## <a name="syntax"></a>構文  
  
```cpp  
explicit Semaphore(  
   HANDLE h  
);  
  
WRL_NOTHROW Semaphore(  
   _Inout_ Semaphore&& h  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *h*  
 ハンドルまたはへの右辺値参照を**セマフォ**オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>関連項目
 [Semaphore クラス](../windows/semaphore-class.md)