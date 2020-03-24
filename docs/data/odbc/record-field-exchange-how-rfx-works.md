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
ms.openlocfilehash: 0661e61bceeedc0dd049ef47f5a0a0b71a8d82ed
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213071"
---
# <a name="record-field-exchange-how-rfx-works"></a>レコード フィールド エクスチェンジ: RFX の動作のしくみ

このトピックでは、RFX プロセスについて説明します。 これは高度なトピックです。

- [RFX とレコードセット](#_core_rfx_and_the_recordset)

- [RFX プロセス](#_core_the_record_field_exchange_process)

> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` から派生したクラスを対象にしています。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ (Bulk RFX) が実装されます。 Bulk RFX は、RFX に似ています。 違いを理解するには、「レコード[セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

##  <a name="rfx-and-the-recordset"></a><a name="_core_rfx_and_the_recordset"></a>RFX とレコードセット

レコードセットオブジェクトのフィールドデータメンバーは、1つのレコードの選択された列を保持する編集バッファーを構成します。 レコードセットが最初に開かれ、最初のレコードを読み取るときに、RFX は、選択した各列を適切なフィールドデータメンバーのアドレスにバインド (関連付けます) します。 レコードセットがレコードを更新すると、RFX は ODBC API 関数を呼び出して、SQL **UPDATE**または**INSERT**ステートメントをドライバーに送信します。 RFX では、フィールドデータメンバーの知識を使用して、書き込む列を指定します。

フレームワークは、必要に応じてコンテンツを復元できるように、特定の段階で編集バッファーをバックアップします。 RFX は、新しいレコードを追加する前、および既存のレコードを編集する前に、編集バッファーをバックアップします。 たとえば、`AddNew`次のような `Update` の呼び出しの後など、場合によっては編集バッファーを復元します。 `Update`を呼び出す前に別のレコードに移動するなどして、新しく変更されたエディットバッファーを破棄した場合、編集バッファーは復元されません。

RFX では、データソースとレコードセットのフィールドデータメンバーの間でデータを交換するだけでなく、バインドパラメーターを管理します。 レコードセットが開かれると、すべてのパラメーターデータメンバーが、`CRecordset::Open` コンストラクトである SQL ステートメントの "?" プレースホルダーの順序でバインドされます。 詳細については、「[レコードセット: レコードセットのパラメーター化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。

レコードセットクラスの `DoFieldExchange` のオーバーライドにより、すべての処理が実行され、双方向のデータが移動します。 ダイアログデータエクスチェンジ (DDX) と同様に、RFX はクラスのデータメンバーに関する情報を必要とします。 ウィザードでは、ウィザードで指定したフィールドのデータメンバー名とデータ型に基づいて、`DoFieldExchange` のレコードセット固有の実装を作成することによって、必要な情報を得られます。

##  <a name="record-field-exchange-process"></a><a name="_core_the_record_field_exchange_process"></a>レコードフィールドの交換プロセス

このセクションでは、レコードセットオブジェクトが開かれたときと、レコードを追加、更新、および削除したときの RFX イベントのシーケンスについて説明します。 このトピックでは、[レコードセットが開いている間の Rfx 操作のテーブルシーケンス](#_core_sequence_of_rfx_operations_during_recordset_open)と、このトピックの[スクロール中](#_core_sequence_of_rfx_operations_during_scrolling)の rfx 操作のテーブルシーケンスで、rfx がレコードセット内の `Move` コマンドを処理し、rfx が更新を管理していることを示します。 これらのプロセスでは、さまざまな操作を実行するために[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)が呼び出されます。 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクトの `m_nOperation` データメンバーによって、どの操作が要求されるかが決まります。 レコードセットを読み取ることが役に立つ場合があります。レコードセットが[レコードを選択する方法 (odbc)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)と[レコードセット: レコードを更新する方法 (odbc)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)については、この資料を参照してください。

###  <a name="rfx-initial-binding-of-columns-and-parameters"></a><a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a>RFX: 列とパラメーターの初期バインド

次の RFX アクティビティは、レコードセットオブジェクトの[Open](../../mfc/reference/crecordset-class.md#open)メンバー関数を呼び出すと、示されている順序で発生します。

- レコードセットにパラメーターデータメンバーが含まれている場合、フレームワークは `DoFieldExchange` を呼び出して、レコードセットの SQL ステートメント文字列のパラメータープレースホルダーにパラメーターをバインドします。 パラメーターの値のデータ型に依存する表現は、 **SELECT**ステートメントで見つかった各プレースホルダーに対して使用されます。 これは、SQL ステートメントが準備されてから実行されるまでの間に発生します。 ステートメントの準備の詳細については、ODBC*プログラマーリファレンス*の `::SQLPrepare` 関数を参照してください。

- フレームワークは `DoFieldExchange` をもう一度呼び出して、選択した列の値をレコードセット内の対応するフィールドデータメンバーにバインドします。 これにより、レコードセットオブジェクトが、最初のレコードの列を含む編集バッファーとして設定されます。

- レコードセットによって SQL ステートメントが実行され、データソースによって最初のレコードが選択されます。 レコードの列は、レコードセットのフィールドデータメンバーに読み込まれます。

次の表に、レコードセットを開いたときの RFX 操作の順序を示します。

### <a name="sequence-of-rfx-operations-during-recordset-open"></a><a name="_core_sequence_of_rfx_operations_during_recordset_open"></a>レコードセットを開くときの RFX 操作のシーケンス

|操作|DoFieldExchange 操作|データベース/SQL 操作|
|--------------------|-------------------------------|-----------------------------|
|1. レコードセットを開きます。|||
||2. SQL ステートメントを作成します。||
|||3. SQL を送信します。|
||4. パラメーターのデータメンバーをバインドします。||
||5. フィールドデータメンバーを列にバインドします。||
|||6. ODBC は移動を行い、データを入力します。|
||7. のC++データを修正します。||

レコードセットでは、ODBC の準備実行を使用して、同じ SQL ステートメントで高速の再クエリを実行できます。 準備実行の詳細については、MSDN ライブラリの ODBC SDK*プログラマーリファレンス*を参照してください。

###  <a name="rfx-scrolling"></a><a name="_mfc_rfx.3a_.scrolling"></a>RFX: スクロール

あるレコードから別のレコードにスクロールすると、フレームワークは `DoFieldExchange` を呼び出して、フィールドデータメンバーに以前に格納されていた値を新しいレコードの値に置き換えます。

次の表は、ユーザーがレコード間を移動したときの RFX 操作の順序を示しています。

### <a name="sequence-of-rfx-operations-during-scrolling"></a><a name="_core_sequence_of_rfx_operations_during_scrolling"></a>スクロール中の RFX 操作のシーケンス

|操作|DoFieldExchange 操作|データベース/SQL 操作|
|--------------------|-------------------------------|-----------------------------|
|1. `MoveNext` またはその他の Move 関数のいずれかを呼び出します。|||
|||2. ODBC は移動を行い、データを入力します。|
||3. のC++データを修正します。||

###  <a name="rfx-adding-new-records-and-editing-existing-records"></a><a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a>RFX: 新しいレコードの追加と既存のレコードの編集

新しいレコードを追加すると、レコードセットは、新しいレコードの内容を構築するための編集バッファーとして動作します。 レコードを追加する場合と同様に、レコードを編集するには、レコードセットのフィールドデータメンバーの値を変更する必要があります。 RFX の観点からは、シーケンスは次のようになります。

1. レコードセットの[AddNew](../../mfc/reference/crecordset-class.md#addnew)または[Edit](../../mfc/reference/crecordset-class.md#edit)メンバー関数を呼び出すと、RFX は、後で復元できるように、現在の編集バッファーを格納します。

1. `AddNew` または `Edit` では、RFX が変更されたフィールドデータメンバーを検出できるように、エディットバッファー内のフィールドを準備します。

   新しいレコードには、新しいレコードとの比較に使用する値がないため、では、各フィールドのデータメンバーの値が PSEUDO_NULL の値に設定され `AddNew` ます。 その後、`Update`を呼び出すと、RFX は各データメンバーの値を PSEUDO_NULL の値と比較します。 違いがある場合は、データメンバーが設定されています。 (PSEUDO_NULL は、null 値が true であるレコード列と同じではなく、null とC++同じでもありません)。

   `AddNew`の `Update` の呼び出しとは異なり、`Edit` の `Update` の呼び出しでは、更新された値と以前に格納されていた値が PSEUDO_NULL を使用せずに比較されます。 違いは、`AddNew` には比較のために以前に格納された値がないことです。

1. 値を編集する必要があるフィールドデータメンバーの値、または新しいレコードに入力する値を直接設定します。 これには `SetFieldNull`の呼び出しを含めることができます。

1. [更新](../../mfc/reference/crecordset-class.md#update)を呼び出すと、手順2で説明したように、変更されたフィールドデータメンバーが確認されます (「[スクロール中の RFX 操作の](#_core_sequence_of_rfx_operations_during_scrolling)表」を参照してください)。 何も変更されていない場合、`Update` は0を返します。 一部のフィールドデータメンバーが変更された場合、`Update` は、レコード内のすべての更新されたフィールドの値を含む SQL **INSERT**ステートメントを準備して実行します。

1. `AddNew`の場合、`Update` は、`AddNew` 呼び出しの前に現在あったレコードの以前に格納されていた値を復元することによって終了します。 `Edit`の場合、編集された新しい値はそのまま残ります。

次の表は、新しいレコードを追加したり、既存のレコードを編集したりするときの RFX 操作の順序を示しています。

### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>AddNew および Edit 中の RFX 操作のシーケンス

|操作|DoFieldExchange 操作|データベース/SQL 操作|
|--------------------|-------------------------------|-----------------------------|
|1. `AddNew` または `Edit`を呼び出します。|||
||2. 編集バッファーをバックアップします。||
||3. `AddNew`には、フィールドデータメンバーを "clean" および Null としてマークします。||
|4. レコードセットフィールドのデータメンバーに値を代入します。|||
|5. `Update`を呼び出します。|||
||6. 変更されたフィールドを確認します。||
||7. `Edit`の `AddNew` または**UPDATE**ステートメントの SQL **INSERT**ステートメントを構築します。||
|||8. SQL を送信します。|
||9. `AddNew`には、編集バッファーをバックアップされたコンテンツに復元します。 `Edit`には、バックアップを削除します。||

### <a name="rfx-deleting-existing-records"></a>RFX: 既存のレコードの削除

レコードを削除すると、RFX は、レコードが削除されたことを通知するためにすべてのフィールドを NULL に設定し、そのレコードから移動する必要があります。 その他の RFX シーケンス情報は必要ありません。

## <a name="see-also"></a>参照

[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[MFC ODBC コンシューマー](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[マクロ、グローバル関数、およびグローバル変数](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::D oFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)
