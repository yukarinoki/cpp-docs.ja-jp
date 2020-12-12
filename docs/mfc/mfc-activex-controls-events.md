---
description: '詳細については、「MFC ActiveX コントロール: イベント」を参照してください。'
title: 'MFC ActiveX コントロール : イベント'
ms.date: 11/04/2016
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
ms.openlocfilehash: 8a360931287432e9f0ee0fc55e7e5120bcbd390f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240690"
---
# <a name="mfc-activex-controls-events"></a>MFC ActiveX コントロール : イベント

ActiveX コントロールは、イベントを使用して、コントロールに何かが発生したことをコンテナーに通知します。 イベントの一般的な例としては、コントロールのクリック、キーボードを使用して入力されたデータ、コントロールの状態の変更などがあります。 これらのアクションが発生すると、コントロールは、コンテナーに警告するイベントを発生させます。

イベントは、メッセージとも呼ばれます。

MFC では、stock と custom の2種類のイベントがサポートされています。 Stock イベントは [、クラスが](reference/colecontrol-class.md) 自動的に処理するイベントです。 Stock イベントの完全な一覧については、「 [MFC ActiveX コントロール: ストックイベントの追加](mfc-activex-controls-adding-stock-events-to-an-activex-control.md)」を参照してください。 カスタムイベントを使用すると、そのコントロールに固有のアクションが発生したときにコンテナーに通知する機能を制御できます。 一部の例は、特定のウィンドウメッセージのコントロールまたは受信の内部状態の変化です。

コントロールがイベントを適切に起動するには、コントロールクラスが、関連イベントが発生したときに呼び出されるメンバー関数にコントロールの各イベントをマップする必要があります。 このマッピング機構 (イベントマップと呼ばれます) は、イベントに関する情報を一元化し、Visual Studio がコントロールのイベントに簡単にアクセスして操作できるようにします。 このイベントマップは、ヘッダー () にある次のマクロによって宣言されます。H) を実行します。

[!code-cpp[NVC_MFC_AxUI#2](codesnippet/cpp/mfc-activex-controls-events_1.h)]

イベントマップが宣言されたら、コントロールの実装 () で定義する必要があります。CPP) ファイル。 次のコード行では、コントロールで特定のイベントを発生させることができるように、イベントマップを定義しています。

[!code-cpp[NVC_MFC_AxUI#3](codesnippet/cpp/mfc-activex-controls-events_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#4](codesnippet/cpp/mfc-activex-controls-events_3.cpp)]

MFC ActiveX コントロールウィザードを使用してプロジェクトを作成すると、これらの行が自動的に追加されます。 MFC ActiveX コントロールウィザードを使用しない場合は、これらの行を手動で追加する必要があります。

クラスビューを使用すると、 `COleControl` 定義したクラスまたはカスタムイベントでサポートされているストックイベントを追加できます。 新しいイベントごとに、クラスビューによってコントロールのイベントマップとコントロールのに適切なエントリが自動的に追加されます。IDL ファイル。

イベントの詳細については、次の2つの記事をご覧ください。

- [MFC ActiveX コントロール: ストックイベントの追加](mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [MFC ActiveX コントロール: カスタムイベントの追加](mfc-activex-controls-adding-custom-events.md)

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: メソッド](mfc-activex-controls-methods.md)<br/>
[COleControl クラス](reference/colecontrol-class.md)
