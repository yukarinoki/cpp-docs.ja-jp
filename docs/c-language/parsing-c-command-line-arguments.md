---
title: C コマンド ライン引数の解析 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- command line, parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c7d4c0a1a5afc7c43b601f048d14b4bc9619b08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065726"
---
# <a name="parsing-c-command-line-arguments"></a>C コマンド ライン引数の解析

**Microsoft 固有の仕様**

Microsoft C スタートアップ コードは、オペレーティング システムのコマンド ラインで指定された引数を解釈する場合に、次の規則を使用します。

- 引数は、空白 (スペースまたはタブ) で区切ります。

- 二重引用符で囲まれた文字列は、空白を含む場合でも、単一の引数と見なされます。 二重引用符で囲んだ文字列を引数に埋め込むこともできます。 キャレット (**^**) は、エスケープ文字や区切り記号としては認識されません。

- 円記号を前に付けた二重引用符 (**\\"**) は、リテラル二重引用符文字 (**"**) として解釈されます。

- 二重引用符の直前にある円記号以外は、円記号 (\) として解釈されます。

- 二重引用符の直前に円記号が偶数個あると、円記号のペア (**\\\\**) ごとに 1 個の円記号 (**\\**) が `argv` 配列に配置されます。この場合、二重引用符 (**"**) は文字列の区切り記号として解釈されます。

- 二重引用符の直前に円記号が奇数個 (3 個以上) あると、円記号のペア (**\\\\**) ごとに 1 個の円記号 (**\\**) が `argv` 配列に格納されます。この場合、二重引用符は残った円記号によりエスケープ シーケンスと見なされます。これにより、リテラル二重引用符 (**"**) が `argv` に追加されます。

この一覧では、コマンド ライン引数のいくつかの例で `argv` に渡される解釈された結果を示して、上記の規則について説明しています。 2 番目、3 番目、および 4 番目の列に表示される出力は、一覧に続く ARGS.C のプログラムからのものです。

|コマンド ライン入力|argv[1]|argv[2]|argv[3]|
|-------------------------|---------------|---------------|---------------|
|`"a b c" d e`|`a b c`|`d`|`e`|
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

## <a name="example"></a>例

### <a name="code"></a>コード

```
// Parsing_C_Commandline_args.c
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

## <a name="see-also"></a>参照

[main 関数とプログラム実行](../c-language/main-function-and-program-execution.md)