---
title: /permissive -(標準への準拠)
ms.date: 06/21/2018
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 85439598ae4c3e0f9ef923f21e701e0399aefa70
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619298"
---
# <a name="permissive--standards-conformance"></a>/permissive -(標準への準拠)

コンパイラに標準準拠のモードを指定します。 特定しより正確と移植性を向上させる、コードで準拠の問題を修正するためには、このオプションを使用します。

## <a name="syntax"></a>構文

> **/permissive-**

## <a name="remarks"></a>Remarks

Visual Studio 2017 以降、このオプションはサポートされています。

使用することができます、 **/permissive -** コンパイラ オプションは、標準準拠コンパイラの動作を指定します。 このオプションは、制限の緩やかな動作を無効にし、設定、 [/Zc](../../build/reference/zc-conformance.md)厳密に準拠コンパイラ オプション。 IDE では、このオプションも IntelliSense エンジン下線非準拠コードになります。

既定で、 **/permissive -** Visual Studio 2017 バージョン 15.5 以降で作成された新しいプロジェクトのオプションを設定します。 既定では以前のバージョンに設定されていません。 前にいくつかの一般的なバグを含む、オプションの設定、コンパイラ診断のエラーが発生またはコードの非標準の言語で構築したときに警告が検出された、ときに、c++ 11 コード。

