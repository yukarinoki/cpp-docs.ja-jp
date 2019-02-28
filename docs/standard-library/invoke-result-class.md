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
ms.openlocfilehash: 7c03240d3ee666fcda30562279a8dbda2ca8dc7b
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006873"
---
# <a name="invokeresult-class"></a>invoke_result クラス

コンパイル時に指定した引数型を受け取る呼び出し可能型の戻り値の型を決定します。 C++ 17 で追加されます。

## <a name="syntax"></a>構文

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<lass Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>パラメーター

*呼び出し可能*<br/>
照会する呼び出し可能型。

*Args*<br/>
照会する呼び出し可能型の引数リストの種類。

## <a name="remarks"></a>Remarks

結果型を判断するこのテンプレートを使用して*Callable*(*Args*...)、コンパイル時に、 *Callable*とすべての型*Args*完全な型、配列の不明なバインドは、または、おそらく cv で修飾された`void`します。 `type`の戻り値の型のテンプレート クラスのメンバー名*Callable*引数を使用して呼び出されたときに*Args*.`type`場合にのみ、メンバーが定義*Callable*引数を使用して呼び出されたときに呼び出すことができます*Args*.未評価のコンテキスト。 テンプレート クラスは、メンバーがない場合は、`type`コンパイル時に特定の引数の型のセット上でのテスト SFINAE ことができます。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[invoke](functional-functions.md#invoke)
