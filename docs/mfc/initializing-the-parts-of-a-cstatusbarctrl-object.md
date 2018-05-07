---
title: CStatusBarCtrl オブジェクトの区画の初期化 |Microsoft ドキュメント
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
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89cea1516924530f821003affd96e2848687882b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトの区画の初期化
既定では、ステータス バーには、個別のペインを使用してステータス情報が表示されます。 これらのペイン (パーツとも呼ばれます) には、文字列、アイコン、またはその両方を含めることができます。  
  
 使用して[呼び出した](../mfc/reference/cstatusbarctrl-class.md#setparts)パーツの数、および長さを定義する、ステータス バーになります。 ステータス バーの各部分を作成した後に電話をかける[SetText](../mfc/reference/cstatusbarctrl-class.md#settext)と[SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon)テキストや、ステータス バーの特定の部分のアイコンを設定します。 部品が正常に設定されると、コントロールが自動的に再描画されます。  
  
 次の例では、既存を初期化`CStatusBarCtrl`オブジェクト (`m_StatusBarCtrl`) 4 つのペインにし、2 番目の部分でアイコン (IDI_ICON1) およびいくつかのテキストを設定します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]  
  
 モードの設定方法について、`CStatusBarCtrl`単純で、「」を参照するオブジェクト[CStatusBarCtrl オブジェクト モードの設定](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

