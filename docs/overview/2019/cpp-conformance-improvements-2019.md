---
title: C++ 準拠の強化
ms.date: 05/16/2019
description: Visual Studio 2019 の Microsoft C++ は、C++20 言語標準との完全準拠に向かって進んでいます。
ms.technology: cpp-language
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 02b778f10ad94342c922a4e79a856cc2a7d53076
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66451219"
---
# <a name="c-conformance-improvements-in-visual-studio-2019-rtw-and-version-161improvements161"></a>Visual Studio 2019 RTW とバージョン [16.1](#improvements_161) の C++ 準拠の強化

## <a name="improvements-in-visual-studio-2019-rtw"></a>Visual Studio 2019 RTW の機能強化

Visual Studio 2019 RTW には、Microsoft C++ コンパイラ (MSVC) の次の準拠強化、バグ修正、動作変更が含まれます。

**注:** C++20 の機能は、コンパイラと IntelliSense の C++20 実装が完了するまで `/std:c++latest` モードで利用できます。 その時点で、`/std:c++20` コンパイラ モードが導入されます。

### <a name="improved-modules-support-for-templates-and-error-detection"></a>改善されたモジュールのテンプレート サポートとエラー検出

モジュールは現在、公式に C++20 標準になりました。 改善されたサポートは、Visual Studio 2017 バージョン 15.9 で追加されました。 詳細については、「[Better template support and error detection in C++ Modules with MSVC 2017 version 15.9](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/)」 (C++ Modules での、テンプレート サポートとエラー検出に対する MSVC 2017 バージョン 15.9 を使用した改善) を参照してください。

### <a name="modified-specification-of-aggregate-type"></a>集計の種類の変更後の仕様

