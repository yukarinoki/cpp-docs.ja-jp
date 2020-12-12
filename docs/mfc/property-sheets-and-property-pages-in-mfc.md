---
description: 詳細については、「MFC のプロパティシートとプロパティページ」を参照してください。
title: MFC のプロパティ シートとプロパティ ページ
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: 93662dcf07e2810ad9f4f51d6df8341f9f6df6dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185428"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC のプロパティ シートとプロパティ ページ

プロパティシートは、タブダイアログボックスとも呼ばれ、プロパティページを含むダイアログボックスです。 各プロパティページは、ダイアログテンプレートリソースに基づいており、コントロールが含まれています。 上部にタブがあるページで囲まれています。 タブはページに名前を指定し、その目的を示します。 ユーザーは、プロパティシートのタブをクリックして、コントロールのセットを選択します。

ページを使用して、プロパティシート内のコントロールを意味のあるセットにグループ化します。 含まれているプロパティシートには、通常、独自のコントロールがいくつかあります。 これらはすべてのページに適用されます。

プロパティシートは、 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)クラスに基づいています。 プロパティページは、 [CPropertyPage](../mfc/reference/cpropertypage-class.md)クラスに基づいています。

プロパティシートは、通常はビュー内の現在の選択範囲など、一部の外部オブジェクトの属性を変更するために使用される特別な種類のダイアログボックスです。 プロパティシートには、次の3つの主要部分があります。 [含んでいる] ダイアログボックス、1つまたは複数のプロパティページ、およびユーザーがクリックしてページを選択する各ページの上部にあるタブです。 プロパティシートは、さまざまな設定やオプションのグループを変更する場合に便利です。 プロパティシートは、簡単に理解できる方法で情報をグループ化します。

> [!NOTE]
> を使用してプロパティシートを表示しようとすると、 `CPropertySheet::DoModal` システムによって初回例外が生成される可能性があります。 この例外は、オブジェクトが作成される前に、システムがオブジェクトの [ウィンドウスタイル](../mfc/reference/styles-used-by-mfc.md#window-styles) を変更しようとしているために発生します。 この例外の詳細と、この例外を回避または処理する方法については、「 [CPropertySheet::D oModal](../mfc/reference/cpropertysheet-class.md#domodal)」を参照してください。

## <a name="see-also"></a>関連項目

[プロパティシート](../mfc/property-sheets-mfc.md)
