---
title: main 関数とコマンドライン引数 (C++)
description: main関数は、C++ プログラムのエントリポイントです。
ms.date: 01/15/2019
ms.assetid: c6568ee6-40ab-4ae8-aa44-c99e232f64ac
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
ms.openlocfilehash: b27668c3c7ce77e4369af144bb8be4efb695e522
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499811"
---
# <a name="no-locmain-function-and-command-line-arguments"></a>main 関数とコマンドライン引数

すべての C++ プログラムは、関数を持つ必要があり `main` ます。 関数を使用せずに C++ の *.exe* プロジェクトをコンパイルしようとすると、コンパイラでエラーが発生 main します。 (ダイナミックリンクライブラリとライブラリには static 関数がありません `main` )。 `main` 関数では、ソースコードの実行が開始されますが、プログラムが関数に入る前に `main` 、 static 明示的な初期化子のないすべてのクラスメンバーが0に設定されます。 Microsoft C++ では、 static へのエントリの前にグローバルオブジェクトも初期化され `main` ます。 `main`他の C++ 関数に適用されない関数には、いくつかの制限が適用されます。 `main`関数:

- オーバーロードできません (「 [関数のオーバーロード](function-overloading.md)」を参照してください)。
- をとして宣言することはできません **`inline`** 。
- をとして宣言することはできません **`static`** 。
- そのアドレスを取得することはできません。
- 呼び出すことはできません。

関数は、 main 言語に組み込まれているため、宣言を持ちません。 これが行われた場合、の宣言構文は次の `main` ようになります。

```cpp
int main();
int main(int argc, char *argv[], char *envp[]);
```

**Microsoft 固有の仕様**

ソースファイルで Unicode ワイド acters が使用されている場合は char `wmain` 、のワイド acter バージョンであるを使用でき char `main` ます。 `wmain` の宣言構文は次のとおりです。

```cpp
int wmain( );
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

を使用することもできます。 `_tmain` これは、.h で定義されてい char ます。 `_tmain``main`_UNICODE が定義されている場合を除き、に解決されます。 定義されている場合、`_tmain` は `wmain` に解決されます。

戻り値が指定されていない場合、コンパイラは戻り値として0を指定します。 または、 `main` 関数および関数を、 `wmain` 戻り値を返さないとして宣言することもでき **`void`** ます。 を返すようにまたはを宣言する場合 `main` `wmain` **`void`** 、return ステートメントを使用して、 exit 親プロセスまたは[return](./program-termination.md)オペレーティングシステムにコードを返すことはできません。 exit `main` または `wmain` がとして宣言されている場合にコードを返すには、 **`void`** 関数を使用する必要があり [exit](./program-termination.md) ます。

**Microsoft 固有の仕様はここまで**

## <a name="command-line-arguments"></a>コマンド ライン引数

またはの引数を `main` `wmain` 使用すると、簡単に引数を解析したり、必要に応じて環境変数にアクセスしたりできます。 `argc` と `argv` の型は、言語によって定義されています。 名前、 `argc` 、およびは従来の名前です `argv` が、 `envp` 好きな名前を付けることができます。

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

引数の定義は、次のとおりです。

*argc*<br/>
の後続の引数の数を含む整数 *argv* 。 パラメーターには、常に1以上の *argc* 値を指定します。

*argv*<br/>
プログラムのユーザーが入力したコマンド ライン引数を表す、null で終了する文字列配列。 慣例として、 `argv[0]` はプログラムの呼び出しに使用されるコマンドで、 `argv[1]` は最初のコマンドライン引数であり、それ以降は常に NULL になり `argv[argc]` ます。 コマンドライン処理の抑制については、「 [コマンドライン処理のカスタマイズ]() 」を参照してください。

最初のコマンド ライン引数は、必ず `argv[1]` となり、最後のコマンド ライン引数は、`argv[argc - 1]` になります。

> [!NOTE]
> 慣例により、 `argv[0]` はプログラムの呼び出しに使用されるコマンドです。 ただし、 [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 1 番目と2番目の引数 (*lpapplicationname* と *lpapplicationname*) の両方を使用する場合は、を使用してプロセスを生成することができ `argv[0]` ます。実行可能ファイルの [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 名前を取得するには、を使用します。実行可能ファイル名とその完全修飾パスを取得します。

**Microsoft 固有の仕様**

*envp*<br/>
*envp* Microsoft C++ では、多くの UNIX システムで共通の拡張機能である配列が使用されています。 これは、ユーザーの環境で設定された変数を表す文字列の配列です。 この配列は NULL エントリで終了します。 このメソッドは、() へのポインターの配列として、 **`char`** `char *envp[]` または () へのポインターへのポインターとして宣言でき **`char`** `char **envp` ます。 プログラムがの代わりにを使用する場合は `wmain` `main` 、 **`wchar_t`** の代わりにデータ型を使用し **`char`** ます。 に渡される環境ブロックは、 `main` `wmain` 現在の環境の "固定" コピーです。 後でまたはへの呼び出しを使用して環境を変更した場合 `putenv` `_wputenv` 、現在の環境 (または、または変数によって返される `getenv` `_wgetenv` `_environ`  `_wenviron` ) は変更されますが、が指すブロックは変更され envp ません。 環境処理の抑制については、「 [コマンドライン処理のカスタマイズ]() 」を参照してください。 この引数は、C では ANSI 互換ですが、C++ では非互換です。

**Microsoft 固有の仕様はここまで**

### <a name="example"></a>例

次の例では、に、、の各引数を使用する方法を示し *argc* *argv* *envp* `main` ます。

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int main( int argc, char *argv[], char *envp[] ) {
    int iNumberLines = 0;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.

    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )
         iNumberLines = 1;

    // Walk through list of strings until a NULL is encountered.
    for( int i = 0; envp[i] != NULL; ++i ) {
        if( iNumberLines )
            cout << i << ": " << envp[i] << "\n";
    }
}
```

