---
title: スレッド固有のホット キー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f480b293e9c57e7fa189c6427ab39147681cfdaf
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206861"
---
# <a name="thread-specific-hot-keys"></a>スレッド固有のホット キー
アプリケーション スレッドに固有のホット キーの設定 ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md))、Windows を使用して`RegisterHotKey`関数。 ユーザーは、スレッド固有のホット キーを押すと、Windows の投稿、 [WM_HOTKEY](/windows/desktop/inputdev/wm-hotkey)メッセージを特定のスレッドのメッセージ キューの先頭にします。 WM_HOTKEY メッセージには、仮想キー コード、シフト状態および押されたホット キーの特定のユーザー定義の ID が含まれています。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。 このメソッドの詳細については、次を参照してください。 [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309)します。  
  
 フラグのシフト状態への呼び出しで使用される注`RegisterHotKey`がによって返されるものと同じでない、 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey)メンバー関数の呼び出しの前にこれらのフラグを変換する必要があります`RegisterHotKey`します。  
  
## <a name="see-also"></a>関連項目  
 [Chotkeyctrl の使い方](../mfc/using-chotkeyctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

