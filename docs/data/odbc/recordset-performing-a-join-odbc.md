---
title: 'レコードセット: 結合 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
ms.openlocfilehash: 7e8d42f2b96911cd57aca7c132b53ed7c10162be
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212798"
---
# <a name="recordset-performing-a-join-odbc"></a>レコードセット: 結合 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

## <a name="what-a-join-is"></a>結合とは

一般的なデータアクセスタスクである結合操作を使用すると、1つのレコードセットオブジェクトを使用して複数のテーブルのデータを操作できます。 2つ以上のテーブルを結合すると、各テーブルの列を含むことができるレコードセットが生成されますが、アプリケーションには1つのテーブルとして表示されます。 結合ですべてのテーブルのすべての列が使用されることもありますが、結合の SQL **SELECT**句では、各テーブルの一部の列のみを使用する場合があります。 データベースクラスは読み取り専用の結合をサポートしますが、更新可能な結合はサポートしていません。

結合されたテーブルの列を含むレコードを選択するには、次のものが必要です。

- 結合されているすべてのテーブルの名前を含むテーブルの一覧。

- 参加しているすべての列の名前を含む列リスト。 同じ名前でテーブルが異なる列は、テーブル名によって修飾されます。

- テーブルが結合される列を指定するフィルター (SQL **WHERE**句) です。 このフィルターは"Table1.KeyCol = Table2.KeyCol"、実際には、結合を行うことができます。

複数の列のペアをひずみすることで、2つ以上のテーブルを結合できます。各ペアは、SQL キーワード**と**によって結合されます。

## <a name="see-also"></a>参照

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: 定義済みクエリを利用したクラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[レコードセット: テーブルにアクセスするレコードセット クラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[レコードセット: クエリの再実行 (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)
