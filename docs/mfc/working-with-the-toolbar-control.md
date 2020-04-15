---
title: ToolBar コントロールの操作
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: 371f1944fae655556bbc9f89d7ffcce7cc326e5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365249"
---
# <a name="working-with-the-toolbar-control"></a>ToolBar コントロールの操作

この記事では、CToolBar の基になる[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクトにアクセスして、ツール バーをより詳細に制御する方法について説明します。 [CToolBar](../mfc/reference/ctoolbar-class.md) これは高度なトピックです。

## <a name="procedures"></a>手順

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>CToolBar オブジェクトの基になるツール バーコモン コントロールにアクセスするには

1. 呼び出し[C ツールバー::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).

`GetToolBarCtrl`オブジェクトへの[参照を返](../mfc/reference/ctoolbarctrl-class.md)します。 参照を使用して、ツール バー コントロール クラスのメンバー関数を呼び出すことができます。

> [!CAUTION]
> `CToolBarCtrl` **Get**関数を呼び出すことは安全ですが **、Set**関数を呼び出す場合は注意が必要です。 これは高度なトピックです。 通常は、基になるツール バー コントロールにアクセスする必要はありません。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [コントロール (Windows コモン コントロール)](../mfc/controls-mfc.md)

- [ツールバーの基本](../mfc/toolbar-fundamentals.md)

- [ツール バーのフローティングとドッキング](../mfc/docking-and-floating-toolbars.md)

- [ツール バーの動的なサイズ変更](../mfc/docking-and-floating-toolbars.md)

- [ツールバーのツールヒント](../mfc/toolbar-tool-tips.md)

- [フライバイステータスバーの更新](../mfc/toolbar-tool-tips.md)

- [ツール ヒントの通知の処理](../mfc/handling-tool-tip-notifications.md)

- [クラス](../mfc/reference/ctoolbar-class.md)[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)

- [カスタマイズ通知の処理](../mfc/handling-customization-notifications.md)

- [複数のツールバー](../mfc/toolbar-fundamentals.md)

- [古い形式のツール バーの使用](../mfc/using-your-old-toolbars.md)

- [コントロールバー](../mfc/control-bars.md)

Windows コモン コントロールの一般的な使用方法については、「[コモン コントロール](/windows/win32/Controls/common-controls-intro)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)
