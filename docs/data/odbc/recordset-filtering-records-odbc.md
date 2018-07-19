---
title: 'レコード セット: レコード (ODBC) のフィルター処理 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4b4860726fa77d7b852290d8ea4680fe1bbbd86f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091804"
---
# <a name="recordset-filtering-records-odbc"></a>レコードセット: レコードのフィルター処理 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、使用可能なレコードの特定のサブセットのみを選択するように、レコード セットをフィルター処理する方法について説明します。 たとえば、MATH101 などの特定の一連のクラスのセクションだけを選択することができます。 SQL の内容によって定義された検索条件にフィルターが**場所**句。 フレームワークは、レコード セットの SQL ステートメントに追加するとき、**場所**句は、選択範囲を制限します。  
  
 呼び出す前に、オブジェクトを構築した後は、レコード セット オブジェクトのフィルターを確立する必要があります、**開く**メンバー関数 (を呼び出す前に、または、 **Requery**既存のレコード セットのメンバー関数オブジェクトの**開く**メンバー関数)。  
  
#### <a name="to-specify-a-filter-for-a-recordset-object"></a>レコード セット オブジェクトのフィルターを指定するには  
  
1.  新しいレコード セット オブジェクトを構築 (を呼び出す準備または**Requery**既存のオブジェクト)。  
  
2.  オブジェクトの値を設定[か](../../mfc/reference/crecordset-class.md#m_strfilter)データ メンバーです。  
  
     このフィルターでは、SQL の内容を表す null で終わる文字列**場所**句がキーワードではなく**場所**です。 たとえば、次のように使用します。  
  
    ```  
    m_pSet->m_strFilter = "CourseID = 'MATH101'";  
    ```  
  
     not  
  
    ```  
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";  
    ```  
  
    > [!NOTE]
    >  リテラル文字列"MATH101"には、上記の 1 つの引用符が表示されます。 ODBC SQL の仕様では、単一引用符は、文字の文字列リテラルを表すために使用されます。 このような状況で、DBMS の引用符の要件については、ODBC ドライバーのマニュアルを確認してください。 この構文についても説明さらに、このトピックの最後の近くです。  
  
3.  たとえば、並べ替え順序やロック モードは、パラメーターなどの必要なその他のオプションを設定します。 パラメーターを指定することは、特に便利です。 フィルターをパラメーター化の詳細については、次を参照してください。[レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)です。  
  
4.  呼び出す**開く**に新しいオブジェクト (または**Requery**既に開かれているオブジェクトの)。  
  
> [!TIP]
>  パラメーターを使用して、フィルターでは、レコードを取得するための最も効率的な方法があります。  
  
> [!TIP]
>  レコード セットのフィルターが適しています。[への参加](../../data/odbc/recordset-performing-a-join-odbc.md)テーブルを使用する[パラメーター](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)情報を取得または実行時に計算を基にします。  
  
 レコード セットは、指定した検索条件を満たすレコードだけを選択します。 たとえば、コース フィルターを指定する前に説明した (変数を想定して`strCourseID`に設定されて、たとえば、"MATH101") を次の操作します。  
  
```  
// Using the recordset pointed to by m_pSet  
  
// Set the filter  
m_pSet->m_strFilter = "CourseID = " + strCourseID;   
  
// Run the query with the filter in place  
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )  
  
// Use the recordset  
```  
  
 レコード セットには、MATH101 のクラスのセクションではすべてのレコードが含まれています。  
  
 文字列変数を使用して、上記の例で、フィルター文字列を設定した方法に注意してください。 これは、一般的な用途です。 コース ID のリテラル値 100 を指定するとしますが、 次のコードは、リテラル値で正しくフィルター文字列を設定する方法を示しています。  
  
```  
m_strFilter = "StudentID = '100'";   // correct  
```  
  
 単一引用符の使用に注意してください。フィルター文字列を直接設定する場合、フィルター文字列は**いない**:  
  
```  
m_strFilter = "StudentID = 100";   // incorrect for some drivers  
```  
  
 上記の引用符、ODBC 仕様に準拠しているが、一部の Dbms が他の引用符文字を必要があります。 詳細については、次を参照してください。 [SQL: をカスタマイズするレコード セットの SQL ステートメント (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)です。  
  
> [!NOTE]
>  独自の SQL 文字列を渡すことによって、レコード セットの既定の SQL 文字列を上書きする場合**開く**、カスタム文字列がある場合にフィルターを設定しないでください、**場所**句。 既定の SQL をオーバーライドする方法の詳細については、次を参照してください。 [SQL: をカスタマイズするレコード セットの SQL ステートメント (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)   
 [: レコード選択レコードのしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [: レコード更新レコードのしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)