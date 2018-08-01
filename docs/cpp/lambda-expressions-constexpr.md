---
title: C++ でのラムダ式の constexpr |Microsoft Docs
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
ms.openlocfilehash: b78fa3de7777ffc6702902cf967a405595caf12f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408204"
---
# <a name="constexpr-lambda-expressions-in-c"></a>C++ でのラムダ式の constexpr
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
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C++ 標準ライブラリ内の関数オブジェクト](../standard-library/function-objects-in-the-stl.md)   
 [関数呼び出し](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)