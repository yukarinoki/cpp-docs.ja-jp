---
title: 'トランザクション: レコード セット (ODBC) からのトランザクションの実行 |Microsoft Docs'
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
ms.openlocfilehash: 5d73b7c45223c029451f300e495915eb15b0a956
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103936"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>トランザクション: レコードセットからのトランザクション実行 (ODBC)

このトピックでは、レコード セットのトランザクションを実行する方法について説明します。  
  
> [!NOTE]
>  トランザクションの 1 つだけのレベルがサポートされています。トランザクションを入れ子にすることはできません。  
  
#### <a name="to-perform-a-transaction-in-a-recordset"></a>レコード セットのトランザクションを実行するには  
  
1. 呼び出す、`CDatabase`オブジェクトの`BeginTrans`メンバー関数。  
  
1. バルク行フェッチを実装しない場合、 `AddNew/Update`、 `Edit/Update`、および`Delete`必要な回数と同じデータベースの 1 つまたは複数のレコード セット オブジェクトのメンバー関数。 詳細については、次を参照してください。[レコード セット: 追加、更新、およびレコードの削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)します。 バルク行フェッチを実装している場合は、データ ソースを更新する、独自の関数を記述する必要があります。  
  
1. 最後に、呼び出し、`CDatabase`オブジェクトの`CommitTrans`メンバー関数。 呼び出す場合、更新プログラムのいずれかでエラーが発生したまたは変更をキャンセルする場合、その`Rollback`メンバー関数。  
  
次の例では、2 つのレコード セットを使用して、生徒が登録されているすべてのクラスから受講者を削除する、学校の登録情報データベースから学生の登録を削除します。 `Delete`両方のレコード セットでの呼び出しが成功する必要があります、トランザクションが必要です。 例では、ことを想定の`m_dbStudentReg`、型のメンバー変数`CDatabase`、データ ソースとレコード セット クラスに既に接続されている`CEnrollmentSet`と`CStudentSet`します。 `strStudentID`変数には、ユーザーから取得した値が含まれています。  
  
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
>  呼び出す`BeginTrans`呼び出さずにもう一度`CommitTrans`または`Rollback`エラーが発生します。  
  
## <a name="see-also"></a>関連項目  

[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[トランザクション: トランザクションが更新処理に与える影響 (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[CDatabase クラス](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)