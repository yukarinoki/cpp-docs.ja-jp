---
description: 詳細については、「Thread-Specific ホットキー」を参照してください。
title: スレッド固有のホット キー
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: 352d39b801d7e6dcecfbf27d841d6977d3666138
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216120"
---
# <a name="thread-specific-hot-keys"></a>スレッド固有のホット キー

アプリケーションは、Windows の関数を使用して、スレッド固有のホットキー ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) を設定 `RegisterHotKey` します。 ユーザーがスレッド固有のホットキーを押すと、Windows によって [WM_HOTKEY](/windows/win32/inputdev/wm-hotkey) メッセージが特定のスレッドのメッセージキューの先頭にポストされます。 WM_HOTKEY メッセージには、押された特定のホットキーの仮想キーコード、シフト状態、およびユーザー定義の ID が含まれています。 標準の仮想キーコードの一覧については、「Winuser. h」を参照してください。 この方法の詳細については、「 [Registerhotkey キー](/windows/win32/api/winuser/nf-winuser-registerhotkey)」を参照してください。

の呼び出しで使用されている shift 状態フラグ `RegisterHotKey` は、 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) メンバー関数によって返されるフラグとは異なります。を呼び出す前に、これらのフラグを変換する必要があり `RegisterHotKey` ます。

## <a name="see-also"></a>関連項目

[CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
