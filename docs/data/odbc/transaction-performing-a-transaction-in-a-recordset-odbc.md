---
title: 'トランザクション: レコードセットからのトランザクション実行 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 94177a27a1f99a8c9c37b7fce3f697fd0088b7c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212590"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>トランザクション: レコードセットからのトランザクション実行 (ODBC)

このトピックでは、レコードセットでトランザクションを実行する方法について説明します。

> [!NOTE]
>  サポートされているトランザクションのレベルは1つだけです。トランザクションを入れ子にすることはできません。

#### <a name="to-perform-a-transaction-in-a-recordset"></a>レコードセットでトランザクションを実行するには

1. `CDatabase` オブジェクトの `BeginTrans` メンバー関数を呼び出します。

1. バルク行フェッチを実装していない場合は、同じデータベースの1つ以上のレコードセットオブジェクトの `AddNew/Update`、`Edit/Update`、および `Delete` メンバー関数を、必要に応じて何度でも呼び出します。 詳細については、「レコード[セット: レコードの追加、更新、および削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)」を参照してください。 バルク行フェッチを実装している場合は、独自の関数を記述してデータソースを更新する必要があります。

1. 最後に、`CDatabase` オブジェクトの `CommitTrans` メンバー関数を呼び出します。 いずれかの更新でエラーが発生した場合、または変更を取り消す場合は、`Rollback` メンバー関数を呼び出します。

次の例では、2つのレコードセットを使用して、学生の登録を学校登録データベースから削除し、学生が登録されているすべてのクラスから学生を削除します。 両方のレコードセットの `Delete` の呼び出しが成功する必要があるため、トランザクションが必要です。 この例では、`m_dbStudentReg`が存在すること、`CDatabase` 型のメンバー変数が既にデータソースに接続されていること、およびレコードセットクラス `CEnrollmentSet` および `CStudentSet`を使用していることを前提としています。 `strStudentID` 変数には、ユーザーから取得した値が含まれます。

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
>  `CommitTrans` または `Rollback` を呼び出さずに `BeginTrans` を再度呼び出すと、エラーになります。

## <a name="see-also"></a>参照

[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[トランザクション: トランザクションが更新処理に与える影響 (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[CDatabase クラス](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)