## <a name="parsing-c-command-line-arguments"></a>C++ コマンドライン引数の解析

**Microsoft 固有の仕様**

Microsoft C/C++ 起動コードは、オペレーティング システムのコマンド ラインで指定された引数を解釈する場合に、次の規則を使用します。

- 引数は、空白 (スペースまたはタブ) で区切ります。

- キャレット char (^) は、エスケープ char acter または区切り記号として認識されません。 charActer は、プログラムの配列に渡される前に、オペレーティングシステムのコマンドラインパーサーによって完全に処理され `argv` ます。

- 二重引用符で囲まれた文字列 ("*string*") は、内に空白が含まれていなくても、単一の引数として解釈されます。 二重引用符で囲んだ文字列を引数に埋め込むこともできます。

- 円記号 (") を前に付けた二重引用符 \\ は、リテラル二重引用符 char acter (") として解釈されます。

- 二重引用符の直前にある円記号以外は、円記号 (\) として解釈されます。

- 二重引用符の直前に円記号が偶数個あると、円記号のペアごとに 1 個の円記号が `argv` 配列に配置されます。この場合、二重引用符は文字列の区切り記号として解釈されます。

- 円記号の奇数の後に二重引用符が続く場合、円記号のペアごとに1つの円記号が配列に格納され `argv` ます。二重引用符は、円記号の区切り記号によって "エスケープ" されます。これにより main 、リテラル二重引用符 (") がに配置され `argv` ます。

### <a name="example"></a>例

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

次の表は、前の一覧の規則を示しながら、入力例と予想される出力を示しています。

### <a name="results-of-parsing-command-lines"></a>コマンドラインの解析結果

|コマンド ライン入力|argv[1]|argv[2]|argv番|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**Microsoft 固有の仕様はここまで**

## <a name="wildcard-expansion"></a>ワイルドカードの展開

**Microsoft 固有の仕様**

コマンド ラインでファイル名とパスの引数を指定するときに、ワイルドカード (疑問符 (?) およびアスタリスク (*)) を使用できます。

コマンドライン引数は、(ワイド acter 環境では) と呼ばれるルーチンによって処理され `_setargv` `_wsetargv` char ます。既定では、ワイルドカードは文字列配列内の個別の文字列に展開されません `argv` 。 ワイルドカードの展開を有効にする方法の詳細については、「 [ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="customizing-c-command-line-processing"></a>C++ のコマンド ライン処理のカスタマイズ

**Microsoft 固有の仕様**

プログラムがコマンド ラインの引数を受け取らない場合は、コマンド ライン処理を実行するライブラリ ルーチンの使用を制約することで、領域を節約できます。 このルーチンは `_setargv` 、「 [ワイルドカードの展開]()」で説明されています。 使用しないようにするには、関数を含むファイルで何も実行しないルーチンを定義 `main` し、という名前を指定し `_setargv` ます。 `_setargv`の呼び出しがの定義によって満たされ、 `_setargv` ライブラリのバージョンが読み込まれていません。

同様に、引数を使用して環境テーブルにアクセスしない場合は、 `envp` 環境処理ルーチンの代わりに独自の空のルーチンを使用することができ `_setenvp` ます。 関数と同様に `_setargv` 、は `_setenvp` ** extern "C"** として宣言する必要があります。

プログラムによって、 `spawn` C ランタイムライブラリのまたはルーチンのファミリが呼び出される場合があり `exec` ます。 存在する場合は、環境処理ルーチンを抑制しないでください。このルーチンは、親プロセスから子プロセスに環境を渡すために使用されるためです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[基本的な概念](../cpp/basic-concepts-cpp.md)
