---
title: ヘルプ ファイル (WinHelp)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
ms.openlocfilehash: 142702699523633bf810d0077ce7ba6355557d21
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496303"
---
# <a name="help-files-winhelp"></a>ヘルプ ファイル (WinHelp)

MFC アプリケーション ウィザードの [[高度な機能]](../mfc/reference/advanced-features-mfc-application-wizard.md) ページで **[ポップ ヒント]** チェック ボックスをオンにしてから **[WinHelp format]\(WinHelp 形式\)** を選択して、アプリケーションに WinHelp 形式のヘルプ サポートを追加すると、以下のファイルが作成されます。

|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hpj|*Projname*\hlp|ソース ファイル|プログラムまたはコントロールのヘルプ ファイルを作成するためにヘルプ コンパイラで使用されるヘルプ プロジェクト ファイルです。|
|*Projname*.rtf|*Projname*\hlp|ヘルプ ファイル|編集可能なテンプレート トピックと、.hpj ファイルのカスタマイズに関する情報が含まれます。|
|*Projname*.cnt|*Projname*\hlp|ヘルプ ファイル|Windows ヘルプの **[目次]** ウィンドウの構造を定義します。|
|Makehelp.bat|*Projname*|ソース ファイル|プロジェクトのコンパイル時に、ヘルプ プロジェクトをビルドするためにシステムで使用します。|
|Print.rtf|*Projname*\hlp|ヘルプ ファイル|プロジェクトで印刷をサポートする場合 (既定値) に作成されるファイルです。 印刷コマンドとダイアログ ボックスが記述されています。|
|*.bmp|*Projname*\hlp|リソース ファイル (Visual Studio)|生成された別のヘルプ ファイル トピックのイメージが含まれています。|

MFC ActiveX コントロール プロジェクトに WinHelp サポートを追加するには、MFC ActiveX コントロール ウィザードの [[アプリケーションの設定]](../mfc/reference/application-settings-mfc-activex-control-wizard.md) タブで **[Generate help files]\(ヘルプ ファイルの生成\)** を選択します。 MFC ActiveX コントロールにヘルプ サポートを追加すると、プロジェクトに以下のファイルが追加されます。

|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hpj|*Projname*\hlp|ソース ファイル|プログラムまたはコントロールのヘルプ ファイルを作成するためにヘルプ コンパイラで使用されるプロジェクト ファイルです。|
|*Projname*.rtf|*Projname*\hlp|プロジェクト|編集可能なテンプレート トピックと、.hpj ファイルのカスタマイズに関する情報が含まれます。|
|Makehelp.bat|*Projname*|ソース ファイル|プロジェクトのコンパイル時に、ヘルプ プロジェクトをビルドするためにシステムで使用します。|
|Bullet.bmp|*Projname*|リソース ファイル (Visual Studio)|箇条書きを表すために標準のヘルプ ファイル トピックで使用されます。|

## <a name="see-also"></a>参照

[Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)