---
title: ツリーのコントロールの通知メッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7c352da9f9283f53c926a8223984620ee7fa6ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-notification-messages"></a>ツリー コントロールの通知メッセージ
ツリー コントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) として、次の通知メッセージを送信**WM_NOTIFY**メッセージ。  
  
|通知メッセージ|説明|  
|--------------------------|-----------------|  
|**TVN_BEGINDRAG**|ドラッグ アンド ドロップ操作の開始を通知します。|  
|**TVN_BEGINLABELEDIT**|インプレースでラベルの編集の開始を通知します。|  
|**TVN_BEGINRDRAG**|マウスの右ボタンを使用して、ドラッグ アンド ドロップ操作の開始を通知します。|  
|**TVN_DELETEITEM**|特定の項目の削除を知らせます。|  
|**TVN_ENDLABELEDIT**|ラベルの編集の終了を通知します。|  
|**TVN_GETDISPINFO**|ツリー コントロールが項目を表示するのに必要な情報を要求|  
|**TVN_ITEMEXPANDED**|子アイテムの親項目の一覧が展開されたかどうか、または折りたたまれているシグナル|  
|**TVN_ITEMEXPANDING**|子アイテムの親項目の一覧を展開したり折りたたんだりできることを通知|  
|**TVN_KEYDOWN**|キーボード イベントを通知します。|  
|**TVN_SELCHANGED**|1 つの項目から別の選択が変更されたことを通知|  
|**TVN_SELCHANGING**|選択範囲は 1 つの項目から別に変更することを通知|  
|**TVN_SETDISPINFO**|アイテムを管理している情報を更新する通知|  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

