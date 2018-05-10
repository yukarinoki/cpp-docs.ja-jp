---
title: -Gy (関数レベルのリンクの有効化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
dev_langs:
- C++
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36e939a12cf23a9d9e476b676a5b068889414497
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="gy-enable-function-level-linking"></a>/Gy (関数レベルのリンクの有効化)
コンパイラが個々の関数をパッケージ関数 (COMDAT) の形式でパッケージ化できるようになります。  
  
## <a name="syntax"></a>構文  
  
```  
/Gy[-]  
```  
  
## <a name="remarks"></a>コメント  
 リンカーは、関数が、除外したり、DLL ファイルまたは .exe ファイルの各関数の順序の Comdat として個別にパッケージ化することが必要です。  
  
 リンカー オプションを使用することができます[/OPT (最適化)](../../build/reference/opt-optimizations.md) .exe ファイルから参照されていないパッケージ化された関数を除外します。  
  
 リンカー オプションを使用することができます[/ORDER (配置の順序での関数)](../../build/reference/order-put-functions-in-order.md)に .exe ファイルで指定された順序でパッケージ化された関数を含めます。  
  
 インスタンスが呼び出される場合に、インライン関数が常にパッケージ化 (する場合に発生、たとえば、インライン展開がオフまたは関数のアドレスを取得する)。 さらに、クラス宣言で定義されている C++ メンバー関数は自動的にパッケージ化されます。その他の関数は使用できません、およびパッケージ化された関数としてコンパイルに必要なは、このオプションを選択します。  
  
> [!NOTE]
>  [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) 、エディット コンティニュを使用するオプションが自動的に設定、 **/Gy**オプション。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**コード生成**プロパティ ページ。  
  
4.  変更、**関数レベルのリンクを有効にする**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)