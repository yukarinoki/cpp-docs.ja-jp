---
title: is_nothrow_copy_assignable クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90b63179156b1bd3d9f2dc1594f51bfa10586522
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102170"
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable クラス

スローしないことがコンパイラに判明しているコピー代入演算子が型にあるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

## <a name="remarks"></a>Remarks

型述語のインスタンスは、参照型の場合は true を保持*T*場所`is_nothrow_assignable<T&, const T&>`それ以外の場合は true を保持して false を保持します。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable クラス](../standard-library/is-nothrow-assignable-class.md)<br/>
