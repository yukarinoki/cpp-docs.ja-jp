---
title: ':::no-loc(extern)::: (C++)'
description: 'C++ 言語キーワードのガイド :::no-loc(extern)::: 。'
ms.date: 01/28/2020
f1_keywords:
- ':::no-loc(extern):::'
- :::no-loc(extern):::_CPP
helpviewer_keywords:
- ':::no-loc(extern)::: keyword [C++], linkage to non-C++ functions'
- declarations, :::no-loc(extern):::al
- ':::no-loc(extern):::al linkage, :::no-loc(extern)::: modifier'
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
no-loc:
- ':::no-loc(extern):::'
- ':::no-loc(const):::'
- ':::no-loc(constexpr):::'
- ':::no-loc(permissive):::'
ms.openlocfilehash: 510352f9e99e513f4a426f6ef89be4474085d97c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227505"
---
# <a name="no-locextern-c"></a>:::no-loc(extern)::: (C++)

キーワードは、 **`:::no-loc(extern):::`** グローバル変数、関数、またはテンプレート宣言に適用できます。 シンボルに* :::no-loc(extern)::: al リンケージ*があることを指定します。 リンケージの背景情報と、グローバル変数の使用を推奨しない理由については、「[翻訳単位とリンケージ](program-and-linkage-cpp.md)」を参照してください。

**`:::no-loc(extern):::`** キーワードには、コンテキストに応じて次の4つの意味があります。

- 非 **`:::no-loc(const):::`** グローバル変数宣言では、 **`:::no-loc(extern):::`** 変数または関数が別の翻訳単位で定義されていることを指定します。 は、 **`:::no-loc(extern):::`** 変数が定義されているものを除くすべてのファイルに適用する必要があります。

- 変数宣言では、 **`:::no-loc(const):::`** 変数に al リンケージがあることを指定し :::no-loc(extern)::: ます。 は、 **`:::no-loc(extern):::`** すべてのファイルのすべての宣言に適用する必要があります。 (グローバル **`:::no-loc(const):::`** 変数には、既定で内部リンケージがあります)。

- ** :::no-loc(extern)::: "C"** は、関数が他の場所で定義され、C 言語の呼び出し規約を使用することを指定します。 :::no-loc(extern):::"C" 修飾子は、ブロック内の複数の関数宣言にも適用できます。

- テンプレート宣言で、 **`:::no-loc(extern):::`** テンプレートが他の場所で既にインスタンス化されていることを指定します。 **`:::no-loc(extern):::`** 現在の場所に新しいインスタンスを作成するのではなく、他のインスタンス化を再利用できるようにコンパイラに指示します。 のこの使用方法の詳細について **`:::no-loc(extern):::`** は、「[明示的なインスタンス化](explicit-instantiation.md)」を参照してください。

## <a name="no-locextern-linkage-for-non-no-locconst-globals"></a>:::no-loc(extern):::非グローバルのリンケージ :::no-loc(const):::

リンカーは、 **`:::no-loc(extern):::`** グローバル変数宣言の前に参照すると、別の翻訳単位で定義を検索します。 **`:::no-loc(const):::`** グローバルスコープでの非変数の宣言は、 :::no-loc(extern)::: 既定では al です。 **`:::no-loc(extern):::`** 定義を提供しない宣言にのみ適用されます。

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
:::no-loc(extern)::: int i;  // declaration only. same as i in FileA

//fileC.cpp
:::no-loc(extern)::: int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
:::no-loc(extern)::: int i = 43; // same error (:::no-loc(extern)::: is ignored on definitions)
```

## <a name="no-locextern-linkage-for-no-locconst-globals"></a>:::no-loc(extern):::globals のリンケージ :::no-loc(const):::

**`:::no-loc(const):::`** グローバル変数には、既定で内部リンケージがあります。 変数に al リンケージを設定する場合は、 :::no-loc(extern)::: キーワードを **`:::no-loc(extern):::`** 定義に、他のファイル内の他のすべての宣言に適用します。

```cpp
//fileA.cpp
:::no-loc(extern)::: :::no-loc(const)::: int i = 42; // :::no-loc(extern)::: :::no-loc(const)::: definition

