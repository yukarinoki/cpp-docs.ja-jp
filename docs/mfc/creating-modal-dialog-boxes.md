---
title: モーダル ダイアログ ボックスの作成
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: eb9aab7e8579fbbbfdf5d0f2dca9b6e6abea0066
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657342"
---
# <a name="creating-modal-dialog-boxes"></a>モーダル ダイアログ ボックスの作成

モーダル ダイアログ ボックスを作成するで宣言されている 2 つのパブリック コンス トラクターのいずれかを呼び出す[CDialog](../mfc/reference/cdialog-class.md)します。 次に、呼び出すダイアログ オブジェクトの[DoModal](../mfc/reference/cdialog-class.md#domodal) ダイアログ ボックスを表示し、ユーザーが [ok] を選択するまで対話操作を管理またはキャンセルするメンバー関数。 この管理によって`DoModal`はモーダル ダイアログ ボックスは、します。 モーダル ダイアログ ボックス、`DoModal`ダイアログ リソースを読み込みます。

## <a name="see-also"></a>関連項目

[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

