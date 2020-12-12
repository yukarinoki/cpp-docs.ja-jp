---
description: '詳細情報: モードレスダイアログボックスの作成'
title: モードレス ダイアログ ボックスの作成
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: c754391a0f1ab2713f3ce01b5d30ccc33be4aaa5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309785"
---
# <a name="creating-modeless-dialog-boxes"></a>モードレス ダイアログ ボックスの作成

モードレスダイアログボックスの場合は、独自のパブリックコンストラクターをダイアログクラスに指定する必要があります。 モードレスダイアログボックスを作成するには、パブリックコンストラクターを呼び出し、ダイアログオブジェクトの [create](reference/cdialog-class.md#create) member 関数を呼び出してダイアログリソースを読み込みます。 **Create** は、コンストラクターの呼び出し中または後に呼び出すことができます。 ダイアログリソースにプロパティ **WS_VISIBLE** がある場合は、ダイアログボックスがすぐに表示されます。 それ以外の場合は、 [ShowWindow](reference/cwnd-class.md#showwindow) メンバー関数を呼び出す必要があります。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
