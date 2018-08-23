---
title: Makeallocator::allocate メソッド |Microsoft Docs
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
ms.openlocfilehash: 4422dea0b0bfb07904d0c4defad8f33281a51bec
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609863"
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
__forceinline void* Allocate();
```

## <a name="return-value"></a>戻り値

成功した場合、割り当てられたメモリ; へのポインターそれ以外の場合、 **nullptr**します。

## <a name="remarks"></a>Remarks

メモリを割り当て、現在のそれに**MakeAllocator**オブジェクト。

割り当てられたメモリのサイズは、現在指定された型のサイズ**MakeAllocator**テンプレート パラメーター。

だけをオーバーライドする必要がある開発者、 **Allocate()** さまざまなメモリの割り当てモデルを実装するメソッド。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[MakeAllocator クラス](../windows/makeallocator-class.md)  
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)