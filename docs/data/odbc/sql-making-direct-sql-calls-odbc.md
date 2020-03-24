---
title: 'SQL: SQL の直接呼び出し (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
ms.openlocfilehash: 9240a227cdc4004d1e6e2b7ac26946ca233b71ec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212629"
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: SQL の直接呼び出し (ODBC)

このトピックでは、次の内容について説明します。

- 直接 SQL 呼び出しを使用する場合。

- [データソースへの直接 SQL 呼び出しを行う方法](#_core_making_direct_sql_function_calls)。

> [!NOTE]
>  この情報は、MFC ODBC クラスに該当します。 MFC DAO クラスを使用している場合は、DAO ヘルプの「Microsoft Jet データベースエンジン SQL および ANSI SQL の比較」を参照してください。

##  <a name="when-to-call-sql-directly"></a><a name="_core_when_to_call_sql_directly"></a>SQL を直接呼び出す場合

新しいテーブルを作成したり、テーブルを削除 (削除) したり、既存のテーブルを変更したり、インデックスを作成したり、[データソース (ODBC)](../../data/odbc/data-source-odbc.md)スキーマを変更する他の sql 関数を実行したりするには、データベース定義言語 (DDL) を使用してデータソースに直接 SQL ステートメントを発行する必要があります。 (デザイン時に) テーブルのレコードセットを作成するためにウィザードを使用する場合は、テーブルのどの列をレコードセットに表すかを選択できます。 これにより、プログラムがコンパイルされた後で、データソースのユーザーまたは別のユーザーがテーブルに追加することはできません。 データベースクラスは DDL を直接サポートしていませんが、実行時に新しい列をレコードセットに動的にバインドするコードを記述することはできます。 このバインディングを実行する方法の詳細については、「[レコードセット: データ列を動的にバインドする (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。

DBMS 自体を使用して、スキーマや、DDL 関数を実行できる別のツールを変更することができます。 ODBC 関数呼び出しを使用して、レコードを返さない定義済みクエリ (ストアドプロシージャ) の呼び出しなど、SQL ステートメントを送信することもできます。

##  <a name="making-direct-sql-function-calls"></a><a name="_core_making_direct_sql_function_calls"></a>SQL 関数の直接呼び出し

[CDatabase Class](../../mfc/reference/cdatabase-class.md)オブジェクトを使用して SQL 呼び出しを直接実行できます。 SQL ステートメント文字列 (通常は `CString`) を設定し、`CDatabase` オブジェクトの[CDatabase:: ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)メンバー関数に渡します。 ODBC 関数呼び出しを使用して、通常はレコードを返す SQL ステートメントを送信する場合、レコードは無視されます。

## <a name="see-also"></a>参照

[SQL](../../data/odbc/sql.md)
