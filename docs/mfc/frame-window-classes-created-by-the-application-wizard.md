---
description: 詳細については、「アプリケーションウィザードで作成された Frame-Window クラス」を参照してください。
title: アプリケーション ウィザードで作成されるフレーム ウィンドウ クラス
ms.date: 11/04/2016
f1_keywords:
- CMainFrame
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
ms.openlocfilehash: 38ed83d56737d0a26d9025a9940b34d3bd6d6126
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154982"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>アプリケーション ウィザードで作成されるフレーム ウィンドウ クラス

[ **新しいプロジェクト** ] ダイアログから新しい MFC プロジェクトを作成するときに、アプリケーション、ドキュメント、およびビュークラスに加えて、アプリケーションウィザードでは、アプリケーションのメインフレームウィンドウ用の派生フレームウィンドウクラスを作成します。 クラスは既定で呼び出され、 `CMainFrame` それを含むファイルには mainfrm.cpp という名前が付けられます。H と MAINFRM.CPP。.CPP.

アプリケーションが SDI の場合、 `CMainFrame` クラスは、クラス [CFrameWnd](reference/cframewnd-class.md)から派生します。

アプリケーションが MDI の場合、 `CMainFrame` はクラス [CMDIFrameWnd](reference/cmdiframewnd-class.md)から派生します。 この場合、 `CMainFrame` メニュー、ツールバー、およびステータスバーを保持するメインフレームが実装されます。 アプリケーションウィザードでは、新しいドキュメントフレームウィンドウクラスは派生しません。 代わりに、 [CMDIChildWnd クラス](reference/cmdichildwnd-class.md)の既定の実装を使用します。 MFC フレームワークは、アプリケーションが必要とする各ビュー (型、、、など) を格納する子ウィンドウを作成し `CScrollView` `CEditView` `CTreeView` `CListView` ます。 ドキュメントフレームウィンドウをカスタマイズする必要がある場合は、新しいドキュメントフレームウィンドウクラスを作成できます (「 [クラスの追加](../ide/adding-a-class-visual-cpp.md)」を参照してください)。

ツールバーをサポートすることを選択した場合、クラスには、 [CToolBar](reference/ctoolbar-class.md) と [CStatusBar](reference/cstatusbar-class.md) 型のメンバー変数と、 `OnCreate` 2 つの [コントロールバー](control-bars.md)を初期化するためのメッセージハンドラー関数も含まれます。

これらのフレームウィンドウクラスは作成されたとおりに動作しますが、機能を強化するには、メンバー変数とメンバー関数を追加する必要があります。 また、ウィンドウクラスで他の Windows メッセージを処理することもできます。 詳細については、「 [MFC で作成されたウィンドウのスタイルを変更する](changing-the-styles-of-a-window-created-by-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[フレームウィンドウクラス](frame-window-classes.md)<br/>
[MFC プログラムまたはコントロールのソースファイルとヘッダーファイル](../build/reference/mfc-program-or-control-source-and-header-files.md)
