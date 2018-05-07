---
title: ダイアログ ボックスのライフ サイクル |Microsoft ドキュメント
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
ms.openlocfilehash: faf204f05c03e742e0f491fb3991b56d3405ebc4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="life-cycle-of-a-dialog-box"></a>ダイアログ ボックスの有効期間
ライフ サイクルは、ダイアログ ボックスの中に、ユーザーがダイアログ ボックスを呼び出します、通常コマンド ハンドラーを作成し、ダイアログ オブジェクトを初期化する、内部ユーザーと通信します ダイアログ ボックス、ダイアログ ボックスを閉じます。  
  
 モーダル ダイアログ ボックス、ハンドラーはユーザーが入力した後、ダイアログ ボックスが閉じ、データを収集します。 ダイアログ ウィンドウが閉じられた後にダイアログ オブジェクトが存在するので、データを抽出するのにだけで、ダイアログ クラスのメンバー変数を使用できます。  
  
 モードレス ダイアログ ボックスの可能性があります多くの場合、データを抽出するダイアログ オブジェクトからダイアログ ボックスがまだ表示されています。 ある時点で、ダイアログ オブジェクトは破棄されます。この場合は、コードによって異なります。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [作成して、ダイアログ ボックスを表示します。](../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [モーダル ダイアログ ボックスの作成](../mfc/creating-modal-dialog-boxes.md)  
  
-   [モードレス ダイアログ ボックスの作成](../mfc/creating-modeless-dialog-boxes.md)  
  
-   [メモリ内でダイアログ テンプレートの使用](../mfc/using-a-dialog-template-in-memory.md)  
  
-   [ダイアログ ボックスの背景色の設定](../mfc/setting-the-dialog-boxs-background-color.md)  
  
-   [ダイアログ ボックスの初期化](../mfc/initializing-the-dialog-box.md)  
  
-   [ダイアログ ボックスで Windows メッセージの処理](../mfc/handling-windows-messages-in-your-dialog-box.md)  
  
-   [ダイアログ オブジェクトからのデータの取得](../mfc/retrieving-data-from-the-dialog-object.md)  
  
-   [ダイアログ ボックスを閉じる](../mfc/closing-the-dialog-box.md)  
  
-   [ダイアログ ボックスの破棄](../mfc/destroying-the-dialog-box.md)  
  
-   [ダイアログ データ エクス (チェンジ DDX) および検証 (DDV)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [プロパティ シート ダイアログ ボックス](../mfc/property-sheets-and-property-pages-mfc.md)  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)

