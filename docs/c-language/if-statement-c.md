---
title: if ステートメント (C)
ms.date: 11/04/2016
f1_keywords:
- else
- if
helpviewer_keywords:
- if keyword [C]
- else clauses
- else keyword [C]
- if keyword [C], if statement syntax
- nested statements
ms.assetid: d7fc16a0-fdbc-4f39-b596-76e1ca4ad4a5
ms.openlocfilehash: 67cdae033c3c8669c8bc7ae1d2e3584ef68498f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227843"
---
# <a name="if-statement-c"></a>if ステートメント (C)

**`if`** ステートメントでは、条件分岐が制御されます。 **`if`** ステートメントの本体は、式の値が 0 でないの場合に実行されます。 **`if`** ステートメントの構文には 2 つの形式があります。

## <a name="syntax"></a>構文

*selection-statement*: **if (**  *expression*  **)**  *statement*

**if (**  *expression*  **)**  *statement*  **`else`**  *statement*

**`if`** ステートメントのどちらの形式でも、構造体以外のすべての値を持つことができる式が、すべての副作用を含めて評価されます。

最初の構文では、*expression* が true (0 以外) の場合、*statement* が実行されます。 *expression* が false の場合、*statement* は無視されます。 **`else`** を使用する 2 番目の構文形式では、2 番目の *statement* は *expression* が false の場合に実行されます。 どちらの形式でも、いずれかのステートメントに **`break`** 、 **`continue`** 、または **`goto`** が含まれていない場合は、制御が **`if`** ステートメントからプログラムの次のステートメントに移ります。

**`if`** ステートメントの例を次に示します。

```
if ( i > 0 )
    y = x / i;
else
{
    x = i;
    y = f( x );
}
```

この例では、ステートメント本体 `y = x/i;` は、`i` が 0 を超える場合に実行されます。 `i` が 0 以下の場合、`i` が `x` に割り当てられ、`f( x )` が `y` に割り当てられます。 **`if`** 句を形成するステートメントはセミコロンで終わることに注意してください。

**`if`** ステートメントと **`else`** 句を入れ子にする場合は、意図がはっきりわかるように、中かっこを使用してステートメントと句を複合ステートメントにグループ化します。 中かっこがない場合、コンパイラでは各 **`else`** を **`else`** のない最も近い **`if`** と関連付けることによって、あいまいさが解消されます。

```
if ( i > 0 )           /* Without braces */
    if ( j > i )
        x = j;
    else
        x = i;
```

**`else`** 句は、この例の内側の **`if`** ステートメントに関連付けられます。 `i` が 0 以下の場合、`x` に値は割り当てられません。

```
if ( i > 0 )
{                      /* With braces */
    if ( j > i )
        x = j;
}
else
    x = i;
```

この例の内側の **`if`** ステートメントを囲んでいる中かっこにより、 **`else`** 句は外側の **`if`** ステートメントの一部になります。 `i` が 0 以下の場合、`i` が `x` に割り当てられます。

## <a name="see-also"></a>関連項目

[if-else ステートメント (C++)](../cpp/if-else-statement-cpp.md)
