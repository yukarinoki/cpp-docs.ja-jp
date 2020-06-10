---
title: ヘッダーとフッター
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], multipage documents
- page headers [MFC], printing
- headers [MFC], printing
- footers [MFC], printing
- page footers [MFC], printing
- page headers [MFC]
- printing [MFC], headers and footers
- page footers [MFC]
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
ms.openlocfilehash: 7024c57dbe41a579582d409d0536db0ca0bc46d6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620109"
---
# <a name="headers-and-footers"></a>ヘッダーとフッター

この記事では、印刷されるドキュメントにヘッダーとフッターを追加する方法について説明します。

画面上のドキュメントを見ると、ドキュメントの名前とドキュメント内の現在の場所は、通常、タイトルバーとステータスバーに表示されます。 ドキュメントの印刷されたコピーを見るときは、ヘッダーまたはフッターに名前とページ番号を表示すると便利です。 これは、印刷と画面表示を実行する方法が WYSIWYG によって異なるという一般的な方法です。

[OnPrint](reference/cview-class.md#onprint)メンバー関数は、ヘッダーまたはフッターを印刷するための適切な場所です。これは、各ページに対して呼び出され、画面表示ではなく印刷専用として呼び出されるためです。 ヘッダーまたはフッターを印刷するための個別の関数を定義し、それにプリンターデバイスコンテキストを渡すことができ `OnPrint` ます。 場合によっては、 [OnDraw](reference/cview-class.md#ondraw)を呼び出す前にウィンドウの原点または範囲を調整して、ページの本文がヘッダーまたはフッターと重複しないようにする必要があります。 また、 `OnDraw` ページに収まるドキュメントの量を減らすことができるため、変更が必要になる場合もあります。

ヘッダーまたはフッターによって取得される領域を補正する方法の1つとして、 [CPrintInfo](reference/cprintinfo-structure.md)の**m_rectDraw**メンバーを使用する方法があります。 ページが印刷されるたびに、このメンバーはページの使用可能な領域で初期化されます。 ページの本文を印刷する前にヘッダーまたはフッターを印刷する場合は、 **m_rectDraw**に格納されている四角形のサイズを小さくして、ヘッダーまたはフッターによって取得される領域を考慮することができます。 次 `OnPrint` に、 **m_rectDraw**を参照して、ページの本文を印刷するための残りの領域を確認します。

[OnPrepareDC](reference/cview-class.md#onpreparedc)からヘッダーを印刷することはできません。これは、 `StartPage` [CDC](reference/cdc-class.md)のメンバー関数が呼び出される前に呼び出されるためです。 その時点で、プリンターデバイスコンテキストはページ境界であると見なされます。 印刷は、メンバー関数からのみ実行でき `OnPrint` ます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [印刷 (複数ページのドキュメントを)](multipage-documents.md)

- [印刷用の GDI リソースの割り当て](allocating-gdi-resources.md)

## <a name="see-also"></a>関連項目

[印刷](printing.md)
