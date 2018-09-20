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
ms.openlocfilehash: 933d332ce2653fd8ea907a5fafda524ae0220906
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409000"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= 演算子

別の値を移動**HStringReference**現在オブジェクト**HStringReference**オブジェクト。

## <a name="syntax"></a>構文

```cpp
HStringReference& operator=(HStringReference&& other) throw()  
```

### <a name="parameters"></a>パラメーター

*other*<br/>
既存の**HStringReference**オブジェクト。

## <a name="remarks"></a>Remarks

既存の値*他*現在にオブジェクトがコピーされます**HStringReference**オブジェクト、し、*他*オブジェクトが破棄されます。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HStringReference クラス](../windows/hstringreference-class.md)