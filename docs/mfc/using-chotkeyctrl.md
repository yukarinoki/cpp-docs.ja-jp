---
description: 詳細については、CHotKeyCtrl の使用に関するページをご覧ください。
title: CHotKeyCtrl の使い方
ms.date: 11/04/2016
helpviewer_keywords:
- keys, hot and CHotKeyCtrl
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
ms.openlocfilehash: 7f17063a4fb3732a9b121e2b93f5d55e51d5654a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271682"
---
# <a name="using-chotkeyctrl"></a>CHotKeyCtrl の使い方

[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)クラスによって表されるホットキーコントロールは、CTRL + SHIFT + Q など、ユーザーが入力したキーの組み合わせのテキスト表現を表示するウィンドウです。 また、このキーの内部表現は、仮想キーコードの形式と、シフト状態を表すフラグのセットでも保持されます。 ホットキーコントロールは、実際にはホットキーを設定しません。これはプログラムによって行われます。 (標準の仮想キーコードの一覧については、「Winuser. h」を参照してください)。

ホットキーコントロールを使用して、ウィンドウまたはスレッドに関連付けるホットキーに対するユーザーの入力を取得します。 ホットキーコントロールは、ユーザーにホットキーの割り当てを要求したときに表示されるなど、ダイアログボックスでよく使用されます。 ホットキーコントロールからホットキーを記述した値を取得し、適切な関数を呼び出してホットキーをウィンドウまたはスレッドに関連付けるのは、プログラムの役割です。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ホットキーコントロールの使用](../mfc/using-a-hot-key-control.md)

- [ホットキーの設定](../mfc/setting-a-hot-key.md)

- [グローバルホットキー](../mfc/global-hot-keys.md)

- [スレッド固有のホットキー](../mfc/thread-specific-hot-keys.md)

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)
