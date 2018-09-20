---
title: ダイアログ ボックスを閉じる |Microsoft Docs
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
ms.openlocfilehash: e9ad4b8af63b68912c232767bf1fd14070fda261
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409052"
---
# <a name="closing-the-dialog-box"></a>ダイアログ ボックスのクローズ

ユーザーが [ok] ボタンまたは [キャンセル] ボタンでは通常、そのボタンのいずれかを選択すると、モーダル ダイアログ ボックスを閉じます。 Windows ダイアログ オブジェクトを送信する、[ok] または [キャンセル] ボタンを選択すると、 **BN_CLICKED**ボタンとコントロール通知メッセージの ID がか**IDOK**または**IDCANCEL**します。 `CDialog` これらのメッセージの既定のハンドラー関数を提供します。`OnOK`と`OnCancel`します。 既定のハンドラーの呼び出し、`EndDialog`メンバー関数は、ダイアログ ウィンドウを閉じます。 呼び出すこともできます`EndDialog`独自のコードから。 詳細については、次を参照してください。、 [EndDialog](../mfc/reference/cdialog-class.md#enddialog)クラスのメンバー関数`CDialog`で、 *MFC リファレンス*します。

終了およびモードレス ダイアログ ボックスを削除するための配置にオーバーライド`PostNcDestroy`を呼び出すと、**削除**演算子に対して、**この**ポインター。 [ダイアログ ボックスの破棄](../mfc/destroying-the-dialog-box.md)次の動作について説明します。

## <a name="see-also"></a>関連項目

[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

