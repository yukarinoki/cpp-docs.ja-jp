---
description: '詳細については、「SQL: レコードセットの SQL ステートメントのカスタマイズ (ODBC)」を参照してください。'
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
ms.openlocfilehash: 73765ed66dacbc017cca6236ae5a90388390fa45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278689"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: レコードセットの SQL ステートメントのカスタマイズ (ODBC)

このトピックでは、次の内容について説明します。

- フレームワークによる SQL ステートメントの構築方法

- SQL ステートメントを上書きする方法

> [!NOTE]
> この情報は、MFC ODBC クラスに該当します。 MFC DAO クラスを使用している場合は、DAO ヘルプの「Microsoft Jet データベースエンジン SQL および ANSI SQL の比較」を参照してください。

## <a name="sql-statement-construction"></a>SQL ステートメントの構築

レコードセットは主に SQL **SELECT** ステートメントに基づいてレコードを選択します。 ウィザードを使用してクラスを宣言すると、次のようなメンバー関数のオーバーライドバージョンが書き込まれ `GetDefaultSQL` ます (というレコードセットクラスの場合 `CAuthors` )。

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

既定では、この上書きによって、ウィザードで指定したテーブル名が返されます。 この例では、テーブル名は "AUTHORS" です。 後でレコードセットのメンバー関数を呼び出すと `Open` 、 `Open` 次の形式の最終的な **SELECT** ステートメントが作成されます。

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

`table-name`はを呼び出すことによって取得され `GetDefaultSQL` 、 `rfx-field-list` の RFX 関数呼び出しから取得され `DoFieldExchange` ます。 これは、 **SELECT** ステートメントを実行時にオーバーライドするバージョンに置き換える場合を除き、パラメーターまたはフィルターを使用して既定のステートメントを変更することもできます。

> [!NOTE]
> 空白を含む (または含めることができる) 列名を指定する場合は、名前を角かっこで囲む必要があります。 たとえば、"First Name" という名前は "[First Name]" になります。

既定の **select** ステートメントをオーバーライドするには、を呼び出すときに、完全な **select** ステートメントを含む文字列を渡し `Open` ます。 独自の既定文字列を構築する代わりに、レコードセットは指定した文字列を使用します。 置換ステートメントに **WHERE** 句が含まれている場合は、 `m_strFilter` 2 つのフィルターステートメントを使用するため、でフィルターを指定しないでください。 同様に、置換ステートメントに **ORDER BY** 句が含まれている場合は、 `m_strSort` 2 つの並べ替えステートメントを使用しないように、の並べ替えを指定しないでください。

> [!NOTE]
> フィルター (または SQL ステートメントのその他の部分) でリテラル文字列を使用する場合は、DBMS 固有のリテラルプレフィックスとリテラルサフィックス文字 (または文字) を使用して、文字列の "引用符" (指定した区切り記号で囲む) が必要になることがあります。

DBMS によっては、外部結合などの操作に対して特別な構文要件が発生する場合もあります。 ODBC 関数を使用して、DBMS 用のドライバーからこの情報を取得します。 たとえば、などの `::SQLGetTypeInfo` 特定のデータ型に対してを呼び出し、 `SQL_VARCHAR` LITERAL_PREFIX と LITERAL_SUFFIX 文字を要求します。 データベースに依存しないコードを記述する場合は、「 [付録 C:](/sql/odbc/reference/appendixes/appendix-c-sql-grammar) [ODBC プログラマーズリファレンス](/sql/odbc/reference/odbc-programmer-s-reference) 」の「SQL 文法」を参照して、構文に関する詳細情報を参照してください。

レコードセットオブジェクトは、カスタム SQL ステートメントを渡さない限り、レコードの選択に使用する SQL ステートメントを構築します。 この方法は、主に、メンバー関数の *lpszSQL* パラメーターで渡す値によって異なり `Open` ます。

SQL **SELECT** ステートメントの一般的な形式は次のとおりです。

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

レコードセットの SQL ステートメントに **DISTINCT** キーワードを追加する方法の1つとして、の最初の RFX 関数呼び出しにキーワードを埋め込む方法が `DoFieldExchange` あります。 次に例を示します。

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
> この手法は、読み取り専用として開かれたレコードセットでのみ使用してください。

## <a name="overriding-the-sql-statement"></a>SQL ステートメントのオーバーライド

次の表は、の *lpszSQL* パラメーターの可能性を示して `Open` います。 表にあるケースについては、次の表で説明します。

**LpszSQL パラメーターと結果の SQL 文字列**

