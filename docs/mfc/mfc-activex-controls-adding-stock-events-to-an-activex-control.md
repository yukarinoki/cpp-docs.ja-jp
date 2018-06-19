---
title: 'MFC ActiveX コントロール: ActiveX コントロールへのストック イベントの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 210749906391ccdba2e488b75be98264bcba39cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359339"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールへのストック イベントの追加
ストック イベントは、クラスによって自動的に呼び出される点で、カスタム イベントとは異なります。 [COleControl](../mfc/reference/colecontrol-class.md)です。 `COleControl` 定義済みのメンバー関数の一般的なアクションの結果として得られるイベントを発生させることがあります。 いくつかの一般的なアクションによって実装される`COleControl`に含める 1 つのシングル クリックやダブルクリック コントロール、キーボード イベント、および変更のマウス ボタンの状態。 ストック イベントのイベント マップ エントリには、必ず、 **EVENT_STOCK**プレフィックス。  
  
##  <a name="_core_stock_events_supported_by_classwizard"></a> ストック イベントでサポートされている、イベント追加ウィザード  
 `COleControl`クラスには、次の表に、10 個のストック イベントが用意されています。 使用して、コントロールの対象とするイベントを指定することができます、[イベント追加ウィザード](../ide/add-event-wizard.md)です。  
  
### <a name="stock-events"></a>ストック イベント  
  
|event|発生させる関数|コメント|  
|-----------|---------------------|--------------|  
|クリック|**FireClick に関するページ () を無効にします。**|コントロールが任意のマウスをキャプチャしたときに発生した**BUTTONUP** (左、中央、または右) のメッセージを受信し、コントロールの上、ボタンが離されました。 株価 MouseDown、MouseUp イベントは、このイベントの前に発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_CLICK に関するページ)**|  
|DblClick|**FireDblClick に関するページ () を無効にします。**|をクリックすると似ていますが発生したときに、 **BUTTONDBLCLK**メッセージを受信します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_DBLCLICK に関するページ)**|  
|Error|**FireError を無効にする (SCODE***scode* **、LPCSTR** `lpszDescription` **、UINT**`nHelpID`**= 0)** |メソッドの呼び出しまたはプロパティのアクセスのスコープ外で ActiveX コントロール内でエラーが発生したときに発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_ERROREVENT に関するページ)**|  
|KeyDown|**FireKeyDown を無効にする (短い**`nChar` **、短い**`nShiftState`**)** |発生したときに、`WM_SYSKEYDOWN`または`WM_KEYDOWN`メッセージを受信します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_KEYDOWN に関するページ)**|  
|Keypress イベント|**FireKeyPress を無効にする (短い\***`pnChar`**)** |発生したときに、`WM_CHAR`メッセージを受信します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_KEYPRESS に関するページ)**|  
|KeyUp|**FireKeyUp を無効にする (短い**`nChar` **、短い**`nShiftState`**)** |発生したときに、`WM_SYSKEYUP`または`WM_KEYUP`メッセージを受信します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_KEYUP に関するページ)**|  
|MouseDown|**FireMouseDown を無効にする (短い**`nButton` **、短い**`nShiftState` **、float***x* **、float** *y***)** |存在する場合に発生した**BUTTONDOWN** (左、中央、または右) を受信します。 このイベントが発生する直前に、マウスがキャプチャされます。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_MOUSEDOWN に関するページ)**|  
|MouseMove|**FireMouseMove を無効にする (短い**`nButton` **、短い**`nShiftState` **、float***x* **、float** *y***)** |発生したときに、`WM_MOUSEMOVE`メッセージを受信します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_MOUSEMOVE に関するページ)**|  
|MouseUp|**FireMouseUp を無効にする (短い**`nButton` **、短い**`nShiftState` **、float***x* **、float** *y***)** |存在する場合に発生した**BUTTONUP** (左、中央、または右) を受信します。 このイベントが発生する前に、マウスのキャプチャが解放されます。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_MOUSEUP に関するページ)**|  
|ReadyStateChange|**FireReadyStateChange に関するページ () を無効にします。**|受信データの量のため次の準備完了状態に移行するコントロールのときに発生します。<br /><br /> イベント マップ エントリ: **EVENT_STOCK_READYSTATECHANGE に関するページ)**|  
  
##  <a name="_core_adding_a_stock_event_using_classwizard"></a> ストック イベントを使用して、追加する、イベント追加ウィザード  
 実際のイベントの発生は、基底クラスによって自動的に処理されるため、カスタム イベントを追加するよりも処理量が少ないストック イベントを追加する必要があります`COleControl`です。 次の手順を使用して開発されたコントロールへのストック イベントの追加[MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)です。 KeyPress と呼ばれる、イベントは、キーが押され、コントロールがアクティブなときに発生します。 この手順は、その他のストック イベントを追加するも使用できます。 KeyPress のストック イベントの選択した名前に置き換えます。  
  
#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>イベントの追加ウィザードを使用して、KeyPress ストック イベントを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  クラス ビューでは、ショートカット メニューを開く、ActiveX コントロール クラスを右クリックします。  
  
3.  ショートカット メニューから **[追加]** をクリックし、**イベントの追加**です。  
  
     イベントの追加ウィザードが開きます。  
  
4.  **イベント名**ドロップダウン リストで、`KeyPress`です。  
  
5.  **[完了]** をクリックします。  
  
##  <a name="_core_classwizard_changes_for_stock_events"></a> ストック イベントのイベント ウィザードによる変更を追加します。  
 ストック イベントが処理されるため、コントロールの基底クラスによって、イベントの追加ウィザードに任意の方法でクラスの宣言は変更されません。 コントロールのイベントのマップにイベントを追加し、内のエントリは、そのします。IDL ファイルです。 次の行が、コントロール クラスの実装にある、コントロールのイベントのマップに追加 (です。Cpp):  
  
 [!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]  
  
 KeyPress イベントを発生させるこのコードを追加するときに、`WM_CHAR`とコントロールがアクティブでメッセージを受信します。 KeyPress イベントは起動処理関数を呼び出すことによって他のタイミングで起動されます (たとえば、 `FireKeyPress`) から、コントロールのコード内で。  
  
 イベントの追加ウィザードでは、コントロールの次のコード行を追加します。IDL ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]  
  
 この行 KeyPress イベントと関連付けて、標準のディスパッチ ID とコンテナーの KeyPress イベントに対応します。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)
