---
title: 'SQL: レコードセットの SQL ステートメントのカスタマイズ (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
ms.openlocfilehash: 083d268d2b2f2eef072809b1afde9d6ea34f6996
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374520"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: レコードセットの SQL ステートメントのカスタマイズ (ODBC)

このトピックでは、次の内容について説明します。

- フレームワークが SQL ステートメントを構築する方法

- SQL ステートメントをオーバーライドする方法

> [!NOTE]
> この情報は、MFC ODBC クラスに該当します。 MFC DAO クラスを使用している場合は、DAO ヘルプのトピック「Microsoft Jet データベース エンジン SQL と ANSI SQL の比較」を参照してください。

## <a name="sql-statement-construction"></a>SQL ステートメントの構築

レコードセットは、主に SQL SELECT ステートメントに基づいてレコードを**選択**します。 ウィザードでクラスを宣言すると、次のような`GetDefaultSQL`オーバーライドバージョンのメンバー関数が書き込まれます`CAuthors`(というレコードセット クラスの場合)。

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

既定では、このオーバーライドは、ウィザードで指定したテーブル名を返します。 この例では、テーブル名は "AUTHORS" です。 後でレコードセットの`Open`メンバー関数を呼び出`Open`すと、次の形式の最終的な**SELECT**ステートメントが作成されます。

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

は`table-name`呼び出し`GetDefaultSQL`によって`rfx-field-list`取得され、RFX 関数呼び`DoFieldExchange`出しから取得されます。 これは、実行時にオーバーライドするバージョンに置き換える場合を除き **、SELECT**ステートメントで取得されますが、パラメーターまたはフィルターを使用して既定のステートメントを変更することもできます。

> [!NOTE]
> スペースを含む (または含むことがある) 列名を指定する場合は、名前を角かっこで囲む必要があります。 たとえば、"名" という名前は "[名]" にする必要があります。

既定の**SELECT ステートメント**をオーバーライドするには、 を呼**SELECT**び出`Open`すときに完全な SELECT ステートメントを含む文字列を渡します。 レコードセットは、独自の既定の文字列を作成する代わりに、指定した文字列を使用します。 置換ステートメントに**WHERE**句が含まれている場合は、 で`m_strFilter`2 つのフィルター ステートメントを使用するため、フィルターを指定しないでください。 同様に、置換ステートメントに**ORDER BY**句が含まれている場合は、 `m_strSort` 2 つのソートステートメントを持たないように、 でソートを指定しないでください。

> [!NOTE]
> フィルタ (または SQL ステートメントの他の部分) でリテラル文字列を使用する場合は、DBMS 固有のリテラルプレフィックスとリテラルサフィックス文字 (または文字) を使用して、このような文字列を "引用符で囲む" (指定された区切り記号で囲む) 必要があります。

また、DBMS によっては、外部結合などの操作に対する特別な構文要件が発生することもあります。 ODBC 関数を使用して、DBMS 用のドライバからこの情報を取得します。 たとえば、LITERAL_PREFIX文字`::SQLGetTypeInfo`やLITERAL_SUFFIX文字を要求するために、`SQL_VARCHAR`などの特定のデータ型を呼び出します。 データベースに依存しないコードを記述する場合は、構文の詳細については[、ODBC プログラマ](/sql/odbc/reference/odbc-programmer-s-reference)リファレンスの[「付録 C: SQL 文法](/sql/odbc/reference/appendixes/appendix-c-sql-grammar)」を参照してください。

レコードセット オブジェクトは、カスタム SQL ステートメントを渡す場合を除き、レコードの選択に使用する SQL ステートメントを構築します。 この方法は、主に`Open`メンバー関数の*lpszSQL*パラメーターで渡す値によって異なります。

SQL **SELECT**ステートメントの一般的な形式は次のとおりです。

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

レコードセットの SQL ステートメントに**DISTINCT**キーワードを追加する 1 つの方法は、 の最初の`DoFieldExchange`RFX 関数呼び出しにキーワードを埋め込むことです。 次に例を示します。

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
> この方法は、レコードセットを読み取り専用で開いた場合にのみ使用します。

## <a name="overriding-the-sql-statement"></a>SQL ステートメントのオーバーライド

次の表に *、lpszSQL*パラメータを 使用する`Open`可能性を示します。 表のケースは、表の後に説明されています。

**lpszSQL パラメータと結果の SQL 文字列**

|ケース|lpszSQL で渡す内容|結果の SELECT ステートメント|
|----------|------------------------------|------------------------------------|
|1|NULL|**テーブル***名から rfx フィールド リスト***FROM***を選択します。*<br /><br /> `CRecordset::Open`テーブル`GetDefaultSQL`名を取得する呼び出し。 結果の文字列は、戻り値`GetDefaultSQL`に応じて、ケース 2 ~ 5 のいずれかになります。|
|2|テーブル名|**テーブル***名から rfx フィールド リスト***FROM***を選択します。*<br /><br /> フィールド リストは、 の RFX`DoFieldExchange`ステートメントから取得されます。 空`m_strFilter``m_strSort`でない場合は **、WHERE**句または ORDER **BY**句を追加します。|
|3\*|完全な**SELECT**ステートメントですが **、WHERE**句または**ORDER BY**句がない場合|渡された通り。 空`m_strFilter``m_strSort`でない場合は **、WHERE**句または ORDER **BY**句を追加します。|
|4\*|**WHERE**句または**ORDER BY**句を含む完全な**SELECT**ステートメント|渡された通り。 `m_strFilter`または、空`m_strSort`のままにする必要があります。|
|5\*|ストアド プロシージャの呼び出し|渡された通り。|

