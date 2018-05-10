---
title: ユーザー定義型変換 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- explicit_cpp
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfe76a74a46a6da48e22cc07232457f8c0957fbc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="user-defined-type-conversions-c"></a>ユーザー定義型の変換 (C++)
A*変換*値、別の種類のいくつかの型の新しい値を生成します。 *標準変換*、組み込み型できますを作成して、C++ 言語とサポートに組み込まれて*ユーザー定義の変換*から、またはユーザー定義型の間で変換を実行します。  
  
 標準変換は組み込み型の間、継承によって関連付けられる型へのポインターまたは参照の間、void ポインターを変換元または変換先として、および null ポインターを変換先として変換を実行します。 詳細については、次を参照してください。[標準変換](../cpp/standard-conversions.md)です。 ユーザー定義変換はユーザー定義型の間、またはユーザー定義型と組み込み型の間で変換を実行します。 可能な実装として[変換コンス トラクター](#ConvCTOR)か、または[変換関数](#ConvFunc)です。  
  
 変換は明示的 (キャストまたは直接の初期化などのように、ある型が別の型に変換されることをプログラマが要求するとき) または暗黙的 (プログラマによって指定された型と異なる型を言語またはプログラムが要求するとき) にすることができます。  
  
 暗黙的な変換は次の場合に試行されます。  
  
-   関数に提供される引数が一致するパラメーターと同じ型を持たない。  
  
-   関数から返される値が関数の戻り値の型と同じ型を持たない。  
  
-   初期化子式が初期化されるオブジェクトと同じ型を持たない。  
  
-   条件付きステートメント、ループ構造、またはスイッチを制御する式が制御に必要な結果の型を持たない。  
  
-   演算子に提供されるオペランドが一致するオペランド パラメーターと同じ型を持たない。 組み込み演算子の場合、両方のオペランドは同じ型を持つ必要があり、両方を表す共通の型に変換されます。 詳細については、次を参照してください。[標準変換](standard-conversions.md)です。 ユーザー定義演算子の場合、各オペランドは一致するオペランド パラメーターと同じ型を持つ必要があります。  
  
 1 つの標準変換が暗黙的な変換を完了できない場合、コンパイラはユーザー定義変換を使用し、その後オプションとして追加の標準変換を使用して変換を完了します。  
  
 同じ変換を実行する 2 つ以上のユーザー定義変換が変換サイトで使用可能な場合、変換はあいまいであると言われます。 コンパイラは使用可能な変換のどれを使用すべきか判別がつかないので、そうしたあいまいさはエラーになります。 ただし、ソース コード内の異なる場所で使用可能な変換のセットは異なることがあるので (たとえば、ソース ファイルに含まれるヘッダー ファイルに依存)、同じ変換を実行する複数の方法を定義するだけではエラーになりません。 変換サイトでただ 1 つの変換が使用可能である限り、あいまいさはありません。 あいまいな変換が発生する原因にはいくつかの可能性がありますが、最も一般的な原因は次の通りです。  
  
-   多重継承。 変換が複数の基底クラスで定義されています。 
  
-   あいまいな関数呼び出し。 変換がターゲット型の変換コンストラクターとして、かつ、ソース型の変換関数として定義されています。 詳細については、次を参照してください。[変換関数](#ConvFunc)です。  
  
 通常、関係する型の名前を完全に修飾するか、または目的を明確化するために明示的なキャストを実行するだけであいまいさを解決できます。  
  
 変換コンストラクターと変換関数は両方ともメンバー アクセス制御規則に従いますが、 変換のアクセシビリティは明確な変換が判別可能な場合にのみ考慮されます。 つまり、競合する変換のアクセス レベルによって使用できない可能性があっても、変換はあいまいになることがあります。 メンバーのアクセシビリティの詳細については、次を参照してください。[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)です。  
  
## <a name="the-explicit-keyword-and-problems-with-implicit-conversion"></a>明示的なキーワードと暗黙的な変換の問題  
 既定では、ユーザー定義変換を作成すると、コンパイラはユーザー定義変換を使用して暗黙的な変換を実行できます。 これが目的の動作である場合もありますが、コンパイラに暗黙的な変換を作成させる単純な規則によって、不要なコードが受け入れられてしまうことがあります。  
  
 問題を生じる可能性のある暗黙的な変換のよく知られた例の 1 つは `bool` への変換です。 さまざまな理由により、ブール値のコンテキストで使用可能なクラス型を作成することがありますが (たとえば、`if` ステートメントまたはループを制御するのに使用するためなど)、コンパイラが組み込み型へのユーザー定義変換を実行すると、コンパイラは追加の標準変換を後で適用できるようになります。 この追加の標準変換の目的は `short` から `int` への上位変換などを許可することですが、たとえば `bool` から `int` への変換といった明確でない変換の可能性を許すことになり、想定しなかった整数のコンテキストでクラス型が使用可能になります。 この特定の問題と呼ばれる、*安全な Bool 問題*です。 この種の問題には `explicit` キーワードが役立つことがあります。  
  
 `explicit` キーワードはコンパイラに対して、指定された変換が暗黙的な変換を実行するために使用できないことを伝えます。 `explicit` キーワードが導入される前は、暗黙的な変換の構文上の利便性を求める場合、暗黙的な変換によって生じる可能性がある意図しない結果を受け入れるか、回避策として利便性が低い、名前付き変換関数を使用する必要がありました。 現在は `explicit` キーワードを使用することで、明示的なキャストまたは直接の初期化を実行するためだけに使用可能で、安全なブール値問題に例示される種類の問題を生じることがない、便利な変換を作成できます。  
  
 `explicit` キーワードは、C++98 以降の変換コンストラクターと C++11 以降の変換関数に適用できます。 次のセクションでは `explicit` キーワードの使用方法についてさらに詳しく説明します。  
  
##  <a name="ConvCTOR"></a> 変換コンス トラクター  
 変換コンストラクターはユーザー定義型または組み込み型からユーザー定義型への変換を定義します。 次の例は組み込み型 `double` からユーザー定義型 `Money` への変換を行う変換コンストラクターを示します。  
  
```  
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
  
 関数 `display_balance` の最初の呼び出しは `Money` 型の引数を取り、引数は正しい型なので変換は必要ないことに注意してください。 ただし、2 つ目の呼び出し時に`display_balance`、変換が必要なため、引数の型、`double`の値を持つ`49.95`、されていないどのような関数が必要です。 関数はこの値を直接使用できませんが、引数の型 `double` から一致するパラメーターの型 `Money` への変換が存在するので、型 `Money` の一時的な値が引数から構築され、関数呼び出しを完了するために使用されます。 3 番目の呼び出しで`display_balance`、引数がないことを確認、`double`が代わりには、`float`の値を持つ`9.99`—、まだ関数呼び出しが完了できるよう、コンパイラは、標準の変換を実行できるため: ここでは、から`float`に`double`— してから、ユーザー定義の変換を実行して`double`に`Money`必要な変換を完了します。  
  
### <a name="declaring-conversion-constructors"></a>変換コンストラクターの宣言  
 次の規則は変換コンストラクターの宣言に適用されます。  
  
-   変換のターゲット型は構築されるユーザー定義型です。  
  
-   通常、変換コンストラクターは、ソース型を持つ、ただ 1 つの引数を取ります。 ただし、変換コンストラクターは追加パラメーターを指定できます (各追加パラメーターが既定値を持つ場合)。 ソース型は最初のパラメーターの型を維持します。  
  
-   変換コンストラクターはすべてのコンストラクターと同様に戻り値の型を指定しません。 宣言内で戻り値の型を指定するとエラーになります。  
  
-   変換コンストラクターは明示的にすることができます。  
  
### <a name="explicit-conversion-constructors"></a>明示的な変換コンストラクター  
 変換コンストラクターを `explicit` と宣言することにより、オブジェクトの直接の初期化を実行するか、明示的なキャストを実行するためにだけ使用できます。 これにより、このクラス型の引数を受け入れる関数が変換コンストラクターのソース型の引数も暗黙的に受け入れるのを防ぎ、クラス型がソース型の値からコピー初期化されるのを防ぎます。 次の例は、明示的な変換コンストラクターの定義方法とコードの整形における効果を示します。  
  
```  
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
  
 この例で、明示的な変換コンストラクターを使用して、`payable` の直接の初期化を実行できることに注意してください。 代わりに `Money payable = 79.99;` をコピー初期化しようとするとエラーになります。 `display_balance` の最初の呼び出しは引数が正しい型なので影響を受けません。 `display_balance` の 2 番目の呼び出しは、変換コンストラクターが暗黙的な変換を実行するために使用できないため、エラーになります。 `display_balance` の 3 番目の呼び出しは、`Money` への明示的なキャストのために有効ですが、コンパイラは `float` から `double` への暗黙的なキャストを挿入することで、キャストの完了を助けていることに注意してください。  
  
 暗黙的な変換を許すことによる利便性は魅力的ですが、そうすると発見困難なバグを誘発する恐れがあります。 経験則では、特定の変換を暗黙的に発生させたいことが確かである場合を除き、すべての変換コンストラクターを明示的にすることです。  
  
##  <a name="ConvFunc"></a> 変換関数  
 変換関数はユーザー定義型から他の型への変換を定義します。 これらの関数は、値が異なる型にキャストされるときに、変換コンストラクターと共に呼び出されるため、「キャスト演算子」と呼ばれることがあります。 次の例はユーザー定義型 `Money` から組み込み型 `double` への変換を行う変換関数を示します。  
  
```  
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
  
 メンバー変数 `amount` がプライベートになっていること、および、`double` の値を返すためだけに `amount` 型へのパブリック変換関数が導入されていることに注意してください。 関数 `display_balance` では、ストリーム挿入演算子 `balance` を使用することにより、`<<` の値が標準出力にストリームされるときに暗黙的な変換が発生します。 ユーザー定義型 `Money` にストリーム挿入演算子は定義されていませんが、組み込み型 `double` には定義されているので、コンパイラは `Money` から `double` への変換関数を使用し、ストリーム挿入演算子を満たすことができます。  
  
 変換関数は派生クラスによって継承されます。 派生クラスの変換関数は、完全に同じ型に変換する場合にのみ、継承された変換関数をオーバーライドします。 たとえば、派生クラス `operator int` のユーザー定義関数は基底クラス `operator short` のユーザー定義関数をオーバーライドをせず、影響も与えません (標準変換が `int` と `short` の間の変換関係を定義している場合でも同様)。  
  
### <a name="declaring-conversion-functions"></a>変換関数の宣言  
 次の規則は変換関数の宣言に適用されます。  
  
-   変換のターゲット型は変換関数の宣言の前に宣言する必要があります。 クラス、構造体、列挙型、typedef は変換関数の宣言内で宣言できません。  
  
    ```  
    operator struct String { char string_storage; }() // illegal  
    ```  
  
-   変換関数は引数を受け取りません。 宣言内でパラメーターを指定するとエラーになります。  
  
-   変換関数は、変換関数の名前 (変換のターゲット型の名前でもあります) で指定される戻り値の型を持ちます。 宣言内で戻り値の型を指定するとエラーになります。  
  
-   変換関数は仮想にすることができます。  
  
-   変換関数は明示的にすることができます。  
  
### <a name="explicit-conversion-functions"></a>明示的な変換関数  
 変換関数を明示的に宣言すると、明示的なキャストを実行するためだけに使用できます。 これにより、変換関数のターゲット型の引数を受け入れる関数がクラス型の引数も暗黙的に受け入れるのを防ぎ、ターゲット型のインスタンスがクラス型の値からコピー初期化されるのを防ぎます。 次の例は、明示的な変換関数の定義方法とコードの整形における効果を示します。  
  
```  
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
  
 ここで、変換関数 `operator double` は明示的で、`double` 型への明示的なキャストが関数 `display_balance` に導入され、変換を実行します。 このキャストを省略すると、コンパイラは `<<` 型に対する適切なストリーム挿入演算子 `Money` を特定できず、エラーが発生します。  
  
