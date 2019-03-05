---
title: モーダル ダイアログ ボックスの作成
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: 5de6eeb616f32c7b8829d827988a972e41658530
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304965"
---
# <a name="creating-modal-dialog-boxes"></a>モーダル ダイアログ ボックスの作成

モーダル ダイアログ ボックスを作成するで宣言されている 2 つのパブリック コンス トラクターのいずれかを呼び出す[CDialog](../mfc/reference/cdialog-class.md)します。 次に、呼び出すダイアログ オブジェクトの[DoModal](../mfc/reference/cdialog-class.md#domodal) ダイアログ ボックスを表示し、ユーザーが [ok] を選択するまで対話操作を管理またはキャンセルするメンバー関数。 この管理によって`DoModal`はモーダル ダイアログ ボックスは、します。 モーダル ダイアログ ボックス、`DoModal`ダイアログ リソースを読み込みます。

## <a name="see-also"></a>関連項目

[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)
