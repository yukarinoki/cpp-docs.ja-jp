---
title: -ERRORREPORT (内部リンカー エラーの報告) |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
dev_langs:
- C++
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72e620e5347d422a8de66cba3ea9cfd601bb3f29
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (内部リンカー エラーの報告)

> **/errorreport:**[ **none** | **プロンプト** | **キュー** | **送信**]

## <a name="arguments"></a>引数

**none**  
内部コンパイラ エラーに関するレポートは、収集されず、マイクロソフトに送信されません。

**prompt**  
内部コンパイラ エラーを受信したときにレポートを送信するかどうか確認するメッセージを表示します。 **プロンプト**開発環境でアプリケーションのコンパイル時に既定値です。

**queue**  
エラー レポートを待ち行列に入れます。 管理者特権使用してログインするときに、ウィンドウが表示され、前回のログに記録されたエラーを報告する (いない求められます 3 日間に 2 回以上のエラー レポートを送信する)。 **キュー**コマンド プロンプトで、アプリケーションのコンパイル時に既定値です。

**send**  
自動的に Windows エラー報告サービスの設定でレポートが有効になっている場合は、Microsoft に内部コンパイラ エラー レポートを送信します。

## <a name="remarks"></a>コメント

**/ERRORREPORT**オプションでは、Microsoft に直接内部コンパイラ エラー (ICE) 情報を提供することができます。

オプション **/errorreport:send** Windows エラー報告サービスの設定で有効になっている場合は、Microsoft にエラー情報を自動的に送信します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 開く、**構成プロパティ** > **リンカー** > **詳細**プロパティ ページ。

1. 変更、**エラー報告**プロパティです。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/errorReport (内部コンパイラ エラーの報告)](../../build/reference/errorreport-report-internal-compiler-errors.md)  
[リンカー オプションの設定](../../build/reference/setting-linker-options.md)  
[リンカー オプション](../../build/reference/linker-options.md)  
