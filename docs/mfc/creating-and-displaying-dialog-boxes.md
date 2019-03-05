---
title: ダイアログ ボックスの作成と表示
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
ms.openlocfilehash: e0b7ff31576b345ac2911e62a6e10469845eecba
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302316"
---
# <a name="creating-and-displaying-dialog-boxes"></a>ダイアログ ボックスの作成と表示

2 フェーズの操作は、ダイアログ ボックスのオブジェクトを作成します。 最初に、ダイアログのオブジェクトを構築し、ダイアログ ウィンドウを作成します。 モーダルとモードレスのダイアログ ボックスでは、作成し、それらを表示するために使用するプロセスが少し異なります。 次の表では、どのモーダルおよびモードレス ダイアログ ボックスは通常生成方法し、表示を示します。

### <a name="dialog-creation"></a>ダイアログの作成

|ダイアログの種類|これを作成する方法|
|-----------------|----------------------|
|[モードレス](../mfc/creating-modeless-dialog-boxes.md)|構築`CDialog`、呼び出して`Create`メンバー関数。|
|[モーダル](../mfc/creating-modal-dialog-boxes.md)|構築`CDialog`、呼び出して`DoModal`メンバー関数。|

する場合は、作成できますからダイアログ ボックス、[メモリ内のダイアログ テンプレート](../mfc/using-a-dialog-template-in-memory.md)作成したダイアログ テンプレート リソースからではなく。 ただし、高度なトピックになります。

## <a name="see-also"></a>関連項目

[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)
