---
title: -寛容 - (標準準拠) |Microsoft ドキュメント
ms.date: 11/11/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
dev_langs:
- C++
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90cfdcf20cf74244afe026a392759ac59616bbdf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379316"
---
# <a name="permissive--standards-conformance"></a>寛容/-(標準準拠)

コンパイラに標準準拠モードを指定します。 特定し、コードをより正確と移植性を向上させるで準拠の問題を解決するためには、このオプションを使用します。

## <a name="syntax"></a>構文

> **/permissive-**

## <a name="remarks"></a>コメント

使用することができます、**寛容/-** コンパイラ オプションをコンパイラの標準準拠の動作を指定します。 このオプションは、制限の緩やかな動作を無効にし、設定、 [/Zc](../../build/reference/zc-conformance.md)厳密に準拠するためのコンパイラ オプション。 IDE では、このオプションは、IntelliSense エンジン下線非準拠コードも、します。

既定では、**寛容/-** オプションは Visual Studio 2017 バージョン 15.5 およびそれ以降のバージョンで作成された新しいプロジェクトで設定します。 以前のバージョンで既定で設定されていません。 オプションが設定されている、コンパイラ診断エラーが発生、コードで標準以外の言語構成要素と、警告が検出された場合は、前にいくつかの一般的なバグを含めて、c++ 11 コード。

