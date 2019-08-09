---
title: MFC アプリケーションの作成
ms.date: 07/28/2019
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: 454a994da6db2841317d41ea1cdacfd36b0705e4
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606472"
---
# <a name="creating-an-mfc-application"></a>MFC アプリケーションの作成

MFC アプリケーションは、MFC (Microsoft Foundation Class) ライブラリに基づく Windows 対応の実行可能なアプリケーションです。 MFC アプリケーションを作成する最も簡単な方法は、MFC アプリケーションウィザード (Visual Studio 2019 の**Mfc アプリプロジェクト**) を使用することです。 MFC コンソールアプリケーションを作成するには、Windows デスクトップウィザードを使用して、 **[コンソールアプリケーション]** オプションと **[MFC ヘッダー]** オプションを選択します。

> [!IMPORTANT]
>  MFC プロジェクトは、Visual Studio Express エディションではサポートされていません。

MFC の実行可能ファイルは、一般に、標準の Windows アプリケーション、ダイアログボックス、フォームベースのアプリケーション、エクスプローラースタイルのアプリケーション、および Web ブラウザースタイルのアプリケーションの5種類に分類されます。 詳細については次を参照してください:

- [クラスを使用した Windows アプリケーションの記述](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [ダイアログ ボックスの作成と表示](../../mfc/creating-and-displaying-dialog-boxes.md)

- [フォーム ベースの MFC アプリケーションの作成](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [エクスプローラー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [Web ブラウザー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

MFC アプリケーション ウィザードでは、これらのアプリケーションのすべてに適したクラスやファイルが生成されます。作成されるクラスやファイルは、ウィザードで選択したオプションによって異なります。

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードを使用して MFC アプリケーションを作成するには

1. ヘルプトピック「[コンソールアプリプロジェクトC++の作成](../../get-started/tutorial-console-cpp.md)」の手順に従います。

1. **新しいプロジェクト** ダイアログボックスで、テンプレート ペインの **MFC アプリケーション** をクリックしてウィザードを開きます。

1. [MFC アプリケーションウィザード](../../mfc/reference/mfc-application-wizard.md)を使用して、アプリケーションの設定を定義します。

    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。

1. **[完了]** をクリックしてウィザードを閉じ、新しいプロジェクトを開発環境で開きます。

プロジェクトを作成したら、**ソリューション エクスプローラー**で、作成したファイルを表示できます。 ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。 ファイルの種類の詳細については、「[Visual Studio の C++ プロジェクトに対して作成されるファイルの種類](../../build/reference/file-types-created-for-visual-cpp-projects.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[プロパティ ページ](../../build/reference/property-pages-visual-cpp.md)

