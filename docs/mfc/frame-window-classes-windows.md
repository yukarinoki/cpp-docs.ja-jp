---
title: フレーム ウィンドウ クラス (Windows) |Microsoft Docs
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
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be63dd57900bbbe1691e132cd880d3da60caf4e5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431945"
---
# <a name="frame-window-classes-windows"></a>フレーム ウィンドウ クラス (Windows)

フレーム ウィンドウでは、ウィンドウ フレームのアプリケーションまたはアプリケーションの一部です。 通常、フレーム ウィンドウには、ビュー、ツール バー、およびステータス バーなどの他のウィンドウが含まれます。 場合に`CMDIFrameWnd`を含めることは`CMDIChildWnd`オブジェクトを直接します。

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
SDI アプリケーションのメイン フレーム ウィンドウの基本クラス。 またの基本クラスの他のすべてのフレーム ウィンドウ クラス。

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
MDI アプリケーションのメイン フレーム ウィンドウの基本クラス。

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
MDI アプリケーションのドキュメント フレーム ウィンドウの基本クラスです。

[CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)<br/>
一般的にフローティング ツールバーの周りの半分の高さのフレーム ウィンドウ。

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
インプレース サーバー ドキュメントを編集するときに、フレーム ウィンドウ ビューを提供します。

## <a name="related-class"></a>関連クラス

クラス`CMenu`アプリケーションのメニューにアクセスするためのインターフェイスを提供します。 実行時に動的メニューを操作するのに役立ちますたとえば、追加またはコンテキストに応じてメニュー項目を削除する場合です。 メニューは、フレーム ウィンドウで最もよく使用される、ダイアログ ボックスおよびその他の子ウィンドウ以外のウィンドウで、使用できます。

[CMenu](../mfc/reference/cmenu-class.md)<br/>
カプセル化、`HMENU`アプリケーションのメニュー バーやポップアップ メニューへのハンドル。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

