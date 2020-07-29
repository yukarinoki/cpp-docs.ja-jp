---
title: :::no-loc(main):::関数とコマンドライン引数 (C++)
description: :::no-loc(main):::関数は、C++ プログラムのエントリポイントです。
ms.date: 01/15/2019
ms.assetid: c6568ee6-40ab-4ae8-aa44-c99e232f64ac
no-loc:
- ':::no-loc(main):::'
- ':::no-loc(wmain):::'
- ':::no-loc(inline):::'
- ':::no-loc(static):::'
- ':::no-loc(_tmain):::'
- ':::no-loc(void):::'
- ':::no-loc(exit):::'
- ':::no-loc(argc):::'
- ':::no-loc(argv):::'
- ':::no-loc(envp):::'
- ':::no-loc(CreateProcess):::'
- ':::no-loc(GetModuleFileName):::'
- ':::no-loc(char):::'
- ':::no-loc(wchar_t):::'
- ':::no-loc(extern):::'
ms.openlocfilehash: 9fe7c7a0808584a70bffa541903866b3de364e5f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213321"
---
# <a name="no-locmain-function-and-command-line-arguments"></a>:::no-loc(main):::関数とコマンドライン引数

すべての C++ プログラムは、関数を持つ必要があり `:::no-loc(main):::` ます。 関数を使用せずに C++ の *.exe*プロジェクトをコンパイルしようとすると、コンパイラでエラーが発生 :::no-loc(main)::: します。 (ダイナミックリンクライブラリとライブラリには :::no-loc(static)::: 関数がありません `:::no-loc(main):::` )。`:::no-loc(main):::`関数では、ソースコードの実行が開始されますが、プログラムが関数に入る前に `:::no-loc(main):::` 、 :::no-loc(static)::: 明示的な初期化子のないすべてのクラスメンバーが0に設定されます。 Microsoft C++ では、 :::no-loc(static)::: へのエントリの前にグローバルオブジェクトも初期化され `:::no-loc(main):::` ます。 `:::no-loc(main):::`他の C++ 関数に適用されない関数には、いくつかの制限が適用されます。 `:::no-loc(main):::`関数:

- オーバーロードできません (「[関数のオーバーロード](function-overloading.md)」を参照してください)。
- をとして宣言することはできません **`:::no-loc(inline):::`** 。
- をとして宣言することはできません **`:::no-loc(static):::`** 。
- そのアドレスを取得することはできません。
- 呼び出すことはできません。

関数は、 :::no-loc(main)::: 言語に組み込まれているため、宣言を持ちません。 これが行われた場合、の宣言構文は次の `:::no-loc(main):::` ようになります。

```cpp
int :::no-loc(main):::();
int :::no-loc(main):::(int :::no-loc(argc):::, :::no-loc(char)::: *:::no-loc(argv):::[], :::no-loc(char)::: *:::no-loc(envp):::[]);
```

**Microsoft 固有の仕様**

ソースファイルで Unicode ワイド acters が使用されている場合は :::no-loc(char)::: `:::no-loc(wmain):::` 、のワイド acter バージョンであるを使用でき :::no-loc(char)::: `:::no-loc(main):::` ます。 `:::no-loc(wmain):::` の宣言構文は次のとおりです。

```cpp
int :::no-loc(wmain):::( );
int :::no-loc(wmain):::(int :::no-loc(argc):::, :::no-loc(wchar_t)::: *:::no-loc(argv):::[], :::no-loc(wchar_t)::: *:::no-loc(envp):::[]);
```

を使用することもできます。 `:::no-loc(_tmain):::` これは、.h で定義されてい :::no-loc(char)::: ます。 `:::no-loc(_tmain):::``:::no-loc(main):::`_UNICODE が定義されている場合を除き、に解決されます。 定義されている場合、`:::no-loc(_tmain):::` は `:::no-loc(wmain):::` に解決されます。

戻り値が指定されていない場合、コンパイラは戻り値として0を指定します。 または、 `:::no-loc(main):::` 関数および関数を、 `:::no-loc(wmain):::` 戻り値を返さないとして宣言することもでき **`:::no-loc(void):::`** ます。 を返すようにまたはを宣言する場合 `:::no-loc(main):::` `:::no-loc(wmain):::` **`:::no-loc(void):::`** 、return ステートメントを使用して、 :::no-loc(exit)::: 親プロセスまたは[return](../cpp/return-statement-in-program-termination-cpp.md)オペレーティングシステムにコードを返すことはできません。 :::no-loc(exit)::: `:::no-loc(main):::` または `:::no-loc(wmain):::` がとして宣言されている場合にコードを返すには、 **`:::no-loc(void):::`** 関数を使用する必要があり [:::no-loc(exit):::](../cpp/:::no-loc(exit):::-function.md) ます。

**Microsoft 固有の仕様はここまで**

## <a name="command-line-arguments"></a>コマンド ライン引数

