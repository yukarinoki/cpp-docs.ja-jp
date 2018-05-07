---
title: CReBar vs です。CReBarCtrl |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CReBar
- CReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6d0b8df40676cc64c97a6bdef013321c404899f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="crebar-vs-crebarctrl"></a>CReBar vs です。CReBarCtrl
MFC には、rebars を作成する 2 つのクラスが用意されています: [CReBar](../mfc/reference/crebar-class.md)と[CReBarCtrl](../mfc/reference/crebarctrl-class.md) (をラップする Windows のコモン コントロール API)。 **CReBar**のすべての共通の rebar コントロールの機能を提供するため、必要な共通コントロールの設定と構造の多くを処理します。  
  
 `CReBarCtrl` Win32 rebar コントロールのラッパー クラスは、そのため、MFC アーキテクチャに rebar を統合する予定がない場合は、実装に簡単にあります。 使用する場合`CReBarCtrl`MFC アーキテクチャに rebar を統合して、MFC に rebar コントロールの操作を通信するために十分注意を行う必要があります。 この通信が困難です。ただしは、使用する場合、必要な追加の作業が**CReBar**です。  
  
 Visual C には、rebar のコモン コントロールを活用するために 2 つの方法が用意されています。  
  
-   使用して、rebar の作成**CReBar**、まず[CReBar::GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl)へのアクセスを取得する、`CReBarCtrl`メンバー関数。  
  
    > [!NOTE]
    >  `CReBar::GetReBarCtrl` キャストするインライン メンバー関数は、**この**rebar オブジェクトのポインター。 つまり、実行時に、関数呼び出しのオーバーヘッドが発生しません。  
  
-   使用して、rebar の作成[CReBarCtrl](../mfc/reference/crebarctrl-class.md)のコンス トラクターです。  
  
 いずれかの方法 rebar コントロールのメンバー関数にアクセスは許可されます。 呼び出すと`CReBar::GetReBarCtrl`への参照を返します、`CReBarCtrl`オブジェクトのメンバー関数の両方のセットを使用できるようにします。 参照してください[CReBar](../mfc/reference/crebar-class.md)を構築してを使用して、rebar の作成について**CReBar**です。  
  
## <a name="see-also"></a>関連項目  
 [CReBarCtrl の使い方](../mfc/using-crebarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

