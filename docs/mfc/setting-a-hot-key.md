---
description: '詳細情報: ホットキーの設定'
title: ホット キーの設定
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: fa713be2d478eb18b11dca27558656e5e6993076
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217186"
---
# <a name="setting-a-hot-key"></a>ホット キーの設定

アプリケーションでは、次の2つの方法のいずれかでホットキー ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) コントロールによって提供される情報を使用できます。

- 非子ウィンドウをアクティブ化するためのグローバルホットキーを設定するには、アクティブ化するウィンドウに [WM_SETHOTKEY](/windows/win32/inputdev/wm-sethotkey) メッセージを送信します。

- Windows の関数 [registerhotkey](/windows/win32/api/winuser/nf-winuser-registerhotkey)キーを呼び出して、スレッド固有のホットキーを設定します。

## <a name="see-also"></a>関連項目

[CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
