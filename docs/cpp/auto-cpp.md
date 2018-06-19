---
title: 自動 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14ad8e7cb81df62156d35809853e1060107d7c90
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418225"
---
# <a name="auto-c"></a>自動 (C++)
宣言された変数の型を、その初期化式から推測します。  
  
## <a name="syntax"></a>構文  
  
```  
auto declarator initializer;  
```  
  
```  
[](auto param1, auto param2) {};  
```  
  
## <a name="remarks"></a>コメント  
 `auto` キーワードは、宣言された変数の初期化式、またはラムダ式のパラメーターを使用してその型を推測するようにコンパイラに指示します。  
  
 次のような利点があるので、実際に変換が必要な場合を除き、ほとんどの状況で `auto` キーワードを使用することをお勧めします。  
  
-   **保全性:** 式の型が変更された場合、関数の戻り値の型が変更されたときにこれが含まれています — それだけで動作します。  
  
-   **パフォーマンス:** があるない変換が保証されます。  
  
-   **使いやすさ:** 型名のスペルの難しさや入力ミスについて心配する必要はありません。  
  
-   **効率性:** コーディングは効率的であることができます。  
  
 `auto` を使用するのではなく、変換を行うのは、次のような場合です。  
  
-   特定の型が必要であり、他の型を使用できない場合。  
  
-   式テンプレート ヘルパー型 — たとえば、`(valarray+valarray)`です。  
  
 `auto` キーワードを使用するには、変数を宣言する型の代わりに使用し、初期化式を指定します。 また、`auto`、`const`、ポインター (`volatile`)、参照 (`*`)、および右辺値参照 `&`) などの指定子と宣言子を使用して、`(&&` キーワードを修飾できます。 コンパイラは初期化式を評価し、その情報を使用して変数の型を推測します。  
  
 初期化式が代入 (等号構文)、直接の初期化 (関数形式の構文) を指定できます、 [new 演算子](new-operator-cpp.md)式、または初期化式を指定できます、 *範囲の宣言の*内のパラメーター、[ステートメント (C++) の範囲に基づく](../cpp/range-based-for-statement-cpp.md)ステートメントです。 詳細については、次を参照してください。[初期化子](../cpp/initializers.md)と、このドキュメントで後でコードの例です。  
  
 `auto` キーワードは、型のプレースホルダーであり、それ自体が型ではありません。 したがって、`auto`キーワードでは使用できません演算子やキャストなど[sizeof](../cpp/sizeof-operator.md)と[typeid](../windows/typeid-cpp-component-extensions.md)です。  
  
## <a name="usefulness"></a>実用性  
 `auto` キーワードは、複雑な型を持つ変数を宣言する簡単な方法です。 たとえば、`auto` キーワードを使用して、初期化式にテンプレート、関数へのポインター、またはメンバーへのポインターが含まれる変数を宣言できます。  
  
 `auto` を使用して、ラムダ式の変数を宣言して初期化することもできます。 ラムダ式の型を認識できるのはコンパイラのみであるため、プログラマが変数の型を宣言することはできません。 詳細については、次を参照してください。[ラムダ式の例](../cpp/examples-of-lambda-expressions.md)です。  
  
## <a name="trailing-return-types"></a>後続の戻り値の型  
 テンプレート ライブラリの記述を支援するには、`auto` 型指定子と共に、`decltype` を使用します。 `auto` と `decltype` を使用して、テンプレートの引数の型に応じた戻り値の型を持つテンプレート関数を宣言します。 または、別の関数の呼び出しをラップするテンプレート関数を `auto` と `decltype` を使用して宣言し、その別の関数の戻り値の型を返します。 詳細については、次を参照してください。 [decltype](../cpp/decltype-cpp.md)です。  
  
## <a name="references-and-cv-qualifiers"></a>参照と cv 修飾子  
 `auto` を使用すると、参照、const 修飾子、および volatile 修飾子がなくなることに注意してください。 次に例を示します。  
  
```cpp  
// cl.exe /analyze /EHsc /W4  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
    int count = 10;  
    int& countRef = count;  
    auto myAuto = countRef;  
  
    countRef = 11;  
    cout << count << " ";  
  
    myAuto = 12;  
    cout << count << endl;  
}  
  
```  
  
 前の例では、myAuto は int、int 参照ではなく、出力は`11 11`ではなく、`11 12`がある場合の参照の修飾子が削除されていない場合、`auto`です。  
  
## <a name="type-deduction-with-braced-initializers-c14"></a>中かっこで囲んだ初期化子 (c++ 14) を含む型の推論  
 次のコード exmample は、中かっこを使用して自動変数を初期化する方法を示します。 B と C の間と A の間の違いに注意してくださいおよび E です。  
  
