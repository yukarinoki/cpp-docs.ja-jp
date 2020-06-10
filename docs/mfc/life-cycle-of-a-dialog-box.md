---
title: MFC でのダイアログ ボックスの操作
ms.date: 09/27/2019
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: d365be21ef19a6779df649e9368fdc0cda4851df
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621449"
---
# <a name="working-with-dialog-boxes-in-mfc"></a>MFC でのダイアログ ボックスの操作

ダイアログボックスのライフサイクル中に、ユーザーはダイアログボックスを起動します。通常は、ダイアログオブジェクトを作成して初期化するコマンドハンドラー内で、ユーザーがダイアログボックスを操作し、ダイアログボックスが閉じます。

モーダルダイアログボックスでは、ダイアログボックスを閉じると、ユーザーが入力したデータがハンドラーによって収集されます。 ダイアログオブジェクトはダイアログウィンドウが閉じられた後に存在するため、ダイアログクラスのメンバー変数を使用してデータを抽出できます。

モードレスダイアログボックスの場合、ダイアログボックスがまだ表示されている間に、ダイアログオブジェクトからデータを抽出することがよくあります。 ある時点で、ダイアログオブジェクトが破棄されます。このような状況が発生するのは、コードによって異なります。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ダイアログボックスの作成と表示](creating-and-displaying-dialog-boxes.md)

- [モーダルダイアログボックスの作成](creating-modal-dialog-boxes.md)

- [モードレス ダイアログ ボックスの作成](creating-modeless-dialog-boxes.md)

- [メモリ内のダイアログ テンプレートの使用](using-a-dialog-template-in-memory.md)

- [ダイアログボックスの背景色の設定](setting-the-dialog-boxs-background-color.md)

- [ダイアログボックスの初期化](initializing-the-dialog-box.md)

- [ダイアログボックスでの Windows メッセージの処理](handling-windows-messages-in-your-dialog-box.md)

- [ダイアログオブジェクトからのデータの取得](retrieving-data-from-the-dialog-object.md)

- [ダイアログボックスを閉じる](closing-the-dialog-box.md)

- [ダイアログボックスの破棄](destroying-the-dialog-box.md)

- [ダイアログデータエクスチェンジ (DDX) と検証 (DDV)](dialog-data-exchange-and-validation.md)

- [プロパティシートのダイアログボックス](property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)
