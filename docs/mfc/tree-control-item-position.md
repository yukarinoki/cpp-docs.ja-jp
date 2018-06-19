---
title: ツリーのコントロールの項目位置 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7b7576786f456320a355920a7a9ef9e4935ab03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382152"
---
# <a name="tree-control-item-position"></a>ツリー コントロールの項目位置
ツリー コントロールに項目が追加されたときに、最初の項目の位置に設定されている ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) を使用して、`InsertItem`メンバー関数。 メンバー関数の呼び出しは、親アイテムのハンドルと、その後、新しい項目を挿入する項目のハンドルを指定します。 2 番目のハンドルは、指定した親の子項目を識別する必要がありますか、これらのいずれかの値: `TVI_FIRST`、 `TVI_LAST`、または`TVI_SORT`です。  
  
 ときに`TVI_FIRST`または`TVI_LAST`を指定すると、ツリー コントロールは、先頭または指定された親項目の子項目の一覧の末尾に新しいアイテムを配置します。 ときに`TVI_SORT`を指定すると、ツリー コントロールでは、項目のラベルのテキストに基づいてアルファベット順での子項目の一覧に新しい項目を挿入します。  
  
 アルファベット順に子項目の親項目の一覧を配置するには呼び出すことによって、 [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren)メンバー関数。 この関数には、すべてのレベルの子項目が指定された親アイテムから降順がアルファベット順に並べ替えるもかどうかを指定するパラメーターが含まれます。  
  
 [SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb)メンバー関数は、定義されている条件に基づいた子項目を並べ替えることができます。 この関数を呼び出すときに、ツリー コントロールが 2 つの子項目の相対順序を決定する必要があるときに呼び出すことができるアプリケーション定義のコールバック関数を指定します。 コールバック関数は 2 つ 32 ビット アプリケーション定義の値の比較対象となる項目とを呼び出すときに指定する 3 番目の 32 ビット値受信`SortChildrenCB`です。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

