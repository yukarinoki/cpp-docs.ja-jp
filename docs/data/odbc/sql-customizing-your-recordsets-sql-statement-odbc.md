---
title: 'SQL: レコード セットの SQL ステートメント (ODBC) のカスタマイズ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f385127d1b61e1453eb7a079963da727f82f1874
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: レコードセットの SQL ステートメントのカスタマイズ (ODBC)
このトピックでは、次の内容について説明します。  
  
-   フレームワークが SQL ステートメントを作成する方法  
  
-   SQL ステートメントをオーバーライドする方法  
  
> [!NOTE]
>  この情報は、MFC ODBC クラスに適用されます。 MFC DAO クラスを使用する場合は、"比較の Microsoft Jet データベース エンジン SQL と ANSI SQL"DAO ヘルプのトピックを参照してください。  
  
## <a name="sql-statement-construction"></a>SQL ステートメントの作成  
 レコード セットが、主に、SQL のレコードの選択**選択**ステートメントです。 オーバーライド元のバージョンのウィザードを使用して、クラスを宣言するときに書き込む、`GetDefaultSQL`次のようなメンバー関数 (レコード セット クラスと呼ばれる`CAuthors`)。  
  
```  
CString CAuthors::GetDefaultSQL()  
{  
    return "AUTHORS";  
}  
```  
  
 既定では、この上書きは、ウィザードで指定したテーブル名を返します。 例では、テーブル名は「作成者」 後で呼び出すと、レコード セットの**開く**メンバー関数は、**開く**構築、最終**選択**形式のステートメント。  
  
```  
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]   
       [ORDER BY m_strSort]  
```  
  
 ここで`table-name`呼び出すことによって取得`GetDefaultSQL`と`rfx-field-list`RFX 関数の呼び出しから取得した`DoFieldExchange`です。 これは、新機能を取得するか、**選択**ステートメントしない限り、オーバーライド元のバージョンで実行時に、パラメーターまたはフィルターで既定のステートメントを変更することもできます。 ただしです。  
  
> [!NOTE]
>  スペースが含まれています (または含まれている) する列名を指定する場合は、角かっこで囲んで、名前を囲む必要があります。 たとえば、名前「名」は"[First Name]"にする必要があります。  
  
 既定値をオーバーライドする**選択**ステートメントでは、文字列、完全なパス**選択**ステートメントを呼び出すとき**開いている**。 独自の既定の文字列を作成するには、代わりには、レコード セットは、指定した文字列を使用します。 置換ステートメントが含まれている場合、**場所**句内のフィルターを指定しない**か**ステートメントをフィルター処理し、必要がありますので 2 つです。 同様に、置換ステートメントが含まれている場合、 **ORDER BY**句で並べ替えを指定しない`m_strSort`ステートメントを 2 つで並べ替える必要がないようにします。  
  
> [!NOTE]
>  フィルターの (または、SQL ステートメントの他の部分) のリテラル文字列を使用する場合は、"quote"する必要があります (指定された区切り記号で囲みます)、DBMS に固有のリテラル プレフィックスを持つとリテラル文字列をこのようなサフィックス文字 (または文字)。  
  
 DBMS によって外部結合などの操作に対して特別な構文上の要件が発生することもあります。 ODBC 関数を使用して、DBMS のドライバーからこの情報を取得します。 たとえば、呼び出す **:: SQLGetTypeInfo**特定のデータ型の場合など**SQL_VARCHAR**を要求、 **LITERAL_PREFIX**と**LITERAL_SUFFIX**文字です。 データベースに依存しないコードを記述する場合で「付録 C を参照してください、 *ODBC SDK * * プログラマーズ リファレンス*構文の詳細については、MSDN ライブラリの CD にします。  
  
 レコード セット オブジェクトでは、カスタム SQL ステートメントを指定しないレコードの選択に使用される SQL ステートメントを構築します。 これを行う方法、主に依存に渡す値、`lpszSQL`のパラメーター、**開く**メンバー関数。  
  
 SQL の一般的な形式**選択**ステートメントは。  
  
```  
SELECT [ALL | DISTINCT] column-list FROM table-list  
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]  
```  
  
 追加する方法の 1 つ、 **DISTINCT** 、RFX 関数の最初の呼び出しに、キーワードを埋め込むには、レコード セットの SQL ステートメントにキーワード`DoFieldExchange`です。 例えば:  
  
```  
...  
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);  
...  
```  
  
> [!NOTE]
>  読み取り専用で開かれたレコード セットでのみ、この手法を使用します。  
  
## <a name="overriding-the-sql-statement"></a>SQL ステートメントをオーバーライドします。  
 次の表の可能性を示しています、`lpszSQL`パラメーターを**開く**です。 次の表に、テーブル内のケースを説明します。  
  
 **LpszSQL パラメーターおよび結果として得られる SQL 文字列**  
  
