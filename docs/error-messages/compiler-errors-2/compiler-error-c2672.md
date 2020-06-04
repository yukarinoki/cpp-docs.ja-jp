---
title: コンパイラエラー C2672
ms.date: 10/24/2017
f1_keywords:
- C2672
helpviewer_keywords:
- C2672
ms.assetid: 7e86338a-2d4b-40fe-9dd2-ac6886f3f31a
ms.openlocfilehash: 9f844b54285a7df69bfb4387a7afcc82dfef9252
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177132"
---
# <a name="compiler-error-c2672"></a>コンパイラエラー C2672

> '*function*': 一致するオーバーロードされた関数が見つかりませんでした

コンパイラは、指定された関数と一致するオーバーロードされた関数を見つけることができませんでした。 一致するパラメーターを受け取る関数が見つからないか、コンテキストに必要なアクセシビリティが一致する関数がありません。

特定の標準ライブラリのコンテナーまたはアルゴリズムで使用する場合、型は、コンテナーまたはアルゴリズムの要件を満たすアクセス可能なメンバーまたはフレンド関数を提供する必要があります。 たとえば、反復子型は `std::iterator<>`から派生する必要があります。 比較演算、またはコンテナー要素型に対する他の演算子の使用では、型を左辺オペランドと右辺オペランドの両方として考慮する必要がある場合があります。 型を右辺オペランドとして使用するには、演算子を型の非メンバー関数として実装する必要があります。

## <a name="example"></a>例

一部のテンプレートコンテキストで、Visual Studio 2017 が修飾名に対してアクセスチェックを実行しなかった前のコンパイラのバージョン。 これは、名前にアクセスできないために置換が失敗すると予想される場合に、予期される SFINAE の動作に干渉する可能性があります。 コンパイラが演算子の誤ったオーバーロードを誤って呼び出すために、これが原因でクラッシュまたは実行時に予期しない動作が発生する可能性があります。 Visual Studio 2017 年では、コンパイラ エラーが発生します。

この例は、Visual Studio 2015 でコンパイルされますが、Visual Studio 2017 ではエラーが発生します。 この問題を解決するには、テンプレートパラメーターメンバーが評価される場所にアクセスできるようにします。

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
