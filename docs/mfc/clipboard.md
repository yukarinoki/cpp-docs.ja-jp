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
ms.openlocfilehash: b17268c78fb5e82cbe75cbe0647b931d06934ef1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440795"
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

- [Windows クリップボード](https://msdn.microsoft.com/library/ms648709)

- [ドラッグ アンド ドロップ (OLE) を実装します。](../mfc/drag-and-drop-ole.md)

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
