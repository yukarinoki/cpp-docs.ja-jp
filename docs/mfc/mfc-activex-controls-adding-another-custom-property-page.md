---
title: 'MFC ActiveX コントロール: カスタム プロパティ ページの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce81436781a92c8d2c9156e1d1c02513c3816dc4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440057"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX コントロール : カスタム プロパティ ページの追加

場合によっては、ActiveX コントロールは、1 つのプロパティ ページにある程度に収まるよりも多くのプロパティがあります。 この場合、これらのプロパティを表示する ActiveX コントロールにプロパティ ページを追加できます。

この記事では、少なくとも 1 つのプロパティ ページに既にある ActiveX コントロールへの新しいプロパティ ページの追加について説明します。 ストック プロパティを追加する方法についてのページ (フォント、画像、または色) は、記事を参照して[MFC ActiveX コントロール: ストック プロパティ ページを使用して](../mfc/mfc-activex-controls-using-stock-property-pages.md)します。

次の手順では、ActiveX コントロール ウィザードによって作成されたサンプルの ActiveX コントロール フレームワークを使用します。 そのため、クラスの名前と識別子は、この例に一意です。

ActiveX コントロールのプロパティ ページの使用に関する詳細については、次の記事を参照してください。

- [MFC ActiveX コントロール: プロパティ ページ](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX コントロール: ストック プロパティ ページの使用](../mfc/mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  新しいプロパティ ページが ActiveX コントロールのプロパティ ページの標準のサイズに従う強く勧めします。 画像およびカラー ストック プロパティ ページの測定 250 x 62 ダイアログ単位 (DLU)。 標準的なフォントのプロパティ ページでは、250 x 110 Dlu です。 ActiveX コントロール ウィザードによって作成された既定のプロパティ ページでは、250 x 62 DLU 標準を使用します。

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>プロジェクトに新しいプロパティ ページのテンプレートを挿入するには

1. コントロール プロジェクトを開き、プロジェクトのワークスペースでリソース ビューを開きます。

1. ショートカット メニューを開き、をクリックして、リソース ビューで右クリックして**リソースの追加**します。

1. 展開、**ダイアログ**ノード、および選択**IDD_OLE_PROPPAGE_SMALL**します。

1. クリックして**新規**をプロジェクトにリソースを追加します。

1. [プロパティ] ウィンドウを更新する新しいプロパティ ページ テンプレートを選択します。

1. 新しい値を入力、 **ID**プロパティ。 この例では**IDD_PROPPAGE_NEWPAGE**します。

1. クリックして**保存**ツールバー。

### <a name="to-associate-the-new-template-with-a-class"></a>クラスの新しいテンプレートを関連付けるには

1. クラス ビューを開きます。

1. ショートカット メニューを開き、クラス ビューで右クリックします。

1. ショートカット メニューでは、次のようにクリックします。**追加** をクリックし、**クラスの追加**します。

     開き、[クラスの追加](../ide/add-class-dialog-box.md) ダイアログ ボックス。

1. ダブルクリックして、 **MFC クラス**テンプレート。

1. **クラス名**ボックスに、 [MFC クラス ウィザード](../mfc/reference/mfc-add-class-wizard.md)、新しいダイアログ クラスの名前を入力します。 (この例で`CAddtlPropPage`)。

1. ファイル名を変更する場合は、クリックして**変更**します。 実装とヘッダー ファイルの名前を入力するか、既定の名前をそのまま使用します。

1. **ベース クラス**ボックスで、`COlePropertyPage`します。

1. **ダイアログ ID**ボックスで、 **IDD_PROPPAGE_NEWPAGE**します。

9. クリックして**完了**クラスを作成します。

コントロールのユーザーにこの新しいプロパティ ページへのアクセスを許可するには、コントロールのプロパティ ページ Id マクロ セクション (コントロールの実装ファイルにあります) を次の変更のため。

[!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

2 を 1 から BEGIN_PROPPAGEIDS マクロ (プロパティのページ数) の 2 番目のパラメーターを変更する必要がありますに注意してください。

コントロールの実装ファイルを変更することも必要があります (します。CPP) ファイルにヘッダーを含める (します。H)、新しいプロパティ ページ クラスのファイルです。

次の手順では、新しいプロパティ ページの型名およびキャプションを提供する 2 つの新しい文字列リソースを作成する必要があります。

#### <a name="to-add-new-string-resources-to-a-property-page"></a>プロパティ ページに新しい文字列リソースを追加するには

1. コントロール プロジェクトを開き、リソース ビューを開きます。

1. ダブルクリックして、**ストリング テーブル**フォルダーとダブルクリックして、既存の文字列テーブルの文字列を追加するリソース。

     これは、ウィンドウで、文字列テーブルを開きます。

1. 文字列のテーブルの末尾の空白行を選択し、テキスト、または文字列のキャプションを入力しますたとえば、"追加プロパティのページです。"。

     開き、**文字列プロパティ**ページが表示された**キャプション**と**ID**ボックス。 **キャプション**ボックスに入力した文字列が含まれています。

1. **ID**ボックス、選択するか、文字列の ID を入力します。 完了したら、Enter キーを押します。

     この例では**として**新しいプロパティ ページの型の名前にします。

1. 手順 3 と 4 を使用して**IDS_SAMPLE_ADDPPG_CAPTION** ID とキャプションを「追加プロパティ ページ」にします。

1. の。新しいプロパティ ページ クラスの CPP ファイル (この例で`CAddtlPropPage`) を変更、`CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry`としてがによって渡されるように[AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass)、次の例のように。

     [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. コンス トラクターを変更`CAddtlPropPage`IDS_SAMPLE_ADDPPG_CAPTION に渡されるように、`COlePropertyPage`コンス トラクターには、次のようにします。

     [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

プロジェクトをビルドし、新しいプロパティ ページをテストするテスト コンテナーを使用して、必要な変更が終了したら。 Test Container にアクセスする方法について詳しくは、「 [テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md) 」をご覧ください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

