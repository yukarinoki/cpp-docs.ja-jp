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
ms.openlocfilehash: aac3c9ba284abc634af2fbeb25633b812e07f926
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928571"
---
# <a name="ordering-items-in-the-header-control"></a>ヘッダー コントロールの項目の並べ替え
したら[ヘッダー コントロールに項目を追加](../mfc/adding-items-to-the-header-control.md)、操作するか、次の関数では、その順序に関する情報を取得します。  
  
-   [CHeaderCtrl::GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray)と[CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)  
  
     取得し、ヘッダー項目の左から右の順序を設定します。  
  
-   [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex)です。  
  
     特定のヘッダー項目のインデックス値を取得します。  
  
 に加えて、前のメンバー関数は、HDS_DRAGDROP 形式をドラッグして、ヘッダー コントロール内のヘッダー項目、ユーザーをできます。 詳細については、次を参照してください。[ヘッダー項目に対するドラッグ アンド ドロップのサポートを提供する](../mfc/providing-drag-and-drop-support-for-header-items.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)

