---
title: レコード フィールド エクスチェンジ (RFX)
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
ms.openlocfilehash: 6f965b90e1e0bbcfd3ad04bb5b40644d61050b2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367159"
---
# <a name="record-field-exchange-rfx"></a>レコード フィールド エクスチェンジ (RFX)

MFC ODBC データベース クラスは、データ ソースと[レコードセット](../../data/odbc/recordset-odbc.md)オブジェクト間のデータ移動を自動化します。 [CRecordset](../../mfc/reference/crecordset-class.md)からクラスを派生し、バルク行フェッチを使用しない場合、データはレコード フィールド エクスチェンジ (RFX) メカニズムによって転送されます。

> [!NOTE]
> 派生`CRecordset`クラスでバルク行フェッチを実装している場合、フレームワークは、バルク レコード フィールド エクスチェンジ (Bulk RFX) メカニズムを使用してデータを転送します。 詳細については、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

RFX は、ダイアログ データ エクスチェンジ (DDX) に似ています。 データ ソースとレコードセットのフィールド データ メンバー間でデータを移動するには、レコードセットの[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)関数を複数回呼び出し、フレームワークと[ODBC](../../data/odbc/odbc-basics.md)との間での多大なやり取りが必要です。 RFX メカニズムはタイプ セーフであり、などの ODBC 関数を呼び出`::SQLBindCol`す作業を省きます。 DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

RFXは、ほとんどあなたに透明です。 MFC アプリケーション ウィザードまたは**クラスの追加**(MFC [ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)で説明) を使用してレコードセット クラスを宣言すると、RFX は自動的に組み込まれます。 レコードセット クラスは、フレームワークによって提供される`CRecordset`基本クラスから派生する必要があります。 MFC アプリケーション ウィザードを使用すると、初期レコードセット クラスを作成できます。 **クラスの追加**では、必要に応じて他のレコードセット クラスを追加できます。 詳細と例については[、「MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照してください。

次の場合に、次の 3 つのケースで少量の RFX コードを手動で追加する必要があります。

- パラメータ化クエリを使用します。 詳細については、「[レコードセット : レコードセットのパラメータ化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。

- 結合を実行する (複数のテーブルの列に 1 つのレコードセットを使用する)。 詳細については、「[レコードセット : 結合の実行 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)」を参照してください。

- データ列を動的にバインドします。 これは、パラメーター化よりも一般的ではありません。 詳細については、「[レコードセット : データ列の動的なバインド (ODBC)」](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)を参照してください。

RFX についてより高度な理解が必要な場合は、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。

次のトピックでは、レコードセット オブジェクトの使用方法について説明します。

- [レコード フィールド エクスチェンジ: RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)

- [レコード フィールド エクスチェンジ: RFX 関数の使い方](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

- [レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)

## <a name="see-also"></a>関連項目

[データベース接続を開く (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[MFC ODBC コンシューマー](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[データベース サポート、MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)
