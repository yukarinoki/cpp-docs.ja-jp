---
title: Mutex::mutex コンス トラクター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb7782e44fc8598ca3b806ef922f8d0840765e28
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876457"
---
# <a name="mutexmutex-constructor"></a>Mutex::Mutex コンストラクター
Mutex クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit Mutex(  
   HANDLE h  
);  
  
Mutex(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ハンドル、またはハンドル、ミュー テックス オブジェクトへの右辺値参照。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターは、指定されたハンドルからミュー テックス オブジェクトを初期化します。 2 番目のコンス トラクターは指定のハンドルからミュー テックス オブジェクトを初期化し、現在ミュー テックス オブジェクトにミュー テックスの所有権を移動します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>関連項目
 [Mutex クラス](../windows/mutex-class1.md)