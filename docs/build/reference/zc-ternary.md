---
title: /Zc:ternary (条件演算子ルールの適用)
ms.date: 3/06/2018
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: cb9a4f8468a9cb57af711cdca36ee343e5092493
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816491"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (条件演算子ルールの適用)

型の C++ 標準の規則の適用と条件演算子の式で 2 番目と 3 番目のオペランドが const または volatile で (cv) 認定を有効にします。

## <a name="syntax"></a>構文

> **/Zc:ternary**[**-**]

## <a name="remarks"></a>Remarks

Visual Studio バージョン 15.3 では C++ 標準の条件付き (または三項) 演算子に対するコンパイラ サポート (**?:**) 動作します。 C++ 標準では、cv 修飾子と同じ型のまたは同じの型と、ほかの cv 認定に明確に変換可能であるオペランドを 1 つだけや throw 式を指定する 1 つまたは両方のオペランドにする、いずれかのオペランドが必要です。 Visual Studio バージョン 15.5 より前に、のバージョンでは、コンパイラは、標準であいまいと見なされる変換を許可します。 ときに、 **/Zc:ternary**オプションを指定すると、コンパイラは、標準に準拠しているし、は一致する型と 2 番目と 3 番目のオペランドの cv で修飾の規則に従っていないコードを拒否します。

**/Zc:ternary**オプションは既定でオフです。 使用 **/Zc:ternary**準拠の動作を有効にまたは **/Zc:ternary-** 以前非準拠コンパイラの動作を明示的に指定します。 [/Permissive -](permissive-standards-conformance.md)オプションでは、このオプションは、暗黙的に有効化を使用してオーバーライドできますが、 **/Zc:ternary-** します。

### <a name="examples"></a>使用例

このサンプルでは、どの型の型への変換と両方明示的でない初期化を提供するクラスが、あいまいな変換につながります。 を示します。 このコードは既定では、コンパイラによって受け入れられますが、場合に拒否 **/Zc:ternary**または **/permissive -** を指定します。

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

必要な修正の方法では、ことを推奨される共通の型に明示的なキャストまたは明示的な変換を行う 1 つの方向への参加型の一致をコンパイラ検索からの変換を防ぐためです。

この一般的なパターンには、次の重要な例外がオペランドの型がなど、null で終わる文字列型のいずれかが`const char*`、`const char16_t*`など。 配列の型およびに decay、ポインター型でこれを再現できます。 動作とする実際の 2 番目または 3 番目のオペランドですか?: は、対応する型の文字列リテラルが使用される標準の言語に依存します。 C++ 17 には、c++ 14 からこの場合のセマンティクスが変更されました。 結果として、次の例ではコードが正しい **/std:c + + + 14** (コンパイラの既定値) では場合に拒否 **/std:c + + + 17**が指定されてです。

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

**/Zc:ternary**のいずれかの引数がコンパイラ拒否の条件演算子は void 型し、もう一方が throw 式ではありません。 これらの一般的な用途は、アサートに似たマクロには。

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

典型的なソリューションでは、単に非 void 引数を void() に置き換えます。

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

**/Zc:ternary**失敗の理由が明確になりますアーキテクチャのいくつか実装で定義された呼び出し元の規則を各ラムダの生成に使用できる場所で、コンパイラを示しませんそれらの間での基本設定。可能なラムダのシグネチャを区別する可能性があります。 新しい出力は、次のようになります。

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

導入に関連する問題の一般的な原因 **/Zc:ternary**このスイッチでの変更結果型の一部としてテンプレート メタプログラミング、条件演算子の使用に由来します。 次の例では、2 つのケースで **/Zc:ternary**非メタ プログラミング コンテキストでの条件付きの式の結果型を変更します。

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

このような場合の一般的な解決方法は、適用する、`std::remove_reference`結果での特徴であるが、以前の動作を維持するために必要な場所を入力します。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:ternary**または **/Zc:ternary-** 選び、 **OK**します。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)
