---
title: 既定の処理の変更 (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
ms.openlocfilehash: 7ea616caf176cd1e9e2f26bee1339640067b4e3e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213464"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>既定の処理の変更 (MFC データ アクセス)

[MFC アプリケーションウィザード](../mfc/reference/database-support-mfc-application-wizard.md)では、1つのテーブル内のすべてのレコードを選択するためのレコードセットクラスが書き込まれます。 この動作は多くの場合、次の 1 つ以上の方法で変更する必要があります。

- レコードセットのフィルターまたは並べ替え順序の設定。 この操作は、レコードセットオブジェクトが構築された後、その `Open` メンバー関数が呼び出される前に `OnInitialUpdate` で行います。 詳細については、「レコード[セット: レコードのフィルター処理 (odbc)](../data/odbc/recordset-filtering-records-odbc.md) 」および「レコード[セット: レコードの並べ替え (odbc)](../data/odbc/recordset-sorting-records-odbc.md)」を参照してください。

- レコードセットのパラメーター化。 実際のランタイム パラメーター値はフィルターの後に指定します。 詳細については、「[レコードセット: レコードセットのパラメーター化 (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 」を参照してください。

- カスタマイズした SQL 文字列を[Open](../mfc/reference/crecordset-class.md#open)メンバー関数に渡します。 この手法で実行できる内容の詳細については、「 [sql: レコードセットの Sql ステートメントのカスタマイズ (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)」を参照してください。

## <a name="see-also"></a>参照

[レコードビューの使用](../data/using-a-record-view-mfc-data-access.md)
