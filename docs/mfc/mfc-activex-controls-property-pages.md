---
title: 'MFC ActiveX コントロール : プロパティ ページ'
ms.date: 11/19/2018
helpviewer_keywords:
- DDP_ functions [MFC]
- MFC ActiveX controls [MFC], properties
- property pages [MFC], MFC ActiveX controls
- DoDataExchange method [MFC]
- OLEIVERB_PROPERTIES
- CPropertyPageDialog class [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
ms.openlocfilehash: 3d22085daa503a7c778111718445920f98b98a89
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615438"
---
# <a name="mfc-activex-controls-property-pages"></a>MFC ActiveX コントロール : プロパティ ページ

プロパティページを使用すると、ActiveX コントロールユーザーは ActiveX コントロールのプロパティを表示および変更できます。 これらのプロパティにアクセスするには、[コントロールのプロパティ] ダイアログボックスを呼び出します。このダイアログボックスには、コントロールのプロパティを表示および編集するためのカスタマイズされたグラフィカルインターフェイスを提供する、1つまたは複数のプロパティページがあります。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールのプロパティページは、次の2つの方法で表示されます。

- コントロールのプロパティ動詞 (**OLEIVERB_PROPERTIES**) が呼び出されると、コントロールは、コントロールのプロパティページを含むモーダルプロパティダイアログボックスを開きます。

- コンテナーは、選択したコントロールのプロパティページを表示する独自のモードレスダイアログボックスを表示できます。

次の図に示すように、[プロパティ] ダイアログボックスには、現在のプロパティページを表示する領域、プロパティページを切り替えるためのタブ、および [プロパティページ] ダイアログの終了、変更内容の取り消し、ActiveX コントロールへの変更の即時適用などの一般的なタスクを実行するボタンのコレクションが含まれています。

![Circ3 のプロパティ ダイアログ ボックス](../mfc/media/vc373i1.gif "Circ3 のプロパティ ダイアログ ボックス") <br/>
[プロパティ] ダイアログ ボックス

この記事では、ActiveX コントロールのプロパティページの使用に関連するトピックについて説明します。 これには以下が含まれます。

- [ActiveX コントロールの既定のプロパティページの実装](#_core_implementing_the_default_property_page)

- [プロパティページへのコントロールの追加](#_core_adding_controls_to_a_property_page)

- [DoDataExchange 関数のカスタマイズ](#_core_customizing_the_dodataexchange_function)

ActiveX コントロールでのプロパティページの使用の詳細については、次の記事を参照してください。

- [MFC ActiveX コントロール : カスタム プロパティ ページの追加](mfc-activex-controls-adding-another-custom-property-page.md)

- [MFC ActiveX コントロール : ストック プロパティ ページの使用](mfc-activex-controls-using-stock-property-pages.md)

ActiveX コントロール以外の MFC アプリケーションでプロパティシートを使用する方法の詳細については、「[プロパティシート](property-sheets-mfc.md)」を参照してください。

## <a name="implementing-the-default-property-page"></a><a name="_core_implementing_the_default_property_page"></a>既定のプロパティページの実装

ActiveX コントロールウィザードを使用してコントロールプロジェクトを作成する場合、ActiveX コントロールウィザードには、 [COlePropertyPage クラス](reference/colepropertypage-class.md)から派生したコントロールの既定のプロパティページクラスが用意されています。 初期状態では、このプロパティページは空白ですが、ダイアログボックスコントロールまたはコントロールのセットを追加できます。 既定では、ActiveX コントロールウィザードによって作成されるプロパティページクラスは1つだけなので、追加のプロパティページクラス (からも派生 `COlePropertyPage` ) をクラスビューを使用して作成する必要があります。 この手順の詳細については、「 [MFC ActiveX コントロール: 別のカスタムプロパティページの追加](mfc-activex-controls-adding-another-custom-property-page.md)」を参照してください。

プロパティページ (この場合は既定値) を実装するには、次の3つの手順を実行します。

#### <a name="to-implement-a-property-page"></a>プロパティページを実装するには

1. `COlePropertyPage`派生クラスをコントロールプロジェクトに追加します。 (この場合と同様に) ActiveX コントロールウィザードを使用してプロジェクトを作成した場合は、既定のプロパティページクラスが既に存在しています。

1. ダイアログエディターを使用して、プロパティページテンプレートにコントロールを追加します。

1. の派生クラスの関数をカスタマイズして、 `DoDataExchange` `COlePropertyPage` プロパティページコントロールと ActiveX コントロールの間で値を交換します。

たとえば、次の手順では、単純なコントロール ("Sample" という名前) を使用します。 サンプルは、ActiveX コントロールウィザードを使用して作成されたもので、stock Caption プロパティのみが含まれています。

## <a name="adding-controls-to-a-property-page"></a><a name="_core_adding_controls_to_a_property_page"></a>プロパティページへのコントロールの追加

#### <a name="to-add-controls-to-a-property-page"></a>プロパティページにコントロールを追加するには

1. コントロールプロジェクトを開いた状態で、リソースビューを開きます。

1. **ダイアログ**ディレクトリアイコンをダブルクリックします。

1. [IDD_PROPPAGE_SAMPLE] ダイアログボックスを開きます。

   ActiveX コントロールウィザードでは、プロジェクトの名前がダイアログ ID の末尾 (この場合は [サンプル]) に追加されます。

1. 選択したコントロールを [ツールボックス] からダイアログボックス領域にドラッグアンドドロップします。

1. この例では、テキストラベルコントロール "Caption:" と IDC_CAPTION 識別子を持つエディットボックスコントロールで十分です。

1. ツールバーの [**保存**] をクリックして、変更を保存します。

ユーザーインターフェイスが変更されたので、[キャプション] プロパティを使用して編集ボックスをリンクする必要があります。 これを行うには、次のセクションで関数を編集し `CSamplePropPage::DoDataExchange` ます。

## <a name="customizing-the-dodataexchange-function"></a><a name="_core_customizing_the_dodataexchange_function"></a>DoDataExchange 関数のカスタマイズ

プロパティページ[CWnd::D odataexchange](reference/cwnd-class.md#dodataexchange)関数を使用すると、プロパティページの値をコントロールのプロパティの実際の値とリンクできます。 リンクを確立するには、適切なプロパティページのフィールドをそれぞれのコントロールプロパティにマップする必要があります。

これらのマッピングは、プロパティページ**DDP_** 関数を使用して実装されます。 **DDP_** 関数は、標準の MFC ダイアログで使用される**DDX_** 関数と同様に機能しますが、1つの例外があります。 メンバー変数への参照に加えて、 **DDP_** の関数は、コントロールプロパティの名前を受け取ります。 プロパティページの関数の一般的なエントリを次に示し `DoDataExchange` ます。

[!code-cpp[NVC_MFC_AxUI#31](codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]

この関数は、関数を使用して、プロパティページの*m_caption*メンバー変数をキャプションに関連付け `DDP_TEXT` ます。

プロパティページコントロールが挿入されたら、前述のように、関数を使用して、プロパティページコントロール、IDC_CAPTION、および実際のコントロールプロパティ Caption との間にリンクを確立する必要があり `DDP_Text` ます。

[プロパティページ](reference/property-pages-mfc.md)は、チェックボックス、オプションボタン、リストボックスなど、他の種類のダイアログコントロールで使用できます。 次の表は、一連のプロパティページ**DDP_** 関数とその目的を示しています。

### <a name="property-page-functions"></a>プロパティページの関数

|関数名|リンクするには、この関数を使用します|
|-------------------|-------------------------------|
|`DDP_CBIndex`|コントロールプロパティを持つコンボボックス内の選択された文字列のインデックス。|
|`DDP_CBString`|コントロールプロパティを持つコンボボックス内の選択された文字列。 選択した文字列は、プロパティの値と同じ文字で始まることができますが、完全に一致している必要はありません。|
|`DDP_CBStringExact`|コントロールプロパティを持つコンボボックス内の選択された文字列。 選択した文字列とプロパティの文字列値が正確に一致している必要があります。|
|`DDP_Check`|コントロールプロパティを持つチェックボックス。|
|`DDP_LBIndex`|コントロールプロパティを持つリストボックス内の選択された文字列のインデックス。|
|`DDP_LBString`|コントロールプロパティを持つリストボックス内の選択された文字列。 選択した文字列は、プロパティの値と同じ文字で始まることができますが、完全に一致している必要はありません。|
|`DDP_LBStringExact`|コントロールプロパティを持つリストボックス内の選択された文字列。 選択した文字列とプロパティの文字列値が正確に一致している必要があります。|
|`DDP_Radio`|コントロールプロパティを持つオプションボタン。|
|`DDP_Text`|コントロールプロパティを持つテキスト。|

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[COlePropertyPage クラス](reference/colepropertypage-class.md)
