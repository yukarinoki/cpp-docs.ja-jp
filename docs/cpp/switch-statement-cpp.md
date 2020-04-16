---
title: switchステートメント (C++)
description: 標準 C++switchステートメントへの参照です。
ms.date: 04/15/2020
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
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 1f65d4699423d74be9c75a9be47e543a9a1256e2
ms.sourcegitcommit: 9266fc76ac2e872e35a208b4249660dfdfc87cba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81480821"
---
# <a name="opno-locswitch-statement-c"></a>switchステートメント (C++)

整数式の値に応じてコードの複数のセクション間を切り替えます。

## <a name="syntax"></a>構文

> **`switch (`**\[[*初期化***`;`**]*式***`)`**\
> **`{`**\
> &nbsp;&nbsp;&nbsp;&nbsp;**`case`***定数式***`:`***ステートメント*\
> &nbsp;&nbsp;&nbsp;&nbsp;\[**`default :`***明細書*]\
> **`}`**

## <a name="remarks"></a>解説

*式*は、整数型を持っているか、整数型への明確な変換を持つクラス型である必要があります。 整数の昇格は、[標準変換](standard-conversions.md)で説明されているように行われます。

ステートメント**switch** 本体は、一連のラベル**case** とオプション**default** のラベルで構成されます。 総称して、ラベルの後に続くステートメントは*ラベル付きステートメントと*呼ばれます。 ラベル付けされたステートメントは構文上の要件ではありませんが、**switch** ステートメントがなければ意味がありません。 ステートメント内の**case** 2 つの定数式が同じ値に評価されません。 ラベル**default** は一度だけ表示されます。 ステートメント**default** は、通常は最後に配置されますが、**switch** ステートメントの本文のどこにでも記述できます。 または**case****default** ラベルは**switch**、ステートメント内でのみ使用できます。

各**case** ラベル*の定数式*は、*式*の型に変換されます。 次に、等価の*式*と比較されます。 定数式が**case***expression*の値と一致するステートメントに制御が渡*されます。* 結果の動作を次の表に示します。

### <a name="switch-statement-behavior"></a>ステートメントの動作の切り替え

| 条件 | アクション |
|--|--|
| 変換後の値は、上位変換された制御式の値と一致します。 | 制御は、そのラベルの次のステートメントに移ります。 |
| どの定数も**case** ラベルの定数と一致しません。**default** ラベルが存在します。 | コントロールはラベルに転送**default** されます。 |
| どの定数も**case** ラベルの定数と一致しません。ラベル**default** が存在しません。 | 制御は、ステートメントの後にステートメント**switch** に転送されます。 |

一致する式が見つかった場合は、実行は**case** 後**default** で実行を続けることができます。 この[`break`](../cpp/break-statement-cpp.md)ステートメントは、実行を停止し、ステートメントの後に制御を**switch** 転送するために使用されます。 ステートメントを**break** 指定しない場合、一致した**case** ラベルから の末尾まで**switch** のすべてのステートメントが**default** 実行されます。 次に例を示します。

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

上の例では、`uppercase_A` は `c` が大文字 `'A'` の場合、インクリメントします。 ステートメント**break** 本体の`uppercase_A++`実行を**switch** 終了し、制御がループに渡された後の**while** ステートメント。 ステートメントがないと**break**、実行はラベル付きの次のステートメントに "フォールスルー"`lowercase_a`し`other`、インクリメントされます。 同様の目的は、 の**break**`case 'a'`ステートメントによって提供されます。 小文字`c``'a'`の場合`lowercase_a`は、インクリメントされ、ステートメント**break** はステートメント本体を**switch** 終了します。 `'a'`または`c``'A'`でない場合、ステートメント**default** が実行されます。

**Visual Studio 2017 以降:** [(/std:c++17](../build/reference/std-specify-language-standard-version.md)`[[fallthrough]]`で利用可能) 属性は C++17 標準で指定されています。 ステートメントで**switch** 使用できます。 これは、コンパイラ、またはコードを読み取る人にとっては、フォールスルーの動作が意図的な動作であるというヒントです。 現在、Microsoft C++ コンパイラはフォールスルーの動作に関して警告を表示しないので、この属性はコンパイラの動作に影響しません。 この例では、この属性は、終了していないラベル付きステートメント内の空のステートメントに適用されます。 つまり、セミコロンが必要です。

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

**Visual Studio 2017 バージョン 15.3 以降** [(/std:c++17](../build/reference/std-specify-language-standard-version.md)で利用可能)。 ステートメントswitchには*初期化*句を指定できます。 スコープがswitchステートメントのブロックに限定された変数を導入して初期化します。

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

ステートメントの内部ブロックには、初期化を含む定義を含めることができますが、その定義は、すべての実行可能な実行パスによってバイパスされるわけではありません。 *reachable* **switch** これらの宣言を使用して導入された名前にはローカル スコープがあります。 次に例を示します。

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

ステートメント**switch** はネストできます。 ネストすると、 または**case****default** ラベルは、それらを囲**switch** む最も近いステートメントに関連付けられます。

### <a name="microsoft-specific-behavior"></a>マイクロソフト固有の動作

Microsoft C では、ステートメントの値**case** の数を**switch** 制限しません。 この数は、使用できるメモリによってのみ制限されます。 ANSI C では、ステートメントで**case** 少なくとも 257 ラベルを**switch** 使用できる必要があります。

マイクロソフトdefaultC のマイクロソフト拡張機能が有効になっているです。 これらの拡張機能を無効にするには[、/Za](../build/reference/za-ze-disable-language-extensions.md)コンパイラ オプションを使用します。

## <a name="see-also"></a>関連項目

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
