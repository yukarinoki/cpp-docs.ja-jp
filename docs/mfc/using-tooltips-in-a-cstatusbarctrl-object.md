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
ms.openlocfilehash: 323f2861da9fcc498e34792c30c763b4dffb2fd1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトでのツール ヒントの使い方
ステータス バー コントロールにツールヒントを有効にするには、作成、`CStatusBarCtrl`オブジェクトを**には**スタイル。  
  
> [!NOTE]
>  使用している場合、`CStatusBar`を使用して、ステータス バーを実装するオブジェクト、`CStatusBar::CreateEx`関数。 埋め込みの追加のスタイルを指定することができます**CStatusBarCtrl**オブジェクト。  
  
 1 回、`CStatusBarCtrl`オブジェクトが正常に作成されるを使用して[CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext)と[CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext)設定と特定のウィンドウに関するツールヒントのテキストを取得します。  
  
 ツール ヒントを設定すると、パーツ内のすべてのテキストを表示できない場合または部分がある、アイコンとテキストがない場合にのみ表示されます。 ツール ヒントは簡易モードではサポートされていません。  
  
## <a name="see-also"></a>関連項目  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

