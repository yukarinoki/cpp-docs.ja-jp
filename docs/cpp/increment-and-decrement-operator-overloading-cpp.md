---
description: 詳細については、「インクリメントとデクリメント演算子のオーバーロード (C++)」を参照してください。
title: インクリメント演算子とデクリメント演算子のオーバーロード (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
ms.openlocfilehash: f2704a1c10375bf8422324d90f41c6e3ac245505
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113923"
---
# <a name="increment-and-decrement-operator-overloading-c"></a>インクリメント演算子とデクリメント演算子のオーバーロード (C++)

インクリメント演算子とデクリメント演算子は、それぞれに次の 2 種類のバリアントがあるため、特別なカテゴリに分類されています。

- 前置インクリメントと後置インクリメント

- 前置デクリメントと後置デクリメント

オーバーロードされた演算子関数を記述する場合、これらの演算子の前置バージョンと後置バージョン用に別々のバージョンを実装すると便利です。 2つを区別するために、次の規則が確認されています。演算子のプレフィックス形式は、他の単項演算子とまったく同じように宣言されています。後置形式では、型の追加の引数を受け取り **`int`** ます。

> [!NOTE]
> 後置形式のインクリメント演算子またはデクリメント演算子にオーバーロードされた演算子を指定する場合、追加の引数は型である必要があります **`int`** 。他の型を指定するとエラーが生成されます。

次の例に、`Point` クラスに対して前置および後置のインクリメント演算子とデクリメント演算子を定義する方法を示します。

```cpp
// increment_and_decrement1.cpp
class Point
{
public:
   // Declare prefix and postfix increment operators.
   Point& operator++();       // Prefix increment operator.
   Point operator++(int);     // Postfix increment operator.

   // Declare prefix and postfix decrement operators.
   Point& operator--();       // Prefix decrement operator.
   Point operator--(int);     // Postfix decrement operator.

   // Define default constructor.
   Point() { _x = _y = 0; }

   // Define accessor functions.
   int x() { return _x; }
   int y() { return _y; }
private:
   int _x, _y;
};

// Define prefix increment operator.
Point& Point::operator++()
{
   _x++;
   _y++;
   return *this;
}

// Define postfix increment operator.
Point Point::operator++(int)
{
   Point temp = *this;
   ++*this;
   return temp;
}

// Define prefix decrement operator.
Point& Point::operator--()
{
   _x--;
   _y--;
   return *this;
}

// Define postfix decrement operator.
Point Point::operator--(int)
{
   Point temp = *this;
   --*this;
   return temp;
}
int main()
{
}
```

次の関数のヘッダーを使用すると、同じ演算子をファイル スコープで (グローバルに) 定義できます。

```cpp
friend Point& operator++( Point& )      // Prefix increment
friend Point& operator++( Point&, int ) // Postfix increment
friend Point& operator--( Point& )      // Prefix decrement
friend Point& operator--( Point&, int ) // Postfix decrement
```

**`int`** 後置形式のインクリメント演算子またはデクリメント演算子を示す型の引数は、通常、引数を渡すために使用されません。 通常は、値 0 が含まれます。 ただし、次のように使用できます。

```cpp
// increment_and_decrement2.cpp
class Int
{
public:
    Int &operator++( int n );
private:
    int _i;
};

Int& Int::operator++( int n )
{
    if( n != 0 )    // Handle case where an argument is passed.
        _i += n;
    else
        _i++;       // Handle case where no argument is passed.
    return *this;
}
int main()
{
   Int i;
   i.operator++( 25 ); // Increment by 25.
}
```

上記のコードに示すように、明示的に呼び出すこと以外に、インクリメント演算子またはデクリメント演算子を使用してこれらの値を渡すための構文はありません。 この機能を実装するためのより簡単な方法は、加算/代入演算子 () をオーバーロードすることです **+=** 。

## <a name="see-also"></a>関連項目

[演算子のオーバーロード](../cpp/operator-overloading.md)
