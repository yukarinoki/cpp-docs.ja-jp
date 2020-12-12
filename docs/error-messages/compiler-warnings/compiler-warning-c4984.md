---
description: 詳細については、「コンパイラの警告 C4984」を参照してください。
title: コンパイラの警告 C4984
ms.date: 08/19/2019
f1_keywords:
- C4984
helpviewer_keywords:
- C4984
ms.openlocfilehash: 5a6708a1063baf8fa4b5feece65eabd93df7bbeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326001"
---
# <a name="compiler-warning-c4984"></a>コンパイラの警告 C4984

> ' if constexpr ' は C++ 17 言語拡張です

## <a name="remarks"></a>解説

コンパイラは、 `if constexpr` 既定の c++ 14 標準を使用してコンパイルされたコード内に式を検出しました。 この式は、C++ 17 標準で開始されます。 C++ 11 または C++ 14 の互換性が必要な場合、この式は移植できません。

C4984 は、既定ではエラーとして発行されますが、suppressible です。 C++ 17 としてコードをコンパイルしてこの式を有効にするに [は、/std: c++ 17 または/std: C + + latest](../../build/reference/std-specify-language-standard-version.md)を使用します。 `if constexpr`Microsoft 拡張機能として c++ 14 用にコンパイルされたコードで式を使用するには、エラーメッセージの警告レベルを抑制、無効化、または変更することができます。 [/Wd4984](../../build/reference/compiler-option-warning-level.md)を使用して C4984 を無効にするか、または __/w__*n*__4984__ を使用して、エラーではなくレベル *N* の警告として有効にすることができます。 または、ソースファイルの警告を発生させる行の前に [#pragma warning (抑制: 4984)](../../preprocessor/warning.md) を使用します。

この警告は、Visual Studio 2017 バージョン15.3 以降で使用できます。 特定のコンパイラバージョン以降で導入された警告を無効にする方法については、「コンパイラの [バージョン別のコンパイラ警告](compiler-warnings-by-compiler-version.md)」を参照してください。

## <a name="example"></a>例

このサンプルでは、C4984 を生成し、その修正方法を示しています。

```cpp
// C4984.cpp
// compile with: cl /EHsc C4984.cpp
#include <iostream>

int main()
{
    constexpr bool compile_time = true;
    // Uncomment the following line or use /std:c++17 to fix
    // #pragma warning(suppress:4984)
    if constexpr (compile_time)
    {
        std::cout << "compile_time is true";
    }
    else
    {
        std::cout << "compile_time is false";
    }
}
```
