---
title: 関数のオーバーロード
ms.date: 03/27/2019
helpviewer_keywords:
- function overloading [C++], about function overloading
- function overloading
- declaring functions [C++], overloading
ms.assetid: 3c9884cb-1d5e-42e8-9a49-6f46141f929e
ms.openlocfilehash: a59c0e27a4500cb20ef42e9a55b4eb0004e07f65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368909"
---
# <a name="function-overloading"></a>関数のオーバーロード

C++ では、同じスコープ内で同じ名前の複数の関数を指定できます。 これらの関数は *、オーバーロードされた関数と*呼ばれます。 オーバーロードされた関数を使用すると、型と引数の数に応じて、関数に異なるセマンティクスを指定できます。

たとえば、`std::string`引数を`print`受け取る関数は **、double**型の引数を取るタスクとは大きく異なるタスクを実行する場合があります。 オーバーロードを行うと、 や などの名前を`print_string`使用`print_double`する必要が少なく。 コンパイラは、コンパイル時に、呼び出し元によって渡される引数の型に基づいて、使用するオーバーロードを選択します。  を呼び`print(42.0)`出すと、`void print(double d)`関数が呼び出されます。 を呼び`print("hello world")`出すと、`void print(std::string)`オーバーロードが呼び出されます。

メンバー関数と非メンバー関数の両方をオーバーロードできます。 次の表は、同じスコープ内の同じ名前を持つ関数を区別するために、C++ で関数宣言のどの部分が使用されるかをまとめたものです。

### <a name="overloading-considerations"></a>オーバーロードに関する考慮事項

