---
description: 詳細については、「List コントロールの破棄」を参照してください。
title: リスト コントロールの破棄
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: b909889a6365de639f67359859641af6e2bc6525
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327825"
---
# <a name="destroying-the-list-control"></a>リスト コントロールの破棄

ビューまたはダイアログクラスのデータメンバーとして [CListCtrl](reference/clistctrl-class.md) オブジェクトを埋め込むと、その所有者が破棄されるときに破棄されます。 [CListView](reference/clistview-class.md)を使用する場合、フレームワークはビューを破棄するときにコントロールを破棄します。

リストコントロールではなくアプリケーションに格納するリストデータの一部を配置する場合は、その割り当てを解除する必要があります。 詳細については、「Windows SDK での [コールバック項目とコールバックマスク](/windows/win32/Controls/using-list-view-controls) 」を参照してください。

また、作成したイメージリストの割り当てを解除して、リストコントロールオブジェクトに関連付けることもできます。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](using-clistctrl.md)<br/>
[コントロール](controls-mfc.md)
