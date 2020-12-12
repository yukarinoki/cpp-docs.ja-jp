---
description: '詳細情報: モーダルダイアログボックスの作成'
title: モーダル ダイアログ ボックスの作成
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: 82fa10c65161df98ea3d377e302c0fb787feb14c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309798"
---
# <a name="creating-modal-dialog-boxes"></a>モーダル ダイアログ ボックスの作成

モーダルダイアログボックスを作成するには、 [CDialog](reference/cdialog-class.md)で宣言されている2つのパブリックコンストラクターのいずれかを呼び出します。 次に、ダイアログオブジェクトの [DoModal](reference/cdialog-class.md#domodal) メンバー関数を呼び出してダイアログボックスを表示し、ユーザーが [OK] または [キャンセル] を選択するまで、ダイアログボックスとの対話を管理します。 この管理によって `DoModal` 、ダイアログボックスがモーダルになります。 モーダルダイアログボックスの場合は、 `DoModal` ダイアログリソースを読み込みます。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
