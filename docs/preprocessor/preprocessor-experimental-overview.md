---
title: MSVC の新しいプリプロセッサの概要
description: MSVC プリプロセッサは、C/c + + 標準に準拠するように更新されています。
ms.date: 09/10/2020
helpviewer_keywords:
- preprocessor, experimental
- preprocessor, new
ms.openlocfilehash: 5327a8148f78a07e222fae7fb92e6ed741d12011
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924578"
---
# <a name="msvc-new-preprocessor-overview"></a>MSVC の新しいプリプロセッサの概要

::: moniker range="msvc-140"

Visual Studio 2015 では、標準 C++ または C99 に準拠していない従来のプリプロセッサが使用されます。 Visual Studio 2019 バージョン16.5 以降では、C++ 20 standard の新しいプリプロセッササポートは機能が完全になりました。 これらの変更は、 [/zc: プリプロセッサ](../build/reference/zc-preprocessor.md) コンパイラスイッチを使用して利用できます。 新しいプリプロセッサの実験的なバージョンは、Visual Studio 2017 バージョン15.8 以降では、 [/実験的: プリプロセッサ](../build/reference/experimental-preprocessor.md) コンパイラスイッチを使用して利用できます。 Visual Studio 2017 および Visual Studio 2019 で新しいプリプロセッサを使用する方法の詳細については、こちらを参照してください。 優先するバージョンの Visual Studio のドキュメントを表示するには、 **[バージョン]** セレクター コントロールを使用します。 このページの目次の一番上にあります。

::: moniker-end

::: moniker range=">=msvc-150"

標準への準拠を改善し、長期的なバグを修正し、正式に定義されていない動作を変更するために、Microsoft C++ プリプロセッサを更新しています。 また、マクロ定義にエラーが発生した場合に警告する新しい診断も追加しました。

Visual Studio 2019 バージョン16.5 以降では、C++ 20 standard のプリプロセッササポートは機能が完全になりました。 これらの変更は、 [/zc: プリプロセッサ](../build/reference/zc-preprocessor.md) コンパイラスイッチを使用して利用できます。 新しいプリプロセッサの実験的なバージョンは、Visual Studio 2017 バージョン15.8 以降では、以前のバージョンで使用できます。 これを有効にするには、 [/実験的: プリプロセッサ](../build/reference/experimental-preprocessor.md) コンパイラスイッチを使用します。 既定のプリプロセッサ動作は、以前のバージョンと同じです。

## <a name="new-predefined-macro"></a>新しい定義済みマクロ

コンパイル時に使用中のプリプロセッサを検出できます。 定義済みマクロの値を確認 [`_MSVC_TRADITIONAL`](predefined-macros.md) し、従来のプリプロセッサが使用されているかどうかを確認します。 このマクロは、呼び出されたプリプロセッサに関係なく、それをサポートするバージョンのコンパイラによって無条件に設定されます。 この値は、従来のプリプロセッサの場合は1です。 準拠プリプロセッサの場合は0です。

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-new-preprocessor"></a>新しいプリプロセッサでの動作の変更

新しいプリプロセッサでの初期作業は、すべてのマクロ拡張を標準に準拠させることに重点を置いています。 これにより、従来の動作によって現在ブロックされているライブラリで MSVC コンパイラを使用できるようになります。 更新されたプリプロセッサを実際のプロジェクトでテストしました。 次に、よく見られる重大な変更の一部を示します。

### <a name="macro-comments"></a>マクロコメント

従来のプリプロセッサは、プリプロセッサトークンではなく、文字バッファーに基づいています。 これにより、準拠プリプロセッサでは動作しない次のプリプロセッサコメントトリックなどの異常な動作が可能になります。

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
DISAPPEARING_TYPE myVal;
```

標準に準拠した修正は、 `int myVal` 適切なディレクティブ内で宣言することです `#ifdef/#endif` 。

```cpp
#define MYVAL 1

#ifdef MYVAL
int myVal;
#endif
```

