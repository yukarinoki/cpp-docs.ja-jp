---
title: モードレス ダイアログ ボックスの作成
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 7a6125e84438b0ef2ad541c26bda33051d483c8d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619635"
---
# <a name="creating-modeless-dialog-boxes"></a>モードレス ダイアログ ボックスの作成

モードレスダイアログボックスの場合は、独自のパブリックコンストラクターをダイアログクラスに指定する必要があります。 モードレスダイアログボックスを作成するには、パブリックコンストラクターを呼び出し、ダイアログオブジェクトの[create](reference/cdialog-class.md#create) member 関数を呼び出してダイアログリソースを読み込みます。 **Create**は、コンストラクターの呼び出し中または後に呼び出すことができます。 ダイアログリソースにプロパティ**WS_VISIBLE**がある場合は、ダイアログボックスがすぐに表示されます。 それ以外の場合は、 [ShowWindow](reference/cwnd-class.md#showwindow)メンバー関数を呼び出す必要があります。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
