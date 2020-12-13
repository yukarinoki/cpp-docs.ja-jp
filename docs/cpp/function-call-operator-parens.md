---
description: '詳細については、「関数呼び出し演算子: ()」を参照してください。'
title: '関数呼び出し演算子: ()'
ms.date: 06/11/2020
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
no-loc:
- opt
ms.openlocfilehash: 351674f345c7213a3c164ff88e9a165775088c68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344563"
---
# <a name="function-call-operator-"></a>関数呼び出し演算子: ()

関数呼び出しはの一種であり *`postfix-expression`* 、関数または呼び出し可能オブジェクトに評価され、その後に関数呼び出し演算子が続く式によって形成され **`()`** ます。 オブジェクトは、 `operator ()` オブジェクトの関数呼び出しのセマンティクスを提供する関数を宣言できます。

## <a name="syntax"></a>構文

> *`postfix-expression`*:\
> &emsp;*`postfix-expression`* **`(`** *`argument-expression-list`* <sub>opt</sub> **`)`**

## <a name="remarks"></a>解説

関数呼び出し演算子の引数は *`argument-expression-list`* 、式のコンマ区切りリストであるから取得されます。 これらの式の値は、引数として関数に渡されます。 *引数式リスト* は空にすることができます。 C++ 17 より前では、関数式と引数式の評価順序は指定されておらず、任意の順序で発生する可能性があります。 C++ 17 以降では、関数式は、引数式または既定の引数の前に評価されます。 引数の式は、不確定なシーケンスで評価されます。

は、 *`postfix-expression`* 呼び出す関数に評価されます。 次の形式のいずれかを使用できます。

- 現在のスコープ内、または指定された関数引数のスコープ内で参照できる関数識別子。
- 関数、関数ポインター、呼び出し可能オブジェクト、またはそのいずれかへの参照に評価される式。
- メンバー関数アクセサー (明示的または黙示)
- メンバー関数への逆参照されたポインター。

は、 *`postfix-expression`* オーバーロードされた関数識別子でも、オーバーロードされたメンバー関数アクセサーでもかまいません。 オーバーロードの解決規則によって、呼び出す実際の関数が決まります。 メンバー関数が virtual の場合、呼び出す関数は実行時に決定されます。

宣言の例を次に示します。

- 関数の戻り値の型 `T`。 以下に宣言例を示します。

    ```cpp
    T func( int i );
    ```

- 関数の戻り値の型へのポインター `T`。 以下に宣言例を示します。

    ```cpp
    T (*func)( int i );
    ```

- 関数の戻り値の型への参照 `T`。 以下に宣言例を示します。

    ```cpp
    T (&func)(int i);
    ```

- メンバー関数の逆参照戻り値の型へのポインター `T`。 以下に、関数呼び出しの例を示します。

    ```cpp
    (pObject->*pmf)();
    (Object.*pmf)();
    ```

## <a name="example"></a>例

次の例では、3 個の引数を持つ標準ライブラリ関数 `strcat_s` を呼び出しています。

```cpp
// expre_Function_Call_Operator.cpp
// compile with: /EHsc

#include <iostream>
#include <string>

// C++ Standard Library name space
using namespace std;

int main()
{
    enum
    {
        sizeOfBuffer = 20
    };

    char s1[ sizeOfBuffer ] = "Welcome to ";
    char s2[ ] = "C++";

    strcat_s( s1, sizeOfBuffer, s2 );

    cout << s1 << endl;
}
```

```Output
Welcome to C++
```

## <a name="function-call-results"></a>関数呼び出しの結果

関数呼び出しは、関数が参照型として宣言されていない限り、右辺値として評価されます。 参照戻り値の型を持つ関数は、左辺値に評価されます。 次に示すように、これらの関数は、代入ステートメントの左側で使用できます。

```cpp
// expre_Function_Call_Results.cpp
// compile with: /EHsc
#include <iostream>
class Point
{
public:
    // Define "accessor" functions as
    // reference types.
    unsigned& x() { return _x; }
    unsigned& y() { return _y; }
private:
    unsigned _x;
    unsigned _y;
};

using namespace std;
int main()
{
    Point ThePoint;

    ThePoint.x() = 7;           // Use x() as an l-value.
    unsigned y = ThePoint.y();  // Use y() as an r-value.

    // Use x() and y() as r-values.
    cout << "x = " << ThePoint.x() << "\n"
         << "y = " << ThePoint.y() << "\n";
}
```

上のコードでは、というクラスを定義し `Point` ています。これには、 *x* 座標と *y* 座標を表すプライベートデータオブジェクトが含まれています。 これらのデータ オブジェクトを変更し、値を取得する必要があります。 このプログラムは、このようなクラスのいくつかの設計の 1 つに過ぎません。`GetX` と `SetX` または `GetY` と `SetY` 関数を使う設計も可能です。

クラス型を返す関数、クラス型へのポインター、またはクラス型への参照は、メンバー選択演算子の左のオペランドとして使用できます。 次のコードは有効です。

```cpp
// expre_Function_Results2.cpp
class A {
public:
   A() {}
   A(int i) {}
   int SetA( int i ) {
      return (I = i);
   }

   int GetA() {
      return I;
   }

private:
   int I;
};

A func1() {
   A a = 0;
   return a;
}

A* func2() {
   A *a = new A();
   return a;
}

A& func3() {
   A *a = new A();
   A &b = *a;
   return b;
}

int main() {
   int iResult = func1().GetA();
   func2()->SetA( 3 );
   func3().SetA( 7 );
}
```

関数は再帰的に呼び出すことができます。 関数宣言の詳細については、「 [関数](functions-cpp.md)」を参照してください。 関連資料は [、翻訳単位およびリンケージ](../cpp/program-and-linkage-cpp.md)に含まれています。

## <a name="see-also"></a>関連項目

[後置式](../cpp/postfix-expressions.md)<br/>
[C++ の組み込み演算子、優先順位、および結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[関数呼び出し](../c-language/function-call-c.md)
