---
title: 'レコード フィールド エクスチェンジ: RFX の使い方'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: 70197d2a9130388e86bb94f0d670360bb35febeb
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075861"
---
# <a name="record-field-exchange-using-rfx"></a>レコード フィールド エクスチェンジ: RFX の使い方

このトピックでは、フレームワークの動作に関連する RFX の使用方法について説明します。

> [!NOTE]
>  このトピックは、一括行フェッチが実装されていない[CRecordset](../../mfc/reference/crecordset-class.md)から派生したクラスに適用されます。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ (Bulk RFX) が実装されます。 Bulk RFX は、RFX に似ています。 違いを理解するには、「レコード[セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

次のトピックには、関連情報が含まれています。

- [レコードフィールドエクスチェンジ: ウィザードコードを使用](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)すると、rfx の主要なコンポーネントが導入され、Mfc アプリケーションウィザードと**追加クラス**(「 [mfc ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照) と、rfx をサポートするための記述、およびウィザードコードの変更方法が説明されています。

- [レコードフィールドエクスチェンジ: Rfx 関数を使用](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)すると、`DoFieldExchange` オーバーライドで rfx 関数の呼び出しを記述する方法について説明します。

次の表は、フレームワークの役割に関連するロールを示しています。

### <a name="using-rfx-you-and-the-framework"></a>RFX の使用: ユーザーとフレームワーク

|あなたが|フレームワークの役割|
|---------|-------------------|
|ウィザードを使用して、レコードセットクラスを宣言します。 フィールドデータメンバーの名前とデータ型を指定します。|このウィザードでは、`CRecordset` クラスを派生させると共に、各フィールドデータメンバーの RFX 関数呼び出しを含む[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) override を書き込みます。|
|Optional必要なパラメーターデータメンバーをクラスに手動で追加します。 パラメーターデータメンバーごとに `DoFieldExchange` に RFX 関数呼び出しを手動で追加し、パラメーターのグループに対して[CFieldExchange:: SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)への呼び出しを追加し、 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)のパラメーターの合計数を指定します。 「[レコードセット: レコードセットのパラメーター化 (ODBC)」を](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)参照してください。||
|Optionalフィールドデータメンバーに追加の列を手動でバインドします。 [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields)を手動でインクリメントします。 「[レコードセット: データ列を動的にバインドする (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。||
|レコードセットクラスのオブジェクトを構築します。 オブジェクトを使用する前に、パラメーターデータメンバー (存在する場合) の値を設定します。|効率を上げるために、フレームワークは ODBC を使用してパラメーターを事前にバインドします。 パラメーター値を渡すと、フレームワークによってデータソースに渡されます。 並べ替えやフィルター文字列が変更されていない限り、再クエリにはパラメーター値のみが送信されます。|
|[CRecordset:: open](../../mfc/reference/crecordset-class.md#open)を使用して、レコードセットオブジェクトを開きます。|レコードセットのクエリを実行し、列をレコードセットのフィールドデータメンバーにバインドし、`DoFieldExchange` を呼び出して、最初に選択したレコードとレコードセットのフィールドデータメンバーとの間でデータを交換します。|
|[CRecordset:: Move](../../mfc/reference/crecordset-class.md#move)またはメニューまたはツールバーのコマンドを使用して、レコードセットをスクロールします。|新しい現在のレコードからフィールドデータメンバーにデータを転送するために `DoFieldExchange` を呼び出します。|
|レコードを追加、更新、および削除します。|データをデータソースに転送するために `DoFieldExchange` を呼び出します。|

## <a name="see-also"></a>参照

[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[レコードセット: 集計値の計算 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)<br/>
[マクロ、グローバル関数、およびグローバル変数](../../mfc/reference/mfc-macros-and-globals.md)
