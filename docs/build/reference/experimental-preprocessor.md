---
title: '/実験的: プリプロセッサ (プリプロセッサ準拠モードの有効化)'
description: '標準準拠プリプロセッサの実験的なコンパイラサポートを有効にするには、/実験的: プリプロセッサコンパイラオプションを使用します。'
ms.date: 09/03/2019
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 3055cfa2a32d1d668dbe0c51b5542415b5bb0af4
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70294439"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>/実験的: プリプロセッサ (プリプロセッサ準拠モードの有効化)

このオプションを使用すると、C99 プリプロセッサ機能を含む、C++ 11 標準に準拠した実験的なトークンベースプリプロセッサが有効になります。

## <a name="syntax"></a>構文

> **/実験的: プリプロセッサ**[ **-** ]

## <a name="remarks"></a>Remarks

試験的準拠プリプロセッサを有効にするには、 **/実験的: プリプロセッサ**コンパイラオプションを使用します。 従来のプリプロセッサを明示的に指定するには、**実験的なプリ**プロセッサオプションを使用します。

**/実験的: プリプロセッサ**オプションは、Visual Studio 2017 バージョン15.8 以降で使用できます。

コンパイル時に使用中のプリプロセッサを検出できます。 従来のプリプロセッサが使用されているかどうかを確認するには、定義済みのマクロ[ \_MSVC\_従来](../../preprocessor/predefined-macros.md)の値を確認します。 このマクロは、呼び出されたプリプロセッサに関係なく、それをサポートするバージョンのコンパイラによって無条件に設定されます。 この値は、従来のプリプロセッサの場合は1です。 準拠している試験的なプリプロセッサの場合は0です。

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

### <a name="behavior-changes-in-the-experimental-preprocessor"></a>実験用プリプロセッサでの動作の変更

次に、プリプロセッサ適合性モードが有効になっている場合によく見られる重大な変更の一部を示します。

#### <a name="macro-comments"></a>マクロコメント

従来のプリプロセッサでは、プリプロセッサトークンではなく文字バッファーを使用します。 これにより、準拠プリプロセッサでは動作しない、次のプリプロセッサコメントトリックなど、いくつかの特殊な動作が可能になります。

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
// To make standards compliant, wrap the following line with the appropriate #if/#endif
DISAPPEARING_TYPE myVal;
```

#### <a name="string-prefixes-lval"></a>文字列プレフィックス (L # val)

従来のプリプロセッサでは、文字列のプレフィックスが文字列化[演算子 (#)](../../preprocessor/stringizing-operator-hash.md)の結果と誤って結合されています。

```cpp
#define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

隣接`L`する文字列リテラルはマクロの展開後に結合されるため、ここではプレフィックスを指定する必要はありません。 旧バージョンとの互換性のある修正は、次のように定義をに変更することです。

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

また、この問題は、次のように、引数をワイド文字列リテラルに "文字列化" する便利なマクロにもあります。

```cpp
// The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str

// Potential fixes:
// Use string concatenation of L"" and #str to add prefix
// This works because adjacent string literals are combined after macro expansion
#define STRING1(str) L""#str

// Add the prefix after #str is stringized with additional macro expansion
#define WIDE(str) L##str
#define STRING2(str) WIDE(#str)

// Use concatenation operator ## to combine the tokens.
// The order of operations for ## and # is unspecified, although all compilers
// checked perform the # operator before ## in this case.
#define STRING3(str) L## #str
```

#### <a name="warning-on-invalid"></a>無効な警告 ##

[トークン連結演算子 (# #)](../../preprocessor/token-pasting-operator-hash-hash.md)で1つの有効なプリプロセストークンが生成されない場合、動作は未定義になります。 従来のプリプロセッサは、トークンの結合に失敗しました。 新しいプリプロセッサは、他のほとんどのコンパイラの動作と一致し、診断を生成します。

```cpp
// The ## is unnecessary and doesn't result in a single preprocessing token.
#define ADD_STD(x) std::##x

// Declare a std::string
ADD_STD(string) s;
```

#### <a name="comma-elision-in-variadic-macros"></a>可変個引数マクロでのコンマ省略

次に例を示します。

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // The following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor replaces the following macro with:
    // func(1, );
    // which results in a syntax error.
    FUNC(1, );
}
```

すべての主要なコンパイラには、この問題に対処するのに役立つプリプロセッサ拡張機能が用意されています。 従来の MSVC プリプロセッサでは、空`__VA_ARGS__`の置換の前に、常にコンマが削除されます。 更新されたプリプロセッサは、他の一般的なクロスプラットフォームコンパイラの動作により厳密に準拠しています。 コンマを削除するには、可変個引数引数が空だけでなく、 `##`演算子でマークされている必要があります。

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
    // The variadic argument is missing in the macro being evoked
    // The comma is removed and replaced with:
    // func(1)
    FUNC2(1);

    // The variadic argument is empty, but not missing. (Notice the
    // comma in the argument list.) The comma isn't removed
    // when the macro is replaced:
    // func(1, )
    FUNC2(1, );
}
```

今後の C + + 2a 標準では、まだ実装されてい`__VA_OPT__`ないを追加することでこの問題に対処しました。

#### <a name="macro-arguments-are-unpacked"></a>マクロの引数は ' アンパック済み ' です

従来のプリプロセッサでは、マクロが引数の1つを別の依存マクロに転送した場合、引数が置換されるときに "アンパック" されることはありません。 通常、この最適化は気付かれませんが、異常な動作につながる可能性があります。

```cpp
// Create a string out of the first argument, and the rest of the arguments.
#define TWO_STRINGS( first, ... ) #first, #__VA_ARGS__
#define A( ... ) TWO_STRINGS(__VA_ARGS__)

