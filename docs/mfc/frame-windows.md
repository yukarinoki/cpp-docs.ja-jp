---
title: フレーム ウィンドウ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame widows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 515df19bcc11f7a6706985014fc44bc4ff315f36
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352064"
---
# <a name="frame-windows"></a>フレーム ウィンドウ
アプリケーションを Windows で実行すると、ユーザーは、フレーム ウィンドウに表示されるドキュメントと対話します。 ドキュメント フレーム ウィンドウが 2 つの主要なコンポーネント: フレームとフレームの内容。 ドキュメント フレーム ウィンドウには、[シングル ドキュメント インターフェイス](../mfc/sdi-and-mdi.md)(SDI) フレーム ウィンドウまたは[マルチ ドキュメント インターフェイス](../mfc/sdi-and-mdi.md)(MDI) 子ウィンドウ。 Windows によるフレーム ウィンドウでのユーザーの操作のほとんどの管理: 移動およびウィンドウのサイズ、終了、およびを最小限に抑えるおよび最大化します。 フレーム内のコンテンツを管理します。  
  
## <a name="frame-windows-and-views"></a>フレーム ウィンドウとビュー  
 MFC フレームワークでは、フレーム ウィンドウを使用して、表示が含まれます。 2 つのコンポーネント: フレームとコンテンツ — 表され、2 つの異なるクラス (MFC の) によって管理されています。 フレーム ウィンドウ クラスが、フレームを管理し、ビューのクラスがコンテンツを管理します。 [ビュー] ウィンドウでは、フレーム ウィンドウの子です。 描画およびその他のユーザーの操作がドキュメントにフレーム ウィンドウのクライアント領域ではなく、ビューのクライアント領域で実行します。 フレーム ウィンドウでは、キャプション バーと標準ウィンドウ コントロールを最小化し、ウィンドウを最大化ボタン、コントロール メニューなどの完全なビューの周囲に枠を表示と、ウィンドウのサイズを制御できます。 「コンテンツ」から成るウィンドウのクライアント領域は、完全に子ウィンドウにより占有 — ビュー。 次の図は、フレーム ウィンドウとビューの関係を示しています。  
  
 ![フレーム ウィンドウの表示](../mfc/media/vc37fx1.gif "vc37fx1")  
フレーム ウィンドウとビュー  
  
## <a name="frame-windows-and-splitter-windows"></a>フレーム ウィンドウと分割ウィンドウ  
 別の一般的な配置は、通常を使用して、複数のビューをフレームをフレーム ウィンドウの[分割ウィンドウ](../mfc/multiple-document-types-views-and-frame-windows.md)します。 分割ウィンドウのフレーム ウィンドウのクライアント領域はペインで、ビューと呼ばれる、複数の子ウィンドウを順番にある分割ウィンドウによって占有されています。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
 **フレーム ウィンドウの概要に関するトピック**  
  
-   [ウィンドウ オブジェクト](../mfc/window-objects.md)  
  
-   [フレーム ウィンドウ クラス](../mfc/frame-window-classes.md)  
  
-   [アプリケーションのウィザードで作成されるフレーム ウィンドウ クラス](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)  
  
-   [フレーム ウィンドウ](../mfc/what-frame-windows-do.md)  
  
 **フレーム ウィンドウの使用に関するトピック**  
  
-   [フレーム ウィンドウの使用](../mfc/using-frame-windows.md)  
  
-   [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)  
  
-   [フレーム ウィンドウの破棄](../mfc/destroying-frame-windows.md)  
  
-   [MDI 子ウィンドウの管理](../mfc/managing-mdi-child-windows.md)  
  
-   [現在のビューを管理する](../mfc/managing-the-current-view.md)の 1 つ以上のビューを含むフレーム ウィンドウ  
  
-   [メニューのコントロール バー、およびアクセラレータ (フレーム ウィンドウの領域を共有する他のオブジェクト) を管理します。](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 **特殊なフレーム ウィンドウの機能に関するトピック**  
  
-   [ドラッグ アンド ドロップ ファイル](../mfc/dragging-and-dropping-files-in-a-frame-window.md)ファイル エクスプ ローラーまたはファイル マネージャーからにフレーム ウィンドウ  
  
-   [ダイナミック データ エクス (チェンジ DDE) への応答](../mfc/responding-to-dynamic-data-exchange-dde.md)  
  
-   [セミモーダル状態: 状況依存の Windows ヘルプを (その他のウィンドウの動作の調整](../mfc/orchestrating-other-window-actions.md)  
  
-   [セミモーダル状態: 印刷と印刷プレビューを (その他のウィンドウの動作の調整](../mfc/orchestrating-other-window-actions.md)  
  
 **Windows の他の種類に関するトピック**  
  
-   [ビューの使い方](../mfc/using-views.md)  
  
-   [ダイアログ ボックス](../mfc/dialog-boxes.md)  
  
-   [コントロール](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>関連項目  
 [Windows](../mfc/windows.md)

