---
title: フレーム ウィンドウ クラス (アーキテクチャ) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 117554b2c34853aa166c12d80b4821d3721e5992
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394128"
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

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
インプレース サーバー ドキュメントを編集するときに、フレーム ウィンドウ ビューを提供します。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

