---
title: ツリー コントロールとの通信 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78bb6a6d6421a5336f8efbffc7d24a6121e208e6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432155"
---
# <a name="communicating-with-a-tree-control"></a>ツリー コントロールとの情報のやり取り

メンバー関数を呼び出すさまざまな方法を使用して、 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)オブジェクトの作成方法に依存するオブジェクト。

- ツリー コントロールがダイアログ ボックスである場合は、型のメンバー変数を使用して、 `CTreeCtrl`  ダイアログ ボックスのクラスで作成します。

- ツリー コントロールが子ウィンドウの場合を使用して、`CTreeCtrl`オブジェクトを構築するために使用するオブジェクト (またはポインター)。

- 使用している場合、`CTreeView`オブジェクト、関数を使用して[CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl)ツリーのコントロールへの参照を取得します。 この値を持つ別の参照を初期化したりへの参照のアドレスを割り当てる、`CTreeCtrl`ポインター。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

