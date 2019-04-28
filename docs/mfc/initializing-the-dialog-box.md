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
ms.openlocfilehash: 87b3405f1441e730cf5c9ce7fc03d2c7372e55db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297100"
---
# <a name="initializing-the-dialog-box"></a>ダイアログ ボックスの初期化

ボックスとそのすべてのコントロールの作成後、ダイアログが直前に、ダイアログ ボックス (のいずれかの種類)、画面に表示されるダイアログ オブジェクトの[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)メンバー関数が呼び出されます。 モーダル ダイアログ ボックスの中にこれが発生した、`DoModal`呼び出します。 モードレス ダイアログ ボックスの`OnInitDialog`時に呼び出される`Create`が呼び出されます。 通常オーバーライドする`OnInitDialog`エディット ボックスの最初のテキストを設定するなどのダイアログ ボックスのコントロールを初期化します。 呼び出す必要があります、 `OnInitDialog` 、基底クラスのメンバー関数`CDialog`から、`OnInitDialog`をオーバーライドします。

ダイアログ ボックスの背景色 (および、アプリケーションで他のすべてのダイアログ ボックス) を設定する場合は、「 [ ダイアログ ボックスの背景色を設定](../mfc/setting-the-dialog-boxs-background-color.md)します。

## <a name="see-also"></a>関連項目

[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)
