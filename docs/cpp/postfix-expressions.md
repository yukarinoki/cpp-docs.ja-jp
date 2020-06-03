---
title: 後置式
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], postfix
- postfix expressions
- expressions [C++], postfix
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
ms.openlocfilehash: 897eb80c713f786ecf0f7e6c9cf24cd8bdfc0aa8
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032279"
---
# <a name="postfix-expressions"></a>後置式

後置式は、1 次式、または後置演算子が 1 次式に続く式で構成されます。 次の表は、後置演算子の一覧です。

### <a name="postfix-operators"></a>後置演算子

|演算子名|演算子表記|
|-------------------|-----------------------|
|[下付き文字演算子](../cpp/subscript-operator.md)|**[ ]**|
|[関数呼び出し演算子](../cpp/function-call-operator-parens.md)|**( )**|
|[明示的な型変換演算子](../cpp/explicit-type-conversion-operator-parens.md)|*タイプ名* **( )**|
|[メンバー アクセス演算子](../cpp/member-access-operators-dot-and.md)|**.** または**->**|
|[後置インクリメント演算子](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**++**|
|[後置デクリメント演算子](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**--**|

次の構文は、可能な後置式について説明しています。

```
primary-expression
postfix-expression[expression]postfix-expression(expression-list)simple-type-name(expression-list)postfix-expression.namepostfix-expression->namepostfix-expression++postfix-expression--cast-keyword < typename > (expression )typeid ( typename )
```

上記*の後置式*は、一次式または別の接尾式であってもよい。  **「基本式**」を参照してください。  後置式は左から右へグループ化されるため、次のように式を連結できます。

```cpp
func(1)->GetValue()++
```

上記`func`式では、一次式`func(1)`、関数の接尾辞式、`func(1)->GetValue`クラスのメンバーを指定する後置式、`func(1)->GetValue()`もう 1 つの関数の後置式、および式全体が GetValue の戻り値をインクリメントする後置式です。  全体として式の意味は、「引数として 1 を渡す関数を呼び出し、戻り値としてクラスへのポインターを取得します。  その後`GetValue()`、そのクラスを呼び出し、返された値をインクリメントします。

前の式は、代入式です。つまり、これらの式の結果が右辺値である必要があります。

後置式のフォーム

```cpp
simple-type-name ( expression-list )
```

コンストラクターの呼び出しを示します。  単純型名が基本型である場合、式リストは 1 つの式である必要があります。また、この式は、基本型への式の値のキャストを示します。  この型のキャスト式はコンストラクターを模倣します。  この形式は同じ構文を使用して構築されている基本型とクラスを使用するため、この形式はテンプレート クラスを定義する場合に特に便利です。

*キャスト キーワード*は、 **static_cast**または**reinterpret_cast** **dynamic_cast**の 1 つです。  詳細については、「 **dynamic_cast**、 **static_cast**および**reinterpet_cast**」 を参照してください。

**typeid**演算子は、後置式と見なされます。  **「typeid 演算子**」を参照してください。

## <a name="formal-and-actual-arguments"></a>仮引数と実引数

呼び出し元のプログラムは "実引数" の呼び出された関数に情報を渡します。 呼び出された関数は、対応する "仮引数" を使用して情報にアクセスします。

関数が呼び出されると、次のタスクが実行されます。

- すべての実際の引数 (呼び出し元で指定されている) が評価されます。 これらの引数が評価される順序は決まっていませんが、すべての引数が評価され、関数に入る前にすべての副作用が完了します。

- それぞれの仮引数は、式リストの対応する実引数で初期化されます (仮引数は、関数ヘッダーで宣言され、関数の本体で使用される引数です。変換は、初期化によって行われるかのように行われます — 標準変換とユーザー定義変換の両方が、実際の引数を正しい型に変換する場合に実行されます。 実行された初期化を次のコードによって概念的に説明します。

    ```cpp
    void Func( int i ); // Function prototype
    ...
    Func( 7 );          // Execute function call
    ```

   呼び出しの前の概念的な初期化は次のとおりです。

    ```cpp
    int Temp_i = 7;
    Func( Temp_i );
    ```

   かっこ構文ではなく、等号構文を使用しているように初期化が実行されることに注意してください。 `i` のコピーは、関数に値を渡す前に作成されます (詳細については、「[初期化子](../cpp/initializers.md)と[変換](../cpp/user-defined-type-conversions-cpp.md)」を参照してください。

   したがって、関数プロトタイプ (宣言) が**long**型の引数を呼び出し、呼び出し元プログラムが実際の引数を**int**型に指定した場合、実際の引数は**標準型の**long 型への変換を使用してプロモートされます ([標準変換](../cpp/standard-conversions.md)を参照)。

   仮引数の型への標準変換またはユーザー定義変換がない実際の引数を指定するとエラーになります。

   クラス型の実引数では、仮引数はクラスのコンストラクターを呼び出すことによって初期化されます (これらの特殊なクラスメンバー関数の詳細については[、「コンストラクター](../cpp/constructors-cpp.md) 」を参照してください。

- 関数呼び出しが実行されます。

次のプログラムは関数呼び出しを示します。

```cpp
// expre_Formal_and_Actual_Arguments.cpp
void func( long param1, double param2 );

int main()
{
    long i = 1;
    double j = 2;

    // Call func with actual arguments i and j.
    func( i, j );
}

// Define func with formal parameters param1 and param2.
void func( long param1, double param2 )
{
}
```

main`func`から呼び出されると、仮`param1`パラメーターは`i`(`i`標準変換を使用して正しい型に対応するように**long**型に変換される) の値で`param2`初期化され、仮パラメーターは`j``j` (標準変換を使用して**double**型に変換される) の値で初期化されます。

## <a name="treatment-of-argument-types"></a>引数の型の処理

const 型として宣言された仮引数は、関数の本体内で変更できません。 関数は const**型以外**の引数を変更できます。 ただし、実際の引数が**const**型ではないオブジェクトへの参照でない場合、この変更は関数に対してローカルであり、実際の引数の値には影響しません。

次の関数はこれらの概念を示しています。

```cpp
// expre_Treatment_of_Argument_Types.cpp
int func1( const int i, int j, char *c ) {
   i = 7;   // C3892 i is const.
   j = i;   // value of j is lost at return
   *c = 'a' + j;   // changes value of c in calling function
   return i;
}

double& func2( double& d, const char *c ) {
   d = 14.387;   // changes value of d in calling function.
   *c = 'a';   // C3892 c is a pointer to a const object.
    return d;
}
```

## <a name="ellipsis-and-default-arguments"></a>省略記号と既定の引数

関数が関数定義で指定されているよりも少ない数の引数を受け取るには、省略記号 (`...`) を使用するか、既定の引数を使用します。

省略記号は、引数が必要である可能性がありますが、数と型が宣言で指定されないことを示します。 この方法は、C++ の利点の 1 つであるタイプ セーフが活用できないため、C++ のプログラミングとしてお勧めできません。 省略記号で宣言された関数には、正式な引数型と実引数型がわかっている関数とは異なる変換が適用されます。

- 実引数が**float**型の場合、関数呼び出しの前に**double**型に昇格されます。

- 符号付きまたは符号なし**char**型 **、short**型、またはビット フィールドは、整数昇格を使用して符号付きまたは符号なし**int**に変換されます。

- クラス型のすべての引数は、データ構造体として値渡しされます。またクラスのコピー コンストラクター (存在する場合) を起動するのではなく、バイナリのコピーによってコピーが作成されます。

省略記号を使用する場合は、引数リストの最後に宣言する必要があります。 可変個の引数の受け渡しの詳細については、『 ランタイム ライブラリ リファレンス 』の[「va_arg、va_start、およびva_list](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)の詳細」を*参照してください*。

CLR プログラミングの既定の引数の詳細については、「[変数引数リスト (..) (C++/CLI)」](../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md)を参照してください。

既定の引数では、関数呼び出しで引数を指定しない場合に、自動的に使用される引数の値を指定できます。 次のコード片では、既定の引数がどのように機能するかを示します。 既定の引数の指定に関する制限の詳細については、「[既定の引数](../cpp/default-arguments.md)」を参照してください。

```cpp
// expre_Ellipsis_and_Default_Arguments.cpp
// compile with: /EHsc
#include <iostream>

// Declare the function print that prints a string,
// then a terminator.
void print( const char *string,
            const char *terminator = "\n" );

int main()
{
    print( "hello," );
    print( "world!" );

    print( "good morning", ", " );
    print( "sunshine." );
}

using namespace std;
// Define print.
void print( const char *string, const char *terminator )
{
    if( string != NULL )
        cout << string;

    if( terminator != NULL )
        cout << terminator;
}
```

上のプログラムでは 2 個の引数を受け取る関数、`print` を宣言します。 ただし、2 番目の引数*であるターミネータ*には既定値`"\n"`があります。 では`main`、最初の 2`print`つの呼び出しにより、既定の 2 番目の引数が新しい行を指定して、印刷された文字列を終了できます。 3 番目の呼び出しでは、2 番目の引数の明示的な値が指定されます。 このプログラムによる出力は次のとおりです。

```Output
hello,
world!
good morning, sunshine.
```

## <a name="see-also"></a>関連項目

[式の型](../cpp/types-of-expressions.md)
