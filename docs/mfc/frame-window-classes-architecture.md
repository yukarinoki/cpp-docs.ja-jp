---
title: フレーム ウィンドウ クラス (アーキテクチャ)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: d1022d9a49e12585a6588e7b3202155f533e4706
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431708"
---
# <a name="frame-window-classes-architecture"></a>フレーム ウィンドウ クラス (アーキテクチャ)

ドキュメント/ビュー アーキテクチャでは、フレーム ウィンドウは、ビュー ウィンドウを持つウィンドウです。 サポート コントロールに割り当てられているバー。

マルチ ドキュメント インターフェイス (MDI) アプリケーションのメイン ウィンドウがから派生`CMDIFrameWnd`します。 直接はドキュメントのフレームは、含まれる、`CMDIChildWnd`オブジェクト。 `CMDIChildWnd`オブジェクト、さらに、ドキュメントのビューが含まれています。

派生したメイン ウィンドウで、シングル ドキュメント インターフェイス (SDI) アプリケーションで`CFrameWnd`、現在のドキュメントのビューが含まれています。

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
SDI アプリケーションのメイン フレーム ウィンドウの基本クラス。 またの基本クラスの他のすべてのフレーム ウィンドウ クラス。

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
MDI アプリケーションのメイン フレーム ウィンドウの基本クラス。

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
MDI アプリケーションのドキュメント フレーム ウィンドウの基本クラスです。

[クラスからではなく、](../mfc/reference/coleipframewnd-class.md)<br/>
インプレース サーバー ドキュメントを編集するときに、フレーム ウィンドウ ビューを提供します。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

