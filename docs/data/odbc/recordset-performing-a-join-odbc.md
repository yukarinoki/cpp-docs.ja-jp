---
title: 'レコード セット: 結合 (ODBC) を実行する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0be740a57f5c455b971dd23575401c666bf0723c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093312"
---
# <a name="recordset-performing-a-join-odbc"></a>レコードセット: 結合 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
## <a name="what-a-join-is"></a>どのような結合とは  
 一般的なデータ アクセス タスクで、結合操作では、1 つのレコード セット オブジェクトを使用して 1 つ以上のテーブルからデータを操作することができます。 2 つ以上のテーブルを結合するには、各テーブルから列を含めることができますが、アプリケーションに 1 つのテーブルとして表示されるレコード セットが生成されます。 結合が、すべてのテーブルが、SQL のすべての列を使用することもあります**選択**結合句を使用して、各テーブルの列の一部のみです。 データベース クラスでは、読み取り専用の結合が更新不可の結合をサポートします。  
  
 結合テーブルから列を含むレコードを選択するには、次の項目が必要です。  
  
-   結合されるすべてのテーブルの名前を含むテーブルの一覧です。  
  
-   すべての参加している列の名前を含む列のリストです。 名前が同じ名前が異なるテーブルから列はテーブル名によって修飾されます。  
  
-   フィルター (SQL**場所**句)、テーブルが参加している列を指定します。 このフィルターは"Table1.KeyCol テーブル 2. 基準列を ="、実際には、結合を行うことができます。  
  
 同じ方法で 3 つ以上のテーブルを結合するには複数の列のペア、SQL キーワードを使用して結合の各ペアが等しいか調査して**AND**です。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: 定義済みクエリ (ODBC) クラスの宣言](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)   
 [レコード セット: テーブル (ODBC) クラスの宣言](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [レコードセット: クエリの再実行 (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)