---
title: ホット キーの設定 |Microsoft Docs
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
ms.openlocfilehash: 254d7532b83a4f30c0029b2488bb0b2111cce31d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219398"
---
# <a name="setting-a-hot-key"></a>ホット キーの設定
アプリケーションは、ホット キーによって提供される情報を使用できます ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) 2 つの方法のいずれかで制御します。  
  
-   送信することによって、子ウィンドウ以外のウィンドウをアクティブ化するためのグローバル ホット キーを設定、 [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey)メッセージ ウィンドウをアクティブ化します。  
  
-   Windows 関数を呼び出すことによって、スレッド固有のホット キーを設定[RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309)します。  
  
## <a name="see-also"></a>関連項目  
 [Chotkeyctrl の使い方](../mfc/using-chotkeyctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

