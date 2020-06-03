---
title: 'レコード フィールド エクスチェンジ: RFX の使い方'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: dc0cdcee758f4842b0738068a8a11c4e2e404155
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367144"
---
# <a name="record-field-exchange-using-rfx"></a>レコード フィールド エクスチェンジ: RFX の使い方

このトピックでは、フレームワークの動作に関連して RFX を使用する方法について説明します。

> [!NOTE]
> このトピックは、バルク行フェッチが実装されていない[CRecordset](../../mfc/reference/crecordset-class.md)から派生したクラスに適用されます。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ (Bulk RFX) が実装されます。 Bulk RFX は、RFX に似ています。 この違いについては、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

以下のトピックには、関連情報が含まれています。

- [レコード フィールド エクスチェンジ: ウィザード コードの操作](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)では、RFX の主要なコンポーネントを紹介し、MFC アプリケーション ウィザードと**クラスの追加**(MFC [ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)を参照) が RFX をサポートするために記述するコードと、ウィザード コードの変更方法について説明します。

- [レコード フィールド エクスチェンジ: RFX 関数を使用して](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)、上書き`DoFieldExchange`の RFX 関数への呼び出しを記述する方法について説明します。

次の表は、フレームワークがあなたのために行う役割を示しています。

### <a name="using-rfx-you-and-the-framework"></a>RFX の使用: あなたとフレームワーク

|あなたが|フレームワークの役割|
|---------|-------------------|
|ウィザードを使用してレコードセット クラスを宣言します。 フィールド データ メンバーの名前とデータ型を指定します。|ウィザードはクラスを`CRecordset`派生させ、各フィールド データ メンバーの RFX 関数呼び出しを含む[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)オーバーライドを書き込みます。|
|(オプション)必要なパラメーター データ メンバーをクラスに手動で追加します。 パラメーター データ メンバーごとに RFX 関数呼び出しを`DoFieldExchange`手動で追加し、パラメーターのグループに対して[CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)への呼び出しを追加し[、m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)でパラメーターの合計数を指定します。 [「レコードセット: レコードセットのパラメータ化 (ODBC)」](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)を参照してください。||
|(オプション)フィールド データ メンバーに追加の列を手動でバインドします。 m_nFields手動[でインク](../../mfc/reference/crecordset-class.md#m_nfields)リメントします。 [「レコードセット: データ列の動的連結 (ODBC)」](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)を参照してください。||
|レコードセット クラスのオブジェクトを構築します。 オブジェクトを使用する前に、パラメーター データ メンバーの値を設定します (存在する場合)。|効率を高めるには、フレームワークは ODBC を使用してパラメーターを事前にバインドします。 パラメーター値を渡すと、フレームワークはデータ ソースに渡します。 並べ替え文字列やフィルタ文字列が変更されていない限り、再クエリの場合はパラメータ値のみが送信されます。|
|レコードセット オブジェクトを[開くには、次の操作を行います](../../mfc/reference/crecordset-class.md#open)。|レコードセットのクエリを実行し、列をレコードセットのフィールド データ メンバにバインド`DoFieldExchange`し、最初に選択したレコードとレコードセットのフィールド データ メンバとの間でデータを交換する呼び出しを行います。|
|レコードセットをスクロールするには[、CRecordset::移動](../../mfc/reference/crecordset-class.md#move)またはメニューまたはツールバーコマンドを使用します。|新`DoFieldExchange`しいカレント レコードからフィールド データ メンバーにデータを転送する呼び出し。|
|レコードの追加、更新、および削除を行います。|データ`DoFieldExchange`をデータ ソースに転送するための呼び出し。|

## <a name="see-also"></a>関連項目

[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[レコードセット: 集計値の計算 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)<br/>
[クラス](../../mfc/reference/cfieldexchange-class.md)<br/>
[マクロ、グローバル関数、およびグローバル変数](../../mfc/reference/mfc-macros-and-globals.md)
