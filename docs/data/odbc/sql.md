---
title: SQL
ms.date: 05/09/2019
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
ms.openlocfilehash: e5ab824f850b6050e11c10734dd709330af416b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376443"
---
# <a name="sql"></a>SQL

SQL (構造化照会言語) は、データの定義、照会、変更、制御を可能にするリレーショナル データベースと通信する方法です。 SQL 構文を使用することで、指定した条件を満たすレコードを抽出するステートメントを構築できます。

> [!NOTE]
> この情報は、MFC ODBC クラスに該当します。 MFC DAO クラスを使用している場合、DAO Help の「Comparison of Microsoft Jet Database Engine SQL and ANSI SQL」 (Microsoft Jet Database Engine SQL と ANSI SQL の比較) というトピックを参照してください。

SQL ステートメントは、**CREATE** や **SELECT** など、キーワード動詞から始まります。 SQL は非常に強力な言語であり、1 つのステートメントがテーブル全体に影響を与えることがあります。

SQL にはさまざまなバージョンが存在します。いずれも特定の DBMS を念頭に開発されています。 MFC データベース クラスでは、X/Open と SQL Access Group Common Applications Environment (CAE) SQL ドラフト仕様 (1991) に対応する一連の SQL ステートメントが認識されます。 これらのステートメントの構文については、MSDN Library CD の *ODBC SDK* *Programmer's Reference* の付録 C を参照してください。

このトピックでは、次の内容について説明します。

- [ODBC と SQL の関係](#_core_open_database_connectivity_.28.odbc.29)。

- [データベース クラスで使用される最も一般的な SQL キーワード](#_core_the_database_classes)。

- [データベース クラスが SQL を使用する方法](#_core_how_the_database_classes_use_sql)。

## <a name="open-database-connectivity-odbc"></a><a name="_core_open_database_connectivity_.28.odbc.29"></a>データベース接続を開く (ODBC)

データベース クラスは ODBC で実装されます。ODBC では、コードに SQL コマンドを埋め込むのではなく、呼び出しレベルのインターフェイスで SQL が使用されます。 ODBC では、ODBC ドライバー経由で[データ ソース](../../data/odbc/data-source-odbc.md)と通信する際、SQL が使用されます。 このようなドライバーでは、SQL が解釈され、必要に応じて、Microsoft Access など、特定のデータベース形式で使用する目的で変換されます。 ODBC による SQL の使用の詳細については、[ODBC](../../data/odbc/odbc-basics.md) と MSDN Library CD の ODBC SDK *Programmer's Reference* を参照してください。

## <a name="database-classes"></a><a name="_core_the_database_classes"></a> データベース クラス

> [!NOTE]
> MFC ODBC コンシューマー ウィザードは、Visual Studio 2019 以降はご利用いただけなくなります。 引き続き、コンシューマーを手動で作成することはできます。

データベース クラスは、既存の[データ ソース](../../data/odbc/data-source-odbc.md)でデータを操作し、更新できるように設計されています。 [MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)、[MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (**[クラスの追加]** 経由でアクセス)、データベース クラスでは、ほとんどの SQL ステートメントが自動的に構築されます。

データベース クラスでは、データ操作言語 (DML) と呼ばれる SQL の一部が使用されます。 これらのコマンドでは、データ ソースの全部または一部を使用したり、新しいレコードを追加、編集、削除したりできます。 次の表は、最も一般的な SQL キーワードとデータベース クラスによるその使用方法をまとめたものです。

### <a name="some-common-sql-keywords"></a>一般的な SQL キーワード

|SQL キーワード|ウィザードとデータベース クラスでそれを使用する目的|
|-----------------|---------------------------------------------|
|**選択**|データ ソースの中から使用されるテーブルと列を特定する|
|**WHERE**|選択を絞り込むフィルターを適用する|
|**ORDER BY**|レコードセットに並べ替え順序を適用する|
|**挿入**|レコードセットに新しいレコードを追加する|
|**削除**|レコードセットから新しいレコードを削除する|
|**更新**|レコードのフィールドを変更する|

また、データベース クラスでは、ODBC **CALL** ステートメントが認識されます。このステートメントを利用し、事前定義されたクエリ (またはストアド プロシージャ) を一部のデータ ソースで呼び出すことができます。 ODBC データベース ドライバーではこれらのステートメントが解釈され、各 DBMS に適したコマンドが代用されます。

> [!NOTE]
> 一部の DBMS では **CALL** ステートメントがサポートされていません。

クラスで `CRecordset::Open` のユーザー指定のステートメントを認識できない場合、テーブル名として解釈されます。

フレームワークが SQL ステートメントを構築する方法の詳細については、「[レコードセット : レコードセットがレコードを選択する方法 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)および[SQL : レコードセットの SQL ステートメント (ODBC) をカスタマイズする](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)」を参照してください。

SQL データベースでは、C と C++ で使用されるものに似たデータ型が使用されます。 これらの類似点については、「 [SQL: SQL および C++ データ型 (ODBC)」](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)を参照してください。

サポートされている SQL ステートメント、データ型、SQL 中心的文法、SQL に関するおすすめ図書リストなど、SQL に関する詳細は、MSDN Library CD の *ODBC SDK* *Programmer's Reference* にあります。

## <a name="how-the-database-classes-use-sql"></a><a name="_core_how_the_database_classes_use_sql"></a> データベース クラスによる SQL の使用方法

データベース クラスから派生されたレコードセットでは、データ ソースと通信するために ODBC が使用されます。ODBC では、SQL ステートメントを送信することでデータ ソースからレコードが取得されます。 このトピックでは、データベース クラスと SQL の関係について説明します。

レコードセットでは、SQL ステートメントの断片を集めて `CString` を組み立てることで SQL ステートメントが作られます。 文字列は **SELECT** ステートメントとして構築されます。このステートメントからは一連のレコードが返されます。

SQL ステートメントをデータ ソースに送信する目的でレコードセットにより ODBC が呼び出されるとき、ODBC Driver Manager によってステートメントが ODBC ドライバーに渡され、ドライバーによってそれが基礎 DBMS に送信されます。 DBMS によってレコードの結果セットが返され、ODBC ドライバーによってアプリケーションにレコードが返されます。 データベース クラスによって、`CRecordset` から誘導されたタイプ セーフな C++ クラスの結果セットにプログラムはアクセスできます。

次のトピックでは、データベース クラスによって SQL が使用されるしくみについて説明します。

- [SQL : レコードセットの SQL ステートメントのカスタマイズ (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

- [SQL: SQL と C++ のデータ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)

- [SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

## <a name="see-also"></a>関連項目

[データベース接続を開く (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[ODBC の基本](../../data/odbc/odbc-basics.md)
