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
ms.openlocfilehash: 9a1d42d129ab7b7d2e98ae1126b8f32f68b1f356
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931828"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Rebar コントロールでの通知メッセージの処理
Rebar コントロールの親クラスの作成、 `OnChildNotify` rebar コントロールすべてに、switch ステートメントを持つハンドラー関数 (`CReBarCtrl`) 通知メッセージを処理します。 ユーザーが rebar コントロール、変更したり、rebar コントロールから、削除、rebar バンドのレイアウトがバンド上のオブジェクトをドラッグしたときに、親ウィンドウへ通知が送信されます。  
  
 Rebar コントロール オブジェクトでは、次の通知メッセージを送信できます。  
  
-   RBN_AUTOSIZE が (したスタイルで作成した)、rebar コントロールから送信されるときに、rebar 自動的にサイズ変更するとき。  
  
-   RBN_BEGINDRAG は、ユーザーがバンドのドラッグを始めたときに、rebar コントロールから送信されます。  
  
-   Rebar コントロール バンドの子ウィンドウのサイズを変更して RBN_CHILDSIZE が送信されます。  
  
-   Rebar コントロール バンドが削除された後で RBN_DELETEDBAND が送信されます。  
  
-   RBN_DELETINGBAND はバンドを削除するときに、rebar コントロールから送信されます。  
  
-   RBN_ENDDRAG は、ユーザーがバンドのドラッグを停止したときに、rebar コントロールから送信されます。  
  
-   (ときスタイルで作成した)、rebar コントロールから送信された RBN_GETOBJECT オブジェクトがコントロールでの帯域外を越えてドラッグされるときにします。  
  
-   RBN_HEIGHTCHANGE が rebar コントロールの高さが変更されたときに送信されます。  
  
-   RBN_LAYOUTCHANGED は、ユーザーがコントロールのバンドのレイアウトを変更したときに、rebar コントロールから送信されます。  
  
 これらの通知の詳細については、次を参照してください。 [Rebar コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb774375)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CReBarCtrl の使い方](../mfc/using-crebarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

