---
title: 引数定義
ms.date: 11/04/2016
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
ms.openlocfilehash: aebd4800ad8d653d532708784ef0a5333211d46b
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857659"
---
# <a name="argument-definitions"></a>引数定義

次のプロトタイプで引数を指定します。

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

これにより、簡単にコマンド ラインの引数を解析し、オプションで環境変数にもアクセスできます。 引数の定義は、次のとおりです。

*argc*<br/>
*Argv*の後続の引数の数を含む整数。 *Argc*パラメーターには、常に1以上の値を指定します。

*argv*<br/>
プログラムのユーザーが入力したコマンド ライン引数を表す、null で終了する文字列配列。 慣例により、`argv[0]` はプログラムの呼び出しに使用するコマンド、`argv[1]` は最初のコマンドライン引数、`argv[argc]`までは常に NULL になります。 コマンドライン処理の抑制については、「[コマンドライン処理のカスタマイズ](../cpp/customizing-cpp-command-line-processing.md)」を参照してください。

最初のコマンド ライン引数は、必ず `argv[1]` となり、最後のコマンド ライン引数は、`argv[argc - 1]` になります。

> [!NOTE]
> 慣例により、`argv[0]` はプログラムが呼び出されるコマンドです。  ただし、 [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew)を使用してプロセスを生成することができます。また、1番目と2番目の引数 (*lpapplicationname*と`argv[0]` *lpapplicationname*) の両方を使用する場合、実行可能ファイル名にすることはできません。[GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) にを使用します。実行可能ファイル名とその完全修飾パスを取得する場合は。

**Microsoft 固有の仕様**

*envp*<br/>
多くの UNIX システムで共通する拡張機能である*envp*配列は、Microsoft C++で使用されています。 これは、ユーザーの環境で設定された変数を表す文字列の配列です。 この配列は NULL エントリで終了します。 **Char** (`char *envp[]`) へのポインターの配列として、または**char** (`char **envp`) へのポインターへのポインターとして宣言できます。 プログラムで `main`ではなく `wmain` を使用する場合は、 **char**ではなく**wchar_t**データ型を使用します。 `main` に渡される環境ブロックと `wmain` は、現在の環境の "固定" コピーです。 その後、`putenv` または `_wputenv`への呼び出しを使用して環境を変更すると、(`getenv` または `_wgetenv` によって返される) 現在の環境、および `_environ` 変数または `_wenviron` 変数) が変更されますが、envp が指すブロックは変更されません。 環境処理の抑制については、「[コマンドライン処理のカスタマイズ](../cpp/customizing-cpp-command-line-processing.md)」を参照してください。 この引数は、C では ANSI 互換ですが、C++ では非互換です。

**Microsoft 固有の仕様はここまで**

## <a name="example"></a>使用例

次の例は、 *argc*、 *argv*、および*envp*引数を使用して `main`する方法を示しています。

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

## <a name="see-also"></a>参照

[main: プログラムの起動](../cpp/main-program-startup.md)