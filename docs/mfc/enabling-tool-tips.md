---
title: ツール ヒントの有効化 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 968d31b49c6d2b2fe5a5f69e04f58f17de8df5a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440486"
---
# <a name="enabling-tool-tips"></a>ツール ヒントを有効にする方法

フォーム ビューまたはダイアログ ボックス コントロール) などのウィンドウの子コントロールのツール ヒントのサポートを有効にすることができます。

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>ウィンドウの子コントロールのツール ヒントを有効にするには

1. 呼び出す`EnableToolTips`ツール ヒントを提供するウィンドウ。

1. 内の各コントロールの文字列を指定して[TTN_NEEDTEXT 通知の](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)ハンドラー。 ハンドラーは、子コントロール (フォーム ビュー クラスなど) を含むウィンドウのメッセージ マップでは。 このハンドラーは関数を呼び出すコントロールを識別し、設定**pszText**ツール ヒント コントロールで使用されるテキストを指定します。

## <a name="see-also"></a>関連項目

[CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

