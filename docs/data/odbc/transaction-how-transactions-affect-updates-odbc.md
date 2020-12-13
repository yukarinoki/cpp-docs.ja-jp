---
description: '詳細については、「トランザクション: トランザクションが更新に与える影響 (ODBC)」を参照してください。'
title: 'トランザクション: トランザクションが更新処理に与える影響 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: 56435d477ab11fe057ec20610a35e75d84cf7340
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333894"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>トランザクション: トランザクションが更新処理に与える影響 (ODBC)

[データソース](../../data/odbc/data-source-odbc.md)への更新は、編集バッファー (トランザクションの外部で使用されるのと同じ方法) を使用してトランザクション中に管理されます。 レコードセットのフィールドデータメンバーは、現在のレコードを含む編集バッファーとして機能します。これは、またはの間にレコードセットによって一時的にバックアップされます `AddNew` `Edit` 。 操作中 `Delete` 、現在のレコードはトランザクション内でバックアップされません。 エディットバッファーの詳細と、更新による現在のレコードの格納方法については、「レコード [セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。

> [!NOTE]
> バルク行フェッチを実装している場合は `AddNew` 、、 `Edit` 、またはを呼び出すことはできません `Delete` 。 代わりに、データソースの更新を実行する独自の関数を記述する必要があります。 バルク行フェッチの詳細については、「レコード [セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

トランザクションの実行中は、、、およびの各 `AddNew` `Edit` 操作を `Delete` コミットまたはロールバックできます。 との影響 `CommitTrans` に `Rollback` より、現在のレコードが編集バッファーに復元されない場合があります。 現在のレコードが適切に復元されていることを確認するには、 `CommitTrans` の `Rollback` 関数とメンバー関数が `CDatabase` の update 関数と `CRecordset` どのように連携するかを理解することが重要です。

## <a name="how-committrans-affects-updates"></a><a name="_core_how_committrans_affects_updates"></a> CommitTrans が更新に与える影響

次の表では、トランザクションに対するの影響について説明し `CommitTrans` ます。

### <a name="how-committrans-affects-updates"></a>CommitTrans が更新に与える影響

|操作|データソースの状態|
|---------------|---------------------------|
|`AddNew` and `Update` 、 `CommitTrans`|新しいレコードがデータソースに追加されます。|
|`AddNew` (なし `Update` )、および `CommitTrans`|新しいレコードは失われます。 レコードがデータソースに追加されていません。|
|`Edit` and `Update` 、 `CommitTrans`|編集がデータソースにコミットされました。|
|`Edit` (なし `Update` )、および `CommitTrans`|レコードの編集は失われます。 レコードはデータソースで変更されません。|
|`Delete` そうしたら `CommitTrans`|レコードがデータソースから削除されました。|

## <a name="how-rollback-affects-transactions"></a><a name="_core_how_rollback_affects_updates"></a> ロールバックがトランザクションに与える影響

次の表では、トランザクションに対するの影響について説明し `Rollback` ます。

### <a name="how-rollback-affects-transactions"></a>ロールバックがトランザクションに与える影響

|操作|現在のレコードの状態|また、|データソースの状態|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew` そして `Update` 、 `Rollback`|新しいレコード用の領域を確保するために、現在のレコードの内容が一時的に保存されます。 エディットバッファーに新しいレコードが入力されます。 `Update`を呼び出すと、現在のレコードがエディットバッファーに復元されます。||によって作成されたデータソースへの追加は元に `Update` 戻されます。|
|`AddNew` (なし `Update` )、 `Rollback`|新しいレコード用の領域を確保するために、現在のレコードの内容が一時的に保存されます。 エディットバッファーに新しいレコードが含まれています。|を `AddNew` 再度呼び出して、空の新しいレコードにエディットバッファーを復元します。 または `Move` (0) を呼び出して、古い値をエディットバッファーに復元します。|`Update`が呼び出されなかったため、データソースに変更は加えられませんでした。|
|`Edit` そして `Update` 、 `Rollback`|現在のレコードの編集されていないバージョンが一時的に保存されます。 編集バッファーの内容に対して編集が行われます。 `Update`を呼び出すと、編集されていないレコードのバージョンが一時的に保存されます。|*ダイナセット*: 現在のレコードをスクロールしてから、編集バッファーに再編集されていないレコードのバージョンを復元します。<br /><br /> *Snapshot*: を呼び出して、 `Requery` データソースからレコードセットを更新します。|によって行われたデータソースへの変更は、元に `Update` 戻されます。|
|`Edit` (なし `Update` )、 `Rollback`|現在のレコードの編集されていないバージョンが一時的に保存されます。 編集バッファーの内容に対して編集が行われます。|`Edit`を再度呼び出して、編集バッファーに、編集されていないレコードのバージョンを復元します。|`Update`が呼び出されなかったため、データソースに変更は加えられませんでした。|
|`Delete` そうしたら `Rollback`|現在のレコードの内容は削除されます。|を呼び出して、 `Requery` データソースから現在のレコードの内容を復元します。|データソースからのデータの削除は元に戻されます。|

## <a name="see-also"></a>関連項目

[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[トランザクション: レコードセットでのトランザクションの実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[CDatabase クラス](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)
