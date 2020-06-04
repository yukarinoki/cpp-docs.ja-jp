---
title: CToolTipCtrl を使用して CToolTipCtrl オブジェクトを作成および操作する方法
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
ms.openlocfilehash: 37dc7bc5a411ebab3737b87fd6977b26cff68178
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442218"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>CToolTipCtrl を使用して CToolTipCtrl オブジェクトを作成および操作する方法

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)の使用例を次に示します。

### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>CToolTipCtrl を作成して操作するには

1. `CToolTipCtrl` オブジェクトを構築します。

1. [Create](../mfc/reference/ctooltipctrl-class.md#create)を呼び出して Windows ツールヒントコモンコントロールを作成し、`CToolTipCtrl` オブジェクトにアタッチします。

1. ツールをツールヒントコントロールに登録するには、 [Addtool](../mfc/reference/ctooltipctrl-class.md#addtool)を呼び出します。これにより、ツールヒントに格納されている情報が、カーソルがツール上にあるときに表示されます。

1. [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo)を呼び出して、ツールのツールヒントによって管理される情報を設定します。

1. [Settoolrect](../mfc/reference/ctooltipctrl-class.md#settoolrect)を呼び出して、ツールの新しい外接する四角形を設定します。

1. [System.windows.media.visualtreehelper.hittest](../mfc/reference/ctooltipctrl-class.md#hittest)を呼び出して、特定のツールの外接する四角形内にあるかどうかを確認し、存在する場合はツールに関する情報を取得します。

1. [Gettoolcount](../mfc/reference/ctooltipctrl-class.md#gettoolcount)を呼び出して、ツールヒントコントロールに登録されているツールの数を取得します。

## <a name="see-also"></a>参照

[CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
