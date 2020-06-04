---
title: イメージ リストの作成
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 440ab6fdfe7663557f6c6a6607e617c793d26674
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371576"
---
# <a name="creating-the-image-lists"></a>イメージ リストの作成

イメージ リストの作成は[、CListView](../mfc/reference/clistview-class.md)または[CListCtrl](../mfc/reference/clistctrl-class.md)を使用する場合と同じです。

> [!NOTE]
> リスト コントロールにスタイルが含まれている場合にのみ、`LVS_ICON`イメージ リストが必要です。

class`CImageList`を使用して、1 つ以上のイメージ リスト (フルサイズのアイコン、小さいアイコン、状態) を作成します。 [CImageList](../mfc/reference/cimagelist-class.md)を参照し、Windows SDK の[リスト ビューのイメージ リスト](/windows/win32/Controls/using-list-view-controls)を参照してください。

各イメージ リストの[CListCtrl::セットイメージリスト](../mfc/reference/clistctrl-class.md#setimagelist)を呼び出します。適切な`CImageList`オブジェクトへのポインタを渡します。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
