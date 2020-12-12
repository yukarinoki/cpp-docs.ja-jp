---
description: '詳細情報: is_nothrow_move_assignable クラス'
title: is_nothrow_move_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_assignable
helpviewer_keywords:
- is_nothrow_move_assignable
ms.assetid: 000baa02-cbba-49de-9870-af730033348e
ms.openlocfilehash: 77d61ff79d56ff1caee2d856ac4d947821c16946
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230758"
---
# <a name="is_nothrow_move_assignable-class"></a>is_nothrow_move_assignable クラス

型に移動代入演算子があるかどうかをテスト **`nothrow`** します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

型が nothrow の移動代入演算子 *を持つ場合* 、型の述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
