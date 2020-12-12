---
description: '詳細情報: レコードセット: 結合の実行 (ODBC)'
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
ms.openlocfilehash: 1c7aa7bfb6925d9f7e916ddb6cd60061667d7859
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204512"
---
# <a name="recordset-performing-a-join-odbc"></a>レコードセット: 結合 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

## <a name="what-a-join-is"></a>結合とは

一般的なデータアクセスタスクである結合操作を使用すると、1つのレコードセットオブジェクトを使用して複数のテーブルのデータを操作できます。 2つ以上のテーブルを結合すると、各テーブルの列を含むことができるレコードセットが生成されますが、アプリケーションには1つのテーブルとして表示されます。 結合ですべてのテーブルのすべての列が使用されることもありますが、結合の SQL **SELECT** 句では、各テーブルの一部の列のみを使用する場合があります。 データベースクラスは読み取り専用の結合をサポートしますが、更新可能な結合はサポートしていません。

結合されたテーブルの列を含むレコードを選択するには、次のものが必要です。

- 結合されているすべてのテーブルの名前を含むテーブルの一覧。

- 参加しているすべての列の名前を含む列リスト。 同じ名前でテーブルが異なる列は、テーブル名によって修飾されます。

- テーブルが結合される列を指定するフィルター (SQL **WHERE** 句) です。 このフィルターは、"KeyCol = KeyCol" という形式になり、実際には結合を実行します。

複数の列のペアをひずみすることで、2つ以上のテーブルを結合できます。各ペアは、SQL キーワード **と** によって結合されます。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: 定義済みクエリのクラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[レコードセット: テーブルのクラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[レコードセット: レコードセットの再クエリ (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)
