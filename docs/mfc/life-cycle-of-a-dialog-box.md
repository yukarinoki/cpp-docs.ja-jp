---
description: 詳細については、「MFC でのダイアログボックスの操作」を参照してください。
title: MFC でのダイアログ ボックスの操作
ms.date: 09/27/2019
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: 5e88d34ab26f8abd24923aacafa02c3c62ec7f06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327788"
---
# <a name="working-with-dialog-boxes-in-mfc"></a>MFC でのダイアログ ボックスの操作

ダイアログボックスのライフサイクル中に、ユーザーはダイアログボックスを起動します。通常は、ダイアログオブジェクトを作成して初期化するコマンドハンドラー内で、ユーザーがダイアログボックスを操作し、ダイアログボックスが閉じます。

モーダルダイアログボックスでは、ダイアログボックスを閉じると、ユーザーが入力したデータがハンドラーによって収集されます。 ダイアログオブジェクトはダイアログウィンドウが閉じられた後に存在するため、ダイアログクラスのメンバー変数を使用してデータを抽出できます。

モードレスダイアログボックスの場合、ダイアログボックスがまだ表示されている間に、ダイアログオブジェクトからデータを抽出することがよくあります。 ある時点で、ダイアログオブジェクトが破棄されます。このような状況が発生するのは、コードによって異なります。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ダイアログ ボックスの作成と表示](creating-and-displaying-dialog-boxes.md)

- [モーダル ダイアログ ボックスの作成](creating-modal-dialog-boxes.md)

- [モードレス ダイアログ ボックスの作成](creating-modeless-dialog-boxes.md)

- [メモリ内のダイアログ テンプレートの使用](using-a-dialog-template-in-memory.md)

- [ダイアログボックスの背景色の設定](setting-the-dialog-boxs-background-color.md)

- [ダイアログ ボックスの初期化](initializing-the-dialog-box.md)

- [ダイアログ ボックスでの Windows メッセージの処理](handling-windows-messages-in-your-dialog-box.md)

- [ダイアログ オブジェクトからのデータの取得](retrieving-data-from-the-dialog-object.md)

- [ダイアログ ボックスのクローズ](closing-the-dialog-box.md)

- [ダイアログ ボックスの破棄](destroying-the-dialog-box.md)

- [ダイアログデータエクスチェンジ (DDX) と検証 (DDV)](dialog-data-exchange-and-validation.md)

- [プロパティシートのダイアログボックス](property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)
