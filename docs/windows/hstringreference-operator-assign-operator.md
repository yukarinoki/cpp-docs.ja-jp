---
title: Hstringreference::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7045229cc15304a88253f97e1ad3c9f171f139a0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597129"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= 演算子

別の値を移動**HStringReference**現在オブジェクト**HStringReference**オブジェクト。

## <a name="syntax"></a>構文

```cpp
HStringReference& operator=(HStringReference&& other) throw()  
```

### <a name="parameters"></a>パラメーター

*other*  
既存の**HStringReference**オブジェクト。

## <a name="remarks"></a>Remarks

既存の値*他*現在にオブジェクトがコピーされます**HStringReference**オブジェクト、し、*他*オブジェクトが破棄されます。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HStringReference クラス](../windows/hstringreference-class.md)