|Case|LpszSQL を渡します|結果の SELECT ステートメント|  
|----------|------------------------------|------------------------------------|  
|1|**NULL**|**選択** *rfx フィールド リスト* **FROM** *テーブル名*<br /><br /> `CRecordset::Open` 呼び出し`GetDefaultSQL`テーブル名を取得します。 ケース 2. ~ 5. 内容に合わせてのいずれかの結果の文字列は`GetDefaultSQL`を返します。|  
|2|テーブル名|**選択** *rfx フィールド リスト* **FROM** *テーブル名*<br /><br /> フィールドの一覧内の RFX ステートメントから取得されます`DoFieldExchange`です。 場合**か**と`m_strSort`空ではない、追加、**場所**や**ORDER BY**句。|  
|3 *|完全な**選択**ステートメントがない、**場所**または**ORDER BY**句|渡されます。 場合**か**と`m_strSort`空ではない、追加、**場所**や**ORDER BY**句。|  
|4 *|完全な**選択**ステートメントを**場所**や**ORDER BY**句|渡されます。 **か**や`m_strSort`必要がありますまま空、または 2 つのフィルターや並べ替えステートメントが生成されます。|  
|5 *|ストアド プロシージャの呼び出し|渡されます。|  
  
 \* `m_nFields` 指定された列の数以下である必要があります、**選択**ステートメントです。 指定された各列のデータ型、**選択**ステートメントには、RFX の対応する出力列のデータ型と同じである必要があります。  
  
### <a name="case-1---lpszsql--null"></a>ケース 1 lpszSQL = NULL  
 レコード セットの選択は、新機能に依存`GetDefaultSQL`時に返す`CRecordset::Open`はそれを呼び出します。 2 ~ 5 の場合は、可能性のある文字列について説明します。  
  
### <a name="case-2---lpszsql--a-table-name"></a>ケース 2 テーブル名を =  
 レコード セットでは、レコード フィールド エクス (チェンジ RFX) を使用して、関数、RFX では、レコード セット クラスのオーバーライドで指定された列名から列の一覧を構築`DoFieldExchange`です。 レコード セット クラスを宣言するウィザードを使用して (ウィザードで指定した同じテーブル名を渡す) が提供できる、この場合は 1 の場合と同じ結果がします。 クラスを作成するウィザードを使用しない場合は、SQL ステートメントを作成する最も簡単な方法はケース 2 です。  
  
 次の例では、MFC データベース アプリケーションからレコードを選択する SQL ステートメントを構築します。 フレームワークを呼び出すと、`GetDefaultSQL`メンバー関数の場合、関数が、テーブルの名前を返します`SECTION`です。  
  
```  
CString CEnrollSet::GetDefaultSQL()  
{  
    return "SECTION";  
}  
```  
  
 SQL の列の名前を取得する**選択**ステートメントでは、フレームワークによって、`DoFieldExchange`メンバー関数。  
  
```  
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
  
 完了すると、SQL ステートメントは、次のようになります。  
  
```  
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo   
    FROM SECTION  
```  
  
### <a name="case-3---lpszsql--a-selectfrom-statement"></a>ケース 3 = SELECT ステートメントから/  
 指定する列の一覧を手動で自動的に構築する RFX ではなく。 場合に、このを実行する可能性があります。  
  
-   指定する、 **DISTINCT**キーワード次**選択**です。  
  
     列の一覧合致していなければならない列名と同じ順序での型はで示されている`DoFieldExchange`です。  
  
-   手動で ODBC 関数を使用して列の値を取得する理由がある **:: SQLGetData** RFX をバインドし、列を取得するのではなくです。  
  
     たとえば、アプリケーションが分散された後、データベース テーブルに、アプリケーションの顧客が追加された新しい列に対応する可能性があります、です。 これらがウィザードを使用して、クラスを宣言したときに知られていない追加のフィールド データ メンバーを追加する必要があります。  
  
     列の一覧合致していなければならない列名と同じ順序での型はで示されている`DoFieldExchange`」と入力し、手動でバインドされた列の名前。 詳細については、次を参照してください。[レコード セット: データ列を動的に結びつける (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)です。  
  
-   複数のテーブルを指定してテーブルを結合する、 **FROM**句。  
  
     情報と例では、次を参照してください。[レコード セット: 結合 (Odbc)](../../data/odbc/recordset-performing-a-join-odbc.md)です。  
  
### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>ケース 4 = 選択/から Plus、および ORDER BY  
 すべてのものを指定する: 列の一覧 (RFX 呼び出しに基づいて`DoFieldExchange`)、テーブルの一覧とのコンテンツ、**場所**や、 **ORDER BY**句。 指定した場合、**場所**や**ORDER BY**句この方法は使用しないでください**か**や`m_strSort`です。  
  
### <a name="case-5---lpszsql--a-stored-procedure-call"></a>ケース 5 = ストアド プロシージャ コール  
 記述する必要があります (Microsoft SQL Server データベース内のストアド プロシージャ) などの定義済みのクエリを呼び出す必要がある場合、**呼び出す**に渡す文字列内のステートメント`lpszSQL`です。 ウィザードは、定義済みクエリを呼び出すためのレコード セット クラスの宣言をサポートしていません。 すべての定義済みクエリは、レコードを返します。  
  
 使用することができます、定義済みのクエリではレコードが返されない場合、`CDatabase`メンバー関数は、`ExecuteSQL`直接です。 レコードが返されるは、定義済みクエリの必要がありますも手動で記述する、rfx 関数の呼び出し`DoFieldExchange`プロシージャは、列を返します。 RFX 呼び出しは、同じ順序で表示され、定義済みのクエリとして、同じ型を返す必要があります。 詳細については、次を参照してください。[レコード セット: 定義済みクエリ (ODBC) のクラスの宣言](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [SQL: SQL と C++ のデータ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)   
 [SQL: SQL の直接呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
