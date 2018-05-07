---
title: グローバル ホット キー |Microsoft ドキュメント
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
ms.openlocfilehash: cd597271d949770ec1a5871cad3ea7be0004e288
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="global-hot-keys"></a>グローバル ホット キー
グローバル ホット キーは、特定の子ウィンドウ以外のウィンドウに関連付けられます。 ユーザーは、システムの任意の部分からウィンドウをアクティブにできます。 アプリケーションが送信することによって特定のウィンドウでグローバル ホット キーを設定、 [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284)そのウィンドウにメッセージ。 たとえば場合、`m_HotKeyCtrl`は、 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)オブジェクトおよび`pMainWnd`へのポインターは、ホット キーが押されたときにアクティブ化されるウィンドウにあるコントロールに指定されたホット キーを関連付けるには、次のコードを使用する可能性がありますウィンドウを指す`pMainWnd`です。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]  
  
 グローバル ホット キーを押したときに指定されたウィンドウを受け取る、 [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360)を示すメッセージ**SC_HOTKEY**コマンドの種類として。 また、このメッセージを受け取ったウィンドウがアクティブにします。 このメッセージには、押されたキーに関する正しい情報が含まれていないためこのメソッドを使用することはできません、同じウィンドウに接続されている異なるホット キーの違い。 送信元アプリケーションまで、ホット キーは有効**WM_SETHOTKEY**が終了します。  
  
## <a name="see-also"></a>関連項目  
 [CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

