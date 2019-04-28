---
title: イメージ リストの作成
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 844bfe71f7b03f299f57b0fd4558b7e9eacf67c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242238"
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