const char* c[2] = { A(1, 2) };
// Conformant preprocessor results:
// const char c[2] = { "1", "2" };
// Traditional preprocessor results, all arguments are in the first string:
// const char c[2] = { "1, 2", };
```

展開`A()`すると、従来のプリプロセッサは、に`__VA_ARGS__`パッケージ化されたすべての`TWO_STRINGS`引数をの最初の引数に転送します。 の`TWO_STRINGS`可変個引数引数が空であるため、の`#first`結果はでは`"1, 2"`なく`"1"`になります。 従来のプリプロセッサ拡張での`#__VA_ARGS__`結果について疑問に思うかもしれません。 可変個引数パラメーターが空の場合、空の文字列リテラル "" が生成されます。 別個の問題のため、空の文字列リテラルトークンは生成されませんでした。

#### <a name="rescanning-replacement-list-for-macros"></a>マクロの置換リストの再スキャン

マクロが置換された後、結果として生成されるトークンは、他のマクロ識別子を置き換えるために再スキャンされます。 従来のプリプロセッサで使用されている再スキャンアルゴリズムは、実際のコードに基づくこの例に示すように、準拠していません。

```cpp
#define CAT(a,b) a ## b
#define ECHO(...) __VA_ARGS__

// IMPL1 and IMPL2 are implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)
// MACRO chooses the expansion behavior based on the value passed to macro_switch
#define DO_THING(macro_switch, b) CAT(IMPL, macro_switch) ECHO(( "Hello", b))

DO_THING(1, "World");
// Traditional preprocessor:
// do_thing_one( "Hello", "World");
// Conformant preprocessor:
// IMPL1 ( "Hello","World");
```

この例で何が起こっているかを確認するために、次の`DO_THING`ように拡張を分割します。

`DO_THING(1, "World")` ->
`CAT(IMPL, 1) ECHO(("Hello", "World"))`

次に、CAT が展開されています。

`CAT(IMPL, 1)` -> `IMPL ## 1` -> `IMPL1`

これにより、トークンは次の状態になります。

`IMPL1 ECHO(("Hello", "World"))`

プリプロセッサは関数に似たマクロ識別子`IMPL1`を検索しますが、その後に "(" はありません。そのため、関数のようなマクロの呼び出しとは見なされません。 次のトークンに移動し、呼び出された関数に似た`ECHO`マクロを検索します。

`ECHO(("Hello", "World"))` -> `("Hello", "World")`

`IMPL1`は、拡張のためにもう一度考慮されることはないため、展開の完全な結果は次のようになります。

`IMPL1("Hello", "World");`

このマクロは、実験的なプリプロセッサと従来のプリプロセッサの両方で同じように動作するように変更できます。 これを解決するには、次のように間接参照レイヤーを追加します。

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__

// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)

#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))

DO_THING_FIXED(1, "World");
// macro expanded to:
// do_thing_one( "Hello", "World");
```

### <a name="conformance-mode-conformance"></a>準拠モード準拠

試験的なプリプロセッサはまだ完了しておらず、一部のプリプロセッサディレクティブロジックは依然として従来の動作にフォールバックします。 不完全な機能の一部を次に示します。

- のサポート`_Pragma`
- C++ 20 の機能
- 追加の診断の機能強化
- /E および/P の下の出力を制御するスイッチ
- ブロッキングバグをブーストします。プリプロセッサ定数式の論理演算子は、新しいプリプロセッサで完全には実装されていません。 ディレクティブに`#if`よっては、新しいプリプロセッサが従来のプリプロセッサにフォールバックすることがあります。 この効果は、従来のプリプロセッサと互換性のないマクロが拡張された場合にのみ顕著になります。これは、プロセッサスロットをブーストする場合に発生する可能性があります。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. **[追加オプション]** プロパティを変更して、 **/実験的: プリプロセッサ**を追加し、[ **OK]** を選択します。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)
