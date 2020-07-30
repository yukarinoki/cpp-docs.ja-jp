---
title: /Zc:implicitNoexcept (暗黙の例外指定子)
ms.date: 03/06/2018
f1_keywords:
- /Zc:implicitNoexcept
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
ms.openlocfilehash: bb1a632ffe684ac0777d0089a2edfd514bf66d0b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223799"
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/Zc:implicitNoexcept (暗黙の例外指定子)

**/Zc: implicitNoexcept**オプションが指定されている場合、コンパイラは、コンパイラによって定義された特殊なメンバー関数、およびユーザー定義のデストラクターと deallocators に暗黙的な[noexcept](../../cpp/noexcept-cpp.md)例外指定子を追加します。 既定では、 **/zc: implicitNoexcept**は ISO c++ 11 標準に準拠するように有効になっています。 このオプションをオフにすると、 **`noexcept`** ユーザー定義のデストラクターと、コンパイラによって定義された特殊なメンバー関数では暗黙的に無効になります。

## <a name="syntax"></a>構文

> **/Zc: implicitNoexcept**[ **-** ]

## <a name="remarks"></a>解説

**/Zc: implicitNoexcept**は、ISO c++ 11 標準のセクション15.4 に従うようにコンパイラに指示します。 **`noexcept`** 暗黙的に宣言または明示的に設定された特殊なメンバー関数 (既定のコンストラクター、コピーコンストラクター、移動コンストラクター、デストラクター、コピー代入演算子、または移動代入演算子) と各ユーザー定義デストラクターまたはデアロケーター関数に、例外指定子を暗黙的に追加します。 ユーザー定義のデアロケーターには、暗黙的な `noexcept(true)` 例外指定子があります。 ユーザー定義のデストラクターでは、含まれているメンバー クラスまたは基底クラスに `noexcept(true)` ではないデストラクターがなければ、暗黙的な例外指定子は `noexcept(true)` です。 コンパイラにより生成された特別なメンバー関数では、この関数によって直接呼び出された任意の関数が実質的に `noexcept(false)` である場合、暗黙的な例外指定子は `noexcept(false)` です。 それ以外の場合、暗黙的な例外指定子は `noexcept(true)` です。

明示的 **`noexcept`** または **`throw`** 指定子または属性を使用して宣言された関数の場合、コンパイラは暗黙的な例外指定子を生成しません `__declspec(nothrow)` 。

既定では、 **/zc: implicitNoexcept**が有効になっています。 [/Permissive-](permissive-standards-conformance.md)オプションは、 **/zc: implicitNoexcept**には影響しません。

**/Zc: implicitNoexcept**を指定してオプションを無効にした場合、コンパイラによって暗黙的な例外指定子は生成されません。 この動作は Visual Studio 2013 と同じです。ただし、例外指定子を持たないデストラクターと deallocators は、ステートメントを持つことができ **`throw`** ます。 既定では、 **/zc: implicitNoexcept**を指定した場合、 **`throw`** 暗黙的な指定子を持つ関数で実行時にステートメントが検出されると、がすぐに呼び出され、 `noexcept(true)` `std::terminate` 例外ハンドラーの通常のアンワインド動作は保証されません。 この状況を特定するために、コンパイラは[コンパイラの警告 (レベル 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)を生成します。 が意図的なものである場合は、 **`throw`** `noexcept(false)` **/zc: implicitNoexcept-** を使用するのではなく、明示的な指定子を持つように関数宣言を変更することをお勧めします。

このサンプルでは、 **/zc: implicitNoexcept**オプションが設定または無効になっている場合に、明示的な例外指定子を持たないユーザー定義のデストラクターが動作する方法を示します。 設定時に動作を表示するには、を使用してコンパイルし `cl /EHsc /W4 implicitNoexcept.cpp` ます。 無効になっているときの動作を表示するには、を使用してコンパイルし `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp` ます。

```cpp
// implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp

#include <iostream>
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS
#include <exception>    // for std::set_terminate

void my_terminate()
{
    std::cout << "Unexpected throw caused std::terminate" << std::endl;
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;
    std::exit(EXIT_FAILURE);
}

struct A {
    // Explicit noexcept overrides implicit exception specification
    ~A() noexcept(false) {
        throw 1;
    }
};

struct B : public A {
    // Compiler-generated ~B() definition inherits noexcept(false)
    ~B() = default;
};

struct C {
    // By default, the compiler generates an implicit noexcept(true)
    // specifier for this user-defined destructor. To enable it to
    // throw an exception, use an explicit noexcept(false) specifier,
    // or compile by using /Zc:implicitNoexcept-
    ~C() {
        throw 1; // C4297, calls std::terminate() at run time
    }
};

struct D : public C {
    // This destructor gets the implicit specifier of its base.
    ~D() = default;
};

int main()
{
    std::set_terminate(my_terminate);

    try
    {
        {
            B b;
        }
    }
    catch (...)
    {
        // exception should reach here in all cases
        std::cout << "~B Exception caught" << std::endl;
    }
    try
    {
        {
            D d;
        }
    }
    catch (...)
    {
        // exception should not reach here if /Zc:implicitNoexcept
        std::cout << "~D Exception caught" << std::endl;
    }
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;
    return EXIT_SUCCESS;
}
```

既定の設定である **/zc: implicitNoexcept**を使用してコンパイルした場合、このサンプルでは次の出力が生成されます。

```Output
~B Exception caught
Unexpected throw caused std::terminate
Exit returning EXIT_FAILURE
```

**/Zc: implicitNoexcept**の設定を使用してコンパイルした場合、このサンプルでは次の出力が生成されます。

```Output
~B Exception caught
~D Exception caught
Exit returning EXIT_SUCCESS
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **/Zc: implicitNoexcept**または **/zc: implicitNoexcept**が含まれるように "**追加オプション**" プロパティを変更し、[ **OK]** をクリックします。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[例外の指定 (throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[解約](../../standard-library/exception-functions.md#terminate)<br/>
