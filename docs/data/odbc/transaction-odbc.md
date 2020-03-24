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
ms.openlocfilehash: 49fc0e244dd4f63bd7a69d963ff2a9fbc00ddb6c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212603"
---
# <a name="transaction-odbc"></a>トランザクション (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

トランザクションとは、1つの[データソース](../../data/odbc/data-source-odbc.md)に対する一連の更新をグループ化またはバッチ処理することで、すべてが一度にコミットされるか、トランザクションをロールバックした場合にはコミットされないようにすることです。 トランザクションを使用しない場合、データソースへの変更は、要求時にコミットされるのではなく、自動的にコミットされます。

> [!NOTE]
>  すべての ODBC データベースドライバーでトランザクションがサポートされるわけではありません。 [CDatabase](../../mfc/reference/cdatabase-class.md)または[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトの `CanTransact` メンバー関数を呼び出して、ドライバーが特定のデータベースのトランザクションをサポートしているかどうかを判断します。 `CanTransact` では、データソースが完全なトランザクションをサポートしているかどうかはわかりません。 また、`CommitTrans` と `Rollback` の後に `CDatabase::GetCursorCommitBehavior` `CDatabase::GetCursorRollbackBehavior` を呼び出して、開いている `CRecordset` オブジェクトでのトランザクションの効果を確認する必要があります。

`CRecordset` オブジェクトの `AddNew` および `Edit` メンバー関数の呼び出しは、`Update`を呼び出すとすぐにデータソースに影響します。 `Delete` の呼び出しもすぐに有効になります。 これに対して、`AddNew`、`Edit`、`Update`、および `Delete`への複数の呼び出しで構成されるトランザクションを使用できます。これは実行されますが、明示的に `CommitTrans` を呼び出すまではコミットされません。 トランザクションを確立することによって、そのような呼び出しをロールバックする機能を維持したまま、一連の呼び出しを実行できます。 重要なリソースが使用できない場合、または他の条件によってトランザクション全体が完了しない場合は、トランザクションをコミットする代わりに、トランザクションをロールバックできます。 この場合、トランザクションに属している変更がデータソースに影響を与えることはありません。

> [!NOTE]
>  現時点では、バルク行フェッチを実装している場合、クラス `CRecordset` はデータソースへの更新をサポートしていません。 つまり、`AddNew`、`Edit`、`Delete`、または `Update`を呼び出すことはできません。 ただし、独自の関数を記述して更新を実行し、特定のトランザクション内でそれらの関数を呼び出すことができます。 バルク行フェッチの詳細については、「レコード[セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

> [!NOTE]
>  トランザクションは、レコードセットに影響を与えるだけでなく、`CDatabase` オブジェクトに関連付けられた ODBC **HDBC** 、またはその**HDBC**に基づく odbc **HSTMT**を使用している限り、直接実行する SQL ステートメントに影響を与えます。

トランザクションは、複数のレコードを同時に更新する必要がある場合に特に便利です。 この場合は、最後の更新が行われる前に例外がスローされた場合に発生する可能性のある、半分の完了したトランザクションを回避する必要があります。 このような更新をトランザクションにグループ化すると、変更からの復旧 (ロールバック) が可能になり、レコードを事前トランザクション状態に戻すことができます。 たとえば、銀行が口座 A から口座 B に金額を転送する場合、資金を正しく処理するためにからの引き出しと B への預入は両方とも成功する必要があります。成功しない場合は、トランザクション全体が失敗します。

データベースクラスでは、`CDatabase` のオブジェクトを使用してトランザクションを実行します。 `CDatabase` オブジェクトは、データソースへの接続を表し、その `CDatabase` オブジェクトに関連付けられた1つ以上のレコードセットは、レコードセットのメンバー関数によってデータベースのテーブルを操作します。

> [!NOTE]
>  サポートされているトランザクションのレベルは1つだけです。 トランザクションを入れ子にすることはできません。また、トランザクションを複数のデータベースオブジェクトにまたがることもできません。

次のトピックでは、トランザクションの実行方法の詳細について説明します。

- [トランザクション: レコードセットからのトランザクション実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [トランザクション: トランザクションが更新処理に与える影響 (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>参照

[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)
