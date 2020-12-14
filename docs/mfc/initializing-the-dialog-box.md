---
description: 詳細については、「ダイアログボックスの初期化」を参照してください。
title: ダイアログ ボックスの初期化
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 317098a8c0cc745bbd4c94b9ed02401774cb0df9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197622"
---
# <a name="initializing-the-dialog-box"></a>ダイアログ ボックスの初期化

ダイアログボックスとそのすべてのコントロールが作成された後、ダイアログボックス (どちらかの種類) が画面に表示される直前に、ダイアログオブジェクトの [OnInitDialog](reference/cdialog-class.md#oninitdialog) メンバー関数が呼び出されます。 モーダルダイアログボックスの場合は、呼び出し中に発生し `DoModal` ます。 モードレスダイアログボックスの場合、が `OnInitDialog` 呼び出されると、が呼び出され `Create` ます。 通常は、 `OnInitDialog` エディットボックスの初期テキストの設定など、ダイアログボックスのコントロールを初期化するようにオーバーライドします。 `OnInitDialog`オーバーライドから、基本クラスのメンバー関数を呼び出す必要があり `CDialog` `OnInitDialog` ます。

ダイアログボックスの背景色 (およびアプリケーション内の他のすべてのダイアログボックスの背景色) を設定する場合は、「 [ダイアログボックスの背景色を設定](setting-the-dialog-boxs-background-color.md)する」を参照してください。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
