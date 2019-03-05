---
title: ダイアログ ボックスのクローズ
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 07e4159eccde1fab89d4a5ffadee4e6d11fc20f0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302580"
---
# <a name="closing-the-dialog-box"></a>ダイアログ ボックスのクローズ

ユーザーが [ok] ボタンまたは [キャンセル] ボタンでは通常、そのボタンのいずれかを選択すると、モーダル ダイアログ ボックスを閉じます。 Windows ダイアログ オブジェクトを送信する、[ok] または [キャンセル] ボタンを選択すると、 **BN_CLICKED**ボタンとコントロール通知メッセージの ID がか**IDOK**または**IDCANCEL**します。 `CDialog` これらのメッセージの既定のハンドラー関数を提供します。`OnOK`と`OnCancel`します。 既定のハンドラーの呼び出し、`EndDialog`メンバー関数は、ダイアログ ウィンドウを閉じます。 呼び出すこともできます`EndDialog`独自のコードから。 詳細については、次を参照してください。、 [EndDialog](../mfc/reference/cdialog-class.md#enddialog)クラスのメンバー関数`CDialog`で、 *MFC リファレンス*します。

終了およびモードレス ダイアログ ボックスを削除するための配置にオーバーライド`PostNcDestroy`を呼び出すと、**削除**演算子に対して、**この**ポインター。 [ダイアログ ボックスの破棄](../mfc/destroying-the-dialog-box.md)次の動作について説明します。

## <a name="see-also"></a>関連項目

[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)
