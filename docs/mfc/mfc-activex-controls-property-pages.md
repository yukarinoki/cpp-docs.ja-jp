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
ms.openlocfilehash: c31d13e03483f8632f17a526da75ebe8e21bccbf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364564"
---
# <a name="mfc-activex-controls-property-pages"></a>MFC ActiveX コントロール : プロパティ ページ

プロパティ ページを使用すると、ActiveX コントロールのユーザーは ActiveX コントロールのプロパティを表示および変更できます。 これらのプロパティにアクセスするには、コントロールプロパティダイアログボックスを呼び出します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールのプロパティ ページは、次の 2 つの方法で表示されます。

- コントロールの Properties 動詞 (**OLEIVERB_PROPERTIES**) が呼び出されると、コントロールのプロパティ ページを含むモーダル プロパティ ダイアログ ボックスが開きます。

- コンテナーは、選択したコントロールのプロパティ ページを表示する独自のモードレス ダイアログ ボックスを表示できます。

プロパティ ダイアログ ボックス (次の図に示す) は、現在のプロパティ ページを表示するための領域、プロパティ ページを切り替えるタブ、およびプロパティ ページ ダイアログを閉じる、変更をキャンセルする、ActiveX コントロールに変更を直ちに適用するなどの一般的なタスクを実行するボタンのコレクションで構成されています。

![Circ3 のプロパティ ダイアログ ボックス](../mfc/media/vc373i1.gif "Circ3 のプロパティ ダイアログ ボックス") <br/>
[プロパティ] ダイアログ ボックス

この記事では、ActiveX コントロールでのプロパティ ページの使用に関するトピックについて説明します。 これには以下が含まれます。

