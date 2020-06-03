---
title: 'トランザクション: レコードセットからのトランザクション実行 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 45ae414c318376b2c4d787498e9a288a0037af83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358096"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>トランザクション: レコードセットからのトランザクション実行 (ODBC)

このトピックでは、レコードセットでトランザクションを実行する方法について説明します。

> [!NOTE]
> 1 レベルのトランザクションのみがサポートされます。トランザクションをネストすることはできません。

#### <a name="to-perform-a-transaction-in-a-recordset"></a>レコードセットでトランザクションを実行するには

1. オブジェクトの`CDatabase`メンバー関数を`BeginTrans`呼び出します。

1. バルク行フェッチを実装していない場合は、同じデータベースの`AddNew/Update` `Edit/Update`1`Delete`つ以上のレコードセット オブジェクトの 、、および メンバー関数を必要な回数だけ呼び出します。 詳細については、「[レコードセット : レコードの追加、更新、および削除 (ODBC)」](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)を参照してください。 バルク行フェッチを実装している場合は、データ ソースを更新する独自の関数を記述する必要があります。

1. 最後に、オブジェクト`CDatabase`のメンバー関数`CommitTrans`を呼び出します。 いずれかの更新でエラーが発生した場合、または変更を取り消す場合は、その`Rollback`メンバー関数を呼び出します。

次の例では、2 つのレコードセットを使用して、学校登録データベースから学生の登録を削除し、学生が登録されているすべてのクラスから生徒を削除します。 両方の`Delete`レコードセットの呼び出しは成功する必要があるため、トランザクションが必要です。 `m_dbStudentReg`この例では、データ ソースに既に接続されている`CDatabase`型のメンバー変数、およびレコードセット クラス`CEnrollmentSet`と`CStudentSet`が存在することを前提としています。 変数`strStudentID`には、ユーザーから取得した値が含まれます。

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
> 呼`BeginTrans`び出し`CommitTrans`を`Rollback`行わずに再度呼び出すか、またはエラーです。

## <a name="see-also"></a>関連項目

[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[トランザクション: トランザクションが更新処理に与える影響 (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[クラス](../../mfc/reference/cdatabase-class.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)
