---
title: データを交換する |Microsoft ドキュメント
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
ms.openlocfilehash: e503bd9268423fbe63ec76de4bcb5443a7d52696
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345821"
---
# <a name="exchanging-data"></a>データの交換
ほとんどのダイアログ ボックスと同様、プロパティ シートとアプリケーション間でデータの交換はプロパティ シートの最も重要な機能の 1 つです。 この記事では、このタスクを実行する方法について説明します。  
  
 プロパティ シートを使用してデータを交換するには実際にプロパティ シートの各プロパティ ページを使用してデータを交換します。 プロパティ ページを使用してデータを交換するための手順は、同じ ダイアログ ボックスでは、データを交換するので、 [CPropertyPage](../mfc/reference/cpropertypage-class.md)オブジェクトがだけ、特殊な[CDialog](../mfc/reference/cdialog-class.md)オブジェクト。 プロシージャでは、ダイアログ ボックスのオブジェクトのダイアログ ボックスとメンバー変数内のコントロール間のデータを交換するフレームワークのダイアログ データ エクス (チェンジ DDX) 機能を活用します。  
  
 プロパティ シートを含む、通常のダイアログ ボックスを使用してデータを交換する重要な違いは、プロパティ シート、複数のページのため、プロパティ シートのすべてのページを使用してデータを交換する必要があります。 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。  
  
 次の例では、ビューとプロパティ シートの 2 つのページ間で交換するデータを示します。  
  
 [!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [プロパティ シート](../mfc/property-sheets-mfc.md)

