---
title: ダイアログ ボックスのクローズ
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 48ea954552b3ea9aa7193a47fc2a66d731312d77
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685381"
---
# <a name="closing-the-dialog-box"></a>ダイアログ ボックスのクローズ

ユーザーがボタンのいずれかを選択すると、モーダルダイアログボックスが閉じます。通常は、[OK] ボタンまたは [キャンセル] ボタンです。 [OK] または [キャンセル] をクリックすると、Windows によってダイアログオブジェクトに、ボタンの ID ( **IDOK**または**IDCANCEL**) を持つ**BN_CLICKED**コントロール通知メッセージが送信されます。 `CDialog` は、これらのメッセージの既定のハンドラー関数を提供します。 `OnOK` と `OnCancel` です。 既定のハンドラーは、`EndDialog` メンバー関数を呼び出してダイアログウィンドウを閉じます。 また、独自のコードから `EndDialog` を呼び出すこともできます。 詳細については、 *MFC リファレンス*のクラス `CDialog` の[EndDialog](../mfc/reference/cdialog-class.md#enddialog)メンバー関数を参照してください。

モードレスダイアログボックスの終了と削除を配置するには、@no__t 0 をオーバーライドし、**この**ポインターに対して**delete**演算子を呼び出します。 [ダイアログボックスを破棄すると、](../mfc/destroying-the-dialog-box.md)次の処理が説明されます。

## <a name="see-also"></a>関連項目

[MFC でのダイアログボックスの操作](../mfc/life-cycle-of-a-dialog-box.md)
