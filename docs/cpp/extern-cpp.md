---
title: extern (C++)
ms.date: 04/12/2018
f1_keywords:
- extern
- extern_CPP
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
ms.openlocfilehash: d42a32202f7fa67751ea36757c13b2c6af4953b2
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301536"
---
# <a name="extern-c"></a>extern (C++)

**Extern**キーワードは、グローバル変数、関数、またはテンプレートの宣言に適用され、*外部リンケージ*を持つ名前を指定します。 リンケージの背景情報と、グローバル変数の使用を推奨しない理由については、「[翻訳単位とリンケージ](program-and-linkage-cpp.md)」を参照してください。

**Extern**キーワードには、コンテキストに応じて次の4つの意味があります。

1. 非 const グローバル変数宣言では、 **extern**は変数または関数が別の翻訳単位で定義されていることを指定します。 **Extern**は、変数が定義されているものを除くすべてのファイルに適用する必要があります。
1. const 変数宣言では、変数に外部リンケージがあることを指定します。 **Extern**は、すべてのファイル内のすべての宣言に適用する必要があります。 (グローバル const 変数には、既定で内部リンケージがあります)。
1. **extern "C"** は、関数が他の場所で定義され、C 言語の呼び出し規約を使用することを指定します。 Extern "C" 修飾子は、ブロック内の複数の関数宣言にも適用できます。
1. テンプレート宣言では、テンプレートが他の場所で既にインスタンス化されていることを指定します。 これは、現在の場所に新しいインスタンスを作成するのではなく、もう一方のインスタンスを再利用できることをコンパイラに指示する最適化です。 この**extern**の使用方法の詳細については、「[テンプレート](templates-cpp.md)」を参照してください。

## <a name="extern-linkage-for-non-const-globals"></a>非 const グローバルの extern リンケージ

リンカーは、グローバル変数宣言の前に**extern**を認識すると、別の翻訳単位で定義を検索します。 グローバルスコープでの非 const 変数の宣言は、既定では外部です。定義を提供しない宣言にのみ**extern**を適用します。

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
extern int i;  // declaration only. same as i in FileA

//fileC.cpp
extern int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
extern int i = 43; // same error (extern is ignored on definitions)
```

## <a name="extern-linkage-for-const-globals"></a>const globals の extern リンケージ

**Const**グローバル変数は、既定で内部リンケージを持ちます。 変数に外部リンケージを設定する場合は、他のファイル内の他のすべての宣言に加えて、 **extern**キーワードを定義に適用します。

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>extern constexpr リンケージ

Visual Studio 2017 バージョン15.3 以前では、変数が extern としてマークされている場合でも、コンパイラは常に constexpr 変数の内部リンケージを与えました。 Visual Studio 2017 バージョン 15.5 では、新しいコンパイラ スイッチ ([/Zc:externConstexpr](../build/reference/zc-externconstexpr.md)) により、正しい標準準拠の動作が可能になります。 最終的にこれは既定値になります。 /Permissive-オプションでは、/Zc: externConstexpr は有効になりません。

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

ヘッダーファイルに extern constexpr として宣言された変数が含まれている場合は、重複する宣言を正しく結合するために、 **__declspec (selectany)** とマークする必要があります。

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>extern "C" および extern "C++" 関数の宣言

でC++は、文字列と共に使用する場合、 **extern**は別の言語のリンケージ規則が宣言子に使用されることを指定します。 C の関数とデータには、C リンケージを持つと以前に宣言されている場合にのみ、アクセスできます。 ただし、別にコンパイルされた翻訳単位で定義する必要があります。

Microsoft C++では、*文字列リテラル*フィールドに文字列 **"C"** と**C++""** をサポートしています。 すべての標準インクルードファイルは、 **extern** "C" 構文を使用して、ランタイムライブラリ関数をプログラムでC++使用できるようにします。

## <a name="example"></a>使用例

次の例は、C リンケージを持つ名前を宣言する方法を示しています。

```cpp
// Declare printf with C linkage.
extern "C" int printf(const char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
extern "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
extern "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
extern "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

extern "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
extern "C" int errno;
```

関数に複数のリンケージ指定子がある場合、それらは一致する必要があります。関数を C と C++ 両方のリンケージを持つ関数として宣言するとエラーになります。 また、プログラム内に、リンケージ指定子を含む関数宣言と含まない関数宣言がある場合、リンケージ指定子を含む宣言を最初に記述する必要があります。 既にリンケージ指定を持つ関数の冗長な宣言には、最初の宣言で指定したリンケージが与えられます。 例:

```cpp
extern "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
extern "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[翻訳単位とリンケージ](program-and-linkage-cpp.md)<br/>
[extern ストレージクラスの指定子 (C)](../c-language/extern-storage-class-specifier.md)<br/>
[C での識別子の動作](../c-language/behavior-of-identifiers.md)<br/>
[C でのリンケージ](../c-language/linkage.md)