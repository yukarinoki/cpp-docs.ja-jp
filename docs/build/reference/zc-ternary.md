---
title: /Zc:ternary (条件演算子ルールの強制)
ms.date: 09/12/2019
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: 7c95f061e195ccf7fef8a6a21d193b257baa5f39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335677"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (条件演算子ルールの強制)

条件演算子式の 2 番目と 3 番目のオペランドの型と定数 (cv) 修飾に対する C++ 標準規則の適用を有効にします。

## <a name="syntax"></a>構文

> **/Zc:三項**[**-**]

## <a name="remarks"></a>解説

Visual Studio 2017 以降、コンパイラは C++ 標準*の条件演算子***(?:**) の動作をサポートしています。 三*項演算子*とも呼ばれます。 C++ 標準では、3 項オペランドが 3 つの条件のいずれかを満たす必要があります: オペランドは、同じ型と**定数**または**揮発性**修飾 (cv 修飾) のどちらであるか、または 1 つのオペランドだけが、もう一方のオペランドと同じ型に明確に変換可能で cv 修飾する必要があります。 または、一方または両方のオペランドが throw 式でなければなりません。 Visual Studio 2017 バージョン 15.5 より前のバージョンでは、コンパイラは、標準によってあいまいと見なされる変換を許可しました。

**/Zc:ternary**オプションを指定すると、コンパイラは標準に準拠します。 これは、一致した型の規則を満たさないコードと、2 番目と 3 番目のオペランドの cv 修飾を拒否します。

Visual Studio 2017 では **、/Zc:ternary**オプションは既定でオフになっています。 **/Zc:ternary**を使用して準拠動作を有効にするか **、/Zc:ternary-** を使用して、以前の非準拠コンパイラの動作を明示的に指定します。 [/permissive-](permissive-standards-conformance.md)オプションは暗黙的にこのオプションを有効にしますが **、/Zc:ternary-** を使用してオーバーライドできます。

### <a name="examples"></a>例

このサンプルでは、型からの非明示的な初期化と型への変換の両方を提供するクラスが、あいまいな変換を引き起こす可能性を示します。 このコードは、既定ではコンパイラによって受け入れられますが **、/Zc:ternary**または **/permissive が**指定されている場合は拒否されます。

```cpp
// zcternary1.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary1.cpp

struct A
{
   long l;
   A(int i) : l{i} {}    // explicit prevents conversion of int
   operator int() const { return static_cast<int>(l); }
};

int main()
{
   A a(42);
   // Accepted when /Zc:ternary (or /permissive-) is not used
   auto x = true ? 7 : a;  // old behavior prefers A(7) over (int)a
   auto y = true ? A(7) : a;   // always accepted
   auto z = true ? 7 : (int)a; // always accepted
   return x + y + z;
}
```

このコードを修正するには、優先される共通型に明示的にキャストするか、型変換の一方向を禁止します。 変換を明示的に指定することで、コンパイラが型変換に一致しないようにすることができます。

この共通パターンの重要な例外は、オペランドの型が、`const char*``const char16_t*`など、NULL で終わる文字列型のいずれかである場合です。 また、配列型と、それらが減衰するポインター型を使用して、効果を再現することもできます。 実際の 2 番目または 3`?:`番目のオペランドが対応する型のリテラル文字列である場合の動作は、使用される言語標準に依存します。 C++17 は、このケースのセマンティクスを C++14 から変更しました。 その結果、コンパイラは、次の例のコードを既定**の /std:c++14**で受け入れますが **、/std:c++17**を指定すると、このコードは拒否されます。

```cpp
// zcternary2.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /std:c++17 zcternary2.cpp

struct MyString
{
   const char * p;
   MyString(const char* s = "") noexcept : p{s} {} // from char*
   operator const char*() const noexcept { return p; } // to char*
};

int main()
{
   MyString s;
   auto x = true ? "A" : s; // MyString: permissive prefers MyString("A") over (const char*)s
}
```

このコードを修正するには、オペランドの 1 つを明示的にキャストします。

**/Zc:ternary**では、引数の一方が**void**型で、もう一方が throw 式ではない場合、コンパイラは条件演算子を拒否します。 このパターンの一般的な使用は、ASSERT のようなマクロです。

```cpp
// zcternary3.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /c zcternary3.cpp

void myassert(const char* text, const char* file, int line);
#define ASSERT(ex) (void)((ex) ? 0 : myassert(#ex, __FILE__, __LINE__))
// To fix, define it this way instead:
// #define ASSERT(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))

int main()
{
   ASSERT(false);  // C3447
}
```

一般的な解決策は、void 以外の引数を`void()`に置き換える方法です。

このサンプルでは **、/Zc:ternary と /Zc:ternary-** の両方でエラーを生成するコード**を**示します。

```cpp
// zcternary4.cpp
// Compile by using:
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp

int main() {
   auto p1 = [](int a, int b) { return a > b; };
   auto p2 = [](int a, int b) { return a > b; };
   auto p3 = true ? p1 : p2; // C2593 under /Zc:ternary, was C2446
}
```

このコードは以前このエラーを与えました:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

**/Zc:ternary**を使用すると、失敗の理由がより明確になります。 実装定義の呼び出し規約のうち、任意の方法を使用して各ラムダを生成できます。 ただし、コンパイラには、可能なラムダシグネチャを明確にする優先規則はありません。 新しい出力は次のようになります。

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

**/Zc:ternary**で見つかった問題の一般的な原因は、テンプレートのメタプログラミングで使用される条件演算子から来ています。 結果の種類の一部は、このスイッチの下で変更されます。 次の例は **、/Zc:ternary**が非メタ プログラミング コンテキストで条件式の結果型を変更する 2 つのケースを示しています。

```cpp
// zcternary5.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary5.cpp

int main(int argc, char**) {
   char a = 'A';
   const char b = 'B';
   decltype(auto) x = true ? a : b; // char without, const char& with /Zc:ternary
   const char(&z)[2] = argc > 3 ? "A" : "B"; // const char* without /Zc:ternary
   return x > *z;
}
```

一般的な修正は、古`std::remove_reference`い動作を保持するために必要な場合に、結果の種類に特性を適用することです。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ** > **C/C++** > **コマンド ライン**] プロパティ ページを選択します。

1. 追加**オプション**プロパティを変更して **、/Zc:ternary**または **/Zc:ternary- を**含めるには **、[OK]** をクリックします。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)
