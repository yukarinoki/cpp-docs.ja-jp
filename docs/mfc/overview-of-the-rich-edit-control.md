---
title: リッチ エディット コントロールの概要
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
ms.openlocfilehash: b99a5c6faaae4679b6aef67f240febbfb0f596e8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617709"
---
# <a name="overview-of-the-rich-edit-control"></a>リッチ エディット コントロールの概要

> [!IMPORTANT]
> アプリケーションが SDI、MDI、ダイアログベースのいずれであるかに関係なく、ダイアログボックスでリッチエディットコントロールを使用している場合は、ダイアログボックスが表示される前に[AfxInitRichEdit](reference/application-information-and-management.md#afxinitrichedit)を1回呼び出す必要があります。 この関数を呼び出す一般的な場所は、プログラムの `InitInstance` メンバー関数です。 ダイアログボックスを初めて表示するたびに、このメソッドを呼び出す必要はありません。 を使用する場合は、を呼び出す必要はありません `AfxInitRichEdit` `CRichEditView` 。

リッチエディットコントロール ([CRichEditCtrl](reference/cricheditctrl-class.md)) は、テキストを書式設定するためのプログラミングインターフェイスを提供します。 ただし、アプリケーションは、ユーザーが書式設定操作を使用できるようにするために必要なユーザーインターフェイスコンポーネントを実装する必要があります。 つまり、リッチエディットコントロールでは、選択したテキストの文字または段落の属性の変更がサポートされます。 文字属性の例としては、太字、斜体、フォントファミリ、ポイントサイズなどがあります。 段落属性の例としては、配置、余白、タブストップなどがあります。 ただし、ツールバーのボタン、メニュー項目、または [書式設定文字] ダイアログボックスのいずれであるかにかかわらず、ユーザーインターフェイスを提供する必要があります。 また、リッチエディットコントロールに対してクエリを実行し、現在の選択範囲の属性を照会する関数もあります。 属性の現在の設定を表示するには、これらの関数を使用します。たとえば、選択範囲に太字の文字書式属性がある場合は、コマンド UI にチェックマークを設定します。

文字と段落の書式設定の詳細については、このトピックで後述する「[文字の書式](character-formatting-in-rich-edit-controls.md)設定と[段落書式](paragraph-formatting-in-rich-edit-controls.md)」を参照してください。

リッチエディットコントロールでは、複数行のエディットコントロールで使用されるほとんどすべての操作と通知メッセージがサポートされます。 そのため、既に編集コントロールを使用しているアプリケーションは、リッチエディットコントロールを使用するように簡単に変更できます。 追加のメッセージと通知を使用すると、アプリケーションは、リッチエディットコントロールに固有の機能にアクセスできます。 エディットコントロールの詳細については、「 [CEdit](reference/cedit-class.md)」を参照してください。

通知の詳細については、このトピックで後述[する「リッチエディットコントロールからの通知](notifications-from-a-rich-edit-control.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](using-cricheditctrl.md)<br/>
[制限](controls-mfc.md)
