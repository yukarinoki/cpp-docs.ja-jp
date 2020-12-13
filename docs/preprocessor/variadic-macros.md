---
description: '詳細情報: 可変個引数マクロ'
title: 可変個引数マクロ
ms.date: 10/17/2019
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: 876e0ca46dd8774796c8a4f9d7572cbff5caa93c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149657"
---
# <a name="variadic-macros"></a>可変個引数マクロ

Variadic マクロは、可変個の引数を含む関数に似たマクロです。

## <a name="remarks"></a>解説

可変個引数マクロを使用するには、マクロ定義で最後の仮引数として省略記号を指定することができます。また、置換識別子は、 `__VA_ARGS__` 追加の引数を挿入するために定義で使用できます。  `__VA_ARGS__` は、省略記号と一致するすべての引数によって置き換えられます (コンマも含む)。

C 標準では、マクロが末尾のコンマを含む式に解決されないようにするために、少なくとも1つの引数を省略記号に渡す必要があることを指定します。 従来の Microsoft C++ の実装では、省略記号に引数が渡されない場合、末尾のコンマが抑制されます。 `/experimental:preprocessor`コンパイラオプションが設定されている場合、末尾のコンマは抑制されません。

## <a name="example"></a>例

```cpp
// variadic_macros.cpp
#include <stdio.h>
#define EMPTY

#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }
#define CHECK3(...) { printf(__VA_ARGS__); }
#define MACRO(s, ...) printf(s, __VA_ARGS__)

int main() {
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print

    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");

    // always invokes printf in the macro
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");

    MACRO("hello, world\n");

    MACRO("error\n", EMPTY); // would cause error C2059, except VC++
                             // suppresses the trailing comma
}
```

```Output
here are some varargs1(1)
here are some varargs2(4)
here are some varargs3(5)
hello, world
error
```

## <a name="see-also"></a>関連項目

[マクロ (C/C++)](../preprocessor/macros-c-cpp.md)
