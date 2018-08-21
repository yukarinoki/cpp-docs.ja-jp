---
title: Mutex::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ce42a1e14e3de77b8ac10c67a8f15b6ee3f080f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019957"
---
# <a name="mutexoperator-operator"></a>Mutex::operator= 演算子
割り当て (移動)、指定した**ミュー テックス**現在オブジェクト**ミュー テックス**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *h*  
 右辺値参照を**ミュー テックス**オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 現在への参照を**ミュー テックス**オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。、**移動セマンティクス**の[右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>関連項目
 [Mutex クラス](../windows/mutex-class1.md)