---
description: 詳細については、「フレームウィンドウについて」を参照してください。
title: フレーム ウィンドウの機能
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], about frame windows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
ms.openlocfilehash: 8f70bbe55b15310133688079236fe57459679090
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142832"
---
# <a name="what-frame-windows-do"></a>フレーム ウィンドウの機能

フレームウィンドウは、単純にビューをフレーミングするだけでなく、フレームをビューとアプリケーションで調整するために必要な多数のタスクを担当します。 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) と [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) は、 [CFrameWnd](../mfc/reference/cframewnd-class.md)から継承されるため、 `CFrameWnd` 追加される新機能だけでなく、機能も備えています。 子ウィンドウの例としては、ビュー、ボタンやリストボックスなどのコントロール、ツールバー、ステータスバー、およびダイアログバーを含むコントロールバーなどがあります。

フレームウィンドウは、子ウィンドウのレイアウトを管理する役割を担います。 MFC フレームワークでは、フレームウィンドウは、コントロールバー、ビュー、およびその他の子ウィンドウをクライアント領域内に配置します。

また、フレームウィンドウは、コマンドをビューに転送し、コントロールウィンドウからの通知メッセージに応答できます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [コントロールバー (フレームウィンドウにどのように表示されるか)](../mfc/control-bars.md)

- [メニュー、コントロールバー、およびアクセラレータの管理 (フレームウィンドウにどのように表示されるか)](../mfc/managing-menus-control-bars-and-accelerators.md)

- [コマンドルーティング (フレームウィンドウからビューおよびその他のコマンドターゲットまで)](../mfc/command-routing.md)

- [ドキュメントの/View アーキテクチャ](../mfc/document-view-architecture.md)

- [コントロール バー](../mfc/control-bars.md)

- [コントロール](../mfc/controls-mfc.md)

## <a name="see-also"></a>関連項目

[フレームウィンドウ](../mfc/frame-windows.md)
