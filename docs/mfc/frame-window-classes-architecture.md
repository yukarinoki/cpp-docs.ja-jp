---
description: '詳細情報: フレームウィンドウクラス (アーキテクチャ)'
title: フレーム ウィンドウ クラス (アーキテクチャ)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: 045108cd1e45325cf6069b5d8259ffab9abb0c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155034"
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
