---
title: Modulebase::incrementobjectcount メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- IncrementObjectCount method
ms.assetid: 2d70b472-684c-4bb7-8bab-09505cfcaf28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b8ac3bcb256c4a54f3b967405e7f2c0699e715d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377183"
---
# <a name="modulebaseincrementobjectcount-method"></a>ModuleBase::IncrementObjectCount メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
virtual long IncrementObjectCount() = 0;
```

## <a name="return-value"></a>戻り値

インクリメント操作の前にカウントします。

## <a name="remarks"></a>Remarks

実装された場合、モジュールによって追跡されるオブジェクトの数をインクリメントします。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[ModuleBase クラス](../windows/modulebase-class.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)