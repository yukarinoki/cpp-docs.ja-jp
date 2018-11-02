---
title: C++ では constexpr ラムダ式
ms.date: 07/19/2017
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: 937fae7da0f20e81ac5450d597af7a822219d654
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506601"
---
# <a name="constexpr-lambda-expressions-in-c"></a>C++ では constexpr ラムダ式

**Visual Studio 2017 バージョン 15.3 以降**(で使用可能な[/std:c + + + 17](../build/reference/std-specify-language-standard-version.md)): としてラムダ式を宣言することがあります**constexpr**か指定する定数式で使用時にそれぞれの初期化キャプチャまたは導入されるデータ メンバーは、定数式内で許可されます。

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

ラムダは暗黙的に**constexpr**その結果の要件を満たしている場合、 **constexpr**関数。

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

ラムダが暗黙的または明示的に場合**constexpr**、および関数ポインターに変換する、結果として得られる関数も**constexpr**:

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