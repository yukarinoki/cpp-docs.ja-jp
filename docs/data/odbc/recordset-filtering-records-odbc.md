---
description: '詳細情報: レコードセット: レコードのフィルター処理 (ODBC)'
title: 'レコードセット: レコードのフィルター処理 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
ms.openlocfilehash: 15cf191f7a5a037c032726bc4f16a5774fb2857b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322339"
---
# <a name="recordset-filtering-records-odbc"></a>レコードセット: レコードのフィルター処理 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、レコードセットをフィルター処理して、使用可能なレコードの特定のサブセットのみを選択する方法について説明します。 たとえば、MATH101 など、特定のコースのクラスセクションだけを選択することができます。 フィルターは、SQL の **where** 句の内容によって定義される検索条件です。 フレームワークによってレコードセットの SQL ステートメントに追加されると、 **where** 句によって選択が制限されます。

オブジェクトを構築した後、メンバー関数を呼び出す前に、レコードセットオブジェクトのフィルターを作成する必要があり `Open` ます (または、 `Requery` メンバー関数が既に呼び出されている既存の recordset オブジェクトのメンバー関数を呼び出す前に `Open` )。

#### <a name="to-specify-a-filter-for-a-recordset-object"></a>レコードセットオブジェクトのフィルターを指定するには

1. 新しいレコードセットオブジェクトを構築します (または、 `Requery` 既存のオブジェクトに対してを呼び出す準備をします)。

1. オブジェクトの [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) データメンバーの値を設定します。

   フィルターは、null で終わる文字列であり、SQL の **where** 句の内容を含みますが、 **キーワードは** 含まれません。 たとえば、次のようなサービスを使います。

    ```
    m_pSet->m_strFilter = "CourseID = 'MATH101'";
    ```

   not

    ```
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";
    ```

    > [!NOTE]
    >  リテラル文字列 "MATH101" は、上に単一引用符付きで表示されます。 ODBC SQL 仕様では、文字列リテラルを表すために単一引用符が使用されています。 この状況では、ODBC ドライバーのドキュメントで DBMS の引用符の要件を確認してください。 この構文の詳細については、このトピックの最後の方で説明します。

1. 並べ替え順序、ロックモード、パラメーターなど、必要なその他のオプションを設定します。 パラメーターの指定は特に便利です。 フィルターのパラメーター化の詳細については、「 [レコードセット: レコードセットのパラメーター化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。

1. `Open`新しいオブジェクト (または `Requery` 、以前に開いたオブジェクト) に対してを呼び出します。

> [!TIP]
> フィルターでパラメーターを使用することは、レコードを取得するための最も効率的な方法である可能性があります。

> [!TIP]
> レコードセットフィルターは、テーブルを [結合](../../data/odbc/recordset-performing-a-join-odbc.md) したり、実行時に取得または計算された情報に基づいて [パラメーター](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) を使用したりする場合に便利です。

レコードセットは、指定した検索条件に一致するレコードだけを選択します。 たとえば、上で説明したコースフィルター (たとえば、変数が現在設定されている場合は "MATH101") を指定するには、 `strCourseID` 次の手順を実行します。

```
// Using the recordset pointed to by m_pSet

// Set the filter
m_pSet->m_strFilter = "CourseID = " + strCourseID;

// Run the query with the filter in place
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )

// Use the recordset
```

レコードセットには、MATH101 のすべてのクラスセクションのレコードが含まれています。

文字列変数を使用して、上記の例でフィルター文字列がどのように設定されているかに注目してください。 これは一般的な使用方法です。 しかし、course ID に対してリテラル値100を指定するとします。 次のコードは、リテラル値を使用してフィルター文字列を正しく設定する方法を示しています。

```
m_strFilter = "StudentID = '100'";   // correct
```

単一引用符文字を使用することに注意してください。フィルター文字列を直接設定した場合、フィルター文字列は **次のようになります**。

```
m_strFilter = "StudentID = 100";   // incorrect for some drivers
```

上記の引用符は ODBC 仕様に準拠していますが、一部の Dbms では他の引用符が必要になる場合があります。 詳細については、「 [sql: レコードセットの Sql ステートメントのカスタマイズ (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)」を参照してください。

> [!NOTE]
> 独自の SQL 文字列をに渡してレコードセットの既定の SQL 文字列を上書きすることを選択した場合 `Open` 、カスタム文字列に **where** 句がある場合はフィルターを設定しないでください。 既定の SQL をオーバーライドする方法の詳細については、「 [sql: レコードセットの Sql ステートメントのカスタマイズ (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)<br/>
[レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[レコードセット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
