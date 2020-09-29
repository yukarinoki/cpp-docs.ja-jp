---
title: 'MFC ActiveX コントロール: フォントの使用'
ms.date: 11/19/2018
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
helpviewer_keywords:
- notifications [MFC], MFC ActiveX controls fonts
- OnDraw method, MFC ActiveX controls
- InternalFont method [MFC]
- SetFont method [MFC]
- OnFontChanged method [MFC]
- IPropertyNotifySink class [MFC]
- MFC ActiveX controls [MFC], fonts
- Stock Font property [MFC]
- HeadingFont property [MFC]
- GetFont method [MFC]
- SelectStockFont method [MFC]
- fonts [MFC], ActiveX controls
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
ms.openlocfilehash: 02c52d2544afdc9d13fc3ec67ad9eed757a3f277
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499696"
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC ActiveX コントロール: フォントの使用

ActiveX コントロールにテキストが表示されている場合は、コントロールユーザーがフォントプロパティを変更して、テキストの外観を変更できるようにすることができます。 フォントプロパティは、フォントオブジェクトとして実装され、stock または custom の2種類のいずれかになります。 ストックフォントプロパティは、プロパティの追加ウィザードを使用して追加できる、事前に実装されたフォントプロパティです。 カスタムフォントプロパティは事前に実装されていないため、コントロール開発者はプロパティの動作と使用法を決定します。

この記事では、次のトピックについて説明します。

