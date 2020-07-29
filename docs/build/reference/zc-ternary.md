---
title: /Zc:ternary (条件演算子ルールの強制)
ms.date: 09/12/2019
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: 04bd0c49528d86ddd4d1e6c77804cf64278db188
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211880"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>`/Zc:ternary`(条件演算子の規則を適用します)

条件演算子式の2番目と3番目のオペランドの型および const または volatile (cv) 修飾子に対して、C++ 標準規則の適用を有効にします。

## <a name="syntax"></a>構文

> **`/Zc:ternary`**[**`-`**]

## <a name="remarks"></a>解説

Visual Studio 2017 以降では、コンパイラは C++ 標準の*条件演算子*() の動作をサポートしてい **`?:`** ます。 これは、*三項演算子*とも呼ばれます。 C++ 標準では、3つの条件のうちの1つを満たす必要があります。オペランドは同じ型であるか、 **`const`** または **`volatile`** 修飾 (cv 修飾) である必要があります。または、1つのオペランドだけを同じ型に明確に変換できる必要があります。 または、一方または両方のオペランドが throw 式である必要があります。 Visual Studio 2017 バージョン15.5 より前のバージョンでは、コンパイラは標準であいまいと見なされる変換を許可していました。

このオプションを指定すると、 **`/Zc:ternary`** コンパイラは標準に準拠します。 一致する型の規則を満たしていないコードと、2番目と3番目のオペランドの cv 修飾子を拒否します。

**`/Zc:ternary`** Visual Studio 2017 では、このオプションは既定でオフになっています。 **`/Zc:ternary`** 準拠の動作を有効にしたり、 **`/Zc:ternary-`** 以前の非準拠のコンパイラの動作を明示的に指定したりするには、を使用します。 [`/permissive-`](permissive-standards-conformance.md)オプションはこのオプションを暗黙的に有効にしますが、を使用してオーバーライドすることもでき **`/Zc:ternary-`** ます。

### <a name="examples"></a>例

このサンプルでは、型からの非明示的な初期化と型への変換の両方を提供するクラスがあいまいな変換につながる可能性があることを示します。 このコードは、既定ではコンパイラによって受け入れられますが、 **/`Zc:ternary`** またはが指定されている場合は拒否され **`/permissive-`** ます。

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

このコードを修正するには、優先共通型への明示的なキャストを行うか、型変換の一方向を回避します。 変換を明示的に行うことによって、コンパイラが型変換に一致しないようにすることができます。

この一般的なパターンの重要な例外は、オペランドの型が、、など、null で終わる文字列型の1つである場合です `const char*` `const char16_t*` 。 また、配列型と、それらが減衰するポインター型を使用して効果を再現することもできます。 の実際の2番目または3番目のオペランドが、対応する型の文字列リテラルである場合の動作は、 `?:` 使用される言語標準によって異なります。 C++ 17 では、C++ 14 からこのケースのセマンティクスが変更されています。 その結果、コンパイラは、次の例のコードを既定値の下で受け入れ **`/std:c++14`** ますが、を指定した場合はそれを拒否し **`/std:c++17`** ます。

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

このコードを修正するには、いずれかのオペランドを明示的にキャストします。

で **`/Zc:ternary`** は、コンパイラは、引数の1つが型 **`void`** で、もう一方が式ではない条件演算子を拒否し **`throw`** ます。 このパターンの一般的な用途は、アサートに似たマクロです。

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

一般的な解決策は、void 以外の引数をに置き換えることです `void()` 。

このサンプルでは、との両方でエラーが生成されるコードを示し **`/Zc:ternary`** **`/Zc:ternary-`** ます。

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

このコードでは、以前に次のエラーが発生しました。

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

では **`/Zc:ternary`** 、障害の原因が明らかになります。 実装で定義されたいくつかの呼び出し規約を使用して、各ラムダを生成できます。 ただし、コンパイラは、使用可能なラムダ署名を明確に区別するための優先順位規則を持ちません。 新しい出力は次のようになります。

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

で見つかった問題の一般的な原因は、 **`/Zc:ternary`** テンプレートメタプログラミングで使用される条件演算子です。 このスイッチでは、結果の種類の一部が変更されます。 次の例は、が **`/Zc:ternary`** メタプログラミング以外のコンテキストで条件式の結果型を変更する2つのケースを示しています。

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

一般的な修正では、 `std::remove_reference` 以前の動作を維持するために必要な場合に、結果の種類に特徴を適用します。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. またはを含むように "**追加オプション**" プロパティを変更し、[ **`/Zc:ternary`** **`/Zc:ternary-`** **OK]** をクリックします。

## <a name="see-also"></a>関連項目

[`/Zc`互換性](zc-conformance.md)
