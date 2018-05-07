---
title: 'レコード フィールド エクス チェンジ: RFX の動作方法 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record editing [C++], using RFX
- RFX (ODBC) [C++], updating data in recordsets
- scrolling [C++]
- ODBC [C++], RFX
- data binding [C++], DFX
- scrolling [C++], RFX
- RFX (ODBC) [C++], binding fields and parameters
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 48cece77101a14efb827e48b53be2f5852df83ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="record-field-exchange-how-rfx-works"></a>レコード フィールド エクスチェンジ: RFX の動作のしくみ
このトピックでは、RFX プロセスについて説明します。 これは、高度なトピック。  
  
-   [RFX とレコード セット](#_core_rfx_and_the_recordset)  
  
-   [RFX プロセス](#_core_the_record_field_exchange_process)  
  
> [!NOTE]
>  このトピックの対象から派生したクラス`CRecordset`バルク行フェッチは実装されていません。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクス チェンジ (Bulk RFX) が実装されます。 バルク rfx 関数は rfx 関数に似ています。 相違点を理解するのを参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
##  <a name="_core_rfx_and_the_recordset"></a> RFX とレコード セット  
 まとめると、レコード セット オブジェクトのフィールド データ メンバーは、1 つのレコードの選択した列を保持するエディット バッファーを構成します。 レコード セットを最初に開くしようとしている最初のレコードを読み取り、ときに結び付けられます) 各は、適切なフィールド データ メンバーのアドレスへの列を選択します。 RFX が SQL を送信する ODBC API 関数を呼び出す更新すると、レコード セットのレコード、**更新**または**挿入**ドライバーにステートメントです。 Rfx 関数では、フィールド データ メンバーの情報を使用して、記述する列を指定します。  
  
 フレームワーク バックアップ エディット バッファー任意の段階で必要な場合、その内容を復元できるようにします。 Rfx 関数は、新しいレコードを追加する前に、既存のレコードを編集する前に、エディット バッファーをバックアップします。 例については、いくつかの場合、エディット バッファーの後に復元されます、**更新**呼び出し次`AddNew`です。 破棄した場合、新しく変更された編集バッファーなどを呼び出す前に別のレコードに移動エディット バッファーは復元されません**更新**です。  
  
 データ ソースとレコード セットのフィールド データ メンバーの間でデータを交換するには、以外は、RFX は、バインド パラメーターを管理します。 順序でパラメーター データ メンバーがバインドされるレコード セットを開いたときに、"?"SQL ステートメント内のプレース ホルダーを`CRecordset::Open`を構築します。 詳細については、次を参照してください。[レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)です。  
  
 レコード セット クラスのオーバーライド`DoFieldExchange`双方向のデータの移動、すべての作業を行います。 ダイアログ データ エクス チェンジ (DDX) と同様には、RFX には、クラスのデータ メンバーに関する情報が必要があります。 ウィザードのレコード セットに固有の実装を記述して、必要な情報を提供する`DoFieldExchange`フィールドのデータに基づいて、ウィザードで指定したメンバーの名前とデータ型。  
  
##  <a name="_core_the_record_field_exchange_process"></a> レコード フィールドの交換プロセス  
 RFX イベントの順序、レコード セット オブジェクトが開かれていると説明を追加すると、更新、およびレコードを削除します。 テーブル[レコード セットを開くときの RFX 操作のシーケンス](#_core_sequence_of_rfx_operations_during_recordset_open)とテーブル[スクロールを行うときの RFX 操作のシーケンス](#_core_sequence_of_rfx_operations_during_scrolling)このトピックでは、RFX プロセスとして、プロセスを表示します、**移動**。レコード セットのコマンドと RFX は更新プログラムの管理します。 これらのプロセス中に[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)を呼び出してさまざまな操作を実行します。 **M_nOperation**のデータ メンバー、 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクトは、必要な操作を決定します。 役に立つことを読み取る[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)と[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)説明を読む前にします。  
  
###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a> 列とパラメーターの RFX: 最初のバインド  
 レコード セット オブジェクトを呼び出すと、示されている順序で、次の RFX アクティビティが発生する[開く](../../mfc/reference/crecordset-class.md#open)メンバー関数。  
  
-   レコード セットにパラメーター データ メンバーがある場合、フレームワークによって呼び出されます`DoFieldExchange`レコード セットの SQL ステートメント文字列内のパラメーターのプレース ホルダーにパラメーターをバインドします。 各プレース ホルダーのパラメーターの値の型に依存する形式が使用されるデータを検出、**選択**ステートメントです。 これは、SQL ステートメントが準備されてが実行される前に発生します。 ステートメントの準備については、次を参照してください。、 **:: SQLPrepare**関数、ODBC で*プログラマーズ リファレンス*です。  
  
-   フレームワークによって`DoFieldExchange`レコード セット内の対応するフィールド データ メンバーを選択した列の値をバインドする 2 番目の時間。 これにより、レコード セット オブジェクトが最初のレコードの列を含むエディット バッファーとして確立されます。  
  
-   レコード セットは、SQL ステートメントを実行し、データ ソースは、最初のレコードを選択します。 レコード セットのフィールド データ メンバーには、レコードの列が読み込まれます。  
  
 次の表は、レコード セットを開くときに、RFX 操作のシーケンスを示します。  
  
### <a name="_core_sequence_of_rfx_operations_during_recordset_open"></a> レコード セットを開くときの RFX 処理のシーケンス  
  
|操作|DoFieldExchange 操作|データベースと SQL の操作|  
|--------------------|-------------------------------|-----------------------------|  
|1.レコード セットを開きます。|||  
||2.SQL ステートメントを作成します。||  
|||3.SQL を送信します。|  
||4.パラメーター データ メンバーを連結します。||  
||5.フィールド データ メンバーは、列にバインドします。||  
|||6.ODBC は、移動を行い、データを入力します。|  
||7.C++ のデータを修正します。||  
  
 レコード セットでは、ODBC の準備実行を使用して、同じ SQL ステートメントを使用して高速なクエリを再実行を許可します。 準備実行の詳細については、ODBC SDK を参照してください。*プログラマーズ リファレンス*、MSDN ライブラリです。  
  
###  <a name="_mfc_rfx.3a_.scrolling"></a> RFX: スクロール  
 1 つのレコードから別にスクロールするときに、フレームワークによって呼び出されます`DoFieldExchange`新しいレコードの値を持つフィールド データ メンバーに格納されていた値を置き換えます。  
  
 次の表は、ユーザーがレコード間を移動すると、RFX 操作のシーケンスを示します。  
  
### <a name="_core_sequence_of_rfx_operations_during_scrolling"></a> スクロール中に RFX 処理の流れ  
  
|操作|DoFieldExchange 操作|データベースと SQL の操作|  
|--------------------|-------------------------------|-----------------------------|  
|1.呼び出す`MoveNext`またはその他の移動機能の 1 つです。|||  
|||2.ODBC は、移動を行い、データを入力します。|  
||3.C++ のデータを修正します。||  
  
###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a> RFX: が新しいレコードを追加して、既存のレコードの編集  
 新しいレコードを追加する場合、レコード セットは、新しいレコードの内容を構築するエディット バッファーとして動作します。 同様にレコードを追加すると、レコードの編集は、レコード セットのフィールド データ メンバーの値を変更します。 RFX の観点から、シーケンスのとおりです。  
  
1.  レコード セットへの呼び出し[AddNew](../../mfc/reference/crecordset-class.md#addnew)または[編集](../../mfc/reference/crecordset-class.md#edit)メンバー関数は、後で復元できるように、現在の編集のバッファーを格納する RFX が発生します。  
  
2.  `AddNew` または**編集**RFX が変更されたフィールド データ メンバーを検出できるように編集バッファー内のフィールドを準備します。  
  
     新しいレコードには、新しいものを比較する前の値があるないため`AddNew`する各フィールド データ メンバーの値を設定、 **PSEUDO_** 値。 その後、呼び出すときに**更新**、RFX を持つ各データ メンバーの値を比較し、 **PSEUDO_** 値。 違いがある場合、データ メンバーが設定されています。 (**PSEUDO_** ではなく true Null 値を持つレコード列と同じもこれらのいずれかは、C++ と同じ**NULL**)。  
  
     異なり、**更新**に対して呼び出す`AddNew`、**更新**に対して呼び出す**編集**を使用するのではなく、以前に格納された値で更新された値を比較して**PSEUDO_** です。 その違いは`AddNew`比較については以前に格納された値がありません。  
  
3.  直接の値を編集するか、新しいレコードに入力することは、フィールド データ メンバーの値を設定します。 これは、呼び出しを含めることができます`SetFieldNull`です。  
  
4.  呼び出す[更新](../../mfc/reference/crecordset-class.md#update)手順 2 の説明に従って、変更されたフィールド データ メンバーのチェック (表を参照して[スクロールを行うときの RFX 操作のシーケンス](#_core_sequence_of_rfx_operations_during_scrolling))。 [なし] が変更された場合、**更新**0 を返します。 フィールド データ メンバーが変更された場合、**更新**を準備して、SQL の実行**挿入**レコード内のすべての更新されたフィールドの値を含むステートメント。  
  
5.  `AddNew`、**更新**が終了する前に現在のレコードの保存済みの値を復元して、`AddNew`呼び出します。 **編集**で、編集後の新しい値が保持されます。  
  
 次の表は、新しいレコードを追加または既存のレコードを編集するときに、RFX 操作のシーケンスを示します。  
  
### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>AddNew を編集中の RFX 操作のシーケンス  
  
|操作|DoFieldExchange 操作|データベースと SQL の操作|  
|--------------------|-------------------------------|-----------------------------|  
|1.呼び出す`AddNew`または**編集**です。|||  
||2.エディット バッファーをバックアップします。||  
||3.`AddNew`フィールド データ メンバー「クリーン」としてマーク、および Null です。||  
|4.レコード セットのフィールド データ メンバーに値を割り当てます。|||  
|5.呼び出す**更新**です。|||  
||6.変更されたフィールドを確認します。||  
||7.SQL をビルド**挿入**のステートメント`AddNew`または**更新**の声明**編集**です。||  
|||8.SQL を送信します。|  
||9.`AddNew`、そのバックアップ内容をエディット バッファーを復元します。 **編集**バックアップを削除します。||  
  
### <a name="rfx-deleting-existing-records"></a>RFX: 既存のレコードを削除します。  
 レコードを削除するときに、すべてのフィールドに設定 RFX **NULL**なおに、レコードが削除されたことをオフに移動する必要があります。 その他の RFX シーケンス情報が不要です。  
  
## <a name="see-also"></a>関連項目  
 [レコード フィールド エクス (チェンジ RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [MFC ODBC コンシューマーします。](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [マクロ、グローバル関数、およびグローバル変数](../../mfc/reference/mfc-macros-and-globals.md)  
 [CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)