---
title: リスト コントロールの通知メッセージの処理 |Microsoft ドキュメント
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
ms.openlocfilehash: c5412bbf1fcb7e139394b9563965244080e5c179
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932082"
---
# <a name="processing-notification-messages-in-list-controls"></a>リスト コントロールでの通知メッセージの処理
ユーザーは、列ヘッダーをクリックして、アイコンをドラッグして、ラベルというように、リスト コントロールの編集 ([CListCtrl](../mfc/reference/clistctrl-class.md))、親ウィンドウに通知メッセージを送信します。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーには、列ヘッダーがクリックすると、ことができますを Microsoft Outlook のように、クリックした列の内容に基づいて項目を並べ替えます。  
  
 ビューまたはダイアログ クラスのリスト コントロールから WM_NOTIFY メッセージを処理します。 [プロパティ] ウィンドウを使って作成、 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch ステートメントを持つハンドラー関数が通知メッセージを処理しているに基づいて。  
  
 リスト コントロールを親ウィンドウに送信できる通知の一覧は、次を参照してください。[リスト ビュー コントロールへの参照](http://msdn.microsoft.com/library/windows/desktop/bb774737)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

