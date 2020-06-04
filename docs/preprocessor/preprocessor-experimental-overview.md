---
title: MSVC の実験プリプロセッサの概要
description: MSVC プリプロセッサは、C/C++ 標準に準拠するために更新されています。
ms.date: 02/09/2020
helpviewer_keywords:
- preprocessor, experimental
ms.openlocfilehash: 00c34ef75270e505d3781cf7eedf4d8aba95ee6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337483"
---
# <a name="msvc-experimental-preprocessor-overview"></a>MSVC の実験プリプロセッサの概要

::: moniker range="vs-2015"

Visual Studio 2015 では、標準 C++ に準拠していない従来のプリプロセッサが使用されます。 実験用プリプロセッサは[、/実験:プリプロセッサ](../build/reference/experimental-preprocessor.md)コンパイラ スイッチを使用して、Visual Studio 2017 と Visual Studio 2019 で使用できます。 Visual Studio 2017 および Visual Studio 2019 での新しいプリプロセッサの使用に関する詳細については、次の参照先を参照してください。 Visual Studio の優先バージョンのドキュメントを表示するには、**バージョン**セレクター コントロールを使用します。 このページの目次の上部に表示されます。

::: moniker-end

::: moniker range=">=vs-2017"

Microsoft C++ プリプロセッサを更新して、標準の準拠性を向上させ、長年にわたるバグを修正し、公式に定義されていない動作を変更します。 また、マクロ定義のエラーを警告する新しい診断も追加されました。

これらの変更は、Visual Studio 2017 または Visual Studio 2019 で[/実験:プリプロセッサ](../build/reference/experimental-preprocessor.md)コンパイラ スイッチを使用して利用できます。 デフォルトのプリプロセッサの動作は、以前のバージョンと同じです。

Visual Studio 2019 バージョン 16.5 以降、C++20 標準の実験的プリプロセッサ サポートは機能を完全に提供します。

## <a name="new-predefined-macro"></a>新しい定義済みマクロ

コンパイル時に使用中のプリプロセッサを検出できます。 事前定義されたマクロ[\_MSVC\_トラディショナル](predefined-macros.md)の値を調べて、従来のプリプロセッサーが使用中かどうかを調べるようにしてください。 このマクロは、どのプリプロセッサが呼び出されるのとは無関係に、それをサポートするコンパイラのバージョンによって無条件に設定されます。 この値は、従来のプリプロセッサでは 1 です。 適合プリプロセッサの場合は 0 です。

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-experimental-preprocessor"></a>実験プリプロセッサでの動作の変化

実験プリプロセッサの最初の作業は、すべてのマクロ拡張を標準に準拠させることに焦点を当ててきました。 この機能を使用すると、従来の動作によって現在ブロックされているライブラリで MSVC コンパイラを使用できます。 実際のプロジェクトで更新されたプリプロセッサをテストしました。 見つかった一般的な変更点のいくつかを次に示します。

### <a name="macro-comments"></a>マクロコメント

従来のプリプロセッサは、プリプロセッサ トークンではなく文字バッファに基づいています。 これは、次のような異常な動作を可能にする、次のプリプロセッサのコメントトリックは、準拠プリプロセッサでは動作しません。

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
DISAPPEARING_TYPE myVal;
```

標準に準拠した修正は、適切な`int myVal``#ifdef/#endif`ディレクティブの内部で宣言することです。

```cpp
#define MYVAL 1

#ifdef MYVAL
int myVal;
#endif
```

### <a name="lval"></a>L#ヴァル

