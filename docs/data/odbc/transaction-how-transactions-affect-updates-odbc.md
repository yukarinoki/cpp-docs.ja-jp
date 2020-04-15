---
title: 'トランザクション: トランザクションが更新処理に与える影響 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: 8a87176ecb20beaf46583e1190b0ad458d508b31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376432"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>トランザクション: トランザクションが更新処理に与える影響 (ODBC)

[データ ソース](../../data/odbc/data-source-odbc.md)への更新は、トランザクション中に編集バッファー (トランザクションの外部で使用されるのと同じ方法) を使用して管理されます。 レコードセットのフィールド データ メンバは、現在のレコードを含む編集バッファとして機能します`AddNew``Edit`。 操作中`Delete`、現在のレコードはトランザクション内でバックアップされません。 エディット バッファーの詳細と更新プログラムが現在のレコードを格納する方法については、「[レコードセット : レコード更新の方法 (ODBC)」](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)を参照してください。

> [!NOTE]
> バルク行フェッチを実装している場合は、 、`AddNew``Edit`または`Delete`を呼び出すことはできません。 代わりに、データ ソースの更新を実行する独自の関数を記述する必要があります。 バルク行フェッチの詳細については、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

トランザクション中、 `AddNew`、`Edit`および`Delete`操作は、コミットまたはロールバックできます。 の影響と`CommitTrans``Rollback`、現在のレコードが編集バッファーに復元されない可能性があります。 現在のレコードが正しく復元されるようにするには、`CommitTrans`の更新機能と の動作の`Rollback``CDatabase`メンバー関数と メンバー関数を理解`CRecordset`することが重要です。

## <a name="how-committrans-affects-updates"></a><a name="_core_how_committrans_affects_updates"></a>コミットトランスが更新に与える影響

次の表では、トランザクションに`CommitTrans`及ぼす影響について説明します。

### <a name="how-committrans-affects-updates"></a>コミットトランスが更新に与える影響

|Operation|データ ソースの状態|
|---------------|---------------------------|
|`AddNew`、、`Update`そして、`CommitTrans`|新しいレコードがデータ ソースに追加されます。|
|`AddNew`(なし`Update`)、次に`CommitTrans`|新しいレコードは失われます。 データ ソースに追加されていないレコード。|
|`Edit`、、`Update`そして、`CommitTrans`|データ ソースにコミットされた編集。|
|`Edit`(なし`Update`)、次に`CommitTrans`|レコードへの編集は失われます。 データ ソース上のレコードは変更されません。|
|`Delete`そうしたら`CommitTrans`|データ ソースから削除されたレコード。|

## <a name="how-rollback-affects-transactions"></a><a name="_core_how_rollback_affects_updates"></a>ロールバックがトランザクションに与える影響

次の表では、トランザクションに`Rollback`及ぼす影響について説明します。

### <a name="how-rollback-affects-transactions"></a>ロールバックがトランザクションに与える影響

|Operation|現在のレコードの状態|また、必要があります|データ ソースの状態|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew`および`Update`、`Rollback`|現在のレコードの内容は、新しいレコードのスペースを作るために一時的に保存されます。 新しいレコードが編集バッファに入力されます。 呼`Update`び出された後、現在のレコードは編集バッファーに復元されます。||によって`Update`作成されたデータ ソースへの追加が元に戻ります。|
|`AddNew`(なし`Update`)、次の`Rollback`|現在のレコードの内容は、新しいレコードのスペースを作るために一時的に保存されます。 編集バッファーには、新しいレコードが含まれています。|もう`AddNew`一度呼び出して、編集バッファーを空の新しいレコードに復元します。 または、(0)を呼び出`Move`して、古い値をエディット バッファに復元します。|呼`Update`び出されなかったため、データ ソースに変更は加えられました。|
|`Edit`および`Update`、`Rollback`|現在のレコードの未編集バージョンが一時的に保存されます。 編集バッファの内容を編集します。 呼`Update`び出された後、編集されていないレコードは一時的に保存されます。|*Dynaset*: 現在のレコードをスクロールしてから戻り、編集されていないレコードを編集バッファに復元します。<br /><br /> *スナップショット*:`Requery`データ ソースからレコードセットを更新するための呼び出し。|によって`Update`加えられたデータ ソースへの変更は元に戻されます。|
|`Edit`(なし`Update`)、次の`Rollback`|現在のレコードの未編集バージョンが一時的に保存されます。 編集バッファの内容を編集します。|編集`Edit`されていないレコードを編集バッファーに復元するには、再度呼び出します。|呼`Update`び出されなかったため、データ ソースに変更は加えられました。|
|`Delete`そうしたら`Rollback`|現在のレコードの内容が削除されます。|データ`Requery`ソースから現在のレコードの内容を復元する呼び出し。|データ ソースからのデータの削除が取り消されます。|

## <a name="see-also"></a>関連項目

[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[トランザクション: レコードセットからのトランザクション実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[クラス](../../mfc/reference/cdatabase-class.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)
