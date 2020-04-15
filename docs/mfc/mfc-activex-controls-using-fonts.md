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
ms.openlocfilehash: c336ec6c29b5478655ca8f19f71378a2b446ac64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358271"
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC ActiveX コントロール: フォントの使用

ActiveX コントロールにテキストが表示されている場合は、フォント プロパティを変更することで、コントロール のユーザーがテキストの外観を変更できます。 フォント プロパティはフォント オブジェクトとして実装され、ストックまたはカスタムの 2 種類のいずれかになります。 ストック フォント プロパティは、プロパティの追加ウィザードを使用して追加できる、あらかじめ実装されたフォント プロパティです。 カスタム フォント プロパティは事前に実装されておらず、コントロール開発者はプロパティの動作と使用方法を決定します。

この記事では、次のトピックについて説明します。

- [ストック フォント プロパティの使用](#_core_using_the_stock_font_property)

- [コントロールでのカスタム フォント プロパティの使用](#_core_implementing_a_custom_font_property)

## <a name="using-the-stock-font-property"></a><a name="_core_using_the_stock_font_property"></a>ストック フォント プロパティの使用

ストック フォント プロパティは、クラス[COleControl](../mfc/reference/colecontrol-class.md)によって事前に実装されています。 また、標準のフォント プロパティ ページも使用でき、名前、サイズ、スタイルなど、フォント オブジェクトのさまざまな属性を変更できます。

フォント オブジェクトにアクセスするには、 の[関数を使用](../mfc/reference/colecontrol-class.md#getfont)してフォント を設定[し、](../mfc/reference/colecontrol-class.md#internalgetfont)フォントを取得します。 [SetFont](../mfc/reference/colecontrol-class.md#setfont) `COleControl` コントロール ユーザーは、 と 関数を`GetFont`使用`SetFont`して、他の Get/Set プロパティと同じ方法でフォント オブジェクトにアクセスします。 コントロール内からフォント オブジェクトへのアクセスが必要な場合は、この`InternalGetFont`関数を使用します。

[「MFC ActiveX コントロール: プロパティ](../mfc/mfc-activex-controls-properties.md)」で説明したように、ストック プロパティの追加は、[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)を使用して簡単に行うことができます。 Font プロパティを選択すると、プロパティの追加ウィザードによって、ストック Font エントリがコントロールのディスパッチ マップに自動的に挿入されます。

#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してストック フォント プロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

   これにより、プロパティの追加ウィザードが開きます。

1. [**プロパティ名]** ボックスの**一覧の [フォント**] をクリックします。

1. **[完了]** をクリックします。

プロパティの追加ウィザードは、コントロール クラス実装ファイル内のコントロールのディスパッチ マップに次の行を追加します。

[!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]

また、プロパティの追加ウィザードでは、次の行がコントロールに追加されます。IDL ファイル:

[!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]

ストックキャプションプロパティは、ストックFontプロパティ情報を使用して描画できるテキストプロパティの例です。 コントロールにストック キャプション プロパティを追加すると、ストック Font プロパティに使用される手順と同様の手順が使用されます。

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してストックキャプションプロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

   これにより、プロパティの追加ウィザードが開きます。

1. [**プロパティ名]** ボックスの一**覧の [標題**] をクリックします。

1. **[完了]** をクリックします。

プロパティの追加ウィザードは、コントロール クラス実装ファイル内のコントロールのディスパッチ マップに次の行を追加します。

[!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]

## <a name="modifying-the-ondraw-function"></a><a name="_core_modifying_the_ondraw_function"></a>OnDraw 関数の変更

の既定の`OnDraw`実装では、コントロールに表示されるすべてのテキストに Windows システム フォントが使用されます。 つまり、デバイス コンテキストにフォント`OnDraw`オブジェクトを選択してコードを変更する必要があります。 これを行うには、[次の例に示すように、COleControl::SelectStockFont](../mfc/reference/colecontrol-class.md#selectstockfont)を呼び出し、コントロールのデバイス コンテキストを渡します。

[!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]

フォント`OnDraw`オブジェクトを使用するように関数が変更されると、コントロール内のテキストがコントロールのストック Font プロパティの特性を持って表示されます。

## <a name="using-custom-font-properties-in-your-control"></a><a name="_core_using_custom_font_properties_in_your_control"></a>コントロールでのカスタム フォント プロパティの使用

ストック Font プロパティに加えて、ActiveX コントロールはカスタム フォント プロパティを持つことができます。 カスタム フォント プロパティを追加するには、次の操作を行う必要があります。

- プロパティの追加ウィザードを使用して、カスタム Font プロパティを実装します。

- [フォント通知の処理](#_core_processing_font_notifications):

- [新しいフォント通知インターフェイスを実装](#_core_implementing_a_new_font_notification_interface)する。

### <a name="implementing-a-custom-font-property"></a><a name="_core_implementing_a_custom_font_property"></a>カスタム フォント プロパティの実装

カスタム Font プロパティを実装するには、プロパティの追加ウィザードを使用してプロパティを追加し、コードにいくつかの変更を加えます。 次のセクションでは、カスタム`HeadingFont`プロパティを Sample コントロールに追加する方法について説明します。

##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してカスタム Font プロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

   これにより、プロパティの追加ウィザードが開きます。

1. [**プロパティ名]** ボックスに、プロパティの名前を入力します。 この例では、**見出しフォント**を使用します。

1. **[実装型]** として、 **[Get/Set メソッド]** をクリックします。

1. [**プロパティの種類]** ボックスで、プロパティの型に対して **[IDispatch]**<strong>\*</strong>を選択します。

1. **[完了]** をクリックします。

プロパティの追加ウィザードは、`HeadingFont``CSampleCtrl`カスタム プロパティをクラスおよび SAMPLE に追加するコードを作成します。IDL ファイル。 Get/Set プロパティの種類であるため`HeadingFont`、プロパティの追加ウィザードは`CSampleCtrl`、DISP_PROPERTY_EX_IDDISP_PROPERTY_EXマクロ エントリを含むようにクラスの[DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex)ディスパッチ マップを変更します。

[!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]

DISP_PROPERTY_EX マクロは、プロパティ`HeadingFont`名を対応する`CSampleCtrl`クラス Get メソッドと`GetHeadingFont`Set`SetHeadingFont`メソッド、および に関連付けます。 プロパティ値の型も指定します。この場合は、VT_FONT。

プロパティの追加ウィザードでは、コントロール ヘッダー ファイル (.H) 関数`GetHeadingFont`および`SetHeadingFont`関数の場合、その関数テンプレートをコントロール実装ファイル (.CPP):

[!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]

最後に、プロパティの追加ウィザードによってコントロールが変更されます。`HeadingFont`プロパティのエントリを追加して IDL ファイル:

[!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]

### <a name="modifications-to-the-control-code"></a>コントロール コードの変更

コントロールにプロパティを`HeadingFont`追加したので、新しいプロパティを完全にサポートするために、コントロール ヘッダーと実装ファイルを変更する必要があります。

コントロール ヘッダー ファイル (.H) を指定すると、プロテクト メンバー変数の宣言を次のように追加します。

[!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]

コントロール実装ファイル (.CPP)、次の操作を行います。

- コントロール コンストラクターで*m_fontHeading*を初期化します。

   [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]

- フォントのデフォルト属性を含む静的 FONTDESC 構造体を宣言します。

   [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]

- コントロール`DoPropExchange`メンバー関数で、関数への呼び出し`PX_Font`を追加します。 これにより、カスタムの Font プロパティの初期化と永続化が可能になります。

   [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]

- コントロール`GetHeadingFont`のメンバー関数の実装を完了します。

   [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]

- コントロール`SetHeadingFont`のメンバー関数の実装を完了します。

   [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]

- コントロール`OnDraw`のメンバー関数を変更して、以前に選択したフォントを保持する変数を定義します。

   [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]

- コントロール`OnDraw`のメンバー関数を変更して、フォントを使用する場所に次の行を追加して、デバイス コンテキストにカスタム フォントを選択します。

   [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]

- コントロール`OnDraw`のメンバー関数を変更して、フォントが使用された後に次の行を追加して、以前のフォントをデバイス コンテキストに戻します。

   [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]

カスタム Font プロパティを実装した後、標準の Font プロパティ ページを実装して、コントロールのユーザーがコントロールの現在のフォントを変更できるようにする必要があります。 標準のフォント プロパティ ページのプロパティ ページ ID を追加するには、BEGIN_PROPPAGEIDS マクロの後に次の行を挿入します。

[!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]

また、BEGIN_PROPPAGEIDSマクロの count パラメータも 1 ずつインクリメントする必要があります。 次の行に例を示します。

[!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]

これらの変更が行われた後、プロジェクト全体を再構築して追加機能を組み込みます。

### <a name="processing-font-notifications"></a><a name="_core_processing_font_notifications"></a>フォント通知の処理

ほとんどの場合、コントロールは、フォント オブジェクトの特性が変更されたタイミングを知る必要があります。 各フォント オブジェクトは、インターフェイスのメンバー関数を呼び出すことによって、変更されたときに`IFontNotification`通知を提供できます`COleControl`。

コントロールが stock Font プロパティを使用する場合、その通知`OnFontChanged`は`COleControl`のメンバー関数によって処理されます。 カスタム フォント プロパティを追加する場合、同じ実装を使用できます。 前のセクションの例では、m_fontHeading*メンバー変数*を初期化するときに *&m_xFontNotification*渡すことで、これを実現しました。

![複数のフォント オブジェクト インターフェイスの実装](../mfc/media/vc373q1.gif "複数のフォント オブジェクト インターフェイスの実装") <br/>
複数のフォント オブジェクト インターフェイスの実装

上の図の実線は、両方のフォントオブジェクトが同じ実装を`IFontNotification`使用していることを示しています。 これは、変更されたフォントを区別する場合に問題を引き起こす可能性があります。

コントロールのフォント オブジェクト通知を区別する 1 つの方法は、コントロール内の各`IFontNotification`フォント オブジェクトのインターフェイスの個別の実装を作成することです。 この手法を使用すると、最近変更したフォントを使用する文字列だけを更新して、描画コードを最適化できます。 次のセクションでは、2 つ目の Font プロパティに対して個別の通知インターフェイスを実装するために必要な手順を示します。 2 番目のフォント プロパティは、`HeadingFont`前のセクションで追加されたプロパティであると想定されます。

### <a name="implementing-a-new-font-notification-interface"></a><a name="_core_implementing_a_new_font_notification_interface"></a>新しいフォント通知インターフェイスの実装

複数のフォントの通知を区別するには、コントロールで使用されるフォントごとに新しい通知インターフェイスを実装する必要があります。 以降のセクションでは、コントロールヘッダーと実装ファイルを変更して、新しいフォント通知インタフェースを実装する方法について説明します。

### <a name="additions-to-the-header-file"></a>ヘッダー ファイルへの追加

コントロール ヘッダー ファイル (.H) をクラス宣言に次の行を追加します。

[!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]

これにより、 という`IPropertyNotifySink``HeadingFontNotify`インターフェイスの実装が作成されます。 この新しいインターフェイスには、`OnChanged`というメソッドが含まれています。

### <a name="additions-to-the-implementation-file"></a>実装ファイルへの追加

(コントロール コンストラクター内) の見出しフォントを初期化するコードで *、m_xFontNotification&* &*m_xHeadingFontNotify*に変更します。 次のコードを追加します。

[!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]

インターフェイスの`Release`and メソッドは`AddRef`、ActiveX コントロール オブジェクトの参照カウントを追跡します。 `IPropertyNotifySink` コントロールがインターフェイス ポインターへのアクセスを取得すると、コントロールは`AddRef`参照カウントをインクリメントするために呼び出します。 コントロールがポインターを使用して終了すると、グローバル`Release`メモリ ブロックを解放するために呼`GlobalFree`び出されるのとほぼ同じ方法で、コントロールが呼び出されます。 このインターフェイスの参照カウントが 0 になると、インターフェイスの実装を解放できます。 この例では、関数`QueryInterface`は特定のオブジェクトの`IPropertyNotifySink`インターフェイスへのポインターを返します。 この関数を使用すると、ActiveX コントロールはオブジェクトに対してクエリを実行して、サポートするインターフェイスを決定できます。

プロジェクトに対してこれらの変更が行われた後、プロジェクトを再構築し、テスト コンテナーを使用してインターフェイスをテストします。 Test Container にアクセスする方法について詳しくは、「 [テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md) 」をご覧ください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: ActiveX コントロールにおけるピクチャの使用](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)<br/>
[MFC ActiveX コントロール : ストック プロパティ ページの使用](../mfc/mfc-activex-controls-using-stock-property-pages.md)
