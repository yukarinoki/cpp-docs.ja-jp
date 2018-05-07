---
title: レコード ビュー (MFC データ アクセス) を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 23dd3335f6c77a3efec26f13e78824806f05821a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-a-record-view--mfc-data-access"></a>レコード ビューの使用法 (MFC データ アクセス)
このトピックでは、ウィザードで生成したレコード ビュー用の既定のコードをカスタマイズする一般的な方法について説明します。 一般に、必要な制約によるレコードの選択、[フィルター](../data/odbc/recordset-filtering-records-odbc.md)または[パラメーター](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)、おそらく[並べ替え](../data/odbc/recordset-sorting-records-odbc.md)レコード、SQL ステートメントのカスタマイズします。  
  
 使用して`CRecordView`が使用する場合とほぼ同じ[CFormView](../mfc/reference/cformview-class.md)です。 基本的には、レコード ビューを使用して、1 つのレコードセットのレコードを表示し、場合によっては更新します。 さらに、できるだけでなくで説明した他のレコード セットを使用する可能性があります[レコード ビュー: セカンド レコード セットからリスト ボックス](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)