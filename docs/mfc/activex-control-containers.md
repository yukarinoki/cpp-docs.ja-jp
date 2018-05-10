---
title: ActiveX コントロール コンテナー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73496f892cc55ef59b2d84228ae9ae0416d3e8a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="activex-control-containers"></a>ActiveX コントロール コンテナー
ActiveX コントロール コンテナーは完全に ActiveX コントロールをサポートするコンテナーであり、独自のウィンドウまたはダイアログに組み込むことができます。 ActiveX コントロールは、多くの開発プロジェクトで使用できる再利用可能なソフトウェア要素です。 コントロールをできるように、アプリケーションのデータベースへのアクセス、データを監視し、アプリケーション内でさまざまな選択を行います。 ActiveX コントロールの詳細については、記事を参照してください。 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)です。  
  
 通常、コントロール コンテナーは、プロジェクトの 2 つの形式を取ります。  
  
-   ダイアログ ボックスとダイアログのようなウィンドウには、ActiveX コントロールが使用されている任意の場所 ダイアログ ボックスをフォーム ビューなどです。  
  
-   ActiveX コントロールが、ツールバー、またはユーザーのウィンドウでは、他の場所で使用されているアプリケーションでは、Windows です。  
  
 ActiveX コントロール コンテナーを使用してコントロールを操作が公開される[メソッド](../mfc/mfc-activex-controls-methods.md)と[プロパティ](../mfc/mfc-activex-controls-properties.md)です。 これらのメソッドとプロパティは、アクセスおよび変更できるコントロール コンテナーで、これについては、ActiveX コントロール コンテナー プロジェクトのラッパー クラスを使用してアクセスします。 埋め込みの ActiveX コントロールも操作により、コンテナー (送信) を発生させることによって[イベント](../mfc/mfc-activex-controls-events.md)アクションが発生したコンテナーに通知します。 か、これらの通知時に機能するコントロールのコンテナーを選択できます。  
  
 その他の記事では、Visual C でビルドされた ActiveX コントロール コンテナーに関連する基本的な実装の問題に ActiveX コントロール コンテナー プロジェクトの作成から、いくつかのトピックについて説明します。  
  
-   [MFC ActiveX コントロール コンテナーの作成](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [ActiveX コントロールのコンテナー](../mfc/containers-for-activex-controls.md)  
  
-   [ActiveX コントロール コンテナー: ActiveX コントロール サポートの手動による有効化](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)  
  
-   [ActiveX コントロール コンテナー: コントロール コンテナー アプリケーションへのコントロールの追加](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [ActiveX コントロール コンテナー: ActiveX コントロールとメンバー変数の関連付け](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [ActiveX コントロール コンテナー: ActiveX からのイベントの処理の制御します。](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [ActiveX コントロール コンテナー: コントロール プロパティの表示と変更](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [ActiveX コントロール コンテナー: ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [ActiveX コントロール コンテナー: ダイアログ ベースではないコンテナーでのコントロールの使用](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)  
  
 ダイアログ ボックスに ActiveX コントロールの使用に関する詳細については、次を参照してください。、[ダイアログ エディター](../windows/dialog-editor.md)トピックです。  
  
 Visual C と MFC ActiveX コントロールのクラスを使用して ActiveX コントロールの開発の詳細を説明する記事の一覧は、次を参照してください。 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)です。 アーティクルは、機能カテゴリでグループ化されます。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

