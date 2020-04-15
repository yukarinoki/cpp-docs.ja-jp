---
title: 'ActiveX コントロール コンテナー : ActiveX コントロールで発生したイベントの処理'
ms.date: 09/12/2018
helpviewer_keywords:
- event handlers [MFC], ActiveX controls
- ActiveX control containers [MFC], event sinks
- event handling [MFC], ActiveX controls
- ON_EVENT macro [MFC]
- ActiveX controls [MFC], events [MFC]
- END_EVENTSINK_MAP macro, using
- events [MFC], ActiveX controls
- BEGIN_EVENTSINK_MAP macro
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
ms.openlocfilehash: ae623ee0973e78db3b542646dd6bdec58cc2dfc8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367952"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX コントロール コンテナー : ActiveX コントロールで発生したイベントの処理

この資料では **、ActiveX**コントロール コンテナーに ActiveX コントロールのイベント ハンドラーをインストールする **[プロパティ]** ウィンドウ (クラス ビュー) を使用する方法について説明します。 イベント ハンドラーは、特定のイベントの通知を (コントロールから) 受信し、応答として何らかのアクションを実行するために使用されます。 この通知は、イベントを 「発生」と呼びます。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

> [!NOTE]
> この記事では、プロシージャとコードの例として、Container という名前のダイアログ ベースの ActiveX コントロール コンテナー プロジェクトと Circ という名前の埋め込みコントロールを使用します。

[**プロパティ**] ウィンドウ (**クラス ビュー**) の [イベント] ボタンを使用すると、ActiveX コントロール コンテナー アプリケーションで発生する可能性のあるイベントのマップを作成できます。 このマップは、"イベント シンク マップ" と呼ばれ、Visual C++ によって作成され、コントロール コンテナー クラスにイベント ハンドラーを追加するときに管理されます。 イベント マップ エントリを使用して実装された各イベント ハンドラーは、特定のイベントをコンテナー イベント ハンドラーのメンバー関数にマップします。 このイベント ハンドラー関数は、指定されたイベントが ActiveX コントロール オブジェクトによって発生したときに呼び出されます。

イベント シンク マップの詳細については、『クラス ライブラリ リファレンス』の[「イベント シンク マップ](../mfc/reference/event-sink-maps.md)」を*参照してください*。

## <a name="event-handler-modifications-to-the-project"></a><a name="_core_event_handler_modifications_to_the_project"></a>プロジェクトに対するイベント ハンドラの変更

**[プロパティ]** ウィンドウを使用してイベント ハンドラーを追加すると、イベント シンク マップが宣言され、プロジェクトで定義されます。 次のステートメントがコントロールに追加されます。CPP ファイルは、イベント ハンドラーが最初に追加された時に発生します。 このコードは、ダイアログ ボックス クラスのイベント シンク マップを宣言します`CContainerDlg`(この場合は次のようになります)。

[!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

**[プロパティ]** ウィンドウを使用してイベントを追加すると、イベント`ON_EVENT`マップ エントリ ( ) がイベント シンク マップに追加され、イベント ハンドラー関数がコンテナーの実装 ( ) に追加されます。CPP) ファイル。

次の例では、Circ コントロール`OnClickInCircCtrl``ClickIn`のイベントに対して、 というイベント ハンドラーを宣言します。

[!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

さらに、次のテンプレートがクラスの`CContainerDlg`実装に追加されます (.イベント ハンドラ メンバー関数の CPP) ファイル:

[!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

イベント シンク マクロの詳細については、「クラス ライブラリ リファレンス」の[「イベント シンク マップ](../mfc/reference/event-sink-maps.md)」を*参照してください*。

#### <a name="to-create-an-event-handler-function"></a>イベント ハンドラー関数を作成するには

1. クラス ビューから、ActiveX コントロールを含むダイアログ クラスを選択します。 この例では、`CContainerDlg`を使用します。

1. **[プロパティ]** ウィンドウで、 **[イベント]** ボタンをクリックします。

1. **[プロパティ]** ウィンドウで、埋め込まれた ActiveX コントロールのコントロール ID を選択します。 この例では、`IDC_CIRCCTRL1`を使用します。

   **[プロパティ]** ウィンドウには、埋め込まれた ActiveX コントロールによって発生できるイベントの一覧が表示されます。 太字で示されているメンバー関数には、ハンドラー関数が既に割り当てられています。

1. ダイアログ クラスで処理するイベントを選択します。 この例では、 **[ クリック**] を選択します。

1. 右側のドロップダウン リスト ボックスで、[**\<クリックキルカ1 の追加>** を選択します。

1. クラス ビューから新しいハンドラー関数をダブルクリックして、実装内のイベント ハンドラー コードにジャンプします (.の CPP)`CContainerDlg`ファイル。

## <a name="see-also"></a>関連項目

[ActiveX コントロール コンテナ](../mfc/activex-control-containers.md)
