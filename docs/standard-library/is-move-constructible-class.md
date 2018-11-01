---
title: is_move_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 1b1e450338a123c51b80f40f2369207c8b987cd6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508994"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible クラス

型に移動コンストラクターが存在するかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
評価される型

## <a name="remarks"></a>Remarks

型の場合に true に評価される型の述語*T*移動操作を使用して構築できます。 この述語は `is_constructible<T, T&&>` と同じです。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
