---
title: Windows のフレーム |Microsoft Docs
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
- frame windows [MFC], about frame windows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 895476da05d4480741577a04749df4be43016006
ms.sourcegitcommit: e4a690bf33b44432179de0bc537e26616d13c553
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "48892177"
---
# <a name="frame-windows"></a>フレーム ウィンドウ

Windows アプリケーションを実行すると、ユーザーは、フレーム ウィンドウに表示されるドキュメントと対話します。 ドキュメント フレーム ウィンドウが 2 つの主要なコンポーネント: フレームとフレームの内容。 ドキュメント フレーム ウィンドウを[シングル ドキュメント インターフェイス](../mfc/sdi-and-mdi.md)(SDI) フレーム ウィンドウまたは[マルチ ドキュメント インターフェイス](../mfc/sdi-and-mdi.md)(MDI) 子ウィンドウ。 Windows フレーム ウィンドウとユーザーのやり取りのほとんどの管理: 移動し、ウィンドウのサイズ変更、終了、および最小限に抑えることおよび最大化します。 フレーム内のコンテンツを管理します。

## <a name="frame-windows-and-views"></a>フレームの Windows とビュー

MFC フレームワークでは、フレーム ウィンドウを使用して、表示が含まれます。 2 つのコンポーネント: フレームとコンテンツ-表され、2 つの異なるクラス (mfc の) によって管理します。 フレーム ウィンドウ クラスは、フレームを管理し、ビューのクラスがコンテンツを管理します。 [ビュー] ウィンドウでは、フレーム ウィンドウの子です。 描画と他のユーザーのやり取り、ドキュメント フレーム ウィンドウのクライアント領域ではなく、ビューのクライアント領域で実行します。 フレーム ウィンドウでは、ビュー、キャプション バーと標準ウィンドウ コントロールを最小化し、ウィンドウを最大化ボタン、コントロール メニューなどの周囲に枠を表示と、ウィンドウのサイズを制御できます。 「コンテンツ」は、ウィンドウのクライアント領域で、子ウィンドウによって占有されて完全で構成されています: ビュー。 次の図は、フレーム ウィンドウとビュー間の関係を示します。

![フレーム ウィンドウ ビュー](../mfc/media/vc37fx1.gif "vc37fx1")フレーム ウィンドウとビュー

## <a name="frame-windows-and-splitter-windows"></a>フレームの Windows と Windows の分割

他の一般的な配置方法は、通常を使用して、複数のビューの周囲にフレーム ウィンドウ、[スプリッター ウィンドウ](../mfc/multiple-document-types-views-and-frame-windows.md)します。 分割ウィンドウのペインで、ビューと呼ばれる複数の子ウィンドウがあり、分割ウィンドウによってフレーム ウィンドウのクライアント領域が占有されています。

### <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

**フレーム ウィンドウの概要のトピック**

- [ウィンドウ オブジェクト](../mfc/window-objects.md)

- [フレーム ウィンドウ クラス](../mfc/frame-window-classes.md)

- [アプリケーション ウィザードで作成されるフレーム ウィンドウ クラス](../mfc/frame-window-classes-created-by-the-application-wizard.md)

- [フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)

- [フレーム ウィンドウ](../mfc/what-frame-windows-do.md)

**フレームの Windows の使用に関するトピック**

- [フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

- [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)

- [フレーム ウィンドウの破棄](../mfc/destroying-frame-windows.md)

- [MDI 子ウィンドウの管理](../mfc/managing-mdi-child-windows.md)

- [現在のビューを管理する](../mfc/managing-the-current-view.md)の 1 つ以上のビューを含むフレーム ウィンドウ

- [メニューのコントロール バー、およびアクセラレータ (フレーム ウィンドウの領域を共有する他のオブジェクト) の管理](../mfc/managing-menus-control-bars-and-accelerators.md)

**特別なフレーム ウィンドウの機能に関するトピック**

- [ドラッグ アンド ドロップ ファイル](../mfc/dragging-and-dropping-files-in-a-frame-window.md)エクスプ ローラーまたはフレーム ウィンドウにファイル マネージャーから

- [ダイナミック データ エクス (チェンジ DDE) への応答](../mfc/responding-to-dynamic-data-exchange-dde.md)

- [セミモーダル状態: 状況依存の Windows ヘルプを (その他のウィンドウの動作を調整すること)](../mfc/orchestrating-other-window-actions.md)

- [セミモーダル状態: 印刷と印刷プレビューを (その他のウィンドウの動作を調整すること)](../mfc/orchestrating-other-window-actions.md)

**Windows の他の種類に関するトピック**

- [ビューの使い方](../mfc/using-views.md)

- [ダイアログ ボックス](../mfc/dialog-boxes.md)

- [コントロール](../mfc/controls-mfc.md)

## <a name="see-also"></a>関連項目

[Windows](../mfc/windows.md)

