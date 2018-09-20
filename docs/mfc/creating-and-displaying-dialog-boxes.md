---
title: 作成して、ダイアログ ボックスの表示 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 437fb934e95ce527a77038d643e9cee86b6f1f2c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387745"
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

