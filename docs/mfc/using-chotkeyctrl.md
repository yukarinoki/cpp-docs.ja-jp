---
title: CHotKeyCtrl の使い方
ms.date: 11/04/2016
helpviewer_keywords:
- keys, hot and CHotKeyCtrl
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
ms.openlocfilehash: e2002d96a1eba913e260fa92281f730355a83ca5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447244"
---
# <a name="using-chotkeyctrl"></a>CHotKeyCtrl の使い方

[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)クラスによって表されるホットキーコントロールは、CTRL + SHIFT + Q など、ユーザーが入力したキーの組み合わせのテキスト表現を表示するウィンドウです。 また、このキーの内部表現は、仮想キーコードの形式と、シフト状態を表すフラグのセットでも保持されます。 ホットキーコントロールは、実際にはホットキーを設定しません。これはプログラムによって行われます。 (標準の仮想キーコードの一覧については、「Winuser. h」を参照してください)。

ホットキーコントロールを使用して、ウィンドウまたはスレッドに関連付けるホットキーに対するユーザーの入力を取得します。 ホットキーコントロールは、ユーザーにホットキーの割り当てを要求したときに表示されるなど、ダイアログボックスでよく使用されます。 ホットキーコントロールからホットキーを記述した値を取得し、適切な関数を呼び出してホットキーをウィンドウまたはスレッドに関連付けるのは、プログラムの役割です。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ホット キー コントロールの使い方](../mfc/using-a-hot-key-control.md)

- [ホット キーの設定](../mfc/setting-a-hot-key.md)

- [グローバル ホット キー](../mfc/global-hot-keys.md)

- [スレッド固有のホット キー](../mfc/thread-specific-hot-keys.md)

## <a name="see-also"></a>参照

[コントロール](../mfc/controls-mfc.md)
