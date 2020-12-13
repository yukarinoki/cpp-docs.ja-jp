---
description: '詳細情報: 制限カラムリッチエディットコントロール'
title: 自動的にサイズ調整されるリッチ エディット コントロール
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: ad3f78fb4a5e172c16faf3421b6a9da91d422888
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339814"
---
# <a name="bottomless-rich-edit-controls"></a>自動的にサイズ調整されるリッチ エディット コントロール

アプリケーションでは、必要に応じてリッチエディットコントロール ([CRichEditCtrl](reference/cricheditctrl-class.md)) のサイズを変更して、常にコンテンツと同じサイズにすることができます。 リッチエディットコントロールは、そのコンテンツのサイズが変更されるたびに親ウィンドウ [EN_REQUESTRESIZE](/windows/win32/Controls/en-requestresize) 通知メッセージを送信することで、このいわゆる "制限カラム" 機能をサポートしています。

**EN_REQUESTRESIZE** 通知メッセージを処理する場合、アプリケーションは、指定された [REQRESIZE](/windows/win32/api/richedit/ns-richedit-reqresize)構造内のディメンションにコントロールのサイズを変更する必要があります。 アプリケーションでは、コントロールの高さの変化に合わせて、コントロールの近くにあるすべての情報を移動することもできます。 コントロールのサイズを変更するには、 `CWnd` 関数 [SetWindowPos](reference/cwnd-class.md#setwindowpos)を使用します。

制限カラム rich edit コントロールに対して、 [REQUESTRESIZE](reference/cricheditctrl-class.md#requestresize)メンバー関数を使用して **EN_REQUESTRESIZE** 通知メッセージを送信するように強制することができます。 このメッセージは、 [OnSize](reference/cwnd-class.md#onsize) ハンドラーで役に立ちます。

**EN_REQUESTRESIZE** 通知メッセージを受信するには、メンバー関数を使用して通知を有効にする必要があり `SetEventMask` ます。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](using-cricheditctrl.md)<br/>
[コントロール](controls-mfc.md)
