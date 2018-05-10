---
title: is_destructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41a5da108c082dc4199a216d36f51d41e1748ada
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="isdestructible-class"></a>is_destructible クラス

型が破棄可能かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

## <a name="remarks"></a>コメント

型 `T` が破棄可能な型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 破棄可能な型は、参照型、オブジェクト型、および `U` に等しいいくつかの型 `remove_all_extents_t<T>` に対して、未評価オペランド `std::declval<U&>.~U()` が整形式である型です。 不完全な型、 `void`、および関数型を含む他の型は、破棄可能な型ではありません。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
