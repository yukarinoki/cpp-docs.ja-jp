---
title: ボトムレス リッチ エディット コントロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2b08f6c04d345b4ae3ab32c6d0f17a1d8a4647
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343312"
---
# <a name="bottomless-rich-edit-controls"></a>自動的にサイズ調整されるリッチ エディット コントロール
リッチ エディット コントロールのサイズを変更できる、アプリケーション ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) の内容と同じサイズでは常にするために必要とします。 リッチ エディット コントロールがその親ウィンドウを送信することによっていわゆる「ボトムレス」機能をサポートする、 [EN_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983)通知メッセージの内容のサイズが変更されるたびにします。  
  
 処理するときに、 **EN_REQUESTRESIZE**通知メッセージをアプリケーションを指定した寸法にコントロールのサイズを変更する必要があります[REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950)構造体。 アプリケーションでは、高さでコントロールの変更に対応するコントロールの近くのすべての情報は移動も可能性があります。 コントロールのサイズを変更するには、使用することができます、`CWnd`関数[SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos)です。  
  
 送信するボトムレス リッチ エディット コントロールを強制することができます、 **EN_REQUESTRESIZE**通知メッセージを使用して、 [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize)メンバー関数。 このメッセージに役に立ちます、 [OnSize](../mfc/reference/cwnd-class.md#onsize)ハンドラー。  
  
 受信する**EN_REQUESTRESIZE**通知メッセージを使用して、通知を有効にする必要があります、`SetEventMask`メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

