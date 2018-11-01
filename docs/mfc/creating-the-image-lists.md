---
title: イメージ リストの作成
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 52f375c98b5f73e0f5721c951c94e4b24f0bc224
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608677"
---
# <a name="creating-the-image-lists"></a>イメージ リストの作成

使用するかどうかは、同じイメージのリストを作成する[CListView](../mfc/reference/clistview-class.md)または[CListCtrl](../mfc/reference/clistctrl-class.md)します。

> [!NOTE]
>  のみ必要がありますをイメージ リスト、リスト コントロールが含まれている場合、`LVS_ICON`スタイル。

クラスを使用して`CImageList`(フルサイズのアイコン、小さいアイコン、および状態) の 1 つまたは複数のイメージ リストを作成します。 参照してください[CImageList](../mfc/reference/cimagelist-class.md)を参照してくださいと[リスト ビューのイメージが一覧表示](/windows/desktop/Controls/using-list-view-controls)Windows SDK にします。

呼び出す[CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist)各イメージ リスト; に適切なポインターを渡す`CImageList`オブジェクト。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

