---
title: MFC DLL プロジェクトの作成
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcdll.project
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
ms.openlocfilehash: 44671985b2ab22e866a63b284a4b22d87b614667
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446752"
---
# <a name="creating-an-mfc-dll-project"></a>MFC DLL プロジェクトの作成

MFC DLL とは、複数のアプリケーションで同時に利用できる関数の共有ライブラリとして機能する、バイナリ ファイルです。 MFC DLL プロジェクトを作成する最も簡単な方法は、MFC DLL ウィザードを使用する方法です。

> [!NOTE]
>  IDE に表示される機能は、有効にされている設定やエディションに依存し、ヘルプに記載されている内容とは異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>MFC DLL ウィザードを使用して MFC DLL プロジェクトを作成するには

1. ヘルプ トピックの指示に従って[C++ コンソール アプリ プロジェクトを作成](../../get-started/tutorial-console-cpp.md)です。

**注**で、**新しいプロジェクト**ダイアログ ボックスで、 `MFC DLL` MFC DLL ウィザードを開く [テンプレート] ペインでアイコン。

1. 使用して、アプリケーションの設定を定義、[アプリケーション設定](../../mfc/reference/application-settings-mfc-dll-wizard.md)のページ、 [MFC DLL ウィザード](../../mfc/reference/mfc-dll-wizard.md)します。

    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。

1. をクリックして**完了**をで新しいプロジェクトを開き、ウィザードを閉じて**ソリューション エクスプ ローラー**します。

作成されたファイルを表示するには、プロジェクトが作成されると、**ソリューション エクスプ ローラー**します。 ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。 ファイルの種類についての詳細については、次を参照してください。 [Visual に対して作成されるファイルの種類C++プロジェクト](../../build/reference/file-types-created-for-visual-cpp-projects.md)します。

## <a name="see-also"></a>関連項目

[C++Visual Studio でプロジェクトの種類](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[プロパティ ページ](../../build/reference/property-pages-visual-cpp.md)

