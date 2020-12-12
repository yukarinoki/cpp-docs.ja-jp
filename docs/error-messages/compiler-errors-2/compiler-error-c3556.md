---
description: 詳細については、「コンパイラエラー C3556」を参照してください。
title: コンパイラ エラー C3556
ms.date: 11/04/2016
f1_keywords:
- C3556
helpviewer_keywords:
- C3556
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
ms.openlocfilehash: b608e67958757c3e31a64fcf41954b056d6af404
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262400"
---
# <a name="compiler-error-c3556"></a>コンパイラ エラー C3556

> '*expression*': ' decltype ' の引数が正しくありません

コンパイラは、 `decltype(` *式* の `)` 型指定子への引数である式の型を推測できません。

## <a name="example"></a>例

次のコード例では、 `myFunction` がオーバーロードされているため、コンパイラは `myFunction` 引数の型を推定できません。 この問題を解決するには、を使用して、 **`static_cast`** 式で指定するオーバーロードされた特定の関数へのポインターのインスタンスを作成し **`decltype`** ます。

```cpp
// C3556.cpp
// compile with: cl /W4 /EHsc C3556.cpp
#include <iostream>

void myFunction(int);
void myFunction(float, float);

void callsMyFunction(decltype(myFunction) fn); // C3556
// One way to fix is to comment out the line above, and
// use static_cast to create specialized function pointer
// instances:
auto myFunctionInt = static_cast<void(*)(int)>(myFunction);
auto myFunctionFloatFloat = static_cast<void(*)(float,float)>(myFunction);
void callsMyFunction(decltype(myFunctionInt) fn, int n);
void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g);

void myFunction(int i) {
    std::cout << "called myFunction(" << i << ")" << std::endl;
}

void myFunction(float f, float g) {
    std::cout << "called myFunction(" << f << ", " << g << ")" << std::endl;
}

void callsMyFunction(decltype(myFunctionInt) fn, int n) {
    fn(n);
}

void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g) {
    fn(f, g);
}

int main() {
    callsMyFunction(myFunction, 42);
    callsMyFunction(myFunction, 0.1f, 2.3f);
}
```
