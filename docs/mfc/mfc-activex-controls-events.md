---
title: 'MFC ActiveX コントロール: イベント |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6c8ee059b4136ce1504117246abd12ac74a6233
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348391"
---
# <a name="mfc-activex-controls-events"></a>MFC ActiveX コントロール : イベント
ActiveX コントロールは、コントロールに問題が発生しましたが、コンテナーに通知するのにイベントを使用します。 イベントの一般的な例には、コントロール、コントロールの状態で、キーボード、および変更を使用して入力データのクリックが含まれます。 これらのアクションが発生すると、コントロールは、コンテナーのアラートを生成するイベントを発生させます。  
  
 イベントは、メッセージとも呼ばれます。  
  
 MFC は、次の 2 つの種類のイベントをサポートしています: 株価とカスタムです。 ストック イベントはイベント クラスを[COleControl](../mfc/reference/colecontrol-class.md)自動的に処理されます。 ストック イベントの完全な一覧は、記事を参照してください。 [MFC ActiveX コントロール: ストック イベントの追加](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)です。 カスタム イベントは、コントロールをコントロールに固有の動作が発生すると、コンテナーに通知する機能を許可します。 コントロールの内部状態または特定のウィンドウ メッセージの受信に変更があります。  
  
 正しくイベントを発生させる、コントロールのコントロール クラスは、関連するイベントが発生したときに呼び出す必要がありますをメンバー関数に、コントロールの各イベントをマップする必要があります。 このマッピング機構 (イベント マップと呼ばれます) を使用して、イベントに関する情報を一元化、Visual Studio は簡単にアクセスし、コントロールのイベントを操作できます。 このイベントのマップがヘッダーにある次のマクロで宣言されている (です。H) コントロール クラス宣言のファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/cpp/mfc-activex-controls-events_1.h)]  
  
 イベント マップを宣言すると、コントロールの実装で定義する必要があります (です。CPP) ファイルです。 次のコード行には、コントロールで特定のイベントを発生させるイベント マップを定義します。  
  
 [!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/cpp/mfc-activex-controls-events_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/cpp/mfc-activex-controls-events_3.cpp)]  
  
 MFC ActiveX コントロール ウィザードを使用して、プロジェクトを作成する場合は、これらの行が自動的に追加します。 MFC ActiveX コントロール ウィザードを使用しない場合は、これらの行を手動で追加する必要があります。  
  
 クラス ビュー、クラスがサポートするストック イベントを追加できます`COleControl`やカスタム イベントを定義します。 自動的にクラス ビューは、新しいイベントごとに、コントロールのイベント マップし、コントロールの適切なエントリを追加します。IDL ファイルです。  
  
 その他の 2 つのアーティクルでは、イベントの詳細について説明します。  
  
-   [MFC ActiveX コントロール: ストック イベントの追加](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [MFC ActiveX コントロール: カスタム イベントの追加](../mfc/mfc-activex-controls-adding-custom-events.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)
