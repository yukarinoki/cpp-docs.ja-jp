---
title: 反映されたメッセージの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b317f4c1b55e04f61aa0639bbd6953e5f36187a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931841"
---
# <a name="handling-reflected-messages"></a>反映されたメッセージの処理方法
リフレクションを使用してなど、コントロールのメッセージを処理できるメッセージ**WM_CTLCOLOR**、 **WM_COMMAND**、および**WM_NOTIFY**、コントロール自体の内部です。 これによってより自己完結してポータブル コントロール。 メカニズムは、Windows のコモン コントロール、および ActiveX コントロール (旧称 OLE コントロール) では動作します。  
  
 メッセージ リフレクションでは、再利用することができます、 `CWnd`-派生クラスをより容易にします。 メッセージのリフレクションの動作を使用して[CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify)、特別なを使用して**ON_XXX_REFLECT**メッセージ マップ エントリ: たとえば、 **ON_CTLCOLOR_REFLECT**と**ON_CONTROL_REFLECT**です。 [テクニカル ノート 62](../mfc/tn062-message-reflection-for-windows-controls.md)さらに詳しくメッセージ リフレクションについて説明します。  
  
## <a name="what-do-you-want-to-do"></a>どうしたいんですか  
  
-   [詳細については、メッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [コモン コントロールの実装のメッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [ActiveX コントロールの実装のメッセージ リフレクション](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## <a name="see-also"></a>関連項目  
 [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)
