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
ms.openlocfilehash: 955b26137ce976514d84f95f4d819779b93bd78a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368675"
---
# <a name="recordset-more-about-updates-odbc"></a>レコードセット: 更新処理の詳細 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次の内容について説明します。

- [トランザクションなどの他の操作が更新に与える影響](#_core_how_transactions_affect_updates)

- [更新プログラムと他のユーザーの更新](#_core_your_updates_and_the_updates_of_other_users):

- [更新および削除のメンバー関数の詳細](#_core_more_about_update_and_delete)については、

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを実装している場合、一部の情報は適用されません。 たとえば、 `AddNew`、 `Edit`、`Delete`および メンバー関数を`Update`呼び出すことはできません。ただし、トランザクションを実行することはできます。 バルク行フェッチの詳細については、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="how-other-operations-affect-updates"></a><a name="_core_how_other_operations_affect_updates"></a>その他の操作が更新に与える影響

更新は、更新時に有効なトランザクション、トランザクションを完了する前にレコードセットを閉じること、およびトランザクションを完了する前にスクロールすることによって、影響を受けます。

### <a name="how-transactions-affect-updates"></a><a name="_core_how_transactions_affect_updates"></a>トランザクションが更新に与える影響

`AddNew`の方法 、`Edit``Delete`および機能を理解する以外に、 `BeginTrans`CDatabase`CommitTrans`の`Rollback`、 、および メンバー関数が[CRecordset](../../mfc/reference/cdatabase-class.md)の更新関数とどのように連携するかを理解することが重要です。 [CRecordset](../../mfc/reference/crecordset-class.md)

既定では、 を`AddNew`呼`Edit`び出すと、データ ソースが`Update`呼び出され、すぐに反映されます。 `Delete`呼び出しは即時に有効になります。 しかし、トランザクションを確立し、そのような呼び出しのバッチを実行できます。 更新は、コミットするまで永続的ではありません。 考えが変わった場合は、コミットせずにトランザクションをロールバックできます。

トランザクションの詳細については、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

### <a name="how-closing-the-recordset-affects-updates"></a><a name="_core_how_closing_the_recordset_affects_updates"></a>レコードセットを閉じると更新に与える影響

トランザクションが進行中のレコードセットまたは関連`CDatabase`オブジェクトを閉じると[(CDatabase::CommitTrans または CDatabase::Rollback)、](../../mfc/reference/cdatabase-class.md#committrans)トランザクションは自動的にロールバックされます (データベースバックエンドが Microsoft Jet データベース エンジンでない限り)。 [CDatabase::Rollback](../../mfc/reference/cdatabase-class.md#rollback)

> [!CAUTION]
> Microsoft Jet データベース エンジンを使用している場合、明示的なトランザクション内でレコードセットを閉じると、明示的なトランザクションがコミットまたはロールバックされるまで、変更された行やロックが解放されることはありません。 明示的な Jet トランザクションの内部または外部のレコードセットは、常に開く、閉じるのを行うことをお勧めします。

### <a name="how-scrolling-affects-updates"></a><a name="_core_how_scrolling_affects_updates"></a>スクロールが更新に与える影響

[レコードセット: レコードセット内のスクロール (ODBC) の](../../data/odbc/recordset-scrolling-odbc.md)場合、編集バッファーには新しいレコードがそれぞれ格納されます (前のレコードは最初に保存されません)。 スクロールすると、以前に削除されたレコードをスキップします。 を`CommitTrans`呼び出さず`AddNew`に`Edit`、または`Rollback``Update`を呼び出した後にスクロールすると、新しいレコードがエディット バッファに取り込まれるため、変更は失われます (警告は表示されません)。 編集バッファーには、レコードがスクロールされて、格納されているレコードが解放され、データ ソースに変更は発生しません。 これは、`AddNew` と `Edit` の両方に適用されます。

## <a name="your-updates-and-the-updates-of-other-users"></a><a name="_core_your_updates_and_the_updates_of_other_users"></a>更新プログラムと他のユーザーの更新

レコードセットを使用してデータを更新すると、更新が他のユーザーに影響を与えます。 同様に、レコードセットの有効期間中に他のユーザーが更新された場合にも影響します。

マルチユーザー環境では、他のユーザーがレコードセットで選択したレコードと同じレコードを含むレコードセットを開くことができます。 レコードを取得する前に変更したレコードは、レコードセットに反映されます。 ダイナセットは、レコードにスクロールするたびにレコードを取得するため、レコードにスクロールするたびに変更が反映されます。 スナップショットは、最初にレコードにスクロールしたときにレコードを取得するため、最初にレコードにスクロールする前に発生した変更のみがスナップショットに反映されます。

レコードセットを開いた後に他のユーザーによって追加されたレコードは、再クエリを行わない限り、レコードセットに表示されません。 レコードセットがダイナセットの場合、影響を受けるレコードまでスクロールすると、他のユーザーによる既存のレコードの編集がダイナセットに表示されます。 レコードセットがスナップショットの場合、スナップショットを再クエリするまで編集は表示されません。 スナップショットの他のユーザーによって追加または削除されたレコード、またはダイナセット内の他のユーザーによって追加されたレコードを表示するには[、CRecordset::Requery](../../mfc/reference/crecordset-class.md#requery)を呼び出してレコードセットを再構築します。 (他のユーザーの削除はダイナセットに表示されることに注意してください。追加したレコードを`Requery`表示するために呼び出す場合もありますが、削除を表示することはできません。

> [!TIP]
> スナップショット全体を一度にキャッシュするには、スナップショットを`MoveLast`開いた直後に呼び出します。 次に`MoveFirst`、レコードの操作を開始するために呼び出します。 `MoveLast`すべてのレコードをスクロールするのと同じですが、すべてを一度に取得します。 ただし、パフォーマンスが低下する可能性があり、一部のドライバでは必要ない場合があることに注意してください。

更新プログラムが他のユーザーに及ぼす影響は、ユーザーに与える影響と似ています。

## <a name="more-about-update-and-delete"></a><a name="_core_more_about_update_and_delete"></a>更新と削除の詳細

ここでは、 および の作業に役立`Update`つ`Delete`追加情報を提供します。

### <a name="update-success-and-failure"></a>更新の成功と失敗

成功`Update`すると、または`Edit`モード`AddNew`は終了します。 または`AddNew``Edit`モードをもう一度開始`AddNew`するには`Edit`、 または を呼び出します。

失敗`Update`した場合 (FALSE を返すか、例外をスロー `AddNew` )、最後に呼び出した関数に応じて、または`Edit`モードのままになります。 その場合、次のいずれかを行うことができます。

- フィールド データ メンバーを変更して`Update`、もう一度実行してください。

- フィールド`AddNew`データ メンバーを Null にリセットし、フィールド データ メンバーの値を設定`Update`してから、もう一度呼び出します。

- または`Edit`への最初の呼び出しの前にレコードセットに`AddNew`含`Edit`まれている値を再読み込みし、フィールド データ`Update`メンバーの値を設定してから、再度呼び出します。 呼び出`Update`しが成功した後`AddNew`(呼び出し後を除く)、フィールド データ メンバーは新しい値を保持します。

- AFX_MOVE_REFRESH`Move`のパラメータ`Move`を含む呼び出し(パラメータを含む、または 0)、`Edit`変更をフラッシュし、有効な任意のモードまたはモードを`AddNew`終了します。

### <a name="update-and-delete"></a>更新と削除

このセクションは、`Update`および`Delete`の両方に適用されます。

または`Delete``Update`操作では、1 つのレコードだけを更新する必要があります。 レコードはカレント レコードであり、レコードセットのフィールドのデータ値に対応します。 何らかの理由でレコードが影響を受けない場合、または複数のレコードが影響を受ける場合は、次のいずれかの**RETCODE**値を含む例外がスローされます。

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

これらの例外がスローされた場合は、`AddNew`または`Edit``Update``Delete`を呼び出したときに 、または の状態が維持されます。 これらの例外が発生する最も一般的なシナリオを次に示します。 次の項目が表示される可能性が最も高い:

- AFX_SQL_ERROR_NO_ROWS_AFFECTEDオプティミスティック ロック モードを使用していて、別のユーザーが更新または削除する正しいレコードをフレームワークが識別できないようにレコードを変更した場合です。

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED更新するテーブルに主キーまたは一意のインデックスがなく、テーブルの行を一意に識別するための十分な列がレコードセットにない場合です。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[例外処理 : データベースの例外](../../mfc/exceptions-database-exceptions.md)
