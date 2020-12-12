---
description: '詳細情報: is_trivially_assignable クラス'
title: is_trivially_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_assignable
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
ms.openlocfilehash: fbbf14b83dff4bea9ed50eddf93512899f6d9fb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118551"
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

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
