---
description: '詳細情報: グローバルホットキー'
title: グローバル ホット キー
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
ms.openlocfilehash: 3d481c637ec20ed7b9ec3f45a916bd39470ffb5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189276"
---
# <a name="global-hot-keys"></a>グローバル ホット キー

グローバルホットキーは、特定の子以外のウィンドウに関連付けられています。 これにより、ユーザーはシステムの任意の部分からウィンドウをアクティブ化できるようになります。 アプリケーションでは、そのウィンドウに [WM_SETHOTKEY](/windows/win32/inputdev/wm-sethotkey) メッセージを送信することによって、特定のウィンドウのグローバルホットキーを設定します。 たとえば、 `m_HotKeyCtrl` が [CHotKeyCtrl](reference/chotkeyctrl-class.md) オブジェクトで、 `pMainWnd` ホットキーが押されたときにアクティブになるウィンドウへのポインターである場合、次のコードを使用して、コントロールで指定されたホットキーを、が指すウィンドウに関連付けることができ `pMainWnd` ます。

[!code-cpp[NVC_MFCControlLadenDialog#18](codesnippet/cpp/global-hot-keys_1.cpp)]

ユーザーがグローバルホットキーを押すたびに、指定されたウィンドウは、コマンドの種類として **SC_HOTKEY** を指定する [WM_SYSCOMMAND](/windows/win32/menurc/wm-syscommand)メッセージを受信します。 このメッセージは、それを受信するウィンドウもアクティブにします。 このメッセージには、押されたキーに関する情報は含まれていないため、この方法を使用すると、同じウィンドウに接続されている可能性のある異なるホットキーを区別できません。 ホットキーは、 **WM_SETHOTKEY** 送信されたアプリケーションが終了するまで有効なままです。

## <a name="see-also"></a>関連項目

[CHotKeyCtrl の使い方](using-chotkeyctrl.md)<br/>
[コントロール](controls-mfc.md)
