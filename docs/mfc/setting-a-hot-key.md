---
title: ホット キーの設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3987ddee98ae35e02a181e38cd71f181801aeb61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379646"
---
# <a name="setting-a-hot-key"></a>ホット キーの設定
アプリケーションは、ホット キーによって提供される情報を使用して ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) 2 つの方法のいずれかで制御します。  
  
-   送信することによって、子ウィンドウ以外のウィンドウをアクティブ化するためのグローバル ホット キーを設定、 [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284)メッセージをウィンドウをアクティブ化します。  
  
-   Windows の関数を呼び出すことによって、スレッド固有のホット キーを設定[RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309)です。  
  
## <a name="see-also"></a>関連項目  
 [CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

