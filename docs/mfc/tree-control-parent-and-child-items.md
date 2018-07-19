---
title: ツリー コントロールの親と子項目 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7937ef604d14c464141c6e432a4d20a9d06e172
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954508"
---
# <a name="tree-control-parent-and-child-items"></a>ツリー コントロールの親項目と子項目
ツリー コントロールの項目 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 関連付けられている子項目と呼ばれる、サブ項目の一覧を持つことができます。 1 つまたは複数の子項目をあるアイテムには、親項目が呼び出されます。 子項目は、親項目下に表示され、親のサブことを示すためにインデントされます。 親を持たない項目は、階層の最上部となりますルート項目は呼び出されます。  
  
 任意の時点で子アイテムの親項目の一覧の状態できますか、展開したり折りたたんだりできます。 状態を展開すると、親項目の下の子アイテムが表示されます。 折りたたまれている場合、子項目は表示されません。 親項目をダブルクリックするか、親がある、この一覧は、自動的に展開と折りたたまれた状態の間でを切り替えます、**切り替え**スタイル、ユーザーには、親アイテムに関連付けられたボタンがクリックしたとき。 アプリケーションは展開したりを使用して、子項目を折りたたんだり、[展開](../mfc/reference/ctreectrl-class.md#expand)メンバー関数。  
  
 ツリー コントロールを呼び出すことによって項目を追加する、 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem)メンバー関数。 この関数のハンドルを返します、 **HTREEITEM**型で、アイテムを一意に識別します。 項目を追加する場合は、新しい項目の親アイテムのハンドルを指定する必要があります。 指定した場合**NULL**または**TVI_ROOT**で親アイテムのハンドルではなく値、 [TVINSERTSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb773452)構造または*hParent*パラメーターをルート項目として追加されます。  
  
 ツリー コントロールの送信、 [TVN_ITEMEXPANDING](http://msdn.microsoft.com/library/windows/desktop/bb773537)子アイテムの親項目の一覧を展開したり折りたたんだりできるときに通知メッセージです。 通知では、変更を防ぐために、または子項目の一覧の状態に依存する親項目の属性を設定することをテストできます。 ツリー コントロールの送信、一覧の状態を変更した後、 [TVN_ITEMEXPANDED](http://msdn.microsoft.com/library/windows/desktop/bb773533)通知メッセージです。  
  
 子アイテムの一覧を展開すると、親項目を基準にインデントされます。 使用してインデントの値を設定することができます、 [SetIndent](../mfc/reference/ctreectrl-class.md#setindent)メンバー関数または取得を使用して現在の量、 [GetIndent](../mfc/reference/ctreectrl-class.md#getindent)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

