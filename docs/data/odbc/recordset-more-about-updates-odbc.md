---
description: '詳細については、「レコードセット: 更新プログラムの詳細 (ODBC)」を参照してください。'
title: 'レコードセット: 更新処理の詳細 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
ms.openlocfilehash: 9d125456189828d50f1fbfd4aece00a16790424f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304442"
---
# <a name="recordset-more-about-updates-odbc"></a>レコードセット: 更新処理の詳細 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次の内容について説明します。

- [トランザクションなどの他の操作が更新に与える影響](#_core_how_transactions_affect_updates)。

- [更新プログラムと他のユーザーの更新プログラム](#_core_your_updates_and_the_updates_of_other_users)。

- [メンバー関数 Update および Delete の詳細については、こちらを参照して](#_core_more_about_update_and_delete)ください。

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを実装している場合は、一部の情報が適用されません。 たとえば、、、、およびの各メンバー関数を呼び出すことはできません `AddNew` `Edit` `Delete` `Update` 。ただし、トランザクションを実行することはできます。 バルク行フェッチの詳細については、「レコード [セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="how-other-operations-affect-updates"></a><a name="_core_how_other_operations_affect_updates"></a> 他の操作による更新への影響

更新は、トランザクションの完了前にレコードセットを閉じ、トランザクションを完了する前にスクロールすることによって、更新時に有効なトランザクションの影響を受けます。

### <a name="how-transactions-affect-updates"></a><a name="_core_how_transactions_affect_updates"></a> トランザクションが更新に与える影響

、、およびのしくみを理解すること以外に、 `AddNew` `Edit` `Delete` `BeginTrans` `CommitTrans` CDatabase の、、および `Rollback` メンバー関数が CRecordset [](../../mfc/reference/cdatabase-class.md)の update 関数とどのように[](../../mfc/reference/crecordset-class.md)連携するかを理解することが重要です。

既定では、を呼び出すと、との呼び出しが `AddNew` `Edit` すぐにデータソースに影響し `Update` ます。 `Delete` 呼び出しはすぐに有効になります。 ただし、トランザクションを確立し、そのような呼び出しのバッチを実行できます。 更新プログラムは、コミットするまで永続的ではありません。 変更した場合は、コミットせずにトランザクションをロールバックできます。

トランザクションの詳細については、「 [Transaction (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

### <a name="how-closing-the-recordset-affects-updates"></a><a name="_core_how_closing_the_recordset_affects_updates"></a> レコードセットを閉じることによる更新への影響

実行中のトランザクションを含むレコードセットまたは関連付けられたオブジェクトを閉じると `CDatabase` ( [cdatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) または [cdatabase:: Rollback](../../mfc/reference/cdatabase-class.md#rollback)が呼び出されていない場合)、トランザクションは自動的にロールバックされます (データベースバックエンドが Microsoft Jet データベースエンジンでない場合)。

> [!CAUTION]
> Microsoft Jet データベースエンジンを使用している場合、明示的なトランザクション内でレコードセットを終了しても、明示的なトランザクションがコミットまたはロールバックされるまで、変更またはロックされた行は解放されません。 明示的な Jet トランザクションの内部または外部で、常にレコードセットを開いたり閉じたりすることをお勧めします。

### <a name="how-scrolling-affects-updates"></a><a name="_core_how_scrolling_affects_updates"></a> スクロールが更新に与える影響

レコードセットでレコード [セット (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) を使用する場合は、新しい現在のレコードが編集バッファーに格納されます (前のレコードが最初に格納されるわけではありません)。 以前に削除したレコードに対しては、スクロールがスキップされます。 `AddNew`、、またはを呼び出さずにまたはを呼び出した後にスクロールすると `Edit` `Update` `CommitTrans` `Rollback` 、新しいレコードが編集バッファーに取り込まれたときに、すべての変更が (警告なしで) 失われます。 エディットバッファーには、スクロールしたレコードが格納され、格納されているレコードは解放され、データソースに対する変更は発生しません。 これは、`AddNew` と `Edit` の両方に適用されます。

## <a name="your-updates-and-the-updates-of-other-users"></a><a name="_core_your_updates_and_the_updates_of_other_users"></a> 更新プログラムと他のユーザーの更新プログラム

レコードセットを使用してデータを更新する場合、更新は他のユーザーに影響します。 同様に、レコードセットの有効期間中に他のユーザーの更新が影響を受ける場合もあります。

マルチユーザー環境では、レコードセットで選択したものと同じレコードの一部を含むレコードセットを他のユーザーが開くことができます。 レコードを取得する前のレコードに対する変更は、レコードセットに反映されます。 ダイナセットは、スクロールするたびにレコードを取得するので、レコードにスクロールするたびに変更が反映されます。 スナップショットは、最初にスクロールしたときにレコードを取得するので、最初にレコードにスクロールする前に発生した変更のみがスナップショットに反映されます。

レコードセットを開いた後に他のユーザーが追加したレコードは、再クエリを実行しない限り、レコードセットに表示されません。 レコードセットがダイナセットである場合、他のユーザーによる既存のレコードの編集は、影響を受けるレコードにスクロールすると、ダイナセットに表示されます。 レコードセットがスナップショットの場合は、スナップショットを再クエリするまで編集が表示されません。 スナップショット内の他のユーザーによって追加または削除されたレコードや、ダイナセット内の他のユーザーによって追加されたレコードを表示するには、 [CRecordset:: Requery](../../mfc/reference/crecordset-class.md#requery) を呼び出してレコードセットを再構築します。 (他のユーザーの削除は、ダイナセットに表示されることに注意してください)。を呼び出し `Requery` て、追加したレコードを表示することもできますが、削除は表示されません。

> [!TIP]
> スナップショット全体を一度に強制的にキャッシュするには、スナップショットを開いた直後にを呼び出します `MoveLast` 。 次 `MoveFirst` に、を呼び出して、レコードの操作を開始します。 `MoveLast` は、すべてのレコードをスクロールするのと同じですが、一度にすべてのレコードを取得します。 ただし、これによりパフォーマンスが低下する可能性があるため、一部のドライバーでは必要ない場合があります。

他のユーザーに対する更新の影響は、お客様の影響に似ています。

## <a name="more-about-update-and-delete"></a><a name="_core_more_about_update_and_delete"></a> 更新と削除の詳細

ここでは、およびの操作に役立つ追加情報について説明し `Update` `Delete` ます。

### <a name="update-success-and-failure"></a>更新の成功と失敗

が成功した場合 `Update` 、 `AddNew` または `Edit` モードは終了します。 またはのモードを再び開始するに `AddNew` `Edit` `AddNew` は、またはを呼び出し `Edit` ます。

`Update`が失敗した場合 (FALSE を返した場合、または例外をスローした場合)、 `AddNew` 最後に `Edit` 呼び出された関数に応じて、またはモードのままになります。 その場合、次のいずれかを行うことができます。

- フィールドデータメンバーを変更してから、を再試行してください `Update` 。

- `AddNew`を呼び出して、フィールドデータメンバーを Null にリセットし、フィールドデータメンバーの値を設定してから、を `Update` 再度呼び出します。

- を呼び出して、 `Edit` レコードセットに含まれていた値をまたはの最初の呼び出しの前に再度読み込み `AddNew` `Edit` 、フィールドのデータメンバーの値を設定してから、を `Update` 再度呼び出します。 呼び出しが成功した後 `Update` (呼び出しの後 `AddNew` を除く)、フィールドデータメンバーには新しい値が保持されます。

- `Move`( `Move` AFX_MOVE_REFRESH、または0のパラメーターを含む) を呼び出すと、すべての変更がフラッシュされ、有効になっている `AddNew` またはモードが終了し `Edit` ます。

### <a name="update-and-delete"></a>更新と削除

このセクションは、との両方に適用さ `Update` `Delete` れます。

`Update`または操作では、1つの `Delete` レコードのみを更新する必要があります。 そのレコードは現在のレコードで、レコードセットのフィールドのデータ値に対応しています。 何らかの理由で、影響を受けるレコードがない場合、または複数のレコードが影響を受ける場合は、次のいずれかの **RETCODE** 値を含む例外がスローされます。

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

これらの例外がスローされた場合、またはを呼び出したときと同じ `AddNew` 状態に `Edit` `Update` `Delete` なります。 これらの例外を確認できる最も一般的なシナリオを次に示します。 ほとんどの場合、次のように表示される可能性があります。

- オプティミスティックロックモードを使用しているときに、別のユーザーが、更新または削除する正しいレコードを識別できないようにレコードを変更した場合に AFX_SQL_ERROR_NO_ROWS_AFFECTED します。

- 更新するテーブルに主キーまたは一意のインデックスがない場合に、テーブルの行を一意に識別するのに十分な列がレコードセットにない場合は、AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED ます。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[例外処理: データベースの例外](../../mfc/exceptions-database-exceptions.md)
