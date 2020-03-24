---
title: 関数のオーバーロード
ms.date: 03/27/2019
helpviewer_keywords:
- function overloading [C++], about function overloading
- function overloading
- declaring functions [C++], overloading
ms.assetid: 3c9884cb-1d5e-42e8-9a49-6f46141f929e
ms.openlocfilehash: fe390ae190f422f7951f7101a7c08808b1c6a526
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179784"
---
# <a name="function-overloading"></a>関数のオーバーロード

C++ では、同じスコープ内で同じ名前の複数の関数を指定できます。 これらの関数は、*オーバーロード*された関数と呼ばれます。 オーバーロードされた関数を使用すると、引数の型と数に応じて、関数に異なるセマンティクスを指定できます。

たとえば、`std::string` 引数を受け取る `print` 関数は、 **double**型の引数を受け取るものとはまったく異なるタスクを実行する場合があります。 オーバーロードを使用すると、`print_string` や `print_double`などの名前を使用する必要がなくなります。 コンパイル時に、コンパイラは、呼び出し元によって渡された引数の型に基づいて、使用するオーバーロードを選択します。  `print(42.0)`を呼び出すと、`void print(double d)` 関数が呼び出されます。 `print("hello world")`を呼び出すと、`void print(std::string)` のオーバーロードが呼び出されます。

メンバー関数と非メンバー関数の両方をオーバーロードすることができます。 次の表は、同じスコープ内の同じ名前を持つ関数を区別するために、C++ で関数宣言のどの部分が使用されるかをまとめたものです。

### <a name="overloading-considerations"></a>オーバーロードに関する考慮事項

