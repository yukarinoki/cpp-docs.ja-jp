---
title: ダイアログ ボックスでの Windows メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- Windows messages [MFC], handling
- message handling [MFC], in dialog boxes
ms.assetid: 4af0c9cb-09da-4b15-97df-a1cfb89def79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8773f7b93c67441fdf1cf6b6b992b152da14619
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401018"
---
# <a name="handling-windows-messages-in-your-dialog-box"></a>ダイアログ ボックスでの Windows メッセージの処理

ダイアログ ボックスでは、適切なハンドラー関数を指定する場合に Windows メッセージを処理できるように、windows がされます。 クラスの追加ウィザードとダイアログ クラスを作成するときに、ウィザードは、空のメッセージ マップをクラスに追加します。 任意の Windows メッセージやコマンドを処理するのにクラスにマップするのにには、[プロパティ] ウィンドウを使用します。

参照してください[ダイアログ クラスの Windows メッセージの割り当て](../mfc/mapping-windows-messages-to-your-class.md)詳細についてはします。

## <a name="see-also"></a>関連項目

[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

