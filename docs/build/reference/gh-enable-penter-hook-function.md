---
title: -Gh (_penter フック関数の有効化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _penter
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68497e4e760e1268a0175d5a68452678153896b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373154"
---
# <a name="gh-enable-penter-hook-function"></a>/Gh (_penter フック関数の有効化)
呼び出しにより、`_penter`すべてのメソッドまたは関数の開始時の関数。  
  
## <a name="syntax"></a>構文  
  
```  
/Gh  
```  
  
## <a name="remarks"></a>コメント  
 `_penter`関数は、任意のライブラリの一部ではないの定義を指定するかどうかは`_penter`します。  
  
 明示的に呼び出す予定がない限り`_penter`プロトタイプを提供する必要はありません。 関数は、する必要がありますとして記述があった次のプロトタイプでは、エントリのすべてのレジスタのコンテンツをプッシュおよび終了時に変更されていないコンテンツを表示する必要があります。  
  
```  
void __declspec(naked) _cdecl _penter( void );  
```  
  
 この宣言は、64 ビット プロジェクトで使用可能ではありません。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコードをコンパイルしたときに **/Gh**を示して 方法`_penter`を 2 回呼び出す関数に入るときに 1 回`main`関数に入るときに 1 回`x`です。  
  
```  
// Gh_compiler_option.cpp  
// compile with: /Gh  
// processor: x86  
#include <stdio.h>  
void x() {}  
  
int main() {  
   x();  
}  
  
extern "C" void __declspec(naked) _cdecl _penter( void ) {  
   _asm {  
      push eax  
      push ebx  
      push ecx  
      push edx  
      push ebp  
      push edi  
      push esi  
    }  
  
   printf_s("\nIn a function!");  
  
   _asm {  
      pop esi  
      pop edi  
      pop ebp  
      pop edx  
      pop ecx  
      pop ebx  
      pop eax  
      ret  
    }  
}  
```  
  
```Output  
In a function!  
In a function!  
```  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)