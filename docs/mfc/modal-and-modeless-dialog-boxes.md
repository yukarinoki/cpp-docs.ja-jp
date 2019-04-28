---
title: モーダルとモードレスのダイアログ ボックス
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
ms.openlocfilehash: c3a5263736324d7fe25066e8879d13b3a41768de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238416"
---
# <a name="modal-and-modeless-dialog-boxes"></a>モーダルとモードレスのダイアログ ボックス

クラスを使用して[CDialog](../mfc/reference/cdialog-class.md)  ダイアログ ボックスの 2 つの種類を管理します。

- *モーダル ダイアログ ボックス*ユーザーがプログラムを続行する前に応答を必要とします。

- *モードレス ダイアログ ボックス*、常に画面とは、いつでも使用できるはその他のユーザー アクティビティを許可

リソースの編集と、ダイアログ テンプレートを作成する手順は、モーダルとモードレスのダイアログ ボックスのと同じです。

プログラムのダイアログ ボックスを作成するには、次の手順が必要です。

1. 使用して、[ダイアログ エディター](../windows/dialog-editor.md)  ダイアログ ボックスを設計すると、そのダイアログ テンプレート リソースを作成します。

1. ダイアログ クラスを作成します。

1. 接続、[メッセージ ハンドラーにコントロールをダイアログ リソースの](../windows/adding-event-handlers-for-dialog-box-controls.md)ダイアログ クラス。

1. 関連付けられているダイアログ ボックスのコントロールを指定するデータ メンバーを追加する[ダイアログ データ エクス チェンジ](../mfc/dialog-data-exchange.md)と[ダイアログ データ検証](../mfc/dialog-data-validation.md)コントロール。

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)
