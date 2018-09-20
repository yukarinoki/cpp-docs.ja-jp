---
title: CTreeCtrl とCtreeview の比較 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CTreeCtrl
- CTreeView
dev_langs:
- C++
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8acaecbdfb99b8ae0b27023145a0ef6aee1f219
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399152"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl とCTreeView

MFC には、ツリーのコントロールをカプセル化する 2 つのクラスが用意されています: [CTreeCtrl](../mfc/reference/ctreectrl-class.md)と[CTreeView](../mfc/reference/ctreeview-class.md)します。 各クラスは、さまざまな状況で役立ちます。

使用`CTreeCtrl`プレーンな子ウィンドウ コントロールである必要がある場合、ダイアログ ボックスで、します。 使用することが特に`CTreeCtrl`他の子コントロールが一般的なダイアログ ボックスのように、ウィンドウ内にある場合。

使用`CTreeView`ドキュメント/ビュー アーキテクチャでビュー ウィンドウと同様に動作するツリー コントロールとツリー コントロールたい場合。 A`CTreeView`のフレーム ウィンドウまたはスプリッター ウィンドウ全体のクライアント領域を占有します。 自動的にサイズを調整する親ウィンドウのサイズを変更し、メニューのアクセラレータ キー、およびツールバーからコマンド メッセージを処理するときにします。 ツリー コントロールにツリーを表示するために必要なデータが格納されているため、対応するドキュメント オブジェクトを複雑になるにはありません-使用することもできます[CDocument](../mfc/reference/cdocument-class.md)ドキュメント テンプレートにドキュメントの種類として。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

