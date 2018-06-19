---
title: Mutex::operator = 演算子 |Microsoft ドキュメント
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
ms.openlocfilehash: 8791d3c947206be399f475bb8c895b2b5e032133
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875488"
---
# <a name="mutexoperator-operator"></a>Mutex::operator= 演算子
割り当て (移動)、指定されたミュー テックスは、現在のミュー テックス オブジェクトをオブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ミュー テックス オブジェクトを右辺値の参照。  
  
## <a name="return-value"></a>戻り値  
 現在のミュー テックス オブジェクトへの参照。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、**移動セマンティクス**のセクション[右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>関連項目
 [Mutex クラス](../windows/mutex-class1.md)