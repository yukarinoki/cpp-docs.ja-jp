---
title: is_nothrow_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_assignable
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
ms.openlocfilehash: 7130079ff58820ec5a8893fd248c5b98fc10c93c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222369"
---
# <a name="is_nothrow_assignable-class"></a>is_nothrow_assignable クラス

型*の値を型**に*割り当てることができるかどうかをテストし、割り当てがスローしないことがわかっていることを確認します。

## <a name="syntax"></a>構文

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>パラメーター

*宛先*\
代入を受け取るオブジェクトの型。

*差出人*\
値を渡すオブジェクトの型。

## <a name="remarks"></a>解説

式 `declval<To>() = declval<From>()` は正しい形式である必要があり、スローしないことがコンパイラに判明している必要があります。 と*の*どちら*To*も、完全な型、 **`void`** 、または不明なバインドの配列である必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
