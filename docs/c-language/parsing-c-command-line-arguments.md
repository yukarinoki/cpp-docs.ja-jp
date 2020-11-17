---
title: C コマンド ライン引数の解析
description: argv パラメーターと argc パラメーターを作成するために Microsoft C ランタイムのスタートアップ コードによってコマンド ライン引数が解釈される方法について説明します。
ms.date: 11/09/2020
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- double quote marks
- command line, parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
ms.openlocfilehash: 92921e91ee6bb37b2bf7b702a1b31ed045187b59
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441256"
---
# <a name="parsing-c-command-line-arguments"></a>C コマンド ライン引数の解析

**Microsoft 固有の仕様**

Microsoft C スタートアップ コードは、オペレーティング システムのコマンド ラインで指定された引数を解釈する場合に、次の規則を使用します。

- 引数は、空白 (スペースまたはタブ) で区切ります。

- 最初の引数 (`argv[0]`) は、特別に処理されます。 それはプログラム名を表します。 有効なパス名である必要があるため、一部分を二重引用符 ( **`"`** ) で囲むことが許可されます。 二重引用符は、`argv[0]` の出力には含まれません。 二重引用符で囲まれた部分については、スペース文字またはタブ文字が引数の末尾として解釈されません。 この一覧で後に示す規則は適用されません。

- 二重引用符で囲まれた文字列は、空白が含まれているかどうかにかかわらず、1 つの引数として解釈されます。 二重引用符で囲んだ文字列を引数に埋め込むこともできます。 キャレット ( **`^`** ) は、エスケープ文字または区切り記号として認識されません。 引用符で囲まれた文字列内では、二重引用符のペアは単一のエスケープされた二重引用符として解釈されます。 終了の二重引用符が検出される前にコマンド ラインが終了した場合は、それまでに読み取られたすべての文字が最後の引数として出力されます。

- 円記号を前に付けた二重引用符 ( **`\"`** ) は、リテラルの二重引用符文字 ( **`"`** ) として解釈されます。

- 二重引用符の直前にある円記号以外は、円記号として文字どおり解釈されます。

- 二重引用符の直前に円記号が偶数個あると、円記号のペア ( **`\\`** ) ごとに 1 個の円記号 ( **`\`** ) が `argv` 配列に配置されます。この場合、二重引用符 ( **`"`** ) は文字列の区切り記号として解釈されます。

- 奇数個の円記号の後に二重引用符がある場合は、円記号のペア ( **`\\`** ) ごとに 1 個の円記号 ( **`\`** ) が `argv` 配列に配置されます。 二重引用符は残りの円記号によってエスケープ シーケンスとして解釈され、リテラルの二重引用符 ( **`"`** ) が `argv` に配置されます。

この一覧では、コマンド ライン引数のいくつかの例で `argv` に渡される解釈された結果を示して、上記の規則について説明しています。 2 番目、3 番目、および 4 番目の列に表示される出力は、一覧に続く ARGS.C のプログラムからのものです。

|コマンド ライン入力|argv[1]|argv[2]|argv[3]|
|-------------------------|---------------|---------------|---------------|
|`"a b c" d e`|`a b c`|`d`|`e`|
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|
|`a"b"" c d`|`ab" c d`|||

## <a name="example"></a>例

### <a name="code"></a>コード

```c
// ARGS.C illustrates the following variables used for accessing
// command-line arguments and environment variables:
// argc  argv  envp
//

#include <stdio.h>

int main( int argc, // Number of strings in array argv
char *argv[],      // Array of command-line argument strings
char **envp )      // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    printf_s( "\nCommand-line arguments:\n" );
    for( count = 0; count < argc; count++ )
        printf_s( "  argv[%d]   %s\n", count, argv[count] );

    // Display each environment variable.
    printf_s( "\nEnvironment variables:\n" );
    while( *envp != NULL )
        printf_s( "  %s\n", *(envp++) );

    return;
}
```

## <a name="comments"></a>コメント

このプログラムからの出力の例は次のとおりです。

```
Command-line arguments:
  argv[0]   C:\MSC\TEST.EXE

Environment variables:
  COMSPEC=C:\NT\SYSTEM32\CMD.EXE

  PATH=c:\nt;c:\binb;c:\binr;c:\nt\system32;c:\word;c:\help;c:\msc;c:\;
  PROMPT=[$p]
  TEMP=c:\tmp
  TMP=c:\tmp
  EDITORS=c:\binr
  WINDIR=c:\nt
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[main 関数とプログラム実行](../c-language/main-function-and-program-execution.md)
