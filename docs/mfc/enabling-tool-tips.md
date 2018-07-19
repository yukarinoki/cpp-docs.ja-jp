---
title: ツール ヒントを有効化 |Microsoft ドキュメント
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
ms.openlocfilehash: 598583360eca2a65a5352fc9d284d8d359ac021c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346137"
---
# <a name="enabling-tool-tips"></a>ツール ヒントを有効にする方法
(フォーム ビュー、またはダイアログ ボックス コントロール) などのウィンドウの子コントロールのツール ヒントのサポートを有効にすることができます。  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>ウィンドウの子コントロールのツール ヒントを有効にするには  
  
1.  呼び出す`EnableToolTips`ツール ヒントを提供するウィンドウです。  
  
2.  内の各コントロールに、文字列を指定して[TTN_NEEDTEXT 通知の](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)ハンドラー。 ハンドラーは、子コントロール (フォーム ビュー クラスなど) を含むウィンドウのメッセージ マップには。 このハンドラーは関数を呼び出すコントロールを識別し、設定**pszText**ツール ヒント コントロールで使用されるテキストを指定します。  
  
## <a name="see-also"></a>関連項目  
 [CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

