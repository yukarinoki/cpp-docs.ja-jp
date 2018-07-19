---
title: CStatusBarCtrl を使用して CStatusBarCtrl オブジェクトを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb378bba1505f8bbc3739c070d52abe9ef4f8afc
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953827"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>CStatusBarCtrl を使用して CStatusBarCtrl オブジェクトを作成する方法
一般的な使用例を次に示します[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):  
  
### <a name="to-use-a-status-bar-control-with-parts"></a>部分とステータス バー コントロールを使用するには  
  
1.  構築、`CStatusBarCtrl`オブジェクト。  
  
2.  呼び出す[SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight)ステータス バー コントロールの高さの最小値を設定する場合の領域を描画します。  
  
3.  呼び出す[SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor)ステータス バー コントロールの背景色を設定します。  
  
4.  呼び出す[呼び出した](../mfc/reference/cstatusbarctrl-class.md#setparts)をステータス バー コントロールと各部分の右端の座標で部分の数を設定します。  
  
5.  呼び出す[SetText](../mfc/reference/cstatusbarctrl-class.md#settext)ステータス バー コントロールの特定の部分でテキストを設定します。 メッセージには、テキストを表示する、新しいコントロールが WM_PAINT メッセージを次に受信され、変更されたコントロールの一部が無効になります。  
  
 場合によっては、ステータス バーのみする必要がある、行のテキストを表示します。 この場合、呼び出しを行う[SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple)です。 これは、ステータス バー コントロールは、「単純」モードは、1 行のテキストを表示になります。  
  
## <a name="see-also"></a>関連項目  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

