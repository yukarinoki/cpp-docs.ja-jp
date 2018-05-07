---
title: コンパイラ エラー C2065 |Microsoft ドキュメント
ms.custom: ''
ms.date: 09/01/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e67fcac9593dc4ad11dbff0cc479ac24d624110
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2065"></a>コンパイラ エラー C2065

> '*識別子*': 宣言されていない識別子

コンパイラは、識別子の宣言を見つけることができません。 このエラーの多くの原因があります。 C2065 の最も一般的な原因は、識別子が宣言されていない、識別子のスペルが間違って、識別子が宣言されているヘッダーが、ファイルに含まれていない、または識別子が不足してスコープ修飾子、たとえば、`cout`の代わりに`std::cout`. C++ の宣言の詳細については、次を参照してください。[宣言と定義 (C++)](../../cpp/declarations-and-definitions-cpp.md)です。

ここでいくつかの一般的な問題とソリューションをより詳細には。

## <a name="the-identifier-is-undeclared"></a>識別子が宣言されていません

識別子が変数または関数名の場合を使用する前に宣言する必要があります。 関数の宣言関数を使用する前にそのパラメーターの型も含める必要があります。 使用して、変数が宣言された場合`auto`コンパイラは、初期化子から型を推論できる必要があります。

識別子は、クラスまたは構造体のメンバーであるか、名前空間で宣言されている場合、は、構造体、クラス、または名前空間のスコープ外に使用する場合、クラスまたは構造体名または名前空間の名前で修飾する必要があります。 または、名前空間必要があります内に収める範囲によって、`using`などディレクティブ`using namespace std;`、メンバー名は別にスコープ内に収める必要がありますか、`using`宣言など`using std::string;`です。 それ以外の場合、非修飾名は、現在のスコープで宣言されていない識別子であると見なされます。

識別子が、ユーザー定義型のタグなどに設定されている場合、`class`または`struct`を使用する前に、タグの型を宣言する必要があります。 たとえば、宣言`struct SomeStruct { /*...*/ };`変数を宣言する前に存在する必要があります`SomeStruct myStruct;`コードにします。

使用して型を宣言する必要があります、識別子が、型の別名の場合、`using`宣言または`typedef`を使用する前にします。 たとえば、宣言する必要があります`using my_flags = std::ios_base::fmtflags;`を使用して`my_flags`の型の別名として`std::ios_base::fmtflags`です。

## <a name="example-misspelled-identifier"></a>例: スペルの正しくない識別子

このエラーは、識別子名のスペルが誤っていない、または識別子、間違った大文字と小文字を区別を使用するときによく発生します。 宣言内の名前を使用する名前と正確に一致する必要があります。

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

## <a name="example-use-an-unscoped-identifier"></a>例: 対象範囲外の識別子を使用します。

このエラーは、ユーザーの識別子は正しくスコープでない場合に発生することができます。 使用するときに、C2065 を表示する場合`cout`、これが原因です。 C++ 標準ライブラリ関数および演算子完全修飾されていない名前空間でまたはいないを移動する場合、`std`名前空間を使用して、現在のスコープを`using`ディレクティブ、コンパイラが検出できないことです。 この問題を解決する必要がありますか、完全に識別子の名前を修飾または指定した、名前空間と、`using`ディレクティブです。

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

内の宣言された識別子`class`、 `struct`、または`enum class`そのスコープの外部で使用する場合、型をその外側のスコープの名前で修飾もする必要があります。

## <a name="example-precompiled-header-isnt-first"></a>例: 最初にプリコンパイル済みヘッダーがされていません。

など、すべてのプリプロセッサ ディレクティブを配置した場合は、このエラーが発生する可能性が #include には、#define、または #pragma、前に、#include プリコンパイル済みヘッダー ファイルの include です。 ソース ファイルでプリコンパイル済みヘッダー ファイルを使用する場合 (を使用してコンパイルされる場合に、 **/Yu**コンパイラ オプション)、プリコンパイル済みヘッダー ファイルの前にすべてのプリプロセッサ ディレクティブは無視されます。

この例は、ため、コンパイルが失敗した`cout`と`endl`で定義されて、 \<iostream > ヘッダーで、プリコンパイル済みヘッダー ファイルの前に含まれているので無視されます。 この例をビルドするには、3 つすべてのファイルを作成し、stdafx.cpp をコンパイル C2065_pch.cpp をコンパイルします。

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

この問題を解決するには追加、# の include \<iostream > プリコンパイル済みヘッダー ファイル、または、ソース ファイルに含まれているプリコンパイル済みヘッダー ファイルの後に移動します。

## <a name="example-missing-header-file"></a>例: ヘッダー ファイルがありません。

識別子を宣言するヘッダー ファイルが含まれているいません。 それを使用するすべてのソース ファイルで、識別子の宣言を格納しているファイルが含まれていることを確認してください。

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

他の考えられる原因は含めずに、初期化子リストを使用するかどうか、 \<initializer_list > ヘッダー。

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

定義した場合は、Windows デスクトップ アプリのソース ファイルでこのエラーを参照してください可能性があります`VC_EXTRALEAN`、 `WIN32_LEAN_AND_MEAN`、または`WIN32_EXTRA_LEAN`です。 これらのプリプロセッサ マクロは、windows.h および afxv からいくつかのヘッダー ファイルを除外する\_w32.h の高速にコンパイルします。 Windows.h および afxv_w32.h 除外された項目の最新の状態の詳細についてを参照してください。

## <a name="example-missing-closing-quote"></a>例: 閉じかっこがありません。

このエラーは、文字列定数の後に、終わりの引用符がない場合に発生することができます。 これは、コンパイラと混同する簡単な方法です。 不足している終わりの引用符が、報告されたエラーの場所の前に複数の行をする可能性がある注意してください。 

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

このエラーは、反復子変数を宣言する場合に発生することができます、`for`ループ、および、使用しようとその反復子変数のスコープ外、`for`ループします。 コンパイラにより、 [/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)既定ではコンパイラ オプション。 参照してください[デバッグ反復子のサポート](../../standard-library/debug-iterator-support.md)詳細についてはします。

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

このエラーは、関数または現在の構成がコンパイルされていない条件付きでコンパイルされたコード内にある変数を参照する場合に発生することができます。 ビルド環境で現在サポートされていないヘッダー ファイルで関数を呼び出す場合にも発生することができます。 特定の変数または関数がある場合のみ、特定のプリプロセッサ マクロが定義されている場合、同じプリプロセッサ マクロが定義されている場合、これらの関数を呼び出すコードをコンパイルすることができますのみを確認します。 この問題がやすい IDE では、現在のビルド構成の必要なプリプロセッサ マクロが定義されていない場合、関数の宣言がグレーです。

デバッグ ビルドは、市販のない場合に機能するコードの例を次に示します。

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

## <a name="example-ccli-type-deduction-failure"></a>例: C + + CLI 型推論が失敗

このエラーは、目的の型引数を使用して、パラメーターから推測できない場合のジェネリック関数を呼び出すときに発生します。 詳細については、次を参照してください。[ジェネリック関数 (C + + CLI)](../../windows/generic-functions-cpp-cli.md)です。

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

## <a name="example-ccli-attribute-parameters"></a>例: C + + CLI 属性パラメーター

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
