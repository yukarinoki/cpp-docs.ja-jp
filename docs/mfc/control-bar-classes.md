---
description: '詳細情報: コントロールバークラス'
title: コントロール バー クラス
ms.date: 11/04/2016
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
ms.openlocfilehash: 9ccb22a90799d7af7db49cd0a1a65a1009e9f36e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310227"
---
# <a name="control-bar-classes"></a>コントロール バー クラス

コントロールバーは、フレームウィンドウに関連付けられています。 これらには、ボタン、状態ペイン、またはダイアログテンプレートが含まれています。 フリーフローティングコントロールバーは、ツールパレットとも呼ばれ、 [CMiniFrameWnd](reference/cminiframewnd-class.md) オブジェクトにアタッチすることによって実装されます。

## <a name="framework-control-bars"></a>フレームワークコントロールバー

これらのコントロールバーは、MFC フレームワークの不可欠な部分です。 これらは、フレームワークに統合されているため、Windows のコントロールバーよりも使いやすく、強力です。 ほとんどの MFC アプリケーションは、Windows のコントロールバーではなく、これらのコントロールバーを使用します。

[CControlBar](reference/ccontrolbar-class.md)<br/>
このセクションに一覧表示されている MFC コントロールバーの基本クラス。 コントロールバーは、フレームウィンドウの端に合わせて並べられたウィンドウです。 コントロールバーには、 `HWND` ベースの子コントロールまたはに基づいていないコントロール `HWND` (ツールバーボタンなど) が含まれています。

[CDialogBar](reference/cdialogbar-class.md)<br/>
ダイアログボックステンプレートに基づくコントロールバー。

[CReBar](reference/crebar-class.md)<br/>
コントロールの形式で追加の子ウィンドウを含めることができるツールバーをサポートします。

[CToolBar](reference/ctoolbar-class.md)<br/>
に基づいていないビットマップコマンドボタンを含む Toolbar コントロールウィンドウ `HWND` 。 ほとんどの MFC アプリケーションは、ではなくこのクラスを使用し `CToolBarCtrl` ます。

[CStatusBar](reference/cstatusbar-class.md)<br/>
ステータスバーコントロールウィンドウの基本クラス。 ほとんどの MFC アプリケーションは、ではなくこのクラスを使用し `CStatusBarCtrl` ます。

## <a name="windows-control-bars"></a>Windows コントロールバー

これらのコントロールバーは、対応する Windows コントロールの細いラッパーです。 これらはフレームワークと統合されていないため、前に示したコントロールバーよりも使用するのが難しくなります。 ほとんどの MFC アプリケーションでは、前に示したコントロールバーが使用されます。

[CRebarCtrl](reference/crebarctrl-class.md)<br/>
オブジェクトの内部コントロールを実装し `CRebar` ます。

[CStatusBarCtrl](reference/cstatusbarctrl-class.md)<br/>
水平方向のウィンドウ。通常はウィンドウに分割され、アプリケーションで状態情報を表示できます。

[CToolBarCtrl](reference/ctoolbarctrl-class.md)<br/>
Windows ツール バー コモン コントロールの機能が用意されています。

## <a name="related-classes"></a>関連クラス

[CToolTipCtrl](reference/ctooltipctrl-class.md)<br/>
アプリケーション内のツールの目的を説明する1行のテキストを表示する小さなポップアップウィンドウ。

[CDockState](reference/cdockstate-class.md)<br/>
コントロールバーのドッキング状態データの永続ストレージを処理します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
