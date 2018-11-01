---
title: タブ コントロールへのタブの追加
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: be622035355a68d1527a515bfdcb633a3af274d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618271"
---
# <a name="adding-tabs-to-a-tab-control"></a>タブ コントロールへのタブの追加

タブ コントロールを作成した後 ([CTabCtrl](../mfc/reference/ctabctrl-class.md))、タブは、必要な数だけを追加します。

### <a name="to-add-a-tab-item"></a>タブ項目を追加するには

1. 準備、 [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema)構造体。

1. 呼び出す[として](../mfc/reference/ctabctrl-class.md#insertitem)、構造体を渡します。

1. 追加のタブ項目の手順 1. および 2. を繰り返します。

詳細については、次を参照してください。[タブ コントロールを作成する](/windows/desktop/Controls/tab-controls)Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[CTabCtrl の使い方](../mfc/using-ctabctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

