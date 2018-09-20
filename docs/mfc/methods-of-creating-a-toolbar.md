---
title: ツールバーの作成方法 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb7e73df0944a7a6c0c7b28c04e43008fcd70b39
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401070"
---
# <a name="methods-of-creating-a-toolbar"></a>ツール バーの作成方法

MFC には、ツールバーを作成する 2 つのクラスが用意されています: [CToolBar](../mfc/reference/ctoolbar-class.md)と[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (ラップしています。 Windows のコモン コントロール API)。 `CToolBar` すべてのツール バー コモン コントロールの機能を提供します必要な一般的なコントロールの設定と構造体の多くを処理し、。ただし、結果として得られる実行可能ファイルは、通常はより大きくするを使用して作成`CToolBarCtrl`です。

`CToolBarCtrl` 小さい実行可能ファイルでの結果を使用することもできます通常`CToolBarCtrl`MFC アーキテクチャにツールバーを統合する予定がない場合。 使用して行う場合`CToolBarCtrl`と MFC アーキテクチャに、ツールバーの統合、mfc ツールバー コントロールの操作を通信するためにさらに注意を行う必要があります。 この通信は困難です。ただしは、使用すると、必要な追加の作業が`CToolBar`します。

Visual C には、ツール バー コモン コントロールを活用するために 2 つの方法が用意されています。

- ツールバーを使用して作成`CToolBar`を呼び出して[CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl)へのアクセスを取得する、`CToolBarCtrl`メンバー関数。

- ツールバーを使用して作成[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)のコンス トラクター。

いずれかの方法、ツール バー コントロールのメンバー関数へアクセスは許可されます。 呼び出すと`CToolBar::GetToolBarCtrl`への参照を返します、`CToolBarCtrl`オブジェクト メンバー関数のいずれかのセットを使用できるようにします。 参照してください[CToolBar](../mfc/reference/ctoolbar-class.md)を構築してを使用して、ツールバーの作成について`CToolBar`します。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

