---
title: 反映されたメッセージの処理方法
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
ms.openlocfilehash: 8907b432cf4dabad33c0925b841f65dfc57c6295
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620150"
---
# <a name="handling-reflected-messages"></a>反映されたメッセージの処理方法

メッセージリフレクションを使用すると、コントロール自体で**WM_CTLCOLOR**、 **WM_COMMAND**、 **WM_NOTIFY**などのコントロールのメッセージを処理できます。 これにより、コントロールがより自己完結型で移植可能になります。 このメカニズムは、Windows コモンコントロールだけでなく、ActiveX コントロール (旧称 OLE コントロール) でも動作します。

メッセージリフレクションを使用すると、 `CWnd` から派生したクラスをより簡単に再利用できます。 メッセージリフレクションは、 [CWnd:: OnChildNotify](reference/cwnd-class.md#onchildnotify)を使用して、特殊な**ON_XXX_REFLECT**メッセージマップエントリ ( **ON_CTLCOLOR_REFLECT**や**ON_CONTROL_REFLECT**など) を使用して動作します。 [テクニカルノート 62](tn062-message-reflection-for-windows-controls.md)では、メッセージリフレクションの詳細について説明しています。

## <a name="what-do-you-want-to-do"></a>どうしたいんですか

- [メッセージリフレクションについての詳細情報](tn062-message-reflection-for-windows-controls.md)

- [コモンコントロールのメッセージリフレクションを実装する](tn062-message-reflection-for-windows-controls.md)

- [ActiveX コントロールのメッセージリフレクションを実装する](mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>関連項目

[メッセージハンドラー関数の宣言](declaring-message-handler-functions.md)
