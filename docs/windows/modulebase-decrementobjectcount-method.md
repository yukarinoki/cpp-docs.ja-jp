---
title: Modulebase::decrementobjectcount メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- DecrementObjectCount method
ms.assetid: a016fb07-a36e-40cd-bc7b-8f6e85e256e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d90e0560ee5aa7036947e0d81f2d608b5a68bf75
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375920"
---
# <a name="modulebasedecrementobjectcount-method"></a>ModuleBase::DecrementObjectCount メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
virtual long DecrementObjectCount() = 0;
```

## <a name="return-value"></a>戻り値

デクリメント操作の前にカウントします。

## <a name="remarks"></a>Remarks

実装された場合、デクリメント オブジェクトの数によって追跡モジュール。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[ModuleBase クラス](../windows/modulebase-class.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)