### <a name="lval"></a>L # val

従来のプリプロセッサでは、文字列のプレフィックスが文字列化 [演算子 (#)](stringizing-operator-hash.md) 演算子の結果と誤って結合されています。

```cpp
 #define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

この場合、隣接する `L` 文字列リテラルはマクロの展開後に結合されるため、プレフィックスは不要です。 下位互換性のある修正は、定義を変更することです。

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

この同じ問題は、次のように、引数をワイド文字列リテラルに "stringize" 表現する便利なマクロにもあります。

```cpp
 // The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str
```

次のようなさまざまな方法で問題を解決できます。

- `L""`プレフィックスを追加するには、との文字列連結を使用し `#str` ます。 隣接する文字列リテラルは、マクロの展開後に結合されます。

   ```cpp
   #define STRING1(str) L""#str
   ```

- `#str`追加のマクロ展開を使用して文字列を追加した後にプレフィックスを追加する

   ```cpp
   #define WIDE(str) L##str
   #define STRING2(str) WIDE(#str)
   ```

- トークンを結合するには、連結演算子を使用し `##` ます。 とに対する操作の `##` 順序 `#` は指定されていませんが、 `#` この場合は、すべてのコンパイラが演算子を評価しているようです `##` 。

   ```cpp
   #define STRING3(str) L## #str
   ```

### <a name="warning-on-invalid-"></a>無効な警告 \#\#

[トークン連結演算子 (# #)](token-pasting-operator-hash-hash.md)によって1つの有効なプリプロセストークンが生成されない場合、動作は未定義になります。 従来のプリプロセッサは、トークンの結合に失敗しました。 新しいプリプロセッサは、他のほとんどのコンパイラの動作と一致し、診断を生成します。

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>可変個引数マクロでのコンマ省略

従来の MSVC プリプロセッサでは、空の置換の前に、常にコンマが削除され `__VA_ARGS__` ます。 新しいプリプロセッサは、他の一般的なクロスプラットフォームコンパイラの動作により厳密に準拠しています。 コンマを削除するには、可変個引数引数が不足している (空ではない) 必要があり、演算子でマークされている必要があり `##` ます。 次の例を確認してください。

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // In the traditional preprocessor, the
    // following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor replaces the
    // following macro with: func(1, ), which
    // results in a syntax error.
    FUNC(1, );
}
```

次の例では、 `FUNC2(1)` 呼び出されているマクロに可変個引数引数がありません。 の呼び出しで `FUNC2(1, )` は、可変個引数引数は空ですが、不足していません (引数リスト内のコンマに注意してください)。

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
   // Expands to func(1)
   FUNC2(1);

   // Expands to func(1, )
   FUNC2(1, );
}
```

今後の C++ 20 標準では、を追加することでこの問題に対処しました `__VA_OPT__` 。 の新しいプリプロセッササポート  `__VA_OPT__` は、Visual Studio 2019 バージョン16.5 以降で使用できます。

### <a name="c20-variadic-macro-extension"></a>C++ 20 可変個引数マクロ拡張機能

新しいプリプロセッサは、C++ 20 可変個引数マクロ引数省略をサポートしています。

```cpp
#define FUNC(a, ...) __VA_ARGS__ + a
int main()
  {
  int ret = FUNC(0);
  return ret;
  }
```

このコードは、C++ 20 標準より前に準拠していません。 MSVC では、新しいプリプロセッサによって、この C++ 20 の動作が下位言語の標準モード (、) に拡張され **`/std:c++14`** **`/std:c++17`** ます。 この拡張機能は、他の主要なクロスプラットフォームの C++ コンパイラの動作と一致します。

### <a name="macro-arguments-are-unpacked"></a>マクロの引数は "アンパック" されます

従来のプリプロセッサでは、マクロが引数の1つを別の依存マクロに転送した場合、引数は挿入されるときに "アンパック" されません。 通常、この最適化は気付かれませんが、異常な動作につながる可能性があります。

```cpp
// Create a string out of the first argument, and the rest of the arguments.
#define TWO_STRINGS( first, ... ) #first, #__VA_ARGS__
#define A( ... ) TWO_STRINGS(__VA_ARGS__)
const char* c[2] = { A(1, 2) };

// Conforming preprocessor results:
// const char c[2] = { "1", "2" };

// Traditional preprocessor results, all arguments are in the first string:
// const char c[2] = { "1, 2", };
```

拡張すると `A()` 、従来のプリプロセッサは、にパッケージ化されたすべての引数 `__VA_ARGS__` を TWO_STRINGS の最初の引数に転送します。これにより、可変個引数引数は空のままに `TWO_STRINGS` なります。 これにより、の結果が `#first` 単に単に "1" ではなく "1, 2" になります。 厳密に従うと、従来のプリプロセッサ展開での結果に何が起こったか疑問に思われるかもしれませ `#__VA_ARGS__` ん。可変個引数パラメーターが空の場合、空の文字列リテラルになり `""` ます。 別個の問題により、空の文字列リテラルトークンが生成されませんでした。

### <a name="rescanning-replacement-list-for-macros"></a>マクロの置換リストの再スキャン

マクロが置換された後、結果として生成されるトークンは、他のマクロ識別子を置き換えるために再スキャンされます。 次の例に示すように、実際のコードに基づいて、再スキャンを実行するために従来のプリプロセッサによって使用されるアルゴリズムは準拠していません。

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
// Conforming preprocessor:
// IMPL1 ( "Hello","World");
```

この例は少し不自然に見えるかもしれませんが、実際のコードで見てきました。

何が起こっているのかを確認するには、次のようにして展開を分割し `DO_THING` ます。

1. `DO_THING(1, "World")` 展開先 `CAT(IMPL, 1) ECHO(("Hello", "World"))`
1. `CAT(IMPL, 1)` をに展開し `IMPL ## 1` ます。 `IMPL1`
1. これで、トークンは次の状態になります。 `IMPL1 ECHO(("Hello", "World"))`
1. プリプロセッサでは、関数に似たマクロ識別子が検索され `IMPL1` ます。 この後にはがないため `(` 、関数のようなマクロの呼び出しとは見なされません。
1. プリプロセッサは、次のトークンに移動します。 関数に似たマクロが呼び出されたことを検出し `ECHO` ます。 `ECHO(("Hello", "World"))``("Hello", "World")`
1. `IMPL1` は、拡張のためにもう一度考慮されることはないため、展開の完全な結果は次のようになります。 `IMPL1("Hello", "World");`

新しいプリプロセッサと従来のプリプロセッサの両方で同じようにマクロが動作するように変更するには、次のように間接参照レイヤーを追加します。

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__
// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)
#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))
DO_THING_FIXED(1, "World");

// macro expands to:
// do_thing_one( "Hello", "World");
```

## <a name="incomplete-features-before-165"></a>16.5 より前の不完全な機能

Visual Studio 2019 バージョン16.5 以降では、新しいプリプロセッサは C++ 20 に対して完全に機能します。 以前のバージョンの Visual Studio では、新しいプリプロセッサはほぼ完了していますが、一部のプリプロセッサディレクティブロジックは依然として従来の動作にフォールバックします。 16.5 より前の Visual Studio バージョンの不完全な機能の一部を次に示します。

- `_Pragma` のサポート
- C++ 20 の機能
- ブロッキングバグのブースト: プリプロセッサ定数式の論理演算子は、バージョン16.5 より前の新しいプリプロセッサでは完全には実装されません。 ディレクティブによっては、 `#if` 新しいプリプロセッサが従来のプリプロセッサにフォールバックすることがあります。 この効果は、マクロが従来のプリプロセッサと互換性がない場合にのみ顕著になります。 プロセッサスロットをブーストするときに発生する可能性があります。

::: moniker-end
