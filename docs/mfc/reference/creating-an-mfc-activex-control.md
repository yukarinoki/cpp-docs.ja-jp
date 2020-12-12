---
description: '詳細情報: MFC ActiveX コントロールの作成'
title: MFC ActiveX コントロールの作成
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: 4b35187ffa3e5e4a11d293d4fe202c6e04213664
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301257"
---
# <a name="creating-an-mfc-activex-control"></a>MFC ActiveX コントロールの作成

ActiveX コントロール プログラムは、親アプリケーションに特定の機能を提供するモジュール プログラムです。 たとえば、ダイアログ ボックスのボタンや Web ページのツール バーなどのコントロールを作成できます。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 詳細については、「 [ActiveX コントロール](../activex-controls.md)」を参照してください。

MFC activex コントロールを作成する最も簡単な方法は、 [Mfc Activex コントロールウィザード](../../mfc/reference/mfc-activex-control-wizard.md)を使用することです。

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>MFC ActiveX コントロール ウィザードを使用して MFC ActiveX コントロールを作成するには

1. ヘルプトピック「 [Mfc アプリケーションの作成](creating-an-mfc-application.md) 」の手順に従いますが、使用可能なテンプレートの一覧から [ **mfc ActiveX コントロール** ] を選択します。

1. MFC ActiveX コントロールウィザードを使用して、 [アプリケーションの設定](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)、 [コントロール名](../../mfc/reference/control-names-mfc-activex-control-wizard.md)、および [コントロールの設定](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) を定義します。

    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。

1. **[完了]** をクリックしてウィザードを閉じ、新しいプロジェクトを開発環境で開きます。

プロジェクトを作成した後、 **ソリューションエクスプローラー** で作成されたファイルを表示できます。 ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。 ファイルの種類の詳細については、「[Visual Studio の C++ プロジェクトに対して作成されるファイルの種類](../../build/reference/file-types-created-for-visual-cpp-projects.md)」を参照してください。

プロジェクトを作成したら、コードウィザードを使用して、 [関数](../../ide/adding-a-member-function-visual-cpp.md#add-member-function-wizard)、 [変数](../../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard)、 [イベント](../../ide/adding-an-event-visual-cpp.md#add-event-wizard)、 [プロパティ](../../ide/adding-a-property-visual-cpp.md#names-add-property-wizard)、および [メソッド](../../ide/adding-a-method-visual-cpp.md#add-method-wizard)を追加できます。 ActiveX コントロールのカスタマイズの詳細については、「 [MFC Activex コントロール](../../mfc/mfc-activex-controls.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[[プロパティ ページ]](../../build/reference/property-pages-visual-cpp.md)
