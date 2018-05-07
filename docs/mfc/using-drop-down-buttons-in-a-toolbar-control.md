---
title: ツール バー コントロールのドロップダウン ボタンを使って |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39edda143e28d262e8eea826ced5c24855fb310b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>ツール バー コントロールでのドロップダウン ボタンの使い方
標準のプッシュ ボタンに加えてでは、ツールバーは、ドロップダウン ボタンもあります。 ドロップダウン ボタンは通常の下向きの矢印によって示されます。  
  
> [!NOTE]
>  場合にのみ、下向きの矢印が表示されます、`TBSTYLE_EX_DRAWDDARROWS`拡張スタイルが設定されています。  
  
 この矢印 (または、ボタン自体、矢印が存在しない場合) で、ユーザーがクリックしたとき、`TBN_DROPDOWN`ツール バー コントロールの親に通知メッセージを送信します。 この通知を処理し、ポップアップ メニューを表示Internet Explorer の動作に似ています。  
  
 次の手順では、ポップアップ メニューとツールバーのドロップダウン ボタンを実装する方法を示します。  
  
### <a name="to-implement-a-drop-down-button"></a>ドロップダウン ボタンを実装するには  
  
1.  1 回、`CToolBarCtrl`オブジェクトが作成された、設定、`TBSTYLE_EX_DRAWDDARROWS`スタイルを次のコードを使用します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  設定、`TBSTYLE_DROPDOWN`新規のスタイルのいずれか ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton)または[AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) か、既存の ([です](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) が表示されるドロップダウン ボタンのボタンです。 次の例で、既存のボタンを変更する、`CToolBarCtrl`オブジェクト。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  追加、`TBN_DROPDOWN`バー オブジェクトの親クラスをハンドラー。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  新しいハンドラーでは、適切なポップアップ メニューを表示します。 次のコードでは、1 つの方法を示します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

