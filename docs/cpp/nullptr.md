---
title: nullptr
ms.date: 07/22/2020
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 801ae927d6c9fb70c3187d10269e87097a879bfc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223630"
---
# <a name="nullptr"></a>nullptr

キーワードは、 **`nullptr`** 型の null ポインター定数を指定し `std::nullptr_t` ます。これは、任意の生ポインター型に変換できます。  ヘッダーを含めずにキーワードを使用することもできますが、 **`nullptr`** コードで型を使用する場合は、 `std::nullptr_t` ヘッダーを含めることによって定義する必要があり `<cstddef>` ます。

> [!NOTE]
> キーワードは、 **`nullptr`** マネージコードアプリケーションの c++/cli でも定義されており、ISO 標準 C++ キーワードと置き換えることはできません。 マネージコードをターゲットとするコンパイラオプションを使用してコードをコンパイルする場合は [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) 、 `__nullptr` コンパイラがネイティブ C++ の解釈を使用することを保証する必要がある任意のコード行でを使用します。 詳細については、「 [ `nullptr` (c++/cli および c++/cx)](../extensions/nullptr-cpp-component-extensions.md)」を参照してください。

## <a name="remarks"></a>解説

`NULL`Null ポインター定数としてまたは 0 () を使用しないでください。を使用 `0` **`nullptr`** すると、誤用に対する脆弱性が低くなり、ほとんどの状況でより適切に動作します。  たとえば、`func(std::pair<const char *, double>)` が指定されている場合に、`func(std::make_pair(NULL, 3.14))` を呼び出すとコンパイラ エラーが発生します。  マクロは `NULL` に展開される `0` ため、呼び出しはを `std::make_pair(0, 3.14)` 返します。これは、 `std::pair<int, double>` `std::pair<const char *, double>` のパラメーター型に変換できません `func` 。  `func(std::make_pair(nullptr, 3.14))` は `std::make_pair(nullptr, 3.14)` に変換可能な `std::pair<std::nullptr_t, double>` を返すので、`std::pair<const char *, double>` の呼び出しは正常にコンパイルされます。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[`nullptr`(C++/CLI および C++/CX)](../extensions/nullptr-cpp-component-extensions.md)