|関数宣言要素|オーバーロードに使用されるかどうか|
|----------------------------------|---------------------------|
|関数の戻り値の型|いいえ|
|引数の数|はい|
|引数の型|はい|
|省略記号の有無|はい|
|**タイプ定義**名の使用|いいえ|
|未指定の配列の範囲|いいえ|
|**定数**または**揮発性**|はい(関数全体に適用される場合)|
|[参照修飾子](#ref-qualifiers)|はい|

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

既定の引数は、関数型の一部とは見なされません。 したがって、オーバーロードされた関数の選択では使用されません。 既定の引数のみが異なる 2 つの関数は、オーバーロードされた関数ではなく複数の定義と見なされます。

オーバーロードされた演算子に対して既定の引数を指定することはできません。

## <a name="argument-matching"></a>引数の一致

オーバーロード関数は、関数呼び出しで指定された引数に最も合った現在のスコープ内の関数宣言に対して選択します。 適切な関数がある場合、その関数が呼び出されます。 このコンテキストでの「適切」とは、次のいずれかを意味します。

- 厳密な一致が見つかりませんでした。

- 単純変換が実行されました。

- 整数の上位変換が実行されました。

- 目的の引数の型への標準変換が存在します。

- 目的の引数の型へのユーザー定義の変換 (変換演算子またはコンストラクター) が存在します。

- 省略記号によって表される引数が見つかりませんでした。

コンパイラは、引数ごとに候補関数のセットを作成します。 候補関数は、その位置の実引数を仮引数の型に変換できる関数です。

一連の "最も一致する関数" は各引数にビルドされ、選択した関数はすべての設定の交差部分です。 交差部分に複数の関数が含まれている場合、オーバーロードはあいまいで、エラーが生成されます。 最終的に選択された関数は、少なくとも 1 つの引数についてはグループ内のどの関数よりも優れた一致です。 勝者が明確になっていない場合、関数呼び出しはエラーを生成します。

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

|セット 1: Fraction 型の第 1 引数を持つ候補関数|セット 2: 2 番目の引数を型**int**に変換できる候補関数|
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
|バリアント 1|バリアント 1 (**int は**標準変換を使用して**long**に変換できます)|
|バリアント 3||

セット 2 の関数は、実パラメータ型から仮パラメータ型への暗黙の変換が行われる関数であり、そのような関数の中には、実際のパラメータ型を仮パラメータ型に変換する「コスト」が最小となる関数があります。

これら 2 つのセットの積集合は、バリアント 1 です。 あいまいな関数呼び出しの例は次のとおりです。

```cpp
F1 = Add( 3, 6 );
```

前の関数呼び出しは次のセットをビルドします。

|セット 1: 型**int**の最初の引数を持つ候補関数|セット 2: 型**int**の 2 番目の引数を持つ候補関数|
|---------------------------------------------------------------------|----------------------------------------------------------------------|
|バリアント 2 (**int は**標準変換を使用して**long**に変換できます)|バリアント 1 (**int は**標準変換を使用して**long**に変換できます)|

これら 2 つのセットの積集合が空であるため、コンパイラはエラー メッセージを生成します。

引数の一致の場合 *、n*のデフォルト引数を持つ関数は、それぞれ異なる数の引数を持つ*n*+1 の別個の関数として扱われます。

省略記号 (...) はワイルドカードとして機能します。これは任意の実際の引数と一致します。 オーバーロードされた関数セットを細心の注意を払って設計しないと、多くのあいまいなセットが生じる可能性があります。

> [!NOTE]
> オーバーロードされた関数のあいまいさは、関数呼び出しが発生するまでは判断できません。 その時点で、設定は関数呼び出しの引数ごとに構築され、明確なオーバーロードがあるかどうかを確認できます。 これは、それらが特定の関数呼び出しによって呼び出されるまで、コードにあいまいさが残ることを意味しています。

## <a name="argument-type-differences"></a>引数の型の違い

オーバーロード関数では、異なる初期化子を受け取る引数型が区別されます。 したがって、指定された型の引数とその型への参照は、オーバーロードの目的では同一であると見なされます。 これらが同一であると見なされるのは、同じ初期化子を受け取るためです。 たとえば、`max( double, double )` は `max( double &, double & )` と同じであると見なされます。 このような関数を 2 つ宣言すると、エラーが発生します。

同じ理由で **、const**または**volatile**によって変更された型の関数引数は、オーバーロードの目的で基本型と異なる処理を行いません。

ただし、関数オーバーロード機構は **、const**で修飾された参照と**volatile**で修飾された参照と基本型への参照を区別できます。 次のようなコードを作成できます。

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

### <a name="output"></a>出力

```Output
Over default constructor
Over&
Over default constructor
const Over&
Over default constructor
volatile Over&
```

**const**オブジェクトと**volatile**オブジェクトへのポインターは、オーバーロードの目的で基本型へのポインターとは異なると見なされます。

## <a name="argument-matching-and-conversions"></a>引数の一致と変換

コンパイラは、関数宣言の引数と実際の引数を照合するとき、厳密な一致が見つからない場合は、正しい型を取得するために標準またはユーザー定義の変換を指定できます。 変換は、次の規則に従って行われます。

- 複数のユーザー定義変換を含む変換のシーケンスは考慮されません。

- 中間変換を削除することによって簡略化できる変換のシーケンスは考慮されません。

変換の結果のシーケンスが存在する場合、それは最適な一致シーケンスと呼ばれます。 標準変換を使用して**int**型のオブジェクトを符号**なし long**型に変換する方法はいくつかあります ([標準変換](../cpp/standard-conversions.md)で説明)。

- **int**から**long**に変換してから、**長**い長い長**い長いから.**

- **int**から**符号なし長**に変換します。

最初のシーケンスは、目的の目標を達成しますが、最適な一致シーケンスではなく、短いシーケンスが存在します。

次の表は、どのシーケンスが最適な一致かの判断に一定の効果を持つ、単純変換と呼ばれる変換を示しています。 単純変換がシーケンスの選択に影響を与える例については、表の後で説明します。

### <a name="trivial-conversions"></a>単純変換

|変換前の型|変換後の型|
|-----------------------|---------------------|
|*タイプ名*|*タイプ名***&**|
|*タイプ名***&**|*タイプ名*|
|*タイプ名* **[ ]**|*タイプ名*__\*__|
|*型名* **(** *引数リスト* **)**|**(** __\*__ *型名* **) (** *引数リスト* **)**|
|*タイプ名*|**定数***型名*|
|*タイプ名*|**揮発性***型名*|
|*タイプ名*__\*__|**定数***型名*__\*__|
|*タイプ名*__\*__|**揮発性***型名*__\*__|

変換が試行されたシーケンスは次のとおりです。

1. 完全一致。 関数の呼び出しに使用された型と関数プロトタイプで宣言された型の完全な一致は、常に最適な一致です。 単純変換のシーケンスは、完全一致として分類されます。 ただし、これらの変換を行わないシーケンスは、変換するシーケンスよりも優れているとみなされます。

   - ポインターから **、const**へのポインター`type` <strong>\*</strong> ( const へのポインター ) を**指**`type`<strong>\*</strong>します。

   - ポインターから**volatile**へのポインター`type` <strong>\*</strong> (**揮発性への)**`type`<strong>\*</strong>へ。

   - 参照から **、const** `type` **&** ( const **)**`type`**&** への参照まで。

   - 参照から**揮発性(揮発性**)`type`**&****への参照**`type`**&** まで。

1. 上位変換を使用した一致。 整数のプロモーション **、float**から**double**への変換、および trivial 変換のみを含む完全一致として分類されないシーケンスは、プロモーションを使用して一致として分類されます。 完全一致による一致ほどではありませんが、標準変換を使用するより上位変換を使用する方が一致の程度が高くなります。

1. 標準変換を使用した一致。 完全一致としても、標準変換および単純変換だけを含む上位変換を使用した一致としても分類されないシーケンスは、標準変換を使用した一致として分類されます。 このカテゴリ内では、次の規則が適用されます。

   - 派生クラスへのポインターからの変換は、直接または間接の基本クラスへのポインターに`void *`変換する方がよいです。 `const void *`

   - 派生クラスへのポインターから基底クラスへのポインターに変換すると、基底クラスが直接基底クラスに近ければ近いほど、一致の程度が向上します。 次の図に示すクラスの階層構造を考えます。

![好ましいコンバージョンのグラフ](../cpp/media/vc391t1.gif "好ましいコンバージョンのグラフ") <br/>
好ましいコンバージョンを示すグラフ

`D*` 型から `C*` 型への変換は、`D*` 型から `B*` 型への変換よりも適しています。 同様に、`D*` 型から `B*` 型への変換は、`D*` 型から `A*` 型への変換よりも適しています。

この同じ規則が、参照変換に適用されます。 `D&` 型から `C&` 型への変換は、`D&` 型から `B&` 型への変換などよりも適しています。

この同じ規則は、ポインターからメンバーへの変換にも適用されます。 `T D::*` 型から `T C::*` 型への変換は、`T D::*` 型から `T B::*` 型への変換などよりも適しています (`T` はメンバーの型)。

上記の規則は、派生の特定のパスに沿ってのみ適用されます。 次の図に示すグラフについて考えます。

![優先変換を示す複数&#45;継承](../cpp/media/vc391t2.gif "優先変換を示す複数&#45;継承") <br/>
優先コンバージョンを示す多重継承グラフ

`C*` 型から `B*` 型への変換は、`C*` 型から `A*` 型への変換よりも適しています。 理由は、これらが同じパスにあり、`B*` の方が近いからです。 ただし、型から型`C*``D*`への変換は、型`A*`に変換する方が望ましいものではありません。変換は異なるパスに従うので、好みはありません。

1. ユーザー定義変換を使用した一致。 このシーケンスは、完全一致、プロモーションを使用した一致、または標準変換を使用した一致として分類することはできません。 このシーケンスには、ユーザー定義の変換、標準変換、またはユーザー定義の変換を使用した一致として分類される単純変換だけが含まれます。 ユーザー定義の変換による一致は、省略記号を含む一致より程度の高い一致と見なされますが、標準変換による一致ほど程度の高い一致とは見なされません。

1. 省略記号を使用した一致。 宣言内の省略記号に一致するシーケンスは、すべて省略記号による一致として分類されます。 これは、最も弱い試合と考えられています。

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

クラス`UDC`で使用できるユーザー定義変換は **、int**型および**long**型からの変換です。 したがって、コンパイラは照合対象のオブジェクトの型、`UDC` に応じて変換を検討します。 **int**への変換が存在し、選択されています。

引数の照合処理中は、引数とユーザー定義変換の結果の両方に標準変換を適用できます。 したがって、次のコードは機能します。

```cpp
void LogToFile( long l );
...
UDC udc;
LogToFile( udc );
```

前の例では、ユーザー定義の変換演算子**long**が呼び出され、型`udc`long**long**に変換されます。 ユーザー定義型への変換が**long**型に定義されていない場合、変換は次のように処理されます。 `UDC` **int** 次に、宣言の引数に一致するように、型**int**から**long**型への標準変換が適用されます。

引数に一致させるためにユーザー定義の変換が必要な場合、最適な一致を評価する際に標準変換は使用されません。 複数の候補関数がユーザー定義の変換を必要とする場合でも、関数は等しいと見なされます。 次に例を示します。

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

の`Func`どちらのバージョンも、型**int**をクラス型引数に変換するためにユーザー定義の変換を必要とします。 発生しうる変換は、次のとおりです。

- 型**int**から型`UDC1`(ユーザー定義の変換) に変換します。

- 型**int**から型を**long**型に変換します。その後、型`UDC2`に変換します (2 段階変換)。

2 つ目の変換では標準変換とユーザー定義変換の両方が必要ですが、2 つの変換は同じであると見なされます。

> [!NOTE]
> ユーザー定義の変換は、コンストラクションによる変換または初期化による変換 (変換関数) と見なされます。 どちらの方法も、最適一致を検討する際には等しいと判断されます。

## <a name="argument-matching-and-the-this-pointer"></a>引数一致と this ポインター

クラス メンバー関数は **、static**として宣言されているかどうかによって、異なる処理を行います。 非静的関数には**this**ポインターを提供する暗黙の引数があるため、非静的関数は静的関数よりも 1 つ多い引数を持つと見なされます。それ以外の場合は、同じように宣言されます。

これらの非静的メンバー関数では、**暗黙的なこの**ポインターが関数の呼び出し元のオブジェクト型と一致すること、またはオーバーロードされた演算子の場合は、最初の引数が演算子が適用されているオブジェクトと一致する必要があります。 (オーバーロードされた演算子の詳細については、「[オーバーロードされた演算子](../cpp/operator-overloading.md)」を参照してください。

オーバーロードされた関数の他の引数とは異なり **、this**ポインター引数と一致させようとすると、一時オブジェクトは導入されず、変換は試行されません。

メンバ選択`->`演算子を使用してクラス`class_name`のメンバー関数にアクセスする場合 **、this**ポインター引数の型は`class_name * const`です。 メンバーが**const**または**volatile**として宣言されている場合`const class_name * const`、`volatile class_name * const`型はそれぞれ および です。

`.` メンバー選択演算子は、暗黙の `&` (アドレス) 演算子がオブジェクト名の前に付けられている場合を除き、まったく同じ方法で動作します 次の例では、このしくみを説明します。

```cpp
// Expression encountered in code
obj.name

// How the compiler treats it
(&obj)->name
```

引数マッチングに関して、`->*` 演算子および `.*` (メンバーへのポインター) 演算子の左オペランドは `.` 演算子および `->` (メンバー選択) 演算子と同じ方法で処理されます。

## <a name="ref-qualifiers-on-member-functions"></a><a name="ref-qualifiers"></a>メンバー関数の参照修飾子

Ref 修飾子を使用すると、**この**オブジェクトが右辺値であるか左辺値であるかに基づいてメンバー関数をオーバーロードできます。  この機能を使用すると、データへのポインタ アクセスを提供しない場合に、不要なコピー操作を回避できます。 たとえば、クラス`C`がコンストラクタのデータを初期化し、そのデータのコピーをメンバ関数`get_data()`で返したとします。 型`C`のオブジェクトが破棄されようとしている右辺値である場合、コンパイラはオーバーロードを`get_data() &&`選択し、データをコピーするのではなく移動します。

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

## <a name="restrictions-on-overloading"></a>オーバーロードの制限

許容可能なオーバーロード関数のセットには複数の制限が適用されます。

- 一連のオーバーロードされた関数の 2 つの関数には、異なる引数リストが必要です。

- オーバーロードは、戻り値の型だけに基づいて同じ型の引数リストと共に機能するエラーです。

     **マイクロソフト固有**

戻り値の型に基づいてのみ、特に指定されたメモリ モデル修飾子に基づいて、**演算子**new をオーバーロードできます。

**エンド マイクロソフト 固有**

- メンバー関数は、静的な関数と非静的関数に基づいてオーバーロードすることはできません。

- **typedef**宣言は新しい型を定義しません。既存の型のシノニムを導入します。 オーバーロードメカニズムには影響しません。 次のコードについて考えてみましょう。

    ```cpp
    typedef char * PSTR;

    void Print( char *szToPrint );
    void Print( PSTR szToPrint );
    ```

   先行する 2 つの関数の引数リストはまったく同じです。 `PSTR`は型`char *`の同義語です。 メンバーのスコープでは、このコードによりエラーが発生します。

- 列挙型は別個の型です。また、オーバーロードされた関数を識別するために使用できます。

- "" と "ポインタ" の型は、オーバーロードされた関数を区別する目的で同一と見なされますが、単一の次元の配列に対してのみ使用できます。 そのため、これらのオーバーロードされた関数は競合し、エラー メッセージが生成されます。

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

クラスのスコープは厳密に守られます。したがって、基本クラスで宣言された関数は、派生クラスで宣言された関数と同じスコープ内にありません。 派生クラスの関数が、基本クラスの仮想関数と同じ名前で宣言されている場合、派生クラスの関数は基本クラスの関数を*オーバーライド*します。 詳細については、「[仮想関数](../cpp/virtual-functions.md)」を参照してください。

基本クラス関数が 'virtual' として宣言されていない場合、派生クラス関数はそれを*隠*していると言われます。 オーバーライドと隠ぺいは、オーバーロードとは異なります。

ブロックスコープは厳密に守られます。したがって、ファイル スコープで宣言された関数は、ローカルで宣言された関数と同じスコープ内にありません。 ローカルで宣言された関数の名前がファイル スコープで宣言された関数と同じ場合、ローカルで宣言された関数では、オーバーロードが発生する代わりに、ファイル スコープ関数を非表示にします。 次に例を示します。

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

前のコードは、関数 `func` からの 2 つの定義を示します。 extern ステートメントが原因で`char *`、型の`main`引数を受**extern**け取る定義はローカルです。 したがって **、int**型の引数を受け取る定義は非表示になり、最初の`func`呼び出しはエラーになります。

オーバーロードされたメンバー関数の場合は、関数の各バージョンにそれぞれ異なるアクセス権限を与えることができます。 これらは、依然として外側のクラスのスコープ内にあると見なされます。このため、オーバーロードされた関数です。 `Deposit` メンバー関数をオーバーロードしている次のコードを考えます。1 つのバージョンはパブリック、もう 1 つのバージョンはプライベートです。

このサンプルの目的は、預金を実行するために正しいパスワードが必要となる `Account` クラスを提供することです。 これは、オーバーロードを使用して行われます。

呼び出`Deposit`し`Account::Deposit`は、プライベート メンバー関数を呼び出します。 この呼び出し`Account::Deposit`は、メンバー関数であり、クラスのプライベート メンバーにアクセスできるため、正しい方法です。

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

## <a name="see-also"></a>関連項目

[関数 (C++)](../cpp/functions-cpp.md)
