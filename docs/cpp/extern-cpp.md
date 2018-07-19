---
title: extern (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/12/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- extern
- extern_CPP
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00b9f94d02443163f45b83d64702fe49622597cd
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261078"
---
# <a name="extern-c"></a>extern (C++)

**Extern**キーワードがそのリソースの名があることを指定するグローバル変数、関数、またはテンプレート宣言に適用される*外部リンケージ*です。 リンケージとグローバル変数の使用が推奨されない理由の背景情報については、次を参照してください。[プログラムとリンケージ](program-and-linkage-cpp.md)です。

**Extern**キーワードは、状況に応じて次の 4 つの意味を持ちます。

1. 非 const グローバル変数宣言で、 **extern**変数または関数が別の翻訳単位で定義されていることを指定します。 **Extern**変数が定義されている、1 つを除くすべてのファイルに適用する必要があります。
1. const 変数の宣言では、変数が外部リンケージを持つことを指定します。 **Extern**すべてのファイル内のすべての宣言に適用する必要があります。 (グローバルの const 変数に、既定である内部リンケージがある)。
1. **extern"C"** 関数が別の場所で定義されているし、C 言語の呼び出し規約を使用するように指定します。 Extern"C"修飾子は、ブロック内の複数の関数宣言にも適用できます。
1. テンプレートの宣言にあるテンプレートが既にインスタンス化された他の場所を指定します。 これは、最適化は、現在の場所に新しいプランを作成するのではなく、他のインスタンス化再使用できることをコンパイラに指示します。 この使用の詳細については**extern**を参照してください[テンプレート](templates-cpp.md)です。

## <a name="extern-linkage-for-non-const-globals"></a>非 const globals の外部リンケージ

ときに、リンカーは**extern**グローバル変数宣言の前に別の翻訳単位内の定義を検索します。 グローバル スコープで非 const 変数の宣言は既定では外部のみ適用**extern**宣言、定義が提供されないことにします。

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

## <a name="extern-linkage-for-const-globals"></a>const globals の外部リンケージ

A **const**グローバル変数が既定では内部リンケージを持ちます。 外部リンケージを持つ変数にする場合は、適用、 **extern**キーワードを他のファイル内の他のすべての宣言に関しても定義します。

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>Extern constexpr リンケージ

Visual Studio 2017 15.3 およびそれ以前のバージョンのコンパイラでは、変数には、extern がマークされている場合でも constexpr 変数内部リンケージが常に指定します。 Visual Studio 2017 バージョン 15.5 では、新しいコンパイラ スイッチ ([/Zc:externConstexpr](../build/reference/zc-externconstexpr.md)) により、正しい標準準拠の動作が可能になります。 最終的にこれは既定値になります。

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

ヘッダー ファイルには、変数の宣言された extern constexpr が含まれている場合、としてマークする必要があります **__declspec(selectany)** するために正しく組み合わせる、重複して宣言します。

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>extern"C"、extern"C++"関数の宣言

 C++ では、文字列を使用すると**extern**によりの別の言語のリンケージ規則が使用されているを指定します。 C の関数とデータには、C リンケージを持つと以前に宣言されている場合にのみ、アクセスできます。 ただし、別にコンパイルされた翻訳単位で定義する必要があります。

 Microsoft C は、文字列をサポートしている **"C"** と **"C++"** で、*文字列リテラル*フィールドです。 ファイルを使用してには、標準のすべてが含まれて、 **extern** C++ プログラムで使用するランタイム ライブラリ関数を許可する"C"構文です。

## <a name="example"></a>例

次の例では、C リンケージを持つ名前を宣言する方法を示します。

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

 関数に複数のリンケージ指定子がある場合、それらは一致する必要があります。関数を C と C++ 両方のリンケージを持つ関数として宣言するとエラーになります。 また、プログラム内に、リンケージ指定子を含む関数宣言と含まない関数宣言がある場合、リンケージ指定子を含む宣言を最初に記述する必要があります。 既にリンケージ指定を持つ関数の冗長な宣言には、最初の宣言で指定したリンケージが与えられます。 例えば:

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

- [キーワード](../cpp/keywords-cpp.md)
- [プログラムとリンケージ](program-and-linkage-cpp.md)
- [extern C では、ストレージ クラス指定子](../c-language/extern-storage-class-specifier.md) 
- [C 識別子の動作](../c-language/behavior-of-identifiers.md) 
- [C リンケージ](../c-language/linkage.md)