- [ActiveX コントロールの既定のプロパティ ページを実装する](#_core_implementing_the_default_property_page)

- [プロパティ ページへのコントロールの追加](#_core_adding_controls_to_a_property_page)

- [関数のカスタマイズ](#_core_customizing_the_dodataexchange_function)

ActiveX コントロールでプロパティ ページを使用する方法の詳細については、次の記事を参照してください。

- [MFC ActiveX コントロール : カスタム プロパティ ページの追加](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

- [MFC ActiveX コントロール : ストック プロパティ ページの使用](../mfc/mfc-activex-controls-using-stock-property-pages.md)

ActiveX コントロール以外の MFC アプリケーションでプロパティ シートを使用する方法については、「[プロパティ シート](../mfc/property-sheets-mfc.md)」を参照してください。

## <a name="implementing-the-default-property-page"></a><a name="_core_implementing_the_default_property_page"></a>既定のプロパティ ページの実装

ActiveX コントロール ウィザードを使用してコントロール プロジェクトを作成する場合、ActiveX コントロール ウィザードは[、COlePropertyPage クラス](../mfc/reference/colepropertypage-class.md)から派生したコントロールの既定のプロパティ ページ クラスを提供します。 最初は、このプロパティ ページは空白ですが、ダイアログ ボックス コントロールまたはコントロールセットを追加できます。 ActiveX コントロール ウィザードは既定で 1 つのプロパティ ページ クラスしか作成しないため、クラス`COlePropertyPage`ビューを使用してプロパティ ページ クラス (派生元) を追加する必要があります。 この手順の詳細については、「 [MFC ActiveX コントロール : 別のカスタム プロパティ ページを追加](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)する 」を参照してください。

プロパティ ページの実装 (この場合は既定) は、次の 3 つの手順で行います。

#### <a name="to-implement-a-property-page"></a>プロパティ ページを実装するには

1. コントロール`COlePropertyPage`プロジェクトに派生クラスを追加します。 ActiveX コントロール ウィザードを使用してプロジェクトを作成した場合 (この場合と同様)、既定のプロパティ ページ クラスは既に存在します。

1. ダイアログ エディターを使用して、プロパティ ページ テンプレートにコントロールを追加します。

1. プロパティ`DoDataExchange`ページ コントロール`COlePropertyPage`と ActiveX コントロールの間で値を交換する -derived クラスの関数をカスタマイズします。

たとえば、次の手順では、単純なコントロール ("Sample" という名前) を使用します。 サンプルは ActiveX コントロール ウィザードを使用して作成され、"ストック キャプション" プロパティのみが含まれています。

## <a name="adding-controls-to-a-property-page"></a><a name="_core_adding_controls_to_a_property_page"></a>プロパティ ページへのコントロールの追加

#### <a name="to-add-controls-to-a-property-page"></a>プロパティ ページにコントロールを追加するには

1. コントロール プロジェクトを開いた後、リソース ビューを開きます。

1. **[ダイアログ]** ディレクトリ アイコンをダブルクリックします。

1. IDD_PROPPAGE_SAMPLE ダイアログ ボックスを開きます。

   ActiveX コントロール ウィザードは、ダイアログ ID の末尾にプロジェクトの名前を追加します (この場合はサンプル)。

1. 選択したコントロールをツールボックスからダイアログ ボックス領域にドラッグ アンド ドロップします。

1. この例では、テキスト ラベル コントロール "Caption :" と、IDC_CAPTION識別子を持つエディット ボックス コントロールで十分です。

1. ツールバーの [**保存**] をクリックして、変更を保存します。

ユーザー インターフェイスが変更された後、編集ボックスを Caption プロパティにリンクする必要があります。 これは、関数を編集することによって、次のセクション`CSamplePropPage::DoDataExchange`で行われます。

## <a name="customizing-the-dodataexchange-function"></a><a name="_core_customizing_the_dodataexchange_function"></a>関数のカスタマイズ

プロパティ ページ[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)関数を使用すると、コントロール内のプロパティの実際の値とプロパティ ページの値をリンクできます。 リンクを確立するには、適切なプロパティ ページ フィールドをそれぞれのコントロール プロパティにマップする必要があります。

これらのマッピングは、プロパティ ページ**DDP_** 関数を使用して実装されます。 **DDP_** 関数は、標準 MFC ダイアログで使用される**DDX_** 関数と同様に機能しますが、例外があります。 メンバー変数への参照に加えて **、DDP_** 関数はコントロール プロパティの名前を取得します。 プロパティ ページの関数の一般的`DoDataExchange`なエントリを次に示します。

[!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]

この関数は、関数を使用して、プロパティ ページの*m_caption*メンバー変数を`DDP_TEXT`Caption に関連付けます。

プロパティ ページ コントロールを挿入したら、上記の関数を使用して、プロパティ ページ コントロール、IDC_CAPTION、および実際のコントロール プロパティ Caption と`DDP_Text`の間にリンクを確立する必要があります。

[プロパティ ページ](../mfc/reference/property-pages-mfc.md)は、チェック ボックス、ラジオ ボタン、リスト ボックスなど、他の種類のダイアログ コントロールで使用できます。 次の表は、プロパティ ページの全セット**DDP_** 関数とその目的を示しています。

### <a name="property-page-functions"></a>プロパティ ページ関数

|関数名|この関数を使用してリンクします|
|-------------------|-------------------------------|
|`DDP_CBIndex`|コントロール プロパティを持つコンボ ボックス内の選択した文字列のインデックス。|
|`DDP_CBString`|コンボ ボックス内の選択された文字列とコントロール プロパティ。 選択した文字列は、プロパティの値と同じ文字で始めることができますが、完全に一致する必要はありません。|
|`DDP_CBStringExact`|コンボ ボックス内の選択された文字列とコントロール プロパティ。 選択した文字列とプロパティの文字列値は、正確に一致する必要があります。|
|`DDP_Check`|コントロール プロパティを持つチェック ボックス。|
|`DDP_LBIndex`|コントロール プロパティを持つリスト ボックス内の選択した文字列のインデックス。|
|`DDP_LBString`|コントロール プロパティを持つリスト ボックス内の選択された文字列。 選択した文字列は、プロパティの値と同じ文字で始めることができますが、完全に一致する必要はありません。|
|`DDP_LBStringExact`|コントロール プロパティを持つリスト ボックス内の選択された文字列。 選択した文字列とプロパティの文字列値は、正確に一致する必要があります。|
|`DDP_Radio`|コントロール プロパティを持つオプション ボタン。|
|`DDP_Text`|コントロール プロパティを持つテキスト。|

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[COlePropertyPage クラス](../mfc/reference/colepropertypage-class.md)
