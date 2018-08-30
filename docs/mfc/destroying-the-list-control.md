---
title: リスト コントロールの破棄 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 01cdbc0f404c34a8c5ebc3ae09adf30e0cea0851
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215043"
---
# <a name="destroying-the-list-control"></a>リスト コントロールの破棄
埋め込む場合、 [CListCtrl](../mfc/reference/clistctrl-class.md)が破棄される所有者が破棄されるときに、ビューまたはダイアログ クラスのデータ メンバーとしてオブジェクトします。 使用する場合、 [CListView](../mfc/reference/clistview-class.md)フレームワークでは、ビューが破棄されると、コントロールが破棄されます。  
  
 リスト コントロールではなく、アプリケーションに格納される、リスト データの一部を配置する場合は、メモリを解放を配置する必要があります。 詳細については、次を参照してください。[コールバック項目とコールバック マスク](/windows/desktop/Controls/using-list-view-controls)Windows SDK に含まれています。  
  
 さらに、イメージのリストを作成し、リスト コントロールのオブジェクトに関連付けられているすべての割り当てを解除する責任は。  
  
## <a name="see-also"></a>関連項目  
 [Clistctrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

