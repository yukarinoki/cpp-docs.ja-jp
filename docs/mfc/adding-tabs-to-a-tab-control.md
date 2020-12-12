---
description: '詳細情報: タブコントロールへのタブの追加'
title: タブ コントロールへのタブの追加
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: ca25edf349fb11271d4e355241f4724d11bc4ac0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185467"
---
# <a name="adding-tabs-to-a-tab-control"></a>タブ コントロールへのタブの追加

タブコントロール ([CTabCtrl](reference/ctabctrl-class.md)) を作成したら、必要な数だけタブを追加します。

### <a name="to-add-a-tab-item"></a>タブ項目を追加するには

1. [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw)構造体を準備します。

1. 構造体を渡して、 [CTabCtrl:: InsertItem](reference/ctabctrl-class.md#insertitem)を呼び出します。

1. 追加のタブ項目について、手順 1. と手順 2. を繰り返します。

詳細については、「Windows SDK での [タブコントロールの作成](/windows/win32/Controls/tab-controls) 」を参照してください。

## <a name="see-also"></a>関連項目

[CTabCtrl の使い方](using-ctabctrl.md)<br/>
[コントロール](controls-mfc.md)
