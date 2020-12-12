---
description: '詳細情報: レコードセット: レコードの並べ替え (ODBC)'
title: 'レコードセット: レコードの並べ替え (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: fbf2ef3c42061bac9b41550a0c44a20f68c099b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204421"
---
# <a name="recordset-sorting-records-odbc"></a>レコードセット: レコードの並べ替え (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、レコードセットを並べ替える方法について説明します。 並べ替えの基準にする列を1つ以上指定できます。また、昇順または降順 (**ASC** または **DESC**) を指定することもできます。指定された各列の既定値は **ASC** です。 たとえば、2つの列を指定した場合、レコードは最初にという名前の最初の列で並べ替えられ、次にという名前の2番目の列で並べ替えられます。 SQL **ORDER by** 句では、並べ替えを定義します。 フレームワークが、レコードセットの SQL クエリに **ORDER BY** 句を追加すると、句は選択の順序を制御します。

オブジェクトを構築した後、そのメンバー関数を呼び出す前 `Open` (または、 `Requery` `Open` メンバー関数が既に呼び出されている既存の recordset オブジェクトのメンバー関数を呼び出す前) に、レコードセットの並べ替え順序を設定する必要があります。

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>レコードセットオブジェクトの並べ替え順序を指定するには

1. 新しい recordset オブジェクトを構築します (または、既存のレコードセットを呼び出すための準備を `Requery` します)。

1. オブジェクトの [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) データメンバーの値を設定します。

   並べ替えは、null で終わる文字列です。 **ORDER by** 句の内容は含まれていますが、キーワード **order by** は含まれていません。 たとえば、次のようなサービスを使います。

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. フィルター、ロックモード、パラメーターなど、必要なその他のオプションを設定します。

1. `Open`新しいオブジェクト (または `Requery` 既存のオブジェクト) に対してを呼び出します。

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
> 独自の SQL 文字列をに渡してレコードセットの既定の SQL 文字列を上書きすることを選択した場合は `Open` 、カスタム文字列に **ORDER by** 句がある場合は並べ替えを設定しないでください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコードセットのパラメーター化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[レコードセット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
