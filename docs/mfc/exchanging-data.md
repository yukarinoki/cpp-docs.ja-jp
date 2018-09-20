---
title: データを交換する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 504d2ff9f011770f75db73a63fa77b821281269b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435559"
---
# <a name="exchanging-data"></a>データの交換

プロパティ シートとアプリケーション間でデータの交換では、ほとんどのダイアログ ボックスと同様、プロパティ シートの最も重要な機能の 1 つです。 この記事では、このタスクを実行する方法について説明します。

実際にプロパティ シートの各プロパティ ページを使用してデータを交換するは、プロパティ シートを使用してデータを交換します。 プロパティ ページを使用してデータを交換するための手順と同じです ダイアログ ボックスでは、データを交換するため、 [CPropertyPage](../mfc/reference/cpropertypage-class.md)オブジェクトが同じ特殊[CDialog](../mfc/reference/cdialog-class.md)オブジェクト。 プロシージャでは、ダイアログ ボックスのオブジェクトのダイアログ ボックスとメンバー変数内のコントロール間でデータを交換するフレームワークのダイアログ データ エクス (チェンジ DDX) 機能を利用します。

プロパティ シートと通常のダイアログ ボックスにデータを交換する重要な違いは、プロパティ シートのすべてのページを使用してデータを交換する必要がありますので、プロパティ シートが、複数のページがあります。 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。

次の例は、ビューとプロパティ シートの 2 つのページ間のデータの交換を示しています。

[!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]

## <a name="see-also"></a>関連項目

[プロパティ シート](../mfc/property-sheets-mfc.md)

