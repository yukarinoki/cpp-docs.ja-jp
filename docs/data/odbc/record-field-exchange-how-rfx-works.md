---
description: '詳細については、「レコードフィールドエクスチェンジ: RFX の動作のしくみ」を参照してください。'
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
ms.openlocfilehash: 81b8d65c4c4f6344456c85ace057ad093c1c18b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268575"
---
# <a name="record-field-exchange-how-rfx-works"></a>レコード フィールド エクスチェンジ: RFX の動作のしくみ

このトピックでは、RFX プロセスについて説明します。 これは高度なトピックです。

- [RFX とレコードセット](#_core_rfx_and_the_recordset)

- [RFX プロセス](#_core_the_record_field_exchange_process)

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` から派生したクラスを対象にしています。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ (Bulk RFX) が実装されます。 Bulk RFX は、RFX に似ています。 違いを理解するには、「レコード [セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="rfx-and-the-recordset"></a><a name="_core_rfx_and_the_recordset"></a> RFX とレコードセット

レコードセットオブジェクトのフィールドデータメンバーは、1つのレコードの選択された列を保持する編集バッファーを構成します。 レコードセットが最初に開かれ、最初のレコードを読み取るときに、RFX は、選択した各列を適切なフィールドデータメンバーのアドレスにバインド (関連付けます) します。 レコードセットがレコードを更新すると、RFX は ODBC API 関数を呼び出して、SQL **UPDATE** または **INSERT** ステートメントをドライバーに送信します。 RFX では、フィールドデータメンバーの知識を使用して、書き込む列を指定します。

フレームワークは、必要に応じてコンテンツを復元できるように、特定の段階で編集バッファーをバックアップします。 RFX は、新しいレコードを追加する前、および既存のレコードを編集する前に、編集バッファーをバックアップします。 たとえば、次の呼び出しの後など、場合によっては編集バッファーを復元し `Update` `AddNew` ます。 を呼び出す前に別のレコードに移動するなどして、新しく変更されたエディットバッファーを破棄した場合、編集バッファーは復元されません `Update` 。

RFX では、データソースとレコードセットのフィールドデータメンバーの間でデータを交換するだけでなく、バインドパラメーターを管理します。 レコードセットが開かれると、すべてのパラメーターデータメンバーが、を構築する SQL ステートメントの "?" プレースホルダーの順序でバインドされ `CRecordset::Open` ます。 詳細については、「 [レコードセット: レコードセットのパラメーター化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。

レコードセットクラスのをオーバーライドすると `DoFieldExchange` 、すべての処理が実行され、双方向のデータが移動します。 ダイアログデータエクスチェンジ (DDX) と同様に、RFX はクラスのデータメンバーに関する情報を必要とします。 ウィザードでは、 `DoFieldExchange` ウィザードで指定したフィールドのデータメンバー名とデータ型に基づいて、レコードセット固有のの実装を作成することによって、必要な情報が提供されます。

## <a name="record-field-exchange-process"></a><a name="_core_the_record_field_exchange_process"></a> レコードフィールドの交換プロセス

このセクションでは、レコードセットオブジェクトが開かれたときと、レコードを追加、更新、および削除したときの RFX イベントのシーケンスについて説明します。 このトピックでは、 [レコードセットが開いている間の Rfx 操作のテーブルシーケンス](#_core_sequence_of_rfx_operations_during_recordset_open) と、このトピックの [スクロール中](#_core_sequence_of_rfx_operations_during_scrolling) の rfx 操作のテーブルシーケンスによって、レコードセット内のコマンドが rfx で処理され、rfx によって更新が管理されていることが示されて `Move` います。 これらのプロセスでは、さまざまな操作を実行するために [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) が呼び出されます。 `m_nOperation` [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクトのデータメンバーによって、どの操作が要求されるかが決まります。 レコードセットを読み取ることが役に立つ場合があります。レコードセットが [レコードを選択する方法 (odbc)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) と [レコードセット: レコードを更新する方法 (odbc)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) については、この資料を参照してください。

### <a name="rfx-initial-binding-of-columns-and-parameters"></a><a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a> RFX: 列とパラメーターの初期バインド

次の RFX アクティビティは、レコードセットオブジェクトの [Open](../../mfc/reference/crecordset-class.md#open) メンバー関数を呼び出すと、示されている順序で発生します。

- レコードセットにパラメーターデータメンバーが含まれている場合、フレームワークはを呼び出し、パラメーターを `DoFieldExchange` レコードセットの SQL ステートメント文字列のパラメータープレースホルダーにバインドします。 パラメーターの値のデータ型に依存する表現は、 **SELECT** ステートメントで見つかった各プレースホルダーに対して使用されます。 これは、SQL ステートメントが準備されてから実行されるまでの間に発生します。 ステートメントの準備の詳細については、 `::SQLPrepare` ODBC *プログラマーリファレンス* の関数を参照してください。

- フレームワークは、 `DoFieldExchange` もう一度を呼び出して、選択した列の値をレコードセット内の対応するフィールドデータメンバーにバインドします。 これにより、レコードセットオブジェクトが、最初のレコードの列を含む編集バッファーとして設定されます。

- レコードセットによって SQL ステートメントが実行され、データソースによって最初のレコードが選択されます。 レコードの列は、レコードセットのフィールドデータメンバーに読み込まれます。

次の表に、レコードセットを開いたときの RFX 操作の順序を示します。

### <a name="sequence-of-rfx-operations-during-recordset-open"></a><a name="_core_sequence_of_rfx_operations_during_recordset_open"></a> レコードセットを開くときの RFX 操作のシーケンス

|操作|DoFieldExchange 操作|データベース/SQL 操作|
|--------------------|-------------------------------|-----------------------------|
|1. レコードセットを開きます。|||
||2. SQL ステートメントを作成します。||
|||3. SQL を送信します。|
||4. パラメーターのデータメンバーをバインドします。||
||5. フィールドデータメンバーを列にバインドします。||
|||6. ODBC は移動を行い、データを入力します。|
||7. C++ のデータを修正します。||

レコードセットでは、ODBC の準備実行を使用して、同じ SQL ステートメントで高速の再クエリを実行できます。 準備実行の詳細については、 [ODBC プログラマーズリファレンス](/sql/odbc/reference/odbc-programmer-s-reference)を参照してください。

### <a name="rfx-scrolling"></a><a name="_mfc_rfx.3a_.scrolling"></a> RFX: スクロール

あるレコードから別のレコードにスクロールすると、フレームワークはを呼び出して、 `DoFieldExchange` フィールドデータメンバーに以前に格納されていた値を新しいレコードの値に置き換えます。

次の表は、ユーザーがレコード間を移動したときの RFX 操作の順序を示しています。

### <a name="sequence-of-rfx-operations-during-scrolling"></a><a name="_core_sequence_of_rfx_operations_during_scrolling"></a> スクロール中の RFX 操作のシーケンス

|操作|DoFieldExchange 操作|データベース/SQL 操作|
|--------------------|-------------------------------|-----------------------------|
|1. `MoveNext` またはその他の Move 関数のいずれかを呼び出します。|||
|||2. ODBC は移動を行い、データを入力します。|
||3. C++ のデータを修正します。||

### <a name="rfx-adding-new-records-and-editing-existing-records"></a><a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a> RFX: 新しいレコードの追加と既存のレコードの編集

新しいレコードを追加すると、レコードセットは、新しいレコードの内容を構築するための編集バッファーとして動作します。 レコードを追加する場合と同様に、レコードを編集するには、レコードセットのフィールドデータメンバーの値を変更する必要があります。 RFX の観点からは、シーケンスは次のようになります。

1. レコードセットの [AddNew](../../mfc/reference/crecordset-class.md#addnew) または [Edit](../../mfc/reference/crecordset-class.md#edit) メンバー関数を呼び出すと、RFX は、後で復元できるように、現在の編集バッファーを格納します。

1. `AddNew` または、 `Edit` RFX が変更されたフィールドデータメンバーを検出できるように、編集バッファー内のフィールドを準備します。

   新しいレコードには、と新しいレコードを比較するための以前の値がないため、では、 `AddNew` 各フィールドデータメンバーの値が PSEUDO_NULL 値に設定されます。 その後、を呼び出すと `Update` 、RFX は各データメンバーの値を PSEUDO_NULL 値と比較します。 違いがある場合は、データメンバーが設定されています。 (PSEUDO_NULL は、Null 値が true のレコード列と同じではなく、C++ NULL と同じでもありません)。

   の呼び出しとは異なり `Update` `AddNew` 、 `Update` の呼び出しは、 `Edit` 更新された値と、PSEUDO_NULL を使用するのではなく、以前に格納された値とを比較します。 違いは、には `AddNew` 比較のために以前に格納された値がないことです。

1. 値を編集する必要があるフィールドデータメンバーの値、または新しいレコードに入力する値を直接設定します。 これには、を呼び出すことができ `SetFieldNull` ます。

1. [更新](../../mfc/reference/crecordset-class.md#update)を呼び出すと、手順2で説明したように、変更されたフィールドデータメンバーが確認されます (「[スクロール中の RFX 操作の](#_core_sequence_of_rfx_operations_during_scrolling)表」を参照してください)。 何も変更されていない場合、は `Update` 0 を返します。 一部のフィールドデータメンバーが変更されている場合、は、 `Update` レコード内のすべての更新されたフィールドの値を含む SQL **INSERT** ステートメントを準備して実行します。

1. の場合 `AddNew` 、は、 `Update` 呼び出しの前に現在あったレコードの以前に格納されていた値を復元することによって終了 `AddNew` します。 では、編集され `Edit` た新しい値はそのまま残ります。

次の表は、新しいレコードを追加したり、既存のレコードを編集したりするときの RFX 操作の順序を示しています。

### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>AddNew および Edit 中の RFX 操作のシーケンス

|操作|DoFieldExchange 操作|データベース/SQL 操作|
|--------------------|-------------------------------|-----------------------------|
|1. `AddNew` または `Edit` を呼び出します。|||
||2. 編集バッファーをバックアップします。||
||3. の場合 `AddNew` は、フィールドのデータメンバーを "clean" および Null としてマークします。||
|4. レコードセットフィールドのデータメンバーに値を代入します。|||
|5. を呼び出し `Update` ます。|||
||6. 変更されたフィールドを確認します。||
||7.  `AddNew` またはの **UPDATE** ステートメントの SQL INSERT ステートメントをビルド `Edit` します。||
|||8. SQL を送信します。|
||9. `AddNew` では、編集バッファーをバックアップされたコンテンツに復元します。 の場合は、 `Edit` バックアップを削除します。||

### <a name="rfx-deleting-existing-records"></a>RFX: 既存のレコードの削除

レコードを削除すると、RFX は、レコードが削除されたことを通知するためにすべてのフィールドを NULL に設定し、そのレコードから移動する必要があります。 その他の RFX シーケンス情報は必要ありません。

## <a name="see-also"></a>関連項目

[レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[MFC ODBC コンシューマー](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[マクロ、グローバル関数、およびグローバル変数](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::D oFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)
