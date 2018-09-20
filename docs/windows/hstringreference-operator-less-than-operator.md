---
title: Hstringreference::operator&lt;演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs:
- C++
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 17acdca8af1250b1f88fa8a6858ffa1854f8ca8c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426407"
---
# <a name="hstringreferenceoperatorlt-operator"></a>Hstringreference::operator&lt;演算子

最初のパラメーターがかどうかが 2 番目のパラメーターを未満を示します。

## <a name="syntax"></a>構文

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()  
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*への参照を指定できます、 **HStringReference**します。

*rhs*<br/>
比較する 2 番目のパラメーター。  *rhs*への参照を指定できます、 **HStringReference**します。

## <a name="return-value"></a>戻り値

**true**場合、 *lhs*パラメーターより小さい*rhs*パラメーター、それ以外の**false**します。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HStringReference クラス](../windows/hstringreference-class.md)