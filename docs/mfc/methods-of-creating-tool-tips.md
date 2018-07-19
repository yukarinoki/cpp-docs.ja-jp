---
title: ツール ヒントの作成方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26f6e7cbf8c6464afa90c52f9cd91dcdb55de767
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349533"
---
# <a name="methods-of-creating-tool-tips"></a>ツール ヒントの作成方法
MFC には、3 つのクラスを作成および管理ツール ヒント コントロール: [CWnd](../mfc/reference/cwnd-class.md)、 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)、 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)と[CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md). これらのクラスにツール ヒントのメンバー関数では、Windows のコモン コントロール API をラップします。 クラス`CToolBarCtrl`とクラス`CToolTipCtrl`クラスから派生した`CWnd`です。  
  
 `CWnd` 4 つのメンバー関数を作成および管理ツール ヒントを提供します[EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips)、 [CancelToolTips](../mfc/reference/cwnd-class.md#canceltooltips)、 [FilterToolTipMessage](../mfc/reference/cwnd-class.md#filtertooltipmessage)、および[OnToolHitTest](../mfc/reference/cwnd-class.md#ontoolhittest)。 ツール ヒントを実装する方法の詳細についてはこれらの個々 のメンバー関数を参照してください。  
  
 使用して、ツールバーを作成する場合`CToolBarCtrl`、次のメンバー関数を使用して直接ツールバーのツール ヒントを実装することができます: [GetToolTips](../mfc/reference/ctoolbarctrl-class.md#gettooltips)と[SetToolTips](../mfc/reference/ctoolbarctrl-class.md#settooltips)です。 これらの個々 のメンバー関数を参照してください、[ツール ヒントの通知の処理](../mfc/handling-tool-tip-notifications.md)ツール ヒントを実装する方法の詳細についてはします。  
  
 `CToolTipCtrl`クラスには、Windows の一般的なツール ヒント コントロールの機能が用意されています。 1 つのツール ヒント コントロールは、1 つ以上のツールの情報を提供できます。 ツールは、子ウィンドウ、またはコントロール、またはウィンドウのクライアント領域内でアプリケーションで定義された四角形領域のいずれかのウィンドウです。 [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md)クラスから派生`CToolTipCtrl`し、その他の visual スタイルと機能を提供します。  
  
## <a name="see-also"></a>関連項目  
 [CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

