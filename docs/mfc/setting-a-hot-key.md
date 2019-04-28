---
title: ホット キーの設定
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: a77aad4881acd04c6dabb6dce90acc01be2cfbc8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307784"
---
# <a name="setting-a-hot-key"></a>ホット キーの設定

アプリケーションは、ホット キーによって提供される情報を使用できます ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) 2 つの方法のいずれかで制御します。

- 送信することによって、子ウィンドウ以外のウィンドウをアクティブ化するためのグローバル ホット キーを設定、 [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey)メッセージ ウィンドウをアクティブ化します。

- Windows 関数を呼び出すことによって、スレッド固有のホット キーを設定[RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey)します。

## <a name="see-also"></a>関連項目

[CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
