---
title: CTreeCtrl と CTreeView の比較
ms.date: 11/04/2016
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: 7c78dfa9920c913fdbedb009c5a6f275a3e3e273
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445221"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl と CTreeView の比較

MFC には、ツリーコントロールをカプセル化する2つのクラス ( [CTreeCtrl](../mfc/reference/ctreectrl-class.md)と[CTreeView](../mfc/reference/ctreeview-class.md)) が用意されています。 各クラスは、状況に応じて役に立ちます。

`CTreeCtrl` は、プレーンな子ウィンドウコントロールが必要な場合に使用します。たとえば、ダイアログボックスを使用します。 一般的なダイアログボックスのように、ウィンドウに他の子コントロールが存在する場合は、`CTreeCtrl` を使用することをお勧めします。

`CTreeView` を使用すると、ツリーコントロールを、ドキュメント/ビューアーキテクチャのビューウィンドウのように、またはツリーコントロールとして動作させることができます。 `CTreeView` は、フレームウィンドウまたは分割ウィンドウのクライアント領域全体を占有します。 親ウィンドウのサイズが変更されると、自動的にサイズが変更されます。また、メニュー、アクセラレータキー、およびツールバーからコマンドメッセージを処理することもできます。 ツリーコントロールには、ツリーを表示するために必要なデータが含まれているため、対応するドキュメントオブジェクトは複雑である必要はありません。ドキュメントテンプレートでは、ドキュメントの種類として[CDocument](../mfc/reference/cdocument-class.md)を使用することもできます。

## <a name="see-also"></a>参照

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
