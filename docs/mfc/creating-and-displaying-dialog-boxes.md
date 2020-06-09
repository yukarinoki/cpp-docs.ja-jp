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
ms.openlocfilehash: 649d64f8e8b894027b9d6850b62d357d79c1dafa
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616269"
---
# <a name="creating-and-displaying-dialog-boxes"></a>ダイアログ ボックスの作成と表示

ダイアログオブジェクトの作成は、2フェーズ操作です。 まず、ダイアログオブジェクトを構築してから、ダイアログウィンドウを作成します。 モーダルおよびモードレスのダイアログボックスは、それらを作成および表示するために使用されるプロセスで多少異なります。 次の表に、モーダルおよびモードレスのダイアログボックスを通常作成して表示する方法を示します。

### <a name="dialog-creation"></a>ダイアログの作成

|ダイアログの種類|作成方法|
|-----------------|----------------------|
|[固定](creating-modeless-dialog-boxes.md)|を構築し `CDialog` 、次に `Create` メンバー関数を呼び出します。|
|[モード](creating-modal-dialog-boxes.md)|を構築し `CDialog` 、次に `DoModal` メンバー関数を呼び出します。|

必要に応じて、ダイアログテンプレートリソースからではなく、構築した[メモリ内ダイアログテンプレート](using-a-dialog-template-in-memory.md)からダイアログボックスを作成できます。 ただし、これは高度なトピックです。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
