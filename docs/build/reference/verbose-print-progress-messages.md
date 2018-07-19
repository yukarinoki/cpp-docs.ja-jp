---
title: -詳細 (進行状況メッセージを印刷) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
dev_langs:
- C++
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee1bf99cdf27e432bf8bdf6b7c0e48a84aeaac21
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377470"
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (進行状況メッセージの出力)
```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## <a name="remarks"></a>コメント  
 リンカーが、リンク セッションへの進行状況に関する情報を送信、**出力**ウィンドウです。 コマンド ラインでリンクを実行すると、この情報は標準出力に送られるため、ファイルにリダイレクトできます。  
  
|オプション|説明|  
|------------|-----------------|  
|/VERBOSE|リンク プロセスに関する詳細情報を表示します。|  
|/VERBOSE:ICF|使用に起因するリンカー動作についての情報を表示[/OPT:ICF](../../build/reference/opt-optimizations.md)です。|  
|/VERBOSE:INCR|インクリメンタル リンク プロセスに関する情報を表示します。|  
|/VERBOSE:LIB|検索されたライブラリだけを示す進行状況メッセージを表示します。<br /><br /> 表示される情報は、ライブラリ検索の進行状況、各ライブラリとオブジェクト名 (完全パス)、そのライブラリで解決されたシンボル、およびそのシンボルを参照しているオブジェクトの一覧です。|  
|/VERBOSE:REF|使用に起因するリンカー動作についての情報が表示されます[/opt:ref による](../../build/reference/opt-optimizations.md)です。|  
|/VERBOSE:SAFESEH|安全な例外処理時に互換性がないモジュールに関する情報を表示[/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)が指定されていません。|  
|/VERBOSE:UNUSEDLIBS|イメージの作成時に使用されていないライブラリ ファイルに関する情報を表示します。|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**リンカー**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  追加するには、オプション、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)