\*`m_nFields` **SELECT**ステートメントで指定された列数以下でなければなりません。 **SELECT ステートメント**で指定する各列のデータ型は、対応する RFX 出力列のデータ型と同じである必要があります。

### <a name="case-1---lpszsql--null"></a>ケース 1 lpszSQL = NULL

レコードセットの選択は、`GetDefaultSQL`レコードセット`CRecordset::Open`を呼び出すときに何が返されるかによって異なります。 ケース 2 から 5 では、可能な文字列について説明します。

### <a name="case-2---lpszsql--a-table-name"></a>ケース 2 lpszSQL = テーブル名

レコードセットはレコード フィールド エクスチェンジ (RFX) を使用して、レコードセット クラスの`DoFieldExchange`オーバーライドで RFX 関数呼び出しで指定された列名から列リストを作成します。 ウィザードを使用してレコードセット クラスを宣言した場合、このケースの結果はケース 1 と同じです (ウィザードで指定したのと同じテーブル名を渡す場合)。 ウィザードを使用してクラスを記述しない場合、SQL ステートメントを構築する最も簡単な方法は、ケース 2 です。

MFC データベース アプリケーションからレコードを選択する SQL ステートメントを構築する例を次に示します。 フレームワークがメンバー関数を`GetDefaultSQL`呼び出すと、この関数はテーブルの名前を`SECTION`返します。

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

SQL **SELECT**ステートメントの列の名前を取得するには、フレームワークはメンバー関数`DoFieldExchange`を呼び出します。

```cpp
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Text(pFX, "CourseID", m_strCourseID);
    RFX_Text(pFX, "InstructorID", m_strInstructorID);
    RFX_Text(pFX, "RoomNo", m_strRoomNo);
    RFX_Text(pFX, "Schedule", m_strSchedule);
    RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

完了すると、SQL ステートメントは次のようになります。

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>ケース 3 lpszSQL = SELECT/FROM ステートメント

列リストは、RFX を使用して自動的に構築するのではなく、手で指定します。 次の場合に、これを行う必要があります。

- **SELECT**の後に**DISTINCT**キーワードを指定する場合。

   列リストは、 に示されている列名と型と同じ順序で`DoFieldExchange`一致する必要があります。

- 列をバインドして取得するために RFX を使用`::SQLGetData`するのではなく、ODBC 関数を使用して列の値を手動で取得する必要があります。

   たとえば、アプリケーションの配布後に、アプリケーションの顧客がデータベース テーブルに追加した新しい列を格納する場合があります。 ウィザードでクラスを宣言した時点では不明であったこれらのフィールド データ メンバーを追加する必要があります。

   列リストは、 に示されている列名と型と同じ順序で、その`DoFieldExchange`後に手動でバインドされた列の名前と一致する必要があります。 詳細については、「[レコードセット : データ列の動的なバインド (ODBC)」](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)を参照してください。

- **FROM**句で複数のテーブルを指定して、テーブルを結合する場合。

   詳細と例については、「[レコードセット: 結合の実行 (ODBC)」](../../data/odbc/recordset-performing-a-join-odbc.md)を参照してください。

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>ケース 4 lpszSQL = 選択/選択からプラス場所および/または順序

すべての項目を指定します: 列リスト ( RFX`DoFieldExchange`呼び出し元に基づく ) 、テーブル リスト **、WHERE**句または**ORDER BY**句の内容を指定します。 **WHERE**句や**ORDER BY**句をこの方法で指定する場合は`m_strFilter`、 や`m_strSort`を使用しないでください。

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>ケース 5 lpszSQL = ストアド プロシージャ呼び出し

定義済みのクエリ (Microsoft SQL Server データベースのストアド プロシージャなど) を呼び出す必要がある場合は *、lpszSQL*に渡した文字列に**CALL**ステートメントを記述する必要があります。 ウィザードでは、定義済みクエリを呼び出すレコードセット クラスの宣言はサポートされていません。 定義済みクエリの中には、レコードが返されるわけではありません。

定義済みのクエリがレコードを返さない場合は、メンバー関数`CDatabase``ExecuteSQL`を直接使用できます。 レコードを返す定義済みクエリの場合は、プロシージャが返す列に対して`DoFieldExchange`RFX 呼び出しを手動で書き込む必要があります。 RFX 呼び出しは、同じ順序で、定義済みクエリと同じ型を返す必要があります。 詳細については、「[レコードセット : 定義済みクエリのクラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[SQL: SQL と C++ のデータ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
