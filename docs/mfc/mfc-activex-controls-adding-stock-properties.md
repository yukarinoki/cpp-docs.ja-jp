---
title: 'MFC ActiveX コントロール : ストック プロパティの追加'
ms.date: 11/04/2016
helpviewer_keywords:
- BackColor property [MFC]
- properties [MFC], adding stock
- ForeColor property [MFC]
- MFC ActiveX controls [MFC], properties
- foreground colors, ActiveX controls
- foreground colors [MFC]
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
ms.openlocfilehash: 13e8af5ddb3dd5130c864e42383e3bb9ff23b87b
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625422"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC ActiveX コントロール : ストック プロパティの追加

ストックプロパティは、クラスによって既に実装されているので、カスタムプロパティとは異なり `COleControl` ます。 `COleControl`コントロールの共通プロパティをサポートする定義済みのメンバー関数が含まれています。 一般的なプロパティには、コントロールのキャプション、前景色、背景色などがあります。 その他のストックプロパティについては、この記事で後述[する「プロパティの追加ウィザードでサポートされるストックプロパティ](#_core_stock_properties_supported_by_classwizard)」を参照してください。 ストックプロパティのディスパッチマップエントリの先頭には常に DISP_STOCKPROP が付きます。

この記事では、プロパティの追加ウィザードを使用して、ストックプロパティ (この場合はキャプション) を ActiveX コントロールに追加する方法と、結果として生成されるコード変更について説明します。 取り上げるトピックは次のとおりです。

- [プロパティの追加ウィザードを使用してストックプロパティを追加する](#_core_using_classwizard_to_add_a_stock_property)

- [ストックプロパティのプロパティの追加ウィザードの変更](#_core_classwizard_changes_for_stock_properties)

- [プロパティの追加ウィザードでサポートされるストックプロパティ](#_core_stock_properties_supported_by_classwizard)

- [ストックのプロパティと通知](#_core_stock_properties_and_notification)

- [色のプロパティ](#_core_color_properties)

    > [!NOTE]
    >  Visual Basic カスタムコントロールには、通常、Top、Left、Width、Height、Align、Tag、Name、TabIndex、TabStop、Parent などのプロパティがあります。 ただし、ActiveX コントロールコンテナーはこれらのコントロールプロパティを実装する必要があるため、ActiveX コントロールはこれらのプロパティをサポートしません。

## <a name="using-the-add-property-wizard-to-add-a-stock-property"></a><a name="_core_using_classwizard_to_add_a_stock_property"></a>プロパティの追加ウィザードを使用してストックプロパティを追加する

ストックプロパティの追加では、プロパティのサポートがによって自動的に処理されるため、カスタムプロパティを追加するよりも少ないコードが必要になり `COleControl` ます。 次の手順では、[ストック Caption] プロパティを ActiveX コントロールフレームワークに追加する方法と、その他のストックプロパティを追加する方法について説明します。 キャプションには、選択したストックプロパティ名を置き換えます。

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してストック Caption プロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカットメニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

   これにより、[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)が開きます。

1. [**プロパティ名**] ボックスで、[**キャプション**] をクリックします。

1. **[完了]** をクリックします。

## <a name="add-property-wizard-changes-for-stock-properties"></a><a name="_core_classwizard_changes_for_stock_properties"></a>ストックプロパティのプロパティの追加ウィザードの変更

は `COleControl` ストックプロパティをサポートしているため、プロパティの追加ウィザードではクラス宣言が変更されず、ディスパッチマップにプロパティが追加されます。 プロパティの追加ウィザードは、実装 () にあるコントロールのディスパッチマップに次の行を追加します。CPP) ファイル:

[!code-cpp[NVC_MFC_AxUI#22](codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

コントロールのインターフェイスの説明 () に次の行が追加されます。IDL) ファイル:

[!code-cpp[NVC_MFC_AxUI#23](codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

この行は、Caption プロパティに特定の ID を割り当てます。 プロパティはバインド可能であり、値を変更する前にデータベースからの権限が要求されることに注意してください。

これにより、コントロールのユーザーがキャプションプロパティを使用できるようになります。 ストックプロパティの値を使用するには、基底クラスのメンバー変数またはメンバー関数にアクセスし `COleControl` ます。 これらのメンバー変数とメンバー関数の詳細については、次のセクション「プロパティの追加ウィザードでサポートされるストックプロパティ」を参照してください。

## <a name="stock-properties-supported-by-the-add-property-wizard"></a><a name="_core_stock_properties_supported_by_classwizard"></a>プロパティの追加ウィザードでサポートされるストックプロパティ

`COleControl`クラスには、9つのストックプロパティが用意されています。 プロパティの追加ウィザードを使用して、必要なプロパティを追加できます。

|プロパティ|ディスパッチマップエントリ|値にアクセスする方法|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE ()|としてアクセスできる値 `m_sAppearance` 。|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR ()|を呼び出すことによってアクセスできる値 `GetBackColor` 。|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE ()|としてアクセスできる値 `m_sBorderStyle` 。|
|`Caption`|DISP_STOCKPROP_CAPTION ()|を呼び出すことによってアクセスできる値 `InternalGetText` 。|
|`Enabled`|DISP_STOCKPROP_ENABLED ()|としてアクセスできる値 `m_bEnabled` 。|
|`Font`|DISP_STOCKPROP_FONT ()|使用方法については、「 [MFC ActiveX コントロール: フォントの使用](mfc-activex-controls-using-fonts.md)」を参照してください。|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR ()|を呼び出すことによってアクセスできる値 `GetForeColor` 。|
|`hWnd`|DISP_STOCKPROP_HWND ()|としてアクセスできる値 `m_hWnd` 。|
|`Text`|DISP_STOCKPROP_TEXT ()|を呼び出すことによってアクセスできる値 `InternalGetText` 。 このプロパティは、 `Caption` プロパティ名を除いてと同じです。|
|`ReadyState`|DISP_STOCKPROP_READYSTATE ()|またはとしてアクセスできる値 `m_lReadyState``GetReadyState`|

## <a name="stock-properties-and-notification"></a><a name="_core_stock_properties_and_notification"></a>ストックのプロパティと通知

ほとんどのストックプロパティには、オーバーライドできる通知関数があります。 たとえば、プロパティが変更されるたびに、 `BackColor` `OnBackColorChanged` 関数 (コントロールクラスのメンバー関数) が呼び出されます。 既定の実装 (では) はを `COleControl` 呼び出し `InvalidateControl` ます。 この状況に応じて追加のアクションを実行する場合は、この関数をオーバーライドします。

## <a name="color-properties"></a><a name="_core_color_properties"></a>色のプロパティ

コントロールを描画するときに、ストックプロパティと `ForeColor` `BackColor` プロパティ、または独自のカスタムカラープロパティを使用できます。 Color プロパティを使用するには、 [COleControl:: TranslateColor](reference/colecontrol-class.md#translatecolor)メンバー関数を呼び出します。 この関数のパラメーターは、color プロパティの値と、オプションのパレットハンドルです。 戻り値は、やなどの GDI 関数に渡すことができる**COLORREF**値です `SetTextColor` `CreateSolidBrush` 。

ストックおよびプロパティの色の値は、 `ForeColor` `BackColor` 関数または関数のいずれかを呼び出すことによってアクセスされ `GetForeColor` `GetBackColor` ます。

次の例では、コントロールを描画するときに、これら2色のプロパティを使用する方法を示します。 このメソッドは、プロパティを使用してプロパティを使用し、もう1つをプロパティを使用して、一時的な**COLORREF**変数と `CBrush` を呼び出してオブジェクトを初期化し `TranslateColor` `ForeColor` `BackColor` ます。 次に、一時オブジェクトを使用して `CBrush` コントロールの四角形を描画し、テキストの色をプロパティを使用して設定し `ForeColor` ます。

[!code-cpp[NVC_MFC_AxUI#24](codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール : プロパティ](mfc-activex-controls-properties.md)<br/>
[MFC ActiveX コントロール: メソッド](mfc-activex-controls-methods.md)<br/>
[COleControl クラス](reference/colecontrol-class.md)
