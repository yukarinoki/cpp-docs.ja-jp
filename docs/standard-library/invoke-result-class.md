---
title: invoke_result クラス
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::invoke_result
- type_traits/std::invoke_result_t
- type_traits/std::invoke_result::type
helpviewer_keywords:
- std::invoke_result
- std::invoke_result_t
- std::invoke_result::type
ms.openlocfilehash: e3e1a28310660ad1fbdae4dd58973de378ddf364
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233133"
---
# <a name="invoke_result-class"></a>invoke_result クラス

コンパイル時に指定された引数の型を受け取る呼び出し可能な型の戻り値の型を決定します。 C++ 17 で追加されました。

## <a name="syntax"></a>構文

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<class Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>パラメーター

*呼び出し可能*\
照会する呼び出し可能型。

*Value*\
照会する呼び出し可能型の引数リストの種類。

## <a name="remarks"></a>解説

このテンプレートを使用して、コンパイル時に*呼び出し*可能な (*args*...) の結果の種類を決定します。*呼び出し*可能なすべての型と*Args*のすべての型は、完全な型、不明な配列、または cv で修飾されたもの **`void`** です。 `type`クラステンプレートのメンバーは、引数*Args*... を使用して呼び出されたときに、*呼び出し*元の戻り値の型に名前を指定します。`type`メンバーは、引数*Args*を使用して呼び出されたときに*呼び出し*可能な場合にのみ定義されます...未評価のコンテキスト。 それ以外の場合、クラステンプレートにはメンバーがない `type` ため、コンパイル時に特定の引数の型に対して SFINAE テストを行うことができます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
