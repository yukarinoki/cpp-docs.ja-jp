---
description: 詳細については、「GDI リソースの割り当て」を参照してください。
title: GDI リソースの割り当て
ms.date: 06/03/2019
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: 348f1ca1eadc22dfc8ca6faa6c31bb2f8d81e51e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176809"
---
# <a name="allocating-gdi-resources"></a>GDI リソースの割り当て

この記事では、印刷に必要な Windows グラフィックス デバイス インターフェイス (GDI) オブジェクトの割り当てと割り当て解除の方法について説明します。

> [!NOTE]
> 詳細については、 [Gdi + SDK のドキュメント](/windows/win32/gdiplus/-gdiplus-gdi-start)を参照してください。

印刷の場合は、特定のフォント、ペン、またはその他の GDI オブジェクトを使用する必要があり、画面表示の場合は、その必要がないとします。 これらのオブジェクトはメモリを必要としますが、アプリケーションの起動時に割り当てるのは効率的ではありません。 アプリケーションがドキュメントを印刷していないときに、そのメモリが他の目的で必要になるかもしれません。 印刷の開始時にオブジェクトを割り当て、印刷の終了時に削除することをお勧めします。

これらの GDI オブジェクトを割り当てるには、 [OnBeginPrinting](reference/cview-class.md#onbeginprinting) メンバー関数をオーバーライドします。 この関数は、この目的に適しています。フレームワークは、各印刷ジョブの開始時にこの関数を1回呼び出します。 [OnPreparePrinting](reference/cview-class.md#onprepareprinting)とは異なり、この関数は、プリンターデバイスドライバーを表す [CDC](reference/cdc-class.md) オブジェクトにアクセスできます。 これらのオブジェクトは、GDI オブジェクト (たとえば、メンバーなど) をポイントするビュークラスでメンバー変数を定義することで、印刷ジョブ中に使用するために保存でき `CFont *` ます。

作成した GDI オブジェクトを使用するには、 [OnPrint](reference/cview-class.md#onprint) メンバー関数のプリンターデバイスコンテキストに選択します。 ドキュメントのページごとに異なる GDI オブジェクトが必要な場合は、 `m_nCurPage` [CPrintInfo](reference/cprintinfo-structure.md) 構造体のメンバーを調べ、それに応じて gdi オブジェクトを選択できます。 いくつかの連続するページで GDI オブジェクトが必要な場合は、`OnPrint` を呼び出すたびにデバイス コンテキストで選択する必要があります。

これらの GDI オブジェクトの割り当てを解除するには、 [OnEndPrinting](reference/cview-class.md#onendprinting) メンバー関数をオーバーライドします。 フレームワークによって、各印刷ジョブの終了時に、この関数が呼び出されます。そのため、アプリケーションが他のタスクに戻る前に、印刷に固有の GDI オブジェクトの割り当てを解除できます。

## <a name="see-also"></a>関連項目

[印刷](printing.md)<br/>
[既定の印刷方法](how-default-printing-is-done.md)
