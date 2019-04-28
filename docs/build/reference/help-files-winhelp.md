---
title: ヘルプ ファイル (WinHelp)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
ms.openlocfilehash: 376d9faa87868cce842a1cb70273e220ff691fa4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270199"
---
# <a name="help-files-winhelp"></a>ヘルプ ファイル (WinHelp)

MFC アプリケーション ウィザードの [[高度な機能]](../../mfc/reference/advanced-features-mfc-application-wizard.md) ページで **[ポップ ヒント]** チェック ボックスをオンにしてから **[WinHelp format]\(WinHelp 形式\)** を選択して、アプリケーションに WinHelp 形式のヘルプ サポートを追加すると、以下のファイルが作成されます。

|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hpj|*Projname*\hlp|ソース ファイル|プログラムまたはコントロールのヘルプ ファイルを作成するためにヘルプ コンパイラで使用されるヘルプ プロジェクト ファイルです。|
|*Projname*.rtf|*Projname*\hlp|ヘルプ ファイル|編集可能なテンプレート トピックと、.hpj ファイルのカスタマイズに関する情報が含まれます。|
|*Projname*.cnt|*Projname*\hlp|ヘルプ ファイル|Windows ヘルプの **[目次]** ウィンドウの構造を定義します。|
|Makehelp.bat|*Projname*|ソース ファイル|プロジェクトのコンパイル時に、ヘルプ プロジェクトをビルドするためにシステムで使用します。|
|Print.rtf|*Projname*\hlp|ヘルプ ファイル|プロジェクトで印刷をサポートする場合 (既定値) に作成されるファイルです。 印刷コマンドとダイアログ ボックスが記述されています。|
|*.bmp|*Projname*\hlp|リソース ファイル (Visual Studio)|生成された別のヘルプ ファイル トピックのイメージが含まれています。|

MFC ActiveX コントロール プロジェクトに WinHelp サポートを追加するには、MFC ActiveX コントロール ウィザードの [[アプリケーションの設定]](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) タブで **[Generate help files]\(ヘルプ ファイルの生成\)** を選択します。 MFC ActiveX コントロールにヘルプ サポートを追加すると、プロジェクトに以下のファイルが追加されます。

|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hpj|*Projname*\hlp|ソース ファイル|プログラムまたはコントロールのヘルプ ファイルを作成するためにヘルプ コンパイラで使用されるプロジェクト ファイルです。|
|*Projname*.rtf|*Projname*\hlp|プロジェクト|編集可能なテンプレート トピックと、.hpj ファイルのカスタマイズに関する情報が含まれます。|
|Makehelp.bat|*Projname*|ソース ファイル|プロジェクトのコンパイル時に、ヘルプ プロジェクトをビルドするためにシステムで使用します。|
|Bullet.bmp|*Projname*|リソース ファイル (Visual Studio)|箇条書きを表すために標準のヘルプ ファイル トピックで使用されます。|

## <a name="see-also"></a>関連項目

[Visual C++ プロジェクトに対して作成されるファイルの種類](file-types-created-for-visual-cpp-projects.md)
