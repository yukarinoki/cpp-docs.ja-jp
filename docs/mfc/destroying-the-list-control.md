---
title: リスト コントロールの破棄
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: d128a613a2a4cb595f362f843a5ae2eba830e538
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621894"
---
# <a name="destroying-the-list-control"></a>リスト コントロールの破棄

ビューまたはダイアログクラスのデータメンバーとして[CListCtrl](reference/clistctrl-class.md)オブジェクトを埋め込むと、その所有者が破棄されるときに破棄されます。 [CListView](reference/clistview-class.md)を使用する場合、フレームワークはビューを破棄するときにコントロールを破棄します。

リストコントロールではなくアプリケーションに格納するリストデータの一部を配置する場合は、その割り当てを解除する必要があります。 詳細については、「Windows SDK での[コールバック項目とコールバックマスク](/windows/win32/Controls/using-list-view-controls)」を参照してください。

また、作成したイメージリストの割り当てを解除して、リストコントロールオブジェクトに関連付けることもできます。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](using-clistctrl.md)<br/>
[制限](controls-mfc.md)
