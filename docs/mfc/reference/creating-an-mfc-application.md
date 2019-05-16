---
title: MFC アプリケーションの作成
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: 0f16fe577f1dc02dc9a2fc0cffb5899b16ad8cca
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708231"
---
# <a name="creating-an-mfc-application"></a>MFC アプリケーションの作成

MFC アプリケーションは、MFC (Microsoft Foundation Class) ライブラリに基づく Windows 対応の実行可能なアプリケーションです。 MFC アプリケーションを作成する最も簡単な方法は、MFC アプリケーション ウィザードを使用する方法です。

> [!IMPORTANT]
>  MFC プロジェクトは、Visual Studio Express エディションではサポートされていません。

MFC の実行可能ファイルは通常 5 つの種類に分類されます。 標準の Windows アプリケーション、ダイアログ ボックス、フォーム ベースのアプリケーション、エクスプ ローラー スタイルのアプリケーションおよび Web ブラウザー スタイルのアプリケーション。 詳細については次を参照してください:

- [Windows アプリケーションを記述するクラスを使用します。](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [ダイアログ ボックスの作成と表示](../../mfc/creating-and-displaying-dialog-boxes.md)

- [フォーム ベースの MFC アプリケーションの作成](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [エクスプローラー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [Web ブラウザー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

MFC アプリケーション ウィザードでは、これらのアプリケーションのすべてに適したクラスやファイルが生成されます。作成されるクラスやファイルは、ウィザードで選択したオプションによって異なります。

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードを使用して MFC アプリケーションを作成するには

1. ヘルプ トピックの指示に従って[C++ コンソール アプリ プロジェクトを作成](../../get-started/tutorial-console-cpp.md)です。

1. **新しいプロジェクト**ダイアログ ボックスで、 **MFC アプリケーション**テンプレート ペイン、ウィザードを開きます。

1. 使用して、アプリケーションの設定を定義、 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)します。

    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。

1. クリックして**完了**ウィザードを終了し、開発環境で新しいプロジェクトを開きます。

作成されたファイルを表示するには、プロジェクトが作成されると、**ソリューション エクスプ ローラー**します。 ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。 ファイルの種類についての詳細については、次を参照してください。 [Visual Studio に対して作成されるファイルの種類C++プロジェクト](../../build/reference/file-types-created-for-visual-cpp-projects.md)します。

## <a name="see-also"></a>関連項目

[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[プロパティ ページ](../../build/reference/property-pages-visual-cpp.md)

