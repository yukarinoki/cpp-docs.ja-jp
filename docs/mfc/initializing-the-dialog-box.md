---
title: ダイアログ ボックスの初期化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7918180a437687eded090b3d014e4affe38fe8f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344712"
---
# <a name="initializing-the-dialog-box"></a>ダイアログ ボックスの初期化
作成した後、ダイアログ ボックスとそのすべてのコントロールは、直前に、ダイアログ ボックスのいずれかの種類) ボックス、画面に表示されるダイアログ オブジェクトの[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)メンバー関数が呼び出されます。 モーダル ダイアログ ボックスの中にこれが発生した、`DoModal`呼び出します。 モードレス ダイアログ ボックスの`OnInitDialog`時に呼び出される**作成**と呼びます。 通常、オーバーライドする`OnInitDialog`エディット ボックスの最初のテキストを設定するなど、ダイアログ ボックスのコントロールを初期化します。 呼び出す必要があります、 `OnInitDialog` 、基底クラスのメンバー関数`CDialog`から、`OnInitDialog`をオーバーライドします。  
  
 ダイアログ ボックスの背景色 (および、アプリケーション内の他のすべてのダイアログ ボックス) を設定する場合は、「 [ ダイアログ ボックスの背景色を設定](../mfc/setting-the-dialog-boxs-background-color.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

