---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 223f4c3e8c838698f9716e241543db405c9394af
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177769"
---
# <a name="nullptr"></a>nullptr

任意の生ポインター型に変換可能な `std::nullptr_t` 型の null ポインター定数を指定します。  キーワード**nullptr**はヘッダーを含めずに使用できますが、コードで型 `std::nullptr_t`を使用する場合は、ヘッダー `<cstddef>`を含めることによって定義する必要があります。

> [!NOTE]
>  **Nullptr**キーワードは、マネージコードアプリケーションC++に対して/cli でも定義されており、ISO C++標準のキーワードと置き換えることはできません。 マネージコードをターゲットとする[/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラオプションを使用してコードをコンパイルする場合は、コンパイラがネイティブC++の解釈を使用することを保証する必要があるコード行で `__nullptr` を使用します。 詳細については、「 [nullptr](../extensions/nullptr-cpp-component-extensions.md)」を参照してください。

## <a name="remarks"></a>解説

Null または 0 (`0`) を null ポインター定数として使用することは避けてください。**nullptr**は悪用に対して脆弱になり、ほとんどの状況でより適切に動作します。  たとえば、`func(std::pair<const char *, double>)` が指定されている場合に、`func(std::make_pair(NULL, 3.14))` を呼び出すとコンパイラ エラーが発生します。  NULL マクロは `0` に展開します。したがって、`std::make_pair(0, 3.14)` の呼び出しでは、func() の `std::pair<int, double>` パラメーター型に変換可能ではない `std::pair<const char *, double>` が返されます。  `func(std::make_pair(nullptr, 3.14))` は `std::make_pair(nullptr, 3.14)` に変換可能な `std::pair<std::nullptr_t, double>` を返すので、`std::pair<const char *, double>` の呼び出しは正常にコンパイルされます。

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)<br/>
[nullptr](../extensions/nullptr-cpp-component-extensions.md)(C++/cli)
