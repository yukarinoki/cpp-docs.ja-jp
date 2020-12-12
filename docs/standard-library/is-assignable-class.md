---
description: '詳細情報: is_assignable クラス'
title: is_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
ms.openlocfilehash: 4165e69de99b7fdb8ae1524d1755e738c846d7c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323861"
---
# <a name="is_assignable-class"></a>is_assignable クラス

`From` 型の値を `To` 型に代入できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>パラメーター

*宛先*\
代入を受け取るオブジェクトの型。

*差出人*\
値を渡すオブジェクトの型。

## <a name="remarks"></a>解説

評価されていない式 `declval<To>() = declval<From>()` は整形式である必要があります。 `From`とはどちらも `To` 完全な型、 **`void`** 、または不明なバインドの配列である必要があります。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