集計の種類の仕様が C++20 で変更されました (「[Prohibit aggregates with user-declared constructors](https://wg21.link/p1008r1)」 (ユーザー宣言コンストラクターの集計を禁止) を参照してください)。 Visual Studio 2019 の `/std:c++latest` では、ユーザー宣言コンストラクター (たとえば、コンストラクター宣言の `= default` や `= delete` を含む) を含むクラスは集計ではありません。 以前は、ユーザー指定のコンストラクターのみで、集計になる資格がクラスから剥奪されました。 今回の変更により、このような種類の初期化方法に対する制約が追加されました。

次のコードは Visual Studio 2017 ではエラーなくコンパイルされますが、Visual Studio 2019 の `/std:c++latest` では、C2280 エラーや C2440 エラーが発生します。

```cpp
struct A
{
    A() = delete; // user-declared ctor
};

struct B
{
    B() = default; // user-declared ctor
    int i = 0;
};

A a{}; // ill-formed in C++20, previously well-formed
B b = { 1 }; // ill-formed in C++20, previously well-formed
```

### <a name="partial-support-for-operator-"></a>演算子 <=> に一部対応

[P0515R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0515r3.pdf) C++20 では、3 方向の比較演算子 `<=>` が導入されました。これは "宇宙船演算子" とも呼ばれています。 `/std:c++latest` モードの Visual Studio 2019 では、この演算子の部分的サポートが導入され、現在は許可されていない構文に対してエラーが発生します。 たとえば、次のコードは Visual Studio 2017 ではエラーなくコンパイルされますが、Visual Studio 2019 の `/std:c++latest` では、複数のエラーが発生します。

```cpp
struct S
{
       bool operator<=(const S&) const { return true; }
};

template <bool (S::*)(const S&) const>
struct U { };
int main(int argc, char** argv)
{
       U<&S::operator<=> u; // In Visual Studio 2019 raises C2039, 2065, 2146.
}
```

エラーを回避するには、`U<&S::operator<= > u;` のように、最後の括弧の前でエラーを出す行にスペースを挿入します。

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>cv 修飾子が一致しない型の参照

MSVC では以前、最上位より下で、cv 修飾子が一致しない型から参照を直接バインドすることが許可されました。 そのため、参照により指示されると思われる const データを変更できる場合がありました。このコンパイラでは現在、標準で要求されるとおり、temporary が作成されます。 Visual Studio 2017 の場合、次のコードは警告なしでコンパイルされます。 Visual Studio 2019 の場合、コンパイラから *警告 C4172: \<func:#1 "?PData@X@@QBEABQBXXZ">* が発行され、ローカル変数または temporary のアドレスが返されます。

```cpp
struct X
{
    const void* const& PData() const
    {
        return _pv;
    }

    void* _pv;
};

int main()
{
    X x;
    auto p = x.PData(); // C4172
}
```
### <a name="reinterpretcast-from-an-overloaded-function"></a>オーバー ロードした関数からの `reinterpret_cast`

`reinterpret_cast` の引数は、オーバーロードした関数のアドレスが許可されるコンテキストの 1 つではありません。 次のコードは Visual Studio 2017 ではエラーなくコンパイルされますが、Visual Studio 2019 では *C2440: cannot convert from 'overloaded-function' to 'fp'* ('オーバーロードした関数' を 'fp' に変換できません) が発生します。

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

このエラーを回避するには、このシナリオで許可されるキャストを使用します。

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>ラムダ クロージャ

C++ 14 では、ラムダ クロージャの型はリテラルではありません。 このルールの最も重要な影響は、ラムダが `constexpr` 変数に割り当てられない可能性があるということです。 次のコードは Visual Studio 2017 ではエラーなくコンパイルされますが、Visual Studio 2019 では *C2127: 'l': illegal initialization of 'constexpr' entity with a non-constant expression* (定数以外の式を持つ 'constexpr' エンティティの初期化が正しくありません) が発生します。

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

エラーを回避するには、`constexpr` 修飾子を削除するか、準拠モードを `/std:c++17` に変更します。

### <a name="stdcreatedirectory-failure-codes"></a>std::create_directory エラー コード

無条件で C++20 から [P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf) が実装されました。 これにより、エラー時、ターゲットが既にディレクトリであったかどうかを確認するように `std::create_directory` が変更されます。 以前は、ERROR_ALREADY_EXISTS タイプのエラーはすべて、success-but-directory-not-created コードに変換されました。

### <a name="operatorstdostream-nullptrt"></a>operator<<(std::ostream, nullptr_t)

[LWG 2221](https://cplusplus.github.io/LWG/issue2221) に基づき、nullptrs をストリームに書き込むための `operator<<(std::ostream, nullptr_t)` が追加されました。 

### <a name="additional-parallel-algorithms"></a>追加の並列アルゴリズム

`is_sorted`、`is_sorted_until`、`is_partitioned`、`set_difference`、`set_intersection`、`is_heap`、`is_heap_until` の新しい並列バージョン。

### <a name="atomic-initialization"></a>アトミック初期化

[P0883 "Fixing atomic initialization"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf) により、含まれる T を既定初期化せず、値初期化するように `std::atomic` が変更されます。 Clang/LLVM と Microsoft Standard Library が使用されるとき、修正は有効になります。 Microsoft C++ コンパイラでは、constexpr 処理のバグに対する回避策としてこれは現在、無効になっています。

### <a name="removecvref-and-removecvreft"></a>remove_cvref と remove_cvref_t

[P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf) から型の特徴、`remove_cvref` と `remove_cvref_t` を実装しました。 それにより、(`std::decay` や `std::decay_t` とは異なり) 関数や配列をポインターに減衰させることなく、reference-ness と cv 修飾が型から削除されます。

### <a name="feature-test-macros"></a>機能テストのマクロ

[P0941R2 - 機能テスト マクロ](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html)は完全であり、`__has_cpp_attribute` がサポートされています。 機能テスト マクロはすべての標準モードでサポートされています。

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>ユーザー宣言コンストラクターによる集計の禁止

[C++20 P1008R1 - ユーザー宣言コンストラクターによる集計の禁止](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf)は完全です。

## <a name="improvements_161"></a> Visual Studio 2019 バージョン 16.1 の改善

### <a name="char8t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html)。 C++20 では、UTF-8 コード単位を表すための新しい文字型が追加されます。 C++20 の u8 文字列リテラルには、以前のケースだった `const char[N]` に代わり、型 `const char8_t[N]` が与えられます。 [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm) では、C Standard に同様の変更が提案されています。 char8_t 下位互換性改善の提案が [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html) で与えられています。 **/Zc:char8_t** コンパイラ オプションを指定すると、Microsoft C++ コンパイラでは、Visual Studio 2019 バージョン 16.1 の char8_t のサポートが追加されます。 将来的にこれは [/std:c++latest](../../build/reference/std-specify-language-standard-version.md) でサポートされます。/std:c++latest は、 **/Zc:char8_t-** 経由で C++17 の動作に戻すことができます。 IntelliSense の動力源となる EDG コンパイラではまだそれがサポートされていません。そのため、誤った IntelliSense のみのエラーが表示されますが、それは実際のコンパイルに影響を与えません。

#### <a name="example"></a>例

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtypeidentity-metafunction-and-stdidentity-function-object"></a>std::type_identity メタ関数と std::identity 関数オブジェクト

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). 非推奨 `std::identity` クラス テンプレート拡張が削除され、C++20 `std::type_identity` メタ関数と `std::identity` 関数オブジェクトに置換されました。 いずれも [/std:c++latest](../../build/reference/std-specify-language-standard-version.md) でのみ利用できます。 

次の例では、Visual Studio 2017 の `std::identity` (\<type_traits> に定義) に対して非推奨警告 C4996 が生成されます。 

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

次の例では、新しい `std::type_identity` と共に新しい `std::identity` (\<functional> で定義) を使用する方法を確認できます。

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>汎用ラムダの構文チェック

新しいラムダ プロセッサにより、汎用ラムダの [/std:c++latest](../../build/reference/std-specify-language-standard-version.md) で、あるいは **/experimental:newLambdaProcessor** を含む他の言語モードで、一部の準拠モード構文チェックが有効になります。 

Visual Studio 2017 の場合、このコードは警告なくコンパイルされますが、Visual Studio 2019 の場合、*C2760 syntax error: unexpected token '\<id-expr>', expected 'id-expression'* というエラーが出ます。

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

次の例では、コンパイラから強制されるようになった正しい構文を確認できます。

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>関数呼び出しの引数依存検索

[P0846R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0846r0.html) (C++20) 明示的なテンプレート引数を含む関数呼び出し式の引数依存照合を使用する、関数テンプレートの検索機能が強化されました。 **/std:c++latest** を必要とします。

### <a name="designated-initialization"></a>初期化の指定

[P0329R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf) (C++20) 初期化の指定により、集計初期化で、`Type t { .member = expr }` 構文を使用し、特定のメンバーを選択できます。 **/std:c++latest** を必要とします。

### <a name="new-and-updated-standard-library-functions-c20"></a>新しい Standard Library 関数と更新された Standard Library (C++20)

- `basic_string` と `basic_string_view` 向けの `starts_with()` と `ends_with()`。
- 連想コンテナーの `contains()`。
- ` list` と `forward_list` の `remove()`、`remove_if()`、`unique()` で `size_type` が返されるようになりました。
- `shift_left()` と `shift_right()` が \<algorithm> に追加されました。

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019-rtw"></a>Visual Studio 2019 RTW のバグの修正と動作の変更

### <a name="correct-diagnostics-for-basicstring-range-constructor"></a>basic_string 範囲コンストラクターの正しい診断

Visual Studio 2019 では、`basic_string` 範囲コンストラクターで `static_cast` を含むコンパイラ診断が非表示になることがなくなりました。 次のコードは Visual Studio 2017 では、`out` の初期化時、データが失われ、`wchar_t` が `char` になる可能性がありますが、警告なくコンパイルされます。

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019 の場合、*C4244: 'argument': conversion from 'wchar_t' to 'const _Elem', possible loss of data* が正しく発生します。 この計画を回避するには、この例のように std::string を初期化できます。

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>/clr または /ZW で += や -= の間違った呼び出しを正しく検出できるようになりました

`/clr` または `/ZW` で += や -= の無効な呼び出しに対して、コンパイラが何も表示せずにエラーを無視し、何のコードも生成しないというバグが Visual Studio 2017 にありました。 次のコードは Visual Studio 2017 ではエラーなくコンパイルされますが、Visual Studio 2019 の場合、*error C2845:'System::String ^': pointer arithmetic not allowed on this type* が正しく発生します。

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

この例のエラーを回避するには、`s += E::e.ToString();` のように、ToString() で演算子を使用します。

### <a name="initializers-for-inline-static-data-members"></a>インライン静的データ メンバーの初期化子

`inline` 初期化子と `static constexpr` 初期化子内の無効なメンバー アクセスが正しく検出されるようになりました。 次の例は Visual Studio 2017 ではエラーなくコンパイルされますが、`/std:c++17` モードの Visual Studio 2019 では、*error C2248: cannot access private member declared in class 'X'* が発生します。

```cpp
struct X
{
    private:
        static inline const int c = 1000;
};

struct Y : X
{
    static inline int d = c; // C2248 in Visual Studio 2019
};
```

このエラーを回避するには、メンバー `X::c` を protected として宣言します。

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>C4800 の復帰

MSVC には以前、ブール型への暗黙的変換に関するパフォーマンス警告 C4800 がありましたが、これが煩わしく、かつ非表示にできないため、Visual Studio 2017 で削除されました。 しかしながら、Visual Studio 2017 が使用されている間、この警告が役に立った事例についてたくさんのフィードバックがありました。 Visual Studio 2019 では、慎重に調整された C4800 とそれに付属する C4165 を復帰させました。いずれも明示的な型変換か該当する型の 0 と比較することで簡単に非表示にできます。 C4800 は既定でオフのレベル 4 警告であり、C4165 は既定でオフのレベル 3 警告です。 いずれも `/Wall` コンパイラ オプションで検出できます。

次の例では C4800 と C4165 が `/Wall` の下で発生します。

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

前の例の警告を回避する目的で、コードを次のように記述できます。

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>ローカル クラスのメンバー関数に本体がない

Visual Studio 2017 では、*C4822:Local class member function doesn't have a body* は、コンパイラ オプション `/w14822` が明示的に設定されている場合にのみ発生します。`/Wall` で表示されることはありません。 Visual Studio 2019 では、C4822 はデフォルトでオフの警告であり、`/w14822` を明示的に設定しなくても `/Wall` の下で見つかります。

```cpp
void foo()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>constexpr if ステートメントを含む関数テンプレートの本体

`if constexpr` ステートメントを含むテンプレート関数の本体では、一部の `/permissive-` 解析関連チェックが有効になっています。 たとえば、Visual Studio 2017 では、*C7510:'Type': use of dependent type name must be prefixed with 'typename'* は `/permissive-` オプションが設定されている場合にのみ、次のコードで発生します。 Visual Studio 2019 の場合、`/permissive-` オプションが設定されているかどうかに関係なく、同じコードでエラーが発生します。

```cpp
template <typename T>

int f()
{
    T::Type a; // error C7510

    if constexpr (T::val)
    {
        return 1;
    }
    else
    {
        return 2;
    }
}

struct X
{
    using Type = X;
    constexpr static int val = 1;
};

int main()
{
    return f<X>();
}

```

このエラーを回避するには、`typename T::Type a;` のように、`typename` キーワードを `a` の宣言に追加します。

### <a name="inline-assembly-code-is-not-supported-in-a-lambda-expression"></a>インライン アセンブリ コードがラムダ式でサポートされない

Visual C++ チームは最近、ラムダ内のインライン アセンブラーが実行時、'ebp' (リターン アドレス レジスタ) の破損につながる可能性があるセキュリティ上の問題を発見しました。 悪意のある攻撃者は、このシナリオを活用できる可能性があります。 問題の性質、インライン アセンブラーが x86 でのみサポートされるという事実、インライン アセンブラーとコンパイラの残りの部分の対話が乏しいことを考慮すると、この問題の最も安全な解決策は、ラムダ式内でインライン アセンブラーを禁止することでした。

注: 'wild' で遭遇した、ラムダ式内でのインライン アセンブラーの唯一の使い方は、リターン アドレスをキャプチャすることを目的とする使い方でした。 このシナリオでは、コンパイラ固有の `_ReturnAddress()` を使用し、すべてのプラットフォームでリターン アドレスをキャプチャできます。

次のコードでは、*C7552: inline assembler is not supported in a lambda* が Visual Studio 2017 15.9 と Visual Studio 2019 の両方で発生します。

```cpp
#include <cstdio>

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;

    auto lambda = [&]
    {
        __asm {

            mov eax, x
            mov y, eax
        }
    };

    lambda();
    return y;
}
```

このエラーを回避するには、次の例のように、名前付きの関数にアセンブリ コードを移動します。

```cpp
#include <cstdio>

void g(int& x, int& y)
{
    __asm {
        mov eax, x
        mov y, eax
    }
}

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;
    auto lambda = [&]
    {
        g(x, y);
    };
    lambda();
    return y;
}

