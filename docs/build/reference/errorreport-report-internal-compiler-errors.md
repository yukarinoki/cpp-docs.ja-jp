---
title: -errorreport (内部コンパイラ エラーの報告) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
- /errorreport
dev_langs:
- C++
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67e87143d31de98039f5d679c102a5815dd87abb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377249"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (内部コンパイラ エラーの報告)
内部コンパイル エラー (ICE) 情報を Microsoft に直接報告できます。  
  
## <a name="syntax"></a>構文  
  
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## <a name="arguments"></a>引数  
 **none**  
 内部コンパイラ エラーに関するレポートは、収集されず、マイクロソフトに送信されません。  
  
 **prompt**  
 内部コンパイラ エラーを受信したときにレポートを送信するかどうか確認するメッセージを表示します。 **プロンプト**開発環境でアプリケーションのコンパイル時に既定値です。  
  
 **queue**  
 エラー レポートを待ち行列に入れます。 管理者特権使用してログインするときに、ウィンドウが表示され、前回のログに記録されたエラーを報告する (いない求められます 3 日間に 2 回以上のエラー レポートを送信する)。 **キュー**コマンド プロンプトで、アプリケーションのコンパイル時に既定値です。  
  
 **send**  
 自動的にシステムの Windows エラー報告設定によってレポートが有効になっている場合は、Microsoft に内部コンパイラ エラー レポートを送信します。  
  
## <a name="remarks"></a>コメント  
 コンパイラがソース コード ファイルを処理できないと、内部コンパイラ エラー (ICE: Internal Compiler Error) が発生します。 ICE が発生した場合、コードの修正に利用できる出力ファイルや診断は生成されません。  
  
 以前のリリースでは、ICE が発生する場合は、問題を報告するマイクロソフト製品サポート サービスを呼び出すことをお勧めしていました。 **/ErrorReport**Microsoft に直接 ICE 情報を提供できます。 エラー レポートは、今後リリースされるコンパイラの機能向上に役立ちます。  
  
 コンピューターまたはユーザー ポリシーによるアクセス許可によっては、レポートを送信できない場合があります。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**詳細**プロパティ ページ。  
  
4.  変更、**エラー報告**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)