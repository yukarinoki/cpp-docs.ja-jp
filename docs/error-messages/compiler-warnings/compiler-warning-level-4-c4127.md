---
description: '詳細情報: コンパイラの警告 (レベル 4) C4127'
title: コンパイラの警告 (レベル 4) C4127
ms.date: 10/16/2019
f1_keywords:
- C4127
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
ms.openlocfilehash: 54c319c6894c0a82c99100c736498466a1c7c135
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261893"
---
# <a name="compiler-warning-level-4-c4127"></a>コンパイラの警告 (レベル 4) C4127

> 条件式が定数です。

## <a name="remarks"></a>解説

**`if`** ステートメントまたはループの制御式が **`while`** 定数に評価されます。 慣用的なの一般的な使用方法により、Visual Studio 2015 update 3 以降では、1やなどの単純な定数は、 **`true`** 式の演算の結果でない限り、警告をトリガーしません。

ループが途中で終了するためにループの制御式が定数である場合は、ループを **`while`** ループに置き換えることを検討してください **`while`** **`for`** 。 ループの初期化、終了テスト、およびループインクリメントを省略すると、と同様に **`for`** ループが無限になるため、 `while(1)` ステートメントの本体からループを終了できます **`for`** 。

## <a name="example"></a>例

次の例は、C4127 が生成される2つの方法を示しています。また、for ループを使用して警告を回避する方法を示しています。

```cpp
// C4127.cpp
// compile with: /W4
#include <stdio.h>
int main() {
   if (true) {}           // OK in VS2015 update 3 and later
   if (1 == 1) {}         // C4127
   while (42) { break; }  // C4127

   // OK
   for ( ; ; ) {
      printf("test\n");
      break;
   }
}
```

この警告は、条件式でコンパイル時定数が使用されている場合にも生成されます。

```cpp
#include <string>

using namespace std;

template<size_t S, class T>
void MyFunc()
{
   if (sizeof(T) >= S) // C4127. "Consider using 'if constexpr' statement instead"
   {
   }
}

class Foo
{
   int i;
   string s;
};

int main()
{
   Foo f;
   MyFunc<4, Foo>();
}
```
