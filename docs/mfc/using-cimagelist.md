---
title: CImageList の使い方
ms.date: 11/04/2016
helpviewer_keywords:
- image list control
- CImageList class [MFC], using
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
ms.openlocfilehash: 09fd0e95ce2981afbebbfe10d87b26f88a7b5e13
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447226"
---
# <a name="using-cimagelist"></a>CImageList の使い方

クラス[CImageList](../mfc/reference/cimagelist-class.md)によって表されるイメージリストは、同じサイズのイメージのコレクションであり、それぞれのインデックスで参照できます。 イメージリストは、多数のアイコンまたはビットマップのセットを効率的に管理するために使用されます。 イメージリストはウィンドウではないため、それ自体がコントロールではありません。ただし、リストコントロール ([CListCtrl](../mfc/reference/clistctrl-class.md))、ツリーコントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))、タブコントロール ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) など、さまざまな種類のコントロールで使用されます。

イメージリスト内のすべてのイメージは、画面デバイス形式の1つのワイドビットマップに含まれています。 イメージリストには、画像を透過的に描画するために使用されるマスクを含むモノクロビットマップを含めることもできます (アイコンのスタイル)。 `CImageList` には、イメージの描画、イメージリストの作成と破棄、イメージの追加と削除、イメージの置換、イメージの結合、イメージのドラッグなどを行うためのメンバー関数が用意されています。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [イメージ リストの種類](../mfc/types-of-image-lists.md)

- [イメージ リストの使い方](../mfc/using-an-image-list.md)

- [イメージ リストの操作](../mfc/manipulating-image-lists.md)

- [イメージ リストのイメージの描画](../mfc/drawing-images-from-an-image-list.md)

- [イメージ リストのイメージのオーバーレイ](../mfc/image-overlays-in-image-lists.md)

- [イメージ リストのイメージのドラッグ](../mfc/dragging-images-from-an-image-list.md)

- [イメージ リストのイメージ情報](../mfc/image-information-in-image-lists.md)

## <a name="see-also"></a>参照

[コントロール](../mfc/controls-mfc.md)
