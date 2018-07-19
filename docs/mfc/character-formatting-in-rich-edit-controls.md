---
title: リッチ エディット コントロールで書式設定文字 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c02165635e8715c1fcac28b9fbee72612b72c1f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349481"
---
# <a name="character-formatting-in-rich-edit-controls"></a>リッチ エディット コントロールでの文字書式の設定
リッチ エディット コントロールのメンバー関数を使用することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 文字の書式設定し、書式設定情報を取得します。 文字については、フォント、サイズ、色、および太字、斜体などの効果を指定し、保護されています。  
  
 使用して文字が書式設定を適用することができます、 [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat)と[SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat)メンバー関数。 現在の文字を選択したテキストの書式設定を確認するには[GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat)メンバー関数。 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881)構造がこれらのメンバー関数で使用を文字の属性を指定します。 重要なメンバーのいずれかの**CHARFORMAT**は**dwMask**です。 `SetSelectionCharFormat`と`SetWordCharFormat`、 **dwMask**文字属性はこの関数の呼び出しで設定されますを指定します。 `GetSelectionCharFormat` レポートの選択範囲の最初の文字の属性**dwMask**選択範囲全体で一貫性のある属性を指定します。  
  
 取得および設定できる、「既定の文字の書式設定、」これは、後で挿入された文字に適用される書式設定します。 たとえば、アプリケーションは、既定の文字を太字に書式を設定すると、ユーザーが入力する文字、その文字が太字にします。 既定の文字書式の設定を使用して、 [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat)と[SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat)メンバー関数。  
  
 「保護された」文字の属性は、テキストの外観を変更していません。 リッチ エディット コントロールがその親ウィンドウを送信する場合は、ユーザーが保護されたテキストを変更しようとすると、 **EN_PROTECTED**通知メッセージを許可するか、変更を禁止する親ウィンドウ。 この通知メッセージを受信する必要がありますして有効にすることを使用して、 [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask)メンバー関数。 イベント マスクの詳細については、次を参照してください。[リッチ エディット コントロールからの通知](../mfc/notifications-from-a-rich-edit-control.md)、このトピックで後述します。  
  
 前景色は文字属性が、背景色はリッチ エディット コントロールのプロパティです。 背景色を設定するには、使用、 [SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

