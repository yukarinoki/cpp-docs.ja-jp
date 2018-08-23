---
title: Hstring::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
dev_langs:
- C++
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9294650db7a1b18c2542603988952a80b3f1905d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598546"
---
# <a name="hstringoperator-operator"></a>HString::Operator= 演算子

別の値を移動**HString**現在オブジェクト**HString**オブジェクト。

## <a name="syntax"></a>構文

```cpp
HString& operator=(HString&& other) throw()  
```

### <a name="parameters"></a>パラメーター

*other*  
既存の**HString**オブジェクト。

## <a name="remarks"></a>Remarks

既存の値*他*現在にオブジェクトがコピーされます**HString**オブジェクト、し、*他*オブジェクトが破棄されます。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HString クラス](../windows/hstring-class.md)