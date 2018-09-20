---
title: Hstringreference::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
dev_langs:
- C++
ms.assetid: cad3d52d-cd67-4194-a270-5239b1121a09
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e369aa819c7bff372113b2e422fef2441485a85a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381376"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator== 演算子

2 つのパラメーターが等しいかどうかを示します。

## <a name="syntax"></a>構文

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*できます、 **HStringReference**オブジェクトまたは HSTRING ハンドル。

*rhs*<br/>
比較する 2 番目のパラメーター。  *rhs*できます、 **HStringReference**オブジェクトまたは HSTRING ハンドル。

## <a name="return-value"></a>戻り値

**true**場合、 *lhs*と*rhs*パラメーターは、それ以外の**false**します。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HStringReference クラス](../windows/hstringreference-class.md)