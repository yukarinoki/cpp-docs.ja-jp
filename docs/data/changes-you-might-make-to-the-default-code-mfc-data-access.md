---
title: 変更 (MFC データ アクセス) の既定のコードに加える可能性があります |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e647f6350819fa2cccb5f8319f95fbac16ca19fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088366"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>既定の処理の変更 (MFC データ アクセス)
[MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)が 1 つのテーブル内のすべてのレコードを選択したレコード セット クラスを書き込みます。 この動作は多くの場合、次の 1 つ以上の方法で変更する必要があります。  
  
-   レコードセットのフィルターまたは並べ替え順序の設定。 これを行う`OnInitialUpdate`レコード セット オブジェクトを構築する前にその**開く**メンバー関数が呼び出されます。 詳細については、次を参照してください。[レコード セット: レコードのフィルター処理 (ODBC)](../data/odbc/recordset-filtering-records-odbc.md)と[レコード セット: レコードの並べ替え (ODBC)](../data/odbc/recordset-sorting-records-odbc.md)です。  
  
-   レコードセットのパラメーター化。 実際のランタイム パラメーター値はフィルターの後に指定します。 詳細については、次を参照してください[レコード セット: レコード セット (ODBC) のパラメーター化。](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   カスタマイズした SQL 文字列を渡す、[開く](../mfc/reference/crecordset-class.md#open)メンバー関数。 この方法で行うことができますの詳細については、次を参照してください。 [SQL: をカスタマイズするレコード セットの SQL ステートメント (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード ビューを使用します。](../data/using-a-record-view-mfc-data-access.md)