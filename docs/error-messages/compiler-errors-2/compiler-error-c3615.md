---
title: コンパイラエラー C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: c1a5b6edbc87e14de267cf962dc2b1a71dd6be12
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200539"
---
# <a name="compiler-error-c3615"></a>コンパイラエラー C3615

> constexpr 関数 '*function*' の結果を定数式にすることはできません

関数*関数*をコンパイル時に `constexpr` として評価できませんでした。 `constexpr`するために、関数は他の `constexpr` 関数だけを呼び出すことができます。

## <a name="example"></a>例

Visual Studio 2017 では、条件に応じて評価する操作の左側のオペランドが `constexpr` コンテキストで有効でない場合に、エラーが正しく発生します。 次のコードは、visual Studio 2015 ではコンパイルされますが、Visual Studio 2017 ではコンパイルされません。

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

この問題を解決するには、`array::size()` 関数を `constexpr` として宣言するか、`f`から `constexpr` 修飾子を削除します。
