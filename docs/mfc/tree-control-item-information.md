---
description: 詳細については、「ツリーコントロール項目の情報」を参照してください。
title: ツリー コントロールの項目の情報
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
ms.openlocfilehash: ced75bdf6ed6a10e3a34536adf4af0ed1c7e0c86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264142"
---
# <a name="tree-control-item-information"></a>ツリー コントロールの項目の情報

ツリーコントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) には、コントロール内の項目に関する情報を取得する多くのメンバー関数があります。 [GetItem](../mfc/reference/ctreectrl-class.md#getitem)メンバー関数は、アイテムに関連付けられたデータの一部またはすべてを取得します。 このデータには、項目のテキスト、状態、画像、子項目の数、およびアプリケーションによって定義された32ビットのデータ値が含まれます。 また、アイテムに関連付けられたデータの一部またはすべてを設定できる [SetItem](../mfc/reference/ctreectrl-class.md#setitem) 関数もあります。

[GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate)、 [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext)、 [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata)、および[GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage)の各メンバー関数は、項目の個々の属性を取得します。 これらの各関数には、項目の属性を設定するための対応するセット関数があります。

[Getnextitem](../mfc/reference/ctreectrl-class.md#getnextitem)メンバー関数は、指定されたリレーションシップを持つツリーコントロール項目を現在の項目に取得します。 この関数は、項目の親、次または前に表示される項目、最初の子項目などを取得できます。 ツリーを走査するためのメンバー関数もあります。 [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem)、 [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem)、 [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem)、 [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem)、 [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem)、 [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem)、 [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem)、 [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem)、 [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem)、 [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem)です。

[GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect)メンバー関数は、ツリーコントロール項目の外接する四角形を取得します。 [GetCount](../mfc/reference/ctreectrl-class.md#getcount)および[GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount)メンバー関数は、ツリーコントロール内の項目の数と、ツリーコントロールのウィンドウに現在表示されている項目の数をそれぞれ取得します。 [Ensurevisible\](../mfc/reference/ctreectrl-class.md#ensurevisible)メンバー関数を呼び出すことによって、特定の項目が表示されるようにすることができます。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
