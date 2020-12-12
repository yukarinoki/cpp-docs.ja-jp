---
description: 詳細については、「ダイアログボックスの破棄」を参照してください。
title: ダイアログ ボックスの破棄
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
ms.openlocfilehash: f46c86e5f3e869f321b8306470e5821658ceafcb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327847"
---
# <a name="destroying-the-dialog-box"></a>ダイアログ ボックスの破棄

モーダルダイアログボックスは通常、スタックフレーム上に作成され、それを作成した関数が終了すると破棄されます。 ダイアログオブジェクトのデストラクターは、オブジェクトがスコープ外に出ると呼び出されます。

モードレスダイアログボックスは通常、親ビューまたはフレームウィンドウ (アプリケーションのメインフレームウィンドウまたはドキュメントフレームウィンドウ) によって作成および所有されます。 既定の [OnClose](reference/cwnd-class.md#onclose) ハンドラーは [DestroyWindow](reference/cwnd-class.md#destroywindow)を呼び出します。これにより、ダイアログボックスウィンドウが破棄されます。 ダイアログボックスが単独で表示される場合、またはその他の特別な所有権のセマンティクスにポインターがない場合は、 [PostNcDestroy](reference/cwnd-class.md#postncdestroy) をオーバーライドして C++ ダイアログオブジェクトを破棄する必要があります。 また、 [OnCancel](reference/cdialog-class.md#oncancel) をオーバーライドし、 `DestroyWindow` その中からを呼び出す必要があります。 そうでない場合、ダイアログボックスの所有者は、不要になったときに C++ オブジェクトを破棄する必要があります。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
