---
title: 'ActiveX コントロール コンテナー: ActiveX コントロールからイベントを処理する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a3844788330cfe79366221ee215c437fc4aefc8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930662"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX コントロール コンテナー : ActiveX コントロールで発生したイベントの処理
この記事では、[プロパティ] ウィンドウを使用して ActiveX コントロール コンテナーで ActiveX コントロールのイベント ハンドラーをインストールするについて説明します。 (制御) から特定のイベントの通知を受信し、応答で何らかのアクションを実行するイベント ハンドラーが使用されます。 この通知は、イベントを「発生」と呼ばれます。  
  
> [!NOTE]
>  この記事では、ダイアログ ベース ActiveX コントロール コンテナーという名前のプロジェクト コンテナーと Circ をという名前のプロシージャとコードの例として、埋め込みのコントロールを使用します。  
  
 イベント ボタンを使用して、[プロパティ] ウィンドウで、ActiveX コントロール コンテナー アプリケーションで発生するイベントのマップを作成できます。 このマップは、マップと呼ばれる、"イベント シンク、' が作成され、コントロールのコンテナー クラスにイベント ハンドラーを追加すると、Visual C で保持されます。 イベント マップ エントリの場合で実装される、各イベント ハンドラーは、特定のイベントをコンテナー イベント ハンドラーのメンバー関数にマップします。 ActiveX コントロール オブジェクトによって指定されたイベントが発生したときに、このイベント ハンドラー関数が呼び出されます。  
  
 イベント シンク マップの詳細については、次を参照してください。[イベント シンク マップ](../mfc/reference/event-sink-maps.md)で、*クラス ライブラリ リファレンス*です。  
  
##  <a name="_core_event_handler_modifications_to_the_project"></a> プロジェクトにイベント ハンドラーの変更  
 [プロパティ] ウィンドウを使用してイベント ハンドラーを追加するときに、イベント シンク マップが宣言され、プロジェクトで定義されています。 次のステートメントは、コントロールに追加されます。CPP ファイルにイベント ハンドラーを追加します。 このコードのダイアログ ボックス クラスのイベント シンク マップ (この場合、 `CContainerDlg`)。  
  
 [!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]  
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]  
  
 [プロパティ] ウィンドウを使用してイベントを追加すると、イベントをマップ エントリ (`ON_EVENT`) が追加されるイベント シンク マップし、イベント ハンドラー関数が、コンテナーの実装に追加 (です。CPP) ファイルです。  
  
 次の例と呼ばれる、イベント ハンドラーを宣言する`OnClickInCircCtrl`、Circ コントロールの`ClickIn`イベント。  
  
 [!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]  
  
 次のテンプレートをさらに、追加、`CContainerDlg`クラスの実装 (です。メンバー関数のイベント ハンドラーのファイルを CPP):  
  
 [!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]  
  
 イベント シンク マクロの詳細については、次を参照してください。[イベント シンク マップ](../mfc/reference/event-sink-maps.md)で、*クラス ライブラリ リファレンス*です。  
  
#### <a name="to-create-an-event-handler-function"></a>イベント ハンドラー関数を作成するには  
  
1.  クラス ビューからには、ActiveX コントロールを含むダイアログ クラスを選択します。 この例では、使用`CContainerDlg`です。  
  
2.  [プロパティ] ウィンドウ、**イベント**ボタンをクリックします。  
  
3.  [プロパティ] ウィンドウで、埋め込みの ActiveX コントロールのコントロール ID を選択します。 この例では、使用`IDC_CIRCCTRL1`です。  
  
     [プロパティ] ウィンドウには、埋め込みの ActiveX コントロールによって起動できるイベントの一覧が表示されます。 既に太字で表示されたメンバー関数では、それに割り当てられているハンドラー関数があります。  
  
4.  ダイアログ クラスに処理するイベントを選択します。 この例では、選択**クリックして**です。  
  
5.  右側のドロップダウン リスト ボックスから選択**\<追加 > ClickCircctrl1**です。  
  
6.  クラス ビューの実装でイベント ハンドラーのコードに移動することから、新しいハンドラー関数をダブルクリックして (です。CPP) ファイルの`CContainerDlg`します。  
  
## <a name="see-also"></a>関連項目  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)

