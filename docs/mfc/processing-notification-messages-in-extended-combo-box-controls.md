---
title: コンボ ボックス コントロールを拡張に通知メッセージの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 576735841748d0b99053d038f8d5f674d5692f00
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930190"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>拡張コンボ ボックス コントロールでの通知メッセージの処理
ユーザーが拡張コンボ ボックスを操作すると、コントロール (`CComboBoxEx`) から親ウィンドウ (通常はビュー オブジェクトかダイアログ オブジェクト) に通知メッセージが送信されます。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーは、ドロップダウン リストをアクティブ化か、コントロールのエディット ボックスでクリックすると、CBEN_BEGINEDIT 通知が送信されます。  
  
 [プロパティ] ウィンドウを使用して、実装するメッセージの親クラスに通知ハンドラーを追加します。  
  
 拡張コンボ ボックス コントロールで送信される通知を一覧で説明します。  
  
-   CBEN_BEGINEDIT は、ドロップダウン リストをアクティブにしたり、コントロールのエディット ボックス内をクリックしたときに送信されます。  
  
-   CBEN_DELETEITEM は、項目が削除されたときに送信されます。  
  
-   CBEN_DRAGBEGIN は、ユーザーがコントロールの編集部分に表示される項目のイメージのドラッグを始めたときに送信されます。  
  
-   CBEN_ENDEDIT は、ユーザーがエディット ボックス内の操作を完了またはコントロールのドロップダウン リストから項目が選択されているときに送信されます。  
  
-   CBEN_GETDISPINFO 送信コールバック項目に関する表示情報を取得します。  
  
-   CBEN_INSERTITEM は、コントロールに新しい項目が挿入されたときに送信されます。  
  
## <a name="see-also"></a>関連項目  
 [CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)   
 [コントロール](../mfc/controls-mfc.md)

