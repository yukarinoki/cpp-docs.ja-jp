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
ms.openlocfilehash: 16bdfddf0c028bc6a312767844b38c58c942d56e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364658"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC ActiveX コントロール : ストック プロパティの追加

ストック プロパティは、既にクラス`COleControl`によって実装されているという点で、カスタム プロパティとは異なります。 `COleControl`には、コントロールの共通プロパティをサポートする定義済みのメンバー関数が含まれています。 一般的なプロパティには、コントロールのキャプション、前景色、背景色などがあります。 その他のストック プロパティについては、この記事[の「プロパティの追加ウィザードでサポートされるストック プロパティ](#_core_stock_properties_supported_by_classwizard)」を参照してください。 ストック プロパティのディスパッチ マップ エントリには、常にDISP_STOCKPROPがプレフィックスとして付きます。

この資料では、プロパティの追加ウィザードを使用して、ストック プロパティ (この場合は Caption) を ActiveX コントロールに追加する方法について説明し、結果として得られるコードの変更について説明します。 取り上げるトピックは次のとおりです。

- [プロパティの追加ウィザードを使用してストック プロパティを追加する](#_core_using_classwizard_to_add_a_stock_property)

- [ストック プロパティのプロパティ追加ウィザードの変更](#_core_classwizard_changes_for_stock_properties)

- [プロパティの追加ウィザードでサポートされるストック プロパティ](#_core_stock_properties_supported_by_classwizard)

- [株式のプロパティと通知](#_core_stock_properties_and_notification)

- [色のプロパティ](#_core_color_properties)

    > [!NOTE]
    >  通常、Visual Basic カスタム コントロールには、トップ、左、幅、高さ、配置、タグ、名前、タブインデックス、タブストップ、親などのプロパティがあります。 ただし、ActiveX コントロール コンテナーは、これらのコントロール プロパティの実装を行うため、ActiveX コントロールはこれらのプロパティをサポートしません。

## <a name="using-the-add-property-wizard-to-add-a-stock-property"></a><a name="_core_using_classwizard_to_add_a_stock_property"></a>プロパティ追加ウィザードを使用したストック プロパティの追加

ストック プロパティを追加する場合、カスタム プロパティのサポートは`COleControl`によって自動的に処理されるため、カスタム プロパティの追加よりもコードが少なくなります。 次の手順では、ストック キャプション プロパティを ActiveX コントロール フレームワークに追加する方法を示します。 選択したストック プロパティ名を [キャプション] に置き換えます。

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してストックキャプションプロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

   これにより、[プロパティの追加ウィザードが](../ide/names-add-property-wizard.md)開きます。

1. [**プロパティ名]** ボックスの一**覧の [標題**] をクリックします。

1. **[完了]** をクリックします。

## <a name="add-property-wizard-changes-for-stock-properties"></a><a name="_core_classwizard_changes_for_stock_properties"></a>ストック プロパティのプロパティ ウィザードの変更の追加

ストック`COleControl`プロパティをサポートしているため、プロパティの追加ウィザードではクラス宣言は変更されません。このプロパティは、ディスパッチ マップに追加されます。 プロパティの追加ウィザードは、実装内にあるコントロールのディスパッチ マップに次の行を追加します ( .CPP) ファイル:

[!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

コントロールのインターフェイスの説明 (.IDL) ファイル:

[!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

この行は、キャプション プロパティに特定の ID を割り当てます。 プロパティはバインド可能であり、値を変更する前にデータベースにアクセス許可を要求することに注意してください。

これにより、コントロールのユーザーが Caption プロパティを使用できるようになります。 ストック プロパティの値を使用するには、基本クラスのメンバー変数またはメンバー関数に`COleControl`アクセスします。 これらのメンバー変数とメンバー関数の詳細については、次のセクション「プロパティの追加ウィザードでサポートされるストック プロパティ」を参照してください。

## <a name="stock-properties-supported-by-the-add-property-wizard"></a><a name="_core_stock_properties_supported_by_classwizard"></a>プロパティの追加ウィザードでサポートされるストック プロパティ

この`COleControl`クラスは、9 つのストック プロパティを提供します。 プロパティの追加ウィザードを使用して、必要なプロパティを追加できます。

|プロパティ|ディスパッチ マップ エントリ|値にアクセスする方法|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE( )|として`m_sAppearance`アクセスできる値。|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR( )|を呼び出`GetBackColor`すことによってアクセスできる値。|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE( )|として`m_sBorderStyle`アクセスできる値。|
|`Caption`|DISP_STOCKPROP_CAPTION( )|を呼び出`InternalGetText`すことによってアクセスできる値。|
|`Enabled`|DISP_STOCKPROP_ENABLED( )|として`m_bEnabled`アクセスできる値。|
|`Font`|DISP_STOCKPROP_FONT( )|「MFC [ActiveX コントロール: フォントを使用して](../mfc/mfc-activex-controls-using-fonts.md)使用する」を参照してください。|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR( )|を呼び出`GetForeColor`すことによってアクセスできる値。|
|`hWnd`|DISP_STOCKPROP_HWND( )|として`m_hWnd`アクセスできる値。|
|`Text`|DISP_STOCKPROP_TEXT( )|を呼び出`InternalGetText`すことによってアクセスできる値。 このプロパティは、 と`Caption`同じですが、プロパティ名は除きます。|
|`ReadyState`|DISP_STOCKPROP_READYSTATE()|またはとして`m_lReadyState`アクセスできる値`GetReadyState`|

## <a name="stock-properties-and-notification"></a><a name="_core_stock_properties_and_notification"></a>ストックプロパティと通知

ほとんどのストック プロパティには、オーバーライドできる通知関数があります。 たとえば、プロパティが`BackColor`変更されるたびに、`OnBackColorChanged`関数 (コントロール クラスのメンバー関数) が呼び出されます。 既定の実装 (`COleControl`で`InvalidateControl`の ) は を呼び出します。 この状況に対応して追加のアクションを実行する場合は、この関数をオーバーライドします。

## <a name="color-properties"></a><a name="_core_color_properties"></a>色のプロパティ

コントロールを描画するときに、`ForeColor`ストック`BackColor`とプロパティ、または独自のカスタムカラープロパティを使用できます。 色のプロパティを使用するには、呼び出します[。](../mfc/reference/colecontrol-class.md#translatecolor) この関数のパラメーターは、color プロパティの値とオプションのパレット ハンドルです。 戻り値は、および などの`SetTextColor`GDI 関数に渡すことができる**COLORREF** `CreateSolidBrush`値です。

ストック`ForeColor`と`BackColor`プロパティのカラー値は、`GetForeColor`または`GetBackColor`関数をそれぞれ呼び出すことによってアクセスされます。

コントロールを描画するときに、これら 2 つの色プロパティを使用する例を次に示します。 一時的な**COLORREF**変数とオブジェクト`CBrush`を初期化し、`TranslateColor`一方は`ForeColor`プロパティを使用し、もう`BackColor`1 つはプロパティを使用して呼び出しを行います。 一時`CBrush`オブジェクトは、コントロールの四角形を描画するために使用され、テキストの色は、プロパティを`ForeColor`使用して設定されます。

[!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール : プロパティ](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl クラス](../mfc/reference/colecontrol-class.md)
