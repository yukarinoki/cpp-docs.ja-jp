---
title: ツリー コントロールの親項目と子項目
ms.date: 11/04/2016
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
ms.openlocfilehash: 2961009e3f1b21c3caacec001c53f5e52740dd67
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304575"
---
# <a name="tree-control-parent-and-child-items"></a>ツリー コントロールの親項目と子項目

ツリー コントロールの項目 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 関連付けられている子アイテムと呼ばれるサブ項目の一覧を持つことができます。 1 つまたは複数の子項目が含まれている項目は、親アイテムと呼ばれます。 子項目は、親項目の下に表示され、親の下位であることを示すインデントされます。 親を持たない項目は、階層の最上部にし、ルート項目が呼び出されます。

、特定の時点子項目の親項目の一覧の状態か、展開または折りたたまれています。 状態が展開されている場合は、親項目の下に子項目が表示されます。 折りたたまれている場合は、子項目は表示されません。 親がある場合またはユーザーが親項目をダブルクリックすると、この一覧は、自動的に展開された、折りたたまれた状態の間を切り替えます、**切り替え**スタイル、ユーザーが親項目に関連付けられたボタンをクリックするとします。 アプリケーションの展開またはを使用して子項目を折りたたむことができます、[展開](../mfc/reference/ctreectrl-class.md#expand)メンバー関数。

呼び出すことによって、ツリー コントロールに項目を追加する、 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem)メンバー関数。 この関数のハンドルを返します、 **HTREEITEM**型で、アイテムを一意に識別します。 項目を追加する場合は、新しい項目の親項目のハンドルを指定する必要があります。 指定した場合**NULL**または**TVI_ROOT**で親項目のハンドルではなく値、 [TVINSERTSTRUCT](/windows/desktop/api/commctrl/ns-commctrl-tagtvinsertstructa)構造または*hParent*パラメーター項目は、ルート項目として追加されます。

ツリー コントロールが送信する、 [TVN_ITEMEXPANDING](/windows/desktop/Controls/tvn-itemexpanding)子項目の親項目の一覧が展開したり折りたたんだりするときに通知メッセージ。 通知では、営業案件を変更を防ぐために、または子項目の一覧の状態に依存する親項目の属性を設定できます。 ツリー コントロールの送信、リストの状態を変更した後、 [TVN_ITEMEXPANDED](/windows/desktop/Controls/tvn-itemexpanded)通知メッセージ。

子アイテムの一覧が展開されている場合は、親アイテムに対して相対的インデントされます。 使用してインデントの量を設定することができます、 [SetIndent](../mfc/reference/ctreectrl-class.md#setindent)メンバー関数または取得を使用して現在の量、 [GetIndent](../mfc/reference/ctreectrl-class.md#getindent)メンバー関数。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
