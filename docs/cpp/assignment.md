---
description: '詳細情報: 割り当て'
title: 割り当て
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
ms.openlocfilehash: 696706202e70e8baf50dda34ac98ff9bca5dcda2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319490"
---
# <a name="assignment"></a>割り当て

代入演算子 ( **=** ) は、厳密に言えば二項演算子です。 この宣言は他の二項演算子と同じですが、次の例外があります。

- 非静的メンバー関数である必要があります。 **Operator =** を非メンバー関数として宣言することはできません。
- 派生クラスにより継承されません。
- クラス型の場合は、コンパイラによって既定の **operator =** 関数が生成されます (存在しない場合)。

次の例では、代入演算子を宣言する方法を示しています。

```cpp
class Point
{
public:
    int _x, _y;

    // Right side of copy assignment is the argument.
    Point& operator=(const Point&);
};

// Define copy assignment operator.
Point& Point::operator=(const Point& otherPoint)
{
    _x = otherPoint._x;
    _y = otherPoint._y;

    // Assignment operator returns left side of assignment.
    return *this;
}

int main()
{
    Point pt1, pt2;
    pt1 = pt2;
}
```

指定された引数は式の右辺です。 演算子は、代入の完了後に左側の値を返す代入演算子の動作を保持するオブジェクトを返します。 これにより、次のような割り当てを連鎖させることができます。

```cpp
pt1 = pt2 = pt3;
```

コピー代入演算子は、コピーコンストラクターと混同しないようにしてください。 後者は、既存のオブジェクトから新しいオブジェクトを構築するときに呼び出されます。

```cpp
// Copy constructor is called--not overloaded copy assignment operator!
Point pt3 = pt1;

// The previous initialization is similar to the following:
Point pt4(pt1); // Copy constructor call.
```

> [!NOTE]
> コピー代入演算子を定義するクラスでは、C++ 11、移動コンストラクター、移動代入演算子で始まるコピーコンストラクター、デストラクター、およびを明示的に定義する必要があるという [3 つの規則](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming)) に従うことをお勧めします。

## <a name="see-also"></a>関連項目

- [演算子のオーバーロード](../cpp/operator-overloading.md)
- [コピー コンストラクターとコピー代入演算子 (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)
