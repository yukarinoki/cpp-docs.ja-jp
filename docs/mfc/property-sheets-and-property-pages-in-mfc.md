---
title: MFC のプロパティ シートとプロパティ ページ
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: 10fb34c79745e672d30dd2d3c3b97d457583f795
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371169"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC のプロパティ シートとプロパティ ページ

プロパティ シートは、タブ ダイアログ ボックスとも呼ばれ、プロパティ ページを含むダイアログ ボックスです。 各プロパティ ページは、ダイアログ テンプレート リソースに基づいており、コントロールを含みます。 ページ上にタブが表示されます。 タブにはページの名前が付け、その目的が示されます。 ユーザーは、プロパティ シートのタブをクリックして、コントロールのセットを選択します。

ページを使用して、プロパティ シート内のコントロールを意味のあるセットにグループ化します。 含まれているプロパティ シートには、通常、独自のコントロールがいくつか用意されています。 これらはすべてのページに適用されます。

プロパティ シートは、クラス[CPropertySheet に](../mfc/reference/cpropertysheet-class.md)基づいています。 プロパティ ページは、クラス[CPropertyPage に](../mfc/reference/cpropertypage-class.md)基づいています。

プロパティ シートは、ビュー内の現在の選択など、外部オブジェクトの属性を変更するために一般的に使用される特別なダイアログ ボックスです。 プロパティ シートには、3 つの主要な部分があります: 含まれているダイアログ ボックス、1 つずつ表示される 1 つ以上のプロパティ ページ、およびユーザーがそのページを選択するためにクリックする各ページの上部にタブがあります。 プロパティ シートは、類似した設定またはオプションのグループを変更する場合に便利です。 プロパティ シートは、情報をわかりやすい方法でグループ化します。

> [!NOTE]
> を使用`CPropertySheet::DoModal`してプロパティ シートを表示しようとすると、システムが初回例外を生成する可能性があります。 この例外は、オブジェクトが作成される前にオブジェクトの[ウィンドウ スタイル](../mfc/reference/styles-used-by-mfc.md#window-styles)を変更しようとしているために発生します。 この例外の詳細と、それを回避または処理する方法については[、「CPropertySheet::DoModal」](../mfc/reference/cpropertysheet-class.md#domodal)を参照してください。

## <a name="see-also"></a>関連項目

[プロパティ シート](../mfc/property-sheets-mfc.md)
