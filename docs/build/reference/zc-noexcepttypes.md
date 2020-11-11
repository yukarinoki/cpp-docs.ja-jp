---
title: '/Zc: noexceptTypes (C++ 17 noexcept ルール)'
description: 'Microsoft C++/Zc: noexceptTypes コンパイラオプションに準拠または緩やかに対応する C++ 17 noexcept のソースコードの互換性について説明します。'
ms.date: 06/04/2020
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: c15d4203f343eced7c112757b2665aa71a982c7c
ms.sourcegitcommit: 25f6d52eb9e5d84bd0218c46372db85572af81da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94448504"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc: noexceptTypes (C++ 17 noexcept ルール)

C++ 17 標準では、 `throw()` のエイリアスを作成し、 **`noexcept`** とを削除し、特定の `throw(` *`type-list`* `)` `throw(...)` 型に含めることができる **`noexcept`** ようにします。 この変更により、C++ 14 以前に準拠しているコードでソース互換性の問題がいくつか発生する可能性があります。 オプションは、 **`/Zc:noexceptTypes`** c++ 17 標準に準拠することを指定します。 **`/Zc:noexceptTypes-`**  c++ 17 モードでコードをコンパイルするときに、C++ 14 以前の動作を許可します。

## <a name="syntax"></a>構文

> **`/Zc:noexceptTypes`**\[**`-`** ]

## <a name="remarks"></a>解説

このオプションを指定すると、 **`/Zc:noexceptTypes`** コンパイラは c++ 17 標準に準拠し、 [`throw()`](../../cpp/exception-specifications-throw-cpp.md) の別名としてを処理し、 [`noexcept`](../../cpp/noexcept-cpp.md) とを削除して、特定の `throw(` *`type-list`* `)` `throw(...)` 型を含めることができる **`noexcept`** ようにします。 オプションは、 **`/Zc:noexceptTypes`** [`/std:c++17`](std-specify-language-standard-version.md) またはが有効になっている場合にのみ使用でき [`/std:c++latest`](std-specify-language-standard-version.md) ます。 **`/Zc:noexceptTypes`** は、ISO C++ 17 標準に準拠するように既定で有効になっています。 [`/permissive-`](permissive-standards-conformance.md)オプションはには影響しません **`/Zc:noexceptTypes`** 。 **`/Zc:noexceptTypes-`** **`noexcept`** **`/std:c++17`** またはが指定された場合に、を c++ 14 の動作に戻すように指定して、このオプションをオフにし **`/std:c++latest`** ます。

Visual Studio 2017 バージョン15.5 以降では、c++ コンパイラは C++ 17 モードの宣言で一致しない例外指定を診断します。または、オプションを指定した場合はを診断し [`/permissive-`](permissive-standards-conformance.md) ます。

このサンプルでは、 **`/Zc:noexceptTypes`** オプションが設定または無効になった場合に、例外指定子を使用した宣言がどのように動作するかを示します。 設定時に動作を表示するには、を使用してコンパイルし `cl /EHsc /W4 noexceptTypes.cpp` ます。 無効になっているときの動作を表示するには、を使用してコンパイルし `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp` ます。

```cpp
// noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp

void f() throw();    // equivalent to void f() noexcept;
void f() { }         // warning C5043
void g() throw(...); // warning C5040

struct A
{
    virtual void f() throw();
};

struct B : A
{
    virtual void f() { } // error C2694
};
```

既定の設定を使用してコンパイルされた場合、サンプルでは **`/Zc:noexceptTypes`** 警告が生成されます。 コードを更新するには、代わりに次のコードを使用します。

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A
{
    virtual void f() noexcept;
};

struct B : A
{
    virtual void f() noexcept { }
};
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成プロパティ** ] [  >  **C/c + +**  >  **コマンドライン** ] プロパティページを選択します。

1. またはを含むように " **追加オプション** " プロパティを変更し、[ *`/Zc:noexceptTypes`* *`/Zc:noexceptTypes-`* **OK]** をクリックします。

## <a name="see-also"></a>関連項目

[`/Zc` 互換性](zc-conformance.md)\
[noexcept](../../cpp/noexcept-cpp.md)\
[例外の指定 (スロー)](../../cpp/exception-specifications-throw-cpp.md)
