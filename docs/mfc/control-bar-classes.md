---
title: コントロール バー クラス
ms.date: 11/04/2016
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
ms.openlocfilehash: a050c5d2f7396324c2c380a03fc28e01ab992208
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440954"
---
# <a name="control-bar-classes"></a>コントロール バー クラス

コントロールバーは、フレームウィンドウに関連付けられています。 これらには、ボタン、状態ペイン、またはダイアログテンプレートが含まれています。 フリーフローティングコントロールバーは、ツールパレットとも呼ばれ、 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)オブジェクトにアタッチすることによって実装されます。

## <a name="framework-control-bars"></a>フレームワークコントロールバー

これらのコントロールバーは、MFC フレームワークの不可欠な部分です。 これらは、フレームワークに統合されているため、Windows のコントロールバーよりも使いやすく、強力です。 ほとんどの MFC アプリケーションは、Windows のコントロールバーではなく、これらのコントロールバーを使用します。

[CControlBar](../mfc/reference/ccontrolbar-class.md)<br/>
このセクションに一覧表示されている MFC コントロールバーの基本クラス。 コントロールバーは、フレームウィンドウの端に合わせて並べられたウィンドウです。 コントロールバーには、`HWND`ベースの子コントロール、またはツールバーボタンなどの `HWND`に基づいていないコントロールが含まれています。

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
ダイアログボックステンプレートに基づくコントロールバー。

[CReBar](../mfc/reference/crebar-class.md)<br/>
コントロールの形式で追加の子ウィンドウを含めることができるツールバーをサポートします。

[CToolBar](../mfc/reference/ctoolbar-class.md)<br/>
`HWND`に基づいていないビットマップコマンドボタンを含むツールバーコントロールウィンドウ。 ほとんどの MFC アプリケーションでは、`CToolBarCtrl`ではなく、このクラスを使用します。

[CStatusBar](../mfc/reference/cstatusbar-class.md)<br/>
ステータスバーコントロールウィンドウの基本クラス。 ほとんどの MFC アプリケーションでは、`CStatusBarCtrl`ではなく、このクラスを使用します。

## <a name="windows-control-bars"></a>Windows コントロールバー

これらのコントロールバーは、対応する Windows コントロールの細いラッパーです。 これらはフレームワークと統合されていないため、前に示したコントロールバーよりも使用するのが難しくなります。 ほとんどの MFC アプリケーションでは、前に示したコントロールバーが使用されます。

[CRebarCtrl](../mfc/reference/crebarctrl-class.md)<br/>
`CRebar` オブジェクトの内部コントロールを実装します。

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
水平方向のウィンドウ。通常はウィンドウに分割され、アプリケーションで状態情報を表示できます。

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Windows ツール バー コモン コントロールの機能が用意されています。

## <a name="related-classes"></a>関連クラス

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
アプリケーション内のツールの目的を説明する1行のテキストを表示する小さなポップアップウィンドウ。

[CDockState](../mfc/reference/cdockstate-class.md)<br/>
コントロールバーのドッキング状態データの永続ストレージを処理します。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
