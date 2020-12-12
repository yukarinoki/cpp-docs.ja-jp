---
description: '詳細情報: Windows'
title: Windows
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], window
- windows [MFC]
- MFC, windows
- window objects [MFC], MFC Framework
ms.assetid: dd92bf34-842e-40fe-8aea-3028b55314d5
ms.openlocfilehash: c38dd8224fbd518fb0ebb2407ec4d03a43d90c63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284929"
---
# <a name="windows"></a>Windows

この記事ファミリでは、MFC フレームワークのウィンドウオブジェクトについて説明します。 すべての MFC ウィンドウは、フレームウィンドウ、ビュー、ダイアログボックス、コントロールなどのクラス [CWnd](../mfc/reference/cwnd-class.md)から派生します。

最初の記事のグループでは、一般的な [ウィンドウオブジェクト](../mfc/window-objects.md) について説明します。 C++ ウィンドウオブジェクトの一般的な情報、をカプセル化する方法、 `HWND` および子ウィンドウなど、独自のウィンドウを作成するときにそれらを使用する方法については、このグループを参照してください。

2番目の記事では、フレーム [ウィンドウ](../mfc/frame-windows.md)(コンテンツの周囲にフレームを配置するウィンドウ) について説明します。 コントロールバーとビューを含む、フレームウィンドウとそのフレームの内容を MFC フレームワークで管理する方法の詳細については、このグループを参照してください。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

*ウィンドウオブジェクトに関する一般的なトピック*

- [ウィンドウ オブジェクト](../mfc/window-objects.md)

- [C++ ウィンドウオブジェクトと HWND ハンドルの関係](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)

- [派生ウィンドウクラス](../mfc/derived-window-classes.md)

- [作成 (ウィンドウオブジェクトを)](../mfc/creating-windows.md)

- [破棄 (ウィンドウオブジェクトを)](../mfc/destroying-window-objects.md)

- [ウィンドウ "classes" を登録しています](../mfc/registering-window-classes.md)

- [ウィンドウ オブジェクトの操作](../mfc/working-with-window-objects.md)

- [デバイスコンテキスト](../mfc/device-contexts.md): Windows がデバイスに依存しないようにするオブジェクト

- [グラフィックオブジェクト](../mfc/graphic-objects.md): ペン、ブラシ、フォント、ビットマップ、パレット、領域

*フレームウィンドウのトピック*

- [フレームウィンドウ](../mfc/frame-windows.md): フレームを提供するウィンドウオブジェクト

- [フレームウィンドウとビュー](../mfc/frame-windows.md)

- [フレーム ウィンドウ クラス](../mfc/frame-window-classes.md)

- [フレームウィンドウスタイル](../mfc/frame-window-styles-cpp.md)

- [MFC で作成したウィンドウのスタイル変更](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

- [フレーム ウィンドウの機能](../mfc/what-frame-windows-do.md)

- [フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

- [MD/子ウィンドウの管理 (MDICLIENT ウィンドウ)](../mfc/managing-mdi-child-windows.md)

- [メニュー、コントロール バー、およびアクセラレータの管理](../mfc/managing-menus-control-bars-and-accelerators.md)

- [CFrameWnd](../mfc/reference/cframewnd-class.md)

- [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)

- [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)

- [ビューの使用](../mfc/using-views.md)

- [複数のドキュメントタイプ、ビュー、フレームウィンドウ (分割ウィンドウ)](../mfc/multiple-document-types-views-and-frame-windows.md)

- [Messages (maps および handler 関数)](../mfc/messages.md)

*ウィンドウの作成と破棄*

- [全般ウィンドウ作成順序](../mfc/general-window-creation-sequence.md)

- [ウィンドウオブジェクトの破棄](../mfc/destroying-window-objects.md)

- [ドキュメントフレームウィンドウを作成する](../mfc/creating-document-frame-windows.md)

- [フレームウィンドウの破棄](../mfc/destroying-frame-windows.md)

*分割ウィンドウの作成*

- [分割ウィンドウの作成](../mfc/multiple-document-types-views-and-frame-windows.md)

*子ウィンドウと現在のビューの管理*

- [MDI 子ウィンドウの管理](../mfc/managing-mdi-child-windows.md)

- [現在のビューを管理する](../mfc/managing-the-current-view.md)

- [メニュー、コントロールバー、およびアクセラレータの管理](../mfc/managing-menus-control-bars-and-accelerators.md)

*デバイスコンテキストとウィンドウスタイルを操作する*

- [デバイスコンテキストでペンとその他のグラフィックオブジェクトを使用する](../mfc/graphic-objects.md)

- [MFC によって作成されたウィンドウのスタイルを変更する](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](../mfc/user-interface-elements-mfc.md)<br/>
[ダイアログボックス](../mfc/dialog-boxes.md)<br/>
[[ツール バー]](../mfc/toolbars.md)<br/>
[ステータスバー](../mfc/status-bars.md)<br/>
[ダイアログバー](../mfc/dialog-bars.md)
