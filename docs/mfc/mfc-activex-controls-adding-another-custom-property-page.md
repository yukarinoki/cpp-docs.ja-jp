---
description: '詳細については、「MFC ActiveX コントロール: 別のカスタムプロパティページの追加」を参照してください。'
title: 'MFC ActiveX コントロール : カスタム プロパティ ページの追加'
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
ms.openlocfilehash: 3802a32ed86536850e3a15ae9ce4bb53feb1ff1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203030"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX コントロール : カスタム プロパティ ページの追加

場合によっては、ActiveX コントロールのプロパティが、1つのプロパティページに適度に適合するよりも多くなることがあります。 この場合は、ActiveX コントロールにプロパティページを追加して、これらのプロパティを表示できます。

この記事では、既に少なくとも1つのプロパティページがある ActiveX コントロールに新しいプロパティページを追加する方法について説明します。 ストックプロパティページ (フォント、画像、または色) の追加の詳細については、「 [MFC ActiveX コントロール: ストックプロパティページの使用](mfc-activex-controls-using-stock-property-pages.md)」を参照してください。

次の手順では、ActiveX コントロールウィザードによって作成された ActiveX コントロールフレームワークのサンプルを使用します。 したがって、この例ではクラス名と識別子が一意です。

ActiveX コントロールでのプロパティページの使用の詳細については、次の記事を参照してください。

- [MFC ActiveX コントロール: プロパティページ](mfc-activex-controls-property-pages.md)

- [MFC ActiveX コントロール: ストックプロパティページの使用](mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  新しいプロパティページを ActiveX コントロールのプロパティページのサイズ標準に準拠させることを強くお勧めします。 Stock picture and color プロパティページは、250x62 dialog units (DLU) を測定します。 標準フォントプロパティページは 250x110 Dlu です。 ActiveX コントロールウィザードによって作成される既定のプロパティページでは、250x62 DLU 標準が使用されます。

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>新しいプロパティページテンプレートをプロジェクトに挿入するには

1. コントロールプロジェクトを開いた状態で、プロジェクトワークスペースでリソースビューを開きます。

1. リソースビューを右クリックしてショートカットメニューを開き、[ **リソースの追加**] をクリックします。

1. **ダイアログ** ノードを展開し、[ **IDD_OLE_PROPPAGE_SMALL**] を選択します。

1. [ **新規** ] をクリックして、リソースをプロジェクトに追加します。

1. [新しいプロパティページ] テンプレートを選択して、[ **プロパティ** ] ウィンドウ ( **リソースビュー**) を更新します。

1. **ID** プロパティの新しい値を入力します。 この例では、 **IDD_PROPPAGE_NEWPAGE** を使用します。

1. ツール バーの **[Save]\(保存\)** をクリックします。

### <a name="to-associate-the-new-template-with-a-class"></a>新しいテンプレートをクラスに関連付けるには

1. クラスビューを開きます。

1. クラスビューを右クリックして、ショートカットメニューを開きます。

1. ショートカット メニューの **[追加]** をクリックし、**[クラスの追加]** をクリックします。

   [クラスの [追加](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) ] ダイアログボックスが表示されます。

1. **MFC クラス** テンプレートをダブルクリックします。

1. [MFC クラスウィザード](reference/mfc-add-class-wizard.md)の [**クラス名**] ボックスに、新しいダイアログクラスの名前を入力します。 (この例では、 `CAddtlPropPage` )。

1. ファイル名を変更する場合は、[ **変更**] をクリックします。 実装ファイルとヘッダーファイルの名前を入力するか、既定の名前をそのまま使用します。

1. [ **基底クラス** ] ボックスで、を選択し `COlePropertyPage` ます。

1. [ **ダイアログ ID** ] ボックスで、[ **IDD_PROPPAGE_NEWPAGE**] を選択します。

1. [ **完了** ] をクリックして、クラスを作成します。

コントロールのユーザーがこの新しいプロパティページにアクセスできるようにするには、コントロールの [プロパティページ Id] マクロセクション (コントロール実装ファイルにあります) に次の変更を加えます。

[!code-cpp[NVC_MFC_AxUI#32](codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

BEGIN_PROPPAGEIDS マクロ (プロパティページ数) の2番目のパラメーターを1から2に増やす必要があることに注意してください。

また、コントロールの実装ファイル () も変更する必要があります。CPP) ヘッダーを含めるファイル ()。H) ファイルを作成します。

次の手順では、新しいプロパティページの型名とキャプションを提供する2つの新しい文字列リソースを作成します。

#### <a name="to-add-new-string-resources-to-a-property-page"></a>新しい文字列リソースをプロパティページに追加するには

1. コントロールプロジェクトを開いた状態で、リソースビューを開きます。

1. [ **String table** ] フォルダーをダブルクリックし、文字列を追加する既存の文字列テーブルリソースをダブルクリックします。

   これにより、文字列テーブルがウィンドウに表示されます。

1. 文字列テーブルの末尾にある空白行を選択し、文字列のテキスト (キャプション) を入力します。たとえば、「追加のプロパティページ」と入力します。

   [**キャプション**] ボックスと [ **ID** ]**ボックスが表示** されます。 [ **キャプション** ] ボックスには、入力した文字列が表示されます。

1. [ **Id** ] ボックスで、文字列の id を選択または入力します。 完了したら Enter キーを押します。

   この例では、新しいプロパティページの型名に **IDS_SAMPLE_ADDPAGE** を使用します。

1. ID には **IDS_SAMPLE_ADDPPG_CAPTION** を、キャプションには "追加のプロパティページ" を使用して、手順 3. と 4. を繰り返します。

1. の。新しいプロパティページクラスの CPP ファイル (この例では `CAddtlPropPage` ) は、次の例に示すように、 `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` IDS_SAMPLE_ADDPAGE が [AfxOleRegisterPropertyPageClass](reference/registering-ole-controls.md#afxoleregisterpropertypageclass)によって渡されるようにを変更します。

   [!code-cpp[NVC_MFC_AxUI#33](codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. 次のよう `CAddtlPropPage` に IDS_SAMPLE_ADDPPG_CAPTION がコンストラクターに渡されるように、のコンストラクターを変更 `COlePropertyPage` します。

   [!code-cpp[NVC_MFC_AxUI#34](codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

必要な変更を行った後、プロジェクトをリビルドし、テストコンテナーを使用して新しいプロパティページをテストします。 Test Container にアクセスする方法について詳しくは、「 [テスト コンテナーでのプロパティとイベントのテスト](testing-properties-and-events-with-test-container.md) 」をご覧ください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
