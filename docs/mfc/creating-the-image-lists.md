---
description: '詳細情報: イメージリストの作成'
title: イメージ リストの作成
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: f2776902e7be06161bdbcfad23bd21d9188467f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309668"
---
# <a name="creating-the-image-lists"></a>イメージ リストの作成

[CListView](reference/clistview-class.md)と[CListCtrl](reference/clistctrl-class.md)のどちらを使用する場合でも、イメージリストの作成は同じです。

> [!NOTE]
> リストコントロールにスタイルが含まれている場合にのみ、イメージリストが必要に `LVS_ICON` なります。

クラスを使用し `CImageList` て、1つまたは複数のイメージリストを作成します (フルサイズのアイコン、小さいアイコン、状態)。 「 [CImageList](reference/cimagelist-class.md)」を参照し、Windows SDK の [リストビューのイメージリスト](/windows/win32/Controls/using-list-view-controls) を参照してください。

各イメージリストに対して、 [CListCtrl:: SetImageList](reference/clistctrl-class.md#setimagelist) を呼び出します。適切なオブジェクトへのポインターを渡し `CImageList` ます。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](using-clistctrl.md)<br/>
[コントロール](controls-mfc.md)
