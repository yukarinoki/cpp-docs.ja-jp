---
title: Hstring::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
dev_langs:
- C++
ms.assetid: 77ff4c1a-e62a-4256-bf9d-0f017137c630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dee6fd7b50d116264ea6b8b9a6b7bac3936e95cf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413719"
---
# <a name="hstringoperator-operator"></a>HString::Operator== 演算子

2 つのパラメーターが等しいかどうかを示します。

## <a name="syntax"></a>構文

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*できます、 **HString**または`HStringReference`オブジェクト、または、HSTRING ハンドル。

*rhs*<br/>
比較する 2 番目のパラメーター。*rhs*できます、 **HString**または`HStringReference`オブジェクト、または、HSTRING ハンドル。

## <a name="return-value"></a>戻り値

**true**場合、 *lhs*と*rhs*パラメーターは、それ以外の**false**します。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HString クラス](../windows/hstring-class.md)