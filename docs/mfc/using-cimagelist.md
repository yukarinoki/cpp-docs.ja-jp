---
description: 詳細については、「Using CImageList」を参照してください。
title: CImageList の使い方
ms.date: 11/04/2016
helpviewer_keywords:
- image list control
- CImageList class [MFC], using
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
ms.openlocfilehash: 9e0126e3d5b083dc4a88bfb1ca2130be0e9fbaaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202536"
---
# <a name="using-cimagelist"></a>CImageList の使い方

クラス [CImageList](../mfc/reference/cimagelist-class.md)によって表されるイメージリストは、同じサイズのイメージのコレクションであり、それぞれのインデックスで参照できます。 イメージリストは、多数のアイコンまたはビットマップのセットを効率的に管理するために使用されます。 イメージリストはウィンドウではないため、それ自体がコントロールではありません。ただし、リストコントロール ([CListCtrl](../mfc/reference/clistctrl-class.md))、ツリーコントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))、タブコントロール ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) など、さまざまな種類のコントロールで使用されます。

イメージリスト内のすべてのイメージは、画面デバイス形式の1つのワイドビットマップに含まれています。 イメージリストには、画像を透過的に描画するために使用されるマスクを含むモノクロビットマップを含めることもできます (アイコンのスタイル)。 `CImageList` イメージの描画、イメージリストの作成と破棄、イメージの追加と削除、イメージの置換、イメージの結合、およびイメージのドラッグを行うことができるメンバー関数を提供します。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [イメージリストの種類](../mfc/types-of-image-lists.md)

- [イメージリストの使用](../mfc/using-an-image-list.md)

- [イメージリストの操作](../mfc/manipulating-image-lists.md)

- [イメージリストからのイメージの描画](../mfc/drawing-images-from-an-image-list.md)

- [イメージリストのイメージのオーバーレイ](../mfc/image-overlays-in-image-lists.md)

- [イメージリストからのイメージのドラッグ](../mfc/dragging-images-from-an-image-list.md)

- [イメージリストのイメージ情報](../mfc/image-information-in-image-lists.md)

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)
