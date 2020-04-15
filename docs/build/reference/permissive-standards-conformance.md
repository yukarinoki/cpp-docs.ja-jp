---
title: /permissive- (標準への準拠)
description: Microsoft C++ /寛容- (標準準拠) コンパイラ オプションのリファレンス ガイド。
ms.date: 04/14/2020
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 695f84e64f07128ac7744dc99e736f2a71ab3e79
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337403"
---
# <a name="permissive--standards-conformance"></a>/permissive- (標準への準拠)

コンパイラに標準準拠モードを指定します。 このオプションを使用すると、コード内の準拠の問題を特定して修正し、より正確で移植性を高めます。

## <a name="syntax"></a>構文

> **/寛容-**

## <a name="remarks"></a>解説

このオプションは、Visual Studio 2017 以降でサポートされています。

**/permissive コンパイラ**オプションを使用して、標準に準拠するコンパイラの動作を指定できます。 このオプションは、寛容な動作を無効にし[、/Zc](zc-conformance.md)コンパイラ オプションを厳密に準拠させる設定を行います。 IDE では、このオプションを使用すると、IntelliSense エンジンが非準拠コードに下線を引くようになります。

既定では **、/permissive-** オプションは、Visual Studio 2017 バージョン 15.5 以降で作成された新しいプロジェクトで設定されます。 以前のバージョンでは既定では設定されていません。 このオプションを設定すると、C++11 より前のコードに一般的なバグを含め、標準以外の言語構成要素がコードで検出されると、コンパイラは診断エラーまたは警告を生成します。

