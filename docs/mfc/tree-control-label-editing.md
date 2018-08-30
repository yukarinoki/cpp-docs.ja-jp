---
title: ツリー コントロールのラベルの編集 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f9ba5360ddce81061bf73839e1700fed57c9fa7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210404"
---
# <a name="tree-control-label-editing"></a>ツリー コントロールのラベルの編集
ユーザーは、ツリー コントロールの項目のラベルを直接編集できます ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) を持つ、 **TVS_EDITLABELS**スタイル。 ユーザーは、フォーカスがある項目のラベルをクリックして編集を開始します。 アプリケーションを使用して編集を開始、 [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel)メンバー関数。 ツリー コントロールでは、編集するときに通知を開始しがキャンセルまたは完了を送信します。 編集が完了したら、項目のラベルを更新する場合は適切です。  
  
 ラベルの編集が開始すると、ツリー コントロールが送信する、 [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit)通知メッセージ。 この通知を処理することによっては、一部のラベルの編集を許可して、他のユーザーの編集できないようにします。 0 を返すことにより、編集、および 0 以外の値を返すようにします。  
  
 ツリー コントロールの送信ラベルの編集をキャンセル、または完了時に、 [TVN_ENDLABELEDIT](/windows/desktop/Controls/tvn-endlabeledit)通知メッセージ。 *LParam*パラメーターは、のアドレスを[NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa)構造体。 **項目**メンバーは、 [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema)アイテムを識別し、編集済みのテキストを含む構造体。 更新するため、項目のラベルでは、該当する場合はおそらく編集済みの文字列を検証した後にあります。 *PszText*のメンバー`TV_ITEM`編集がキャンセルされた場合は 0 です。  
  
 ラベル編集、通常への応答中に、 [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit)通知のメッセージを使用してラベルを編集するために使用される編集コントロールにポインターを取得できます、 [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol)メンバー関数。 編集コントロールの呼び出すことができます[SetLimitText](../mfc/reference/cedit-class.md#setlimittext)メンバー関数は、ユーザーが入力できるテキストまたはサブクラスをインターセプトし、無効な文字を破棄して、編集コントロールの量を制限します。 ただし、のみ、編集コントロールが表示される*後* **TVN_BEGINLABELEDIT**送信されます。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

