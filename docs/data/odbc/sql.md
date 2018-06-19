---
title: SQL |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: df1563d8bb3d53bb405fbb0d89b2b26cc964bd44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093244"
---
# <a name="sql"></a>SQL
SQL (構造化照会言語) は、クエリの定義、変更、およびデータを制御できるようにするリレーショナル データベースと通信する方法です。 SQL 構文を使用すると、指定した条件に従ってレコードを抽出するステートメントを構築できます。  
  
> [!NOTE]
>  この情報は、MFC ODBC クラスに適用されます。 MFC DAO クラスを使用する場合は、このトピックの比較の Microsoft Jet データベース エンジン SQL と DAO ヘルプの ANSI SQL を参照してください。  
  
 SQL ステートメントなどのキーワードの動詞を使用して開始**作成**または**選択**です。 SQL が非常に強力な言語です。1 つのステートメントは、テーブル全体に影響を与えます。  
  
 多くのバージョンの SQL の存在は、特定の DBMS ことに注意を使用して各開発。 MFC データベース クラスでは、X を/Open を対応する SQL ステートメントおよび SQL アクセス グループ一般的なアプリケーション環境 (CAE) SQL ドラフト仕様 (1991) のセットを認識します。 これらのステートメントの構文の詳細については、付録 C を参照してください、 *ODBC SDK* *プログラマーズ リファレンス*MSDN ライブラリの CD に収録されています。  
  
 このトピックでは、次の内容について説明します。  
  
-   [ODBC や SQL の間のリレーションシップ](#_core_open_database_connectivity_.28.odbc.29)です。  
  
-   [データベース クラスで使用される最も一般的な SQL キーワード](#_core_the_database_classes)です。  
  
-   [データベース クラスでの SQL の使用方法](#_core_how_the_database_classes_use_sql)です。  
  
##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> Open Database Connectivity (ODBC)  
 データベース クラスは、odbc で、コード内の SQL コマンドを埋め込むのではなく、呼び出しレベルのインターフェイスでの SQL を使用して実装されます。 ODBC SQL を使用して通信するために、[データソース](../../data/odbc/data-source-odbc.md)ODBC ドライバーを通じてします。 これらのドライバーでは、SQL を解釈し、必要に応じて、Microsoft Access などの特定のデータベース形式で使用するためを変換します。 ODBC で SQL の使用方法の詳細については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)と ODBC SDK*プログラマーズ リファレンス*MSDN ライブラリの CD にします。  
  
##  <a name="_core_the_database_classes"></a> データベース クラス  
 データベース クラスが操作し、既存のデータを更新できるように設計[データソース](../../data/odbc/data-source-odbc.md)です。 [MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)、 [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md)(を使用してアクセス**クラスの追加**)、データベース クラスでは、ほとんどの SQL ステートメントを構築するとします。  
  
 データベース クラスでは、既知のデータ操作言語 (DML) と SQL の一部を使用します。 これらのコマンドでは、データ ソースの一部またはすべてを使用、新しいレコードを追加、編集、およびレコードを削除できます。 次の表に、最も一般的な SQL キーワード方法は、データベース クラスを使用しています。  
  
### <a name="some-common-sql-keywords"></a>いくつかの一般的な SQL キーワード  
  
|SQL キーワード|ウィザードおよびデータベース クラスを使用して、|  
|-----------------|---------------------------------------------|  
|**SELECT**|識別するには、対象のテーブルとデータ ソース内の列を使用します。|  
|**WHERE**|選択範囲を限定するフィルターを適用します。|  
|**ORDER BY**|レコード セットを並べ替え順序を適用します。|  
|**挿入します。**|レコード セットに新しいレコードを追加します。|  
|**削除**|レコード セットからレコードを削除します。|  
|**更新プログラム**|レコードのフィールドを変更します。|  
  
 データベース クラスがさらに、ODBC を認識**呼び出す**ステートメントで、一部のデータ ソースで定義済みクエリ (またはストアド プロシージャ) の呼び出しに使用できます。 ODBC データベース ドライバーでは、これらのステートメントを解釈し、各 DBMS 用のコマンドを置換します。  
  
> [!NOTE]
>  すべての Dbms サポート**呼び出す**ステートメントです。  
  
 クラス内のユーザーが指定したステートメントが認識されない`CRecordset::Open`テーブル名として解釈されます。  
  
 フレームワークでの SQL ステートメントの作成方法の詳細については、次を参照してください。[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)と[SQL: をカスタマイズするレコード セットの SQL ステートメント (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)です。  
  
 SQL データベースでは、C および C++ で使用されるもののようなデータ型を使用します。 こうした類似性の詳細については、次を参照してください。 [SQL: SQL と C++ のデータ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)です。  
  
 サポートされている SQL ステートメント、データ型、コアな SQL 文法、および SQL では、に関する推奨されるパブリケーションの閲覧リストの一覧を含む、SQL の詳細についてを見つけることができます、 *ODBC SDK* *プログラマーズ リファレンス* MSDN ライブラリの CD に収録されています。  
  
##  <a name="_core_how_the_database_classes_use_sql"></a> データベース クラスでの SQL の使用方法  
 データベース クラスから派生したレコード セットでは、ODBC を使用して、データ ソースと通信し、ODBC は、SQL ステートメントを送信することによって、データ ソースからレコードを取得します。 このトピックでは、データベース クラスと SQL の間の関係について説明します。  
  
 レコード セットに SQL ステートメントの要素を構築して、SQL ステートメントの構築、`CString`です。 として文字列は、**選択**ステートメントでは、一連のレコードが返されます。  
  
 レコード セットは、ODBC SQL ステートメントを送信するデータ ソースを呼び出してと ODBC ドライバー マネージャーが、ステートメントを ODBC ドライバーに渡しますドライバーが、基になる DBMS に送信されます。 DBMS が、レコードの結果セットを返すし、ODBC ドライバーでは、アプリケーションにレコードが返されます。 データベース クラスでは、タイプ セーフな C++ クラスで結果セットから派生した、プログラムのアクセスを使用できます。`CRecordset`です。  
  
 次のトピックでは、データベース クラスでの SQL の使用方法の詳細についてを説明します。  
  
-   [SQL: レコード セットの SQL ステートメント (ODBC) のカスタマイズ](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)  
  
-   [SQL: SQL と C++ のデータ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)  
  
-   [SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)  
  
## <a name="see-also"></a>関連項目  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [ODBC の基礎](../../data/odbc/odbc-basics.md)