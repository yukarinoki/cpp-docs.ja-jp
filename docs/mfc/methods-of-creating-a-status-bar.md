---
title: ステータス バーの作成方法
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
ms.openlocfilehash: 9bdaa76dc68467dce1021d9b5f54eaafa248c529
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624266"
---
# <a name="methods-of-creating-a-status-bar"></a>ステータス バーの作成方法

MFC には、ステータスバーを作成するための2つのクラスが用意されています。 [CStatusBar](reference/cstatusbar-class.md)と[CStatusBarCtrl](reference/cstatusbarctrl-class.md) (Windows コモンコントロール API をラップする) です。 `CStatusBar`は、ステータスバーコモンコントロールのすべての機能を提供し、メニューやツールバーと自動的に対話します。また、必要な共通のコントロール設定と構造の多くを処理します。ただし、結果の実行可能ファイルは通常、を使用して作成したものよりも大きくなり `CStatusBarCtrl` ます。

`CStatusBarCtrl`通常は、より小さな実行可能ファイルが生成 `CStatusBarCtrl` されます。ステータスバーを MFC アーキテクチャに統合しない場合は、を使用することをお勧めします。 `CStatusBarCtrl`ステータスバーを使用して mfc アーキテクチャに統合する予定がある場合は、ステータスバーコントロールの操作を mfc に伝えるために、さらに注意する必要があります。 この通信は難しくありません。ただし、を使用する場合は、不要な追加作業です `CStatusBar` 。

Visual C++ には、ステータスバーのコモンコントロールを利用する2つの方法があります。

- を使用してステータスバーを作成 `CStatusBar` し、 [CStatusBar:: GetStatusBarCtrl](reference/cstatusbar-class.md#getstatusbarctrl)を呼び出してメンバー関数へのアクセスを取得し `CStatusBarCtrl` ます。

- [CStatusBarCtrl](reference/cstatusbarctrl-class.md)のコンストラクターを使用してステータスバーを作成します。

どちらの方法でも、ステータスバーコントロールのメンバー関数へのアクセス権が付与されます。 を呼び出すと `CStatusBar::GetStatusBarCtrl` 、 `CStatusBarCtrl` メンバー関数のいずれかを使用できるように、オブジェクトへの参照が返されます。 を使用したステータスバーの構築と作成の詳細については、「 [CStatusBar](reference/cstatusbar-class.md) 」を参照してください `CStatusBar` 。

## <a name="see-also"></a>関連項目

[CStatusBarCtrl の使い方](using-cstatusbarctrl.md)<br/>
[制限](controls-mfc.md)
