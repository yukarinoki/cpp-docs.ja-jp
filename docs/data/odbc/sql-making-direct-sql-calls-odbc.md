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
ms.openlocfilehash: e2421e047d217fdc7a138509385399fa37d36a1f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374500"
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: SQL の直接呼び出し (ODBC)

このトピックでは、次の内容について説明します。

- 直接 SQL 呼び出しを使用する場合。

- [データ ソースに対して直接 SQL 呼び出しを行う方法](#_core_making_direct_sql_function_calls)。

> [!NOTE]
> この情報は、MFC ODBC クラスに該当します。 MFC DAO クラスを使用している場合は、DAO ヘルプのトピック「Microsoft Jet データベース エンジン SQL と ANSI SQL の比較」を参照してください。

## <a name="when-to-call-sql-directly"></a><a name="_core_when_to_call_sql_directly"></a>SQL を直接呼び出す場合

新しいテーブルの作成、テーブルの削除 (削除) 、既存のテーブルの変更、インデックスの作成、および[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)スキーマを変更するその他の SQL 関数を実行するには、データベース定義言語 (DDL) を使用してデータ ソースに対して SQL ステートメントを直接実行する必要があります。 ウィザードを使用してテーブルのレコードセットを作成する場合 (デザイン時に)、テーブルのどの列をレコードセットで表すのかを選択できます。 この場合、ユーザーまたはデータ ソースの別のユーザーが、後でプログラムをコンパイルした後でテーブルに追加することはできません。 データベース クラスは DDL を直接サポートしませんが、実行時に新しい列を動的にレコードセットにバインドするコードを記述できます。 このバインドの方法については、「[レコードセット : データ列の動的連結 (ODBC)」](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)を参照してください。

DBMS 自体を使用して、DDL 関数を実行できるスキーマや別のツールを変更できます。 レコードを返さない定義済みクエリ (ストアド プロシージャ) の呼び出しなど、SQL ステートメントの送信に ODBC 関数呼び出しを使用することもできます。

## <a name="making-direct-sql-function-calls"></a><a name="_core_making_direct_sql_function_calls"></a>SQL 関数呼び出しの直接実行

[CDatabase クラス](../../mfc/reference/cdatabase-class.md)オブジェクトを使用して、SQL 呼び出しを直接実行できます。 SQL ステートメント文字列 (通常は )`CString`を設定し、`CDatabase`オブジェクトの[CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)メンバー関数に渡します。 ODBC 関数呼び出しを使用して、通常はレコードを返す SQL ステートメントを送信する場合、レコードは無視されます。

## <a name="see-also"></a>関連項目

[SQL](../../data/odbc/sql.md)
