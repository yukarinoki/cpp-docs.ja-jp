---
description: '詳細情報: Transaction (ODBC)'
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
ms.openlocfilehash: a7b769c37b58b34433939a18cb0dccf5fb4a798d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333864"
---
# <a name="transaction-odbc"></a>トランザクション (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

トランザクションとは、1つの [データソース](../../data/odbc/data-source-odbc.md) に対する一連の更新をグループ化またはバッチ処理することで、すべてが一度にコミットされるか、トランザクションをロールバックした場合にはコミットされないようにすることです。 トランザクションを使用しない場合、データソースへの変更は、要求時にコミットされるのではなく、自動的にコミットされます。

> [!NOTE]
> すべての ODBC データベースドライバーでトランザクションがサポートされるわけではありません。 `CanTransact` [CDatabase](../../mfc/reference/cdatabase-class.md)または[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトのメンバー関数を呼び出して、ドライバーが特定のデータベースのトランザクションをサポートしているかどうかを判断します。 で `CanTransact` は、データソースが完全なトランザクションをサポートしているかどうかはわかりません。 また、との `CDatabase::GetCursorCommitBehavior` 後にとを呼び出して、 `CDatabase::GetCursorRollbackBehavior` 開いて `CommitTrans` `Rollback` いるオブジェクトに対するトランザクションの効果を確認する必要があり `CRecordset` ます。

`AddNew`オブジェクトのおよびメンバー関数の呼び出しは、を `Edit` `CRecordset` 呼び出すとすぐにデータソースに影響し `Update` ます。 `Delete` 呼び出しもすぐに有効になります。 これに対して、、、、およびの複数の呼び出しで構成されるトランザクションを使用できます `AddNew` `Edit` `Update` `Delete` 。これは、を明示的に呼び出すまでは実行されますが、コミットされません `CommitTrans` 。 トランザクションを確立することによって、そのような呼び出しをロールバックする機能を維持したまま、一連の呼び出しを実行できます。 重要なリソースが使用できない場合、または他の条件によってトランザクション全体が完了しない場合は、トランザクションをコミットする代わりに、トランザクションをロールバックできます。 この場合、トランザクションに属している変更がデータソースに影響を与えることはありません。

> [!NOTE]
> 現時点では、 `CRecordset` バルク行フェッチを実装している場合、クラスはデータソースへの更新をサポートしていません。 つまり、、、 `AddNew` `Edit` `Delete` 、またはを呼び出すことはできません `Update` 。 ただし、独自の関数を記述して更新を実行し、特定のトランザクション内でそれらの関数を呼び出すことができます。 バルク行フェッチの詳細については、「レコード [セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

> [!NOTE]
> トランザクションは、レコードセットに影響を与えるだけでなく、  `CDatabase` オブジェクトやその **HDBC** に基づく odbc **HSTMT** に関連付けられている odbc HDBC を使用している限り、直接実行する SQL ステートメントに影響を与えます。

トランザクションは、複数のレコードを同時に更新する必要がある場合に特に便利です。 この場合は、最後の更新が行われる前に例外がスローされた場合に発生する可能性のある、半分の完了したトランザクションを回避する必要があります。 このような更新をトランザクションにグループ化すると、変更からの復旧 (ロールバック) が可能になり、レコードを事前トランザクション状態に戻すことができます。 たとえば、銀行が口座 A から口座 B に金額を転送する場合、資金を正しく処理するためにからの引き出しと B への預入は両方とも成功する必要があります。成功しない場合は、トランザクション全体が失敗します。

データベースクラスでは、オブジェクトを使用してトランザクションを実行し `CDatabase` ます。 `CDatabase`オブジェクトはデータソースへの接続を表し、そのオブジェクトに関連付けられた1つ以上のレコードセットは、 `CDatabase` レコードセットのメンバー関数を使用してデータベースのテーブルを操作します。

> [!NOTE]
> サポートされているトランザクションのレベルは1つだけです。 トランザクションを入れ子にすることはできません。また、トランザクションを複数のデータベースオブジェクトにまたがることもできません。

次のトピックでは、トランザクションの実行方法の詳細について説明します。

- [トランザクション: レコードセットでのトランザクションの実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [トランザクション: トランザクションが更新に与える影響 (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>関連項目

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
