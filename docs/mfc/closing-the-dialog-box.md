---
description: 詳細については、「ダイアログボックスを閉じる」を参照してください。
title: ダイアログ ボックスのクローズ
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 4e60bdfb1ecb6968996d6c657f0c667ad2686a56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338372"
---
# <a name="closing-the-dialog-box"></a>ダイアログ ボックスのクローズ

ユーザーがボタンのいずれかを選択すると、モーダルダイアログボックスが閉じます。通常は、[OK] ボタンまたは [キャンセル] ボタンです。 [OK] または [キャンセル] をクリックすると、Windows によって、ダイアログオブジェクトに、ボタンの ID ( **IDOK** または **IDCANCEL**) を含む **BN_CLICKED** コントロール通知メッセージが送信されます。 `CDialog` これらのメッセージの既定のハンドラー関数 (および) を提供し `OnOK` `OnCancel` ます。 既定のハンドラーは、このメンバー関数を呼び出して `EndDialog` ダイアログウィンドウを閉じます。 独自のコードからを呼び出すこともでき `EndDialog` ます。 詳細については、 [](reference/cdialog-class.md#enddialog) `CDialog` *MFC リファレンス* の「クラスの EndDialog メンバー関数」を参照してください。

モードレスダイアログボックスの終了と削除を配置するには、 `PostNcDestroy` ポインターに対して演算子をオーバーライドして呼び出し **`delete`** **`this`** ます。 [ダイアログボックスを破棄すると、](destroying-the-dialog-box.md) 次の処理が説明されます。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
