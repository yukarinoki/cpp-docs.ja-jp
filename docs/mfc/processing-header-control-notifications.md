---
title: ヘッダー コントロール通知の処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a0fe657089c33679cf8d18f95268a70335804c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348892"
---
# <a name="processing-header-control-notifications"></a>ヘッダー コントロール通知の処理
ビューまたはダイアログ クラスで、ウィンドウを使用してプロパティを作成、 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify)ハンドラー関数のヘッダー コントロールの switch ステートメントを持つ ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) にする通知メッセージ処理 (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。 ユーザーがクリックするか、項目との間の区分線をドラッグが、ヘッダー項目をダブルクリックしたときに、親ウィンドウへ通知が送信されます。  
  
 ヘッダー コントロールに関連付けられている通知メッセージに記載されて[ヘッダー コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb775239)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

