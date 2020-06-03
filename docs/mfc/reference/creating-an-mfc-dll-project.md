---
title: MFC DLL プロジェクトの作成
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.mfcdll.project
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
ms.openlocfilehash: 6367b2a4b85b2c586c5a4420a8be1f80d334b2e4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363961"
---
# <a name="creating-an-mfc-dll-project"></a>MFC DLL プロジェクトの作成

MFC DLL とは、複数のアプリケーションで同時に利用できる関数の共有ライブラリとして機能する、バイナリ ファイルです。 MFC DLL プロジェクトを作成する最も簡単な方法は、MFC DLL ウィザードを使用する方法です。

> [!NOTE]
> IDE に表示される機能は、有効にされている設定やエディションに依存し、ヘルプに記載されている内容とは異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** を選択してください。 詳細については、「 [IDE の個人用設定](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>MFC DLL ウィザードを使用して MFC DLL プロジェクトを作成するには

1. MFC アプリケーションの作成に関[する](creating-an-mfc-application.md)ヘルプ トピックの指示に従って、使用可能なテンプレートの一覧から**MFC ダイナミック リンク ライブラリ**または MFC **DLL**を選択します。

1. [MFC DLL ウィザード](../../mfc/reference/mfc-dll-wizard.md)の[アプリケーション設定](../../mfc/reference/application-settings-mfc-dll-wizard.md)ページを使用してアプリケーション設定を定義します。

    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。

1. [**完了] を**クリックしてウィザードを閉じ、**新**しいプロジェクトをソリューション エクスプローラで開きます。

プロジェクトを作成したら、**ソリューション エクスプローラー**で、作成したファイルを表示できます。 ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。 ファイルの種類の詳細については、「[Visual Studio の C++ プロジェクトに対して作成されるファイルの種類](../../build/reference/file-types-created-for-visual-cpp-projects.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Visual Studio の C++ プロジェクトの種類](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[プロパティ ページ](../../build/reference/property-pages-visual-cpp.md)
