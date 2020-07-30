---
title: is_destructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_destructible
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
ms.openlocfilehash: cd3c54684fe08a77d3a8774cd6a2554db9fb0c9c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215687"
---
# <a name="is_destructible-class"></a>is_destructible クラス

型が破棄可能かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

## <a name="remarks"></a>解説

型*T*が破棄可能な型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 破棄可能な型は、参照型、オブジェクト型、および `U` に等しいいくつかの型 `remove_all_extents_t<T>` に対して、未評価オペランド `std::declval<U&>.~U()` が整形式である型です。 不完全な型、、および関数型を含むその他の型 **`void`** は、破棄可能な型ではありません。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
