---
title: 'MFC ActiveX コントロール: カスタム イベントの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b82232b8f2ad7a5e3bc1ff8fed0e8a38b1a7d66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352532"
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC ActiveX コントロール : カスタム イベントの追加
カスタム イベントとは異なりストック イベントからクラスによって自動的に起動しません`COleControl`です。 カスタム イベントは、特定のアクション、イベントとして、コントロールの開発者によって決定を認識します。 カスタム イベントのイベントのマップ エントリがによって表される、`EVENT_CUSTOM`マクロです。 次のセクションでは、ActiveX コントロール ウィザードを使用して作成された ActiveX コントロール プロジェクトのカスタム イベントを実装します。  
  
##  <a name="_core_adding_a_custom_event_with_classwizard"></a> カスタム イベントを追加する、イベント追加ウィザード  
 次の手順では、特定のカスタム イベント ClickIn を追加します。 この手順を使用すると、その他のカスタム イベントを追加します。 カスタム イベントの名前と ClickIn イベントの名前およびパラメーターについては、そのパラメーターを置き換えてください。  
  
#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>イベントの追加ウィザードを使用して、ClickIn カスタム イベントを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  クラス ビューでは、ショートカット メニューを開く、ActiveX コントロール クラスを右クリックします。  
  
3.  ショートカット メニューから **[追加]** をクリックし、**イベントの追加**です。  
  
     イベントの追加ウィザードが開きます。  
  
4.  **イベント名**ボックスを最初に、既存のイベントを選択して、をクリックして、**カスタム**ラジオ ボタンをクリックし、入力`ClickIn`です。  
  
5.  **内部名**ボックスに、イベントの起動処理関数の名前を入力します。 この例では、イベントの追加ウィザードによって提供される既定値を使用 (`FireClickIn`)。  
  
6.  という名前のパラメーターを追加`xCoord`(型`OLE_XPOS_PIXELS`) を使用して、**パラメーター名**と**パラメーターの型**コントロール。  
  
7.  呼ばれる 2 番目のパラメーターを追加`yCoord`(型`OLE_YPOS_PIXELS`)。  
  
8.  をクリックして**完了**イベントを作成します。  
  
##  <a name="_core_classwizard_changes_for_custom_events"></a> カスタム イベントのイベント ウィザードによる変更を追加します。  
 カスタム イベントを追加するときに、追加イベント ウィザードによって、コントロール クラスにします。H、します。CPP とします。IDL ファイル。 次のコード サンプルは、ClickIn イベントに固有です。  
  
 次の行がヘッダーに追加されます (です。H)、コントロールのクラス ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]  
  
 このコードが呼び出されるインライン関数を宣言`FireClickIn`を呼び出す[COleControl::FireEvent](../mfc/reference/colecontrol-class.md#fireevent) ClickIn イベントとパラメーターを定義したイベントの追加ウィザードを使用します。  
  
 クラスの実装、コントロールのイベントのマップに次の行をさらに、追加 (です。コントロール クラスの CPP) ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]  
  
 このコードは、インライン関数に ClickIn イベントをマップ`FireClickIn`イベントの追加ウィザードを使用して定義したパラメーターを渡すことです。  
  
 最後に、次の行は、コントロールに追加されます。IDL ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]  
  
 この行は、ClickIn イベント イベントのイベントの追加ウィザード ボックスの一覧で、イベントの位置から取得する、特定の ID 番号を割り当てます。 イベント一覧内のエントリは、イベントに対応するためのコンテナーを使用できます。 たとえば、イベントが発生したときに実行されるハンドラー コードを提供、可能性があります。  
  
##  <a name="_core_calling_fireclickin"></a> FireClickIn を呼び出す  
 イベントの追加ウィザードを使用して、ClickIn カスタム イベントを追加すると、これで、このイベントが発生する場合を決定する必要があります。 呼び出すことによって、これを行う`FireClickIn`適切な操作が発生したとき。 ここでは、コントロールを使用して、`InCircle`関数、 `WM_LBUTTONDOWN` ClickIn イベントを円または楕円領域内に、ユーザーがクリックしたときに発生させるメッセージ ハンドラー。 次の手順を追加、`WM_LBUTTONDOWN`ハンドラー。  
  
#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>イベントの追加ウィザードでメッセージのハンドラーを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  クラス ビューでは、ActiveX コントロール クラスを選択します。  
  
3.  [プロパティ] ウィンドウ、**メッセージ**ボタンをクリックします。  
  
     [プロパティ] ウィンドウには、ActiveX コントロールによって処理できるメッセージの一覧が表示されます。 既に太字で表示されているメッセージには、それに割り当てられているハンドラー機能があります。  
  
4.  [プロパティ] ウィンドウから、処理するメッセージを選択します。 この例では、選択`WM_LBUTTONDOWN`です。  
  
5.  右側のドロップダウン リスト ボックスから選択**\<追加 > OnLButtonDown**です。  
  
6.  クラス ビュー、実装ではメッセージ ハンドラーのコードに移動することで、新しいハンドラー関数をダブルクリックして (です。ActiveX コントロールの CPP) ファイルです。  
  
 次のコード サンプルの呼び出し、 **InCircle**コントロール ウィンドウ内でマウスの左ボタンをクリックするたびに機能します。 このサンプルは含まれて、`WM_LBUTTONDOWN`ハンドラー関数`OnLButtonDown`で、 [Circ サンプル](../visual-cpp-samples.md)抽象です。  
  
 [!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]  
  
> [!NOTE]
>  イベントの追加ウィザードでは、マウス ボタンの動作についてのメッセージ ハンドラーを作成するとき、基本クラスの同じメッセージ ハンドラーへの呼び出しが自動的に追加します。 この呼び出しを削除しないでください。 を、コントロールがマウスのストック メッセージのいずれかを使用する場合は、マウスのキャプチャが適切に処理されることを確認する基本クラスのメッセージ ハンドラーを呼び出す必要があります。  
  
 次の例では、このイベントは、コントロール内の円または楕円領域内をクリックが発生したときにのみ発生します。 この動作を実現するために配置することができます、`InCircle`コントロールの実装内の関数 (です。Cpp):  
  
 [!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]  
  
 次の宣言を追加する必要がありますも、`InCircle`コントロールのヘッダーを関数 (です。H) ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]  
  
##  <a name="_core_custom_events_with_stock_names"></a> ストックの名前のカスタム イベント  
 ストック イベントとして同じ名前のカスタム イベントを作成するには、両方で同じコントロールを実装することができましていませんただしです。 たとえば、カスタム イベントは起動しませんストック イベントをクリックして通常に発生するという名前を作成することができます。 起動処理関数を呼び出すことによっていつでも Click イベントが発生する可能性があります。  
  
 次の手順の追加、カスタムのクリック イベント。  
  
#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>ストック イベントの名前を使用してカスタム イベントを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  クラス ビューでは、ショートカット メニューを開く、ActiveX コントロール クラスを右クリックします。  
  
3.  ショートカット メニューから **[追加]** をクリックし、**イベントの追加**です。  
  
     イベントの追加ウィザードが開きます。  
  
4.  **イベント名**ドロップダウン リストで、ストック イベント名を選択します。 この例では、選択**クリックして**です。  
  
5.  **イベントの種類****カスタム**です。  
  
6.  をクリックして**完了**イベントを作成します。  
  
7.  呼び出す`FireClick`コードの適切な場所にします。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)
