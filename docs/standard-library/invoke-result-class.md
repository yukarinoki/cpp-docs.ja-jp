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
ms.openlocfilehash: 8cd72e62fcb65209482fd9677afcc2ec83356feb
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689518"
---
# <a name="invoke_result-class"></a>invoke_result クラス

コンパイル時に指定された引数の型を受け取る呼び出し可能な型の戻り値の型を決定します。 C++ 17 で追加されました。

## <a name="syntax"></a>構文

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<lass Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>パラメーター

*呼び出し*可能 \
照会する呼び出し可能型。

*Args* \
照会する呼び出し可能型の引数リストの種類。

## <a name="remarks"></a>Remarks

このテンプレートを使用して、コンパイル時に*呼び出し*可能な (*args*...) の結果の種類を決定します。*呼び出し*可能な引数と、 *args*内のすべての型は、完全な型、不明な配列、または cv で修飾された `void` です。 クラステンプレートの `type` メンバーは、引数*Args*... を使用して呼び出されたときに、*呼び出し*元の戻り値の型に名前を指定します。@No__t_3 メンバーは、引数*Args*を使用して呼び出されたときに*呼び出し*可能な場合にのみ定義されます...未評価のコンテキスト。 それ以外の場合、クラステンプレートには `type` メンバーがなく、コンパイル時に特定の引数の型に対して SFINAE テストを行うことができます。

## <a name="requirements"></a>［要件］

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[スタンド](functional-functions.md#invoke)
