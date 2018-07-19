---
title: -F (スタック サイズの設定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /f
dev_langs:
- C++
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed0ad03d18493cc5618f9aad2a16b07e4a01717f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373141"
---
# <a name="f-set-stack-size"></a>/F (スタック サイズの設定)
プログラムのスタック サイズをバイト単位で設定します。  
  
## <a name="syntax"></a>構文  
  
```  
/F number  
```  
  
## <a name="arguments"></a>引数  
 `number`  
 スタック サイズ (バイト単位)。  
  
## <a name="remarks"></a>コメント  
 このオプションを指定せず、スタック サイズは 1 MB に既定値です。 `number` 10 進数または C 言語表記で引数を指定できます。 引数の範囲は 1 からリンカーによって受け付け最大スタック サイズです。 リンカーは、最も近い 4 バイトに指定した値を丸めます。 間の空白 **/F**と`number`は省略可能です。  
  
 スタック オーバーフローのメッセージが返された場合にスタック サイズを大きく必要があります。  
  
 スタック サイズを設定することもできます。  
  
-   使用して、 **/stack**リンカー オプション。 詳細については、次を参照してください。 [/stack](../../build/reference/stack.md)です。  
  
-   .Exe ファイルを EDITBIN を使用します。 詳細については、次を参照してください。 [EDITBIN リファレンス](../../build/reference/editbin-reference.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)