---
title: -errorreport (内部コンパイラ エラーの報告) |Microsoft Docs
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
ms.openlocfilehash: 0c96225e566593987bef8ec9a82c73daacfcefb6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720110"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (内部コンパイラ エラーの報告)

内部コンパイル エラー (ICE) 情報を Microsoft に直接報告できます。

## <a name="syntax"></a>構文

```
/errorReport:[ none | prompt | queue | send ]
```

## <a name="arguments"></a>引数

**none**<br/>
内部コンパイラ エラーに関するレポートは、収集されず、マイクロソフトに送信されません。

**prompt**<br/>
内部コンパイラ エラーを受信したときにレポートを送信するかどうか確認するメッセージを表示します。 **プロンプト**開発環境でアプリケーションのコンパイル時に既定値です。

**queue**<br/>
エラー レポートを待ち行列に入れます。 管理者特権を使用してログインすると、前回のログに記録されたエラーを報告できるように、ウィンドウが表示されます。 (ことが求められない 3 日間に 2 回以上のエラー レポートを送信する)。 **キュー**コマンド プロンプトで、アプリケーションのコンパイル時に既定値です。

**send**<br/>
自動的にシステムの Windows エラー報告設定によってレポートが有効になっている場合は、内部コンパイラ エラーのレポートを Microsoft に送信します。

## <a name="remarks"></a>Remarks

コンパイラがソース コード ファイルを処理できないと、内部コンパイラ エラー (ICE: Internal Compiler Error) が発生します。 ICE が発生した場合、コードの修正に利用できる出力ファイルや診断は生成されません。

以前のリリースでは、ICE が発生する場合は、問題を報告するマイクロソフト製品サポート サービスを呼び出すことをお勧めしていました。 **/ErrorReport**、ICE 情報を Microsoft に直接提供できます。 エラー レポートは、今後リリースされるコンパイラの機能向上に役立ちます。

コンピューターまたはユーザー ポリシーによるアクセス許可によっては、レポートを送信できない場合があります。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**詳細**プロパティ ページ。

1. 変更、**エラー報告**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)