---
description: 詳細については、「コンパイラエラー C3535」を参照してください。
title: コンパイラ エラー C3535
ms.date: 11/04/2016
f1_keywords:
- C3535
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
ms.openlocfilehash: ba5019d623fe6f390051084894e13235c6503cc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315349"
---
# <a name="compiler-error-c3535"></a>コンパイラ エラー C3535

' type1 ' から ' type1 ' の型を推測できません

キーワードで宣言された変数の型は、 **`auto`** 初期化式の型から推測できません。 たとえば、このエラーは、初期化式 **`void`** が型ではないと評価された場合に発生します。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 初期化式の型がでないことを確認 **`void`** してください。

1. 宣言が基本型へのポインターではないことを確認してください。 詳細については、「 [基本型](../../cpp/fundamental-types-cpp.md)」を参照してください。

1. 宣言が型へのポインターである場合は、初期化式がポインター型であることを確認します。

## <a name="examples"></a>例

次の例では、初期化式がに評価されるため、C3535 が生成され **`void`** ます。

```cpp
// C3535a.cpp
// Compile with /Zc:auto
void f(){}
int main()
{
   auto x = f();   //C3535
   return 0;
}
```

次の例では、ステートメントが `x` 推測された型へのポインターとして変数を宣言していますが、初期化子式の型が double であるため、C3535 が生成されます。 そのため、コンパイラは変数の型を推測できません。

```cpp
// C3535b.cpp
// Compile with /Zc:auto
int main()
{
   auto* x = 123.0;   // C3535
   return 0;
}
```

次の例では、変数が `p` 推測された型へのポインターを宣言していますが、初期化式がポインター型ではないため、C3535 が生成されます。

```cpp
// C3535c.cpp
// Compile with /Zc:auto
class A { };
A x;
auto *p = x;  // C3535
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-cpp.md)<br/>
[基本型](../../cpp/fundamental-types-cpp.md)
