---
title: ヘッダー コントロールの項目の並べ替え |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DS_DRAGDROP
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfa84326286b03f3ed0154138ed7f847440df284
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347153"
---
# <a name="ordering-items-in-the-header-control"></a>ヘッダー コントロールの項目の並べ替え
したら[ヘッダー コントロールに項目を追加](../mfc/adding-items-to-the-header-control.md)、操作するか、次の関数では、その順序に関する情報を取得します。  
  
-   [CHeaderCtrl::GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray)と[CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)  
  
     取得し、ヘッダー項目の左から右の順序を設定します。  
  
-   [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex)です。  
  
     特定のヘッダー項目のインデックス値を取得します。  
  
 前のメンバー関数に加え、`HDS_DRAGDROP`スタイルにより、ユーザーがドラッグし、ヘッダー コントロール内のヘッダー項目をドロップします。 詳細については、次を参照してください。[ヘッダー項目に対するドラッグ アンド ドロップのサポートを提供する](../mfc/providing-drag-and-drop-support-for-header-items.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)

