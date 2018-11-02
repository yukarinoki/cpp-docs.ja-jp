---
title: is_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
ms.openlocfilehash: b1357bf8c5ad4dfd5035855e34a8fd6a7ed73d15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605960"
---
# <a name="isassignable-class"></a>is_assignable クラス

`From` 型の値を `To` 型に代入できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>パラメーター

*目的*<br/>
代入を受け取るオブジェクトの型。

*From*<br/>
値を渡すオブジェクトの型。

## <a name="remarks"></a>Remarks

評価されていない式 `declval<To>() = declval<From>()` は整形式である必要があります。 両方`From`と`To`完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
