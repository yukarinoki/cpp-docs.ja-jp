---
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
ms.openlocfilehash: f11c723e4589cb28a3f38100050a69a78fc0809e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212850"
---
# <a name="recordset-more-about-updates-odbc"></a>レコードセット: 更新処理の詳細 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次の内容について説明します。

- [トランザクションなどの他の操作が更新に与える影響](#_core_how_transactions_affect_updates)。

- [更新プログラムと他のユーザーの更新プログラム](#_core_your_updates_and_the_updates_of_other_users)。

- [メンバー関数 Update および Delete の詳細については、こちらを参照して](#_core_more_about_update_and_delete)ください。

> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを実装している場合は、一部の情報が適用されません。 たとえば、`AddNew`、`Edit`、`Delete`、および `Update` のメンバー関数を呼び出すことはできません。ただし、トランザクションを実行することはできます。 バルク行フェッチの詳細については、「レコード[セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

##  <a name="how-other-operations-affect-updates"></a><a name="_core_how_other_operations_affect_updates"></a>他の操作による更新への影響

更新は、トランザクションの完了前にレコードセットを閉じ、トランザクションを完了する前にスクロールすることによって、更新時に有効なトランザクションの影響を受けます。

###  <a name="how-transactions-affect-updates"></a><a name="_core_how_transactions_affect_updates"></a>トランザクションが更新に与える影響

`AddNew`、`Edit`、`Delete` がどのように動作するかを理解すること以外に、 [CDatabase](../../mfc/reference/cdatabase-class.md)の `BeginTrans`、`CommitTrans`、および `Rollback` メンバー関数が[CRecordset](../../mfc/reference/crecordset-class.md)の update 関数でどのように動作するかを理解することが重要です。

既定では、`Update`を呼び出すと、`AddNew` と `Edit` の呼び出しがデータソースに直ちに影響します。 `Delete` 呼び出しはすぐに有効になります。 ただし、トランザクションを確立し、そのような呼び出しのバッチを実行できます。 更新プログラムは、コミットするまで永続的ではありません。 変更した場合は、コミットせずにトランザクションをロールバックできます。

トランザクションの詳細については、「 [Transaction (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

###  <a name="how-closing-the-recordset-affects-updates"></a><a name="_core_how_closing_the_recordset_affects_updates"></a>レコードセットを閉じることによる更新への影響

トランザクションが進行中であるレコードセットまたはそれに関連付けられている `CDatabase` オブジェクトを閉じると ( [cdatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans)または[Cdatabase:: Rollback](../../mfc/reference/cdatabase-class.md#rollback)が呼び出されていない場合)、トランザクションは自動的にロールバックされます (データベースバックエンドが Microsoft Jet データベースエンジンでない場合)。

> [!CAUTION]
>  Microsoft Jet データベースエンジンを使用している場合、明示的なトランザクション内でレコードセットを終了しても、明示的なトランザクションがコミットまたはロールバックされるまで、変更またはロックされた行は解放されません。 明示的な Jet トランザクションの内部または外部で、常にレコードセットを開いたり閉じたりすることをお勧めします。

###  <a name="how-scrolling-affects-updates"></a><a name="_core_how_scrolling_affects_updates"></a>スクロールが更新に与える影響

レコードセットでレコード[セット (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)を使用する場合は、新しい現在のレコードが編集バッファーに格納されます (前のレコードが最初に格納されるわけではありません)。 以前に削除したレコードに対しては、スクロールがスキップされます。 `AddNew` の後にスクロールするか、`Update`、`CommitTrans`、または `Rollback` を呼び出さずに呼び出しを `Edit` すると、新しいレコードが編集バッファーに取り込まれたときに、すべての変更が失われます (警告は表示されません)。 エディットバッファーには、スクロールしたレコードが格納され、格納されているレコードは解放され、データソースに対する変更は発生しません。 これは、`AddNew` と `Edit` の両方に適用されます。

##  <a name="your-updates-and-the-updates-of-other-users"></a><a name="_core_your_updates_and_the_updates_of_other_users"></a>更新プログラムと他のユーザーの更新プログラム

レコードセットを使用してデータを更新する場合、更新は他のユーザーに影響します。 同様に、レコードセットの有効期間中に他のユーザーの更新が影響を受ける場合もあります。

マルチユーザー環境では、レコードセットで選択したものと同じレコードの一部を含むレコードセットを他のユーザーが開くことができます。 レコードを取得する前のレコードに対する変更は、レコードセットに反映されます。 ダイナセットは、スクロールするたびにレコードを取得するので、レコードにスクロールするたびに変更が反映されます。 スナップショットは、最初にスクロールしたときにレコードを取得するので、最初にレコードにスクロールする前に発生した変更のみがスナップショットに反映されます。

レコードセットを開いた後に他のユーザーが追加したレコードは、再クエリを実行しない限り、レコードセットに表示されません。 レコードセットがダイナセットである場合、他のユーザーによる既存のレコードの編集は、影響を受けるレコードにスクロールすると、ダイナセットに表示されます。 レコードセットがスナップショットの場合は、スナップショットを再クエリするまで編集が表示されません。 スナップショット内の他のユーザーによって追加または削除されたレコードや、ダイナセット内の他のユーザーによって追加されたレコードを表示するには、 [CRecordset:: Requery](../../mfc/reference/crecordset-class.md#requery)を呼び出してレコードセットを再構築します。 (他のユーザーの削除は、ダイナセットに表示されることに注意してください)。また、`Requery` を呼び出して、追加したレコードを表示することもできますが、削除は表示されません。

> [!TIP]
>  一度にスナップショット全体を強制的にキャッシュするには、スナップショットを開いた直後に `MoveLast` を呼び出します。 次に、`MoveFirst` を呼び出してレコードの操作を開始します。 `MoveLast` は、すべてのレコードをスクロールするのと同じですが、一度にすべてのレコードを取得します。 ただし、これによりパフォーマンスが低下する可能性があるため、一部のドライバーでは必要ない場合があります。

他のユーザーに対する更新の影響は、お客様の影響に似ています。

##  <a name="more-about-update-and-delete"></a><a name="_core_more_about_update_and_delete"></a>更新と削除の詳細

ここでは、`Update` と `Delete`の操作に役立つ追加情報について説明します。

### <a name="update-success-and-failure"></a>更新の成功と失敗

`Update` が成功した場合、`AddNew` または `Edit` モードが終了します。 `AddNew` または `Edit` モードを再び開始するには、`AddNew` または `Edit`を呼び出します。

`Update` が失敗した場合 (FALSE が返された場合、または例外がスローされた場合)、最後に呼び出された関数に応じて、`AddNew` モードまたは `Edit` モードのままになります。 その場合、次のいずれかを行うことができます。

- フィールドデータメンバーを変更してから、`Update` を再試行してください。

- `AddNew` を呼び出してフィールドデータメンバーを Null にリセットし、フィールドデータメンバーの値を設定してから `Update` をもう一度呼び出します。

- `Edit` を呼び出して、レコードセットに含まれていた値を、`AddNew` または `Edit`の最初の呼び出しの前に再度読み込み、フィールドのデータメンバーの値を設定してから、`Update` を再度呼び出します。 `Update` の呼び出しが成功した後 (`AddNew` 呼び出しを除きます)、フィールドデータメンバーには新しい値が保持されます。

- `Move` を呼び出します (パラメーターが AFX_MOVE_REFRESH、または0の `Move` を含む)。これにより、すべての変更がフラッシュされ、有効になっている `AddNew` または `Edit` モードが終了します。

### <a name="update-and-delete"></a>更新と削除

このセクションは、`Update` と `Delete`の両方に適用されます。

`Update` または `Delete` 操作では、1つのレコードのみを更新する必要があります。 そのレコードは現在のレコードで、レコードセットのフィールドのデータ値に対応しています。 何らかの理由で、影響を受けるレコードがない場合、または複数のレコードが影響を受ける場合は、次のいずれかの**RETCODE**値を含む例外がスローされます。

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

これらの例外がスローされた場合、`Update` または `Delete`を呼び出したときに発生した `AddNew` または `Edit` の状態が残ります。 これらの例外を確認できる最も一般的なシナリオを次に示します。 ほとんどの場合、次のように表示される可能性があります。

- オプティミスティックロックモードを使用しているときに、別のユーザーが、更新または削除する正しいレコードを識別できないようにレコードを変更した場合に AFX_SQL_ERROR_NO_ROWS_AFFECTED します。

- 更新するテーブルに主キーまたは一意のインデックスがない場合に、テーブルの行を一意に識別するのに十分な列がレコードセットにない場合は、AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED ます。

## <a name="see-also"></a>参照

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[例外処理: データベースの例外](../../mfc/exceptions-database-exceptions.md)
