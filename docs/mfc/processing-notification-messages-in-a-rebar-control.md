---
title: Rebar コントロールの通知メッセージの処理 |Microsoft Docs
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
ms.openlocfilehash: dce09e84e9a2b5262d05847746f819a122ec36c5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208976"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Rebar コントロールでの通知メッセージの処理
Rebar コントロールの親クラスで作成、`OnChildNotify`ハンドラー関数の rebar コントロールの switch ステートメントを (`CReBarCtrl`) 通知のメッセージを処理します。 ユーザーが rebar コントロール、変更、削除、rebar バンドのレイアウトと、rebar コントロールからのバンド上でオブジェクトをドラッグすると、親ウィンドウに通知が送信されます。  
  
 Rebar コントロールによっては、次の通知メッセージを送信できます。  
  
-   RBN_AUTOSIZE が (したスタイルで作成された) rebar コントロールから送信されたときに、rebar 自動的にサイズが変更されます。  
  
-   RBN_BEGINDRAG は、ユーザーがバンドのドラッグを開始するときに、rebar コントロールから送信されます。  
  
-   RBN_CHILDSIZE rebar コントロール バンドの子ウィンドウのサイズによって送信されます。  
  
-   RBN_DELETEDBAND rebar コントロール バンドが削除された後で送信されます。  
  
-   RBN_DELETINGBAND rebar コントロール バンドが削除されるときに送信されます。  
  
-   RBN_ENDDRAG は、ユーザーがバンドのドラッグを停止したとき、rebar コントロールから送信されます。  
  
-   RBN_GETOBJECT が rebar コントロール (ときスタイルで作成された) によって送信される、コントロールのバンド上にオブジェクトをドラッグするとします。  
  
-   RBN_HEIGHTCHANGE rebar コントロールの高さが変更されたときに送信されます。  
  
-   RBN_LAYOUTCHANGED は、ユーザー コントロールのバンドのレイアウトが変更されたとき、rebar コントロールから送信されます。  
  
 これらの通知の詳細については、次を参照してください。 [Rebar コントロールの参照](https://msdn.microsoft.com/library/windows/desktop/bb774375)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [Crebarctrl の使い方](../mfc/using-crebarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

