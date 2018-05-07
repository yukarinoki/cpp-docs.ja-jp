---
title: CToolTipCtrl を使用して作成して CToolTipCtrl オブジェクトを操作する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2143ea37cfe9448e43aacfa75622beab93d2fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>CToolTipCtrl を使用して CToolTipCtrl オブジェクトを作成および操作する方法
例を次に示します[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)使用状況。  
  
### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>作成して、CToolTipCtrl を操作するには  
  
1.  構築、`CToolTipCtrl`オブジェクト。  
  
2.  呼び出す[作成](../mfc/reference/ctooltipctrl-class.md#create)Windows ツール ヒントの一般的なコントロールを作成しをアタッチする、`CToolTipCtrl`オブジェクト。  
  
3.  呼び出す[AddTool](../mfc/reference/ctooltipctrl-class.md#addtool)ツールの上にカーソルがある場合、ツール ヒントに格納されている情報が表示されないように、ツール ヒント コントロールでツールを登録します。  
  
4.  呼び出す[SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo)ツールに対して、ツール ヒントが保持している情報を設定します。  
  
5.  呼び出す[SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect)ツールの新しい外接する四角形を設定します。  
  
6.  呼び出す[HitTest](../mfc/reference/ctooltipctrl-class.md#hittest)場合と指定したツールの外接する四角形内にあるかどうかを判断する点をテストするには、ツールに関する情報を取得します。  
  
7.  呼び出す[GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount)ツール ヒント コントロールに登録されているツールの数を取得します。  
  
## <a name="see-also"></a>関連項目  
 [CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

