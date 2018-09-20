---
title: ダイアログ ボックスのライフ サイクル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05138040b6283b7af01f6e010bc371490aea495e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440499"
---
# <a name="life-cycle-of-a-dialog-box"></a>ダイアログ ボックスの有効期間

ダイアログ ボックスのライフ サイクルでは、ユーザーがダイアログ ボックスを呼び出す、通常コマンド ハンドラーを作成し、ダイアログのオブジェクトを初期化する内部ユーザー ダイアログ ボックスと通信、ダイアログ ボックスを閉じます。

モーダル ダイアログ ボックスの場合は、ハンドラーは、ユーザーの入力 ダイアログ ボックスを閉じるとデータを収集します。 ダイアログ ウィンドウが閉じられた後にダイアログ オブジェクトが存在するので、データを抽出するのに単にダイアログ クラスのメンバー変数を使用できます。

モードレス ダイアログ ボックスの可能性があります多くの場合、データを抽出するダイアログ オブジェクトから、ダイアログ ボックスがまだ表示されているときにします。 ある時点でダイアログ オブジェクトは破棄されます。この場合は、コードに依存します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [作成して、ダイアログ ボックスを表示します。](../mfc/creating-and-displaying-dialog-boxes.md)

- [モーダル ダイアログ ボックスの作成](../mfc/creating-modal-dialog-boxes.md)

- [モードレス ダイアログ ボックスの作成](../mfc/creating-modeless-dialog-boxes.md)

- [メモリ内のダイアログ テンプレートの使用](../mfc/using-a-dialog-template-in-memory.md)

- [ダイアログ ボックスの背景色の設定](../mfc/setting-the-dialog-boxs-background-color.md)

- [ダイアログ ボックスの初期化](../mfc/initializing-the-dialog-box.md)

- [ダイアログ ボックスでの Windows メッセージの処理](../mfc/handling-windows-messages-in-your-dialog-box.md)

- [ダイアログ オブジェクトからのデータの取得](../mfc/retrieving-data-from-the-dialog-object.md)

- [ダイアログ ボックスを閉じる](../mfc/closing-the-dialog-box.md)

- [ダイアログ ボックスの破棄](../mfc/destroying-the-dialog-box.md)

- [ダイアログ データ エクス (チェンジ DDX) と検証 (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [プロパティ シートのダイアログ ボックス](../mfc/property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)

