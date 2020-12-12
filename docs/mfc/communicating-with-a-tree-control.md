---
description: 詳細については、「ツリーコントロールとの通信」を参照してください。
title: ツリー コントロールとの情報のやり取り
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: 82ee4fe0beb65e44166b4d68ffd44923b7fe0c76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310565"
---
# <a name="communicating-with-a-tree-control"></a>ツリー コントロールとの情報のやり取り

オブジェクトの作成方法に応じて、次のように、 [CTreeCtrl](reference/ctreectrl-class.md) オブジェクトでメンバー関数を呼び出すために別のメソッドを使用します。

- ツリーコントロールがダイアログボックス内にある場合は、 `CTreeCtrl` ダイアログボックスクラスで作成した型のメンバー変数を使用します。

- ツリーコントロールが子ウィンドウの場合は、 `CTreeCtrl` オブジェクトの構築に使用したオブジェクト (またはポインター) を使用します。

- オブジェクトを使用している場合は `CTreeView` 、 [CTreeView:: treeview](reference/ctreeview-class.md#gettreectrl) 関数を使用して、ツリーコントロールへの参照を取得します。 この値を使用して別の参照を初期化するか、参照のアドレスをポインターに割り当てることができ `CTreeCtrl` ます。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](using-ctreectrl.md)<br/>
[コントロール](controls-mfc.md)