従来のプリプロセッサでは、文字列のプレフィックスを[文字列化演算子 (#)](stringizing-operator-hash.md)演算子の結果に正しく結合しません。

```cpp
 #define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

この場合、隣接する`L`文字列リテラルはマクロ展開後に結合されるため、プレフィックスは不要です。 下位互換性のある修正プログラムは、定義を変更することです。

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

同じ問題は、広い文字列リテラルに引数を「文字列化」する便利なマクロにも見られます。

```cpp
 // The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str
```

さまざまな方法で問題を解決できます。

- 文字列の連結`L""`を使用し、`#str`プレフィックスを追加します。 隣接する文字列リテラルは、マクロ展開後に結合されます。

   ```cpp
   #define STRING1(str) L""#str
   ```

- 追加のマクロ展開`#str`で文字列化された後にプレフィックスを追加します。

   ```cpp
   #define WIDE(str) L##str
   #define STRING2(str) WIDE(#str)
   ```

- 連結演算子`##`を使用して、トークンを結合します。 `##`この場合`#`、すべてのコンパイラが`#`演算子`##`を評価するように見えますが、演算の順序は指定されていません。

   ```cpp
   #define STRING3(str) L## #str
   ```

### <a name="warning-on-invalid-"></a>無効な場合の警告\#\#

[トークン貼り付け演算子 (##) が](token-pasting-operator-hash-hash.md)1 つの有効な前処理トークンを返さない場合、動作は未定義です。 従来のプリプロセッサは、トークンを結合できないままです。 新しいプリプロセッサは、他のほとんどのコンパイラの動作と一致し、診断を出力します。

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>可変個変数マクロにおけるコンマの省略

従来の MSVC プリプロセッサは、空`__VA_ARGS__`の置換の前に常にコンマを削除します。 実験用プリプロセッサは、他の一般的なクロスプラットフォームコンパイラの動作に密接に従います。 コンマを削除するには、可変個引数が欠落している必要があり (空の場合だけでなく) 演算子でマークする`##`必要があります。 次の例を確認してください。

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

次の例では、呼び出される`FUNC2(1)`マクロで可変引数の呼び出しがありません。 可変個引数`FUNC2(1, )`の呼び出しでは空ですが、欠落していません (引数リストのコンマに注意してください)。

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

今後の C++ 20 標準では、この問題は を追加`__VA_OPT__`することで解決されています。 Visual Studio 2019 バージョン 16.5 以降で、実験的なプリプロセッサ のサポート`__VA_OPT__`が利用可能です。

### <a name="c20-variadic-macro-extension"></a>C++20 可変個変数マクロ拡張

実験プリプロセッサは、C++20 可変量マクロ引数の明知をサポートしています。

```cpp
#define FUNC(a, ...) __VA_ARGS__ + a
int main()
  {
  int ret = FUNC(0);
  return ret;
  }
```

このコードは C++20 標準より前に準拠していません。 MSVC では、実験プリプロセッサは、この C++20 動作を低言語**`/std:c++14`** 標準**`/std:c++17`** モード ( 、 ) に拡張します。 この拡張機能は、他の主要なクロスプラットフォーム C++ コンパイラの動作と一致します。

### <a name="macro-arguments-are-unpacked"></a>マクロ引数は"アンパック" されます。

従来のプリプロセッサでは、マクロが引数の 1 つを別の従属マクロに転送した場合、その引数は挿入時に "アンパック" されません。 通常、この最適化は気付かれませんが、異常な動作につながる可能性があります。

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

`A()`を拡張すると、従来のプリプロセッサは、パッケージ化されたすべての引数`__VA_ARGS__`を TWO_STRINGS の最初の引数に転送します`TWO_STRINGS`。 その結果、結果は`#first`単なる "1" ではなく "1, 2" になります。 あなたが密接に従っているなら、伝統的なプリプロセッサ拡張の`#__VA_ARGS__`結果に何が起こったのか疑問に思うかもしれません: variadic パラメータが空の場合は空の文字列リテラル`""`になります。 別の問題により、空の文字列リテラル トークンが生成されないという問題が発生しました。

### <a name="rescanning-replacement-list-for-macros"></a>マクロの置換リストを再スキャンする

マクロを置き換えた後、結果のトークンは、置換する追加のマクロ識別子のために再スキャンされます。 この例では、実際のコードに基づいて、再スキャンを実行するために従来のプリプロセッサで使用されるアルゴリズムが準拠していません。

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

この例は少し工夫されているように見えるかもしれませんが、実際のコードで見てきました。 何が起こっているのかを確認するには、次の項目から`DO_THING`拡張を分解します。

1. `DO_THING(1, "World")`に拡大`CAT(IMPL, 1) ECHO(("Hello", "World"))`
1. `CAT(IMPL, 1)`に`IMPL ## 1`拡張され、`IMPL1`
1. これで、トークンはこの状態になります。`IMPL1 ECHO(("Hello", "World"))`
1. プリプロセッサは関数のようなマクロ識別子`IMPL1`を検索します。 に続くわけではないので、`(`関数のようなマクロ呼び出しとは見なされません。
1. プリプロセッサは次のトークンに移動します。 関数に似たマクロ`ECHO`が呼び出されます: `ECHO(("Hello", "World"))``("Hello", "World")`
1. `IMPL1`展開のために再び考慮されることはないので、拡張の完全な結果は次のようになります。`IMPL1("Hello", "World");`

実験プリプロセッサと従来のプリプロセッサの両方で同じように動作するようにマクロを変更するには、間接別のレイヤーを追加します。

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

## <a name="incomplete-features"></a>不完全な機能

Visual Studio 2019 バージョン 16.5 以降、C++20 の機能は、実験用プリプロセッサが完全です。 以前のバージョンの Visual Studio では、実験用プリプロセッサはほとんど完了していますが、一部のプリプロセッサ ディレクティブ ロジックは従来の動作に戻ります。 16.5 より前の Visual Studio バージョンの不完全な機能の一部を次に示します。

- `_Pragma` のサポート
- C++20の機能
- ブロックのバグを高める: プリプロセッサ定数式の論理演算子は、バージョン 16.5 より前の新しいプリプロセッサで完全には実装されていません。 ディレクティブによっては`#if`、新しいプリプロセッサが従来のプリプロセッサにフォールバックする場合があります。 この効果は、従来のプリプロセッサと互換性のないマクロが展開された場合にのみ顕著です。 これは、Boost プリプロセッサ スロットを構築するときに発生する可能性があります。

::: moniker-end
