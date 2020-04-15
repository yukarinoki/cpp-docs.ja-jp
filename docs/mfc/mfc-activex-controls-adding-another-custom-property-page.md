---
title: 'MFC ActiveX コントロール : カスタム プロパティ ページの追加'
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
ms.openlocfilehash: 02c87c2c5283b7293c2a7ab028ec9a2abbba2b33
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364737"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX コントロール : カスタム プロパティ ページの追加

ActiveX コントロールには、1 つのプロパティ ページに適した値よりも多くのプロパティが含まれやすい場合があります。 この場合、ActiveX コントロールにプロパティ ページを追加して、これらのプロパティを表示できます。

この資料では、少なくとも 1 つのプロパティ ページが既に存在する ActiveX コントロールに新しいプロパティ ページを追加する方法について説明します。 ストック プロパティ ページ (フォント、ピクチャ、または色) の追加の詳細については[、「MFC ActiveX コントロール: ストック プロパティ ページの使用](../mfc/mfc-activex-controls-using-stock-property-pages.md)」を参照してください。

次の手順では、ActiveX コントロール ウィザードで作成された ActiveX コントロール フレームワークのサンプルを使用します。 したがって、クラス名と識別子はこの例に固有です。

ActiveX コントロールでプロパティ ページを使用する方法の詳細については、次の記事を参照してください。

- [MFC ActiveX コントロール: プロパティ ページ](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX コントロール : ストック プロパティ ページの使用](../mfc/mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  新しいプロパティ ページは、ActiveX コントロールのプロパティ ページのサイズ標準に準拠することを強くお勧めします。 ストックピクチャとカラーのプロパティページは、250x62 ダイアログユニット(DLU)を測定します。 標準フォント プロパティ ページは 250x110 DLU です。 ActiveX コントロール ウィザードによって作成される既定のプロパティ ページでは、250x62 DLU 標準が使用されます。

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>新しいプロパティ ページ テンプレートをプロジェクトに挿入するには

1. コントロール プロジェクトを開いた状態で、プロジェクト ワークスペースでリソース ビューを開きます。

1. リソース ビューで右クリックしてショートカット メニューを開き、[**リソースの追加**] をクリックします。

1. **[ダイアログ]** ノードを展開し、[ **IDD_OLE_PROPPAGE_SMALL**] を選択します。

1. [**新規**] をクリックして、リソースをプロジェクトに追加します。

1. 新しいプロパティ ページ テンプレートを選択して、[**プロパティ**] ウィンドウを更新します ( **[リソース ビュー**] )。

1. **ID**プロパティに新しい値を入力します。 この例では **、IDD_PROPPAGE_NEWPAGE**を使用します。

1. ツール バーの **[Save]\(保存\)** をクリックします。

### <a name="to-associate-the-new-template-with-a-class"></a>新しいテンプレートをクラスに関連付けるには

1. クラス ビューを開きます。

1. クラス ビューで右クリックしてショートカット メニューを開きます。

1. ショートカット メニューの **[追加]** をクリックし、**[クラスの追加]** をクリックします。

   [クラスの[追加]](../ide/add-class-dialog-box.md)ダイアログ ボックスが開きます。

1. **MFC クラス**テンプレートをダブルクリックします。

1. MFC クラス[ウィザード](../mfc/reference/mfc-add-class-wizard.md)の [**クラス名**] ボックスに、新しいダイアログ クラスの名前を入力します。 (この例では.) `CAddtlPropPage`

1. ファイル名を変更する場合は、[**変更**] をクリックします。 実装ファイルとヘッダーファイルの名前を入力するか、デフォルトの名前をそのまま使用します。

1. [**基本クラス**] ボックスで`COlePropertyPage`、 を選択します。

1. [**ダイアログ ID]** ボックスの**一覧の [IDD_PROPPAGE_NEWPAGE]** をクリックします。

1. [**完了] を**クリックしてクラスを作成します。

コントロールのユーザーがこの新しいプロパティ ページにアクセスできるようにするには、コントロールのプロパティ ページ ID マクロ セクション (コントロール実装ファイル内) に次の変更を加えます。

[!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

BEGIN_PROPPAGEIDS マクロの 2 番目のパラメーター (プロパティ ページ数) を 1 から 2 に増やす必要があることに注意してください。

また、コントロール実装ファイル (.ヘッダーを含める CPP) ファイル (.H) ファイルは、新しいプロパティ ページ クラスです。

次の手順では、新しいプロパティ ページの型名とキャプションを提供する 2 つの新しい文字列リソースを作成します。

#### <a name="to-add-new-string-resources-to-a-property-page"></a>プロパティ ページに新しい文字列リソースを追加するには

1. コントロール プロジェクトを開いた後、リソース ビューを開きます。

1. **文字列テーブル**フォルダをダブルクリックし、文字列を追加する既存の文字列テーブル リソースをダブルクリックします。

   これにより、文字列テーブルがウィンドウに開きます。

1. 文字列テーブルの最後にある空白行を選択し、文字列のテキストまたはキャプションを入力します。

   [**キャプション**] ボックスと **[ID]** ボックスが表示された **[文字列のプロパティ]** ページが開きます。 [**キャプション]** ボックスには、入力した文字列が表示されます。

1. **[ID]** ボックスで、文字列の ID を選択または入力します。 終了したら Enter キーを押します。

   この例では、新しいプロパティ ページの型名に**IDS_SAMPLE_ADDPAGE**を使用します。

1. ID の**IDS_SAMPLE_ADDPPG_CAPTION**を使用して手順 3 と 4 を繰り返し、キャプションに対して 「追加のプロパティ ページ」を使用します。

1. の。新しいプロパティ ページ クラスの CPP ファイル`CAddtlPropPage`(この例`CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry`では) は、次の例のように、IDS_SAMPLE_ADDPAGE [AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass)によって渡されるように変更します。

   [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. 次のように、IDS_SAMPLE_ADDPPG_CAPTION`CAddtlPropPage`がコンストラクターに渡されるようにコンストラクターを`COlePropertyPage`変更します。

   [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

必要な変更を行った後、プロジェクトを再構築し、テスト コンテナーを使用して新しいプロパティ ページをテストします。 Test Container にアクセスする方法について詳しくは、「 [テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md) 」をご覧ください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