int main()
{
    std::printf("%d\n", f());
}
```

### <a name="iterator-debugging-and-stdmoveiterator"></a>反復子のデバッグと std::move_iterator

`std::move_iterator` のラッピングを正しく解除する目的で反復子のデバッグ機能が導入されました。 たとえば、`std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` では、`memcpy` 高速パスを作動させることができるようになりました。

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>\<xkeycheck.h> キーワード強制の修正

Standard Library のマクロ化キーワード強制 \<xkeycheck.h> が汎用的なメッセージではなく、検出された実際に問題となるキーワードを表示するように修正されました。 また、C++ 20 キーワード対応となり、IntelliSense でランダムのキーワードがマクロであるととらえられることがなくなりました。

### <a name="allocator-types-un-deprecated"></a>アロケーター型の非推奨解除

`std::allocator<void>`、`std::allocator::size_type`、`std::allocator::difference_type` の非推奨が解除されました。

### <a name="correct-warning-for-narrowing-string-conversions"></a>文字列変換を絞り込むための正しい警告

C4244 絞り込み警告を間違って非表示にした、標準では呼び出されない不適切な `static_cast` が std::string から削除されました。 `std::string::string(const wchar_t*, const wchar_t*)` を呼び出そうとすると、*C4244 "narrowing a wchar_t into a char"* が正しく表示されるようになりました。

### <a name="various-filesystem-correctness-fixes"></a>\<filesystem> のさまざまな正確性修正

- ディレクトリの最後の書き込み時刻を変更しようとすると失敗する `std::filesystem::last_write_time` が修正されました。
- `std::filesystem::directory_entry` コンストラクターには、存在しないターゲット パスが指定されたとき、例外をスローせず、エラー結果が格納されるようになりました。
- existing_p がシンボリック リンクのとき、基礎となる `CreateDirectoryExW` 関数で `copy_symlink` が実行されるため、`std::filesystem::create_directory` の 2 パラメーター バージョンが 1 パラメーター バージョンを呼び出すように変更されました。
- シンボリック リンクが壊れていても `std::filesystem::directory_iterator` ではエラーを出さなくなりました。
- `std::filesystem::space` で相対パスを受け取るようになりました。
- [LWG 3096](https://cplusplus.github.io/LWG/issue3096) で報告されていた末尾のスラッシュと `std::filesystem::path::lexically_relative` が混同されることがなくなりました。
- `std::filesystem::create_symlink` にスラッシュを含むパスを拒否する `CreateSymbolicLinkW` の回避策が考案されました。
- Windows 10 LTSB 1609 に存在するが、実際にはファイルを削除できない POSIX 削除モード `delete` 関数の回避策が考案されました。
- `std::boyer_moore_searcher` と `std::boyer_moore_horspool_searcher` のコピー コンストラクターとコピー代入演算子で実際にコピーできるようになりました。

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Windows 8 以降の並列アルゴリズム

並列アルゴリズム ライブラリでは、Windows 7 以前のフェイク バージョンを常時使用せず、Windows 8 以降の実際の `WaitOnAddress` ファミリが正しく使用されるようになりました。

### <a name="stdsystemcategorymessage-whitespace"></a>std::system_category::message() のスペース

`std::system_category::message()` では、返されたメッセージから末尾のスペースが削除されるようになりました。

### <a name="stdlinearcongruentialengine-divide-by-zero"></a>std::linear_congruential_engine のゼロ除算

`std::linear_congruential_engine` のゼロ除算を誘発していたいくつかの条件が修正されました。

### <a name="fixes-for-iterator-unwrapping"></a>反復子ラッピング解除の修正

(https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/ で説明されているように) Visual Studio 2017 15.8 におけるプログラマ/ユーザー統合を目的として最初に公開された反復子ラッピング解除機構で、標準ライブラリ反復子から派生する反復子のラッピングが解除されなくなりました。 たとえば、`std::vector<int>::iterator` から派生し、動作をカスタマイズしようとするユーザーには、標準ライブラリ アルゴリズムを呼び出すとき、ポインターの動作ではなく、カスタマイズされた動作が与えられるようになりました。
順序付けられていないコンテナー予約関数は、[LWG 2156](https://cplusplus.github.io/LWG/issue2156) に説明があるように、N 要素に予約されるようになりました。

### <a name="time-handling"></a>時間の処理

- 以前は、`condition_variable::wait_for(seconds::max())` など、同時実行ライブラリに渡されていた一部の時間値がオーバーフローしていました。 このようなオーバーフローが解消され、うわべではランダムの 29 日周期で動作が変わりました (基礎となる Win32 API で受け取られる uint32_t ミリ秒がオーバーフローしたとき)。

- <ctime> ヘッダーでは、グローバル名前空間で宣言できることに加え、名前空間 std で timespec と timespec_get を正しく宣言できるようになりました。

### <a name="various-fixes-for-containers"></a>コンテナーのさまざまな修正

- Standard Library のさまざまな内部コンテナー関数がプライベートになり、IntelliSense が使いやすくなりました。 MSVC の今後のリリースでは、メンバーをプライベートにする修正が追加される予定です。

- `list`、`map`、`unordered_map` のようなノードベース コンテナーが破損する、例外の安全性における正確性の問題が解消されました。 `propagate_on_container_copy_assignment` または `propagate_on_container_move_assignment` の再代入演算の間、古いアロケーターを持つコンテナーのセンチネル ノードを解放し、古いアロケーターで POCCA/POCMA 代入を行い、新しいアロケーターからセンチネル ノードの取得を試みました。 この代入に失敗した場合、コンテナーは破損し、さらには破棄できなくなります。センチネル ノードを持つと、データ構造を変えられなくなるためです。 この問題は、既存のセンチネル ノードを破棄する前に、ソース コンテナーのアロケーターから新しいセンチネル ノードを割り当てるように修正されました。

- `is_always_equal` が宣言されたアロケーターの場合でも、常に `propagate_on_container_copy_assignment`、`propagate_on_container_move_assignment`、`propagate_on_container_swap` に基づいてアロケーターをコピー、移動、スワップするようにコンテナーが修正されました。

- [P0083 "Splicing Maps And Sets"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) に基づき右辺値コンテナーを受け取るコンテナーの結合および抽出メンバー関数向けのオーバーロードが追加されました。

### <a name="stdbasicistreamread-processing-of-rn--n"></a>\r\n => \n の std::basic_istream::read 処理

\r\n => \n 処理の一環として、与えられたバッファーの一部を一時的に書き込まないよう、`std::basic_istream::read` が修正されました。 Visual Studio 2017 15.8 において 4K を超える読み込みで得られるパフォーマンス上のいくつかの長所を放棄することになりますが、文字ごとに 3 つの仮想呼び出しを回避することから得られる効率性の改善が残されています。

### <a name="stdbitset-constructor"></a>std::bitset コンストラクター

`std::bitset` のコンストラクターで、大きなビットセットの 1 と 0 が逆の順序で読み取られることがなくなりました。

### <a name="stdpairoperator-regression"></a>std::pair::operator= 回帰

[LWG 2729 "Missing SFINAE on std::pair::operator=";](https://cplusplus.github.io/LWG/issue2729) の導入時に見つかった `std::pair` の代入演算子の回帰が修正されました。 再び `std::pair` に変換できる型を正しく受け取るようになりました。

### <a name="non-deduced-contexts-for-addconstt"></a>add_const_t の非推定コンテキスト

`add_const_t` や関連関数が非推定コンテキストであることが求められる、型の特徴の軽微なバグが修正されました。 言い換えると、`add_const_t` は `const T` ではなく、`typename add_const<T>::type` のエイリアスにする必要があります。

## <a name="see-also"></a>関連項目

[Visual Studio 2019 の新機能](../what-s-new-for-visual-cpp-in-visual-studio.md)