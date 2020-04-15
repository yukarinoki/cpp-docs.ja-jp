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
ms.openlocfilehash: 79cd4fc572e55c67cc5a2cfe3a00e04f2a4a7850
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364687"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールへのストック イベントの追加

ストック イベントは、クラス[COleControl](../mfc/reference/colecontrol-class.md)によって自動的に発生するという点で、カスタム イベントとは異なります。 `COleControl`には、一般的なアクションから発生するイベントを発生させる定義済みのメンバー関数が含まれています。 実装される`COleControl`一般的なアクションには、コントロールのシングル クリックとダブルクリック、キーボード イベント、マウス ボタンの状態の変更などがあります。 ストック イベントのイベント マップ エントリには、常に EVENT_STOCK プレフィックスが付きます。

## <a name="stock-events-supported-by-the-add-event-wizard"></a><a name="_core_stock_events_supported_by_classwizard"></a>イベント追加ウィザードでサポートされるストックイベント

この`COleControl`クラスは、次の表に示す 10 個のストック イベントを提供します。 イベント追加ウィザード を使用して、コントロールに必要な[イベント](../ide/add-event-wizard.md)を指定できます。

### <a name="stock-events"></a>ストックイベント

|Event|焼成機能|説明|
|-----------|---------------------|--------------|
|Click|**ボイドファイアクリック( )**|コントロールがマウスをキャプチャしたときに発生し **、BUTTONUP** (左、中央、または右) メッセージが受信され、ボタンがコントロール上で離されます。 このイベントの前に、ストックの MouseDown イベントと MouseUp イベントが発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_CLICK( )**|
|Dblclick|**ボイドファイアドブルクリック( )**|クリックと同様ですが **、BUTTONDBLCLK**メッセージを受信したときに発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_DBLCLICK( )**|
|エラー|**無効火災エラー(***SCODE スコード 、* **LPCSTR** `lpszDescription` **、UINT**`nHelpID`= 0 **)**        |メソッド呼び出しまたはプロパティ アクセスのスコープ外で ActiveX コントロール内でエラーが発生したときに発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_ERROREVENT( )**|
|KeyDown|**ボイドファイアキーダウン(短い**`nChar`**、短い**`nShiftState`**)**      |または`WM_KEYDOWN`メッセージ`WM_SYSKEYDOWN`を受信したときに発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_KEYDOWN( )**|
|Keypress|**ボイドファイアキープレス( ショート**<strong>\*</strong>`pnChar`**)**    |メッセージを`WM_CHAR`受信したときに発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_KEYPRESS( )**|
|KeyUp|**ボイドファイアキーアップ(短い**`nChar`**、短い**`nShiftState`**)**      |または`WM_KEYUP`メッセージ`WM_SYSKEYUP`を受信したときに発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_KEYUP( )**|
|Mousedown|**ボイド FireMouseDown(**`nButton`**短い 、 短い**`nShiftState`,**フロート***x* **, フロート***y***)**          |**ボタンダウン**(左、中央、または右)が受信された場合に発生します。 マウスは、このイベントが発生する直前にキャプチャされます。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_MOUSEDOWN( )**|
|Mousemove|**ボイド FireMouseMove(**`nButton`**短い 、 短い**`nShiftState`,**フロート***x* **, フロート***y***)**          |WM_MOUSEMOVE メッセージを受信したときに発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_MOUSEMOVE( )**|
|Mouseup|**ボイド FireMouseUp(短い**  `nButton` **、 ショート**  `nShiftState` **、 フロート**  *x* **、 フロート**  *y*  **)**|**BUTTONUP** (左、中央、または右) が受信された場合に発生します。 マウス キャプチャは、このイベントが発生する前に解放されます。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_MOUSEUP( )**|
|レディステートチェンジ|**ボイドファイアレディステートチェンジ/ )**|受信したデータ量が原因でコントロールが次の準備完了状態に遷移したときに発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_READYSTATECHANGE( )**|

## <a name="adding-a-stock-event-using-the-add-event-wizard"></a><a name="_core_adding_a_stock_event_using_classwizard"></a>イベント追加ウィザードを使用したストックイベントの追加

実際のイベントの発生は基本クラス によって自動的に処理されるため、ストック イベントの追加はカスタム イベントの`COleControl`追加よりも少ない作業が必要です。 次の手順では[、MFC ActiveX](../mfc/reference/mfc-activex-control-wizard.md)コントロール ウィザードを使用して開発されたコントロールにストック イベントを追加します。 KeyPress と呼ばれるイベントは、キーが押され、コントロールがアクティブなときに発生します。 この手順は、他のストックイベントを追加するためにも使用できます。 選択したストックイベント名を KeyPress に置き換えます。

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>イベント追加ウィザードを使用して KeyPress ストックイベントを追加するには

1. コントロールのプロジェクトを読み込みます。

1. クラス ビューで、ActiveX コントロール クラスを右クリックしてショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**イベントの追加**] をクリックします。

   これにより、イベントの追加ウィザードが開きます。

1. [**イベント名]** ドロップダウン リストで、[ `KeyPress`] を選択します。

1. **[完了]** をクリックします。

## <a name="add-event-wizard-changes-for-stock-events"></a><a name="_core_classwizard_changes_for_stock_events"></a>ストック イベントのイベント ウィザードの変更の追加

ストック イベントはコントロールの基本クラスによって処理されるため、イベントの追加ウィザードではクラス宣言が変更されることはありません。 コントロールのイベント マップにイベントを追加し、そのイベント マップにエントリを作成します。IDL ファイル。 コントロールのイベント マップに次の行が追加され、コントロール クラスの実装 () に配置されます。CPP) ファイル:

[!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

このコードを追加すると、WM_CHAR メッセージが受信され、コントロールがアクティブな場合に、KeyPress イベントが発生します。 KeyPress イベントは、コントロール コード内からその起動関数 (たとえば)`FireKeyPress`を呼び出すことによって、他の時間に発生させることができます。

イベントの追加ウィザードは、コントロールの コードの次の行を追加します。IDL ファイル:

[!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

この行は、KeyPress イベントを標準ディスパッチ ID に関連付け、コンテナが KeyPress イベントを予測できるようにします。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl クラス](../mfc/reference/colecontrol-class.md)
