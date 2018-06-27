---
title: ツリー コントロール項目の選択 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc533046695db409067ff603e30cedbe11ad5ca4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953558"
---
# <a name="tree-control-item-selection"></a>ツリー コントロールの項目の選択
選択範囲が変更されたとき 1 つの項目からを別のツリー コントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 送信[TVN_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547)と[TVN_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544)通知メッセージです。 両方の通知には、変更のマウス クリックやキー入力の結果であるかどうかを指定する値が含まれます。 通知には、選択が解除される項目と、選択される項目に関する情報も含まれます。 この情報を使用すると、アイテムの選択状態に依存する項目の属性を設定します。 返す**TRUE**への応答`TVN_SELCHANGING`により、選択内容を変更する; から返す**FALSE**変更は可能です。  
  
 アプリケーションは呼び出すことによって、選択を変更することができます、 [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

