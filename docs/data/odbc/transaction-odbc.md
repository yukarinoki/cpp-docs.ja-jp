---
title: トランザクション (ODBC) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3acd47746d3a920b679fb5509c34e5978ad43eed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094027"
---
# <a name="transaction-odbc"></a>トランザクション (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 トランザクションは、グループ、または一連の更新をバッチ処理する方法、[データソース](../../data/odbc/data-source-odbc.md)すべてが 1 回にコミットされるかは、トランザクションをロールバックするようにします。 トランザクションを使用しない場合、データ ソースへの変更は、要求時にコミットされるのではなく、自動的にコミットされます。  
  
> [!NOTE]
>  すべての ODBC データベース ドライバーでは、トランザクションをサポートします。 呼び出す、`CanTransact`のメンバー関数、 [CDatabase](../../mfc/reference/cdatabase-class.md)または[CRecordset](../../mfc/reference/crecordset-class.md)ドライバーが指定されたデータベースのトランザクションをサポートするかどうかを確認するオブジェクト。 なお`CanTransact`が決まるわけでは、データ ソースが完全なトランザクションのサポートを提供するかどうか。 呼び出す必要があります`CDatabase::GetCursorCommitBehavior`と`CDatabase::GetCursorRollbackBehavior`後**CommitTrans**と**ロールバック**開くときに、トランザクションの結果を確認する`CRecordset`オブジェクト。  
  
 呼び出し、`AddNew`と**編集**のメンバー関数は、`CRecordset`オブジェクトのデータ ソースを呼び出すと即座に影響**更新**です。 **削除**呼び出しもすぐに有効です。 複数回呼び出すので構成されるトランザクションを使用する一方、 `AddNew`、**編集**、**更新**、および**削除**、これは実行しますが、までコミットされていません。呼び出す**CommitTrans**明示的にします。 トランザクションを確立してにロールバックする機能を維持したまま、一連のような呼び出しを実行できます。 重要なリソースが利用できない、またはその他の条件により、トランザクション全体を完了できなく、することができますトランザクションをロールバックそのコミットの代わりにします。 その場合は、データ ソースのどのトランザクションに属する変更に影響します。  
  
> [!NOTE]
>  クラスの現在のところ、`CRecordset`バルク行フェッチを実装している場合は、データ ソースへの更新をサポートしません。 つまりへの呼び出しを行うことはできません`AddNew`、**編集**、**削除**、または**更新**です。 ただし、することができます関数を記述する独自の更新を実行し、特定のトランザクション内でこれらの関数を呼び出します。 バルク行フェッチの詳細については、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
> [!NOTE]
>  レコード セットに影響を与える、他のトランザクションに影響を与える、ODBC を使用する限り、直接実行する SQL ステートメント**HDBC**に関連付けられている、`CDatabase`オブジェクトまたは ODBC **HSTMT**に基づいて**HDBC**です。  
  
 トランザクションは、同時に更新する必要がある複数のレコードが存在する場合に特に便利です。 ここでは、最後の更新が行われる前に、例外がスローされた場合に発生する可能性がありますなど半分完了トランザクション、されないようにします。 このような更新プログラムをトランザクションにグループ化、変更からの回復 (ロールバック) でき、状態に戻す、レコードを返します。 たとえば、銀行引き落とし口座 A から口座 B、両方、資金を正しく処理する B に A、預金を引き出しが成功する必要がありますかトランザクション全体が失敗する必要があります。  
  
 データベース クラスで使用したトランザクションを実行して`CDatabase`オブジェクト。 A`CDatabase`オブジェクト データ ソースへの接続を表し、1 つまたは複数のレコード セットに関連付けられている`CDatabase`オブジェクトは、レコード セットのメンバー関数を使用して、データベースのテーブルを操作します。  
  
> [!NOTE]
>  トランザクションの 1 つだけのレベルはサポートされています。 トランザクションを入れ子にすることはできません。 また、トランザクションが複数のデータベース オブジェクトにまたがることができます。  
  
 次のトピックでは、トランザクションの実行方法の詳細についてを説明します。  
  
-   [トランザクション: レコードセットからのトランザクション実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)  
  
-   [トランザクション: トランザクションが更新処理に与える影響 (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)  
  
## <a name="see-also"></a>関連項目  
 [ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)