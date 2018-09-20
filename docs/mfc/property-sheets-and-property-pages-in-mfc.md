---
title: プロパティ シートとプロパティ ページ (mfc の) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f35282ce46aff3a3f0fba5fca505653cd892a392
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430048"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC のプロパティ シートとプロパティ ページ

プロパティ シート、タブ ダイアログ ボックスとも呼ばれますが、プロパティ ページを含むダイアログ ボックスです。 各プロパティ ページでは、ダイアログ テンプレート リソースに基づいており、コントロールが含まれています。 上部のタブ ページに囲まれています。 タブ、ページの名前をその目的を示します。 ユーザーは、コントロールのセットを選択するプロパティ シートのタブをクリックします。

ページを使用すると、意味のあるセット プロパティ シート内のコントロールにグループ化します。 通常、コンテナーのプロパティ シートには、独自のいくつかのコントロールがあります。 これらは、すべてのページに適用されます。

プロパティ シートがクラスに基づく[CPropertySheet](../mfc/reference/cpropertysheet-class.md)します。 プロパティ ページはクラスに基づいて[CPropertyPage](../mfc/reference/cpropertypage-class.md)します。

プロパティ シートは、一般にビューの現在の選択など、いくつかの外部オブジェクトの属性を変更するために使用されるダイアログ ボックスの特別な種類です。 プロパティ シートには次の 3 つの主要な部分: 格納 ダイアログ ボックス、1 つまたは複数のプロパティ ページに示すように 1 つずつが発生した場合とユーザーがクリックすると、そのページを選択する各ページの上部にあるタブ。 プロパティ シートは、いくつかの類似したグループの設定または変更するオプションがある場合に便利です。 プロパティ シートでは、わかりやすい方法で情報をグループ化します。

> [!NOTE]
>  使用してプロパティ シートを表示しようと`CPropertySheet::DoModal`システムは、初回例外を生成可能性があります。 システムは、変更しようとします。 この例外が発生、[ウィンドウ スタイル](../mfc/reference/styles-used-by-mfc.md#window-styles)オブジェクトが作成される前に、オブジェクトの。 この例外とも回避またはそれを処理する方法の詳細については、次を参照してください。[する](../mfc/reference/cpropertysheet-class.md#domodal)します。

## <a name="see-also"></a>関連項目

[プロパティ シート](../mfc/property-sheets-mfc.md)

