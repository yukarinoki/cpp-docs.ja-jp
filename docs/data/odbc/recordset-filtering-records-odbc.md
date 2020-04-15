---
title: 'レコードセット: レコードのフィルター処理 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
ms.openlocfilehash: 56b8c4f52ec294f58a760e1309d32aa81286ddec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367012"
---
# <a name="recordset-filtering-records-odbc"></a>レコードセット: レコードのフィルター処理 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

ここでは、レコードセットをフィルタ処理して、使用可能なレコードの特定のサブセットのみを選択する方法について説明します。 たとえば、MATH101 など、特定のコースのクラス セクションのみを選択できます。 フィルタは、SQL **WHERE**句の内容によって定義される検索条件です。 フレームワークがレコードセットの SQL ステートメントに追加すると **、WHERE**句は選択を制約します。

オブジェクトを構築した後、その`Open`メンバー関数を呼び出す前に (または、以前にメンバー関数が`Requery``Open`呼び出された既存のレコードセット オブジェクトのメンバー関数を呼び出す前に) レコードセット オブジェクトのフィルタを確立する必要があります。

#### <a name="to-specify-a-filter-for-a-recordset-object"></a>レコードセット オブジェクトのフィルタを指定するには

1. 新しいレコードセット オブジェクトを構築します`Requery`(または既存のオブジェクトを呼び出す準備をします)。

1. オブジェクトの[m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter)データ メンバーの値を設定します。

   フィルタは、SQL **WHERE**句の内容を含む NULL で終わる文字列ですが、キーワード**WHERE**は含まれません。 たとえば、次のようなサービスを使います。

    ```
    m_pSet->m_strFilter = "CourseID = 'MATH101'";
    ```

   not

    ```
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";
    ```

    > [!NOTE]
    >  リテラル文字列 "MATH101" は、上記の単一引用符で示されています。 ODBC SQL 仕様では、文字ストリング・リテラルを表すために単一引用符が使用されます。 この状況での DBMS の見積もり要件については、ODBC ドライバーのマニュアルを参照してください。 この構文についても、このトピックの最後の近くで詳しく説明します。

1. 並べ替え順序、ロック モード、パラメーターなど、必要なその他のオプションを設定します。 パラメータを指定すると特に便利です。 フィルタのパラメータ化については、「[レコードセット: レコードセットのパラメータ化 (ODBC)」](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)を参照してください。

1. 新`Open`しいオブジェクト (または`Requery`以前に開いたオブジェクト) を呼び出します。

> [!TIP]
> フィルターでパラメーターを使用することは、レコードを取得する最も効率的な方法である可能性があります。

> [!TIP]
> レコードセット フィルタは、テーブルを[結合](../../data/odbc/recordset-performing-a-join-odbc.md)したり、実行時に取得または計算された情報に基づいて[パラメータ](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)を使用する場合に便利です。

レコードセットは、指定した検索条件に一致するレコードのみを選択します。 たとえば、上で説明したコースフィルタを指定するには(例えば`strCourseID`、変数が「MATH101」に設定されている変数を想定)、次の操作を行います。

```
// Using the recordset pointed to by m_pSet

// Set the filter
m_pSet->m_strFilter = "CourseID = " + strCourseID;

// Run the query with the filter in place
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )

// Use the recordset
```

レコードセットには、MATH101 のすべてのクラス セクションのレコードが含まれています。

上記の例では、文字列変数を使用してフィルター文字列がどのように設定されているのか確認してください。 これは一般的な使用方法です。 ただし、コース ID にリテラル値 100 を指定するとします。 次のコードは、リテラル値を使用してフィルター文字列を正しく設定する方法を示しています。

```
m_strFilter = "StudentID = '100'";   // correct
```

単一引用符の使用に注意してください。フィルター文字列を直接設定した場合、フィルター文字列は次**の値ではありません**。

```
m_strFilter = "StudentID = 100";   // incorrect for some drivers
```

上記の引用は ODBC 仕様に準拠していますが、一部の DBMS では他の引用符が必要な場合があります。 詳細については、「 [SQL : レコードセットの SQL ステートメントのカスタマイズ (ODBC)」](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)を参照してください。

> [!NOTE]
> 独自の SQL 文字列を に渡してレコードセットの既定の SQL`Open`文字列をオーバーライドする場合は、カスタム文字列に**WHERE**句がある場合はフィルタを設定しないでください。 既定の SQL のオーバーライドの詳細については、「 [SQL : レコードセットの SQL ステートメントのカスタマイズ (ODBC)」](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)<br/>
[レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[レコードセット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
