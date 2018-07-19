---
title: /Zc:ternary (演算子の条件付き規則の実施) |Microsoft ドキュメント
ms.date: 3/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:ternary
dev_langs:
- C++
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
author: corob-msft
ms.author: corob
ms.openlocfilehash: 613381795fb962e1f10ec01598748b617b7543aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380824"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (演算子の条件付き規則の適用)

型の C++ 標準の規則の実施段階および条件演算子の式で 2 番目と 3 番目のオペランドが const または volatile (cv) で認定を有効にします。

## <a name="syntax"></a>構文

> **/Zc:ternary**[**-**]

## <a name="remarks"></a>コメント

Visual Studio 15.3 のバージョンでは C++ の標準的な条件 (三項) 演算子のコンパイラ サポート (**?:**) 動作します。 C++ 標準では、いずれかのオペランドは、cv 修飾子と同じ型のまたは 1 つだけのオペランドが同じ型と、他の cv 修飾子に明確に変換できるかに throw 式を指定する 1 つまたは両方のオペランドが必要です。 Visual Studio version 15.5 より前に、のバージョンでは、コンパイラは、標準であいまいと見なされる変換を許可します。 ときに、 **/Zc:ternary**オプションを指定すると、コンパイラは、標準に準拠しているし、は一致する型と、2 番目と 3 番目のオペランドの cv 認定の規則を満たしていないコードを拒否します。

**/Zc:ternary**オプションは既定でオフになっています。 使用して **/Zc:ternary**準拠の動作を有効にまたは **/Zc:ternary-** 以前非準拠コンパイラの動作を明示的に指定します。 [寛容/-](permissive-standards-conformance.md)オプションは、このオプションを暗黙的にできますを使用してオーバーライドできます **/Zc:ternary-** です。

### <a name="examples"></a>使用例

このサンプルでは、型と型への変換から両方の非明示的な初期化を提供するクラスがあいまいな変換につながる可能性が方法を示します。 このコードは、既定では、コンパイラによって受け入れられますが、場合に拒否 **/Zc:ternary**または**寛容/-** を指定します。

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

優先の共通の型に明示的なキャストを作成または変換を明示的にすることにより、コンパイラ、一致の検索の種類への参加からの変換の 1 つの方向を回避するためには必要な修正されます。

この一般的なパターンの重要な例外は、オペランドの型は、null で終わる文字列型の 1 つをなどが`const char*`、`const char16_t*`のようにします。 これは、配列の型およびに decay、ポインター型でも再現できます。 動作時に実際の 2 番目または 3 番目のオペランドですか?: は、対応する型の文字列リテラルが使用される標準の言語に依存します。 C++ 17 には、c++ 14 からこの場合のセマンティクスが変更されました。 下にある次の例のコードが受け入れられる結果として、 **/std:c + + 14** (コンパイラの既定値) では場合に拒否 **/std:c + + 17**を指定します。

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

このコードを修正するのには、明示的をキャスト、オペランドの 1 つ。

**/Zc:ternary**、ここで、引数の 1 つはコンパイラ拒否の条件演算子は void 型および他の throw 式ではありません。 これらの一般的な用途は、アサートに似たマクロには。

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

一般的なソリューションでは、void でない引数を void() 単に置き換えます。

このサンプルは、両方のエラーを生成するコードを示しています **/Zc:ternary**と **/Zc:ternary-**:。

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

このコードでは、このエラーが発生したしました。

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

**/Zc:ternary**失敗の理由が明確になりますアーキテクチャでは実装定義の呼び出し規約のいくつかのいずれかを各ラムダの生成に使用できる場所、コンパイラを示しませんそれらの間の基本設定。可能なラムダのシグネチャを明確に区別可能性があります。 新しい出力は、次のようになります。

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

導入に関連する問題の一般的な原因 **/Zc:ternary**このスイッチの下の変更結果型の一部としてのテンプレート メタプログラミングで条件演算子の使用に由来します。 次の例では、2 つのケースで **/Zc:ternary**非メタ プログラミング コンテキストの条件付きの式の結果型を変更します。

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

このような場合の一般的な解像度を適用する、`std::remove_reference`結果での特徴である従来の動作を維持するために必要な場所を入力します。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:ternary**または **/Zc:ternary-** を選択し**OK**です。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)  
