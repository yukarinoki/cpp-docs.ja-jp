---
title: switchステートメント (C++)
description: Microsoft Visual Studio C++ の標準 C++ ステートメントへの参照 switch 。
ms.date: 04/25/2020
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
no-loc:
- switch
- case
- default
- break
- while
- opt
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: d43a7a64b5a74f00833093ae8999d73edd7f5753
ms.sourcegitcommit: c4cf8976939dd0e13e25b82930221323ba6f15d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83389702"
---
# <a name="switch-statement-c"></a>`switch`ステートメント (C++)

整数式の値に応じてコードの複数のセクション間を切り替えます。

## <a name="syntax"></a>構文

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp;__`switch`__&nbsp;__`(`__&nbsp;*`init-statement`*<sub>opt</sub><sup>C++ 17</sup>&nbsp;*`condition`*&nbsp;__`)`__&nbsp;*`statement`*

> *`init-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression-statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`simple-declaration`*

> *`condition`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`attribute-specifier-seq`*<sub>opt</sub>&nbsp;*`decl-specifier-seq`*&nbsp;*`declarator`*&nbsp;*`brace-or-equal-initializer`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; __`case`__&nbsp;*`constant-expression`*&nbsp;__`:`__&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; __`default`__&nbsp;__`:`__&nbsp;*`statement`*

## <a name="remarks"></a>Remarks

__`switch`__ ステートメントを指定すると、 *`condition`* の値に応じて、ステートメント本体の 1 つの *`labeled-statement`* にコントロールが転送されます。

は *`condition`* 整数型であるか、または整数型への明確な変換を持つクラス型である必要があります。 「[標準変換](standard-conversions.md)」で説明されているように、整数の上位変換が行われます。

ステートメントの本体は、 __`switch`__ 一連のラベルとオプションのラベルで構成され __`case`__ __`default`__ ます。 *`labeled-statement`* は、これらのラベルの1つであり、後続のステートメントです。 ラベル付きステートメントは構文要件ではありませんが、ステートメントを使用しても __`switch`__ 意味がありません。 *`constant-expression`* ステートメント内の2つの値 __`case`__ が同じ値に評価されることはありません。 __`default`__ ラベルが1回だけ表示される場合があります。 ステートメントは、 __`default`__ 多くの場合、末尾に配置されますが、ステートメント本体内の任意の場所に記述でき __`switch`__ ます。 __`case`__ または __`default`__ ラベルは、 __`switch`__ ステートメント内でのみ使用できます。

各ラベルのは、 *`constant-expression`* __`case`__ と同じ型の定数値に変換され *`condition`* ます。 次に、が *`condition`* 等しいかどうかを比較します。 制御は、の値に一致する値の後の最初のステートメントに渡さ __`case`__ *`constant-expression`* *`condition`* れます。 結果の動作を次の表に示します。

### <a name="switch-statement-behavior"></a>`switch`ステートメントの動作

| 条件 | アクション |
|--|--|
| 変換後の値は、上位変換された制御式の値と一致します。 | 制御は、そのラベルの次のステートメントに移ります。 |
| どの定数もラベル内の定数と一致しません。 __`case`__ __`default`__ ラベルが存在します。 | コントロールはラベルに転送され __`default`__ ます。 |
| どの定数もラベル内の定数と一致しません。 __`case`__ __`default`__ ラベルは存在しません。 | 制御は、ステートメントの後のステートメントに転送され __`switch`__ ます。 |

一致する式が見つかった場合は、後で実行するか、ラベルを使用して実行を続行でき __`case`__ __`default`__ ます。 ステートメントは、実行を停止し、ステートメントの [`break`](../cpp/break-statement-cpp.md) 後のステートメントに制御を転送するために使用され __`switch`__ ます。 ステートメントを使用しない場合、を __`break`__ 含む、一致するラベルからの末尾までのすべてのステートメント __`case`__ __`switch`__ __`default`__ が実行されます。 次に例を示します。

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   const char *buffer = "Any character stream";
   int uppercase_A, lowercase_a, other;
   char c;
   uppercase_A = lowercase_a = other = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            uppercase_A++;
            break;
         case 'a':
            lowercase_a++;
            break;
         default:
            other++;
      }
   }
   printf_s( "\nUppercase A: %d\nLowercase a: %d\nTotal: %d\n",
      uppercase_A, lowercase_a, (uppercase_A + lowercase_a + other) );
}
```

上の例では、`uppercase_A` は `c` が大文字 `'A'` の場合、インクリメントします。 __`break`__ の後のステートメントは、 `uppercase_A++` ステートメント本体の実行を終了 __`switch`__ し、制御をループに渡し __`while`__ ます。 ステートメントを使用しない場合 __`break`__ 、実行は次のラベル付きステートメントに "フォールスルー" されるので、 `lowercase_a` と `other` もインクリメントされます。 同様の目的は、のステートメントによって処理され __`break`__ `case 'a'` ます。 `c`が小文字の場合は `'a'` 、 `lowercase_a` がインクリメントされ、ステートメントによって __`break`__ ステートメント本体が終了し __`switch`__ ます。 が `c` `'a'` またはでない場合は `'A'` 、 __`default`__ ステートメントが実行されます。

**Visual Studio 2017 以降:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能) `[[fallthrough]]` 属性は c++ 17 標準で指定されています。 ステートメントで使用でき __`switch`__ ます。 これは、コンパイラにとってのヒントであり、コードを読み取るユーザーは、フォールスルー動作が意図的であることを示します。 現在、Microsoft C++ コンパイラでは fallthrough 動作について警告されないため、この属性はコンパイラの動作には影響しません。 この例では、未終了のラベルが付けられていないステートメント内の空のステートメントに属性が適用されます。 言い換えると、セミコロンが必要です。

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能)。 ステートメントには、 __`switch`__ 句を含めることができ *`init-statement`* ます。この句は、セミコロンで終わります。 次のように、スコープがステートメントのブロックに制限されている変数を導入し、初期化し __`switch`__ ます。

```cpp
    switch (Gadget gadget(args); auto s = gadget.get_status())
    {
    case status::good:
        gadget.zip();
        break;
    case status::bad:
        throw BadGadget();
    };
```

ステートメントの内部ブロックには、 __`switch`__ *到達*可能である限り、初期化子を持つ定義を含めることができます。つまり、すべての実行パスでバイパスされることはありません。 これらの宣言を使用して導入された名前にはローカル スコープがあります。 次に例を示します。

```cpp
// switch_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    switch( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    case 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        break;

    case 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        break;

    default:
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        break;
    }
}
```

ステートメントは入れ子にする __`switch`__ ことができます。 入れ子になっている場合、 __`case`__ ラベルまたはラベルは、 __`default`__ それを囲む最も近いステートメントに関連付けられ __`switch`__ ます。

### <a name="microsoft-specific-behavior"></a>Microsoft 固有の動作

Microsoft C++ では、ステートメントの値の数は制限されません __`case`__ __`switch`__ 。 この数は、使用できるメモリによってのみ制限されます。

## <a name="see-also"></a>関連項目

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
