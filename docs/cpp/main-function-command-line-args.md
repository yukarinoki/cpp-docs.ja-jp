---
title: '`main` 関数とコマンドライン引数 (C++)'
description: '`main`関数は、C++ プログラムのエントリポイントです。'
ms.date: 12/16/2020
no-loc:
- main
- wmain
- inline
- static
- _tmain
- void
- exit
- argc
- argv
- envp
- CreateProcess
- GetModuleFileName
- char
- wchar_t
- extern
ms.openlocfilehash: a9c68f199d4169c02260542a9730472e4ab397bd
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645073"
---
# <a name="no-locmain-function-and-command-line-arguments"></a>`main` 関数とコマンドライン引数

すべての C++ プログラムは、関数を持つ必要があり `main` ます。 関数を使用せずに C++ プログラムをコンパイルしようとすると、 `main` コンパイラでエラーが発生します。 (ダイナミックリンクライブラリとライブラリには static 関数がありません `main` )。 `main` 関数では、ソースコードの実行が開始されますが、プログラムが関数に入る前に `main` 、 static 明示的な初期化子のないすべてのクラスメンバーが0に設定されます。 Microsoft C++ では、 static へのエントリの前にグローバルオブジェクトも初期化され `main` ます。 `main`他の C++ 関数に適用されない関数には、いくつかの制限が適用されます。 `main` 関数は、次のことを行います。

- オーバーロードすることはできません (「 [関数のオーバーロード](./function-overloading.md)」を参照してください)。
- をとして宣言することはできません **`inline`** 。
- をとして宣言することはできません **`static`** 。
- アドレスを取得することはできません。
- をプログラムから呼び出すことはできません。

## <a name="the-no-locmain-function-signature"></a>`main`関数シグネチャ

関数は、 `main` 言語に組み込まれているため、宣言を持ちません。 これが行われた場合、の宣言構文は次の `main` ようになります。

```cpp
int main();
int main(int argc, char *argv[]);
```

に戻り値が指定されていない場合 `main` 、コンパイラは戻り値として0を指定します。

## <a name="standard-command-line-arguments"></a>標準のコマンドライン引数

の引数を `main` 使用すると、コマンドラインで引数を簡単に解析できます。 `argc` と `argv` の型は、言語によって定義されています。 という名前は `argc` `argv` 従来と同じですが、好きな名前を付けることができます。

引数の定義は、次のとおりです。

*`argc`*\
の後続の引数の数を含む整数 *argv* 。 パラメーターには、常に1以上の *argc* 値を指定します。

*`argv`*\
プログラムのユーザーが入力したコマンド ライン引数を表す、null で終了する文字列配列。 慣例により、 `argv[0]` はプログラムの呼び出しに使用されるコマンドです。 `argv[1]` は、最初のコマンドライン引数です。 コマンドラインからの最後の引数は `argv[argc - 1]` であり、 `argv[argc]` は常に NULL です。

