---
title: ツリー コントロール項目情報 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 724e9d7c4e0ee7db80f024c30e363612cb40fed1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-item-information"></a>ツリー コントロールの項目の情報
ツリー コントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) コントロール内の項目に関する情報を取得するメンバー関数の数が必要です。 [GetItem](../mfc/reference/ctreectrl-class.md#getitem)メンバー関数は、一部またはすべての項目に関連付けられているデータを取得します。 このデータには、項目のテキスト、状態、イメージ、子項目の数およびアプリケーション定義の 32 ビット データ値を含めることができます。 [SetItem](../mfc/reference/ctreectrl-class.md#setitem)一部またはすべての項目に関連付けられているデータを設定する関数。  
  
 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate)、 [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext)、 [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata)、および[GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage)メンバー関数での個々 の属性を取得します。項目。 これらの各関数は、項目の属性を設定するための対応する Set 関数。  
  
 [れた](../mfc/reference/ctreectrl-class.md#getnextitem)メンバー関数を現在のアイテムに指定されたリレーションシップを持つツリー コントロール項目を取得します。 この関数および取得できます、アイテムの親、次または前に表示される項目、最初子項目にします。 また、ツリーを走査するメンバー関数は: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem)、 [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem)、 [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem)、 [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem)、 [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem)、 [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem)、 [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem)、 [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem)、 [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem)、および[GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem)です。  
  
 [GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect)メンバー関数は、ツリー コントロールの項目の外接する四角形を取得します。 [GetCount](../mfc/reference/ctreectrl-class.md#getcount)と[GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount)メンバー関数では、現在表示されているツリー コントロールのウィンドウで、それぞれのアイテムの数およびツリー コントロール内の項目の数を取得します。 呼び出して、特定の項目が表示されていることを確認することができます、 [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

