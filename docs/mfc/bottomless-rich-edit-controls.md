---
title: 制限のないリッチ エディット コントロール |Microsoft Docs
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
ms.openlocfilehash: 9ce3922bfd1a86864886057a4457627547fe85e0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373354"
---
# <a name="bottomless-rich-edit-controls"></a>自動的にサイズ調整されるリッチ エディット コントロール

リッチ エディット コントロールのサイズを変更できるアプリケーション ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) の内容と同じサイズでは常に必要な場合。 リッチ エディット コントロールがいわゆる「制限のない」機能をサポートする親ウィンドウに送信することによって、 [EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize)通知メッセージの内容のサイズが変更されるたびにします。

処理するときに、 **EN_REQUESTRESIZE**通知メッセージ、アプリケーションは、指定したディメンションにコントロールをサイズ変更する必要があります[REQRESIZE](/windows/desktop/api/richedit/ns-richedit-_reqresize)構造体。 アプリケーションでは、コントロールの高さの変更に合わせてコントロールの近くのすべての情報は移動も可能性があります。 コントロールのサイズを変更するには、使用することができます、`CWnd`関数[SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos)します。

送信制限のないリッチ エディット コントロールを強制することができます、 **EN_REQUESTRESIZE**通知メッセージを使用して、 [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize)メンバー関数。 このメッセージはで役に立ちます、 [OnSize](../mfc/reference/cwnd-class.md#onsize)ハンドラー。

受信する**EN_REQUESTRESIZE** 、通知メッセージを使用して、通知を有効にする必要があります、`SetEventMask`メンバー関数。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