またはの引数を `:::no-loc(main):::` `:::no-loc(wmain):::` 使用すると、簡単に引数を解析したり、必要に応じて環境変数にアクセスしたりできます。 `:::no-loc(argc):::` と `:::no-loc(argv):::` の型は、言語によって定義されています。 名前、 `:::no-loc(argc):::` 、およびは従来の名前です `:::no-loc(argv):::` が、 `:::no-loc(envp):::` 好きな名前を付けることができます。

```cpp
int :::no-loc(main):::( int :::no-loc(argc):::, :::no-loc(char):::* :::no-loc(argv):::[], :::no-loc(char):::* :::no-loc(envp):::[]);
int :::no-loc(wmain):::( int :::no-loc(argc):::, :::no-loc(wchar_t):::* :::no-loc(argv):::[], :::no-loc(wchar_t):::* :::no-loc(envp):::[]);
```

引数の定義は、次のとおりです。

*:::no-loc(argc):::*<br/>
の後続の引数の数を含む整数 *:::no-loc(argv):::* 。 パラメーターには、常に1以上の *:::no-loc(argc):::* 値を指定します。

*:::no-loc(argv):::*<br/>
プログラムのユーザーが入力したコマンド ライン引数を表す、null で終了する文字列配列。 慣例として、 `:::no-loc(argv):::[0]` はプログラムの呼び出しに使用されるコマンドで、 `:::no-loc(argv):::[1]` は最初のコマンドライン引数であり、それ以降は常に NULL になり `:::no-loc(argv):::[:::no-loc(argc):::]` ます。 コマンドライン処理の抑制については、「[コマンドライン処理のカスタマイズ](../cpp/customizing-cpp-command-line-processing.md)」を参照してください。

最初のコマンド ライン引数は、必ず `:::no-loc(argv):::[1]` となり、最後のコマンド ライン引数は、`:::no-loc(argv):::[:::no-loc(argc)::: - 1]` になります。