|ケース|LpszSQL で渡されること|結果として得られる SELECT ステートメント|
|----------|------------------------------|------------------------------------|
|1|NULL|*テーブル名***から** の **[** *rfx-フィールドリスト*] の選択<br /><br /> `CRecordset::Open``GetDefaultSQL`を呼び出して、テーブル名を取得します。 結果の文字列は、が返す内容に応じて、2 ~ 5 のケースの1つです `GetDefaultSQL` 。|
|2|テーブル名|*テーブル名***から** の **[** *rfx-フィールドリスト*] の選択<br /><br /> フィールドリストは、の RFX ステートメントから取得され `DoFieldExchange` ます。 `m_strFilter`と `m_strSort` が空でない場合は、 **WHERE** 句、or 句、または **ORDER BY** 句を追加します。|
|番 \*|**Where** 句または **ORDER by** 句を含まない、完全な **SELECT** ステートメント|渡された。 `m_strFilter`と `m_strSort` が空でない場合は、 **WHERE** 句、or 句、または **ORDER BY** 句を追加します。|
|4/4 \*|**WHERE** および/または **order by** 句を含む完全な **SELECT** ステートメント|渡された。 `m_strFilter` またはを `m_strSort` 空のままにする必要があります。または、2つのフィルターまたは並べ替えステートメントが生成されます。|
|5/5 \*|ストアドプロシージャの呼び出し|渡された。|

\*`m_nFields` **SELECT** ステートメントで指定された列の数以下である必要があります。 **SELECT** ステートメントで指定された各列のデータ型は、対応する RFX 出力列のデータ型と同じである必要があります。

### <a name="case-1---lpszsql--null"></a>ケース 1 lpszSQL = NULL

レコードセットの選択は、 `GetDefaultSQL` がそれを呼び出すときの戻り値によって異なり `CRecordset::Open` ます。 ケース 2 ~ 5 では、使用可能な文字列が記述されています。

### <a name="case-2---lpszsql--a-table-name"></a>ケース 2 lpszSQL = テーブル名

レコードセットはレコードフィールドエクスチェンジ (RFX) を使用して、レコードセットクラスののオーバーライドに含まれる RFX 関数呼び出しで指定された列名から列リストを作成し `DoFieldExchange` ます。 ウィザードを使用してレコードセットクラスを宣言した場合、この例ではケース1と同じ結果が得られます (ウィザードで指定したのと同じテーブル名を渡した場合)。 クラスを記述するためにウィザードを使用しない場合は、SQL ステートメントを作成する最も簡単な方法はケース2です。

次の例では、MFC データベースアプリケーションからレコードを選択する SQL ステートメントを作成します。 フレームワークがメンバー関数を呼び出すと、 `GetDefaultSQL` 関数はテーブルの名前を返し `SECTION` ます。

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

フレームワークは、SQL **SELECT** ステートメントの列の名前を取得するために、 `DoFieldExchange` メンバー関数を呼び出します。

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

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Case 3 lpszSQL = a SELECT/FROM ステートメント

列リストは、RFX に依存して自動的に構築するのではなく、手動で指定します。 次のような場合に、この操作を行うことができます。

- **SELECT** の後に **DISTINCT** キーワードを指定する必要があります。

   列の一覧は、列の名前と型がに表示されている順序と一致している必要があり `DoFieldExchange` ます。

- `::SQLGetData`RFX に依存して列をバインドおよび取得するのではなく、ODBC 関数を使用して列の値を手動で取得する理由があります。

   たとえば、アプリケーションが配布された後に、アプリケーションの顧客がデータベーステーブルに追加された新しい列に対応することが必要になる場合があります。 これらの追加のフィールドデータメンバーを追加する必要があります。これは、ウィザードを使用してクラスを宣言した時点ではわかりませんでした。

   列の一覧は、列の名前と型がに表示されている順序と一致し、その後に手動でバインドされた列の名前と一致している必要があり `DoFieldExchange` ます。 詳細については、「 [レコードセット: データ列の動的なバインド (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。

- From 句で複数 **の** テーブルを指定してテーブルを結合する場合。

   詳細と例については、「 [レコードセット: 結合の実行 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)」を参照してください。

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>Case 4 lpszSQL = SELECT/FROM プラス WHERE and/or ORDER BY

すべての列の一覧 (の RFX 呼び出しに基づく `DoFieldExchange` )、テーブルの一覧、および **WHERE** 句と **order by** 句の内容を指定します。 **WHERE** 句または **ORDER BY** 句をこのように指定する場合は、and または or を使用しないで `m_strFilter` `m_strSort` ください。

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Case 5 lpszSQL = ストアドプロシージャ呼び出し

定義済みのクエリ (Microsoft SQL Server データベース内のストアドプロシージャなど) を呼び出す必要がある場合は、 *lpszSQL* に渡す文字列に **call** ステートメントを記述する必要があります。 ウィザードでは、定義済みのクエリを呼び出すためのレコードセットクラスの宣言はサポートされていません。 定義済みのクエリによってレコードが返されるわけではありません。

定義済みのクエリがレコードを返さない場合は、 `CDatabase` メンバー関数を `ExecuteSQL` 直接使用できます。 レコードを返す定義済みクエリの場合は、 `DoFieldExchange` プロシージャから返されるすべての列に対して、の RFX 呼び出しを手動で書き込む必要もあります。 RFX 呼び出しは、定義済みのクエリと同じ順序で同じ型を返す必要があります。 詳細については、「 [レコードセット: 定義済みクエリのクラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[SQL: SQL と C++ のデータ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
