---
title: 引数定義 |Microsoft Docs
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
ms.openlocfilehash: 4a401caad212978372bcb02b412fa8a9648b7170
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943970"
---
# <a name="argument-definitions"></a>引数定義
次のプロトタイプで引数を指定します。  
  
```cpp 
  
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);  
```  
  
 これにより、簡単にコマンド ラインの引数を解析し、オプションで環境変数にもアクセスできます。 引数の定義は、次のとおりです。  
  
 *argc*  
 続く引数の数を格納する整数*argv*します。 *Argc*パラメーターが常に 1 以上です。  
  
 *argv*  
 プログラムのユーザーが入力したコマンド ライン引数を表す、null で終了する文字列配列。 慣例により、 `argv` **[0]** 、プログラムが起動されるコマンドは、 `argv` **[1]** までは、最初のコマンドライン引数と、 `argv` **[**`argc`**]** は常に NULL にします。 参照してください[コマンドライン処理のカスタマイズ](../cpp/customizing-cpp-command-line-processing.md)コマンドライン処理の抑制について。  
  
 最初のコマンドライン引数は常に`argv` **[1]** 、最後の 1 つは`argv` **[** `argc` - 1 **]** します。  
  
> [!NOTE]
>  慣例では、`argv`**[0]** は、プログラムが起動されるコマンドです。  ただしを使用してプロセスを起動することは[CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197)最初と 2 つ目の両方の引数を使用する場合 (`lpApplicationName`と`lpCommandLine`)、 `argv` **[0]** できない可能性があります、実行可能ファイル名。使用して、 [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197)実行可能ファイルの名前とその完全修飾パスを取得します。  
  
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 *envp*  
 *Envp* Microsoft C では、共通の拡張機能は、多くの UNIX システムでは、配列が使用されます。 これは、ユーザーの環境で設定された変数を表す文字列の配列です。 この配列は NULL エントリで終了します。 ポインターの配列として宣言できます**char (char** \*envp **)** またはへのポインターへのポインターとして**char (char** \* \*envp **)** します。 プログラムで使用する場合**wmain**の代わりに**メイン**を使用して、 **wchar_t**データ型の代わりに**char**します。 渡される環境ブロック**メイン**と**wmain** 「固定の」現在の環境のコピーです。 その後の呼び出しによって環境を変更した場合**putenv**または`_wputenv`、現在の環境 (によって返される`getenv` / `_wgetenv`と`_environ` /  `_wenviron`変数) は、変更が、envp が指すブロックは変更されません。 参照してください[コマンドライン処理のカスタマイズ](../cpp/customizing-cpp-command-line-processing.md)環境処理の抑制について。 この引数は、C では ANSI 互換ですが、C++ では非互換です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="example"></a>例  
 次の例は、使用する方法を示します、 *argc*、 *argv*、および*envp*引数**メイン**:  
  
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
  
## <a name="see-also"></a>関連項目  
 [main: プログラムの起動](../cpp/main-program-startup.md)