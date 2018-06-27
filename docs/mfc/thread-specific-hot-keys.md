---
title: スレッド固有のホット キー |Microsoft ドキュメント
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
ms.openlocfilehash: 14da7f0e5b0adbe72b6705700c1e9298751bc345
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953610"
---
# <a name="thread-specific-hot-keys"></a>スレッド固有のホット キー
アプリケーションのスレッドに固有のホット キーの設定 ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md))、Windows を使用して`RegisterHotKey`関数。 ユーザーは、スレッド固有のホット キーを押すと、Windows の投稿、 [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279)特定のスレッドのメッセージ キューの先頭へのメッセージ。 WM_HOTKEY メッセージには、仮想キー コード、シフト状態と押されたホット キーの特定のユーザー定義の ID が含まれています。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。 このメソッドの詳細については、次を参照してください。 [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309)です。  
  
 呼び出しで使用されるシフト状態フラグ注`RegisterHotKey`によって返されるものと同じではない、 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey)メンバー関数呼び出しの前にこれらのフラグを変換する必要があります`RegisterHotKey`です。  
  
## <a name="see-also"></a>関連項目  
 [CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

