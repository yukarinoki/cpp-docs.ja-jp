---
title: CImageList の使い方 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CImageList
dev_langs:
- C++
helpviewer_keywords:
- image list control
- CImageList class [MFC], using
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8dd30b21b1ec635c6d5b5f2f5c6c6d9eb6fc3fa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-cimagelist"></a>CImageList の使い方
イメージ リストは、クラスによって表される[CImageList](../mfc/reference/cimagelist-class.md)、それぞれの参照インデックスを使用して、同じサイズのイメージのコレクションです。 イメージ リストを使用して、多数のアイコンまたはビットマップを効率的に管理できます。 イメージ リスト; windows ではないために、コントロールをそれ自体されませんただし、いくつかのさまざまな種類のコントロール、リスト コントロールが含むされる ([CListCtrl](../mfc/reference/clistctrl-class.md))、ツリー コントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))、およびコントロールのタブ ([CTabCtrl](../mfc/reference/ctabctrl-class.md))。  
  
 イメージ リスト内のすべてのイメージは、1 つワイド形式のビットマップ画面デバイスに格納されます。 イメージ リストは、モノクロ ビットマップを透過的にイメージを描画するためのマスク (アイコンのスタイル) を含むもあります。 `CImageList` 使用すると、イメージの描画、作成しイメージ リストを破棄、および追加および削除イメージ、イメージを置き換える、イメージのマージ、イメージのドラッグをメンバー関数を提供します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [イメージ リストの種類](../mfc/types-of-image-lists.md)  
  
-   [イメージ リストの使い方](../mfc/using-an-image-list.md)  
  
-   [イメージ リストの操作](../mfc/manipulating-image-lists.md)  
  
-   [イメージ リストのイメージの描画](../mfc/drawing-images-from-an-image-list.md)  
  
-   [イメージ リストのイメージのオーバーレイ](../mfc/image-overlays-in-image-lists.md)  
  
-   [イメージ リストのイメージのドラッグ](../mfc/dragging-images-from-an-image-list.md)  
  
-   [イメージ リストのイメージ情報](../mfc/image-information-in-image-lists.md)  
  
## <a name="see-also"></a>関連項目  
 [コントロール](../mfc/controls-mfc.md)

