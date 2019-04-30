---
title: コンパイラ エラー C2065
ms.date: 09/01/2017
f1_keywords:
- C2065
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
ms.openlocfilehash: 3daf2cd532cd07225b822c80b46fc28274d4e2a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408616"
---
# <a name="compiler-error-c2065"></a>コンパイラ エラー C2065

> '*identifier*' : undeclared identifier

コンパイラは、識別子の宣言を見つけることができません。 このエラーの考えられる原因の多くがあります。 C2065 の最も一般的な原因は、識別子が宣言されていない、識別子のスペルが間違って、識別子が宣言されているヘッダーがファイルに含まれていないまたは識別子が、スコープ修飾子をなどにありません`cout`の代わりに`std::cout`. C++ の宣言の詳細については、次を参照してください。[宣言と定義 (C++)](../../cpp/declarations-and-definitions-cpp.md)します。

ここで、いくつかの一般的な問題とソリューションはさらに詳しく説明です。

## <a name="the-identifier-is-undeclared"></a>識別子が宣言されていません

識別子が、変数または関数名の場合を可能にする前に宣言する必要があります。 関数の宣言、関数を使用する前にそのパラメーターの型も含める必要があります。 使用して、変数を宣言する場合`auto`コンパイラは初期化子から型を推論できる必要があります。

識別子は、クラスまたは構造体のメンバーまたは名前空間で宣言されている、構造体、クラス、または名前空間のスコープ外に使用する場合、クラスまたは構造体の名前または名前空間の名前によって修飾する必要があります。 または、名前空間がによってスコープに取り込む必要がある、`using`などディレクティブ`using namespace std;`、メンバー名は、スコープに取り込む必要があるか、`using`宣言など`using std::string;`。 それ以外の場合、非修飾名は、現在のスコープで宣言されていない識別子と見なされます。

識別子が、ユーザー定義型のタグなどに設定されている場合、`class`または`struct`を使用するタグの型を宣言する必要があります。 たとえば、宣言`struct SomeStruct { /*...*/ };`変数を宣言する前に存在する必要があります`SomeStruct myStruct;`コードでします。

使用して型を宣言する必要があります、識別子が型の別名の場合、`using`宣言または`typedef`を使用します。 たとえば、宣言する必要があります`using my_flags = std::ios_base::fmtflags;`使用する前に`my_flags`の型の別名として`std::ios_base::fmtflags`します。

## <a name="example-misspelled-identifier"></a>例: スペル ミスの識別子

このエラーは、識別子名のスペルが誤っていない、または識別子間違ったの大文字と小文字の文字を使用するときによく発生します。 宣言内の名前を使用する名前と正確に一致する必要があります。

```cpp
// C2065_spell.cpp
// compile with: cl /EHsc C2065_spell.cpp
#include <iostream>
using namespace std;
int main() {
    int someIdentifier = 42;
    cout << "Some Identifier: " << SomeIdentifier << endl;
    // C2065: 'SomeIdentifier': undeclared identifier
    // To fix, correct the spelling:
    // cout << "Some Identifier: " << someIdentifier << endl;
}
```

## <a name="example-use-an-unscoped-identifier"></a>例: スコープを持たない識別子を使用します。

このエラーは、識別子のスコープは正しくない場合に発生します。 表示を使用する場合は、C2065 場合`cout`、これが原因です。 C++ 標準ライブラリ関数および演算子は完全修飾名前空間でまたはが戻らない場合、`std`名前空間を使用して、現在のスコープを`using`ディレクティブ、コンパイラ、見つけることができません。 この問題を解決する完全に識別子の名前を修飾かと名前空間を指定、`using`ディレクティブ。

この例は、ため、コンパイルが失敗した`cout`と`endl`で定義されて、`std`名前空間。

```cpp
// C2065_scope.cpp
// compile with: cl /EHsc C2065_scope.cpp
#include <iostream>
// using namespace std;   // Uncomment this line to fix

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead
    std::cout << "Hello" << std::endl;
}
```

内部で宣言される識別子`class`、 `struct`、または`enum class`そのスコープの外部で使用すると、型をその外側のスコープの名前で修飾もする必要があります。

## <a name="example-precompiled-header-isnt-first"></a>例: 最初にプリコンパイル済みヘッダーがされていません。

など、任意のプリプロセッサ ディレクティブを配置した場合、このエラーが発生する可能性が #include には、#、define または #pragma、前に、# プリコンパイル済みヘッダー ファイルの include します。 ソース ファイルでプリコンパイル済みヘッダー ファイルを使用する場合 (を使用してコンパイルされる場合は、 **/Yu**コンパイラ オプション) プリコンパイル済みヘッダー ファイルの前にすべてのプリプロセッサ ディレクティブは無視されます。

この例は、ため、コンパイルが失敗した`cout`と`endl`で定義されて、 \<iostream > ヘッダーで、プリコンパイル済みヘッダー ファイルの前に含まれているため、無視されます。 この例をビルドするには、すべての 3 つのファイルを作成し、stdafx.cpp のコンパイル C2065_pch.cpp をコンパイルします。

```cpp
// stdafx.h
#include <stdio.h>
```