**寛容/-** オプションは、ほぼすべての Windows Driver Kit (WDK)、Windows 秋作成者 SDK (10.0.16299.0) 以降で、ソフトウェア開発キット (SDK) など、最新の Windows Kits からヘッダー ファイルとの互換性。 SDK の古いバージョンは、コンパイルに失敗する可能性があります**寛容/-** コードへの準拠の理由によりさまざまなソース。 コンパイラと別のリリースのタイムライン上の Sdk 出荷いくつか残っている問題があるためです。 特定のヘッダー ファイル問題については、次を参照してください。 [Windows ヘッダー問題](#windows-header-issues)以下です。

**寛容/-** オプション セットに、 [/Zc:strictStrings](../../build/reference/zc-conformance.md)と[/Zc:rvalueCast](../../build/reference/zc-conformance.md)オプション準拠の動作をします。 既定値は、非準拠の動作です。 特定に渡すことができます **/Zc**後オプション**寛容/-** この動作をオーバーライドするコマンド ラインでします。

Visual Studio 2017 15.3 のバージョンのコンパイラ以降のバージョンで、**寛容/-** オプション セットに、 [/Zc:ternary](../../build/reference/zc-ternary.md)オプション。 コンパイラでは、2 段階名前検索の要件の詳細も実装します。 ときに、**寛容/-** オプションの設定と、コンパイラがテンプレートで使用される依存と非依存の名前を識別する、関数とクラス テンプレート定義を解析します。 このリリースでは、名前の依存関係分析だけが実行されます。

環境に固有の拡張機能と実装では、最大、標準のまま言語領域受けません**寛容/-** です。 たとえば、Microsoft 固有`__declspec`、呼び出し規約と構造化例外処理キーワード、およびコンパイラ固有プラグマ ディレクティブまたは属性に、コンパイラによってフラグがない**寛容/-** モード。

**寛容/-** オプションでは、現在のコンパイラ バージョンで準拠サポートを使用する言語構成要素が非準拠かを判断します。 オプションでは、コードを特定のバージョンの C++ 標準に準拠しているかどうかは判断されません。 最新のドラフト標準のすべての実装済みのコンパイラ サポートを有効にするを使用して、 [/std:latest](../../build/reference/std-specify-language-standard-version.md)オプション。 使用して、現在実装されている c++ 17 規格にコンパイラのサポートを制限、 [/std:c + + 17](../../build/reference/std-specify-language-standard-version.md)オプション。 C++ 14 標準をより厳密に一致するようにコンパイラのサポートを制限するには、 [/std:c + + 14](../../build/reference/std-specify-language-standard-version.md)オプションは、既定値です。

すべての c++ 11、c++ 14、または c++ 17 標準に準拠できませんコードは、Visual Studio 2017 で Visual C コンパイラでサポートされます。 **寛容/-** オプションは、名前の 2 フェーズ参照の一部の側面に関連、一時的に非定数の参照をバインド、コピー初期化を直接 init として扱うでの複数のユーザー定義の変換を許可する問題を検出いない可能性があります初期化、または論理演算子、およびその他の適合性のサポートされていない領域の代替トークンです。 Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="how-to-fix-your-code"></a>コードを修正する方法

ここでは、非準拠を使用するときとして検出されるコードの例をいくつか**寛容/-**、と共に、問題を修正する方法をお勧めします。

#### <a name="use-default-as-an-identifier-in-native-code"></a>ネイティブ コードで識別子として既定値の使用

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="lookup-members-in-dependent-base"></a>依存する基本の参照メンバー

```cpp
template <typename T>
struct B {
    void f();
};

template <typename T>
struct D : public B<T> // B is a dependent base because its type
                       // depends on the type of T.
{
    // One possible fix is to uncomment the following line.
    // If this is a type, don't forget the 'typename' keyword.
    // using B<T>::f;

    void g() {
        f(); // error C3861: 'f': identifier not found
             // Another fix is to change it to 'this->f();'
    }
};

void h() {
    D<int> d;
    d.g();
}
```

#### <a name="use-of-qualified-names-in-member-declarations"></a>メンバーの宣言内の修飾名の使用

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>メンバーの初期化子内の複数の共用体のメンバーを初期化します。

```cpp
union U
{
    U()
        : i(1), j(1) // error C3442: Initializing multiple members of
                     // union: 'U::i' and 'U::j'.
                     // Remove all but one of the initializations to fix.
    {}
    int i;
    int j;
};
```

#### <a name="hidden-friend-name-lookup-rules"></a>フレンド名のルックアップ規則を非表示

```cpp
// Example 1
struct S {
    friend void f(S *);
};
// Uncomment this declaration to make the hidden friend visible:
// void f(S *); // This declaration makes the hidden friend visible

using type = void (*)(S *);
type p = &f; // error C2065: 'f': undeclared identifier.
```

```cpp
// Example 2
struct S {
    friend void f(S *);
};
void g() {
    // Using nullptr instead of S prevents argument dependent lookup in S
    f(nullptr); // error C3861: 'f': identifier not found

    S *p = nullptr;
    f(S); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>配列の範囲でスコープを持つ列挙型を使用します。

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>ネイティブ コードでは、それぞれの使用

```cpp
void func() {
    int array[] = {1, 2, 30, 40};
    for each (int i in array) // error C4496: nonstandard extension
                              // 'for each' used: replace with
                              // ranged-for statement:
                              // for (int i: array)
    {
        // ...
    }
}
```

#### <a name="use-of-atl-attributes"></a>ATL 属性の使用

```cpp
// Example 1
[uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
class A {};
```

```cpp
// Fix for example 1
class __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) B {};
```

```cpp
// Example 2
[emitidl];
[module(name="Foo")];

[object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
__interface ICustom {
    HRESULT Custom([in] longl, [out, retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out, retval] long*pLong);
};

[coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
class CFoo : public ICustom
{};
```

```cpp
// Fix for example 2
// First, create the *.idl file. The vc140.idl generated file can be 
// used to automatically obtain a *.idl file for the interfaces with 
// annotation. Second, add a midl step to your build system to make 
// sure that the C++ interface definitions are outputted. 
// Last, adjust your existing code to use ATL directly as shown in 
// the atl implementation section.

-- IDL  FILE--
import "docobj.idl";

[object, local, uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)]
interface ICustom : IUnknown {
    HRESULT Custom([in] longl, [out,retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out,retval] long*pLong);
};

[ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]
library Foo {
    importlib("stdole2.tlb");
    importlib("olepro32.dll");

    [version(1.0), appobject, uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)]
    coclass CFoo { interface ICustom; };
}

-- ATL IMPLEMENTATION--
#include <idl.header.h>
#include <atlbase.h>

class ATL_NO_VTABLE CFooImpl : public ICustom,
    public ATL::CComObjectRootEx<CComMultiThreadModel>
{
    public:BEGIN_COM_MAP(CFooImpl)
    COM_INTERFACE_ENTRY(ICustom)
    END_COM_MAP()
};
```

#### <a name="ambiguous-conditional-operator-arguments"></a>あいまいな条件演算子の引数

Visual Studio 2017 バージョン 15.3 する前に、コンパイラのバージョンは、コンパイラは条件演算子 (または三項演算子) への引数を受け入れられます`?:`をでとみなされるあいまいな標準です。 **寛容/-** モードでは、コンパイラはこれで以前のバージョンでの診断を使用せずにコンパイルされるケースで 1 つまたは複数の診断発行します。

この変更につながる可能性のある一般的なエラーは次のとおりです。

- エラー C2593: 'operator'? あいまいです。

- エラー C2679: バイナリ '?': 'B' 型の右側のオペランドを扱う演算子が見つかりません (または許容可能な変換はありません)

- エラー C2678: バイナリ '?': タイプ 'A' の左側のオペランドを扱う演算子が見つかりません (または許容可能な変換はありません)

- エラー C2446: ':': 'B' から 'A' への変換はありません

この問題を引き起こす可能性のある一般的なコード パターンは、いくつかのクラス C 型 T に別の型 T から非明示的コンス トラクターと非明示的な変換演算子の両方を提供する場合ここでは、3 番目の型に 2 番目の引数の変換と 3 番目の引数の 2 番目の型への変換の両方は有効な変換では、これは、標準に従ってあいまいな。

```cpp
// Example 1: class that provides conversion to and initialization from some type T
struct A
{
    A(int);
    operator int() const;
};

extern bool cond;

A a(42);
// Accepted when /Zc:ternary or /permissive- is not used:
auto x = cond ? 7 : a; // A: permissive behavior prefers A(7) over (int)a
// Accepted always:
auto y = cond ? 7 : int(a);
auto z = cond ? A(7) : a;
```

T は、null で終わる文字列型の 1 つを表すときにこの一般的なパターンの重要な例外がある (たとえば、 `const char *`、`const char16_t *`など) と実際の引数に`?:`文字列は、対応する型のリテラルです。 C++ 17 には、c++ 14 のセマンティクスが変更されました。 例 2 のコードは受け入れられます結果として、 **/std:c + + 14** 、および 拒否された **/std:c + + 17**とき **/Zc:ternary**または **/permissive-** を使用します。

```cpp
// Example 2: exception from the above
struct MyString
{
    MyString(const char* s = "") noexcept;  // from char*
    operator const char* () const noexcept; //   to char*
};

extern bool cond;

MyString s; 
// Using /std:c++14, /permissive- or /Zc:ternary behavior
// is to prefer MyString("A") over (const char*)s
// but under /std:c++17 this line causes error C2445:
auto x = cond ? "A" : s;
// You can use a static_cast to resolve the ambiguity:
auto y = cond ? "A" : static_cast<const char*>(s);
```

型の引数の 1 つの条件演算子では、別のケースでエラーが発生する可能性があります`void`です。 この場合は、アサートに似たマクロで一般的な可能性があります。

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

条件演算子の結果の型を下にある変更可能性がありますテンプレート メタプログラミングでエラーが発生する可能性がありますも **/Zc:ternary**と**寛容/-** です。 この問題を使用して解決するのには 1 つの方法[std::remove_reference](../../standard-library/remove-reference-class.md)結果の型にします。

```cpp
// Example 4: different result types 
extern bool cond;
extern int count;
char  a = 'A'; 
const char  b = 'B'; 
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary 
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary 
```

#### <a name="two-phase-name-look-up-partial"></a>2 段階名前検索 (部分的)

ときに、**寛容/-** Visual Studio 2017 15.3 のバージョンでは、オプションを設定してください、コンパイラ解析関数やクラスのテンプレート定義、必要に応じてテンプレートで 2 フェーズ名に使用される依存と非依存の名前を識別する。検索します。 このリリースでは、名前の依存関係分析だけが実行されます。 具体的には、テンプレート定義のコンテキストで宣言されていない非依存名では、ISO C 標準で必要に応じて、診断メッセージが発生します。 ただし、引数依存ファイルの場所を定義コンテキストが完了していないを必要とする非依存名のバインドです。

```cpp
// dependent base
struct B {
    void g();
};

template<typename T>
struct D : T {
    void f() {
        // The call to g was incorrectly allowed in VS2017:
        g();  // Now under /permissive-: C3861
        // Possible fixes:
        // this->g();
        // T::g();
    }
};

int main()
{
    D<B> d;
    d.f();
}
```

### <a name="windows-header-issues"></a>Windows ヘッダーの問題

**寛容/-** オプションは Windows 秋作成者更新 SDK (10.0.16299.0) する前に Windows キットのバージョンの Windows Driver Kit (WDK) バージョン 1709 厳しすぎます。 使用するために Windows Kits の最新バージョンに更新することをお勧め**寛容/-** に Windows またはデバイスのドライバー コード。

Windows 秋作成者更新 SDK (10.0.16299.0)、または Windows Driver Kit (WDK) 1709、内の特定のヘッダー ファイルには、使用と互換性がないように問題も含まれている**寛容/-** です。 これらの問題を回避することをお勧めのみこれらのソース コード ファイルをそれらを必要とし、削除するこれらのヘッダーの使用を制限する、**寛容/-** それらの特定のソース コード ファイルをコンパイルするオプションを選択します。 次の問題は、Windows 秋作成者更新 SDK (10.0.16299.0) に固有です。

#### <a name="issue-in-umqueryh"></a>Um\Query.h での問題します。

使用する場合、**寛容/-** コンパイラ スイッチ、 `tagRESTRICTION` case(RTOr) メンバーのための構造はコンパイルされません 'または' です。

```cpp
struct tagRESTRICTION
    {
    ULONG rt;
    ULONG weight;
    /* [switch_is][switch_type] */ union _URes
        {
        /* [case()] */ NODERESTRICTION ar;
        /* [case()] */ NODERESTRICTION or;  // error C2059: syntax error: '||'
        /* [case()] */ NODERESTRICTION pxr;
        /* [case()] */ VECTORRESTRICTION vr;
        /* [case()] */ NOTRESTRICTION nr;
        /* [case()] */ CONTENTRESTRICTION cr;
        /* [case()] */ NATLANGUAGERESTRICTION nlr;
        /* [case()] */ PROPERTYRESTRICTION pr;
        /* [default] */  /* Empty union arm */
        } res;
    };
```

この問題に対処することがなく Query.h を含むファイルをコンパイル、**寛容/-** オプション。

#### <a name="issue-in-umcellularapioemh"></a>Um\cellularapi_oem.h での問題します。

使用する場合、**寛容/-** コンパイラ スイッチの事前宣言`enum UICCDATASTOREACCESSMODE`警告が発生します。

```cpp
typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
```

対象範囲外の列挙の事前宣言は、Microsoft 拡張です。 この問題に対処することがなく cellularapi_oem.h を含むファイルをコンパイル、**寛容/-** オプション、またはを使用して、 [/wd](../../build/reference/compiler-option-warning-level.md)警告 C4471 をミュートするにはオプションです。

#### <a name="issue-in-umomscripth"></a>Um\omscript.h での問題します。

C++ 03、文字列リテラルから BSTR に変換 (typedef でにある ' wchar_t *') は推奨されなくなりましたが、許可されています。 C++ 11 では、変換は許可されません。

```cpp
virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
    /* [in] */ __RPC__in BSTR propname,
    /* [in] */ __RPC__in BSTR expression,
    /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
```

この問題に対処することがなく omscript.h を含むファイルをコンパイル、**寛容/-** オプション、または使用 **/Zc:strictStrings-** 代わりにします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

Visual Studio 2017 バージョン 15.5 およびそれ以降のバージョンでは、この手順を使用します。

1. プロジェクトの開く**プロパティ ページ** ダイアログ ボックス。

1. **構成プロパティ**、展開、 **C/C++** フォルダーを選択し、**言語**プロパティ ページ。

1. 変更、**準拠モード**プロパティの値を**はい (制限の緩やかな/-)** です。 選択**OK**または**適用**して変更を保存します。

Visual Studio 2017 バージョン 15.5 前に、のバージョンでは、この手順を使用します。

1. プロジェクトの開く**プロパティ ページ** ダイアログ ボックス。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 入力、**寛容/-** コンパイラ オプション、**追加オプション**ボックス。 選択**OK**または**適用**して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)   
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
