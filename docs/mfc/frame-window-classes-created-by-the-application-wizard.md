---
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
ms.openlocfilehash: c17ba2b6dd79e8e62baa29bba403c136d16a0d95
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077532"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>アプリケーション ウィザードで作成されるフレーム ウィンドウ クラス

**[新しいプロジェクト]** ダイアログから新しい MFC プロジェクトを作成するときに、アプリケーション、ドキュメント、およびビュークラスに加えて、アプリケーションウィザードでは、アプリケーションのメインフレームウィンドウ用の派生フレームウィンドウクラスを作成します。 クラスは既定で `CMainFrame` 呼び出され、それを含むファイルには MAINFRM.CPP という名前が付けられます。H と MAINFRM.CPP.CPP.

アプリケーションが SDI の場合、`CMainFrame` クラスは、クラス[CFrameWnd](../mfc/reference/cframewnd-class.md)から派生します。

アプリケーションが MDI の場合、`CMainFrame` はクラス[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)から派生します。 この場合、`CMainFrame` には、メニュー、ツールバー、およびステータスバーを保持するメインフレームが実装されます。 アプリケーションウィザードでは、新しいドキュメントフレームウィンドウクラスは派生しません。 代わりに、 [CMDIChildWnd クラス](../mfc/reference/cmdichildwnd-class.md)の既定の実装を使用します。 MFC フレームワークは、アプリケーションが必要とする各ビュー (`CScrollView`、`CEditView`、`CTreeView`、`CListView`など) を格納する子ウィンドウを作成します。 ドキュメントフレームウィンドウをカスタマイズする必要がある場合は、新しいドキュメントフレームウィンドウクラスを作成できます (「[クラスの追加](../ide/adding-a-class-visual-cpp.md)」を参照してください)。

ツールバーをサポートすることを選択した場合、クラスには、 [CToolBar](../mfc/reference/ctoolbar-class.md)および[CStatusBar](../mfc/reference/cstatusbar-class.md)型のメンバー変数と、2つの[コントロールバー](../mfc/control-bars.md)を初期化するための `OnCreate` メッセージハンドラー関数も含まれます。

これらのフレームウィンドウクラスは作成されたとおりに動作しますが、機能を強化するには、メンバー変数とメンバー関数を追加する必要があります。 また、ウィンドウクラスで他の Windows メッセージを処理することもできます。 詳細については、「 [MFC で作成されたウィンドウのスタイルを変更する](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)」を参照してください。

## <a name="see-also"></a>参照

[フレーム ウィンドウ クラス](../mfc/frame-window-classes.md)<br/>
[MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../build/reference/mfc-program-or-control-source-and-header-files.md)
