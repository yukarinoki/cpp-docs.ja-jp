---
title: リスト コントロールの通知メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3362074ce0f8d4d7a3a3463d22f9089f847e747d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208711"
---
# <a name="processing-notification-messages-in-list-controls"></a>リスト コントロールでの通知メッセージの処理
ユーザーは、列ヘッダーをクリック、アイコンをドラッグして、ラベルというように、リスト コントロールの編集 ([CListCtrl](../mfc/reference/clistctrl-class.md))、親ウィンドウに通知メッセージを送信します。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーは、列ヘッダーをクリックすると、Microsoft Outlook のように、クリックされた列の内容に基づいて項目の並べ替えにする可能性があります。  
  
 ビューまたはダイアログ クラスのリスト コントロールから WM_NOTIFY メッセージの処理。 [プロパティ] ウィンドウを使用して作成する、 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify)ハンドラー関数を switch ステートメントが通知メッセージの処理に基づきます。  
  
 リスト コントロールが親ウィンドウに送信できる通知の一覧は、次を参照してください。[リスト ビュー コントロールのリファレンス](/windows/desktop/Controls/list-view-control-reference)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [Clistctrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