//fileB.cpp
:::no-loc(extern)::: :::no-loc(const)::: int i;  // declaration only. same as i in FileA
```

## <a name="no-locextern-no-locconstexpr-linkage"></a>:::no-loc(extern)::::::no-loc(constexpr):::リンケージ

Visual Studio 2017 バージョン15.3 以前では、 **`:::no-loc(constexpr):::`** 変数がとしてマークされている場合でも、コンパイラは常に変数内部リンケージを指定していました **`:::no-loc(extern):::`** 。 Visual Studio 2017 バージョン15.5 以降では、 [/zc: :::no-loc(extern)::: Constexpr](../build/reference/zc-:::no-loc(extern)::::::no-loc(constexpr):::.md)コンパイラスイッチにより、正しい標準準拠の動作が有効になります。 最終的には、このオプションが既定値になります。 [/:::no-loc(permissive):::-](../build/reference/:::no-loc(permissive):::-standards-conformance.md)オプションで **/Zc: :::no-loc(extern)::: Constexpr**が有効になっていません。

```cpp
:::no-loc(extern)::: :::no-loc(constexpr)::: int x = 10; //error LNK2005: "int :::no-loc(const)::: x" already defined
```

宣言された変数がヘッダーファイルに含まれている場合は **`:::no-loc(extern):::`** **`:::no-loc(constexpr):::`** 、 `__declspec(selectany)` 重複する宣言を正しく組み合わせるようにマークする必要があります。

```cpp
:::no-loc(extern)::: :::no-loc(constexpr)::: __declspec(selectany) int x = 10;
```

## <a name="no-locextern-c-and-no-locextern-c-function-declarations"></a>:::no-loc(extern):::"C" :::no-loc(extern)::: 関数と "C++" 関数宣言

C++ では、文字列と共に使用する場合、 **`:::no-loc(extern):::`** 別の言語のリンケージ規則が宣言子に使用されることを指定します。 C 関数とデータは、以前に C リンケージを持つように宣言されている場合にのみアクセスできます。 ただし、別にコンパイルされた翻訳単位で定義する必要があります。

Microsoft C++ では、*文字列リテラル*フィールドに文字列 **"C"** と **"C++"** がサポートされています。 すべての標準インクルードファイルは、 ** :::no-loc(extern)::: "C"** 構文を使用して、ランタイムライブラリ関数を C++ プログラムで使用できるようにします。

## <a name="example"></a>例

次の例は、C リンケージを持つ名前を宣言する方法を示しています。

```cpp
// Declare printf with C linkage.
:::no-loc(extern)::: "C" int printf(:::no-loc(const)::: char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
:::no-loc(extern)::: "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
:::no-loc(extern)::: "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
:::no-loc(extern)::: "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

:::no-loc(extern)::: "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
:::no-loc(extern)::: "C" int errno;
```

関数に複数のリンケージ指定がある場合は、それに同意する必要があります。 C と C++ の両方のリンケージを持つ関数を宣言すると、エラーになります。 また、プログラム内に、リンケージ指定子を含む関数宣言と含まない関数宣言がある場合、リンケージ指定子を含む宣言を最初に記述する必要があります。 既にリンケージ指定を持つ関数の冗長な宣言には、最初の宣言で指定したリンケージが与えられます。 次に例を示します。

```cpp
:::no-loc(extern)::: "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
:::no-loc(extern)::: "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)\
[翻訳単位とリンケージ](program-and-linkage-cpp.md)\
[:::no-loc(extern):::C でのストレージクラス指定子](../c-language/:::no-loc(extern):::-storage-class-specifier.md)\
[C での識別子の動作](../c-language/behavior-of-identifiers.md)\
[C でのリンケージ](../c-language/linkage.md)
