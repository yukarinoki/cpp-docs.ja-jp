---
title: トランザクション (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
ms.openlocfilehash: 56629f8c5ff74aff4e0df589cda1e7b988fb5fd3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376415"
---
# <a name="transaction-odbc"></a>トランザクション (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

トランザクションは、[データ ソース](../../data/odbc/data-source-odbc.md)に対する一連の更新をグループ化する方法です。 トランザクションを使用しない場合、データ ソースへの変更は、要求に応じてコミットされるのではなく、自動的にコミットされます。

> [!NOTE]
> すべての ODBC データベース ドライバがトランザクションをサポートしているわけではありません。 CDatabase`CanTransact`または[CRecordset](../../mfc/reference/cdatabase-class.md)オブジェクト[CRecordset](../../mfc/reference/crecordset-class.md)のメンバー関数を呼び出して、ドライバーが特定のデータベースのトランザクションをサポートしているかどうかを確認します。 データ`CanTransact`ソースが完全なトランザクションサポートを提供しているかどうかは示されないことに注意してください。 また、オープンオブジェクト`CDatabase::GetCursorCommitBehavior`に`CDatabase::GetCursorRollbackBehavior`対`CommitTrans`する`Rollback`トランザクションの影響を確認するために、呼び出`CRecordset`しと後および後で確認する必要があります。

`CRecordset`オブジェクト`AddNew`の メンバー`Edit`関数および メンバー関数を呼び出すと、 を`Update`呼び出すとすぐにデータ ソースに影響します。 `Delete`呼び出しもすぐに有効になります。 これに対し、実行されるが明示的に呼び`AddNew`出`Edit``Update``Delete``CommitTrans`すまでコミットされない、 、 、 、 、 に対する複数の呼び出しから成るトランザクションを使用できます。 トランザクションを確立することで、ロールバック機能を維持しながら、一連の呼び出しを実行できます。 クリティカル リソースが使用できない場合や、トランザクション全体が完了しない状況が発生した場合は、トランザクションをコミットせずにロールバックできます。 その場合、トランザクションに属する変更はデータ ソースに影響しません。

> [!NOTE]
> 現在、バルク`CRecordset`行フェッチを実装している場合、クラスはデータ ソースの更新をサポートしていません。 つまり`AddNew`、 、 `Edit`、 、`Delete`または`Update`に呼び出しを行うことはできません。 ただし、更新を実行する独自の関数を作成し、特定のトランザクション内でそれらの関数を呼び出すことができます。 バルク行フェッチの詳細については、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

> [!NOTE]
> レコード`CDatabase`セットに影響を与えるだけでなく、オブジェクトに関連付けられた ODBC HDBC またはその**HDBC**に基づく ODBC **HSTMT**を**HDBC**使用する限り、直接実行する SQL ステートメントにトランザクションが影響します。

トランザクションは、複数のレコードを同時に更新する必要がある場合に特に便利です。 この場合、最後の更新が行われる前に例外がスローされた場合など、トランザクションが半分完了しないようにします。 このような更新をトランザクションにグループ化すると、変更から回復 (ロールバック) が可能になり、レコードがトランザクション前の状態に戻ります。 たとえば、銀行が口座 A から口座 B に送金する場合、A からの出金と B へのデポジットの両方が資金を正しく処理するために成功するか、トランザクション全体が失敗する必要があります。

データベース クラスでは、オブジェクトを介して`CDatabase`トランザクションを実行します。 オブジェクト`CDatabase`はデータ ソースへの接続を表し、そのオブジェクトに関連付けられた 1`CDatabase`つ以上のレコードセットが、レコードセット メンバー関数を通じてデータベースのテーブルを操作します。

> [!NOTE]
> 1 レベルのトランザクションのみがサポートされます。 トランザクションを入れ子にしたり、複数のデータベース オブジェクトにまたがることはできません。

次のトピックでは、トランザクションの実行方法について詳しく説明します。

- [トランザクション: レコードセットからのトランザクション実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [トランザクション: トランザクションが更新処理に与える影響 (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>関連項目

[データベース接続を開く (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
