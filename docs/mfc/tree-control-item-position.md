---
description: 詳細については、「ツリーコントロール項目の位置」を参照してください。
title: ツリー コントロールの項目位置
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
ms.openlocfilehash: 7eeab82c48344f7e16a31b8d6962007024277dfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264073"
---
# <a name="tree-control-item-position"></a>ツリー コントロールの項目位置

項目の初期位置は、メンバー関数を使用して項目がツリーコントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) に追加されたときに設定され `InsertItem` ます。 メンバー関数呼び出しでは、親項目のハンドルと、新しい項目を挿入する前の項目のハンドルを指定します。 2番目のハンドルは、指定された親の子項目を識別するか `TVI_FIRST` 、、、またはのいずれかの値を識別する必要があり `TVI_LAST` `TVI_SORT` ます。

またはが指定されている場合 `TVI_FIRST` `TVI_LAST` 、ツリーコントロールは、指定された親項目の子項目のリストの先頭または末尾に新しい項目を配置します。 `TVI_SORT`を指定すると、項目ラベルのテキストに基づいて、新しい項目が子項目のリストにアルファベット順に挿入されます。

[Sortchildren](../mfc/reference/ctreectrl-class.md#sortchildren)メンバー関数を呼び出すと、親アイテムの子アイテムのリストをアルファベット順に並べ替えることができます。 この関数には、特定の親項目から降順に子項目のすべてのレベルを並べ替えるかどうかを指定するパラメーターが含まれています。

[SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb)メンバー関数を使用すると、定義した条件に基づいて子項目を並べ替えることができます。 この関数を呼び出す場合は、2つの子項目の相対的な順序を決定する必要があるときに、ツリーコントロールが呼び出すことができるアプリケーション定義のコールバック関数を指定します。 コールバック関数は、比較対象の項目に対して 2 32 ビットのアプリケーション定義値を受け取り、を呼び出すときに指定する32ビットの3番目の値を受け取り `SortChildrenCB` ます。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
