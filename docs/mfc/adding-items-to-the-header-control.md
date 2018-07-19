---
title: ヘッダー コントロールに項目を追加する |Microsoft ドキュメント
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
ms.openlocfilehash: 69d64265a94df2770e3a234ab992130b4809f9e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342736"
---
# <a name="adding-items-to-the-header-control"></a>ヘッダー コントロールへの項目の追加
ヘッダー コントロールを作成した後 ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md))、その親ウィンドウで項目数だけ追加"ヘッダー"ようにする必要があります: 通常は 1 列あたり 1 台。  
  
### <a name="to-add-a-header-item"></a>ヘッダー項目を追加するには  
  
1.  準備、 [HD_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247)構造体。  
  
2.  呼び出す[として](../mfc/reference/cheaderctrl-class.md#insertitem)、構造体を渡します。  
  
3.  追加の項目を手順 1. と 2. を繰り返します。  
  
 詳細については、次を参照してください。[アイテムをヘッダー コントロールに追加する](http://msdn.microsoft.com/library/windows/desktop/bb775238)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

