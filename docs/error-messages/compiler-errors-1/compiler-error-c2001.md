---
title: コンパイラエラー C2001
ms.date: 11/04/2016
f1_keywords:
- C2001
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
ms.openlocfilehash: 6b40a3bd186b5c45a0ea5163f433635ab1e7b07f
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743491"
---
# <a name="compiler-error-c2001"></a>コンパイラエラー C2001

定数の改行

次の操作を行わない限り、文字列定数は2行目で続けることはできません。

- 最初の行の末尾に円記号を付けます。

- 最初の行で二重引用符で囲まれた文字列を閉じ、次の行の文字列をもう1つの二重引用符で開きます。

\N で最初の行を終了するだけでは十分ではありません。

## <a name="examples"></a>例

次の例では、C2001 が生成されます。

```cpp
// C2001.cpp
// C2001 expected
#include <stdio.h>

int main()
{
    printf_s("Hello,
             world");
    printf_s("Hello,\n
             world");
}
```

文字列定数には、行連結文字の後の次の行の先頭にあるスペースが含まれます。 上の例では、文字列定数に改行文字が埋め込まれていません。 次に示すように、改行文字を埋め込むことができます。

```cpp
// C2001b.cpp
#include <stdio.h>

int main()
{
    printf_s("Hello,\n\
             world");

    printf_s("Hello,\
             \nworld");

    printf_s("Hello,\n"
             "world");

    printf_s("Hello,"
             "\nworld");

    printf_s("Hello,"
             " world");

    printf_s("Hello,\
             world");
}
```
