---
title: Hstring::operator! = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
dev_langs:
- C++
ms.assetid: dcdd2aca-e7d6-4bf1-b2de-03efbb430a93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 96131bc566271de9d99d1530ffb407c0870c71a7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604326"
---
# <a name="hstringoperator-operator"></a>HString::Operator!= 演算子

2 つのパラメーターが異なるかどうかを示します。

## <a name="syntax"></a>構文

```cpp
inline bool operator!=( const HString& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HStringReference& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HStringReference& rhs) throw()

inline bool operator!=( const HSTRING& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>パラメーター

*lhs*  
比較する最初のパラメーター。 *lhs*できます、 **HString**または`HStringReference`オブジェクト、または、HSTRING ハンドル。

*rhs*  
比較する 2 番目のパラメーター。*rhs*できます、 **HString**または`HStringReference`オブジェクト、または、HSTRING ハンドル。

## <a name="return-value"></a>戻り値

**true**場合、 *lhs*と*rhs*パラメーターが、それ以外の**false**します。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HString クラス](../windows/hstring-class.md)