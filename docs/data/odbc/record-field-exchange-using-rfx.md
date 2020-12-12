---
description: '詳細については、「レコードフィールドエクスチェンジ: RFX の使用」を参照してください。'
title: 'レコード フィールド エクスチェンジ: RFX の使い方'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: 9ded7bc2a10bc37f7f1f835f8706d385b543af9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298800"
---
# <a name="record-field-exchange-using-rfx"></a>レコード フィールド エクスチェンジ: RFX の使い方

このトピックでは、フレームワークの動作に関連する RFX の使用方法について説明します。

> [!NOTE]
> このトピックは、一括行フェッチが実装されていない [CRecordset](../../mfc/reference/crecordset-class.md) から派生したクラスに適用されます。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ (Bulk RFX) が実装されます。 Bulk RFX は、RFX に似ています。 違いを理解するには、「レコード [セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

次のトピックには、関連情報が含まれています。

- [レコードフィールドエクスチェンジ: ウィザードコードを使用](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) すると、rfx の主要なコンポーネントが導入され、Mfc アプリケーションウィザードと **追加クラス** (「 [mfc ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照) と、rfx をサポートするための記述、およびウィザードコードの変更方法が説明されています。

- [レコードフィールドエクスチェンジ: Rfx 関数を使用](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) すると、オーバーライドで rfx 関数の呼び出しを記述する方法について説明 `DoFieldExchange` します。

次の表は、フレームワークの役割に関連するロールを示しています。

### <a name="using-rfx-you-and-the-framework"></a>RFX の使用: ユーザーとフレームワーク

|自分|フレームワークの役割|
|---------|-------------------|
|ウィザードを使用して、レコードセットクラスを宣言します。 フィールドデータメンバーの名前とデータ型を指定します。|このウィザードは、クラスを派生させる `CRecordset` と共に、各フィールドデータメンバーの RFX 関数呼び出しを含む、 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) override を書き込みます。|
|Optional必要なパラメーターデータメンバーをクラスに手動で追加します。 各パラメーターデータメンバーに対して RFX 関数呼び出しを手動で追加し `DoFieldExchange` 、パラメーターのグループに対して [CFieldExchange:: SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) への呼び出しを追加し、 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)のパラメーターの合計数を指定します。 「 [レコードセット: レコードセットのパラメーター化 (ODBC)」を](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)参照してください。||
|Optionalフィールドデータメンバーに追加の列を手動でバインドします。 [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields)を手動でインクリメントします。 「 [レコードセット: データ列を動的にバインドする (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。||
|レコードセットクラスのオブジェクトを構築します。 オブジェクトを使用する前に、パラメーターデータメンバー (存在する場合) の値を設定します。|効率を上げるために、フレームワークは ODBC を使用してパラメーターを事前にバインドします。 パラメーター値を渡すと、フレームワークによってデータソースに渡されます。 並べ替えやフィルター文字列が変更されていない限り、再クエリにはパラメーター値のみが送信されます。|
|[CRecordset:: open](../../mfc/reference/crecordset-class.md#open)を使用して、レコードセットオブジェクトを開きます。|レコードセットのクエリを実行し、列をレコードセットのフィールドデータメンバーにバインドし、を呼び出して、 `DoFieldExchange` 最初に選択したレコードとレコードセットのフィールドデータメンバーとの間でデータを交換します。|
|[CRecordset:: Move](../../mfc/reference/crecordset-class.md#move)またはメニューまたはツールバーのコマンドを使用して、レコードセットをスクロールします。|`DoFieldExchange`を呼び出して、新しい現在のレコードからフィールドデータメンバーにデータを転送します。|
|レコードを追加、更新、および削除します。|データ `DoFieldExchange` ソースにデータを転送するためにを呼び出します。|

## <a name="see-also"></a>関連項目

[レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[レコードセット: 合計およびその他の集計結果の取得 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)<br/>
[マクロ、グローバル関数、およびグローバル変数](../../mfc/reference/mfc-macros-and-globals.md)
