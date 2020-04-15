---
title: GDI リソースの割り当て
ms.date: 06/03/2019
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: 149aefeade6f99c294b12bfb294cdf1addb9e5e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370848"
---
# <a name="allocating-gdi-resources"></a>GDI リソースの割り当て

この記事では、印刷に必要な Windows グラフィックス デバイス インターフェイス (GDI) オブジェクトの割り当てと割り当て解除の方法について説明します。

> [!NOTE]
> 詳細については[、GDI+ SDK のドキュメントを参照してください](/windows/win32/gdiplus/-gdiplus-gdi-start)。

印刷の場合は、特定のフォント、ペン、またはその他の GDI オブジェクトを使用する必要があり、画面表示の場合は、その必要がないとします。 これらのオブジェクトはメモリを必要としますが、アプリケーションの起動時に割り当てるのは効率的ではありません。 アプリケーションがドキュメントを印刷していないときに、そのメモリが他の目的で必要になるかもしれません。 印刷の開始時にオブジェクトを割り当て、印刷の終了時に削除することをお勧めします。

これらの GDI オブジェクトを割り当てるには[、OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)メンバー関数をオーバーライドします。 この関数は、フレームワークが各印刷ジョブの先頭でこの関数を 1 回呼び出し[、OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)とは異なり、この関数はプリンター デバイス ドライバーを表す[CDC](../mfc/reference/cdc-class.md)オブジェクトにアクセスできる 2 つの理由から、この目的に適しています。 GDI オブジェクト (メンバーなど) を指すメンバー変数をビュー クラスに定義することで、印刷ジョブ中に使用するためにこれらの`CFont *`オブジェクトを格納できます。

作成した GDI オブジェクトを使用するには[、OnPrint](../mfc/reference/cview-class.md#onprint)メンバー関数でプリンター デバイス コンテキストに選択します。 ドキュメントのページごとに異なる GDI オブジェクトが必要な場合は`m_nCurPage`[、CPrintInfo](../mfc/reference/cprintinfo-structure.md)構造体のメンバーを調べて、それに応じて GDI オブジェクトを選択できます。 いくつかの連続するページで GDI オブジェクトが必要な場合は、`OnPrint` を呼び出すたびにデバイス コンテキストで選択する必要があります。

これらの GDI オブジェクトの割り当てを解除するには[、OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)メンバー関数をオーバーライドします。 フレームワークによって、各印刷ジョブの終了時に、この関数が呼び出されます。そのため、アプリケーションが他のタスクに戻る前に、印刷に固有の GDI オブジェクトの割り当てを解除できます。

## <a name="see-also"></a>関連項目

[印刷](../mfc/printing.md)<br/>
[既定の印刷プロセス](../mfc/how-default-printing-is-done.md)
