---
title: 'レコードセット: レコードの並べ替え (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: 4bbe635cdda9152be6ba178b863147db93b7c706
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212746"
---
# <a name="recordset-sorting-records-odbc"></a>レコードセット: レコードの並べ替え (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、レコードセットを並べ替える方法について説明します。 並べ替えの基準にする列を1つ以上指定できます。また、昇順または降順 (**ASC**または**DESC**) を指定することもできます。指定された各列の既定値は**ASC**です。 たとえば、2つの列を指定した場合、レコードは最初にという名前の最初の列で並べ替えられ、次にという名前の2番目の列で並べ替えられます。 SQL **ORDER by**句では、並べ替えを定義します。 フレームワークが、レコードセットの SQL クエリに**ORDER BY**句を追加すると、句は選択の順序を制御します。

オブジェクトを構築した後で、その `Open` メンバー関数を呼び出す前に、レコードセットの並べ替え順序を設定する必要があります (または、`Open` メンバー関数が既に呼び出されている既存のレコードセットオブジェクトの `Requery` メンバー関数を呼び出す前)。

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>レコードセットオブジェクトの並べ替え順序を指定するには

1. 新しい recordset オブジェクトを構築します (または、既存のレコードセットの `Requery` を呼び出すための準備をします)。

1. オブジェクトの[m_strSort](../../mfc/reference/crecordset-class.md#m_strsort)データメンバーの値を設定します。

   並べ替えは、null で終わる文字列です。 **ORDER by**句の内容は含まれていますが、キーワード**order by**は含まれていません。 たとえば、次のようなサービスを使います。

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. フィルター、ロックモード、パラメーターなど、必要なその他のオプションを設定します。

1. 新しいオブジェクト (または既存のオブジェクトの `Requery`) の `Open` を呼び出します。

選択したレコードは、指定された順序で並べられます。 たとえば、生徒のレコードのセットを姓の降順に並べ替えるには、次のようにします。

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

レコードセットには、すべての学生レコードが含まれています。このレコードは、姓、名の順に降順に並べ替えられています。

> [!NOTE]
>  独自の SQL 文字列を `Open`に渡すことによってレコードセットの既定の SQL 文字列を上書きすることを選択した場合は、カスタム文字列に**ORDER by**句がある場合は並べ替えを設定しないでください。

## <a name="see-also"></a>参照

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: パラメーターを利用したレコードセット (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[レコードセット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
