---
title: ダイアログ ボックスの初期化
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 1f8f8f7e40b1c873c4428542c628d02e250f14b4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626336"
---
# <a name="initializing-the-dialog-box"></a>ダイアログ ボックスの初期化

ダイアログボックスとそのすべてのコントロールが作成された後、ダイアログボックス (どちらかの種類) が画面に表示される直前に、ダイアログオブジェクトの[OnInitDialog](reference/cdialog-class.md#oninitdialog)メンバー関数が呼び出されます。 モーダルダイアログボックスの場合は、呼び出し中に発生し `DoModal` ます。 モードレスダイアログボックスの場合、が `OnInitDialog` 呼び出されると、が呼び出され `Create` ます。 通常は、 `OnInitDialog` エディットボックスの初期テキストの設定など、ダイアログボックスのコントロールを初期化するようにオーバーライドします。 `OnInitDialog`オーバーライドから、基本クラスのメンバー関数を呼び出す必要があり `CDialog` `OnInitDialog` ます。

ダイアログボックスの背景色 (およびアプリケーション内の他のすべてのダイアログボックスの背景色) を設定する場合は、「[ダイアログボックスの背景色を設定](setting-the-dialog-boxs-background-color.md)する」を参照してください。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