**/Permissive -** オプションは、ほぼすべてのソフトウェア開発キット (SDK) や Windows Driver Kit (WDK)、Windows Fall Creators SDK (10.0.16299.0) 以降など、最新の Windows キットからヘッダー ファイルとの互換性。 以前のバージョンの SDK をコンパイルできない可能性があります **/permissive -** 各種のソース コードへの準拠の理由。 コンパイラと別のリリースのタイムライン上の Sdk の出荷の残りの問題があるためです。 特定のヘッダー ファイルの問題を参照してください。 [Windows ヘッダー問題](#windows-header-issues)以下。

**/Permissive -** オプション セット、 [/Zc:strictStrings](../../build/reference/zc-conformance.md)と[/Zc:rvalueCast](../../build/reference/zc-conformance.md)準拠した動作するためのオプション。 非準拠の動作を既定使用されます。 特定渡すことができます **/Zc**後オプション **/permissive -** でこの動作をオーバーライドするためのコマンドライン。

Visual Studio 2017 バージョン 15.3 では、コンパイラの最初のバージョンでは、 **/permissive -** オプション セット、 [/Zc:ternary](../../build/reference/zc-ternary.md)オプション。 コンパイラでは、2 フェーズの名前検索の要件の詳細も実装します。 ときに、 **/permissive -** オプションが設定されている、コンパイラは、テンプレートで使用される依存と非依存の名前を識別する、関数とクラス テンプレート定義を解析します。 このリリースでは、名前の依存関係の分析だけが実行されます。

環境固有の拡張機能と、標準の実装に依存しますまま言語領域は受けません **/permissive -** します。 たとえば、Microsoft 固有`__declspec`、呼び出し規約、および構造化例外処理キーワード、および特定のコンパイラのプラグマ ディレクティブまたは属性はフラグが設定されないでコンパイラ **/permissive -** モード。

**/Permissive -** オプション サポートを使用して、準拠コンパイラの現在のバージョンでどの言語コンストラクトが非準拠を確認します。 オプションは、コードが特定のバージョンの C++ 標準に準拠しているかどうかを決定できません。 最新のドラフト標準のすべての実装済みのコンパイラ サポートを有効にするには使用、 [/std:latest](../../build/reference/std-specify-language-standard-version.md)オプション。 コンパイラのサポートを現在実装されている c++ 17 標準に制限する、 [/std:c + + 17](../../build/reference/std-specify-language-standard-version.md)オプション。 C++ 14 標準をより厳密に一致するように、コンパイラのサポートを制限するには、 [/std:c + + + 14](../../build/reference/std-specify-language-standard-version.md)オプションは、既定値です。

すべての c++ 11、c++ 14、または c++ 17 標準に準拠しないコードが Visual Studio 2017 で Visual C コンパイラによってサポートされています。 Visual Studio のバージョンに応じて、 **/permissive -** オプションは、2 フェーズの名前参照の一部の側面に関する、一時的に非定数の参照をバインド、直接の初期化としてコピー init を扱うこと、許可の問題を検出しない可能性があります複数ユーザー定義の変換では、初期化、または別のトークンの論理演算子は、およびその他の適合性のサポートされていない領域。 Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。 取得を最大限に活用する **/permissive -**、Visual Studio の最新バージョンに更新します。

### <a name="how-to-fix-your-code"></a>コードを修正する方法

いくつかの例として、非準拠を使用するときに検出されたコードの **/permissive -**、と共に、問題を修正する方法をお勧めします。

#### <a name="use-default-as-an-identifier-in-native-code"></a>ネイティブ コードの識別子として既定値の使用

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="lookup-members-in-dependent-base"></a>依存ベース参照メンバー

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

#### <a name="use-of-qualified-names-in-member-declarations"></a>メンバー宣言の修飾名の使用

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>メンバー初期化子内の複数の共用体のメンバーを初期化します。

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

#### <a name="hidden-friend-name-lookup-rules"></a>非表示のフレンド名のルックアップ規則

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

#### <a name="use-for-each-in-native-code"></a>ネイティブ コードでは for each の使用

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

Visual Studio 2017 バージョン 15.3 の前に、コンパイラのバージョンでは、コンパイラは条件演算子 (または三項演算子) の引数を受け入れられる`?:`標準によってあいまいなが検討されます。 **/Permissive -** モードでは、コンパイラはこれで以前のバージョンでの診断を使用せずにコンパイルする場合、1 つまたは複数の診断発行します。

この変更の可能性のある一般的なエラーは次のとおりです。

- エラー C2593: '演算子?' あいまいです。

- エラー C2679: バイナリ '?': 'B' 型の右辺のオペランドを扱う演算子が見つかりません (または、変換はありません)

- エラー C2678: バイナリ '?': 型 'A' の左側のオペランドを扱う演算子が見つかりません (または、変換はありません)

- エラー C2446: ':': 'a' から 'B' 変換なし

この問題を引き起こす可能性のある一般的なコード パターンがいくつかのクラス C 型 T を別の型 T から非明示的コンス トラクターと非明示的変換演算子の両方を提供するときにします。この場合、2 番目の引数の 3 番目の型への変換と 3 番目の引数の 2 番目の型への変換の両方が有効な変換は、標準に従ってあいまいであります。

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

T が null で終わる文字列型のいずれかを表す場合にこの共通パターンに重要な例外がある (たとえば、 `const char *`、`const char16_t *`など) と実際の引数を`?:`文字列は、対応する型のリテラル。 C++ 17 には、c++ 14 のセマンティクスが変更されました。 例 2 のコードが受け入れられるため、 **/std:c + + + 14**および 拒否された **/std:c + + + 17**とき **/Zc:ternary**または **/permissive-** 使用されます。

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

別のケースでエラーが発生する可能性がありますが、型の引数の 1 つの条件演算子`void`します。 この場合は、アサートに似たマクロで一般的な可能性があります。

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

条件演算子の結果の型の下で変更可能性がありますが、メタプログラミング テンプレートでエラーが発生する可能性がありますも **/Zc:ternary**と **/permissive -** します。 使用して、この問題を解決する方法の 1 つ[std::remove_reference](../../standard-library/remove-reference-class.md)結果の型にします。

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>2 フェーズの名前を参照してください。

ときに、 **/permissive -** オプションが設定されている、コンパイラは、2 フェーズの名前検索の必要に応じてテンプレートで使用される依存と非依存の名前を識別する、関数とクラス テンプレート定義を解析します。 Visual Studio 2017 バージョン 15.3 では、名前の依存関係の分析が実行されます。 具体的には、テンプレート定義のコンテキストで宣言されていない非依存名では、ISO C 標準で必要な診断メッセージが発生します。 Visual Studio 2017 バージョン 15.7 では、引数依存の検索の定義のコンテキストを必要とする非依存名のバインドも行われます。

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

2 フェーズ参照は、従来の動作をしますが、それ以外の場合に必要なかどうか **/permissive -** の動作を追加、 **/Zc:twoPhase-** オプション。

### <a name="windows-header-issues"></a>Windows ヘッダーの問題

**/Permissive -** オプションは、Windows Fall Creators Update SDK (10.0.16299.0) する前に Windows キットのバージョン、または Windows Driver Kit (WDK) バージョン 1709 の厳しすぎます。 使用するには、Windows キットの最新バージョンに更新することをお勧めします。 **/permissive -** Windows またはデバイスのドライバー コードにします。

Windows April 2018 Update SDK (10.0.17134.0)、Windows Fall Creators Update SDK (10.0.16299.0) または Windows Driver Kit (WDK) 1709 で特定のヘッダー ファイルの使用を互換性の問題がある **/permissive-**. これらの問題を回避するをお勧めをそれらを必要とし、削除するソース コード ファイルのみにこれらのヘッダーの使用を制限する、 **/permissive -** それらの特定のソース コード ファイルをコンパイルするときのオプションします。

これらの WinRT WRL ヘッダーがリリースされた、Windows April 2018 Update SDK (10.0.17134.0) のないでクリーン **/permissive -** します。 これらの問題を回避するには、いずれかには、使わない **/permissive -**、使用または **/permissive -** で **/Zc:twoPhase-** これらのヘッダーを使用する場合。

- Winrt/wrl/async.h の問題

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- Winrt/wrl/implements.h を発行します。

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

これらのユーザー モード ヘッダーがリリースされた、Windows April 2018 Update SDK (10.0.17134.0) のないでクリーン **/permissive -** します。 これらの問題を回避するを使用しないで **/permissive -** これらのヘッダーを使用する場合。

- Um/Tune.h の問題

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- Um/spddkhlp.h を発行します。

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Um/refptrco.h の問題

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

これらの問題は、Windows Fall Creators Update SDK (10.0.16299.0) のヘッダーをユーザー モードに固有します。

- Um/Query.h を発行します。

   使用する場合、 **/permissive -** コンパイラ スイッチ、 `tagRESTRICTION` case(RTOr) メンバーによりコンパイルしない構造体 'または'。

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

   この問題に対処せず Query.h を含むファイルをコンパイル、 **/permissive -** オプション。

- Um/cellularapi_oem.h を発行します。

   使用する場合、 **/permissive -** コンパイラ スイッチの事前宣言`enum UICCDATASTOREACCESSMODE`警告が発生します。

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   スコープを持たない列挙型の事前宣言は、Microsoft 拡張です。 この問題に対処せず cellularapi_oem.h を含むファイルをコンパイル、 **/permissive -** オプション、またはを使用して、 [/wd](../../build/reference/compiler-option-warning-level.md)警告 C4471 をミュートするオプション。

- Um/omscript.h を発行します。

   C++ 03、文字列リテラルから BSTR への変換で (typedef でにある ' wchar_t *') は非推奨とされますが、許可されています。 C++ 11 では、変換は使用できなくします。

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   この問題に対処せず omscript.h を含むファイルをコンパイル、 **/permissive -** オプション、またはを使用して、 **/Zc:strictStrings-** 代わりにします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

Visual Studio 2017 バージョン 15.5 以降では、この手順を使用します。

1. プロジェクトの開く**プロパティ ページ** ダイアログ ボックス。

1. 選択、**構成プロパティ** > **C/C++** > **言語**プロパティ ページ。

1. 変更、**準拠モード**プロパティの値を **[はい] (/permissive -)** します。 選択**OK**または**適用**変更を保存します。

Visual Studio 2017 バージョン 15.5 より前に、のバージョンでは、この手順を使用します。

1. プロジェクトの開く**プロパティ ページ** ダイアログ ボックス。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 入力、 **/permissive -** コンパイラ オプションで、**追加オプション**ボックス。 選択**OK**または**適用**変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

- [コンパイラ オプション](../../build/reference/compiler-options.md)
- [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
