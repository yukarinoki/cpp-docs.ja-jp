---
title: メニュー、コントロール バー、およびアクセラレータの管理
ms.date: 11/04/2016
helpviewer_keywords:
- MDI [MFC], frame windows
- control bars [MFC], updating in frame windows
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- accelerator tables [MFC]
- sharing menus [MFC]
- updating user-interface objects [MFC]
- frame windows [MFC], updating
- status bars [MFC], updating
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
ms.openlocfilehash: 9945dc68ffd46bbf5e114a79467299e4b67e3659
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621326"
---
# <a name="managing-menus-control-bars-and-accelerators"></a>メニュー、コントロール バー、およびアクセラレータの管理

フレームウィンドウは、メニュー、ツールバーボタン、ステータスバー、アクセラレータなどのユーザーインターフェイスオブジェクトの更新を管理します。 また、MDI アプリケーションのメニューバーの共有も管理します。

## <a name="managing-menus"></a>メニューの管理

フレームウィンドウは、「[ユーザーインターフェイスオブジェクトを更新する方法](how-to-update-user-interface-objects.md)」で説明されている ON_UPDATE_COMMAND_UI 機構を使用して、ユーザーインターフェイス項目の更新に関与します。 ツールバーやその他のコントロールバーのボタンは、アイドルループ中に更新されます。 メニューバーのドロップダウンメニューのメニュー項目は、メニューがドロップされる直前に更新されます。

MDI アプリケーションの場合、MDI フレームウィンドウはメニューバーとキャプションを管理します。 MDI フレームウィンドウは、アクティブな MDI 子ウィンドウがないときにメニューバーとして使用される既定のメニューを1つ所有します。 アクティブな子がある場合、MDI フレームウィンドウのメニューバーは、アクティブな MDI 子ウィンドウのメニューによって表示されます。 MDI アプリケーションでグラフやワークシートドキュメントなどの複数のドキュメントの種類がサポートされている場合は、それぞれの種類のメニューがメニューバーに表示され、メインフレームウィンドウのキャプションが変更されます。

[CMDIFrameWnd](reference/cmdiframewnd-class.md)には、MDI アプリケーション用に表示される [ウィンドウ] メニューの標準コマンドの既定の実装が用意されています。 特に、新しいウィンドウコマンド (ID_WINDOW_NEW) を実装して、現在のドキュメントに新しいフレームウィンドウとビューを作成します。 これらの実装は、高度なカスタマイズが必要な場合にのみオーバーライドする必要があります。

同じドキュメントの種類の複数の MDI 子ウィンドウは、メニューリソースを共有します。 複数の MDI 子ウィンドウが同じドキュメントテンプレートによって作成されている場合は、すべて同じメニューリソースを使用して、Windows のシステムリソースを節約できます。

## <a name="managing-the-status-bar"></a>ステータスバーの管理

また、フレームウィンドウは、ステータスバーをクライアント領域内に配置し、ステータスバーのインジケーターを管理します。 フレームウィンドウは、必要に応じてステータスバーのメッセージ領域をクリアおよび更新し、ユーザーがメニュー項目またはツールバーボタンを選択したときに、[ステータスバーにコマンド情報を表示する方法に関する](how-to-display-command-information-in-the-status-bar.md)ページで説明されているように、プロンプト文字列を表示します。

## <a name="managing-accelerators"></a>アクセラレータの管理

各フレームウィンドウは、自動的にキーボードアクセスの変換を行うオプションのアクセラレータテーブルを保持します。 このメカニズムを使用すると、メニューコマンドを呼び出すアクセラレータキー (ショートカットキーとも呼ばれます) を簡単に定義できます。

## <a name="see-also"></a>関連項目

[フレームウィンドウの使用](using-frame-windows.md)
