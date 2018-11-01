---
title: GDI リソースの割り当て
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: d637d524d37dc466e15aed3b571cccf24c18216d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505730"
---
# <a name="allocating-gdi-resources"></a>GDI リソースの割り当て

この記事では、印刷に必要な Windows グラフィックス デバイス インターフェイス (GDI) オブジェクトの割り当てと割り当て解除の方法について説明します。

> [!NOTE]
>  詳細については、GDI + SDK のドキュメントを参照してください: [ https://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp](https://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp)します。

印刷の場合は、特定のフォント、ペン、またはその他の GDI オブジェクトを使用する必要があり、画面表示の場合は、その必要がないとします。 これらのオブジェクトはメモリを必要としますが、アプリケーションの起動時に割り当てるのは効率的ではありません。 アプリケーションがドキュメントを印刷していないときに、そのメモリが他の目的で必要になるかもしれません。 印刷の開始時にオブジェクトを割り当て、印刷の終了時に削除することをお勧めします。

これらの GDI オブジェクトを割り当てるには、オーバーライド、 [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)メンバー関数。 この関数は、2 つの理由はこの目的に適して: フレームワークこの関数を呼び出す 1 回の各印刷ジョブとは異なり、先頭にある[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)、この関数へのアクセスには、 [CDC](../mfc/reference/cdc-class.md)プリンター デバイス ドライバーを表すオブジェクト。 GDI オブジェクトを指すビュー クラスでメンバー変数を定義することで、印刷ジョブ中に使用するため、これらのオブジェクトを格納できます (たとえば、`CFont *`メンバー、およびなど)。

作成した GDI オブジェクトを使用するプリンター デバイス コンテキストに選択し、 [OnPrint](../mfc/reference/cview-class.md#onprint)メンバー関数。 調べることができますが、ドキュメントのさまざまなページの別の GDI オブジェクトを必要な場合、`m_nCurPage`のメンバー、 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体し、それに応じて GDI オブジェクトを選択します。 いくつかの連続するページで GDI オブジェクトが必要な場合は、`OnPrint` を呼び出すたびにデバイス コンテキストで選択する必要があります。

これらの GDI オブジェクトの割り当てを解除するには、オーバーライド、 [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)メンバー関数。 フレームワークによって、各印刷ジョブの終了時に、この関数が呼び出されます。そのため、アプリケーションが他のタスクに戻る前に、印刷に固有の GDI オブジェクトの割り当てを解除できます。

## <a name="see-also"></a>関連項目

[印刷](../mfc/printing.md)<br/>
[既定の印刷プロセス](../mfc/how-default-printing-is-done.md)

