---
title: ステータス バーの作成方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0428bfc906ba6e8a1ecc7bd7c198327e8c31505
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346930"
---
# <a name="methods-of-creating-a-status-bar"></a>ステータス バーの作成方法
MFC には、ステータス バーを作成する 2 つのクラスが用意されています: [CStatusBar](../mfc/reference/cstatusbar-class.md)と[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (をラップする Windows のコモン コントロール API)。 `CStatusBar` すべての機能を提供バー コモン コントロールの状態の自動的にメニューとツールバーと通信できません必要な共通コントロールの設定と構造の多くを処理。ただし、実行可能ファイル、通常はより大きくするを使用して作成`CStatusBarCtrl`です。  
  
 `CStatusBarCtrl` 通常、小規模な実行可能ファイルに結果が利用しやすい`CStatusBarCtrl`MFC アーキテクチャにステータス バーを統合する予定がない場合。 使用する場合`CStatusBarCtrl`MFC アーキテクチャにステータス バーを統合して、ステータス バーの mfc コントロールの操作を通信するために十分注意を行う必要があります。 この通信が困難です。ただしは、使用する場合、必要な追加の作業が`CStatusBar`です。  
  
 Visual C には、ステータス バーの一般的なコントロールを活用するために 2 つの方法が用意されています。  
  
-   ステータス バーを使用して作成`CStatusBar`、まず[CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl)へのアクセスを取得する、`CStatusBarCtrl`メンバー関数。  
  
-   ステータス バーを使用して作成[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)のコンス トラクターです。  
  
 どちらの方法でもにアクセスできます、ステータス バー コントロールのメンバー関数。 呼び出すと`CStatusBar::GetStatusBarCtrl`への参照を返します、`CStatusBarCtrl`オブジェクトのメンバー関数の両方のセットを使用できるようにします。 参照してください[CStatusBar](../mfc/reference/cstatusbar-class.md)を構築して、ステータス バーを使用しての作成について`CStatusBar`です。  
  
## <a name="see-also"></a>関連項目  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

