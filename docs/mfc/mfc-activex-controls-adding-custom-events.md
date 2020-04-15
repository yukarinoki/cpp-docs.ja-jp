---
title: 'MFC ActiveX コントロール : カスタム イベントの追加'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], events [MFC]
- EVENT_CUSTOM prefix [MFC]
- custom events [MFC], adding to ActiveX controls
- EVENT_CUSTOM macro [MFC]
- InCircle method [MFC]
- ClickIn event
- FireClickIn event
- COleControl class [MFC], custom events [MFC]
- Click event, custom events [MFC]
- events [MFC], ActiveX controls
- custom events [MFC]
- FireEvent method, adding custom events
ms.assetid: c584d053-1e34-47aa-958e-37d3e9b85892
ms.openlocfilehash: 8d464e5d7c9731e158e44d66d569fd1555401e17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364730"
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC ActiveX コントロール : カスタム イベントの追加

カスタム イベントは、クラス`COleControl`によって自動的に発生しないという点で、ストック イベントとは異なります。 カスタム イベントは、コントロール開発者によって決定された特定のアクションをイベントとして認識します。 カスタム イベントのイベント マップ エントリは、EVENT_CUSTOM マクロによって表されます。 次のセクションでは、ActiveX コントロール ウィザードを使用して作成された ActiveX コントロール プロジェクトのカスタム イベントを実装します。

## <a name="adding-a-custom-event-with-the-add-event-wizard"></a><a name="_core_adding_a_custom_event_with_classwizard"></a>イベント追加ウィザードを使用したカスタムイベントの追加

次の手順では、特定のカスタム イベント ClickIn を追加します。 この手順を使用して、他のカスタム イベントを追加できます。 ClickIn イベントの名前とパラメーターをカスタム イベント名とパラメーターに置き換えます。

#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>イベント追加ウィザードを使用して ClickIn カスタム イベントを追加するには

1. コントロールのプロジェクトを読み込みます。

1. **[クラス ビュー**] で ActiveX コントロール クラスを右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**イベントの追加**] をクリックします。

   これにより、イベントの追加ウィザードが開きます。

1. [**イベント名**] ボックスで、まず既存のイベントを選択し、[**カスタム**] ラジオ ボタンをクリックしてから *、「ClickIn」* と入力します。

1. [**内部名**] ボックスに、イベントの起動関数の名前を入力します。 この例では、イベント追加ウィザード ( )`FireClickIn`で提供される既定値を使用します。

1. [パラメーター名]**コントロールと***[パラメーター*の型] コントロールを使用して *、xCoord* ( OLE_XPOS_PIXELS 型 ) と呼ばれる**パラメーター**を追加します。

1. *yCoord*と呼ばれる 2 番目のパラメータを追加します *(OLE_YPOS_PIXELS*と入力します)。

1. [**完了] を**クリックしてイベントを作成します。

## <a name="add-event-wizard-changes-for-custom-events"></a><a name="_core_classwizard_changes_for_custom_events"></a>カスタム イベントのイベント ウィザードの変更の追加

カスタム イベントを追加すると、イベントの追加ウィザードによってコントロール クラス が変更されます。H。CPP と .IDL ファイル。 ClickIn イベントに固有のコード サンプルを次に示します。

ヘッダー (.コントロールクラスの H) ファイル:

[!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]

