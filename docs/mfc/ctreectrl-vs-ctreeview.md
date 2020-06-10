---
title: CTreeCtrl と CTreeView の比較
ms.date: 11/04/2016
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: 83e07c75b9eab6df05dbcd0f52cfbe8b90e1d768
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620479"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl と CTreeView の比較

MFC には、ツリーコントロールをカプセル化する2つのクラス ( [CTreeCtrl](reference/ctreectrl-class.md)と[CTreeView](reference/ctreeview-class.md)) が用意されています。 各クラスは、状況に応じて役に立ちます。

たとえば `CTreeCtrl` 、ダイアログボックスで、単純な子ウィンドウコントロールが必要な場合に使用します。 `CTreeCtrl`一般的なダイアログボックスのように、ウィンドウに他の子コントロールがある場合は、を使用することをお勧めします。

ツリーコントロール `CTreeView` を、ドキュメント/ビューアーキテクチャのビューウィンドウと同じように、またはツリーコントロールとして動作させる場合に使用します。 は、 `CTreeView` フレームウィンドウまたはスプリッターウィンドウのクライアント領域全体を占有します。 親ウィンドウのサイズが変更されると、自動的にサイズが変更されます。また、メニュー、アクセラレータキー、およびツールバーからコマンドメッセージを処理することもできます。 ツリーコントロールには、ツリーを表示するために必要なデータが含まれているため、対応するドキュメントオブジェクトは複雑である必要はありません。ドキュメントテンプレートでは、ドキュメントの種類として[CDocument](reference/cdocument-class.md)を使用することもできます。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](using-ctreectrl.md)<br/>
[制限](controls-mfc.md)
