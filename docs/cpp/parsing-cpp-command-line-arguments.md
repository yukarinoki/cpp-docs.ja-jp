---
title: C++ コマンド ライン引数の解析
ms.date: 11/04/2016
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- command line [C++], parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
ms.openlocfilehash: 53873fa9340253ab5e8459eb442385641246f930
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471033"
---
# <a name="parsing-c-command-line-arguments"></a>C++ コマンド ライン引数の解析

**Microsoft 固有の仕様**

Microsoft C/C++ 起動コードは、オペレーティング システムのコマンド ラインで指定された引数を解釈する場合に、次の規則を使用します。

- 引数は、空白 (スペースまたはタブ) で区切ります。

- キャレット (^) は、エスケープ文字やデリミターとしては認識されません。 文字は、プログラムの `argv` 配列に渡される前に、オペレーティング システムのコマンド ライン パーサーによって完全に処理されます。

- 二重引用符で囲まれた文字列 ("*文字列*") に含まれる空白文字に関係なく、1 つの引数として解釈されます。 二重引用符で囲んだ文字列を引数に埋め込むこともできます。

- 円記号を前に付けた二重引用符 (\\") は、リテラル二重引用符文字 (") として解釈されます。

- 二重引用符の直前にある円記号以外は、円記号 (\\) として解釈されます。

- 二重引用符の直前に円記号が偶数個あると、円記号のペアごとに 1 個の円記号が `argv` 配列に配置されます。この場合、二重引用符は文字列の区切り記号として解釈されます。

- 二重引用符の直前に円記号が奇数個あると、円記号のペアごとに 1 個の円記号が `argv` 配列に配置されます。この場合、二重引用符は残った円記号によってエスケープされます。これにより、リテラル二重引用符 (") が `argv` に配置されます。

## <a name="example"></a>例

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

### <a name="results-of-parsing-command-lines"></a>コマンド ラインの解析結果

|コマンド ライン入力|argv[1]|argv[2]|argv[3]|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[main: プログラムの起動](../cpp/main-program-startup.md)