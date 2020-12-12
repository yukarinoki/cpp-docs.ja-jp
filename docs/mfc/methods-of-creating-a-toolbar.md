---
description: '詳細情報: ツールバーを作成する方法'
title: ツール バーの作成方法
ms.date: 11/04/2016
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
ms.openlocfilehash: 14626f398d3ccabd002cc21be682c1a5616a0410
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203082"
---
# <a name="methods-of-creating-a-toolbar"></a>ツール バーの作成方法

MFC には、 [CToolBar](reference/ctoolbar-class.md) と [CToolBarCtrl](reference/ctoolbarctrl-class.md) (Windows コモンコントロール API をラップするツールバー) を作成するための2つのクラスが用意されています。 `CToolBar` ツールバーコモンコントロールのすべての機能を提供し、必要な共通コントロール設定と構造の多くを処理します。ただし、結果の実行可能ファイルは通常、を使用して作成したものよりも大きくなり `CToolBarCtrl` ます。

`CToolBarCtrl` は通常、より小さな実行可能ファイルになり `CToolBarCtrl` ます。ツールバーを MFC アーキテクチャに統合しない場合は、を使用することをお勧めします。 ツールバーを使用して MFC アーキテクチャに統合する予定がある場合は `CToolBarCtrl` 、ツールバーコントロールの操作を mfc に伝えるために、さらに注意する必要があります。 この通信は難しくありません。ただし、を使用する場合は、不要な追加作業です `CToolBar` 。

Visual C++ には、ツールバーコモンコントロールを利用する2つの方法が用意されています。

- を使用してツールバーを作成 `CToolBar` し、次に [CToolBar:: GetToolBarCtrl](reference/ctoolbar-class.md#gettoolbarctrl) を呼び出して、メンバー関数にアクセスできるようにし `CToolBarCtrl` ます。

- [CToolBarCtrl](reference/ctoolbarctrl-class.md)のコンストラクターを使用してツールバーを作成します。

どちらの方法でも、ツールバーコントロールのメンバー関数へのアクセス権が付与されます。 を呼び出すと `CToolBar::GetToolBarCtrl` 、 `CToolBarCtrl` メンバー関数のいずれかを使用できるように、オブジェクトへの参照が返されます。 を使用したツールバーの構築と作成の詳細については、「 [CToolBar](reference/ctoolbar-class.md) 」を参照してください `CToolBar` 。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](using-ctoolbarctrl.md)<br/>
[コントロール](controls-mfc.md)