コマンドライン処理を抑制する方法の詳細については、「 [C++ コマンドライン処理のカスタマイズ](#customize)」を参照してください。

> [!NOTE]
> 慣例により、 `argv[0]` はプログラムのファイル名です。 ただし、Windows では、を使用してプロセスを生成することができ [`CreateProcess`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) ます。 1番目と2番目の引数 (と) の両方を使用する場合は *`lpApplicationName`* *`lpCommandLine`* 、を `argv[0]` 実行可能ファイルの名前にすることはできません。 を使用する [`GetModuleFileName`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) と、実行可能ファイル名とその完全修飾パスを取得できます。

## <a name="microsoft-specific-extensions"></a>Microsoft 固有の拡張機能

以下のセクションでは、Microsoft 固有の動作について説明します。

## <a name="the-no-locwmain-function-and-no-loc_tmain-macro"></a>`wmain`関数と `_tmain` マクロ

Unicode ワイド acters を使用するようにソースコードを設計する場合は、 char Microsoft 固有 `wmain` のエントリポイントを使用できます。これは、 char のワイド acter バージョンです `main` 。 次に、の有効な宣言構文を示し `wmain` ます。

```cpp
int wmain();
int wmain(int argc, wchar_t *argv[]);
```

`_tmain`「」で定義されているプリプロセッサマクロである、Microsoft 固有のを使用することもでき *`tchar.h`* ます。 `_tmain``main`が定義されている場合を除き、に解決され `_UNICODE` ます。 定義されている場合、`_tmain` は `wmain` に解決されます。 `_tmain`で始まるマクロとその他のマクロ `_t` は、ナローとワイドの両方の acter セットに個別のバージョンを構築する必要があるコードに便利です char 。 詳細については、「 [汎用テキストマップの使用](../c-runtime-library/using-generic-text-mappings.md)」を参照してください。

## <a name="returning-no-locvoid-from-no-locmain"></a>返す `void`main

Microsoft の拡張機能として、 `main` `wmain` 関数と関数を返す **`void`** (戻り値はありません) として宣言できます。 この拡張機能は、他のいくつかのコンパイラでも使用できますが、その使用は推奨されていません。 が値を返さない場合、対称に使用でき `main` ます。

を返すようにまたはを宣言する場合、ステートメントを使用して、 `main` `wmain` **`void`** exit 親プロセスまたはオペレーティングシステムにコードを返すことはできません [`return`](./program-termination.md) 。 exit `main` または `wmain` がとして宣言されている場合にコードを返すには、 **`void`** 関数を使用する必要があり [`exit`](./program-termination.md) ます。

## <a name="the-no-locenvp-command-line-argument"></a>`envp`コマンドライン引数

`main`または `wmain` シグネチャにより、オプションの Microsoft 固有の拡張機能を使用して環境変数にアクセスできます。 この拡張機能は、Windows および UNIX システムの他のコンパイラでも一般的です。 名前は *`envp`* 従来と同じですが、環境パラメーターに任意の名前を付けることができます。 環境パラメーターを含む引数リストの有効な宣言を次に示します。

```cpp
int main(int argc, char* argv[], char* envp[]);
int wmain(int argc, wchar_t* argv[], wchar_t* envp[]);
```

*`envp`*\
省略可能な *`envp`* パラメーターは、ユーザーの環境で設定された変数を表す文字列の配列です。 この配列は NULL エントリで終了します。 このメソッドは、() へのポインターの配列として、 **`char`** `char *envp[]` または () へのポインターへのポインターとして宣言でき **`char`** `char **envp` ます。 プログラムがの代わりにを使用する場合は `wmain` `main` 、 **`wchar_t`** の代わりにデータ型を使用し **`char`** ます。

に渡される環境ブロックは、 `main` `wmain` 現在の環境の "固定" コピーです。 またはを呼び出すことによって環境を変更した場合 `putenv` `_wputenv` 、現在の環境 (または、または変数によって返されたもの `getenv` `_wgetenv` `_environ`  `_wenviron` ) は変更されますが、が指すブロックは *`envp`* 変わりません。 環境処理を抑制する方法の詳細については、「 [C++ コマンドライン処理のカスタマイズ](#customize)」を参照してください。 この *`envp`* 引数は、C89 標準と互換性がありますが、C++ 標準には対応していません。

### <a name="example-arguments-to-no-locmain"></a>引数の例 `main`

次の例では、に、、の各引数を使用する方法を示し *`argc`* *`argv`* *`envp`* `main` ます。

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int main( int argc, char *argv[], char *envp[] )
{
    bool numberLines = false;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.
    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )
         numberLines = true;

    // Walk through list of strings until a NULL is encountered.
    for ( int i = 0; envp[i] != NULL; ++i )
    {
        if ( numberLines )
            cout << i << ": "; // Prefix with numbers if /n specified
        cout << envp[i] << "\n";
    }
}
```

## <a name="parsing-c-command-line-arguments"></a>C++ のコマンド ライン引数の解析

Microsoft C/c + + コードによって使用されるコマンドライン解析規則は、Microsoft 固有のものです。 ランタイムスタートアップコードは、オペレーティングシステムのコマンドラインで指定された引数を解釈するときに、次の規則を使用します。

- 引数は、空白 (スペースまたはタブ) で区切ります。

- 最初の引数 (`argv[0]`) は、特別に処理されます。 それはプログラム名を表します。 有効なパス名である必要があるため、一部分を二重引用符 ( **`"`** ) で囲むことが許可されます。 二重引用符は、`argv[0]` の出力には含まれません。 二重引用符で囲まれた部分は、スペースまたはタブが char 引数の末尾として解釈されないようにします。 この一覧で後に示す規則は適用されません。

- 二重引用符で囲まれた文字列は、空白の acters を含む可能性のある単一の引数として解釈され char ます。 二重引用符で囲んだ文字列を引数に埋め込むこともできます。 キャレット () は、 **`^`** エスケープ char acter または区切り記号として認識されません。 引用符で囲まれた文字列内では、二重引用符のペアは単一のエスケープされた二重引用符として解釈されます。 終了二重引用符が検出される前にコマンドラインが終了した場合、これまでに読み取られたすべての char acters が最後の引数として出力されます。

- 円記号を前に付けた二重引用符 ( **`\"`** ) は、リテラルの二重引用符文字 ( **`"`** ) として解釈されます。

- 二重引用符の直前にある円記号以外は、円記号として文字どおり解釈されます。

- 二重引用符の直前に円記号が偶数個あると、円記号のペア ( **`\\`** ) ごとに 1 個の円記号 ( **`\`** ) が `argv` 配列に配置されます。この場合、二重引用符 ( **`"`** ) は文字列の区切り記号として解釈されます。

- 奇数個の円記号の後に二重引用符がある場合は、円記号のペア ( **`\\`** ) ごとに 1 個の円記号 ( **`\`** ) が `argv` 配列に配置されます。 二重引用符は、バックスラッシュによってエスケープシーケンスとして解釈され main 、リテラル二重引用符 ( **`"`** ) がに配置され `argv` ます。

### <a name="example-of-command-line-argument-parsing"></a>コマンドライン引数の解析の例

次のプログラムは、コマンド ライン引数がどのように受け渡されるかを示します。

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int main( int argc,      // Number of strings in array argv
          char *argv[],   // Array of command-line argument strings
          char *envp[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < argc; count++ )
         cout << "  argv[" << count << "]   "
                << argv[count] << "\n";
}
```

### <a name="results-of-parsing-command-lines"></a>コマンドラインの解析結果

次の表は、前の一覧の規則を示しながら、入力例と予想される出力を示しています。

| コマンドライン入力 | argv[1] | argv[2] | argv番 |
|--|--|--|--|
| `"abc" d e` | `abc` | `d` | `e` |
| `a\\b d"e f"g h` | `a\\b` | `de fg` | `h` |
| `a\\\"b c d` | `a\"b` | `c` | `d` |
| `a\\\\"b c" d e` | `a\\b c` | `d` | `e` |
| `a"b"" c d` | `ab" c d` |  |  |

## <a name="wildcard-expansion"></a>ワイルドカードの展開

Microsoft コンパイラでは、 *ワイルドカード* char acters、疑問符 ()、アスタリスク () を使用して、 **`?`** **`*`** コマンドラインでファイル名とパス引数を指定することもできます。

コマンドライン引数は、ランタイムスタートアップコードの内部ルーチンによって処理されます。既定では、ワイルドカードは文字列配列内の個別の文字列に展開されません `argv` 。 *`setargv.obj`* *`wsetargv.obj`* `wmain` **`/link`** コンパイラオプションまたはコマンドラインでファイル (の場合はファイル) を含めることで、ワイルドカードの展開を有効にすることができ **`LINK`** ます。

ランタイムのスタートアップ リンカー オプションの詳細については、「[リンク オプション](../c-runtime-library/link-options.md)」を参照してください。

## <a name="customize-c-command-line-processing"></a><a name="customize"/> C++ コマンドライン処理のカスタマイズ

プログラムがコマンド ライン引数を受け取らない場合は、コマンド ライン処理ルーチンを抑制して領域を少し節約できます。 その使用を抑制するには、 *`noarg.obj`* ファイルを (`main`、`wmain` どちらの場合でも) **`/link`** コンパイラ オプションまたは **`LINK`** コマンド ラインに含めます。

同様に、 *`envp`* 引数を使用して環境のテーブルにアクセスしない場合は、内部の環境処理ルーチンを抑制できます。 その使用を抑制するには、 *`noenv.obj`* ファイルを (`main`、`wmain` どちらの場合でも) **`/link`** コンパイラ オプションまたは **`LINK`** コマンド ラインに含めます。

プログラムによって、C ランタイム ライブラリの `spawn` または `exec` ファミリのルーチンが呼び出されることがあります。 その場合は、親プロセスから子プロセスに環境を渡すために環境処理ルーチンが使用されるため、抑制しないでください。

## <a name="see-also"></a>関連項目

[基本的な概念](../cpp/basic-concepts-cpp.md)
