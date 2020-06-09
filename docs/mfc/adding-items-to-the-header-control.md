---
title: ヘッダー コントロールへの項目の追加
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
ms.openlocfilehash: 5749a0cae2dfe7e6c9f4c166eca487e36c2d21d2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616464"
---
# <a name="adding-items-to-the-header-control"></a>ヘッダー コントロールへの項目の追加

ヘッダーコントロール ([CHeaderCtrl](reference/cheaderctrl-class.md)) を親ウィンドウに作成したら、必要に応じて "ヘッダー項目" をいくつか追加します。通常は、列ごとに1つずつ追加します。

### <a name="to-add-a-header-item"></a>ヘッダー項目を追加するには

1. [HD_ITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw)構造体を準備します。

1. [CHeaderCtrl:: InsertItem](reference/cheaderctrl-class.md#insertitem)を呼び出し、構造体を渡します。

1. その他の項目についても、手順 1. と手順 2. を繰り返します。

詳細については、「Windows SDK での[ヘッダーコントロールへの項目の追加](/windows/win32/Controls/header-controls)」を参照してください。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](using-cheaderctrl.md)<br/>
[制限](controls-mfc.md)