> [!NOTE]
> 慣例により、 `:::no-loc(argv):::[0]` はプログラムの呼び出しに使用されるコマンドです。 ただし、 [:::no-loc(CreateProcess):::](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 1 番目と2番目の引数 (*lpapplicationname*と*lpapplicationname*) の両方を使用する場合は、を使用してプロセスを生成することができ `:::no-loc(argv):::[0]` ます。実行可能ファイルの [:::no-loc(GetModuleFileName):::](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 名前を取得するには、を使用します。実行可能ファイル名とその完全修飾パスを取得します。

**Microsoft 固有の仕様**

*:::no-loc(envp):::*<br/>
*:::no-loc(envp):::* Microsoft C++ では、多くの UNIX システムで共通の拡張機能である配列が使用されています。 これは、ユーザーの環境で設定された変数を表す文字列の配列です。 この配列は NULL エントリで終了します。 このメソッドは、() へのポインターの配列として、 **`:::no-loc(char):::`** `:::no-loc(char)::: *:::no-loc(envp):::[]` または () へのポインターへのポインターとして宣言でき **`:::no-loc(char):::`** `:::no-loc(char)::: **:::no-loc(envp):::` ます。 プログラムがの代わりにを使用する場合は `:::no-loc(wmain):::` `:::no-loc(main):::` 、 **`:::no-loc(wchar_t):::`** の代わりにデータ型を使用し **`:::no-loc(char):::`** ます。 に渡される環境ブロックは、 `:::no-loc(main):::` `:::no-loc(wmain):::` 現在の環境の "固定" コピーです。 後でまたはへの呼び出しを使用して環境を変更した場合 `putenv` `_wputenv` 、現在の環境 (または、または変数によって返される `getenv` `_wgetenv` `_environ` `_wenviron` ) は変更されますが、が指すブロックは変更され :::no-loc(envp)::: ません。 環境処理の抑制については、「[コマンドライン処理のカスタマイズ](../cpp/customizing-cpp-command-line-processing.md)」を参照してください。 この引数は、C では ANSI 互換ですが、C++ では非互換です。

**Microsoft 固有の仕様はここまで**

### <a name="example"></a>例

次の例では、に、、の各引数を使用する方法を示し *:::no-loc(argc):::* *:::no-loc(argv):::* *:::no-loc(envp):::* `:::no-loc(main):::` ます。

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int :::no-loc(main):::( int :::no-loc(argc):::, :::no-loc(char)::: *:::no-loc(argv):::[], :::no-loc(char)::: *:::no-loc(envp):::[] ) {
    int iNumberLines = 0;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.

    if ( (:::no-loc(argc)::: == 2) && _stricmp( :::no-loc(argv):::[1], "/n" ) == 0 )
         iNumberLines = 1;

    // Walk through list of strings until a NULL is encountered.
    for( int i = 0; :::no-loc(envp):::[i] != NULL; ++i ) {
        if( iNumberLines )
            cout << i << ": " << :::no-loc(envp):::[i] << "\n";
    }
}
```

## <a name="parsing-c-command-line-arguments"></a>C++ コマンドライン引数の解析

**Microsoft 固有の仕様**

Microsoft C/C++ 起動コードは、オペレーティング システムのコマンド ラインで指定された引数を解釈する場合に、次の規則を使用します。

- 引数は、空白 (スペースまたはタブ) で区切ります。

- キャレット :::no-loc(char)::: (^) は、エスケープ :::no-loc(char)::: acter または区切り記号として認識されません。 :::no-loc(char):::Acter は、プログラムの配列に渡される前に、オペレーティングシステムのコマンドラインパーサーによって完全に処理され `:::no-loc(argv):::` ます。

- 二重引用符で囲まれた文字列 ("*string*") は、内に空白が含まれていなくても、単一の引数として解釈されます。 二重引用符で囲んだ文字列を引数に埋め込むこともできます。

- 円記号 (") を前に付けた二重引用符 \\ は、リテラル二重引用符 :::no-loc(char)::: acter (") として解釈されます。

- 二重引用符の直前にある円記号以外は、円記号 (\) として解釈されます。

- 二重引用符の直前に円記号が偶数個あると、円記号のペアごとに 1 個の円記号が `:::no-loc(argv):::` 配列に配置されます。この場合、二重引用符は文字列の区切り記号として解釈されます。

- 円記号の奇数の後に二重引用符が続く場合、円記号のペアごとに1つの円記号が配列に格納され `:::no-loc(argv):::` ます。二重引用符は、円記号の区切り記号によって "エスケープ" されます。これにより :::no-loc(main)::: 、リテラル二重引用符 (") がに配置され `:::no-loc(argv):::` ます。

### <a name="example"></a>例

次のプログラムは、コマンド ライン引数がどのように受け渡されるかを示します。

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int :::no-loc(main):::( int :::no-loc(argc):::,      // Number of strings in array :::no-loc(argv):::
          :::no-loc(char)::: *:::no-loc(argv):::[],   // Array of command-line argument strings
          :::no-loc(char)::: *:::no-loc(envp):::[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < :::no-loc(argc):::; count++ )
         cout << "  :::no-loc(argv):::[" << count << "]   "
                << :::no-loc(argv):::[count] << "\n";
}
```

次の表は、前の一覧の規則を示しながら、入力例と予想される出力を示しています。

### <a name="results-of-parsing-command-lines"></a>コマンドラインの解析結果

|コマンド ライン入力|:::no-loc(argv):::[1]|:::no-loc(argv):::[2]|:::no-loc(argv):::番|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**Microsoft 固有の仕様はここまで**

## <a name="wildcard-expansion"></a>ワイルドカードの展開

**Microsoft 固有の仕様**

コマンド ラインでファイル名とパスの引数を指定するときに、ワイルドカード (疑問符 (?) およびアスタリスク (*)) を使用できます。

コマンドライン引数は、(ワイド acter 環境では) と呼ばれるルーチンによって処理され `_set:::no-loc(argv):::` `_wset:::no-loc(argv):::` :::no-loc(char)::: ます。既定では、ワイルドカードは文字列配列内の個別の文字列に展開されません `:::no-loc(argv):::` 。 ワイルドカードの展開を有効にする方法の詳細については、「[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="customizing-c-command-line-processing"></a>C++ のコマンド ライン処理のカスタマイズ

**Microsoft 固有の仕様**

プログラムがコマンド ラインの引数を受け取らない場合は、コマンド ライン処理を実行するライブラリ ルーチンの使用を制約することで、領域を節約できます。 このルーチンは `_set:::no-loc(argv):::` 、「[ワイルドカードの展開](../cpp/wildcard-expansion.md)」で説明されています。 使用しないようにするには、関数を含むファイルで何も実行しないルーチンを定義 `:::no-loc(main):::` し、という名前を指定し `_set:::no-loc(argv):::` ます。 `_set:::no-loc(argv):::`の呼び出しがの定義によって満たされ、 `_set:::no-loc(argv):::` ライブラリのバージョンが読み込まれていません。

同様に、引数を使用して環境テーブルにアクセスしない場合は、 `:::no-loc(envp):::` 環境処理ルーチンの代わりに独自の空のルーチンを使用することができ `_set:::no-loc(envp):::` ます。 関数と同様に `_set:::no-loc(argv):::` 、は `_set:::no-loc(envp):::` ** :::no-loc(extern)::: "C"** として宣言する必要があります。

プログラムによって、 `spawn` C ランタイムライブラリのまたはルーチンのファミリが呼び出される場合があり `exec` ます。 存在する場合は、環境処理ルーチンを抑制しないでください。このルーチンは、親プロセスから子プロセスに環境を渡すために使用されるためです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[基本的な概念](../cpp/basic-concepts-cpp.md)