このコードは、イベントの追加ウィザードを`FireClickIn`使用して定義した ClickIn イベントとパラメーターを使用して[COleControl::FireEvent](../mfc/reference/colecontrol-class.md#fireevent)を呼び出すインライン関数を宣言します。

さらに、実装内のコントロールのイベント マップに次の行が追加されます (.コントロール クラスの CPP) ファイル:

[!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]

このコードは、イベント ClickIn をインライン関数`FireClickIn`にマップし、イベントの追加ウィザードを使用して定義したパラメーターを渡します。

最後に、次の行がコントロールの に追加されます。IDL ファイル:

[!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]

この行は、ClickIn イベントに、イベント追加ウィザードのイベントリスト内のイベントの位置から取得された特定の ID 番号を割り当てます。 イベントリストのエントリにより、コンテナはイベントを予測できます。 たとえば、イベントが発生したときに実行されるハンドラー コードを提供する場合があります。

## <a name="calling-fireclickin"></a><a name="_core_calling_fireclickin"></a>ファイアクリックインの呼び出し

イベントの追加ウィザードを使用して ClickIn カスタム イベントを追加したので、このイベントをいつ起動するかを決定する必要があります。 これは、適切なアクション`FireClickIn`が発生したときに呼び出すことによって行います。 この説明では、ユーザーが円形または`InCircle`楕円形の`WM_LBUTTONDOWN`領域内をクリックしたときに ClickIn イベントを発生させるメッセージ ハンドラー内の関数を使用します。 次の手順では、`WM_LBUTTONDOWN`ハンドラーを追加します。

#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>イベント追加ウィザードを使用してメッセージ ハンドラーを追加するには

1. コントロールのプロジェクトを読み込みます。

1. **クラス ビュー**で、ActiveX コントロール クラスを選択します。

1. **[プロパティ]** ウィンドウに、ActiveX コントロールで処理できるメッセージの一覧が表示されます。 太字で示されているメッセージには、ハンドラー関数が割り当てられています。

1. 処理するメッセージを選択します。 この例では、`WM_LBUTTONDOWN`を選択します。

1. 右側のドロップダウン リスト ボックスで**\<、[OnLButtonDown に追加>** を選択します。

1. **クラス ビュー**で新しいハンドラー関数をダブルクリックして、実装内のメッセージ ハンドラー コードにジャンプします (.ActiveX コントロールの CPP) ファイル。

次のコード サンプルでは`InCircle`、コントロール ウィンドウ内でマウスの左ボタンがクリックされるたびに関数を呼び出します。 このサンプルは`WM_LBUTTONDOWN`[、Circ](../overview/visual-cpp-samples.md)サンプルの抽象`OnLButtonDown`で、ハンドラー関数 の で見つけることができます。

[!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]

> [!NOTE]
> イベント追加ウィザードでマウス ボタンアクションのメッセージ ハンドラーが作成されると、基本クラスの同じメッセージ ハンドラーの呼び出しが自動的に追加されます。 この呼び出しは削除しないでください。 コントロールでストック マウス メッセージのいずれかを使用する場合は、マウス キャプチャが適切に処理されるように、基本クラスのメッセージ ハンドラーを呼び出す必要があります。

次の例では、コントロール内の円形または楕円形の領域内でクリックが発生した場合にのみイベントが発生します。 この動作を実現するには、コントロールの`InCircle`実装に関数を配置します (.CPP) ファイル:

[!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]

また、次の関数宣言を`InCircle`コントロールのヘッダー (.H) ファイル:

[!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]

## <a name="custom-events-with-stock-names"></a><a name="_core_custom_events_with_stock_names"></a>株式名を持つカスタム イベント

ストックイベントと同じ名前のカスタムイベントを作成できますが、同じコントロールに両方を実装することはできません。 たとえば、通常は株価イベント Click が発生したときに起動しない Click というカスタム イベントを作成できます。 その後、いつでもその起動関数を呼び出して Click イベントを起動できます。

次の手順では、カスタムの Click イベントを追加します。

#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>ストック イベント名を使用するカスタム イベントを追加するには

1. コントロールのプロジェクトを読み込みます。

1. **[クラス ビュー**] で ActiveX コントロール クラスを右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**イベントの追加**] をクリックします。

   これにより、イベントの追加ウィザードが開きます。

1. [**イベント名]** ドロップダウン リストで、ストック イベント名を選択します。 この例では、 **[ クリック**] を選択します。

1. [**イベントの種類]** で [**カスタム**] を選択します。

1. [**完了] を**クリックしてイベントを作成します。

1. コード`FireClick`内の適切な場所で呼び出します。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl クラス](../mfc/reference/colecontrol-class.md)
