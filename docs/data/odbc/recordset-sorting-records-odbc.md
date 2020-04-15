---
title: 'レコードセット: レコードの並べ替え (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: 8b4deea1d8cbd4abe01ccc7a4114131378abe463
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366923"
---
# <a name="recordset-sorting-records-odbc"></a>レコードセット: レコードの並べ替え (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、レコードセットを並べ替える方法について説明します。 ソートの基準となる 1 つ以上の列を指定し、昇順または降順 **(ASC**または**DESC、**;**ASC**は、指定された各列のデフォルトです。 たとえば、2 つの列を指定した場合、最初にレコードが最初に並べ替えられ、次に 2 番目の列が名前付きで並べ替えられます。 SQL **ORDER BY**句は、ソートを定義します。 フレームワークがレコードセットの SQL クエリに**ORDER BY**句を追加すると、その句によって選択の順序が制御されます。

オブジェクトを構築した後、その`Open`メンバー関数を呼び出す前に (または、以前にメンバー関数が`Requery``Open`呼び出された既存のレコードセット オブジェクトのメンバー関数を呼び出す前に) レコードセットの並べ替え順序を設定する必要があります。

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>レコードセット オブジェクトの並べ替え順序を指定するには

1. 新しいレコードセット オブジェクトを構築します`Requery`(または既存のレコードセット オブジェクトを呼び出す準備をします)。

1. オブジェクトの[m_strSort](../../mfc/reference/crecordset-class.md#m_strsort)データ メンバーの値を設定します。

   並べ替えは、NULL で終わる文字列です。 このファイルには ORDER **BY**句の内容が含まれていますが、キーワード**ORDER BY**は含まれません。 たとえば、次のようなサービスを使います。

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. フィルタ、ロック モード、パラメータなど、必要なその他のオプションを設定します。

1. 新`Open`しいオブジェクト (または`Requery`既存のオブジェクト) を呼び出します。

選択したレコードは指定どおりに順序付けられます。 たとえば、学生レコードのセットを姓、名の順に並べ替えるには、次の操作を行います。

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

レコードセットには、学生レコードがすべて含まれています。

> [!NOTE]
> 独自の SQL 文字列を に渡してレコードセットの既定の SQL`Open`文字列をオーバーライドする場合は、カスタム文字列に**ORDER BY**句がある場合は、並べ替えを設定しないでください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: パラメーターを利用したレコードセット (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[レコードセット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
