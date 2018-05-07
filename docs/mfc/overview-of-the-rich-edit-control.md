---
title: リッチ エディット コントロールの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 143fc93fb07d9ac7c4e803bbce426c114c02bfeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="overview-of-the-rich-edit-control"></a>リッチ エディット コントロールの概要
> [!IMPORTANT]
>  ダイアログ ボックスで、リッチ エディット コントロールを使用しているかどうか (アプリケーションは、SDI、MDI、かどうかに関係なくダイアログ ベースまたは)、呼び出す必要があります[AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit)ボックスが表示されるダイアログ ボックスの前に一度です。 この関数を呼び出して標準的な場所は、プログラムの`InitInstance`メンバー関数。 最初にのみ、ダイアログ ボックスを表示するたびに呼び出す必要はありません。 呼び出していない`AfxInitRichEdit`を扱う場合`CRichEditView`です。  
  
 リッチ エディット コントロール ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) テキストの書式設定のプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーに使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。 つまり、豊富なは、選択されたテキストの文字や段落属性を変更するコントロールのサポートを編集します。 属性は、文字の例をいくつかは、太字、斜体、フォント ファミリ、し、サイズをポイントします。 段落の属性には、配置、余白、およびタブ ストップなどがあります。 ただし、これはユーザー インターフェイスを提供するまでツール バー ボタン、メニュー項目、または書式文字 ダイアログ ボックスであるかどうかです。 リッチ エディット コントロールの現在の選択の属性を問い合わせるための関数もします。 これらの関数をたとえば、属性で、現在の設定を表示するのに使用して、太字の文字が書式設定属性が選択されている場合、コマンド UI にチェック マークを設定します。  
  
 文字および段落の書式設定の詳細については、次を参照してください。[文字書式](../mfc/character-formatting-in-rich-edit-controls.md)と[段落の書式設定](../mfc/paragraph-formatting-in-rich-edit-controls.md)このトピックで後述します。  
  
 リッチ エディット コントロール サポートされてほぼすべての操作と通知メッセージが複数行エディット コントロールで使用します。 したがって、アプリケーションが既に編集コントロールを使用して変更できることを簡単にリッチを使用するには、コントロールが編集できません。 追加のメッセージと通知は、機能豊富なに固有の編集コントロールにアクセスするアプリケーションを有効にします。 編集コントロールの概要については、次を参照してください。 [CEdit](../mfc/reference/cedit-class.md)です。  
  
 通知の詳細については、次を参照してください。[リッチ エディット コントロールからの通知](../mfc/notifications-from-a-rich-edit-control.md)このトピックで後述します。  
  
## <a name="see-also"></a>関連項目  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

