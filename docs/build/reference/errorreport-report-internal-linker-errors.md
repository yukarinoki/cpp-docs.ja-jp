---
title: /ERRORREPORT (内部リンカー エラーの報告)
ms.date: 12/28/2017
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
ms.openlocfilehash: 26cc157cb7247a3a2ea7c10b415df1160540c9ad
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818025"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (内部リンカー エラーの報告)

> **/errorreport:**[ **none** | **prompt** | **queue** | **send** ]

## <a name="arguments"></a>引数

**none**<br/>
内部コンパイラ エラーに関するレポートは、収集されず、マイクロソフトに送信されません。

**prompt**<br/>
内部コンパイラ エラーを受信したときにレポートを送信するかどうか確認するメッセージを表示します。 **プロンプト**開発環境でアプリケーションのコンパイル時に既定値です。

**queue**<br/>
エラー レポートを待ち行列に入れます。 管理者特権を使用してログインすると、前回のログに記録されたエラーを報告できるように、ウィンドウが表示されます。 (ことが求められない 3 日間に 2 回以上のエラー レポートを送信する)。 **キュー**コマンド プロンプトで、アプリケーションのコンパイル時に既定値です。

**send**<br/>
自動的に Windows エラー報告サービスの設定でレポートが有効になっている場合は、内部コンパイラ エラーのレポートを Microsoft に送信します。

## <a name="remarks"></a>Remarks

**/ERRORREPORT**オプションを使用して、内部コンパイラ エラー (ICE) 情報を Microsoft に直接提供できます。

オプション **/errorreport:send** Windows エラー報告サービスの設定を有効になっている場合は、Microsoft にエラー情報を自動的に送信します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 開く、**構成プロパティ** > **リンカー** > **詳細**プロパティ ページ。

1. 変更、**エラー報告**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>

## <a name="see-also"></a>関連項目

[/errorReport (内部コンパイラ エラーの報告)](errorreport-report-internal-compiler-errors.md)<br/>
[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
