---
title: コンパイラ エラー C2001
ms.date: 11/04/2016
f1_keywords:
- C2001
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
ms.openlocfilehash: 03b54fe2373063c8c0f9905da93822928392998d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596366"
---
# <a name="compiler-error-c2001"></a>コンパイラ エラー C2001

定数の新しい行

文字列定数は、以下を実行しない限り、2 行目に継続できません。

- 円記号で最初の行を終了します。

- 二重引用符では、最初の行の文字列を閉じて、もう 1 つの二重引用符で次の行に文字列を開きます。

\N で最初の行を終了することは、十分ではありません。

## <a name="example"></a>例

次の例では、C2001 が生成されます。

```
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

## <a name="example"></a>例

文字列定数には、行連結文字の後に次の行の先頭にスペースが含まれます。 前に示した例では、いずれは、文字列定数に改行文字を埋め込みます。 次に示すように、改行文字を埋め込むことができます。

```
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