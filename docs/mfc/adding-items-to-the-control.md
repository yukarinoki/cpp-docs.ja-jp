---
title: コントロールに項目の追加 |Microsoft Docs
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
ms.openlocfilehash: a2e9434e93640de190b78e92a1f009a0ad9cbecf
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214438"
---
# <a name="adding-items-to-the-control"></a>コントロールへの項目の追加
リスト コントロールに項目を追加する ([CListCtrl](../mfc/reference/clistctrl-class.md))、いくつかのバージョンの 1 つを呼び出して、 [InsertItem](../mfc/reference/clistctrl-class.md#insertitem)によってどのような情報がある場合、メンバー関数。 1 つのバージョンは、 [LV_ITEM](/windows/desktop/api/commctrl/ns-commctrl-taglvitema)を準備する構造。 `LV_ITEM`構造体には、多数のメンバーが含まれていますが、リスト コントロール項目の属性をより細かく制御します。  
  
 ([レポート] ビュー) に関して 2 つの重要なメンバーの`LV_ITEM`構造体は、`iItem`と`iSubItem`メンバー。 `iItem`メンバーは、構造体が参照する項目の 0 から始まるインデックス、および`iSubItem`構造体には、項目に関する情報が含まれている場合、メンバーは、サブ項目、または 0 の 1 から始まるインデックス。 これら 2 つのメンバーで、アイテム、型、およびサブ項目のリスト コントロールがレポート ビューに表示される情報の値ごとに決定します。 詳細については、次を参照してください。 [CListCtrl::SetItem](../mfc/reference/clistctrl-class.md#setitem)します。  
  
 追加のメンバーは、項目のテキスト、アイコン、状態、および項目のデータを指定します。 「データの項目」リスト ビュー アイテムに関連付けられているアプリケーション定義の値です。 詳細については、`LV_ITEM`構造体は、「 [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)します。  
  
 他のバージョンの`InsertItem`1 つまたは複数個別の値を受け取る、内のメンバーに対応する、`LV_ITEM`構造をサポートするメンバーのみを初期化することができます。 一般に、リスト コントロール リストの項目のためのストレージを管理するがする格納できる情報の一部、アプリケーションで代わりに、「コールバック項目」を使用します。 詳細については、次を参照してください。[コールバック項目とコールバック マスク](../mfc/callback-items-and-the-callback-mask.md)このトピックの「と[コールバック項目とコールバック マスク](/windows/desktop/Controls/using-list-view-controls)Windows SDK にします。  
  
 詳細については、次を参照してください。[リスト ビュー項目の追加とサブ項目](/windows/desktop/Controls/using-list-view-controls)します。  
  
## <a name="see-also"></a>関連項目  
 [Clistctrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

