---
title: 'トランザクション: レコード セット (ODBC) からのトランザクションの実行 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d7cae3b05c20736a2e271b574569bcac4d5cdc7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094606"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>トランザクション: レコードセットからのトランザクション実行 (ODBC)
このトピックでは、レコード セットで、トランザクションを実行する方法について説明します。  
  
> [!NOTE]
>  トランザクションの 1 つだけのレベルがサポートされています。トランザクションを入れ子にすることはできません。  
  
#### <a name="to-perform-a-transaction-in-a-recordset"></a>レコード セットのトランザクションを実行するには  
  
1.  呼び出す、`CDatabase`オブジェクトの**BeginTrans**メンバー関数。  
  
2.  バルク行フェッチを実装できませんが、場合、 **AddNew/更新**、**編集/更新**、および**削除**の同じ 1 つまたは複数のレコード セット オブジェクトのメンバー関数必要に応じて何度としてデータベースです。 詳細については、次を参照してください。[レコード セット: 追加、更新、およびレコードの削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)です。 バルク行フェッチを実装している場合は、データ ソースを更新する、独自の関数を記述する必要があります。  
  
3.  最後を呼び出して、`CDatabase`オブジェクトの**CommitTrans**メンバー関数。 呼び出すか、更新プログラムのいずれかでエラーが発生した変更をキャンセルする場合、その**ロールバック**メンバー関数。  
  
 次の例では、次の 2 つのレコード セットを使用して、受講者が登録されているすべてのクラスから受講者を削除する、学校の登録情報データベースからスチューデントの登録を削除します。 **削除**両方のレコード セットでの呼び出しが成功する必要があります、トランザクションが必要です。 例では、ことを想定の`m_dbStudentReg`、型のメンバー変数`CDatabase`データ ソースとレコード セット クラスに既に接続されている`CEnrollmentSet`と`CStudentSet`です。 `strStudentID`変数には、ユーザーから取得した値が含まれています。  
  
```  
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )  
{  
    // remove student from all the classes  
    // the student is enrolled in  
  
    if ( !m_dbStudentReg.BeginTrans( ) )  
        return FALSE;  
  
    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);  
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    CStudentSet rsStudentSet(&m_dbStudentReg);  
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsStudentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    TRY  
    {  
        while ( !rsEnrollmentSet.IsEOF( ) )  
        {  
            rsEnrollmentSet.Delete( );  
            rsEnrollmentSet.MoveNext( );  
        }  
  
        // delete the student record  
        rsStudentSet.Delete( );  
  
        m_dbStudentReg.CommitTrans( );  
    }  
  
    CATCH_ALL(e)  
    {  
        m_dbStudentReg.Rollback( );  
        return FALSE;  
    }  
    END_CATCH_ALL  
  
    rsEnrollmentSet.Close( );  
    rsStudentSet.Close( );  
  
    return TRUE;  
  
}  
```  
  
> [!NOTE]
>  呼び出す**BeginTrans**呼び出さずにもう一度**CommitTrans**または**ロールバック**エラーが発生します。  
  
## <a name="see-also"></a>関連項目  
 [トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)   
 [トランザクション: トランザクションに与える影響 (ODBC) の更新](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)