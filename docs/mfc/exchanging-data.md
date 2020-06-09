---
title: データの交換
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
ms.openlocfilehash: 5be82567e02fd5e935d42f9eff5bdee20fa0d5a8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622704"
---
# <a name="exchanging-data"></a>データの交換

ほとんどのダイアログボックスと同様に、プロパティシートとアプリケーション間のデータの交換は、プロパティシートの最も重要な機能の1つです。 この記事では、このタスクを実行する方法について説明します。

プロパティシートとデータを交換することは、実際には、プロパティシートの個々のプロパティページとデータを交換することに関係します。 プロパティページとデータを交換する手順は、ダイアログボックスを使用してデータを交換する場合と同じです。これは、 [CPropertyPage](reference/cpropertypage-class.md)オブジェクトが特殊な[CDialog](reference/cdialog-class.md)オブジェクトであるためです。 この手順では、ダイアログボックス内のコントロールとダイアログボックスオブジェクトのメンバー変数の間でデータを交換する、フレームワークの dialog data exchange (DDX) 機能を利用しています。

プロパティシートと通常のダイアログボックスを使用してデータを交換する場合の重要な違いは、プロパティシートに複数のページがあることです。そのため、プロパティシート内のすべてのページとデータを交換する必要があります。 DDX の詳細については、「[ダイアログデータエクスチェンジと検証](dialog-data-exchange-and-validation.md)」を参照してください。

次の例では、ビューとプロパティシートの2つのページの間でデータを交換する方法を示します。

[!code-cpp[NVC_MFCDocView#4](codesnippet/cpp/exchanging-data_1.cpp)]

## <a name="see-also"></a>関連項目

[プロパティシート](property-sheets-mfc.md)
