---
title: ヘッダー コントロールへの項目の追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6450d99b8df436c64337e52fc14244ecbb0edfc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206148"
---
# <a name="adding-items-to-the-header-control"></a>ヘッダー コントロールへの項目の追加
ヘッダー コントロールを作成した後 ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md))、その親ウィンドウに「ヘッダー項目」する必要がある数だけ追加: 列ごとに、通常は 1 つ。  
  
### <a name="to-add-a-header-item"></a>ヘッダー項目を追加するには  
  
1.  準備、 [HD_ITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema)構造体。  
  
2.  呼び出す[として](../mfc/reference/cheaderctrl-class.md#insertitem)、構造体を渡します。  
  
3.  他のアイテムには、手順 1. および 2. を繰り返します。  
  
 詳細については、次を参照してください。[ヘッダー コントロールに項目を追加](/windows/desktop/Controls/header-controls)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [Cheaderctrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

