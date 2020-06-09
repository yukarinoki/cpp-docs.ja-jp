---
title: 'MFC ActiveX コントロール : ActiveX コントロールへのストック イベントの追加'
ms.date: 11/04/2016
f1_keywords:
- EVENT__STOCK_ERROR
- EVENT__STOCK_READYSTATECHANGE
- ReadyStateChange
- EVENT__STOCK_MOUSEMOVE
- EVENT__STOCK_MOUSEUP
- EVENT__STOCK_DBLCLICK
- KeyPress
- EVENT__STOCK_KEYDOWN
- EVENT__STOCK
- EVENT__STOCK_MOUSEDOWN
- EVENT__STOCK_KEYPRESS
- EVENT__STOCK_CLICK
- EVENT__STOCK_KEYUP
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- KeyPress event
- FireDblClick event
- FireMouseDown event
- events [MFC], stock
- FireKeyPress event
- EVENT_STOCK_MOUSEMOVE event
- EVENT_STOCK_CLICK event
- FireClick event
- FireKeyUp event
- FireMouseUp event
- EVENT_STOCK_ERROREVENT event
- EVENT_STOCK_KEYDOWN event
- EVENT_STOCK_MOUSEDOWN event
- EVENT_STOCK_KEYPRESS macro [MFC]
- EVENT_STOCK_KEYUP event
- EVENT_STOCK_DBLCLICK event
- FireError event
- FireKeyDown event
- ReadyStateChange event
- EVENT_STOCK_MOUSEUP event
- FireMouseMove event
- EVENT_STOCK prefix
- EVENT_STOCK_READYSTATECHANGE event
- EVENT_STOCK_KEYPRESS event
ms.assetid: 3eeadc67-4b3d-4444-8caa-53054073988a
ms.openlocfilehash: a97c08baaf3c11b0436e52bb4fd4ac380999d69a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615590"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールへのストック イベントの追加

Stock イベントは[、クラスに](reference/colecontrol-class.md)よって自動的に起動されるという点でカスタムイベントとは異なります。 `COleControl`一般的なアクションによって生成されるイベントを発生させる定義済みのメンバー関数が含まれています。 によって実装される一般的なアクションに `COleControl` は、コントロール、キーボードイベント、およびマウスボタンの状態の変化が含まれます。 Stock イベントのイベントマップエントリの前には、常に EVENT_STOCK プレフィックスが付きます。

## <a name="stock-events-supported-by-the-add-event-wizard"></a><a name="_core_stock_events_supported_by_classwizard"></a>イベントの追加ウィザードでサポートされるストックイベント

`COleControl`クラスは、次の表に示すように、10個の株価イベントを提供します。 [イベントの追加ウィザード](../ide/add-event-wizard.md)を使用して、コントロールに必要なイベントを指定できます。

### <a name="stock-events"></a>株式イベント

