---
title: フレーム ウィンドウ クラス (アーキテクチャ)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: e3ae432c1adc881a5c67d6a6c292dc1f6a583ab3
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441253"
---
# <a name="frame-window-classes-architecture"></a>フレーム ウィンドウ クラス (アーキテクチャ)

ドキュメント/ビューアーキテクチャでは、フレームウィンドウはビューウィンドウを含むウィンドウです。 また、コントロールバーが接続されていることもサポートしています。

マルチドキュメントインターフェイス (MDI) アプリケーションでは、メインウィンドウは `CMDIFrameWnd`から派生します。 オブジェクト `CMDIChildWnd` であるドキュメントのフレームが間接的に含まれています。 `CMDIChildWnd` オブジェクトには、ドキュメントのビューが含まれます。

シングルドキュメントインターフェイス (SDI) アプリケーションでは、`CFrameWnd`から派生したメインウィンドウには、現在のドキュメントのビューが含まれています。

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
SDI アプリケーションのメインフレームウィンドウの基本クラス。 他のすべてのフレームウィンドウクラスの基本クラスでもあります。

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
MDI アプリケーションのメインフレームウィンドウの基本クラス。

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
MDI アプリケーションのドキュメントフレームウィンドウの基本クラス。

[クラスからではなく、](../mfc/reference/coleipframewnd-class.md)<br/>
サーバードキュメントをその場で編集しているときに、ビューのフレームウィンドウを提供します。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
