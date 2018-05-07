---
title: ダイアログ ボックスを閉じる |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c800c204fd09057585064397d459f92c9ded272d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="closing-the-dialog-box"></a>ダイアログ ボックスのクローズ
[Ok] ボタンまたは [キャンセル] ボタンでは通常、そのボタンのいずれかを選択すると、モーダル ダイアログ ボックスを閉じます。 Windows ダイアログ オブジェクトを送信する、[ok] または [キャンセル] ボタンを選択すると、 **BN_CLICKED**をボタンとコントロール通知メッセージをするか、ID の**IDOK**または**IDCANCEL**です。 `CDialog` これらのメッセージに対する既定のハンドラー関数を提供します。`OnOK`と`OnCancel`です。 既定のハンドラーの呼び出し、`EndDialog`ダイアログ ウィンドウを閉じます。 呼び出すこともできます`EndDialog`独自のコードからです。 詳細については、次を参照してください。、 [EndDialog](../mfc/reference/cdialog-class.md#enddialog)クラスのメンバー関数`CDialog`で、 *『 MFC リファレンス*です。  
  
 閉じると、モードレス ダイアログ ボックスを削除すると、並べ替えるオーバーライド`PostNcDestroy`を呼び出すと、**削除**演算子で、**この**ポインター。 [ダイアログ ボックスの破棄](../mfc/destroying-the-dialog-box.md)次の動作について説明します。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

