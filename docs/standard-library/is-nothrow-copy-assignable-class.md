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
ms.openlocfilehash: e540d6fe4c00772af01b187d24efae18fd62357f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957559"
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable クラス

スローしないことがコンパイラに判明しているコピー代入演算子が型にあるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>パラメーター

*T*照会する型。

## <a name="remarks"></a>Remarks

型述語のインスタンスは、参照型の場合は true を保持*T*場所`is_nothrow_assignable<T&, const T&>`それ以外の場合は true を保持して false を保持します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable クラス](../standard-library/is-nothrow-assignable-class.md)<br/>
