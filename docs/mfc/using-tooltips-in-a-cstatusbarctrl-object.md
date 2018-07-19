---
title: CStatusBarCtrl オブジェクトでツールヒントを使用して |Microsoft ドキュメント
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
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9cce98e4a3b3ffd506607529b9fea6f0c1114cc3
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951269"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトでのツール ヒントの使い方
ステータス バー コントロールにツールヒントを有効にするには、作成、`CStatusBarCtrl`には、スタイルを持つオブジェクト。  
  
> [!NOTE]
>  使用している場合、`CStatusBar`を使用して、ステータス バーを実装するオブジェクト、`CStatusBar::CreateEx`関数。 埋め込みの追加のスタイルを指定することができます`CStatusBarCtrl`オブジェクト。  
  
 1 回、`CStatusBarCtrl`オブジェクトが正常に作成されるを使用して[CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext)と[CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext)設定と特定のウィンドウに関するツールヒントのテキストを取得します。  
  
 ツール ヒントを設定すると、パーツ内のすべてのテキストを表示できない場合または部分がある、アイコンとテキストがない場合にのみ表示されます。 ツール ヒントは簡易モードではサポートされていません。  
  
## <a name="see-also"></a>関連項目  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

