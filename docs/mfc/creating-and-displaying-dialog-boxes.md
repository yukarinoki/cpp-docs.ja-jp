---
description: '詳細情報: ダイアログボックスの作成と表示'
title: ダイアログ ボックスの作成と表示
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
ms.openlocfilehash: 9865e43392021cc7ba1349a73bffb8e47f4cca9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309826"
---
# <a name="creating-and-displaying-dialog-boxes"></a>ダイアログ ボックスの作成と表示

ダイアログオブジェクトの作成は、2フェーズ操作です。 まず、ダイアログオブジェクトを構築してから、ダイアログウィンドウを作成します。 モーダルおよびモードレスのダイアログボックスは、それらを作成および表示するために使用されるプロセスで多少異なります。 次の表に、モーダルおよびモードレスのダイアログボックスを通常作成して表示する方法を示します。

### <a name="dialog-creation"></a>ダイアログの作成

|ダイアログの種類|作成方法|
|-----------------|----------------------|
|[Modeless](creating-modeless-dialog-boxes.md)|を構築し `CDialog` 、次に `Create` メンバー関数を呼び出します。|
|[モーダル](creating-modal-dialog-boxes.md)|を構築し `CDialog` 、次に `DoModal` メンバー関数を呼び出します。|

必要に応じて、ダイアログテンプレートリソースからではなく、構築した [メモリ内ダイアログテンプレート](using-a-dialog-template-in-memory.md) からダイアログボックスを作成できます。 ただし、これは高度なトピックです。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
