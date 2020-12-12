---
description: 詳細については、「コンパイラエラー C3615」を参照してください。
title: コンパイラエラー C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: 9f3b95b96ff10a99f3ebeac1bc3b19f759dd0ab7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262283"
---
# <a name="compiler-error-c3615"></a>コンパイラエラー C3615

> constexpr 関数 '*function*' の結果を定数式にすることはできません

関数 *関数* は、コンパイル時にとして評価できませんでした **`constexpr`** 。 関数は **`constexpr`** 、他の関数だけを呼び出すことができ **`constexpr`** ます。

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
