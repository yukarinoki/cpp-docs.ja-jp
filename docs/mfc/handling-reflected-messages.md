---
title: 反映されたメッセージの処理方法
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
ms.openlocfilehash: 9b580c0c8b8fc970d69f5c57f69bbbbe65e22497
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449869"
---
# <a name="handling-reflected-messages"></a>反映されたメッセージの処理方法

メッセージがリフレクションでは、コントロールのメッセージを処理できます。 **WM_CTLCOLOR**、 **WM_COMMAND**、および**WM_NOTIFY**、コントロール自体の内部。 これによってより自己完結型で移植可能なコントロール。 メカニズムは、(旧称 OLE コントロール) の ActiveX コントロールおよび Windows のコモン コントロールとは動作します。

メッセージがリフレクションを使用して、再利用できる、 `CWnd`-派生クラスをより簡単にします。 リフレクションの動作を使用してメッセージ[CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify)、特別なを使用して**ON_XXX_REFLECT**メッセージ マップ エントリ: たとえば、 **ON_CTLCOLOR_REFLECT**と**ON_CONTROL_REFLECT**します。 [テクニカル ノート 62](../mfc/tn062-message-reflection-for-windows-controls.md)メッセージ リフレクションについて詳しく説明します。

## <a name="what-do-you-want-to-do"></a>どうしたいんですか

- [メッセージ リフレクションについての詳細します。](../mfc/tn062-message-reflection-for-windows-controls.md)

- [コモン コントロールのメッセージ リフレクションを実装します。](../mfc/tn062-message-reflection-for-windows-controls.md)

- [ActiveX コントロールのメッセージ リフレクションを実装します。](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>関連項目

[メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)
