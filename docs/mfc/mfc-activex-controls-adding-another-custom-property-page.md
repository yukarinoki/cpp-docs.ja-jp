---
title: 'MFC ActiveX コントロール: カスタム プロパティ ページの追加 |Microsoft ドキュメント'
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
ms.openlocfilehash: 4a0e8713bc228e65cb06e58d7ccb5389f7366e76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX コントロール : カスタム プロパティ ページの追加
場合によっては、ActiveX コントロールは、1 つのプロパティ ページに収まることにかなり多くのプロパティがあります。 この場合、これらのプロパティを表示する ActiveX コントロールにプロパティ ページを追加できます。  
  
 この記事では、少なくとも 1 つのプロパティ ページが既にいる ActiveX コントロールに新しいプロパティ ページを追加することについて説明します。 ストック プロパティを追加する方法の詳細については、ページ (フォント、画像、または色) は、記事を参照してください。 [MFC ActiveX コントロール: ストック プロパティ ページを使用して](../mfc/mfc-activex-controls-using-stock-property-pages.md)です。  
  
 次の手順では、ActiveX コントロール ウィザードによって作成された ActiveX コントロール フレームワークの例を使用します。 そのため、クラス名と識別子は、この例に一意です。  
  
 ActiveX コントロールのプロパティ ページを使用する方法については、次の記事を参照してください。  
  
-   [MFC ActiveX コントロール: プロパティ ページ](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX コントロール: ストック プロパティ ページの使用](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
    > [!NOTE]
    >  その新しいプロパティのページが ActiveX コントロールのプロパティ ページの標準サイズに従う強く勧めします。 画像およびカラー ストック プロパティ ページの測定 250 x 62 ダイアログ単位 (DLU)。 標準のフォント プロパティ ページは、250 x 110 Dlu です。 ActiveX コントロール ウィザードによって作成された既定のプロパティ ページでは、250 x 62 DLU 標準を使用します。  
  
### <a name="to-insert-a-new-property-page-template-into-your-project"></a>プロジェクトに新しいプロパティ ページのテンプレートを挿入するには  
  
1.  コントロール プロジェクトを開き、プロジェクト ワークスペースで リソース ビューを開きます。  
  
2.  ショートカット メニューを開き、をクリックするリソース ビューを右クリックして**リソースの追加**です。  
  
3.  展開して、**ダイアログ**ノード、および選択**IDD_OLE_PROPPAGE_SMALL**です。  
  
4.  をクリックして`New`をプロジェクトにリソースを追加します。  
  
5.  [プロパティ] ウィンドウを更新する新しいプロパティ ページのテンプレートを選択します。  
  
6.  新しい値を入力、 **ID**プロパティです。 この例では**IDD_PROPPAGE_NEWPAGE**です。  
  
7.  をクリックして**保存**ツールバー。  
  
### <a name="to-associate-the-new-template-with-a-class"></a>クラスの新しいテンプレートを関連付けるには  
  
1.  クラス ビューを開きます。  
  
2.  クラス ビューを開くには、ショートカット メニューを右クリックします。  
  
3.  ショートカット メニューから **[追加]** をクリックし、**クラスの追加**です。  
  
     開き、[クラスの追加](../ide/add-class-dialog-box.md) ダイアログ ボックス。  
  
4.  ダブルクリックして、 **MFC クラス**テンプレート。  
  
5.  **クラス名**ボックスに、 [MFC クラス ウィザード](../mfc/reference/mfc-add-class-wizard.md)、新しいダイアログ クラスの名前を入力します。 (この例では`CAddtlPropPage`)。  
  
6.  ファイル名を変更する場合は、クリックして**変更**です。 実装とヘッダー ファイルの名前を入力するか、既定の名前を受け入れます。  
  
7.  **ベース クラス**ボックスで、`COlePropertyPage`です。  
  
8.  **ダイアログ ID**ボックスで、 **IDD_PROPPAGE_NEWPAGE**です。  
  
9. をクリックして**完了**クラスを作成します。  
  
 コントロールのユーザーがこの新しいプロパティ ページへのアクセスを許可するには、コントロールのプロパティ ページ Id マクロ セクション (コントロール実装ファイルにあります) を次の変更をします。  
  
 [!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]  
  
 2 番目のパラメーターを大きく必要がありますに注意してください、 `BEGIN_PROPPAGEIDS` 2 の 1 からマクロ (プロパティのページ数)。  
  
 また、コントロール実装ファイルを変更する必要があります (です。ヘッダーをインクルードする CPP) ファイル (です。H)、新しいプロパティ ページ クラスのファイルです。  
  
 次の手順には、新しいプロパティ ページの型の名前とキャプションを提供する 2 つの新しい文字列リソースの作成が含まれます。  
  
#### <a name="to-add-new-string-resources-to-a-property-page"></a>プロパティ ページに新しい文字列リソースを追加するには  
  
1.  コントロール プロジェクトを開き、リソース ビューを開きます。  
  
2.  ダブルクリックして、**ストリング テーブル**フォルダーをクリックして、既存の文字列テーブル リソースの文字列を追加します。  
  
     これは、ウィンドウで、文字列テーブルを開きます。  
  
3.  文字列テーブルの最後に空白行を選択し、テキスト、または文字列のキャプションを入力しますたとえば、"追加プロパティのページです。"。  
  
     開き、**文字列プロパティ**ページ表示**キャプション**と**ID**ボックス。 **キャプション** ボックスに入力した文字列が含まれています。  
  
4.  **ID**ボックスを選択するか、文字列の ID を入力します。 完了したら、Enter キーを押します。  
  
     この例では**として**新しいプロパティ ページの型の名前にします。  
  
5.  手順 3 と 4 を使用して繰り返します**IDS_SAMPLE_ADDPPG_CAPTION** ID および「その他の プロパティ ページ」キャプション。  
  
6.  の。新しいプロパティ ページ クラスの CPP ファイル (この例では`CAddtlPropPage`) を変更、`CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry`としては渡されるように[AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass)次の例のように。  
  
     [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]  
  
7.  コンス トラクターを変更`CAddtlPropPage`ように**IDS_SAMPLE_ADDPPG_CAPTION**に渡される、`COlePropertyPage`コンス トラクターで、次のようにします。  
  
     [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]  
  
 プロジェクトをリビルドし、新しいプロパティ ページをテストするテスト コンテナーを使用して必要な修正を行ったらです。 Test Container にアクセスする方法について詳しくは、「 [テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md) 」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

