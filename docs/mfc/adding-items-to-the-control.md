---
title: コントロールへの項目の追加
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
ms.openlocfilehash: 5cc1c7a921cf6d6ba2c0f968012b48bfcaef0658
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623366"
---
# <a name="adding-items-to-the-control"></a>コントロールへの項目の追加

リストコントロール ([CListCtrl](reference/clistctrl-class.md)) に項目を追加するには、使用している情報に応じて、いくつかのバージョンの[InsertItem](reference/clistctrl-class.md#insertitem)メンバー関数のいずれかを呼び出します。 1つのバージョンでは、準備する[LVITEM](/windows/win32/api/commctrl/ns-commctrl-lvitemw)構造体が使用されます。 `LVITEM`構造体には多数のメンバーが含まれているため、リストコントロール項目の属性をより詳細に制御できます。

構造体の2つの重要なメンバー (レポートビューに関して) `LVITEM` は、 `iItem` `iSubItem` メンバーとメンバーです。 メンバーは、 `iItem` 構造体が参照している項目の0から始まるインデックスであり、 `iSubItem` メンバーはサブ項目の1から始まるインデックスです。また、構造体に項目に関する情報が含まれている場合は0になります。 この2つのメンバーを使用して、項目ごとに、リストコントロールがレポートビューであるときに表示されるサブ項目情報の型と値を決定します。 詳細については、「 [CListCtrl:: SetItem](reference/clistctrl-class.md#setitem)」を参照してください。

追加のメンバーは、項目のテキスト、アイコン、状態、および項目データを指定します。 "Item data" は、リストビューアイテムに関連付けられたアプリケーション定義の値です。 構造体の詳細については `LVITEM` 、「 [CListCtrl:: GetItem](reference/clistctrl-class.md#getitem)」を参照してください。

他のバージョンの `InsertItem` では、構造体のメンバーに対応する1つ以上の個別の値を受け取ります。これにより、 `LVITEM` サポートするメンバーだけを初期化できます。 一般に、リストコントロールはリスト項目のストレージを管理しますが、"コールバック項目" を使用して、情報の一部をアプリケーションに格納することができます。 詳細については、このトピックの「[コールバック項目と](callback-items-and-the-callback-mask.md)コールバックマスク」、および「Windows SDK のコールバック[項目と](/windows/win32/Controls/using-list-view-controls)コールバックマスク」を参照してください。

詳細については、「[リストビューの項目と](/windows/win32/Controls/using-list-view-controls)サブ項目の追加」を参照してください。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](using-clistctrl.md)<br/>
[制限](controls-mfc.md)
