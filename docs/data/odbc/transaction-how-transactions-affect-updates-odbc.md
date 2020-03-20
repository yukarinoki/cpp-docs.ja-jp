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
ms.openlocfilehash: d03ec3f71c38f7790d66fbf6f800b7647e080147
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "79544424"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>トランザクション: トランザクションが更新処理に与える影響 (ODBC)

[データソース](../../data/odbc/data-source-odbc.md)への更新は、編集バッファー (トランザクションの外部で使用されるのと同じ方法) を使用してトランザクション中に管理されます。 レコードセットのフィールドデータメンバーは、現在のレコードを含む編集バッファーとして機能します。これは、`AddNew` または `Edit`中にレコードセットによって一時的にバックアップされます。 `Delete` 操作中、現在のレコードはトランザクション内でバックアップされません。 エディットバッファーの詳細と、更新による現在のレコードの格納方法については、「レコード[セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。

> [!NOTE]
>  バルク行フェッチを実装している場合は、`AddNew`、`Edit`、または `Delete`を呼び出すことはできません。 代わりに、データソースの更新を実行する独自の関数を記述する必要があります。 バルク行フェッチの詳細については、「レコード[セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

トランザクション中に、`AddNew`、`Edit`、および `Delete` 操作をコミットまたはロールバックできます。 `CommitTrans` と `Rollback` の影響により、現在のレコードが編集バッファーに復元されない場合があります。 現在のレコードが適切に復元されていることを確認するには、`CDatabase` の `CommitTrans` および `Rollback` メンバー関数と `CRecordset`の update 関数を連携させる方法を理解することが重要です。

##  <a name="how-committrans-affects-updates"></a><a name="_core_how_committrans_affects_updates"></a>CommitTrans が更新に与える影響

次の表では、トランザクションに対する `CommitTrans` の影響について説明します。

### <a name="how-committrans-affects-updates"></a>CommitTrans が更新に与える影響

|操作|データソースの状態|
|---------------|---------------------------|
|`AddNew` と `Update`を行い、その後 `CommitTrans`|新しいレコードがデータソースに追加されます。|
|`AddNew` (`Update`なし)、`CommitTrans`|新しいレコードは失われます。 レコードがデータソースに追加されていません。|
|`Edit` と `Update`を行い、その後 `CommitTrans`|編集がデータソースにコミットされました。|
|`Edit` (`Update`なし)、`CommitTrans`|レコードの編集は失われます。 レコードはデータソースで変更されません。|
|`Delete` `CommitTrans`|レコードがデータソースから削除されました。|

##  <a name="how-rollback-affects-transactions"></a><a name="_core_how_rollback_affects_updates"></a>ロールバックがトランザクションに与える影響

次の表では、トランザクションに対する `Rollback` の影響について説明します。

### <a name="how-rollback-affects-transactions"></a>ロールバックがトランザクションに与える影響

|操作|現在のレコードの状態|また、|データソースの状態|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew` と `Update`、次に `Rollback`|新しいレコード用の領域を確保するために、現在のレコードの内容が一時的に保存されます。 エディットバッファーに新しいレコードが入力されます。 `Update` が呼び出されると、現在のレコードがエディットバッファーに復元されます。||`Update` によって作成されたデータソースの追加は元に戻されます。|
|`AddNew` (`Update`なし)、`Rollback`|新しいレコード用の領域を確保するために、現在のレコードの内容が一時的に保存されます。 エディットバッファーに新しいレコードが含まれています。|`AddNew` をもう一度呼び出して、エディットバッファーを空の新しいレコードに復元します。 または、`Move`(0) を呼び出して、編集バッファーに古い値を復元します。|`Update` が呼び出されなかったため、データソースに変更は加えられませんでした。|
|`Edit` と `Update`、次に `Rollback`|現在のレコードの編集されていないバージョンが一時的に保存されます。 編集バッファーの内容に対して編集が行われます。 `Update` が呼び出された後も、編集されていないレコードのバージョンは一時的に保存されます。|*ダイナセット*: 現在のレコードをスクロールしてから、編集バッファーに再編集されていないレコードのバージョンを復元します。<br /><br /> *Snapshot*: `Requery` を呼び出して、データソースからレコードセットを更新します。|`Update` によって行われたデータソースへの変更は元に戻されます。|
|`Edit` (`Update`なし)、`Rollback`|現在のレコードの編集されていないバージョンが一時的に保存されます。 編集バッファーの内容に対して編集が行われます。|`Edit` をもう一度呼び出して、編集バッファーに編集前のバージョンのレコードを復元します。|`Update` が呼び出されなかったため、データソースに変更は加えられませんでした。|
|`Delete` `Rollback`|現在のレコードの内容は削除されます。|`Requery` を呼び出して、データソースから現在のレコードの内容を復元します。|データソースからのデータの削除は元に戻されます。|

## <a name="see-also"></a>参照

[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[トランザクション: レコードセットからのトランザクション実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[CDatabase クラス](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)
