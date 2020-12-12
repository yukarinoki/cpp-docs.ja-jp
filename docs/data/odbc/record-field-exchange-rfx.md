---
description: 詳細については、「レコードフィールドエクスチェンジ (RFX)」を参照してください。
title: レコード フィールド エクスチェンジ (RFX)
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
ms.openlocfilehash: d181d779f74096dc035e9d492e50ef1823982b24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298891"
---
# <a name="record-field-exchange-rfx"></a>レコード フィールド エクスチェンジ (RFX)

MFC ODBC データベースクラスは、データソースと [レコードセット](../../data/odbc/recordset-odbc.md) オブジェクトの間のデータの移動を自動化します。 [CRecordset](../../mfc/reference/crecordset-class.md)からクラスを派生させ、バルク行フェッチを使用しない場合、データはレコードフィールドエクスチェンジ (RFX) メカニズムによって転送されます。

> [!NOTE]
> 派生クラスでバルク行フェッチを実装している場合、フレームワークでは、 `CRecordset` 一括レコードフィールドエクスチェンジ (BULK RFX) メカニズムを使用してデータを転送します。 詳細については、「レコード [セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

RFX は、ダイアログデータエクスチェンジ (DDX) に似ています。 データソースとレコードセットのフィールドデータメンバーの間でデータを移動するには、レコードセットの [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 関数を複数回呼び出す必要があります。また、フレームワークと [ODBC](../../data/odbc/odbc-basics.md)の間にはかなりのやり取りが必要です。 RFX 機構はタイプセーフであり、などの ODBC 関数を呼び出す作業を保存し `::SQLBindCol` ます。 DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

RFX は、ほとんどの場合、ユーザーにとって透過的です。 MFC アプリケーションウィザードを使用して、またはクラスを **追加** して (「 [mfc ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」の説明に従って)、レコードセットクラスを宣言すると、RFX が自動的に組み込まれます。 レコードセットクラスは、 `CRecordset` フレームワークによって提供される基本クラスから派生する必要があります。 MFC アプリケーションウィザードでは、最初のレコードセットクラスを作成できます。 **クラスの追加** では、必要に応じて他のレコードセットクラスを追加できます。 詳細と例については、「 [MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照してください。

次のような場合は、3つのケースで少量の RFX コードを手動で追加する必要があります。

- パラメーター化クエリを使用します。 詳細については、「 [レコードセット: レコードセットのパラメーター化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。

- 結合を実行します (2 つ以上のテーブルの列に対して1つのレコードセットを使用します)。 詳細については、「 [レコードセット: 結合の実行 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)」を参照してください。

- データ列を動的にバインドします。 これは、パラメーター化よりも一般的ではありません。 詳細については、「 [レコードセット: データ列の動的なバインド (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。

RFX に関するより高度な知識が必要な場合は、「 [レコードフィールドエクスチェンジ: rfx の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

次のトピックでは、レコードセットオブジェクトの使用方法の詳細について説明します。

- [レコードフィールドエクスチェンジ: RFX の使用](../../data/odbc/record-field-exchange-using-rfx.md)

- [レコードフィールドエクスチェンジ: RFX 関数の使用](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

- [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)

## <a name="see-also"></a>関連項目

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[MFC ODBC コンシューマー](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[[データベースサポート] (MFC アプリケーションウィザード)](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)
