---
title: モーダル ダイアログ ボックスの作成
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: ed7cc94982a46e542a5174d4d46b8013cc84ffa4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622982"
---
# <a name="creating-modal-dialog-boxes"></a>モーダル ダイアログ ボックスの作成

モーダルダイアログボックスを作成するには、 [CDialog](reference/cdialog-class.md)で宣言されている2つのパブリックコンストラクターのいずれかを呼び出します。 次に、ダイアログオブジェクトの[DoModal](reference/cdialog-class.md#domodal)メンバー関数を呼び出してダイアログボックスを表示し、ユーザーが [OK] または [キャンセル] を選択するまで、ダイアログボックスとの対話を管理します。 この管理によって `DoModal` 、ダイアログボックスがモーダルになります。 モーダルダイアログボックスの場合は、 `DoModal` ダイアログリソースを読み込みます。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
