---
title: result_of クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b385d822c2f58d26938b3300207a790dc1193060
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953050"
---
# <a name="resultof-class"></a>result_of クラス

指定された引数型を受け取る呼び出し可能型の戻り値の型を決定します。

## <a name="syntax"></a>構文

```cpp
template<class>
struct result_of; // Causes a static assert

template <class Fn, class... ArgTypes>
struct result_of<Fn(ArgTypes...)>;

// Helper type
template<class T>
   using result_of_t = typename result_of<T>::type;
```

### <a name="parameters"></a>パラメーター

*Fn*照会する呼び出し可能型。

*ArgTypes*クエリする呼び出し可能型の引数リストの種類。

## <a name="remarks"></a>Remarks

このテンプレートを使用して、コンパイル時の結果の型を決定`Fn`(`ArgTypes`) ここで、 *Fn*が呼び出し可能型、関数への参照またはで型の引数リストを使用して呼び出される呼び出し可能型への参照*ArgTypes*します。 評価されていない式 `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` が整形式の場合、テンプレート クラスの `type` メンバーによって、`decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` の結果の型が指定されます。 それ以外の場合、このテンプレート クラスはメンバー `type` を持ちません。 型*Fn*パラメーター パック内のすべての型と*ArgTypes*完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
