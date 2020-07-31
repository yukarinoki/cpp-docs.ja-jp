---
title: コンパイラ エラー C3499
ms.date: 11/04/2016
f1_keywords:
- C3499
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
ms.openlocfilehash: 21d7424e727dab54ff507a8ec9a38db44df1806f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228844"
---
# <a name="compiler-error-c3499"></a>コンパイラ エラー C3499

void の戻り値の型を持つように指定されているラムダは、値を返すことができません

戻り値の型としてを指定するラムダ式が値を返す場合、 **`void`** またはラムダ式に複数のステートメントが含まれ、戻り値の型が指定されていない場合、コンパイラはこのエラーを生成します。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- ラムダ式から値を返さないようにする

- ラムダ式の戻り値の型を指定する

- ラムダ式の本体を構成するステートメントを結合して、単一のステートメントにする

## <a name="example"></a>例

次の例では、ラムダ式の本体に複数のステートメントが含まれており、値を返すものの、ラムダ式で戻り値の型が指定されていないため、C3499 が生成されます。

```cpp
// C3499a.cpp

int main()
{
   [](int x) { int n = x * 2; return n; } (5); // C3499
}
```

## <a name="example"></a>例

次の例では、C3499 について考えられる 2 つの解決策を示します。 最初の解決策では、ラムダ式の戻り値の型を指定します。 2 番目の解決策では、ラムダ式の本体を構成するステートメントを結合して、単一のステートメントにします。

```cpp
// C3499b.cpp

int main()
{
   // Possible resolution 1:
   // Provide the return type of the lambda expression.
   [](int x) -> int { int n = x * 2; return n; } (5);

   // Possible resolution 2:
   // Combine the statements that make up the body of
   // the lambda expression into a single statement.
   [](int x) { return x * 2; } (5);
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
