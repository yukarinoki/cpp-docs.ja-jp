---
title: :::no-loc(switch):::ステートメント (C++)
description: 'Microsoft Visual Studio C++ の標準 C++ ステートメントへの参照 :::no-loc(switch)::: 。'
ms.date: 04/25/2020
f1_keywords:
- :::no-loc(default):::_cpp
- :::no-loc(switch):::_cpp
- :::no-loc(case):::_cpp
helpviewer_keywords:
- ':::no-loc(switch)::: keyword [C++]'
- ':::no-loc(case)::: keyword [C++], in :::no-loc(switch)::: statements'
- ':::no-loc(default)::: keyword [C++]'
no-loc:
- ':::no-loc(switch):::'
- ':::no-loc(case):::'
- ':::no-loc(default):::'
- ':::no-loc(break):::'
- ':::no-loc(while):::'
- ':::no-loc(opt):::'
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: d71989b6d8af0213c4cd6d4fbd8d5a84b318701a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223591"
---
# <a name="no-locswitch-statement-c"></a>`:::no-loc(switch):::`ステートメント (C++)

整数式の値に応じてコードの複数のセクション間を切り替えます。

## <a name="syntax"></a>構文

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp;**`:::no-loc(switch):::`**&nbsp;**`(`**&nbsp;*`init-statement`*<sub>:::no-loc(opt):::</sub><sup>C++ 17</sup>&nbsp;*`condition`*&nbsp;**`)`**&nbsp;*`statement`*

> *`init-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression-statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`simple-declaration`*

> *`condition`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`attribute-specifier-seq`*<sub>:::no-loc(opt):::</sub>&nbsp;*`decl-specifier-seq`*&nbsp;*`declarator`*&nbsp;*`brace-or-equal-initializer`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(case):::`**&nbsp;*`constant-expression`*&nbsp;**`:`**&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(default):::`**&nbsp;**`:`**&nbsp;*`statement`*

## <a name="remarks"></a>Remarks

**`:::no-loc(switch):::`** ステートメントを指定すると、 *`condition`* の値に応じて、ステートメント本体の 1 つの *`labeled-statement`* にコントロールが転送されます。

は *`condition`* 整数型であるか、または整数型への明確な変換を持つクラス型である必要があります。 「[標準変換](standard-conversions.md)」で説明されているように、整数の上位変換が行われます。

ステートメントの本体は、 **`:::no-loc(switch):::`** 一連の **`:::no-loc(case):::`** ラベルと ional ラベルで構成され :::no-loc(opt)::: **`:::no-loc(default):::`** ます。 *`labeled-statement`* は、これらのラベルの1つであり、後続のステートメントです。 ラベル付きステートメントは構文要件ではありませんが、ステートメントを使用しても **`:::no-loc(switch):::`** 意味がありません。 *`constant-expression`* ステートメント内の2つの値 **`:::no-loc(case):::`** が同じ値に評価されることはありません。 **`:::no-loc(default):::`** ラベルが1回だけ表示される場合があります。 ステートメントは、 **`:::no-loc(default):::`** 多くの場合、末尾に配置されますが、ステートメント本体内の任意の場所に記述でき **`:::no-loc(switch):::`** ます。 **`:::no-loc(case):::`** または **`:::no-loc(default):::`** ラベルは、 **`:::no-loc(switch):::`** ステートメント内でのみ使用できます。

各ラベルのは、 *`constant-expression`* **`:::no-loc(case):::`** と同じ型の定数値に変換され *`condition`* ます。 次に、が *`condition`* 等しいかどうかを比較します。 制御は、の値に一致する値の後の最初のステートメントに渡さ **`:::no-loc(case):::`** *`constant-expression`* *`condition`* れます。 結果の動作を次の表に示します。

### <a name="no-locswitch-statement-behavior"></a>`:::no-loc(switch):::`ステートメントの動作

| 条件 | アクション |
|--|--|
| 変換後の値は、上位変換された制御式の値と一致します。 | 制御は、そのラベルの次のステートメントに移ります。 |
| どの定数もラベル内の定数と一致しません。 **`:::no-loc(case):::`** **`:::no-loc(default):::`** ラベルが存在します。 | コントロールはラベルに転送され **`:::no-loc(default):::`** ます。 |
| どの定数もラベル内の定数と一致しません。 **`:::no-loc(case):::`** **`:::no-loc(default):::`** ラベルは存在しません。 | 制御は、ステートメントの後のステートメントに転送され **`:::no-loc(switch):::`** ます。 |

一致する式が見つかった場合は、後で実行するか、ラベルを使用して実行を続行でき **`:::no-loc(case):::`** **`:::no-loc(default):::`** ます。 ステートメントは、実行を停止し、ステートメントの [`:::no-loc(break):::`](../cpp/:::no-loc(break):::-statement-cpp.md) 後のステートメントに制御を転送するために使用され **`:::no-loc(switch):::`** ます。 ステートメントを使用しない場合、を **`:::no-loc(break):::`** 含む、一致するラベルからの末尾までのすべてのステートメント **`:::no-loc(case):::`** **`:::no-loc(switch):::`** **`:::no-loc(default):::`** が実行されます。 次に例を示します。

```cpp
// :::no-loc(switch):::_statement1.cpp
#include <stdio.h>

