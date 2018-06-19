---
title: Rebar コントロールの通知メッセージの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a06df0bdfe8d1b81b4285fc86378f3da99882698
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348417"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Rebar コントロールでの通知メッセージの処理
Rebar コントロールの親クラスの作成、 `OnChildNotify` rebar コントロールすべてに、switch ステートメントを持つハンドラー関数 (`CReBarCtrl`) 通知メッセージを処理します。 ユーザーが rebar コントロール、変更したり、rebar コントロールから、削除、rebar バンドのレイアウトがバンド上のオブジェクトをドラッグしたときに、親ウィンドウへ通知が送信されます。  
  
 Rebar コントロール オブジェクトでは、次の通知メッセージを送信できます。  
  
-   **RBN_AUTOSIZE** rebar コントロールから送信されます (で作成された、**した**スタイル) ときに、rebar 自動的にサイズ変更するとき。  
  
-   **RBN_BEGINDRAG**ユーザーがバンドのドラッグを始めたとき rebar コントロールから送信されます。  
  
-   **RBN_CHILDSIZE**バンドの子ウィンドウのサイズが変更されるときに、rebar コントロールから送信します。  
  
-   **RBN_DELETEDBAND**バンドが削除された後に、rebar コントロールから送信します。  
  
-   **RBN_DELETINGBAND**バンドを削除するとき、rebar コントロールから送信されます。  
  
-   **RBN_ENDDRAG**ユーザーがバンドのドラッグを停止するときに、rebar コントロールから送信します。  
  
-   **RBN_GETOBJECT** rebar コントロールから送信されます (で作成された、**とき**スタイル) オブジェクトがコントロールでの帯域外を越えてドラッグされるときにします。  
  
-   **RBN_HEIGHTCHANGE**の高さが変更されたときに、rebar コントロールから送信します。  
  
-   **RBN_LAYOUTCHANGED**ユーザーがコントロールのバンドのレイアウトを変更したときに、rebar コントロールから送信します。  
  
 これらの通知の詳細については、次を参照してください。 [Rebar コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb774375)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CReBarCtrl の使い方](../mfc/using-crebarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

