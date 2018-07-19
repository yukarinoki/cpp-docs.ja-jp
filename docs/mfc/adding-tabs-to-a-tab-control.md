---
title: タブ コントロールへのタブの追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86032bd3d1ce10221cb5d8094e4ba6de866e1eea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342854"
---
# <a name="adding-tabs-to-a-tab-control"></a>タブ コントロールへのタブの追加
タブ コントロールの作成後に ([CTabCtrl](../mfc/reference/ctabctrl-class.md))、タブは、必要な数だけを追加します。  
  
### <a name="to-add-a-tab-item"></a>タブ項目を追加するには  
  
1.  準備、 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554)構造体。  
  
2.  呼び出す[として](../mfc/reference/ctabctrl-class.md#insertitem)、構造体を渡します。  
  
3.  その他のタブの項目を手順 1. および 2. を繰り返します。  
  
 詳細については、次を参照してください。[タブ コントロールを作成する](http://msdn.microsoft.com/library/windows/desktop/bb760550)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CTabCtrl の使い方](../mfc/using-ctabctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

