---
title: コントロールに項目を追加する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eab0c7cb1aebf1675d078aa99941edfd9afdc5a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341366"
---
# <a name="adding-items-to-the-control"></a>コントロールへの項目の追加
リスト コントロールに項目を追加する ([CListCtrl](../mfc/reference/clistctrl-class.md))、いくつかのバージョンの 1 つを呼び出して、 [InsertItem](../mfc/reference/clistctrl-class.md#insertitem)際にどのような情報に応じて、メンバー関数。 1 つのバージョンは、 [LV_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760)を準備する構造。 `LV_ITEM`構造には、多数のメンバーが含まれていますが、リスト コントロール項目の属性をより細かく制御できます。  
  
 ([レポート] ビュー) に関して 2 つの重要なメンバーの`LV_ITEM`構造体は、`iItem`と`iSubItem`メンバー。 `iItem`メンバーは、構造体を参照している項目の 0 から始まるインデックス、および`iSubItem`構造体には、その項目に関する情報が含まれている場合、メンバーは、サブ項目または 0 の 1 から始まるインデックス。 これら 2 つのメンバーと、項目の種類、サブ項目のリスト コントロールがレポート ビューに表示される情報の値ごとに決定します。 詳細については、次を参照してください。 [CListCtrl::SetItem](../mfc/reference/clistctrl-class.md#setitem)です。  
  
 追加のメンバーは、アイテムのテキスト、アイコン、状態、および項目のデータを指定します。 「データを項目」リスト ビューの項目に関連付けられているアプリケーション定義の値です。 詳細については、`LV_ITEM`構造体は、「 [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)です。  
  
 他のバージョンの`InsertItem`値を取る 1 つまたは複数別、内のメンバーに対応する、`LV_ITEM`構造をサポートするメンバーのみを初期化することができます。 一般に、リスト コントロールは、リスト項目のストレージを管理もする格納できる情報の一部、アプリケーションの代わりに、「コールバック項目」の使用 詳細については、次を参照してください。[コールバック項目とコールバック マスク](../mfc/callback-items-and-the-callback-mask.md)」を参照と[コールバック項目とコールバック マスク](http://msdn.microsoft.com/library/windows/desktop/bb774736)Windows SDK に含まれています。  
  
 詳細については、次を参照してください。[リスト ビューの項目の追加とサブ](http://msdn.microsoft.com/library/windows/desktop/bb774736)です。  
  
## <a name="see-also"></a>関連項目  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