|関数宣言要素|オーバーロードに使用されるかどうか|
|----------------------------------|---------------------------|
|関数の戻り値の型|いいえ|
|引数の数|はい|
|引数の型|はい|
|省略記号の有無|はい|
|**Typedef**名の使用|いいえ|
|未指定の配列の範囲|いいえ|
|**const**または**volatile**|はい (関数全体に適用される場合)|
|[Ref 修飾子](#ref-qualifiers)|はい|

## <a name="example"></a>例

次の例は、どのようにオーバーロードが使用できるかを示しています。

```cpp
// function_overloading.cpp
// compile with: /EHsc
#include <iostream>
#include <math.h>
#include <string>

// Prototype three print functions.
int print(std::string s);             // Print a string.
int print(double dvalue);            // Print a double.
int print(double dvalue, int prec);  // Print a double with a
                                     //  given precision.
using namespace std;
int main(int argc, char *argv[])
{
    const double d = 893094.2987;
    if (argc < 2)
    {
        // These calls to print invoke print( char *s ).
        print("This program requires one argument.");
        print("The argument specifies the number of");
        print("digits precision for the second number");
        print("printed.");
        exit(0);
    }

    // Invoke print( double dvalue ).
    print(d);

    // Invoke print( double dvalue, int prec ).
    print(d, atoi(argv[1]));
}

// Print a string.
int print(string s)
{
    cout << s << endl;
    return cout.good();
}

// Print a double in default precision.
int print(double dvalue)
{
    cout << dvalue << endl;
    return cout.good();
}

//  Print a double in specified precision.
//  Positive numbers for precision indicate how many digits
//  precision after the decimal point to show. Negative
//  numbers for precision indicate where to round the number
//  to the left of the decimal point.
int print(double dvalue, int prec)
{
    // Use table-lookup for rounding/truncation.
    static const double rgPow10[] = {
        10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1,
        10E0, 10E1,  10E2,  10E3,  10E4, 10E5,  10E6 };
    const int iPowZero = 6;

    // If precision out of range, just print the number.
    if (prec < -6 || prec > 7)
    {
        return print(dvalue);
    }
    // Scale, truncate, then rescale.
    dvalue = floor(dvalue / rgPow10[iPowZero - prec]) *
        rgPow10[iPowZero - prec];
    cout << dvalue << endl;
    return cout.good();
}
```

上記のコードは、ファイル スコープでの `print` 関数のオーバーロードを示しています。

既定の引数は、関数型の一部とは見なされません。 したがって、オーバーロードされた関数の選択には使用されません。 既定の引数のみが異なる 2 つの関数は、オーバーロードされた関数ではなく複数の定義と見なされます。

オーバーロードされた演算子に既定の引数を指定することはできません。

## <a name="argument-matching"></a>引数の一致

オーバーロード関数は、関数呼び出しで指定された引数に最も合った現在のスコープ内の関数宣言に対して選択します。 適切な関数がある場合、その関数が呼び出されます。 このコンテキストでの "適切" は、次のいずれかを意味します。

- 厳密な一致が見つかりませんでした。

- 単純変換が実行されました。

- 整数の上位変換が実行されました。

- 目的の引数の型への標準変換が存在します。

- 目的の引数の型へのユーザー定義の変換 (変換演算子またはコンストラクター) が存在します。

- 省略記号によって表される引数が見つかりませんでした。

コンパイラは、引数ごとに候補関数のセットを作成します。 候補関数は、その位置の実引数を仮引数の型に変換できる関数です。

一連の "最も一致する関数" は各引数にビルドされ、選択した関数はすべての設定の交差部分です。 交差部分に複数の関数が含まれている場合、オーバーロードはあいまいで、エラーが生成されます。 最終的に選択された関数は、少なくとも 1 つの引数についてはグループ内のどの関数よりも優れた一致です。 明確な勝者がない場合、関数呼び出しによってエラーが生成されます。

次の宣言を考えます (関数には、以下の説明での識別のために `Variant 1`、`Variant 2`、および `Variant 3` とマーク付けしています)。

```cpp
Fraction &Add( Fraction &f, long l );       // Variant 1
Fraction &Add( long l, Fraction &f );       // Variant 2
Fraction &Add( Fraction &f, Fraction &f );  // Variant 3

Fraction F1, F2;
```

次のステートメントを考えます。

```cpp
F1 = Add( F2, 23 );
```

前のステートメントは 2 つのセットをビルドします。

|セット 1: Fraction 型の第 1 引数を持つ候補関数|Set 2: 2 番目の引数を**Int**型に変換できる候補関数|
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
|バリアント 1|バリアント 1 (**int**は標準変換を使用して**long 型**に変換できます)|
|バリアント 3||

Set 2 の関数は、実際のパラメーターの型から仮パラメーターの型への暗黙的な変換が存在する関数であり、そのような関数の中には、実際のパラメーターの型を仮パラメーターの型に変換する "コスト" を使用する関数があります。うち.

これら 2 つのセットの積集合は、バリアント 1 です。 あいまいな関数呼び出しの例は次のとおりです。

```cpp
F1 = Add( 3, 6 );
```

前の関数呼び出しは次のセットをビルドします。

|Set 1: **Int**型の最初の引数を持つ候補関数|Set 2: **Int**型の2番目の引数を持つ候補関数|
|---------------------------------------------------------------------|----------------------------------------------------------------------|
|バリアント 2 (**int**は標準変換を使用して**long 型**に変換できます)|バリアント 1 (**int**は標準変換を使用して**long 型**に変換できます)|

これらの2つのセットの積集合が空であるため、コンパイラはエラーメッセージを生成します。

引数の一致では、既定の引数が*n*の関数は、それぞれ異なる引数を持つ*n*+ 1 個の個別の関数として扱われます。

省略記号 (...) はワイルドカードとして機能します。これは任意の実際の引数と一致します。 オーバーロードされた関数セットを慎重に設計しないと、多くのあいまいなセットが発生する可能性があります。

> [!NOTE]
>  オーバーロードされた関数のあいまいさは、関数呼び出しが検出されるまで判断できません。 その時点で、設定は関数呼び出しの引数ごとに構築され、明確なオーバーロードがあるかどうかを確認できます。 これは、それらが特定の関数呼び出しによって呼び出されるまで、コードにあいまいさが残ることを意味しています。

## <a name="argument-type-differences"></a>引数の型の違い

オーバーロード関数では、異なる初期化子を受け取る引数型が区別されます。 したがって、指定された型の引数とその型への参照は、オーバーロードの目的では同一であると見なされます。 これらが同一であると見なされるのは、同じ初期化子を受け取るためです。 たとえば、`max( double, double )` は `max( double &, double & )` と同じであると見なされます。 このような関数を 2 つ宣言すると、エラーが発生します。

同様の理由で、 **const**または**volatile**によって変更された型の関数引数は、オーバーロードのために基本型とは異なる方法で処理されません。

ただし、関数のオーバーロード機構では、 **const**と**volatile**で修飾された参照と基本型への参照を区別できます。 次のようなコードが可能になります。

```cpp
// argument_type_differences.cpp
// compile with: /EHsc /W3
// C4521 expected
#include <iostream>

using namespace std;
class Over {
public:
   Over() { cout << "Over default constructor\n"; }
   Over( Over &o ) { cout << "Over&\n"; }
   Over( const Over &co ) { cout << "const Over&\n"; }
   Over( volatile Over &vo ) { cout << "volatile Over&\n"; }
};

int main() {
   Over o1;            // Calls default constructor.
   Over o2( o1 );      // Calls Over( Over& ).
   const Over o3;      // Calls default constructor.
   Over o4( o3 );      // Calls Over( const Over& ).
   volatile Over o5;   // Calls default constructor.
   Over o6( o5 );      // Calls Over( volatile Over& ).
}
```

### <a name="output"></a>Output

```Output
Over default constructor
Over&
Over default constructor
const Over&
Over default constructor
volatile Over&
```

また、 **const**オブジェクトおよび**volatile**オブジェクトへのポインターは、オーバーロードのために基本型へのポインターとは異なるものと見なされます。

## <a name="argument-matching-and-conversions"></a>引数の一致と変換

コンパイラは、関数宣言の引数と実際の引数を照合するとき、厳密な一致が見つからない場合は、正しい型を取得するために標準またはユーザー定義の変換を指定できます。 変換は、次の規則に従って行われます。

- 複数のユーザー定義変換を含む変換のシーケンスは考慮されません。

- 中間変換を削除することによって簡略化できる変換のシーケンスは考慮されません。

変換の結果のシーケンスが存在する場合、それは最適な一致シーケンスと呼ばれます。 標準変換 (「[標準変換](../cpp/standard-conversions.md)」を参照) を使用して**int**型のオブジェクトを**unsigned long**型に変換するには、いくつかの方法があります。

- **Int**から**long**に、 **long**から**unsigned long**に変換します。

- **Int**から**unsigned long**に変換します。

最初のシーケンスは目的の目標を達成しますが、最も一致するシーケンスではなく、短いシーケンスが存在します。

次の表は、どのシーケンスが最適な一致かの判断に一定の効果を持つ、単純変換と呼ばれる変換を示しています。 単純変換がシーケンスの選択に影響を与える例については、表の後で説明します。

### <a name="trivial-conversions"></a>単純変換

|変換前の型|変換後の型|
|-----------------------|---------------------|
|*型名*|*型名* **&**|
|*型名* **&**|*型名*|
|*型名* **[]**|*型名* __\*__|
|*型名* **(** *引数リスト* **)**|**(** __\*__ *型名* **) (** *引数リスト* **)**|
|*型名*|**const** *型-名前*|
|*型名*|**volatile** *型名*|
|*型名* __\*__|**const** *型名* __\*__|
|*型名* __\*__|**volatile** *型名* __\*__|

変換が試行されたシーケンスは次のとおりです。

1. 完全一致。 関数の呼び出しに使用された型と関数プロトタイプで宣言された型の完全な一致は、常に最適な一致です。 単純変換のシーケンスは、完全一致として分類されます。 ただし、これらの変換を行わないシーケンスは、次のような変換を行うシーケンスよりも優れていると見なされます。

   - ポインターから**const**へのポインターに (`type` <strong>\*</strong>を**const** `type` <strong>\*</strong>) にします。

   - ポインターから、 **volatile**へのポインター (`type` <strong>\*</strong> **volatile** `type` <strong>\*</strong>)。

   - 参照から、 **const** (`type` **&** を**const** `type` **&** ) に参照します。

   - 参照から**volatile**への参照 (`type` **&** **volatile** `type` **&** )。

1. 上位変換を使用した一致。 整数の上位変換、 **float**から**double**への変換、および自明な変換だけを含む完全一致として分類されていないシーケンスは、昇格を使用して一致として分類されます。 完全一致による一致ほどではありませんが、標準変換を使用するより上位変換を使用する方が一致の程度が高くなります。

1. 標準変換を使用した一致。 完全一致としても、標準変換および単純変換だけを含む上位変換を使用した一致としても分類されないシーケンスは、標準変換を使用した一致として分類されます。 このカテゴリ内では、次の規則が適用されます。

   - 派生クラスへのポインターから直接または間接基底クラスへのポインターへの変換は、`void *` または `const void *`への変換よりも適しています。

   - 派生クラスへのポインターから基底クラスへのポインターに変換すると、基底クラスが直接基底クラスに近ければ近いほど、一致の程度が向上します。 次の図に示すクラスの階層構造を考えます。

![優先される変換のグラフ](../cpp/media/vc391t1.gif "優先される変換のグラフ") <br/>
優先される変換を示すグラフ

`D*` 型から `C*` 型への変換は、`D*` 型から `B*` 型への変換よりも適しています。 同様に、`D*` 型から `B*` 型への変換は、`D*` 型から `A*` 型への変換よりも適しています。

この同じ規則が、参照変換に適用されます。 `D&` 型から `C&` 型への変換は、`D&` 型から `B&` 型への変換などよりも適しています。

この同じ規則は、ポインターからメンバーへの変換にも適用されます。 `T D::*` 型から `T C::*` 型への変換は、`T D::*` 型から `T B::*` 型への変換などよりも適しています (`T` はメンバーの型)。

上記の規則は、派生の特定のパスに沿ってのみ適用されます。 次の図に示すグラフについて考えます。

![優先&#45;される変換を示す多重継承](../cpp/media/vc391t2.gif "優先&#45;される変換を示す多重継承") <br/>
優先変換を示す多重継承グラフ

`C*` 型から `B*` 型への変換は、`C*` 型から `A*` 型への変換よりも適しています。 理由は、これらが同じパスにあり、`B*` の方が近いからです。 ただし、型 `C*` から型 `D*` への変換は `A*`型への変換には適していません。変換は異なるパスに従っているため、設定はありません。

1. ユーザー定義変換を使用した一致。 このシーケンスは、完全一致、昇格を使用した一致、または標準変換を使用した一致として分類することはできません。 このシーケンスには、ユーザー定義の変換、標準変換、またはユーザー定義の変換を使用した一致として分類される単純変換だけが含まれます。 ユーザー定義の変換による一致は、省略記号を含む一致より程度の高い一致と見なされますが、標準変換による一致ほど程度の高い一致とは見なされません。

1. 省略記号を使用した一致。 宣言内の省略記号に一致するシーケンスは、すべて省略記号による一致として分類されます。 最も弱い一致と見なされます。

組み込みの上位変換または変換が存在しない場合、ユーザー定義の変換が適用されます。 これらの変換は照合する引数の型に基づいて選択されます。 次のコードについて考えてみましょう。

```cpp
// argument_matching1.cpp
class UDC
{
public:
   operator int()
   {
      return 0;
   }
   operator long();
};

void Print( int i )
{
};

UDC udc;

int main()
{
   Print( udc );
}
```

クラス `UDC` に使用できるユーザー定義変換は、 **int**型および**long**型です。 したがって、コンパイラは照合対象のオブジェクトの型、`UDC` に応じて変換を検討します。 **Int 型**への変換が存在し、選択されています。

引数の照合処理中は、引数とユーザー定義変換の結果の両方に標準変換を適用できます。 したがって、次のコードは機能します。

```cpp
void LogToFile( long l );
...
UDC udc;
LogToFile( udc );
```

前の例では、ユーザー定義の変換**演算子 long**を呼び出して、`udc` を**long**型に変換しています。 **Long**型へのユーザー定義の変換が定義されていない場合、変換は次のように処理されます。型 `UDC` は、ユーザー定義の変換を使用して**int**型に変換されます。 次に、 **int**型から**long**型への標準変換が適用され、宣言の引数と一致するようになります。

引数に一致する必要があるユーザー定義の変換がある場合、最適な一致を評価する際に標準変換は使用されません。 複数の候補関数でユーザー定義の変換が必要な場合でも、関数は等しいと見なされます。 次に例を示します。

```cpp
// argument_matching2.cpp
// C2668 expected
class UDC1
{
public:
   UDC1( int );  // User-defined conversion from int.
};

class UDC2
{
public:
   UDC2( long ); // User-defined conversion from long.
};

void Func( UDC1 );
void Func( UDC2 );

int main()
{
   Func( 1 );
}
```

どちらのバージョンの `Func` でも、型**int**をクラス型引数に変換するには、ユーザー定義の変換が必要です。 発生しうる変換は、次のとおりです。

- **Int**型から `UDC1` 型 (ユーザー定義の変換) に変換します。

- **Int**型から**long**型に変換します。次に、型 `UDC2` (2 段階の変換) に変換します。

2番目の変換では、標準変換とユーザー定義変換の両方が必要ですが、2つの変換は等価と見なされます。

> [!NOTE]
>  ユーザー定義の変換は、コンストラクションによる変換または初期化による変換 (変換関数) と見なされます。 どちらの方法も、最適一致を検討する際には等しいと判断されます。

## <a name="argument-matching-and-the-this-pointer"></a>引数一致と this ポインター

クラスメンバー関数は、 **static**として宣言されているかどうかによって、異なる方法で処理されます。 非静的関数には**this**ポインターを提供する暗黙の引数があるため、非静的関数は静的関数よりも1つ多くの引数を持つと見なされます。それ以外の場合は、同じように宣言されます。

これらの非静的メンバー関数では、暗黙的な**this**ポインターが関数の呼び出しに使用されるオブジェクト型と一致する必要があります。または、オーバーロードされた演算子の場合は、最初の引数が、演算子が適用されるオブジェクトと一致する必要があります。 (オーバーロードされた演算子の詳細については、「オーバーロードされた[演算子](../cpp/operator-overloading.md)」を参照してください)。

オーバーロードされた関数の他の引数とは異なり、一時オブジェクトは導入されず、**この**ポインター引数を照合しようとしても変換は試行されません。

`->` メンバー選択演算子を使用して `class_name`クラスのメンバー関数にアクセスする場合、 **this**ポインター引数の型は `class_name * const`になります。 メンバーが**const**または**volatile**として宣言されている場合、それぞれの型が `const class_name * const` され、`volatile class_name * const`ます。

`.` メンバー選択演算子は、暗黙の `&` (アドレス) 演算子がオブジェクト名の前に付けられている場合を除き、まったく同じ方法で動作します 次の例では、このしくみを説明します。

```cpp
// Expression encountered in code
obj.name

// How the compiler treats it
(&obj)->name
```

引数マッチングに関して、`->*` 演算子および `.*` (メンバーへのポインター) 演算子の左オペランドは `.` 演算子および `->` (メンバー選択) 演算子と同じ方法で処理されます。

## <a name="ref-qualifiers-on-member-functions"></a><a name="ref-qualifiers"></a>メンバー関数に対する Ref 修飾子

Ref 修飾子を使用すると、**この**が指すオブジェクトが右辺値または左辺値のどちらであるかに基づいて、メンバー関数をオーバーロードすることができます。  この機能を使用すると、データへのポインターアクセスを提供しない場合に、不要なコピー操作を避けることができます。 たとえば、クラス `C` コンストラクターの一部のデータを初期化し、そのデータのコピーをメンバー関数 `get_data()`に返すとします。 `C` 型のオブジェクトが、破棄される右辺値である場合、コンパイラは、データをコピーするのではなく移動する `get_data() &&` のオーバーロードを選択します。

```cpp
#include <iostream>
#include <vector>

using namespace std;

class C
{

public:
    C() {/*expensive initialization*/}
    vector<unsigned> get_data() &
    {
        cout << "lvalue\n";
        return _data;
    }
    vector<unsigned> get_data() &&
    {
        cout << "rvalue\n";
        return std::move(_data);
    }

private:
    vector<unsigned> _data;
};

int main()
{
    C c;
    auto v = c.get_data(); // get a copy. prints "lvalue".
    auto v2 = C().get_data(); // get the original. prints "rvalue"
    return 0;
}
```

## <a name="restrictions-on-overloading"></a>オーバーロードに関する制限事項

許容可能なオーバーロード関数のセットには複数の制限が適用されます。

- 一連のオーバーロードされた関数の 2 つの関数には、異なる引数リストが必要です。

- オーバーロードは、戻り値の型だけに基づいて同じ型の引数リストと共に機能するエラーです。

     **Microsoft 固有の仕様**

戻り値の型に基づいて、特に指定されたメモリモデル修飾子に基づいて、 **operator new**をオーバーロードできます。

**Microsoft 固有の仕様はここまで**

- メンバー関数は、静的であるか、もう一方が非静的であるかに基づいてのみオーバーロードすることはできません。

- **typedef**宣言では新しい型が定義されません。既存の型に対してシノニムを導入します。 オーバーロード機構には影響しません。 次のコードについて考えてみましょう。

    ```cpp
    typedef char * PSTR;

    void Print( char *szToPrint );
    void Print( PSTR szToPrint );
    ```

   先行する 2 つの関数の引数リストはまったく同じです。 `PSTR` は `char *`型のシノニムです。 メンバーのスコープでは、このコードによりエラーが発生します。

- 列挙型は別個の型です。また、オーバーロードされた関数を識別するために使用できます。

- オーバーロードされた関数を区別するために型 "array of" と "pointer to" は同一であると見なされますが、1次元の配列に限定されます。 そのため、これらのオーバーロードされた関数が競合し、エラーメッセージが生成されます。

    ```cpp
    void Print( char *szToPrint );
    void Print( char szToPrint[] );
    ```

   次元配列の乗算では、2 番目以降のすべてのディメンションは、型の一部と見なされます。 したがって、オーバーロードされた関数を識別するために使用されます。

    ```cpp
    void Print( char szToPrint[] );
    void Print( char szToPrint[][7] );
    void Print( char szToPrint[][9][42] );
    ```

## <a name="overloading-overriding-and-hiding"></a>オーバーロード、オーバーライド、および非表示

同じスコープ内で同じ名前の 2 つの関数宣言は、同じ関数またはオーバーロードされる 2 種類の関数を参照できます。 宣言の引数リストに (前のセクションで説明したように) 型が同じ引数が含まれている場合、関数宣言は同じ関数を参照しています。 それ以外の場合は、オーバーロードを使用して選択された 2 つの異なる関数を参照します。

クラススコープは厳密に観察されます。したがって、基底クラスで宣言された関数は、派生クラスで宣言された関数と同じスコープ内にありません。 派生クラスの関数が基底クラスの仮想関数と同じ名前で宣言されている場合、派生クラスの関数は基底クラスの関数を*オーバーライド*します。 詳細については、「[仮想関数](../cpp/virtual-functions.md)」を参照してください。

基底クラスの関数が ' virtual ' として宣言されていない場合、派生クラスの関数は*非表示*になります。 オーバーライドと非表示はどちらもオーバーロードとは異なります。

ブロックスコープは厳密に観察されます。このため、ファイルスコープで宣言された関数は、ローカルで宣言された関数と同じスコープ内にありません。 ローカルで宣言された関数の名前がファイル スコープで宣言された関数と同じ場合、ローカルで宣言された関数では、オーバーロードが発生する代わりに、ファイル スコープ関数を非表示にします。 次に例を示します。

```cpp
// declaration_matching1.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
void func( int i )
{
    cout << "Called file-scoped func : " << i << endl;
}

void func( char *sz )
{
   cout << "Called locally declared func : " << sz << endl;
}

int main()
{
   // Declare func local to main.
   extern void func( char *sz );

   func( 3 );   // C2664 Error. func( int ) is hidden.
   func( "s" );
}
```

前のコードは、関数 `func` からの 2 つの定義を示します。 `char *` 型の引数を受け取る定義は、 **extern**ステートメントが原因で `main` に対してローカルです。 したがって、 **int**型の引数を受け取る定義は非表示になり、`func` の最初の呼び出しはエラーになります。

オーバーロードされたメンバー関数の場合は、関数の各バージョンにそれぞれ異なるアクセス権限を与えることができます。 これらは、依然として外側のクラスのスコープ内にあると見なされます。このため、オーバーロードされた関数です。 `Deposit` メンバー関数をオーバーロードしている次のコードを考えます。1 つのバージョンはパブリック、もう 1 つのバージョンはプライベートです。

このサンプルの目的は、預金を実行するために正しいパスワードが必要となる `Account` クラスを提供することです。 これは、オーバーロードを使用して行われます。

`Account::Deposit` 内の `Deposit` を呼び出すと、プライベートメンバー関数が呼び出されます。 `Account::Deposit` はメンバー関数であり、クラスのプライベートメンバーにアクセスできるため、この呼び出しは正しいです。

```cpp
// declaration_matching2.cpp
class Account
{
public:
   Account()
   {
   }
   double Deposit( double dAmount, char *szPassword );

private:
   double Deposit( double dAmount )
   {
      return 0.0;
   }
   int Validate( char *szPassword )
   {
      return 0;
   }

};

int main()
{
    // Allocate a new object of type Account.
    Account *pAcct = new Account;

    // Deposit $57.22. Error: calls a private function.
    // pAcct->Deposit( 57.22 );

    // Deposit $57.22 and supply a password. OK: calls a
    //  public function.
    pAcct->Deposit( 52.77, "pswd" );
}

double Account::Deposit( double dAmount, char *szPassword )
{
   if ( Validate( szPassword ) )
      return Deposit( dAmount );
   else
      return 0.0;
}
```

## <a name="see-also"></a>参照

[関数 (C++)](../cpp/functions-cpp.md)