**/permissive-** オプションは、ソフトウェア開発キット (SDK) や Windows ドライバー キット (WDK) など、Windows の秋の作成者 SDK (10.0.16299.0) で始まる、最新の Windows キットのヘッダー ファイルのほとんどすべてと互換性があります。 古いバージョンの SDK は、さまざまなソース コード準拠の理由から **/permissive-** の下でコンパイルできない場合があります。 コンパイラと SDK は異なるリリース タイムラインに用意されているため、残りの問題がいくつかあります。 ヘッダー ファイルの問題については、以下の[Windows ヘッダーの問題](#windows-header-issues)を参照してください。

**/permissive-** オプションは[、/Zc:referenceBinding、/Zc:strictStrings](zc-referencebinding-enforce-reference-binding-rules.md)、および[/Zc:rvalueCast](zc-rvaluecast-enforce-type-conversion-rules.md)オプションを準拠の動作に設定します。 [/Zc:strictStrings](zc-strictstrings-disable-string-literal-type-conversion.md) これらのオプションは、既定では非準拠の動作になります。 コマンド ラインで **/permissive-** の後に特定の **/Zc**オプションを渡して、この動作をオーバーライドできます。

Visual Studio 2017 バージョン 15.3 以降のバージョンのコンパイラでは **、/permissive オプション**は[/Zc:ternary](zc-ternary.md)オプションを設定します。 コンパイラは、2 フェーズ名の検索に関する要件の多くを実装します。 **/permissive-** オプションが設定されている場合、コンパイラは関数とクラス テンプレートの定義を解析し、テンプレートで使用される依存名と非依存名を識別します。 このリリースでは、名前依存分析のみが実行されます。

標準が実装に任す環境固有の拡張機能および言語領域は **、/permissive-** の影響を受けません。 たとえば、Microsoft 固有`__declspec`の呼び出し規約と構造化例外処理キーワード、およびコンパイラ固有のプラグマ ディレクティブまたは属性は、コンパイラによって **/permissive-** モードではフラグが付けされません。

**/permissive-** オプションは、現在のコンパイラ バージョンでの準拠サポートを使用して、どの言語構成要素が不適合かを判断します。 このオプションでは、コードが C++ 標準の特定のバージョンに準拠しているかどうかは判断されません。 実装されたすべてのコンパイラ サポートを最新のドラフト標準に対して有効にするには[、/std:latest](std-specify-language-standard-version.md)オプションを使用します。 コンパイラのサポートを現在実装されている C++17 標準に制限するには[、/std:c++17](std-specify-language-standard-version.md)オプションを使用します。 コンパイラのサポートを C++14 標準に近づけるように制限するには[、/std:c++14](std-specify-language-standard-version.md)オプションを使用します。

すべての C++11、C++14、または C++17 標準準拠コードが、すべてのバージョンの Visual Studio 2017 で MSVC コンパイラでサポートされているわけではありません。 Visual Studio のバージョンによっては **、/permissive-** オプションは、2 フェーズ名検索のいくつかの側面に関する問題を検出できないことがあり、非 const 参照を一時的な参照にバインドし、コピー初期化を直接 init として扱い、初期化時に複数のユーザー定義変換を行ったり、論理演算子の代替トークンやその他の不適合領域をサポートしていない場合があります。 Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。 **/permissive**を最大限に活用するには、Visual Studio を最新バージョンに更新します。

### <a name="how-to-fix-your-code"></a>コードを修正する方法

ここでは **、/permissive-** を使用するときに不適合として検出されるコードの例と、問題を解決するための推奨される方法を示します。

#### <a name="use-default-as-an-identifier-in-native-code"></a>ネイティブ コードで識別子として default を使用する

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="look-up-members-in-dependent-base"></a>依存ベースのメンバを検索する

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

#### <a name="use-of-qualified-names-in-member-declarations"></a>メンバー宣言で修飾名を使用する

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>メンバ初期化子で複数の共用体メンバーを初期化する

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

#### <a name="hidden-friend-name-lookup-rules"></a>非表示のフレンド名の検索ルール

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
    f(p); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>配列の範囲内での範囲指定列挙型の使用

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>ネイティブ コードでの各使用

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

Visual Studio 2017 バージョン 15.3 より前のバージョンのコンパイラでは、コンパイラは、標準によってあいまいと見な`?:`される条件演算子 (または三項演算子) への引数を受け入れました。 **/permissive-** モードでは、以前のバージョンで診断なしでコンパイルされた場合に、コンパイラは 1 つ以上の診断を発行するようになりました。

この変更によって発生する可能性のある一般的なエラーは次のとおりです。

- エラー C2593: '演算子?' あいまいです

- エラー C2679: バイナリ '?': 型 'B' の右オペランドを取る演算子が見つかりません (または許容される変換がありません)

- エラー C2678: バイナリ '?': 型 'A' の左オペランドを取る演算子が見つかりません (または許容される変換がありません)

- エラー C2446: ':': ' B から 'A' への変換はありません

この問題を引き起こす可能性がある一般的なコード パターンは、一部のクラス C が別の型 T の非明示的なコンストラクターと、型 T に対する非明示的な変換演算子の両方を提供する場合です。この場合、2 番目の引数から 3 番目の引数の型への変換と、第 3 引数から 2 番目の引数の型への変換の両方が有効な変換になります。 どちらも有効なので、標準に従ってあいまいです。

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

T が null で終わる文字列型`const char *``const char16_t *`(、、など) の 1 つを表し、実際の`?:`引数が対応する型の文字列リテラルである場合、この共通パターンには重要な例外があります。 C++17 は C++14 からセマンティクスを変更しました。 結果として、例 2 のコードは **/std:c++14**で受け入れられ **、/Zc:ternary**または **/permissive-** が使用されている場合は **/std:c++17**の下で拒否されます。

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

エラーが表示される別のケースとして、 type の引数が`void`1 つある条件演算子が挙げられます。 このケースは、ASSERT のようなマクロで一般的な場合があります。

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

また、テンプレートメタプログラミングでエラーが発生する場合があり、条件演算子の結果の種類は **/Zc:ternary**および **/permissive-** で変更される可能性があります。 この問題を解決する方法の 1 つは、結果の型に対して[std::remove_reference](../../standard-library/remove-reference-class.md)を使用することです。

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>2 フェーズ名の検索

**/permissive-** オプションが設定されている場合、コンパイラは関数とクラス テンプレートの定義を解析し、テンプレートで使用される依存名と非依存名を 2 フェーズの名前の検索に必要な場合に識別します。 Visual Studio 2017 バージョン 15.3 では、名前の依存関係の分析が実行されます。 特に、テンプレート定義のコンテキストで宣言されていない非依存名は、ISO C++ 標準で要求される診断メッセージを発生させます。 Visual Studio 2017 バージョン 15.7 では、定義コンテキストで引数依存の検索を必要とする非依存名のバインドも行われます。

```cpp
// dependent base
struct B {
    void g() {}
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

2 フェーズ ルックアップの従来の動作が必要で、それ以外の場合は **/permissive-** 動作を実行する場合は **、/Zc:twoPhase-** オプションを追加します。

### <a name="windows-header-issues"></a>ウィンドウヘッダーの問題

**/permissive-** オプションは、Windows の秋の作成者更新 SDK (10.0.16299.0) または Windows ドライバー キット (WDK) バージョン 1709 より前のバージョンの Windows キットでは厳しすぎます。 Windows またはデバイス ドライバ コードで **/permissive-** を使用するために、最新バージョンの Windows キットに更新することをお勧めします。

Windows 2018 年 4 月更新 SDK (10.0.17134.0)、Windows 秋の作成者更新 SDK (10.0.16299.0)、または Windows ドライバー キット (WDK) 1709 の特定のヘッダー ファイルにまだ**問題**があります。 これらの問題を回避するには、これらのヘッダーの使用を必要とするソース コード ファイルのみに制限し、特定のソース コード ファイルをコンパイルするときに **/permissive オプション**を削除することをお勧めします。

Windows 2018 年 4 月の更新 SDK (10.0.17134.0) でリリースされたこれらの WinRT WRL ヘッダーは **、/permissive-** でクリーンではありません。 これらの問題を回避するには **、/permissive-** を使用しないか **、/Permissive を**使用 **/Zc:twoPhase-** してください。

- ウィント/wrl/async.hの問題

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- ウィント/wrl/implements.h の問題

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Windows 2018 年 4 月更新 SDK (10.0.17134.0) でリリースされたこれらのユーザー モード ヘッダーは **、/permissive-** でクリーンではありません。 これらの問題を回避するには、これらのヘッダーを使用するときに **/permissive-** を使用しないでください。

- um/Tune.h の問題

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- um/spddkhlp.h の問題

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- um/refptrco.h の問題

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

これらの問題は、Windows 秋の作成者更新 SDK (10.0.16299.0) のユーザー モード ヘッダーに固有のものです。

- um/Query.h の問題

   **/permissive-** コンパイラ スイッチを使用する場合`tagRESTRICTION`、構造体は case(RTOr) メンバー 'or' のためにコンパイルされません。

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

   この問題に対処するには **、/permissive-** オプションを指定せずに Query.h を含むファイルをコンパイルします。

- um/cellularapi_oem.h の問題

   **/permissive-** コンパイラ スイッチを使用すると、前方宣言`enum UICCDATASTOREACCESSMODE`によって警告が発生します。

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   スコープなし列挙型の前方宣言は、マイクロソフトの拡張機能です。 この問題に対処するには **、/permissive-** オプションを指定せずに cellularapi_oem.h を含むファイルをコンパイルするか[、/wd](compiler-option-warning-level.md)オプションを使用して警告 C4471 を消音します。

- um/omscript.h の問題

   C++03 では、文字列リテラルから BSTR への変換 (型定義から 'wchar_t *') は非推奨ですが、許可されています。 C++11 では、変換は許可されなくなります。

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   この問題に対処するには **、/permissive-** オプションを指定せずに omscript.h を含むファイルをコンパイルするか、代わりに **/Zc:strictStrings- を**使用します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

Visual Studio 2017 バージョン 15.5 以降では、次の手順を使用します。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。

1. [**構成プロパティ** > **C/C++** > 言語] プロパティ ページ**を**選択します。

1. **[準拠モード**] プロパティ値を **[はい ](/許容範囲)** に変更します。 **[OK]** または **[適用]** を選択して変更を保存します。

Visual Studio 2017 バージョン 15.5 より前のバージョンでは、次の手順を使用します。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。

1. **[構成プロパティ** > **C/C++** > **コマンド ライン**] プロパティ ページを選択します。

1. [追加オプション] ボックス**に /permissive-** コンパイラ**オプション**を入力します。 **[OK]** または **[適用]** を選択して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)\
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
