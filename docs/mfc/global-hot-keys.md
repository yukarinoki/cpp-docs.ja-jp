---
title: グローバル ホット キー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d749fad0fabf8ae99bba129caee399e3f93ff9af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443853"
---
# <a name="global-hot-keys"></a>グローバル ホット キー

グローバル ホット キーは、特定の子ウィンドウ以外のウィンドウに関連付けられます。 ユーザー、システムの任意の部分からウィンドウをアクティブにできます。 アプリケーションが送信することによって特定のウィンドウのグローバル ホット キーを設定、 [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey)そのウィンドウにメッセージ。 たとえば場合、`m_HotKeyCtrl`は、 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)オブジェクトと`pMainWnd`ポインターは、ホット キーが押されたときにアクティブ化するウィンドウを使用して、コントロール内に指定されたホット キーを関連付ける次のコードを使用できますによって示されるウィンドウ`pMainWnd`します。

[!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]

グローバル ホット キーを押すたびに指定されたウィンドウを受け取る、 [WM_SYSCOMMAND](/windows/desktop/menurc/wm-syscommand)を指定するメッセージ**SC_HOTKEY**コマンドの種類として。 また、このメッセージには、受信するウィンドウがアクティブにします。 このメッセージには、押されたキーと完全に一致に関する情報が含まれていないためこのメソッドを使用してにより同じウィンドウに接続されている別のホット キーを識別します。 送信したアプリケーションまで、ホット キーが有効な**WM_SETHOTKEY**が終了します。

## <a name="see-also"></a>関連項目

[CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

