---
title: '関数呼び出し演算子: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
ms.openlocfilehash: 79c43ed11bfc73ec4bfaedad0a20b45fb6ca1ffb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676253"
---
# <a name="function-call-operator-"></a>関数呼び出し演算子: ()

後置式の後ろに関数呼び出し演算子 **()**、関数呼び出しを指定します。

## <a name="syntax"></a>構文

```
postfix-expression
( [argument-expression-list ] )
```

## <a name="remarks"></a>Remarks

関数呼び出し演算子への引数は、コンマで区切ったゼロ個以上の式 (関数への実引数) です。

*後置式*関数のアドレス (たとえば、関数の識別子または関数ポインターの値) に評価される必要がありますと*引数式リスト*(区切られた式の一覧を示しますコンマ) で値を持つ (引数) は、関数に渡されます。 *argument-expression-list* 引数は空の場合もあります。

*後置式*これらの型のいずれかを指定する必要があります。

- 関数の戻り値の型 `T`。 以下に宣言例を示します。

    ```cpp
    T func( int i )
    ```

- 関数の戻り値の型へのポインター `T`。 以下に宣言例を示します。

    ```cpp
    T (*func)( int i )
    ```

- 関数の戻り値の型への参照 `T`。 以下に宣言例を示します。

    ```cpp
    T (&func)(int i)
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

関数呼び出しは、関数が参照型として宣言されていない限り結果が r 値になります。 参照の戻り値の型を持つ関数は左辺値に評価され、次のように代入ステートメントの左側で使用できます。

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

上記のコードと呼ばれるクラスを定義する`Point`、プライベート データを含むオブジェクトを表す*x*と*y*座標。 これらのデータ オブジェクトを変更し、値を取得する必要があります。 このプログラムは、このようなクラスのいくつかの設計の 1 つに過ぎません。`GetX` と `SetX` または `GetY` と `SetY` 関数を使う設計も可能です。

クラス型を返す関数、クラス型へのポインター、またはクラス型への参照は、メンバー選択演算子の左のオペランドとして使用できます。 したがって、次のコードは有効です。

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

関数は再帰的に呼び出すことができます。 関数の宣言に関する詳細については、[関数](functions-cpp.md)を参照してください。 関連資料は[プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)します。

## <a name="see-also"></a>関連項目

[後置式](../cpp/postfix-expressions.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[関数呼び出し](../c-language/function-call-c.md)