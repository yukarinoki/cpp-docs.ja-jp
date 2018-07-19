---
title: 'レコード セット: 複数の更新に関する (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ea46e0462f3763e04ec18ad9bff2b0d3ded1deee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098668"
---
# <a name="recordset-more-about-updates-odbc"></a>レコードセット: 更新処理の詳細 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、次の内容について説明します。  
  
-   [更新トランザクションなどの他の操作に与える](#_core_how_transactions_affect_updates)です。  
  
-   [更新内容や他のユーザーの](#_core_your_updates_and_the_updates_of_other_users)します。  
  
-   [詳細については、Update および Delete のメンバー関数は、](#_core_more_about_update_and_delete)です。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを実装した場合、情報の一部は適用されません。 など、呼び出すことができません、 `AddNew`、**編集**、**削除**、および**更新**メンバー関数です。 ただし、トランザクションを実行することができます。 バルク行フェッチの詳細については、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
##  <a name="_core_how_other_operations_affect_updates"></a> その他の操作が更新プログラムに与える影響  
 更新による影響はトランザクション有効時、更新プログラムのトランザクションを完了する前に、レコード セットを閉じることで、トランザクションを完了する前にスクロールしています。  
  
###  <a name="_core_how_transactions_affect_updates"></a> トランザクションが更新プログラムに与える影響  
 Understanding を超えて方法`AddNew`、**編集**、および**削除**作業を理解しておく必要が方法、 **BeginTrans**、 **CommitTrans**、および**ロールバック**のメンバー関数は[CDatabase](../../mfc/reference/cdatabase-class.md)の更新機能と連携[CRecordset](../../mfc/reference/crecordset-class.md)です。  
  
 既定では、呼び出し`AddNew`と**編集**データ ソースを呼び出すと即座に影響**更新**です。 **削除**呼び出し直ちに有効にします。 トランザクションを行うし、このような呼び出しのバッチを実行することができます。 コミットするまでの更新は永続的なされません。 気が変わった場合することができますをロールバックするトランザクションをコミットせずします。  
  
 トランザクションの詳細については、次を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
###  <a name="_core_how_closing_the_recordset_affects_updates"></a> レコード セットを閉じると、更新プログラムにどのように影響する方法  
 レコード セット、またはそれに関連付けられたを閉じた場合`CDatabase`進行中のトランザクションでのオブジェクト (されませんと呼ばれる[CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans)または[CDatabase::Rollback](../../mfc/reference/cdatabase-class.md#rollback))、トランザクションはロールバックされます自動的に (がない限り、データベース バックエンド Microsoft Jet データベース エンジン) をバックアップします。  
  
> [!CAUTION]
>  Microsoft Jet データベース エンジンを使用している場合、明示的なトランザクション内のレコード セットを閉じる結果がありませんが変更された行または明示的なトランザクションがコミットまたはロールバックされるまでに配置されていたロックの解除。 常に両方 open および close レコード セットはことの内部または外部 Jet の明示的なトランザクションをお勧めします。  
  
###  <a name="_core_how_scrolling_affects_updates"></a> 更新プログラムのスクロールの影響  
 ときに、[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)でレコード セットをエディット バッファーが表示各新しい現在のレコード (前のレコードが最初に格納されません)。 削除されたレコードをスキップをスクロールします。 後にスクロールする場合、`AddNew`または**編集**呼び出さず呼び出し**更新**、 **CommitTrans**、または**ロールバック**最初に、すべての変更失われます (警告を表示しないする)、新しいレコードがエディット バッファーに読み込まれるとします。 エディット バッファーをスクロール レコードが挿入、ストアドのレコードが解放され、データ ソースの変更は発生しません。 これは両方に当てはまります`AddNew`と**編集**です。  
  
##  <a name="_core_your_updates_and_the_updates_of_other_users"></a> およびその他のユーザーの更新プログラム  
 レコード セットを使用してデータを更新するときに、更新プログラムは他のユーザーに影響します。 同様に、レコード セットの有効期間中に他のユーザーの更新プログラムでは、ユーザーに影響します。  
  
 マルチ ユーザー環境の場合は、他のユーザーは、一部のレコード セットで選択した同じレコードを格納したレコード セットを開くことができます。 レコード セットには、取得する前に、レコードへの変更が反映されます。 ダイナセットを使う場合は、それをスクロールするたびにレコードを取得、ためダイナセットを使う場合は、レコードをスクロールするたびに変更を反映します。 スナップショットは、最初にスナップショットが最初に、レコードをスクロールする前に発生した変更のみを反映するためにスクロールするレコードを取得します。  
  
 レコード セットには再実行する限り、レコード セットを開いた後に、他のユーザーによって追加されたレコードは表示されません。 レコード セットがダイナセットの場合は、他のユーザーが既存のレコードを編集は表示をダイナセットに影響を受けるレコードをスクロールする際に。 レコード セットがスナップショットの場合は、スナップショットを再実行するまでの間の編集は表示されません。 追加されたレコードを表示、または呼び出すスナップショット、または、ダイナセットの他のユーザーによって追加されたレコードの他のユーザーによって削除された場合[:requery](../../mfc/reference/crecordset-class.md#requery)をレコード セットを再構築します。 (他のユーザーの削除をダイナセットに表示されるメモ。)呼び出すことができます**Requery**のレコードを追加するに自分が表示されないことができます。  
  
> [!TIP]
>  スナップショットの 1 回にすべてのキャッシュには、呼び出す`MoveLast`スナップショットを開いた後にすぐにします。 呼び出す**MoveFirst**レコードを使用して作業を開始します。 `MoveLast` すべてのレコードをスクロールすると同じですが、それらを一度に取得できます。 ただし、このパフォーマンスが低下して、一部のドライバーに必要なことができない可能性があることに注意してください。  
  
 他のユーザーに対する更新の影響は、影響と似ています。  
  
##  <a name="_core_more_about_update_and_delete"></a> 詳細については、Update および Delete  
 このセクションの内容を操作するための追加の情報を提供する**更新**と**削除**です。  
  
### <a name="update-success-and-failure"></a>更新プログラムの成功と失敗  
 場合**更新**成功すると、`AddNew`または**編集**モードが終了します。 開始する、`AddNew`または**編集**モードをもう一度、呼び出し`AddNew`または**編集**です。  
  
 場合**更新**が失敗した (を返します**FALSE**または例外をスローした) を引き続き`AddNew`または**編集**モード、関数によって、最後に呼び出さです。 次のいずれかを実行できます。  
  
-   フィールド データ メンバーを変更して再試行して、**更新**もう一度です。  
  
-   呼び出す`AddNew`を Null には、フィールド データ メンバーをリセットするには、フィールド データ メンバーの値を設定を呼び出す**更新**もう一度です。  
  
-   呼び出す**編集**最初の呼び出しの前に、レコード セットに含まれていた値を再読み込みする`AddNew`または**編集**フィールド データ メンバーの値を設定し、まず、 **を更新**もう一度です。 正常に実行後**更新**を呼び出す (後を除き、`AddNew`呼び出し)、フィールド データ メンバーは、新しい値を保持します。  
  
-   呼び出す**移動**(など**移動**のパラメーターを持つ**AFX_MOVE_REFRESH**、または 0) を変更し、いずれかの終了をすべて消去する`AddNew`または**を編集**モードを有効にします。  
  
### <a name="update-and-delete"></a>更新および削除  
 このセクションでは、両方に適用されます**更新**と**削除**です。  
  
 **更新**または**削除**操作、1 つだけのレコードを更新する必要があります。 そのレコードは、レコード セットのフィールドのデータ値に対応する現在のレコードです。 場合は、次のいずれかを含む、例外をスローするなんらかの理由で影響を受けるレコードがないか、複数のレコードが影響を受ける、 **RETCODE**値。  
  
-   **AFX_SQL_ERROR_NO_ROWS_AFFECTED**  
  
-   **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED**  
  
 これらの例外がスローされると、引き続き、`AddNew`または**編集**を呼び出したときにされていた状態**更新**または**削除**です。 これらの例外が表示される最も一般的なシナリオを示します。 最も頻繁に発生します。  
  
-   **AFX_SQL_ERROR_NO_ROWS_AFFECTED**オプティミスティック ロック モードと別のユーザーのどちらを使用している場合をフレームワークが更新または削除する適切なレコードを識別するを妨げる方法でレコードが変更されます。  
  
-   **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED**ときに更新するテーブルに主キーがありませんまたは一意なインデックスとする十分な列でない、レコード セットをテーブルの行を一意に識別します。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [: レコード選択レコードのしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [レコード フィールド エクス (チェンジ RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [SQL](../../data/odbc/sql.md)   
 [例外処理: データベースの例外](../../mfc/exceptions-database-exceptions.md)