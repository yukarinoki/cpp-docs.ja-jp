---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 51df20ea00e5dd77ab1fc1a2a01253b8f788ad0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358854"
---
# <a name="nullptr"></a>nullptr

任意の生ポインター型に変換可能な `std::nullptr_t` 型の null ポインター定数を指定します。  キーワード**nullptr**を使用しても、ヘッダーを含めずに使用できますが、コードで`std::nullptr_t`type を使用する場合は、ヘッダー`<cstddef>`を含めて定義する必要があります。

> [!NOTE]
> **nullptr**キーワードは、マネージ コード アプリケーションの C++/CLI でも定義され、ISO 標準 C++ キーワードとの交換はできません。 マネージ コードを対象とする[/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを使用してコードをコンパイルする場合は`__nullptr`、コンパイラがネイティブ C++ の解釈を使用することを保証する必要があるコード行で使用します。 詳細については、 [nullptr](../extensions/nullptr-cpp-component-extensions.md)を参照してください。

## <a name="remarks"></a>解説

NULL またはゼロ (`0`) を NULL ポインター定数として使用しないでください。**nullptr**は、誤用に対して脆弱ではなく、ほとんどの状況で動作する方が良いです。  たとえば、`func(std::pair<const char *, double>)` が指定されている場合に、`func(std::make_pair(NULL, 3.14))` を呼び出すとコンパイラ エラーが発生します。  NULL マクロは `0` に展開します。したがって、`std::make_pair(0, 3.14)` の呼び出しでは、func() の `std::pair<int, double>` パラメーター型に変換可能ではない `std::pair<const char *, double>` が返されます。  `func(std::make_pair(nullptr, 3.14))` は `std::make_pair(nullptr, 3.14)` に変換可能な `std::pair<std::nullptr_t, double>` を返すので、`std::pair<const char *, double>` の呼び出しは正常にコンパイルされます。

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)<br/>
[nullptr](../extensions/nullptr-cpp-component-extensions.md)(C++/CLI)
