---
title: 自動的にサイズ調整されるリッチ エディット コントロール
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: d5650d34ffc350444061aa6147c38af016458811
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915265"
---
# <a name="bottomless-rich-edit-controls"></a>自動的にサイズ調整されるリッチ エディット コントロール

アプリケーションでは、必要に応じてリッチエディットコントロール ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) のサイズを変更して、常にコンテンツと同じサイズにすることができます。 リッチエディットコントロールは、そのコンテンツのサイズが変更されるたびに親ウィンドウに[EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize)通知メッセージを送信することで、このいわゆる "制限カラム" 機能をサポートしています。

**EN_REQUESTRESIZE**通知メッセージを処理する場合、アプリケーションは、指定された[REQRESIZE](/windows/desktop/api/richedit/ns-richedit-reqresize)構造内のディメンションにコントロールのサイズを変更する必要があります。 アプリケーションでは、コントロールの高さの変化に合わせて、コントロールの近くにあるすべての情報を移動することもできます。 コントロールのサイズを変更するには、 `CWnd`関数[SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos)を使用します。

[REQUESTRESIZE](../mfc/reference/cricheditctrl-class.md#requestresize)メンバー関数を使用して、制限カラム rich edit コントロールに**EN_REQUESTRESIZE**通知メッセージを送信させることができます。 このメッセージは、 [OnSize](../mfc/reference/cwnd-class.md#onsize)ハンドラーで役に立ちます。

**EN_REQUESTRESIZE**通知メッセージを受信するには、 `SetEventMask`メンバー関数を使用して通知を有効にする必要があります。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
