---
title: Makeallocator::allocate メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs:
- C++
helpviewer_keywords:
- Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d0e8d387dea7687ad61d85f975d58aa47489266d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876217"
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
__forceinline void* Allocate();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合、割り当てられたメモリ; へのポインターそれ以外の場合、`nullptr`です。  
  
## <a name="remarks"></a>コメント  
 メモリが割り当てられ、現在 MakeAllocator オブジェクトに関連付けます。  
  
 割り当てられたメモリのサイズは、現在の MakeAllocator テンプレート パラメーターで指定された型のサイズです。  
  
 開発者は、異なるメモリ割り当てのモデルを実装する Allocate() メソッドのみをオーバーライドする必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [MakeAllocator クラス](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)