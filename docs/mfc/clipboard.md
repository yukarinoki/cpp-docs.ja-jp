---
title: クリップボードのトピック
ms.date: 11/04/2016
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
ms.openlocfilehash: 5814b2fdfc7fbcaca00037cc64dd71aa27d65cc3
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504613"
---
# <a name="clipboard"></a>クリップボードのトピック

この一連のトピックでは、MFC アプリケーションで Windows クリップボードのサポートを実装する方法について説明します。 Windows クリップボードは、2 つの方法で使用されます。

- 切り取り、コピー、貼り付けなどの標準の編集 メニューのコマンドを実装します。

- 統一されたデータを実装すると、ドラッグの転送し、ドロップ (OLE)。

クリップボードには、ソースとターゲット間でデータを転送する標準の Windows 方法です。 OLE 操作で非常に便利なことができます。 OLE の登場によって、Windows で 2 つのクリップボード機構ですがあります。 標準の Windows クリップボード API は、引き続き使用できますが、OLE のデータ転送メカニズムにより補完されたされています。 OLE の汎用データ転送 (UDT) は、切り取り、コピー、およびクリップボードでの貼り付けをサポートしているとドラッグ アンド ドロップします。

クリップボードとは、ハンドルまたは独自のクラスがないため、Windows セッション全体で共有システム サービスです。 クラスのメンバー関数を使用して、クリップボードを管理する[CWnd](../mfc/reference/cwnd-class.md)します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [クリップボード機構を使用する場合](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)

- [従来の Windows クリップボード API を使用します。](../mfc/clipboard-using-the-windows-clipboard.md)

- [OLE クリップボード機構の使用](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

- [コピーと貼り付けデータ](../mfc/clipboard-copying-and-pasting-data.md)

- [その他のデータ形式の追加](../mfc/clipboard-adding-other-formats.md)

- [Windows クリップボード](/windows/desktop/dataxchg/clipboard)

- [ドラッグ アンド ドロップ (OLE) を実装します。](../mfc/drag-and-drop-ole.md)

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
