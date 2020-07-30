---
title: コンパイラエラー C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: 17a210e2a514af1ffd62bf38651c4d17bd1fe32b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230793"
---
# <a name="compiler-error-c3615"></a>コンパイラエラー C3615

> constexpr 関数 '*function*' の結果を定数式にすることはできません

関数*関数*は、コンパイル時にとして評価できませんでした **`constexpr`** 。 関数は **`constexpr`** 、他の関数だけを呼び出すことができ **`constexpr`** ます。

## <a name="example"></a>例

Visual Studio 2017 では、条件付きで評価する操作の左側のオペランドがコンテキストで有効でない場合に、エラーが正しく発生 **`constexpr`** します。 次のコードは、visual Studio 2015 ではコンパイルされますが、Visual Studio 2017 ではコンパイルされません。

```cpp
// C3615.cpp
// Compile with: /c

template<int N>
struct myarray
{
    int size() const { return N; }
};

constexpr bool f(const myarray<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 starting in Visual Studio 2017
}
```

この問題を解決するには、 `array::size()` 関数をとして宣言するか、 **`constexpr`** から修飾子を削除し **`constexpr`** `f` ます。
