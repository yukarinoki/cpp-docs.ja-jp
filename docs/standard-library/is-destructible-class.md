---
description: '詳細情報: is_destructible クラス'
title: is_destructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_destructible
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
ms.openlocfilehash: fcd41c292c0054553b165529a85e7b23312d3c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231161"
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

型 *T* が破棄可能な型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 破棄可能な型は、参照型、オブジェクト型、および `U` に等しいいくつかの型 `remove_all_extents_t<T>` に対して、未評価オペランド `std::declval<U&>.~U()` が整形式である型です。 不完全な型、、および関数型を含むその他の型 **`void`** は、破棄可能な型ではありません。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
