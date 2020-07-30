---
title: is_trivially_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_assignable
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
ms.openlocfilehash: 14a3ee638bd6df3b52e7327ca6e3c77f4a0e8b71
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224865"
---
# <a name="is_trivially_assignable-class"></a>is_trivially_assignable クラス

`From` 型の値を `To` 型に普通に代入できるかどうかをテストします

## <a name="syntax"></a>構文

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>パラメーター

*宛先*\
代入を受け取るオブジェクトの型。

*差出人*\
値を渡すオブジェクトの型。

## <a name="remarks"></a>解説

式 `declval<To>() = declval<From>()` は正しい形式である必要があり、トリビアルでない演算を必要としないことがコンパイラに判明している必要があります。 `From`とはどちらも `To` 完全な型、 **`void`** 、または不明なバインドの配列である必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
