---
title: 引数の定義 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca012d7b391e011d9658b0b74e0f4433d5dc9fd4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="argument-definitions"></a>引数定義
次のプロトタイプで引数を指定します。  
  
```  
  
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);  
```  
  
 これにより、簡単にコマンド ラインの引数を解析し、オプションで環境変数にもアクセスできます。 引数の定義は、次のとおりです。  
  
 `argc`  
 これに続いて `argv` で渡される引数の数を格納した整数。 `argc` パラメーターは、必ず 1 以上になります。  
  
 `argv`  
 プログラムのユーザーが入力したコマンド ライン引数を表す、null で終了する文字列配列。 慣例により、 `argv` **[0]** 、プログラムが呼び出されますコマンドは、 `argv` **[1]** までは、最初のコマンドライン引数と、 `argv` **[**`argc`**]**、常に**NULL**です。 参照してください[コマンドライン処理のカスタマイズ](../cpp/customizing-cpp-command-line-processing.md)コマンドライン処理の抑制についてです。  
  
 最初のコマンドライン引数は、常に`argv` **[1]** 、最後の 1 つは`argv` **[** `argc` - 1 **]** です。  
  
> [!NOTE]
>  慣例では、`argv`**[0]** は、プログラムが起動されるコマンドです。  ただし、可能であればを使用して、プロセスの起動に[CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197)かつ両方の最初と 2 番目の引数を使用する場合 (`lpApplicationName`と`lpCommandLine`)、 `argv` **[0]** できない可能性があります、実行可能ファイル名です。使用して[GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197)実行可能ファイルの名前とその完全修飾パスを取得します。  
  
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `envp`  
 多くの Unix システムに共通の拡張機能である `envp` 配列は、Microsoft C++ で使用されます。 これは、ユーザーの環境で設定された変数を表す文字列の配列です。 この配列は終了、 **NULL**エントリです。 ポインターの配列として宣言されている**char (char** \*envp **)** またはへのポインターへのポインターとして**char (char** \* \*envp **)** です。 プログラムで使用する場合**wmain**の代わりに**メイン**を使用して、`wchar_t`データ型の代わりに`char`です。 渡される環境ブロック**メイン**と**wmain** "凍結された"現在の環境のコピーです。 呼び出しによって環境を後で変更する場合**putenv**または`_wputenv`、現在の環境 (によって返される`getenv` / `_wgetenv`と`_environ` /  `_wenviron`変数) は変わりますが、envp がポイントするブロックは変更されません。 参照してください[コマンドライン処理のカスタマイズ](../cpp/customizing-cpp-command-line-processing.md)環境処理の抑制についてです。 この引数は、C では ANSI 互換ですが、C++ では非互換です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="example"></a>例  
 次の例を使用する方法を示しています、 `argc`、 `argv`、および`envp`引数**メイン**:  
  
```  
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
  
## <a name="see-also"></a>関連項目  
 [main: プログラムの起動](../cpp/main-program-startup.md)