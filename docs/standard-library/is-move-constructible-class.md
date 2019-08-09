---
title: is_move_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: c83ed4365fd0e73a7daa8b9894c5e85f20387a79
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456117"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible クラス

型に移動コンストラクターが存在するかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>パラメーター

*\T*\
評価される型

## <a name="remarks"></a>Remarks

移動操作を使用して型*T*を構築できる場合は true に評価される型述語。 この述語は `is_constructible<T, T&&>` と同じです。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
