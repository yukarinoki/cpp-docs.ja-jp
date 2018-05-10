---
title: 選択して、レコードの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a4b76d0b4273e5afb32206336b4aabbfe9294eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="selecting-and-manipulating-records"></a>レコードの選択と操作
SQL を使用してデータ ソースからレコードを選択すると通常**選択**ステートメントでは、一連のテーブルまたはクエリからのレコードである結果セットを取得します。 データベース クラスを選択し、結果セットにアクセスするレコード セット オブジェクトを使用します。 クラスから派生したアプリケーションに固有のクラスのオブジェクトは、この[CRecordset](../../mfc/reference/crecordset-class.md)です。 レコード セット クラスを定義するときに、データ ソースに関連付けること、使用するには、テーブルおよびテーブルの列を指定します。 MFC アプリケーション ウィザードまたは**クラスの追加**(」の説明に従って[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) 特定のデータ ソースへの接続を持つクラスを作成します。 ウィザードの書き込み、 [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql)クラスのメンバー関数`CRecordset`テーブル名を取得します。 ウィザードを使用して、レコード セット クラスを作成する方法の詳細については、次を参照してください。[データベースのサポート、MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)と[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)です。  
  
 使用して、 [CRecordset](../../mfc/reference/crecordset-class.md) 、実行時にオブジェクトのことができます。  
  
-   現在のレコードのデータ フィールドを確認します。  
  
-   レコード セットの並べ替えまたはフィルター処理します。  
  
-   既定の SQL カスタマイズ**選択**ステートメントです。  
  
-   選択したレコードをスクロールします。  
  
-   追加、更新、または (データ ソースとレコード セットの両方が、更新可能な) 場合は、レコードを削除します。  
  
-   レコード セットにより、クエリを再実行するかどうかをテストし、レコード セットの内容を更新します。  
  
 レコード セット オブジェクトの使用が終了したらを閉じて破棄します。 レコード セットの詳細については、次を参照してください。[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)