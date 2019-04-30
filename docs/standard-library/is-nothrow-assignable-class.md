---
title: is_nothrow_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_assignable
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
ms.openlocfilehash: c59c3623f9c9548a7b7e59d0c56a2acd4d3883a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383621"
---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable クラス

値かどうかをテスト*から*型に割り当てることができます*に*型および割り当てがスローしないと判明します。

## <a name="syntax"></a>構文

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>パラメーター

*To*<br/>
代入を受け取るオブジェクトの型。

*From*<br/>
値を渡すオブジェクトの型。

## <a name="remarks"></a>Remarks

式 `declval<To>() = declval<From>()` は正しい形式である必要があり、スローしないことがコンパイラに判明している必要があります。 両方*から*と*に*完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
