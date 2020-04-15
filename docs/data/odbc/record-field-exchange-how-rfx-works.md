---
title: 'レコード フィールド エクスチェンジ: RFX の動作のしくみ'
ms.date: 11/04/2016
helpviewer_keywords:
- record editing [C++], using RFX
- RFX (ODBC) [C++], updating data in recordsets
- scrolling [C++]
- ODBC [C++], RFX
- data binding [C++], DFX
- scrolling [C++], RFX
- RFX (ODBC) [C++], binding fields and parameters
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
ms.openlocfilehash: 903acf4f55fb2708f4998a2babf3f143c895429b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367167"
---
# <a name="record-field-exchange-how-rfx-works"></a>レコード フィールド エクスチェンジ: RFX の動作のしくみ

このトピックでは、RFX プロセスについて説明します。 これは高度なトピックです:

- [RFX とレコードセット](#_core_rfx_and_the_recordset)

- [RFX プロセス](#_core_the_record_field_exchange_process)

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` から派生したクラスを対象にしています。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ (Bulk RFX) が実装されます。 Bulk RFX は、RFX に似ています。 この違いについては、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="rfx-and-the-recordset"></a><a name="_core_rfx_and_the_recordset"></a>RFX とレコードセット

レコードセット オブジェクトのフィールド データ メンバは、1 つのレコードの選択した列を保持する編集バッファになります。 レコードセットが最初に開かれ、最初のレコードを読み取ろうとすると、RFX は選択された各列を適切なフィールド データ メンバーのアドレスにバインド (関連付けます) します。 レコードセットがレコードを更新すると、RFX は ODBC API 関数を呼び出して、SQL **UPDATE**ステートメントまたは**INSERT**ステートメントをドライバーに送信します。 RFX は、フィールド データ メンバーに関するナレッジを使用して、書き込む列を指定します。

フレームワークは、必要に応じてその内容を復元できるように、特定の段階で編集バッファーをバックアップします。 RFX は、新しいレコードを追加する前と既存のレコードを編集する前に、編集バッファーをバックアップします。 次の呼び出しの後など、場合によっては編集バッファを`Update`復元`AddNew`します。 新しく変更された編集バッファを破棄した場合、たとえば、呼び出す`Update`前に別のレコードに移動した場合、エディット バッファは復元されません。

RFX は、データ ソースとレコードセットのフィールド データ メンバーとの間でデータを交換するだけでなく、バインド パラメータを管理します。 レコードセットを開くと、パラメータ データ メンバーは`CRecordset::Open`、構築する SQL ステートメントの "?" プレースホルダーの順序でバインドされます。 詳細については、「[レコードセット : レコードセットのパラメータ化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。

レコードセット クラスの オーバーライド`DoFieldExchange`は、すべての作業を行い、双方向のデータを移動します。 ダイアログ データ エクスチェンジ (DDX) と同様に、RFX ではクラスのデータ メンバーに関する情報が必要です。 ウィザードでは、ウィザードで指定したフィールド データ メンバー名と`DoFieldExchange`データ型に基づいて、レコードセット固有の実装を記述することによって必要な情報が提供されます。

## <a name="record-field-exchange-process"></a><a name="_core_the_record_field_exchange_process"></a>レコード フィールドエクスチェンジ プロセス

このセクションでは、レコードセット オブジェクトが開かれ、レコードを追加、更新、および削除するときに発生する RFX イベントのシーケンスについて説明します。 このトピックの表で示す[RFX 操作のレコードセットオープン時](#_core_sequence_of_rfx_operations_during_recordset_open)[の RFX 操作のシーケンスと、RFX](#_core_sequence_of_rfx_operations_during_scrolling)がレコードセット`Move`内のコマンドを処理するプロセスと RFX が更新を管理するプロセスを示します。 これらのプロセスの間に[、DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)は、さまざまな操作を実行するために呼び出されます。 `m_nOperation` [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクトのデータ メンバーは、要求される操作を決定します。 この資料を読む前に、「[レコードセットがレコードを選択する方法 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)と[レコードセット: レコードセットがレコードを更新する方法 (ODBC)」を](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)読み取ると便利です。

### <a name="rfx-initial-binding-of-columns-and-parameters"></a><a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a>RFX: 列とパラメータの初期バインディング

レコードセット オブジェクトの[Open](../../mfc/reference/crecordset-class.md#open)メンバー関数を呼び出すと、次の RFX アクティビティが表示順に実行されます。

- レコードセットにパラメータ データ メンバがある場合、`DoFieldExchange`フレームワークは、パラメータをレコードセットの SQL ステートメント文字列のパラメータ プレースホルダにバインドする呼び出しを行います。 パラメーターの値のデータ型に依存する表現は **、SELECT**ステートメントで見つかった各プレースホルダーに使用されます。 これは、SQL ステートメントが準備された後、実行される前に発生します。 ステートメントの準備については、『ODBC プログラマ`::SQLPrepare`リファレンス』の関数*を参照してください*。

- フレームワークは、`DoFieldExchange`選択した列の値をレコードセット内の対応するフィールド データ メンバーにバインドするために、2 回目に呼び出します。 これにより、レコードセット オブジェクトは、最初のレコードの列を含む編集バッファーとして設定されます。

- レコードセットは SQL ステートメントを実行し、データ ソースは最初のレコードを選択します。 レコードの列は、レコードセットのフィールド データ メンバーに読み込まれます。

次の表は、レコードセットを開くときの RFX 操作のシーケンスを示しています。

### <a name="sequence-of-rfx-operations-during-recordset-open"></a><a name="_core_sequence_of_rfx_operations_during_recordset_open"></a>レコードセットを開く際の RFX 操作のシーケンス

|操作|操作|データベース/SQL 操作|
|--------------------|-------------------------------|-----------------------------|
|1. レコードセットを開きます。|||
||2. SQL ステートメントを作成します。||
|||3. SQL を送信します。|
||4. パラメータデータメンバーをバインドします。||
||5. フィールドデータメンバーを列にバインドします。||
|||6. ODBC は移動を行い、データを入力します。|
||7. C++ のデータを修正します。||

レコードセットは ODBC のプリペアド実行を使用して、同じ SQL ステートメントで高速に再クエリを実行できます。 準備された実行の詳細については、MSDN ライブラリの ODBC SDK*プログラマ リファレンスを参照*してください。

### <a name="rfx-scrolling"></a><a name="_mfc_rfx.3a_.scrolling"></a>RFX: スクロール

あるレコードから別のレコードにスクロールすると、フレームワークは`DoFieldExchange`、フィールド データ メンバーに以前に格納されていた値を新しいレコードの値に置き換える呼び出しを行います。

次の表は、ユーザーがレコード間を移動するときの RFX 操作の順序を示しています。

### <a name="sequence-of-rfx-operations-during-scrolling"></a><a name="_core_sequence_of_rfx_operations_during_scrolling"></a>スクロール中の RFX 操作のシーケンス

|操作|操作|データベース/SQL 操作|
|--------------------|-------------------------------|-----------------------------|
|1.`MoveNext`呼び出すか、または他の移動機能の 1 つを呼び出します。|||
|||2. ODBC は移動を行い、データを入力します。|
||3. C++ のデータを修正します。||

### <a name="rfx-adding-new-records-and-editing-existing-records"></a><a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a>RFX: 新しいレコードの追加と既存のレコードの編集

新しいレコードを追加すると、レコードセットは編集バッファとして動作し、新しいレコードの内容を作成します。 レコードの追加と同様に、レコードの編集では、レコードセットのフィールド データ メンバーの値を変更します。 RFX の観点から見ると、シーケンスは次のようになります。

1. レコードセットの[AddNew](../../mfc/reference/crecordset-class.md#addnew)または[Edit](../../mfc/reference/crecordset-class.md#edit)メンバー関数を呼び出すと、RFX は現在の編集バッファーを格納し、後で復元できるようにします。

1. `AddNew`または`Edit`、RFX が変更されたフィールド データ メンバーを検出できるように、編集バッファー内のフィールドを準備します。

   新しいレコードには、新しい値を比較する前の値`AddNew`がないため、各フィールド データ メンバーの値をPSEUDO_NULL値に設定します。 後で呼び出`Update`すと、RFX は各データ メンバの値とPSEUDO_NULL値を比較します。 違いがある場合は、データ メンバーが設定されています。 (PSEUDO_NULLは、真の Null 値を持つレコード列と同じでも、C++ の NULL と同じでもありません。

   `Update`の呼び出`AddNew`しと`Update`は異`Edit`なり、呼び出しは、PSEUDO_NULLを使用するのではなく、以前に格納された値と更新された値を比較します。 違いは、`AddNew`比較のために以前に格納された値が存在しない点です。

1. 編集する値や新しいレコードに入力するフィールド データ メンバーの値を直接設定します。 これには、 の`SetFieldNull`呼び出しが含まれます。

1. [Update](../../mfc/reference/crecordset-class.md#update)の呼び出しでは、手順 2 で説明したように、変更されたフィールド データ メンバーをチェックします ([スクロール中の RFX 操作のシーケンス](#_core_sequence_of_rfx_operations_during_scrolling)を参照)。 何も変更されていない場合`Update`は、0 を返します。 フィールド・データ・メンバーが変更された`Update`場合は、レコード内のすべての更新済みフィールドの値を含む SQL **INSERT**ステートメントを準備して実行します。

1. の`AddNew``Update`場合は、呼び出し前に現在のレコードに格納されていた値を`AddNew`復元することで終了します。 の`Edit`場合、新しい編集された値はそのまま残ります。

次の表は、新しいレコードを追加するとき、または既存のレコードを編集するときの RFX 操作の順序を示しています。

### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>AddNew および編集時の RFX 操作のシーケンス

|操作|操作|データベース/SQL 操作|
|--------------------|-------------------------------|-----------------------------|
|1.`AddNew`電話`Edit`または .|||
||2. 編集バッファをバックアップします。||
||3.`AddNew`フィールド データ メンバーを "クリーン" および Null としてマークします。||
|4. レコードセットフィールドのデータメンバーに値を割り当てます。|||
|5.`Update`電話.|||
||6. 変更された項目を確認します。||
||7. SQL **INSERT** `AddNew`ステートメントを 作成`Edit`するか、または に対してステートメントを**更新**します。||
|||8. SQL を送信します。|
||9.`AddNew`の場合、編集バッファをバックアップされた内容に復元します。 の`Edit`場合は、バックアップを削除します。||

### <a name="rfx-deleting-existing-records"></a>RFX: 既存のレコードを削除する

レコードを削除すると、RFX はレコードが削除されたことを通知する通知として、すべてのフィールドを NULL に設定し、レコードを移動する必要があります。 他の RFX シーケンス情報は必要ありません。

## <a name="see-also"></a>関連項目

[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[MFC ODBC コンシューマー](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[マクロ、グローバル関数、およびグローバル変数](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[クラス](../../mfc/reference/cfieldexchange-class.md)<br/>
[レコードセット::Dフィールドエクスチェンジ](../../mfc/reference/crecordset-class.md#dofieldexchange)
