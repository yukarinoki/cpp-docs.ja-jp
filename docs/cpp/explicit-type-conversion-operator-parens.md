---
title: '明示的な型変換演算子: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
ms.openlocfilehash: 079a3390df56ba55bd4d71a320faa249266abb54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189014"
---
# <a name="explicit-type-conversion-operator-"></a>明示的な型変換演算子: ()

C++ では、関数呼び出しの構文に似た構文を使用して、明示的な型変換を実行できます。

## <a name="syntax"></a>構文

```
simple-type-name ( expression-list )
```

## <a name="remarks"></a>解説

*単純型名*の後に、かっこで囲まれた*式リスト*が指定された式を使用して、指定された型のオブジェクトを構築します。 次の例は、int 型への明示的な型変換を示しています。

```cpp
int i = int( d );
```

`Point` クラスの例を次に示します。

## <a name="example"></a>例

```cpp
// expre_Explicit_Type_Conversion_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class Point
{
public:
    // Define default constructor.
    Point() { _x = _y = 0; }
    // Define another constructor.
    Point( int X, int Y ) { _x = X; _y = Y; }

    // Define "accessor" functions as
    // reference types.
    unsigned& x() { return _x; }
    unsigned& y() { return _y; }
    void Show()   { cout << "x = " << _x << ", "
                         << "y = " << _y << "\n"; }
private:
    unsigned _x;
    unsigned _y;
};

int main()
{
    Point Point1, Point2;

    // Assign Point1 the explicit conversion
    //  of ( 10, 10 ).
    Point1 = Point( 10, 10 );

    // Use x() as an l-value by assigning an explicit
    //  conversion of 20 to type unsigned.
    Point1.x() = unsigned( 20 );
    Point1.Show();

    // Assign Point2 the default Point object.
    Point2 = Point();
    Point2.Show();
}
```

## <a name="output"></a>Output

```Output
x = 20, y = 10
x = 0, y = 0
```

前の例では定数を使用した明示的な型変換を示しましたが、同じ手法でオブジェクトにこのような変換を実行しても、正常に動作します。 次のコードに、このことを示します。

```cpp
int i = 7;
float d;

d = float( i );
```

明示的な型変換は、"キャスト" 構文を使用して指定することもできます。 キャスト構文を使用して前の例を書き換えると、次のようになります。

```cpp
d = (float)i;
```

キャストでの変換も関数形式の変換も、1 つの値から変換する場合は同じ結果になります。 ただし、関数形式の構文では、変換に複数の引数を指定できます。 この違いは、ユーザー定義型の場合は重要です。 `Point` クラスとその変換を考えます。

```cpp
struct Point
{
    Point( short x, short y ) { _x = x; _y = y; }
    ...
    short _x, _y;
};
...
Point pt = Point( 3, 10 );
```

前の例では、関数形式の変換を使用して、2つの値 ( *x*と*y*の値) をユーザー定義型 `Point`に変換する方法を示しています。

> [!CAUTION]
>  明示的な型変換は C++ コンパイラの組み込みの型チェックをオーバーライドするため、慎重に使用してください。

*単純型名*(ポインター型や参照型など) を持たない型への変換には、[キャスト](../cpp/cast-operator-parens.md)表記を使用する必要があります。 *単純型名*で表現できる型への変換は、どちらの形式でも記述できます。

キャスト内の型定義は無効です。

## <a name="see-also"></a>参照

[後置式](../cpp/postfix-expressions.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
