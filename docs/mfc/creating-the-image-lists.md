---
title: イメージ リストの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e5f5ac8396c32e56e4c0f2f951f45bb33714822
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-image-lists"></a>イメージ リストの作成
使用するかどうかは、同じイメージ リストの作成[CListView](../mfc/reference/clistview-class.md)または[CListCtrl](../mfc/reference/clistctrl-class.md)です。  
  
> [!NOTE]
>  のみ必要がありますをイメージ リストのリスト コントロールが含まれている場合、`LVS_ICON`スタイル。  
  
 クラスを使用して`CImageList`(フルサイズのアイコン、小さいアイコン、および状態) の 1 つまたは複数のイメージ リストを作成します。 参照してください[CImageList](../mfc/reference/cimagelist-class.md)、しを参照してください[リスト ビューのイメージ リスト](http://msdn.microsoft.com/library/windows/desktop/bb774736)Windows SDK に含まれています。  
  
 呼び出す[CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist)各イメージ リスト以外の場合は、適切なへのポインターを渡す`CImageList`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