- [ストックフォントプロパティの使用](#_core_using_the_stock_font_property)

- [コントロールでカスタムフォントプロパティを使用する](#_core_implementing_a_custom_font_property)

## <a name="using-the-stock-font-property"></a><a name="_core_using_the_stock_font_property"></a> ストックフォントプロパティの使用

ストックフォントプロパティは、クラスによってクラスによって事前に実装され [ています](reference/colecontrol-class.md)。 また、標準のフォントプロパティページも使用できるため、ユーザーは、名前、サイズ、スタイルなど、フォントオブジェクトのさまざまな属性を変更できます。

の [Getfont](reference/colecontrol-class.md#getfont)、 [SetFont](reference/colecontrol-class.md#setfont)、および [internalgetfont](reference/colecontrol-class.md#internalgetfont) 関数を使用して、フォントオブジェクトにアクセスし `COleControl` ます。 コントロールユーザーは、 `GetFont` `SetFont` 他の Get/Set プロパティと同じ方法で、および関数を使用して、フォントオブジェクトにアクセスします。 コントロール内から font オブジェクトへのアクセスが必要な場合は、関数を使用し `InternalGetFont` ます。

[「MFC ActiveX コントロール: プロパティ](mfc-activex-controls-properties.md)」で説明したように、プロパティの[追加ウィザード](../ide/adding-a-property-visual-cpp.md#names-add-property-wizard)を使用すると、ストックプロパティを簡単に追加できます。 [フォント] プロパティを選択すると、プロパティの追加ウィザードによって、ストックフォントエントリがコントロールのディスパッチマップに自動的に挿入されます。

#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してストックフォントプロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカットメニューの [ **追加** ] をクリックし、[ **プロパティの追加**] をクリックします。

   これにより、プロパティの追加ウィザードが開きます。

1. [ **プロパティ名** ] ボックスで、[ **フォント**] をクリックします。

1. **[完了]** をクリックします。

プロパティの追加ウィザードは、コントロールクラスの実装ファイルにあるコントロールのディスパッチマップに次の行を追加します。

[!code-cpp[NVC_MFC_AxFont#1](codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]

さらに、プロパティの追加ウィザードでは、次の行がコントロールに追加されます。IDL ファイル:

[!code-cpp[NVC_MFC_AxFont#2](codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]

Stock Caption プロパティは、ストックフォントプロパティ情報を使用して描画できるテキストプロパティの例です。 ストック Caption プロパティをコントロールに追加すると、ストックフォントプロパティに使用されている手順と同様の手順が使用されます。

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してストック Caption プロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカットメニューの [ **追加** ] をクリックし、[ **プロパティの追加**] をクリックします。

   これにより、プロパティの追加ウィザードが開きます。

1. [ **プロパティ名** ] ボックスで、[ **キャプション**] をクリックします。

1. **[完了]** をクリックします。

プロパティの追加ウィザードは、コントロールクラスの実装ファイルにあるコントロールのディスパッチマップに次の行を追加します。

[!code-cpp[NVC_MFC_AxFont#3](codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]

## <a name="modifying-the-ondraw-function"></a><a name="_core_modifying_the_ondraw_function"></a> OnDraw 関数の変更

の既定の実装では、 `OnDraw` コントロールに表示されるすべてのテキストに対して Windows システムフォントが使用されます。 これは、 `OnDraw` デバイスコンテキストに対して font オブジェクトを選択して、コードを変更する必要があることを意味します。 これを行うには、次の例に示すように、 [COleControl:: SelectStockFont](reference/colecontrol-class.md#selectstockfont) を呼び出して、コントロールのデバイスコンテキストを渡します。

[!code-cpp[NVC_MFC_AxFont#4](codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]

`OnDraw`フォントオブジェクトを使用するように関数を変更すると、コントロール内のテキストが、コントロールのストックフォントプロパティの特性と共に表示されます。

## <a name="using-custom-font-properties-in-your-control"></a><a name="_core_using_custom_font_properties_in_your_control"></a> コントロールでカスタムフォントプロパティを使用する

[ストックフォント] プロパティに加えて、ActiveX コントロールにはカスタムフォントプロパティを設定できます。 カスタムフォントプロパティを追加するには、次のことを行う必要があります。

- プロパティの追加ウィザードを使用して、カスタムフォントプロパティを実装します。

- [フォントの通知を処理](#_core_processing_font_notifications)しています。

- [新しいフォント通知インターフェイスを実装](#_core_implementing_a_new_font_notification_interface)しています。

### <a name="implementing-a-custom-font-property"></a><a name="_core_implementing_a_custom_font_property"></a> カスタムフォントプロパティの実装

カスタムフォントプロパティを実装するには、プロパティの追加ウィザードを使用してプロパティを追加し、コードにいくつかの変更を加えます。 次のセクションでは、サンプルコントロールにカスタムプロパティを追加する方法について説明し `HeadingFont` ます。

##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してカスタムフォントプロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカットメニューの [ **追加** ] をクリックし、[ **プロパティの追加**] をクリックします。

   これにより、プロパティの追加ウィザードが開きます。

1. [ **プロパティ名** ] ボックスに、プロパティの名前を入力します。 この例では、 **HeadingFont**を使用します。

1. **[実装型]** として、 **[Get/Set メソッド]** をクリックします。

1. [**プロパティの種類**] ボックスで、プロパティの型として [ **IDispatch** ] を選択し <strong>\*</strong> ます。

1. **[完了]** をクリックします。

プロパティの追加ウィザードによって、 `HeadingFont` カスタムプロパティをクラスとサンプルに追加するためのコードが作成され `CSampleCtrl` ます。IDL ファイル。 `HeadingFont`は Get/Set プロパティ型であるため、プロパティの追加ウィザードは `CSampleCtrl` クラスのディスパッチマップを変更して、DISP_PROPERTY_EX_ID[DISP_PROPERTY_EX](reference/dispatch-maps.md#disp_property_ex)マクロエントリを含めます。

[!code-cpp[NVC_MFC_AxFont#5](codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]

DISP_PROPERTY_EX マクロは、 `HeadingFont` プロパティ名を対応する `CSampleCtrl` クラス Get および Set メソッド、およびに関連付け `GetHeadingFont` `SetHeadingFont` ます。 プロパティ値の型も指定されます。この場合は、VT_FONT ます。

プロパティの追加ウィザードでは、コントロールヘッダーファイル () に宣言も追加されます。H) および関数の場合は、 `GetHeadingFont` `SetHeadingFont` コントロールの実装ファイル () に関数テンプレートを追加します。CPP):

[!code-cpp[NVC_MFC_AxFont#6](codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]

最後に、プロパティの追加ウィザードによってコントロールが変更されます。プロパティのエントリを追加して、IDL ファイルを追加し `HeadingFont` ます。

[!code-cpp[NVC_MFC_AxFont#7](codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]

### <a name="modifications-to-the-control-code"></a>制御コードに対する変更

コントロールにプロパティを追加したので `HeadingFont` 、新しいプロパティを完全にサポートするために、コントロールヘッダーおよび実装ファイルにいくつかの変更を加える必要があります。

コントロールヘッダーファイル (.H) で、プロテクトメンバー変数の次の宣言を追加します。

[!code-cpp[NVC_MFC_AxFont#8](codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]

コントロールの実装ファイル (「」を指定します。CPP) を実行し、次の操作を行います。

- コントロールコンストラクターの *m_fontHeading* を初期化します。

   [!code-cpp[NVC_MFC_AxFont#9](codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]

- フォントの既定の属性を含む静的な FONTDESC 構造体を宣言します。

   [!code-cpp[NVC_MFC_AxFont#10](codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]

- コントロール `DoPropExchange` メンバー関数で、関数の呼び出しを追加し `PX_Font` ます。 これにより、カスタムフォントプロパティの初期化と永続化が可能になります。

   [!code-cpp[NVC_MFC_AxFont#11](codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]

- コントロールメンバー関数の実装を完了 `GetHeadingFont` します。

   [!code-cpp[NVC_MFC_AxFont#12](codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]

- コントロールメンバー関数の実装を完了 `SetHeadingFont` します。

   [!code-cpp[NVC_MFC_AxFont#13](codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]

- `OnDraw`前に選択したフォントを保持する変数を定義するには、コントロールメンバー関数を変更します。

   [!code-cpp[NVC_MFC_AxFont#14](codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]

- `OnDraw`フォントが使用される場所に次の行を追加して、デバイスコンテキストにカスタムフォントを選択するように、コントロールメンバー関数を変更します。

   [!code-cpp[NVC_MFC_AxFont#15](codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]

- `OnDraw`フォントが使用された後に次の行を追加して、コントロールメンバー関数を変更して、以前のフォントをデバイスコンテキストに戻します。

   [!code-cpp[NVC_MFC_AxFont#16](codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]

カスタムフォントプロパティを実装した後、標準のフォントプロパティページを実装する必要があります。これにより、コントロールユーザーはコントロールの現在のフォントを変更できます。 標準フォントプロパティページのプロパティページ ID を追加するには、BEGIN_PROPPAGEIDS マクロの後に次の行を挿入します。

[!code-cpp[NVC_MFC_AxFont#17](codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]

また、BEGIN_PROPPAGEIDS マクロの count パラメーターを1つずつインクリメントする必要があります。 次の行に例を示します。

[!code-cpp[NVC_MFC_AxFont#18](codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]

これらの変更が行われた後、プロジェクト全体をリビルドして、追加の機能を組み込みます。

### <a name="processing-font-notifications"></a><a name="_core_processing_font_notifications"></a> フォント通知の処理

ほとんどの場合、コントロールは、フォントオブジェクトの特性が変更されたことを認識している必要があります。 各フォントオブジェクトは、によって実装されたインターフェイスのメンバー関数を呼び出すことによって変更されるときに、通知を提供 `IFontNotification` `COleControl` できます。

コントロールがストックフォントプロパティを使用している場合、その通知はのメンバー関数によって処理され `OnFontChanged` `COleControl` ます。 カスタムフォントプロパティを追加すると、同じ実装を使用できます。 前のセクションの例では、 *m_fontHeading*メンバー変数を初期化するときに &*m_xFontNotification*を渡すことによってこれを実現しました。

![複数のフォントオブジェクトインターフェイスの実装](../mfc/media/vc373q1.gif "複数のフォント オブジェクト インターフェイスの実装") <br/>
複数のフォント オブジェクト インターフェイスの実装

上の図の実線は、両方のフォントオブジェクトがの同じ実装を使用していることを示して `IFontNotification` います。 これにより、変更されたフォントを区別する必要がある場合に問題が発生する可能性があります。

コントロールのフォントオブジェクト通知を区別する方法の1つは、 `IFontNotification` コントロールの各フォントオブジェクトに対して、インターフェイスの個別の実装を作成することです。 この方法では、最近変更されたフォントを使用する文字列 (または文字列) のみを更新することで、描画コードを最適化できます。 次のセクションでは、2番目のフォントプロパティに個別の通知インターフェイスを実装するために必要な手順について説明します。 2番目のフォントプロパティは、 `HeadingFont` 前のセクションで追加したプロパティと見なされます。

### <a name="implementing-a-new-font-notification-interface"></a><a name="_core_implementing_a_new_font_notification_interface"></a> 新しいフォント通知インターフェイスの実装

2つ以上のフォントの通知を区別するには、コントロールで使用されるフォントごとに新しい通知インターフェイスを実装する必要があります。 以下のセクションでは、コントロールヘッダーおよび実装ファイルを変更して、新しいフォント通知インターフェイスを実装する方法について説明します。

### <a name="additions-to-the-header-file"></a>ヘッダーファイルへの追加

コントロールヘッダーファイル (.H)、クラス宣言に次の行を追加します。

[!code-cpp[NVC_MFC_AxFont#19](codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]

これにより、というインターフェイスの実装が作成され `IPropertyNotifySink` `HeadingFontNotify` ます。 この新しいインターフェイスには、というメソッドが含まれてい `OnChanged` ます。

### <a name="additions-to-the-implementation-file"></a>実装ファイルへの追加

(コントロールコンストラクター内の) 見出しのフォントを初期化するコードで、&*m_xFontNotification* を &*m_xHeadingFontNotify*に変更します。 次のコードを追加します。

[!code-cpp[NVC_MFC_AxFont#20](codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]

`AddRef`インターフェイスの `Release` メソッドとメソッドは、 `IPropertyNotifySink` ActiveX コントロールオブジェクトの参照カウントを追跡します。 コントロールがインターフェイスポインターへのアクセスを取得すると、コントロールはを呼び出して、 `AddRef` 参照カウントをインクリメントします。 ポインターを使用してコントロールを終了すると、 `Release` `GlobalFree` グローバルメモリブロックを解放するために呼び出されるのとほぼ同じ方法で、が呼び出されます。 このインターフェイスの参照カウントがゼロになると、インターフェイスの実装は解放されます。 この例では、 `QueryInterface` 関数は特定のオブジェクトのインターフェイスへのポインターを返し `IPropertyNotifySink` ます。 この関数を使用すると、ActiveX コントロールはオブジェクトを照会して、サポートされているインターフェイスを特定できます。

これらの変更がプロジェクトに加えられた後、プロジェクトをリビルドし、テストコンテナーを使用してインターフェイスをテストします。 Test Container にアクセスする方法について詳しくは、「 [テスト コンテナーでのプロパティとイベントのテスト](testing-properties-and-events-with-test-container.md) 」をご覧ください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: ActiveX コントロールでの画像の使用](mfc-activex-controls-using-pictures-in-an-activex-control.md)<br/>
[MFC ActiveX コントロール: ストックプロパティページの使用](mfc-activex-controls-using-stock-property-pages.md)