```cpp
// stdafx.cpp
// Compile by using: cl /EHsc /W4 /c /Ycstdafx.h stdafx.cpp
#include <stdafx.h>
```

```cpp
// C2065_pch.cpp
// compile with: cl /EHsc /W4 /Yustdafx.h C2065_pch.cpp
#include <iostream>
#include "stdafx.h"
using namespace std;

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
}
```

この問題を解決するには追加、# の include \<iostream > にプリコンパイル済みヘッダー ファイル、またはプリコンパイル済みヘッダー ファイルの後に含まれているソース ファイルに移動します。

## <a name="example-missing-header-file"></a>例: ヘッダー ファイルがありません。

識別子を宣言するヘッダー ファイルを含めていなかったことです。 それを使用するすべてのソース ファイルで、識別子の宣言を含むファイルが含まれていることを確認します。

```cpp
// C2065_header.cpp
// compile with: cl /EHsc C2065_header.cpp

//#include <stdio.h>
int main() {
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined
}
```

もう 1 つの考えられる原因は含めずに、初期化子リストを使用するかどうか、 \<initializer_list > ヘッダー。

```cpp
// C2065_initializer.cpp
// compile with: cl /EHsc C2065_initializer.cpp

// #include <initializer_list>
int main() {
    for (auto strList : {"hello", "world"})
        if (strList == "hello") // C2065: 'strList': undeclared identifier
            return 1;
    // To fix, uncomment the #include <initializer_list> line
}
```

定義する場合は、Windows デスクトップ アプリのソース ファイルでこのエラーを参照してくださいが`VC_EXTRALEAN`、 `WIN32_LEAN_AND_MEAN`、または`WIN32_EXTRA_LEAN`します。 これらのプリプロセッサ マクロは、windows.h および afxv からいくつかのヘッダー ファイルを除外\_w32.h を高速化をコンパイルします。 Windows.h と afxv_w32.h の除外された最新の状態の説明を参照してください。

## <a name="example-missing-closing-quote"></a>例: 閉じかっこがありません。

このエラーは、文字列定数の後に終わりの引用符がない場合に発生することができます。 これは、コンパイラが混乱する簡単な方法です。 終わりの引用符が不足している可能性が報告されたエラーの場所の前にいくつかの行にあるに注意してください。

```cpp
// C2065_quote.cpp
// compile with: cl /EHsc C2065_quote.cpp
#include <iostream>

int main() {
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee";
    std::cout << "Name: " << first
        << " " << last << std::endl; // C2065: 'last': undeclared identifier
}
```

## <a name="example-use-iterator-outside-for-loop-scope"></a>例: for ループ スコープの外側の反復子を使用します。

反復子変数を宣言する場合に、このエラーが発生することができます、`for`ループし、その反復子変数のスコープ外で使用しよう、`for`ループします。 コンパイラにより、 [/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)コンパイラ オプションが既定でします。 参照してください[Debug Iterator Support](../../standard-library/debug-iterator-support.md)詳細についてはします。

```cpp
// C2065_iter.cpp
// compile with: cl /EHsc C2065_iter.cpp
#include <iostream>
#include <string>

int main() {
    // char last = '!';
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" };
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
}
```

## <a name="example-preprocessor-removed-declaration"></a>プリプロセッサの削除宣言の例:

このエラーは、関数または変数が現在の構成がコンパイルされていない条件付きでコンパイルされたコードを参照する場合に発生することができます。 これは、ビルド環境で現在サポートされていませんが、ヘッダー ファイルで関数を呼び出す場合にも発生することができます。 特定の変数または関数は特定のプリプロセッサ マクロが定義されている場合にのみ使用可能な同じプリプロセッサ マクロが定義されている場合、これらの関数を呼び出すコードをコンパイルすることができますのみを確認します。 この問題は、現在のビルド構成の必要なプリプロセッサ マクロが定義されていない場合、関数の宣言がグレーためを IDE では、見つけやすくします。

これは、デバッグ、ビルドしますが、小売りのない場合に動作するコードの例を示します。

```cpp
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate);
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```

## <a name="example-ccli-type-deduction-failure"></a>例:C +/cli CLI 型推論が失敗

このエラーは、目的の型引数を使用するパラメーターから推測できない場合の汎用関数を呼び出すときに発生します。 詳細については、次を参照してください。[ジェネリック関数 (C +/cli CLI)](../../extensions/generic-functions-cpp-cli.md)します。

```cpp
// C2065_b.cpp
// compile with: cl /clr C2065_b.cpp
generic <typename ItemType>
void G(int i) {}

int main() {
   // global generic function call
   G<T>(10);     // C2065
   G<int>(10);   // OK - fix with a specific type argument
}
```

## <a name="example-ccli-attribute-parameters"></a>例:C +/cli CLI 属性のパラメーター

このエラーは、Visual C++ 属性のパラメーター チェックを行う Visual C++ 2005 で行ったコンパイラ準拠作業の結果として生成されることもあります。

```cpp
// C2065_attributes.cpp
// compile with: cl /c /clr C2065_attributes.cpp
[module(DLL, name=MyLibrary)];   // C2065
// try the following line instead
// [module(dll, name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```
