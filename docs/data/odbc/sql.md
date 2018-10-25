---
title: SQL |Microsoft Docs
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
ms.openlocfilehash: 17403899d5ace5f4e5fd3263da936d6665e331a9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053255"
---
# <a name="sql"></a>SQL

SQL (Structured Query Language) は、クエリの定義、変更、およびデータを制御できるようにリレーショナル データベースと通信する方法です。 SQL 構文を使用すると、指定した条件に従ってレコードを抽出するステートメントを構築できます。

> [!NOTE]
>  この情報は、MFC ODBC クラスに適用されます。 MFC DAO クラスを使用する場合は、トピックの比較の Microsoft Jet データベース エンジン SQL と ANSI SQL DAO のヘルプを参照してください。

SQL ステートメントの begin キーワード動詞を使用してなど**作成**または**選択**します。 SQL は、非常に強力な言語です。1 つのステートメントは、テーブル全体に影響を与えます。

SQL の多くのバージョンが存在する、各開発で特定の DBMS に注意してください。 MFC データベース クラスでは、一連の X と開いている場合に対応する SQL ステートメントおよび SQL アクセス グループ一般的なアプリケーション環境 (CAE) SQL ドラフト仕様 (1991) を認識します。 これらのステートメントの構文については、付録 C を参照してください、 *ODBC SDK* *プログラマーズ リファレンス*MSDN ライブラリ CD に収録されています。

このトピックでは、次の内容について説明します。

- [ODBC と SQL 間のリレーションシップ](#_core_open_database_connectivity_.28.odbc.29)します。

- [データベース クラスで使用される最も一般的な SQL キーワード](#_core_the_database_classes)します。

- [SQL データベース クラスの使用方法](#_core_how_the_database_classes_use_sql)します。

##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> Open Database Connectivity (ODBC)

データベース クラスは、odbc でのコードで SQL コマンドを埋め込むのではなく、呼び出しレベルのインターフェイスでの SQL を使用して実装されます。 ODBC SQL を使用して通信する、[データソース](../../data/odbc/data-source-odbc.md)ODBC ドライバーをします。 これらのドライバーは、SQL を解釈し、必要に応じて、Microsoft Access などの特定のデータベース形式で使用するために変換するため、します。 ODBC SQL の使用方法の詳細については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)と ODBC SDK*プログラマーズ リファレンス*、MSDN ライブラリ cd。

##  <a name="_core_the_database_classes"></a> データベース クラス

データベース クラスが操作し、既存のデータを更新できるように設計[データソース](../../data/odbc/data-source-odbc.md)します。 [MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)、 [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md)(を使用してアクセス**クラスの追加**)、データベース クラスでは、ほとんどの SQL ステートメントを構築するとします。

データベース クラスでは、データ操作言語 (DML) と呼ばれる SQL の一部を使用します。 これらのコマンドでは、データ ソースのすべてまたは一部を使用、新しいレコードを追加、編集、およびレコードを削除できます。 次の表に、最も一般的な SQL キーワードおよび方法は、データベース クラスに使用します。

### <a name="some-common-sql-keywords"></a>一般的な SQL キーワード

|SQL キーワード|ウィザードおよびデータベース クラス|
|-----------------|---------------------------------------------|
|**SELECT**|対象のテーブルとデータ ソース内の列が使用されることを確認します。|
|**WHERE**|選択範囲を限定するフィルターを適用します。|
|**ORDER BY**|レコード セットを並べ替え順序を適用します。|
|**挿入します。**|レコード セットには、新しいレコードを追加します。|
|**DELETE**|レコード セットからレコードを削除します。|
|**更新プログラム**|レコードのフィールドを変更します。|

データベース クラスがさらに、ODBC を認識**呼び出す**ステートメントで、一部のデータ ソースの定義済みクエリ (またはストアド プロシージャ) の呼び出しに使用できます。 ODBC データベース ドライバーでは、これらのステートメントを解釈し、各 DBMS 用の適切なコマンドに置換されます。

> [!NOTE]
>  Dbms のすべてのサポート**呼び出す**ステートメント。

クラス内のユーザーが指定したステートメントが認識されない`CRecordset::Open`テーブル名として解釈されます。

フレームワークでの SQL ステートメントの作成方法の詳細については、次を参照してください。[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)と[SQL: の SQL ステートメント (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)します。

SQL データベースでは、C および C++ で使用されるもののようなデータ型を使用します。 これらの類似点の詳細については、次を参照してください。 [SQL: SQL と C++ のデータ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)します。

サポートされている SQL ステートメント、データ型、SQL コアの文法、および SQL に関する推奨されるパブリケーションの読み取りリストの一覧を含む、SQL の詳細についてを見つけることができます、 *ODBC SDK* *プログラマー リファレンス* MSDN ライブラリ CD に収録されています。

##  <a name="_core_how_the_database_classes_use_sql"></a> SQL データベース クラスの使用方法

データベース クラスから派生したレコード セットでは、ODBC を使用して、データ ソースと通信し、ODBC SQL ステートメントを送信することによって、データ ソースからレコードを取得します。 このトピックでは、データベース クラスと SQL 間のリレーションシップについて説明します。

レコード セットを SQL ステートメントの要素を構築することにより、SQL ステートメントを構築します、`CString`します。 として文字列は、**選択**ステートメントで、レコードのセットを返します。

レコード セットを呼び出す ODBC データ ソースに SQL ステートメントを送信すると ODBC ドライバー マネージャーが ODBC ドライバーにステートメントを渡しますドライバーが基になる DBMS に送信します。 DBMS は、レコードの結果セットを返し、ODBC ドライバーは、アプリケーションに、レコードを返します。 データベース クラスでは、タイプ セーフな C++ クラスで結果セットから派生した、プログラムのアクセスを使用できます。`CRecordset`します。

SQL データベース クラスの使用方法の詳細については、以下のトピックです。

- [SQL: レコード セットの SQL ステートメント (ODBC) のカスタマイズ](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

- [SQL: SQL と C++ のデータ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)

- [SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

## <a name="see-also"></a>関連項目

[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[ODBC の基礎](../../data/odbc/odbc-basics.md)