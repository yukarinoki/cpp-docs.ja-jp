---
title: フレーム ウィンドウ クラス (アーキテクチャ)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: 483112d197b7c7211989ecda8b774deb9f30d49e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624608"
---
# <a name="frame-window-classes-architecture"></a>フレーム ウィンドウ クラス (アーキテクチャ)

ドキュメント/ビューアーキテクチャでは、フレームウィンドウはビューウィンドウを含むウィンドウです。 また、コントロールバーが接続されていることもサポートしています。

マルチドキュメントインターフェイス (MDI) アプリケーションでは、メインウィンドウはから派生 `CMDIFrameWnd` しています。 オブジェクトであるドキュメントのフレームが間接的に含まれてい `CMDIChildWnd` ます。 これらのオブジェクトには、 `CMDIChildWnd` ドキュメントのビューが含まれています。

シングルドキュメントインターフェイス (SDI) アプリケーションでは、から派生したメインウィンドウに、 `CFrameWnd` 現在のドキュメントのビューが含まれています。

[CFrameWnd](reference/cframewnd-class.md)<br/>
SDI アプリケーションのメインフレームウィンドウの基本クラス。 他のすべてのフレームウィンドウクラスの基本クラスでもあります。

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
MDI アプリケーションのメインフレームウィンドウの基本クラス。

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
MDI アプリケーションのドキュメントフレームウィンドウの基本クラス。

[クラスからではなく、](reference/coleipframewnd-class.md)<br/>
サーバードキュメントをその場で編集しているときに、ビューのフレームウィンドウを提供します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
