---
title: '-Zc: noexceptTypes (c++ 17 noexcept の規則) |Microsoft ドキュメント'
ms.date: 11/14/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:noexceptTypes
dev_langs:
- C++
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25ad2a662af2cda49e3e8dd8c769fa75dafee94b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379550"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (c++ 17 noexcept ルール)

C++ 17 規格は、`throw()`のエイリアスとして`noexcept`、削除`throw(<type list>)`と`throw(...)`、特定の種類を含めることができ`noexcept`です。 C++ 14 またはそれ以前に準拠しているコードでこの、さまざまなソースの互換性の問題の可能性があります。 **/Zc:noexceptTypes**オプションは、c++ 17 規格に準拠するを指定したり、c++ 17 モードでコードがコンパイルされるときに、c++ 14 およびそれ以前の動作を許可します。

## <a name="syntax"></a>構文

> **/Zc:noexceptTypes**[-]

## <a name="remarks"></a>コメント

ときに、 **/Zc:noexceptTypes**オプションを指定すると、コンパイラは、c++ 17 規格に準拠しているし、処理[throw()](../../cpp/exception-specifications-throw-cpp.md)のエイリアスとして[noexcept](../../cpp/noexcept-cpp.md)、削除`throw(<type list>)`と`throw(...)`、特定の種類を含めることができ`noexcept`です。 **/Zc:noexceptTypes**オプションは、のみ使用可能な場合に[/std:c + + 17](std-specify-language-standard-version.md)または[/std:latest](std-specify-language-standard-version.md)を有効にします。 **/Zc:noexceptTypes** ISO c++ 17 規格に準拠するように既定で有効にします。 [寛容/-](permissive-standards-conformance.md)オプションには影響しません **/Zc:noexceptTypes**です。 指定して、このオプションをオフに **/Zc:noexceptTypes-** 、c++ 14 の動作に戻すには`noexcept`とき **/std::C:operator++ 17**または **/std::latest**が指定されています。

C++ コンパイラを診断する Visual Studio 2017 バージョン 15.5 以降、c++ 17 モードでの宣言で複数の一致しない例外の指定場合や、[寛容/-](permissive-standards-conformance.md)オプションを指定します。

この例では、例外の指定子と宣言ときの動作、 **/Zc:noexceptTypes**オプションを設定するか、または無効になっています。 動作を示すを設定するを使用してコンパイル`cl /EHsc /W4 noexceptTypes.cpp`です。 表示するには無効にしたときの動作を使用してコンパイル`cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`です。

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

既定の設定を使用して、コンパイル時に **/Zc:noexceptTypes**サンプルが表示されている警告を生成します。 コードを更新するには、次の使用を代わりに。

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

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:noexceptTypes**または **/Zc:noexceptTypes-** を選択し**OK**です。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)  
[noexcept](../../cpp/noexcept-cpp.md)  
[例外の仕様 (スロー)](../../cpp/exception-specifications-throw-cpp.md)  