```cpp  
#include <initializer_list>  
  
int main()  
{  
    // std::initializer_list<int>  
    auto A = { 1, 2 };  
  
    // std::initializer_list<int>  
    auto B = { 3 };  
  
    // int  
    auto C{ 4 };  
  
    // C3535: cannot deduce type for 'auto' from initializer list'  
    auto D = { 5, 6.7 };  
  
    // C3518 in a direct-list-initialization context the type for 'auto'  
    // can only be deduced from a single initializer expression  
    auto E{ 8, 9 };  
  
    return 0;  
}  
```  
  
## <a name="restrictions-and-error-messages"></a>制限事項とエラー メッセージ  
 次の表は、`auto` キーワードの使用に関する制限事項と、それに対応してコンパイラによって生成される診断エラー メッセージの一覧です。  
  
|エラー番号|説明|  
|------------------|-----------------|  
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|`auto` キーワードを他の型指定子と組み合わせることはできません。|  
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|`auto` キーワードで宣言されたシンボルには初期化子が必要です。|  
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|`auto` キーワードを不適切に使用して型を宣言しました。 たとえば、メソッドの戻り値の型または配列を宣言しました。|  
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md)、 [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|パラメーターまたはテンプレート引数は `auto` キーワードで宣言することはできません。|  
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|メソッドまたはテンプレート パラメーターは `auto` キーワードで宣言することはできません。|  
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|シンボルは初期化前に使用することはできません。 実際には、変数はその変数自体を初期化するために使用できないことを意味します。|  
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|`auto` キーワードで宣言された型にはキャストできません。|  
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|`auto` キーワードで宣言されている宣言子リスト内のすべてのシンボルは、同じ型に解決する必要があります。 詳細については、次を参照してください。[宣言と定義](declarations-and-definitions-cpp.md)です。|  
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md)、 [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|[Sizeof](../cpp/sizeof-operator.md)と[typeid](../windows/typeid-cpp-component-extensions.md)演算子で宣言されたシンボルに適用することはできません、`auto`キーワード。|  
  
## <a name="examples"></a>使用例  
 以下のコード片は、`auto` キーワードを使用するためのいくつかの方法を示しています。  
  
 次の宣言は同等です。 最初のステートメントでは、変数 `j` は `int` 型として宣言されます。 2 番目のステートメントでは、初期化式 (0) が整数であるため、変数 `k` は型 `int` であると推測されます。  
  
```cpp  
int j = 0;  // Variable j is explicitly type int.  
auto k = 0; // Variable k is implicitly type int because 0 is an integer.  
```  
  
 次の宣言は同じ意味を持ちますが、2 番目の宣言の方が最初の宣言より単純です。 `auto` キーワードを使用する最も説得力のある理由の 1 つは簡潔さです。  
  
```cpp  
map<int,list<string>>::iterator i = m.begin();   
auto i = m.begin();   
```  
  
 次のコード片は、`iter` と範囲の `elem` ループが開始されるときに、変数 `for` と `for` の型を宣言します。  
  
```cpp  
// cl /EHsc /nologo /W4  
#include <deque>  
using namespace std;  
  
int main()  
{  
    deque<double> dqDoubleData(10, 0.1);  
  
    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)  
    { /* ... */ }  
  
    // prefer range-for loops with the following information in mind  
    // (this applies to any range-for with auto, not just deque)  
  
    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples  
    { /* ... */ }  
  
    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE  
    { /* ... */ }  
  
    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE  
    { /* ... */ }  
}  
```  
  
 次のコード片は、ポインターを宣言するために、`new` 演算子とポインター宣言を使用します。  
  
```cpp  
double x = 12.34;  
auto *y = new auto(x), **z = new auto(&x);  
```  
  
 次のコード片は各宣言ステートメントで複数のシンボルを宣言します。 各ステートメントのすべてのシンボルが同じ型に解決されることに注意してください。  
  
```cpp  
auto x = 1, *y = &x, **z = &y; // Resolves to int.  
auto a(2.01), *b (&a);         // Resolves to double.  
auto c = 'a', *d(&c);          // Resolves to char.  
auto m = 1, &n = m;            // Resolves to int.  
```  
  
 次のコード片は、値が 200 の整数として変数 `?:` を宣言するために、条件演算子 (`x`) を使用します。  
  
```cpp  
int v1 = 100, v2 = 200;  
auto x = v1 > v2 ? v1 : v2;  
```  
  
 次のコード フラグメントは、変数を初期化`x`を入力する`int`変数、`y`型への参照を`const int`、および変数`fp`型を返す関数へのポインターに`int`です。  
  
```cpp  
int f(int x) { return x; }  
int main()  
{  
    auto x = f(0);  
    const auto & y = f(1);  
    int (*p)(int x);  
    p = f;  
    auto fp = p;  
    //...  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../cpp/auto-keyword.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [/Zc:auto (変数の型の推測)](../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof 演算子](../cpp/sizeof-operator.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)   
 [new 演算子](new-operator-cpp.md)   
 [宣言と定義](declarations-and-definitions-cpp.md)   
 [ラムダ式の例](../cpp/examples-of-lambda-expressions.md)   
 [初期化子](../cpp/initializers.md)   
 [decltype](../cpp/decltype-cpp.md)