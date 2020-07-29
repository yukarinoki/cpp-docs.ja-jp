---
title: ユーザー定義型の変換 (C++)
ms.date: 11/04/2016
f1_keywords:
- explicit_cpp
helpviewer_keywords:
- constructors [C++], and constants
- conversion functions [C++]
- explicit keyword [C++]
- type conversion
- constructors [C++], drawbacks
- conversion constructors
- type conversion [C++], explicit conversion
- coercion [C++]
- conversions [C++], explicit
- objects [C++], converting
- conversion functions [C++], rules for declaring
- declaring functions [C++], conversion functions
- functions [C++], conversion
- converting objects
- constructors [C++], conversion
- conversions [C++], by constructors
- data type conversion [C++], explicit
ms.assetid: d40e4310-a190-4e95-a34c-22c5c20aa0b9
ms.openlocfilehash: e7889a7365a6b3a362804d3dad4b2fefc3780d01
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227037"
---
# <a name="user-defined-type-conversions-c"></a>ユーザー定義型の変換 (C++)

*変換*によって、異なる型の値から型の新しい値が生成されます。 *標準変換*は C++ 言語に組み込まれており、組み込み型をサポートしています。ユーザー定義の*変換*を作成して、ユーザー定義型との間で変換を実行することもできます。

標準変換は組み込み型の間、継承によって関連付けられる型へのポインターまたは参照の間、void ポインターを変換元または変換先として、および null ポインターを変換先として変換を実行します。 詳細については、「[標準変換](../cpp/standard-conversions.md)」を参照してください。 ユーザー定義変換はユーザー定義型の間、またはユーザー定義型と組み込み型の間で変換を実行します。 変換[コンストラクター](#ConvCTOR)または[変換関数](#ConvFunc)として実装できます。

変換は明示的 (キャストまたは直接の初期化などのように、ある型が別の型に変換されることをプログラマが要求するとき) または暗黙的 (プログラマによって指定された型と異なる型を言語またはプログラムが要求するとき) にすることができます。

暗黙的な変換は次の場合に試行されます。

- 関数に提供される引数が一致するパラメーターと同じ型を持たない。

- 関数から返される値が関数の戻り値の型と同じ型を持たない。

- 初期化子式が初期化されるオブジェクトと同じ型を持たない。

- 条件付きステートメント、ループ構造、またはスイッチを制御する式が制御に必要な結果の型を持たない。

- 演算子に提供されるオペランドが一致するオペランド パラメーターと同じ型を持たない。 組み込み演算子の場合、両方のオペランドは同じ型を持つ必要があり、両方を表す共通の型に変換されます。 詳細については、「[標準変換](standard-conversions.md)」を参照してください。 ユーザー定義演算子の場合、各オペランドは一致するオペランド パラメーターと同じ型を持つ必要があります。

1 つの標準変換が暗黙的な変換を完了できない場合、コンパイラはユーザー定義変換を使用し、その後オプションとして追加の標準変換を使用して変換を完了します。

同じ変換を実行する 2 つ以上のユーザー定義変換が変換サイトで使用可能な場合、変換はあいまいであると言われます。 コンパイラは使用可能な変換のどれを使用すべきか判別がつかないので、そうしたあいまいさはエラーになります。 ただし、ソース コード内の異なる場所で使用可能な変換のセットは異なることがあるので (たとえば、ソース ファイルに含まれるヘッダー ファイルに依存)、同じ変換を実行する複数の方法を定義するだけではエラーになりません。 変換サイトでただ 1 つの変換が使用可能である限り、あいまいさはありません。 あいまいな変換が発生する原因にはいくつかの可能性がありますが、最も一般的な原因は次の通りです。

- 多重継承。 変換が複数の基底クラスで定義されています。

- あいまいな関数呼び出し。 変換がターゲット型の変換コンストラクターとして、かつ、ソース型の変換関数として定義されています。 詳細については、「[変換関数](#ConvFunc)」を参照してください。

通常、関係する型の名前を完全に修飾するか、または目的を明確化するために明示的なキャストを実行するだけであいまいさを解決できます。

変換コンストラクターと変換関数は両方ともメンバー アクセス制御規則に従いますが、 変換のアクセシビリティは明確な変換が判別可能な場合にのみ考慮されます。 つまり、競合する変換のアクセス レベルによって使用できない可能性があっても、変換はあいまいになることがあります。 メンバーアクセシビリティの詳細については、「[メンバー Access Control](../cpp/member-access-control-cpp.md)」を参照してください。

## <a name="the-explicit-keyword-and-problems-with-implicit-conversion"></a>明示的なキーワードと暗黙的な変換の問題

既定では、ユーザー定義変換を作成すると、コンパイラはユーザー定義変換を使用して暗黙的な変換を実行できます。 これが目的の動作である場合もありますが、コンパイラに暗黙的な変換を作成させる単純な規則によって、不要なコードが受け入れられてしまうことがあります。

問題の原因となる可能性がある暗黙の変換の例の1つに、への変換が **`bool`** あります。 ブール値のコンテキストで使用できるクラス型を作成し、ステートメントまたはループの制御に使用できるようにするにはさまざまな理由があります **`if`** が、コンパイラが組み込み型へのユーザー定義の変換を実行するときに、コンパイラは、後で追加の標準変換を適用することができます。 この追加の標準変換は、からへの昇格などを可能にすることを目的としてい **`short`** **`int`** ますが、より明確でない変換のためのドアも開きます。たとえば、からへの変換では、 **`bool`** **`int`** 意図していない整数のコンテキストでクラス型を使用できます。 この特定の問題は、"*安全なブール*型の問題" と呼ばれています。 この種の問題は、 **`explicit`** キーワードが役に立ちます。

キーワードは、指定された変換を使用して **`explicit`** 暗黙的な変換を実行できないことをコンパイラに指示します。 キーワードが導入される前に暗黙的な変換の構文上の利便性を必要とした場合は **`explicit`** 、暗黙的な変換によって生じる可能性のある意図しない結果を受け入れるか、回避策として、より便利ではない名前付き変換関数を使用する必要がありました。 キーワードを使用することにより、 **`explicit`** 明示的なキャストまたは直接初期化の実行にのみ使用できる便利な変換を作成できます。これにより、例示の問題によって発生する問題の種類にはつながりません。

キーワードは、 **`explicit`** c++ 98 以降の変換コンストラクター、および c++ 11 以降の変換関数に適用できます。 次のセクションでは、キーワードを使用する方法の詳細について説明し **`explicit`** ます。

## <a name="conversion-constructors"></a><a name="ConvCTOR"></a>変換コンストラクター

変換コンストラクターはユーザー定義型または組み込み型からユーザー定義型への変換を定義します。 組み込み型からユーザー定義型に変換する変換コンストラクターの例を次に示し **`double`** `Money` ます。

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    Money(double _amount) : amount{ _amount } {};

    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << balance.amount << std::endl;
}

int main(int argc, char* argv[])
{
    Money payable{ 79.99 };

    display_balance(payable);
    display_balance(49.95);
    display_balance(9.99f);

    return 0;
}
```

関数 `display_balance` の最初の呼び出しは `Money` 型の引数を取り、引数は正しい型なので変換は必要ないことに注意してください。 ただし、の2回目の呼び出しでは、 `display_balance` 引数の型 ( **`double`** 値がの `49.95` ) が関数で予期されるものではないため、変換が必要です。 関数は、この値を直接使用することはできませんが、引数の型から一致するパラメーターの型への変換があるため、 **`double`** `Money` 型の一時値 `Money` は引数から構築され、関数呼び出しを完了するために使用されます。 の3番目の呼び出しでは、引数はではなく、値がであるであることに `display_balance` 注意 **`double`** してください。ただし、 **`float`** コンパイラが `9.99` 標準変換 (この場合はから) を実行してから、 **`float`** **`double`** からへのユーザー定義変換を実行して、 **`double`** `Money` 必要な変換を完了できるため、関数呼び出しを完了できます。

### <a name="declaring-conversion-constructors"></a>変換コンストラクターの宣言

次の規則は変換コンストラクターの宣言に適用されます。

- 変換のターゲット型は構築されるユーザー定義型です。

- 通常、変換コンストラクターは、ソース型を持つ、ただ 1 つの引数を取ります。 ただし、変換コンストラクターは追加パラメーターを指定できます (各追加パラメーターが既定値を持つ場合)。 ソース型は最初のパラメーターの型を維持します。

- 変換コンストラクターはすべてのコンストラクターと同様に戻り値の型を指定しません。 宣言内で戻り値の型を指定するとエラーになります。

- 変換コンストラクターは明示的にすることができます。

### <a name="explicit-conversion-constructors"></a>明示的な変換コンストラクター

変換コンストラクターをとして宣言することによって **`explicit`** 、オブジェクトを直接初期化する場合、または明示的なキャストを実行する場合にのみ使用できます。 これにより、このクラス型の引数を受け入れる関数が変換コンストラクターのソース型の引数も暗黙的に受け入れるのを防ぎ、クラス型がソース型の値からコピー初期化されるのを防ぎます。 次の例は、明示的な変換コンストラクターの定義方法とコードの整形における効果を示します。

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    explicit Money(double _amount) : amount{ _amount } {};

    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << balance.amount << std::endl;
}

int main(int argc, char* argv[])
{
    Money payable{ 79.99 };        // Legal: direct initialization is explicit.

    display_balance(payable);      // Legal: no conversion required
    display_balance(49.95);        // Error: no suitable conversion exists to convert from double to Money.
    display_balance((Money)9.99f); // Legal: explicit cast to Money

    return 0;
}
```

この例で、明示的な変換コンストラクターを使用して、`payable` の直接の初期化を実行できることに注意してください。 代わりに `Money payable = 79.99;` をコピー初期化しようとするとエラーになります。 `display_balance` の最初の呼び出しは引数が正しい型なので影響を受けません。 `display_balance` の 2 番目の呼び出しは、変換コンストラクターが暗黙的な変換を実行するために使用できないため、エラーになります。 への3番目の呼び出し `display_balance` は、への明示的なキャストに `Money` よって有効ですが、コンパイラはからへの暗黙的なキャストを挿入することによって、キャストの完了にも役立ち **`float`** **`double`** ます。

暗黙的な変換を許すことによる利便性は魅力的ですが、そうすると発見困難なバグを誘発する恐れがあります。 経験則では、特定の変換を暗黙的に発生させたいことが確かである場合を除き、すべての変換コンストラクターを明示的にすることです。

## <a name="conversion-functions"></a><a name="ConvFunc"></a>変換関数

変換関数はユーザー定義型から他の型への変換を定義します。 これらの関数は、値が異なる型にキャストされるときに、変換コンストラクターと共に呼び出されるため、「キャスト演算子」と呼ばれることがあります。 次の例は、ユーザー定義型から組み込み型への変換を行う変換関数を示してい `Money` **`double`** ます。

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    Money(double _amount) : amount{ _amount } {};

    operator double() const { return amount; }
private:
    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << balance << std::endl;
}
```

メンバー変数 `amount` がプライベートになり、型へのパブリック変換関数 **`double`** がの値を返すためにのみ導入されていることに注意して `amount` ください。 関数 `display_balance` では、ストリーム挿入演算子 `balance` を使用することにより、`<<` の値が標準出力にストリームされるときに暗黙的な変換が発生します。 ユーザー定義型にはストリーム挿入演算子が定義されていません `Money` が、組み込み型にはが1つあるため **`double`** 、コンパイラはからへの変換関数を使用して `Money` **`double`** ストリーム挿入演算子を満たすことができます。

変換関数は派生クラスによって継承されます。 派生クラスの変換関数は、完全に同じ型に変換する場合にのみ、継承された変換関数をオーバーライドします。 たとえば、派生クラス**operator int**のユーザー定義変換関数は、基本クラスの**演算子 short**のユーザー定義変換関数をオーバーライドしたり、影響を与えることはありません。これは、標準変換でとの変換関係を定義する場合でも同様 **`int`** **`short`** です。

### <a name="declaring-conversion-functions"></a>変換関数の宣言

次の規則は変換関数の宣言に適用されます。

- 変換のターゲット型は変換関数の宣言の前に宣言する必要があります。 クラス、構造体、列挙型、typedef は変換関数の宣言内で宣言できません。

    ```cpp
    operator struct String { char string_storage; }() // illegal
    ```

- 変換関数は引数を受け取りません。 宣言内でパラメーターを指定するとエラーになります。

- 変換関数は、変換関数の名前 (変換のターゲット型の名前でもあります) で指定される戻り値の型を持ちます。 宣言内で戻り値の型を指定するとエラーになります。

- 変換関数は仮想にすることができます。

- 変換関数は明示的にすることができます。

### <a name="explicit-conversion-functions"></a>明示的な変換関数

変換関数を明示的に宣言すると、明示的なキャストを実行するためだけに使用できます。 これにより、変換関数のターゲット型の引数を受け入れる関数がクラス型の引数も暗黙的に受け入れるのを防ぎ、ターゲット型のインスタンスがクラス型の値からコピー初期化されるのを防ぎます。 次の例は、明示的な変換関数の定義方法とコードの整形における効果を示します。

```cpp
#include <iostream>

class Money
{
public:
    Money() : amount{ 0.0 } {};
    Money(double _amount) : amount{ _amount } {};

    explicit operator double() const { return amount; }
private:
    double amount;
};

void display_balance(const Money balance)
{
    std::cout << "The balance is: " << (double)balance << std::endl;
}
```

ここで、変換関数の**演算子 double**が明示的になり、型への明示的なキャストが **`double`** 関数で導入され、 `display_balance` 変換が実行されました。 このキャストを省略すると、コンパイラは `<<` 型に対する適切なストリーム挿入演算子 `Money` を特定できず、エラーが発生します。
