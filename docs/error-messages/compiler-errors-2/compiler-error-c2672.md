---
title: コンパイラ エラー C2672 |Microsoft ドキュメント
ms.date: 10/24/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2672
dev_langs:
- C++
helpviewer_keywords:
- C2672
ms.assetid: 7e86338a-2d4b-40fe-9dd2-ac6886f3f31a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98c569c8b9b1466f184b44d345e76341d1476935
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236119"
---
# <a name="compiler-error-c2672"></a>コンパイラ エラー C2672

> '*関数*': 一致するオーバー ロードされた関数。

コンパイラは、指定された関数に一致するオーバー ロードされた関数を見つけられませんでした。 一致するパラメーター、または一致する関数にあるコンテキストで必要なユーザー補助機能が見つかりませんでした。

特定の標準ライブラリのコンテナーまたはアルゴリズムを使用して場合、アクセス可能なメンバーまたはコンテナーまたはアルゴリズムの要件を満たすフレンド関数に、型が指定する必要があります。 たとえば、反復子の型の派生元`std::iterator<>`です。 比較操作またはその他の型の演算子をコンテナー要素の使用は、型が、左辺と右辺のオペランドの両方と見なされる必要があります。 右のオペランドが演算子の実装を必要な型の非メンバー関数としては、型の使用します。

## <a name="example"></a>例

Visual Studio 2017 する前に、コンパイラのバージョンでは、アクセス チェックをテンプレートの一部のコンテキストに修飾名では実行しませんでした。 これは、名前にアクセスできないために置換が失敗すると予想される場合に、予期される SFINAE の動作に干渉する可能性があります。 コンパイラが演算子の誤ったオーバーロードを誤って呼び出すために、これが原因でクラッシュまたは実行時に予期しない動作が発生する可能性があります。 Visual Studio 2017 年では、コンパイラ エラーが発生します。

この例では、Visual Studio 2015 でコンパイルしますが、Visual Studio 2017 でエラーが発生します。 この問題を解決するには、メンバーにする、テンプレート パラメーター アクセスが評価されます。

```cpp
#include <type_traits>

template <class T> class S {
// public:    // Uncomment this line to fix
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x)
{
    return (x == 0);
}

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```