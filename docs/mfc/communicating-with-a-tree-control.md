---
title: ツリー コントロールとの情報のやり取り
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: a5749b76468a7ba30cd48dc3a9b61f2de7ac67b9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654185"
---
# <a name="communicating-with-a-tree-control"></a>ツリー コントロールとの情報のやり取り

メンバー関数を呼び出すさまざまな方法を使用して、 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)オブジェクトの作成方法に依存するオブジェクト。

- ツリー コントロールがダイアログ ボックスである場合は、型のメンバー変数を使用して、 `CTreeCtrl`  ダイアログ ボックスのクラスで作成します。

- ツリー コントロールが子ウィンドウの場合を使用して、`CTreeCtrl`オブジェクトを構築するために使用するオブジェクト (またはポインター)。

- 使用している場合、`CTreeView`オブジェクト、関数を使用して[CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl)ツリーのコントロールへの参照を取得します。 この値を持つ別の参照を初期化したりへの参照のアドレスを割り当てる、`CTreeCtrl`ポインター。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