|Event|関数の起動|コメント|
|-----------|---------------------|--------------|
|ここを|**void 焼討 Click ()**|コントロールがマウスをキャプチャしたときに、 **Buttonup** (左、中央、または右) のメッセージを受信したときに、コントロール上でボタンが解放されたときに発生します。 このイベントの前に、stock MouseDown イベントと MouseUp イベントが発生します。<br /><br /> イベントマップエントリ: **EVENT_STOCK_CLICK ()**|
|DblClick|**void 焼討 Dblclick ()**|Click に似ていますが、 **BUTTONDBLCLK**メッセージを受信したときに発生しました。<br /><br /> イベントマップエントリ: **EVENT_STOCK_DBLCLICK ()**|
|エラー|**void の消火エラー (scode***scode* **, LPCSTR** `lpszDescription` **, UINT** `nHelpID` **= 0)**        |ActiveX コントロール内で、メソッド呼び出しまたはプロパティアクセスのスコープ外でエラーが発生した場合に発生します。<br /><br /> イベントマップエントリ: **EVENT_STOCK_ERROREVENT ()**|
|KeyDown|**void の消火 keydown (short** `nChar` **、short** `nShiftState` **)**      |`WM_SYSKEYDOWN`またはメッセージを受信したときに発生 `WM_KEYDOWN` します。<br /><br /> イベントマップエントリ: **EVENT_STOCK_KEYDOWN ()**|
|System.windows.forms.control.keypress>|**void の焼討 keypress (short** <strong>\*</strong> `pnChar`**)**    |メッセージを受信したときに発生 `WM_CHAR` します。<br /><br /> イベントマップエントリ: **EVENT_STOCK_KEYPRESS ()**|
|KeyUp|**void の消火の keyup (short** `nChar` **、short** `nShiftState` **)**      |`WM_SYSKEYUP`またはメッセージを受信したときに発生 `WM_KEYUP` します。<br /><br /> イベントマップエントリ: **EVENT_STOCK_KEYUP ()**|
|MouseDown|**void 焼討 mousedown (short** `nButton` **、short** `nShiftState` **、float***x* **、float***y***)**          |任意の**Buttondown** (左、中央、または右) が受信された場合に発生します。 このイベントが発生する直前にマウスがキャプチャされます。<br /><br /> イベントマップエントリ: **EVENT_STOCK_MOUSEDOWN ()**|
|Mouseup|**void の消火 mousemove (short** `nButton` **、short** `nShiftState` **、float***x* **、float***y***)**          |WM_MOUSEMOVE メッセージを受信したときに発生します。<br /><br /> イベントマップエントリ: **EVENT_STOCK_MOUSEMOVE ()**|
|対する|**void の消火の mouseup (short** `nButton` **、short** `nShiftState` **、float***x* **、float***y***)**          |任意の**Buttonup** (左、中央、または右) が受信された場合に発生します。 このイベントが発生する前に、マウスキャプチャが解放されます。<br /><br /> イベントマップエントリ: **EVENT_STOCK_MOUSEUP ()**|
|ReadyStateChange|**void FireReadyStateChange ()**|受信したデータ量が原因で、コントロールが次の準備完了状態に遷移したときに発生します。<br /><br /> イベントマップエントリ: **EVENT_STOCK_READYSTATECHANGE ()**|

## <a name="adding-a-stock-event-using-the-add-event-wizard"></a><a name="_core_adding_a_stock_event_using_classwizard"></a>イベントの追加ウィザードを使用したストックイベントの追加

ストックイベントの追加は、基本クラスのによって自動的に処理されるため、カスタムイベントを追加する場合よりも作業が少なくなり `COleControl` ます。 次の手順では、 [MFC ActiveX コントロールウィザード](reference/mfc-activex-control-wizard.md)を使用して開発されたコントロールに stock イベントを追加します。 KeyPress というイベントは、キーが押されていて、コントロールがアクティブなときに呼び出されます。 この手順は、他のストックイベントの追加にも使用できます。 選択したストックイベント名を KeyPress に置き換えます。

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>イベントの追加ウィザードを使用して KeyPress ストックイベントを追加するには

1. コントロールのプロジェクトを読み込みます。

1. クラスビューで、ActiveX コントロールクラスを右クリックしてショートカットメニューを開きます。

1. ショートカットメニューの [**追加**] をクリックし、[**イベントの追加**] をクリックします。

   イベントの追加ウィザードが開きます。

1. [**イベント名**] ボックスの一覧で、を選択し `KeyPress` ます。

1. **[完了]** をクリックします。

## <a name="add-event-wizard-changes-for-stock-events"></a><a name="_core_classwizard_changes_for_stock_events"></a>ストックイベントのイベントの追加ウィザードの変更

Stock イベントはコントロールの基本クラスによって処理されるため、イベントの追加ウィザードでは、クラス宣言は何の方法でも変更されません。 イベントがコントロールのイベントマップに追加され、にエントリが作成されます。IDL ファイル。 次の行がコントロールのイベントマップに追加されます。コントロールクラスの実装 () にあります。CPP) ファイル:

[!code-cpp[NVC_MFC_AxUI#5](codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

このコードを追加すると、WM_CHAR メッセージが受信され、コントロールがアクティブになったときに KeyPress イベントが発生します。 KeyPress イベントは、 `FireKeyPress` コントロールコード内からその起動関数 (など) を呼び出すことによって、他のタイミングで起動できます。

イベントの追加ウィザードは、次のコード行をコントロールのに追加します。IDL ファイル:

[!code-cpp[NVC_MFC_AxUI#6](codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

この行は、KeyPress イベントとその標準ディスパッチ ID を関連付け、コンテナーが KeyPress イベントを予測できるようにします。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: メソッド](mfc-activex-controls-methods.md)<br/>
[COleControl クラス](reference/colecontrol-class.md)
