---
title: 作成して、ダイアログ ボックスを表示する |Microsoft ドキュメント
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
ms.openlocfilehash: 0fcac345a572f8b33d76692d6852e2dc28698367
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342463"
---
# <a name="creating-and-displaying-dialog-boxes"></a>ダイアログ ボックスの作成と表示
2 フェーズの操作は、ダイアログ ボックスのオブジェクトを作成します。 最初に、ダイアログのオブジェクトを構築し、ダイアログ ウィンドウを作成します。 モーダルとモードレスのダイアログ ボックスでは、作成し、それらを表示するために使用するプロセスが少し異なります。 次の表は、どのモーダルとモードレスのダイアログ ボックスは通常構築し、表示されます。  
  
### <a name="dialog-creation"></a>ダイアログの作成  
  
|ダイアログの種類|それを作成する方法|  
|-----------------|----------------------|  
|[モードレス](../mfc/creating-modeless-dialog-boxes.md)|構築`CDialog`、まず**作成**メンバー関数。|  
|[モーダル](../mfc/creating-modal-dialog-boxes.md)|構築`CDialog`、まず`DoModal`メンバー関数。|  
  
 、する場合は、作成、ダイアログ ボックスから、[インメモリでダイアログ テンプレート](../mfc/using-a-dialog-template-in-memory.md)構築するダイアログ テンプレート リソースからではなくです。 ただし、高度なトピックでは、します。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

