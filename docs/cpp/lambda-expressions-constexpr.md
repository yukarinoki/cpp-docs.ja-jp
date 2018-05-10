---
title: C++ のラムダ式の constexpr |Microsoft ドキュメント
ms.custom: ''
ms.date: 07/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e01f41aaf8b761020f57625e7cbf06f8fba2659
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="constexpr-lambda-expressions-in-c"></a>constexpr C++ のラムダ式
**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): としてラムダ式を宣言することは`constexpr`か指定する定数式で使用時に各データ メンバーの初期化がキャプチャまたはが導入されています、定数式は許可されています。  

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
ラムダは、暗黙的に`constexpr`その結果の要件を満たしている場合、`constexpr`関数。
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
場合は、ラムダは、暗黙的または明示的に`constexpr`、関数ポインターに変換するは、結果として得られる関数も`constexpr`:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C++ 標準ライブラリ内の関数オブジェクト](../standard-library/function-objects-in-the-stl.md)   
 [関数呼び出し](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)