---
title: リッチ エディット コントロールの概要
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
ms.openlocfilehash: 9ef696bc348dfb18b797b487224b97261020e11c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366872"
---
# <a name="overview-of-the-rich-edit-control"></a>リッチ エディット コントロールの概要

> [!IMPORTANT]
> アプリケーションが SDI、MDI、またはダイアログ ベースのいずれであるかに関係なく、ダイアログ ボックスでリッチ エディット コントロールを使用している場合は、ダイアログ ボックスが表示される前に[AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit)を呼び出す必要があります。 この関数を呼び出す一般的な場所は、`InitInstance`プログラムのメンバー関数です。 ダイアログ ボックスを表示するたびに呼び出す必要はありません。 で作業している場合は、`AfxInitRichEdit`電話をかける必要はありません`CRichEditView`。

リッチ エディット コントロール ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) は、テキストの書式設定用のプログラミング インターフェイスを提供します。 ただし、アプリケーションは、ユーザーが書式設定操作を使用できるようにするために必要なユーザー インターフェイス コンポーネントを実装する必要があります。 つまり、リッチ エディット コントロールでは、選択したテキストの文字属性または段落属性の変更がサポートされます。 文字属性の例としては、太字、斜体、フォント ファミリ、およびポイント サイズがあります。 段落属性の例としては、配置、余白、タブ位置などがあります。 ただし、ツール バー ボタン、メニュー項目、書式指定文字ダイアログ ボックスのいずれであっても、ユーザー インターフェイスを指定するのはユーザーの操作です。 現在の選択項目の属性をリッチ エディット コントロールに対してクエリする関数もあります。 これらの関数を使用して、属性の現在の設定を表示します。

文字と段落の書式設定の詳細については、このトピックの「[文字書式](../mfc/character-formatting-in-rich-edit-controls.md)と[段落の書式設定](../mfc/paragraph-formatting-in-rich-edit-controls.md)」を参照してください。

リッチ エディット コントロールは、複数行のエディット コントロールで使用される操作および通知メッセージのほとんどすべてをサポートします。 したがって、既にエディット コントロールを使用しているアプリケーションは、リッチ エディット コントロールを使用するように簡単に変更できます。 追加のメッセージと通知を使用すると、アプリケーションはリッチ エディット コントロールに固有の機能にアクセスできます。 エディット コントロールの詳細については、「 [CEdit](../mfc/reference/cedit-class.md)」を参照してください。

通知の詳細については、このトピックの後半[の「リッチ エディット コントロールからの通知](../mfc/notifications-from-a-rich-edit-control.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
