---
title: switch ステートメント (C++)
ms.date: 05/06/2019
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 6b09c0eac939f7ca6a12b68ce5deb3fb83ad27c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160815"
---
# <a name="switch-statement-c"></a>switch ステートメント (C++)

整数式の値に応じてコードの複数のセクション間を切り替えます。

## <a name="syntax"></a>構文

```
   switch ( init; expression )
   case constant-expression : statement
   [default  : statement]
```

## <a name="remarks"></a>解説

*式*は、整数型または整数型へのあいまいな変換が存在するクラス型である必要があります。 整数の上位変換は、「[標準変換](standard-conversions.md)」で説明されているように実行されます。

**Switch**ステートメントの本体は、一連の**case**ラベルと省略可能な**既定**のラベルで構成されます。 **Case**ステートメント内の2つの定数式が同じ値に評価されることはありません。 **既定**のラベルは1回だけ表示できます。 ラベル付きステートメントは構文要件ではありませんが、 **switch**ステートメントを使用しても意味がありません。   default ステートメントを最後に記述する必要はありません。switch ステートメントの本体内の任意の場所で使用できます。 case ラベルまたは default ラベルは、switch ステートメント内でのみ使用できます。

各**case**ラベルの*定数式*は、*式*の型に変換され、*式*が等しいかどうかを比較します。 **Case** *定数式*が*expression*の値と一致するステートメントに制御が渡されます。 結果の動作を次の表に示します。

### <a name="switch-statement-behavior"></a>switch ステートメントの動作

|条件|アクション|
|---------------|------------|
|変換後の値は、上位変換された制御式の値と一致します。|制御は、そのラベルの次のステートメントに移ります。|
|どの定数も、 **case**ラベルの定数と一致しません。**既定**のラベルが存在します。|コントロールは**既定**のラベルに転送されます。|
|どの定数も、 **case**ラベルの定数と一致しません。**既定**のラベルは存在しません。|制御は、 **switch**ステートメントの後のステートメントに転送されます。|

一致する式が見つかった場合、その後の**case**または**default**ラベルによって制御が妨げされることはありません。 [Break](../cpp/break-statement-cpp.md)ステートメントは、実行を停止し、 **switch**ステートメントの後のステートメントに制御を転送するために使用されます。 **Break**ステートメントを使用しない**場合**は、一致した case ラベルから、**既定値**を含む**スイッチ**の最後までのすべてのステートメントが実行されます。 次に例を示します。

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   char *buffer = "Any character stream";
   int capa, lettera, nota;
   char c;
   capa = lettera = nota = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            capa++;
            break;
         case 'a':
            lettera++;
            break;
         default:
            nota++;
      }
   }
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",
      capa, lettera, (capa + lettera + nota) );
}
```

上の例では、`capa` は `c` が大文字 `A` の場合、インクリメントします。 `capa++` 後の**break**ステートメントは、 **switch**ステートメント本体の実行を終了し、 **while**ループに制御を渡します。 **Break**ステートメントを使用しない場合、実行は次のラベルが付けられたステートメントに "フォールスルー" されるので、`lettera` と `nota` もインクリメントされます。 同様の目的は、`case 'a'`の**break**ステートメントによって提供されます。 `c` が小文字 `a`の場合、`lettera` がインクリメントされ、 **break**ステートメントによって**switch**ステートメント本体が終了します。 `c` が `a` または `A`でない場合は、 **default**ステートメントが実行されます。

**Visual Studio 2017 以降:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能) `[[fallthrough]]` 属性は c++ 17 標準で指定されています。 **Switch**ステートメントでは、フォールスルー動作が意図されているコンパイラ (またはコードを読み取るユーザー) にヒントとして使用できます。 現在、 C++ Microsoft コンパイラでは fallthrough 動作について警告されないため、この属性はコンパイラの動作には影響しません。 属性は、ラベル付きステートメント内の空のステートメントに適用されることに注意してください。言い換えると、セミコロンが必要です。

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

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能): switch ステートメントでは、switch ステートメントのブロックに制限されたスコープを持つ変数を導入し、初期化することができます。

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

**Switch**ステートメントの内部ブロックには、到達可能である限り、初期化の定義を含めることができます (つまり、すべての実行パスでバイパスされることはありません)。 これらの宣言を使用して導入された名前にはローカル スコープがあります。 次に例を示します。

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

**Switch**ステートメントは入れ子にすることができます。 このような場合、 **case**または**default**ラベルは、それを囲む最も近い**switch**ステートメントに関連付けられます。

**Microsoft 固有の仕様**

Microsoft C では、 **switch**ステートメントの case 値の数は制限されません。 この数は、使用できるメモリによってのみ制限されます。 ANSI C では、 **switch**ステートメントで少なくとも257の case ラベルが許可されている必要があります。

Microsoft C の既定では、Microsoft 拡張機能が有効になっています。 これらの拡張機能を無効にするには、 [/za](../build/reference/za-ze-disable-language-extensions.md)コンパイラオプションを使用します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
