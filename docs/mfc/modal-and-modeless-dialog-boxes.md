---
title: モーダルとモードレスのダイアログ ボックス
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
ms.openlocfilehash: d3497a19ab14dcc9f14dc0419eb65ea033135b6e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508851"
---
# <a name="modal-and-modeless-dialog-boxes"></a>モーダルとモードレスのダイアログ ボックス

クラス [CDialog](reference/cdialog-class.md) を使用すると、次の2種類のダイアログボックスを管理できます。

- *モーダルダイアログボックス*。プログラムを続行する前にユーザーが応答する必要があります。

- *モードレスダイアログボックス*。画面上に表示され、いつでも使用できますが、他のユーザーアクティビティを許可します。

ダイアログテンプレートを作成するためのリソースの編集と手順は、モーダルおよびモードレスのダイアログボックスでも同じです。

プログラムのダイアログボックスを作成するには、次の手順を実行する必要があります。

1. ダイアログボックスをデザインし、ダイアログテンプレートリソースを作成するには、 [ダイアログエディター](../windows/dialog-editor.md) を使用します。

1. ダイアログクラスを作成します。

1. ダイアログクラスの [メッセージハンドラーにダイアログリソースのコントロールを](../windows/adding-editing-or-deleting-controls.md) 接続します。

1. ダイアログボックスのコントロールに関連付けられているデータメンバーを追加し、コントロールの [ダイアログデータエクスチェンジ](dialog-data-exchange.md) と [ダイアログデータ検証](dialog-data-validation.md) を指定します。

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