int main() {
   const char *buffer = "Any character stream";
   int upper:::no-loc(case):::_A, lower:::no-loc(case):::_a, other;
   char c;
   upper:::no-loc(case):::_A = lower:::no-loc(case):::_a = other = 0;

   :::no-loc(while)::: ( c = *buffer++ )   // Walks buffer until NULL
   {
      :::no-loc(switch)::: ( c )
      {
         :::no-loc(case)::: 'A':
            upper:::no-loc(case):::_A++;
            :::no-loc(break):::;
         :::no-loc(case)::: 'a':
            lower:::no-loc(case):::_a++;
            :::no-loc(break):::;
         :::no-loc(default)::::
            other++;
      }
   }
   printf_s( "\nUpper:::no-loc(case)::: A: %d\nLower:::no-loc(case)::: a: %d\nTotal: %d\n",
      upper:::no-loc(case):::_A, lower:::no-loc(case):::_a, (upper:::no-loc(case):::_A + lower:::no-loc(case):::_a + other) );
}
```

上の例では、 `upper:::no-loc(case):::_A` が upper の場合、がインクリメントされ `c` :::no-loc(case)::: `'A'` ます。 **`:::no-loc(break):::`** の後のステートメントは、 `upper:::no-loc(case):::_A++` ステートメント本体の実行を終了 **`:::no-loc(switch):::`** し、制御をループに渡し **`:::no-loc(while):::`** ます。 ステートメントを使用しない場合 **`:::no-loc(break):::`** 、実行は次のラベル付きステートメントに "フォールスルー" されるので、 `lower:::no-loc(case):::_a` と `other` もインクリメントされます。 同様の目的は、のステートメントによって処理され **`:::no-loc(break):::`** `:::no-loc(case)::: 'a'` ます。 `c`が小さい場合は :::no-loc(case)::: `'a'` 、 `lower:::no-loc(case):::_a` がインクリメントされ、ステートメントによって **`:::no-loc(break):::`** ステートメント本体が終了し **`:::no-loc(switch):::`** ます。 が `c` `'a'` またはでない場合は `'A'` 、 **`:::no-loc(default):::`** ステートメントが実行されます。

**Visual Studio 2017 以降:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能) `[[fallthrough]]` 属性は c++ 17 標準で指定されています。 ステートメントで使用でき **`:::no-loc(switch):::`** ます。 これは、コンパイラにとってのヒントであり、コードを読み取るユーザーは、フォールスルー動作が意図的であることを示します。 現在、Microsoft C++ コンパイラでは fallthrough 動作について警告されないため、この属性はコンパイラの動作には影響しません。 この例では、未終了のラベルが付けられていないステートメント内の空のステートメントに属性が適用されます。 言い換えると、セミコロンが必要です。

```cpp
int main()
{
    int n = 5;
    :::no-loc(switch)::: (n)
    {

    :::no-loc(case)::: 1:
        a();
        :::no-loc(break):::;
    :::no-loc(case)::: 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    :::no-loc(case)::: 3:
        c();
        :::no-loc(break):::;
    :::no-loc(default)::::
        d();
        :::no-loc(break):::;
    }

    return 0;
}
```

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能)。 ステートメントには、 **`:::no-loc(switch):::`** 句を含めることができ *`init-statement`* ます。この句は、セミコロンで終わります。 次のように、スコープがステートメントのブロックに制限されている変数を導入し、初期化し **`:::no-loc(switch):::`** ます。

```cpp
    :::no-loc(switch)::: (Gadget gadget(args); auto s = gadget.get_status())
    {
    :::no-loc(case)::: status::good:
        gadget.zip();
        :::no-loc(break):::;
    :::no-loc(case)::: status::bad:
        throw BadGadget();
    };
```

ステートメントの内部ブロックには、 **`:::no-loc(switch):::`** *到達*可能である限り、初期化子を持つ定義を含めることができます。つまり、すべての実行パスでバイパスされることはありません。 これらの宣言を使用して導入された名前にはローカル スコープがあります。 次に例を示します。

```cpp
// :::no-loc(switch):::_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    :::no-loc(switch):::( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    :::no-loc(case)::: 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        :::no-loc(break):::;

    :::no-loc(case)::: 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        :::no-loc(break):::;

    :::no-loc(default)::::
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        :::no-loc(break):::;
    }
}
```

ステートメントは入れ子にする **`:::no-loc(switch):::`** ことができます。 入れ子になっている場合、 **`:::no-loc(case):::`** ラベルまたはラベルは、 **`:::no-loc(default):::`** それを囲む最も近いステートメントに関連付けられ **`:::no-loc(switch):::`** ます。

### <a name="microsoft-specific-behavior"></a>Microsoft 固有の動作

Microsoft C++ では、ステートメントの値の数は制限されません **`:::no-loc(case):::`** **`:::no-loc(switch):::`** 。 この数は、使用できるメモリによってのみ制限されます。

## <a name="see-also"></a>関連項目

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
