---
title: return ステートメント (C)
description: C 言語の return ステートメントは、関数の実行を終了し、必要に応じて呼び出し元に値を返します。
ms.date: 06/10/2020
helpviewer_keywords:
- ( ) parentheses in return statements
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
ms.openlocfilehash: 7d518aa17185c96de15c8f9aa9b65ae5c72bd014
ms.sourcegitcommit: 01b911613606c3fc92cbd9ca48cca6046a7e8258
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84716295"
---
# <a name="return-statement-c"></a>return ステートメント (C)

**`return`** ステートメントは、関数の実行を終了し、呼び出し元の関数に制御を戻します。 呼び出し直後の位置から、呼び出し元の関数で実行が再開します。 **`return`** ステートメントでは、呼び出し元の関数に値を返すことができます。 詳細については、「[戻り値の型](../c-language/return-type.md)」を参照してください。

## <a name="syntax"></a>構文

> *jump-statement*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`return`** *expression*&#8203;<sub>opt</sub> **`;`**

*expression* の値 (存在する場合) が呼び出し元の関数に返されます。 *expression* が省略されている場合、関数の戻り値は未定義です。 式が存在する場合は、評価され、関数が返した型に変換されます。 **`void`** 戻り値の型を持つ関数の式が **`return`** ステートメントに含まれている場合、コンパイラによって警告が生成され、その式は評価されません。

**`return`** ステートメントが関数定義に含まれていない場合、呼び出された関数の最後のステートメントが実行された後に、制御が自動的に呼び出し元の関数に戻ります。 この場合、呼び出される関数の戻り値は未定義です。 **`void`** 以外の戻り値の型が関数に含まれているいる場合、それは重大なバグであり、警告を示す診断メッセージがコンパイラから出力されます。 戻り値の型 **`void`** が関数に含まれている場合、この動作に問題ありませんが、不適切なスタイルと見なされる可能性があります。 単純な **`return`** ステートメントを使用して、自分の意図を明確にしてください。

エンジニアリング手法として、使用する関数の戻り値の型を常に指定することを推奨します。 戻り値が必要ない場合は、関数の宣言において **`void`** 戻り値の型を使用するようにします。 戻り値の型を指定しない場合、C コンパイラでは **`int`** が既定の戻り値の型であると見なされます。

プログラマの多くはかっこを使用して **`return`** ステートメントの *expression* 引数を囲みます。 ただし、C ではかっこは必要ありません。

コンパイラでは、 **`return`** ステートメントの後に何らかのステートメントが置かれていることを検出した場合、到達できないコードについて警告を示す診断メッセージが発行される可能性があります。

**`main`** 関数では、 **`return`** ステートメントと式は省略可能となります。 戻り値を指定した場合、それがどのようになるかは実装によって異なります。 **Microsoft 固有**: Microsoft C の実装では、 *`cmd.exe`* などのプログラムを呼び出したプロセスに式の値が返されます。 **`return`** 式が指定されていない場合は、成功 (0) または失敗 (0 以外の値) を示す値が Microsoft C ランタイムから返されます。

## <a name="example"></a>例

この例は、複数の部分で構成された 1 つのプログラムです。 ここでは、 **`return`** ステートメントを示すと共に、これを使用して関数の実行を終了する方法と、必要に応じて値を返す方法について説明します。

```C
// C_return_statement.c
// Compile using: cl /W4 C_return_statement.c
#include <limits.h>      // for INT_MAX
#include <stdio.h>       // for printf

long long square( int value )
{
    // Cast one operand to long long to force the
    // expression to be evaluated as type long long.
    // Note that parentheses around the return expression
    // are allowed, but not required here.
    return ( value * (long long) value );
}
```

`square` 関数からは、算術エラーを防ぐために、その引数の 2 乗がより幅の広い型で返されます。 **Microsoft 固有**: Microsoft C の実装の **`long long`** 型は、オーバーフローを発生させることなく、2 つの **`int`** 値の積を保持するのに十分な大きさとなっています。

`square` の **`return`** 式を囲むかっこは、式の一部として評価され、 **`return`** ステートメントでは必要ありません。

```C
double ratio( int numerator, int denominator )
{
    // Cast one operand to double to force floating-point
    // division. Otherwise, integer division is used,
    // then the result is converted to the return type.
    return numerator / (double) denominator;
}
```

`ratio` 関数からは、その 2 つの **`int`** 引数の比率が浮動小数点 **`double`** 値として返されます。 **`return`** 式では、オペランドの 1 つを **`double`** にキャストすることによって、強制的に浮動小数点演算が使用されています。 それ以外の場合は、整数除算演算子が使用され、小数部分は失われます。

```C
void report_square( void )
{
    int value = INT_MAX;
    long long squared = 0LL;
    squared = square( value );
    printf( "value = %d, squared = %lld\n", value, squared );
    return; // Use an empty expression to return void.
}
```

`report_square` 関数では、`INT_MAX` のパラメーター値 ( **`int`** に収まる符号付きの最大整数値) に対して `square` が呼び出されます。 **`long long`** の結果が `squared` に格納されてから、出力されます。 `report_square` 関数には、戻り値の型として **`void`** が指定されているので、その **`return`** ステートメント内に式はありません。

```C
void report_ratio( int top, int bottom )
{
    double fraction = ratio( top, bottom );
    printf( "%d / %d = %.16f\n", top, bottom, fraction );
    // It's okay to have no return statement for functions
    // that have void return types.
}
```

`report_ratio` 関数では、`1` と `INT_MAX` のパラメーター値に対して `ratio` が呼び出されます。 **`double`** の結果が `fraction` に格納されてから、出力されます。 `report_ratio` 関数には、戻り値の型として **`void`** が指定されているため、明示的に値を返す必要はありません。 `report_ratio` を実行すると、"bottom を下回る" ので、呼び出し元に値は返されません。

```C
int main()
{
    int n = 1;
    int x = INT_MAX;

    report_square();
    report_ratio( n, x );

    return 0;
}
```

**`main`** 関数では、`report_square` と `report_ratio`の 2 つの関数が呼び出されます。 `report_square` はパラメーターを取らず、 **`void`** が返されるため、その結果を変数に代入することはしません。 同様に、`report_ratio` からは **`void`** が返されるため、その戻り値の保存も行いません。 これらの関数の各々が呼び出されるたびに、次のステートメントで実行が続行されます。 次に、 **`main`** から、プログラムを終了するための値として `0` (通常は成功を報告するために使用される) が返されます。

この例をコンパイルするには、 *`C_return_statement.c`* という名前のソース コード ファイルを作成します。 次に、すべてのコード例を、示されている順序でコピーします。 ファイルを保存してから、次のコマンドを使用して開発者コマンド プロンプト ウィンドウでコンパイルします。

**`cl /W4 C_return_statement.c`**

次に、コード例を実行するために、コマンド プロンプトで「 **`C_return_statement.exe`** 」と入力します。 この例の出力は次のようになります。

```Output
value = 2147483647, squared = 4611686014132420609
1 / 2147483647 = 0.0000000004656613
```

## <a name="see-also"></a>関連項目

[ステートメント](../c-language/statements-c.md)
