---
title: Chotkeyctrl の使い方 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CHotKeyCtrl
dev_langs:
- C++
helpviewer_keywords:
- keys, hot and CHotKeyCtrl
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd966b74590d0e7641f2f789b5c45f901a3cf8c8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421506"
---
# <a name="using-chotkeyctrl"></a>CHotKeyCtrl の使い方

クラスによって表される、ホット キー コントロール[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)は、ユーザーが CTRL + SHIFT + Q など、型、キーの組み合わせのテキスト表現を表示するウィンドウです。 このキーのシフト状態を表すフラグのセットおよび仮想キー コードの形式での内部表現も保持されます。 ホット キー コントロールがホット キーを実際には設定しません-これまで、プログラムはします。 (標準の仮想キー コードの一覧は、Winuser.h を参照してください)。

ホット キー コントロールを使用すると、ウィンドウまたはスレッドに関連付けるホット キーのユーザーの入力を取得できます。 ホット キー コントロールは、ホット キーを割り当てるユーザーを要求するときに表示することもなどのダイアログ ボックスでよく使用されます。 ホット キー コントロールのホット キーを記述する値を取得するウィンドウまたはスレッドにホット キーを関連付ける適切な関数を呼び出すと、プログラムの役目です。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [ホット キー コントロールの使い方](../mfc/using-a-hot-key-control.md)

- [ホット キーの設定](../mfc/setting-a-hot-key.md)

- [グローバル ホット キー](../mfc/global-hot-keys.md)

- [スレッド固有のホット キー](../mfc/thread-specific-hot-keys.md)

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)

