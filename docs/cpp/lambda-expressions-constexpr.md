---
title: C++ での constexpr ラムダ式
ms.date: 04/08/2019
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: 24c70732093447649b3cfb460f63b2181efdf806
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213347"
---
# <a name="constexpr-lambda-expressions-in-c"></a>C++ での constexpr ラムダ式

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能): ラムダ式は、 **`constexpr`** キャプチャまたは導入される各データメンバーの初期化が定数式内で許可されている場合に、定数式として宣言または使用できます。

```cpp
    int y = 32;
    auto answer = [y]() constexpr
    {
        int x = 10;
        return y + x;
    };

    constexpr int Increment(int n)
    {
        return [n] { return n + 1; }();
    }
```

ラムダは、 **`constexpr`** 結果が関数の要件を満たす場合に暗黙的に行われ **`constexpr`** ます。

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

ラムダが暗黙的または明示的に使用され **`constexpr`** 、関数ポインターに変換された場合、結果として得られる関数も次のようになり **`constexpr`** ます。

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[C++ 標準ライブラリの関数オブジェクト](../standard-library/function-objects-in-the-stl.md)<br/>
[関数呼び出し](../cpp/function-call-cpp.md)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)
