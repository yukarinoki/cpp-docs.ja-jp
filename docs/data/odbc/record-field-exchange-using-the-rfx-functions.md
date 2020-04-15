---
title: 'レコード フィールド エクスチェンジ: RFX 関数の使い方'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
ms.openlocfilehash: f1afded360cfeff564f1f3d8bb9b294aa33cb733
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367132"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>レコード フィールド エクスチェンジ: RFX 関数の使い方

このトピックでは、オーバーライドの本体を構成する RFX 関数呼び出`DoFieldExchange`しの使用方法について説明します。

> [!NOTE]
> このトピックは、バルク行フェッチが実装されていない[CRecordset](../../mfc/reference/crecordset-class.md)から派生したクラスに適用されます。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ (Bulk RFX) が実装されます。 Bulk RFX は、RFX に似ています。 この違いについては、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

RFX グローバル関数は、データ ソースの列とレコードセットのフィールド データ メンバーの間でデータを交換します。 RFX 関数呼び出しは、レコードセットの[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)メンバー関数に記述します。 このトピックでは、RFX 関数が使用可能なデータ型について簡単に説明します。 [テクニカル ノート 43](../../mfc/tn043-rfx-routines.md)では、追加のデータ型に対して独自の RFX 関数を記述する方法について説明します。

## <a name="rfx-function-syntax"></a><a name="_core_rfx_function_syntax"></a>RFX 関数の構文

各 RFX 関数は、3 つのパラメータを受け取ります (オプションの 4 番目または 5 番目のパラメータを受け取る関数もあります)。

- [オブジェクト](../../mfc/reference/cfieldexchange-class.md)へのポインター。 渡されたポインターに`pFX`沿って渡す`DoFieldExchange`だけです。

- データ ソースに表示される列の名前。

- レコードセット クラス内の対応するフィールド データ メンバまたはパラメータ データ メンバの名前。

- (オプション)関数の中には、転送される文字列または配列の最大長。 これはデフォルトで 255 バイトですが、変更したい場合もあります。 最大サイズは`CString`、オブジェクトの最大サイズ **(INT_MAX** (2,147,483,647 バイト) に基づきますが、おそらくそのサイズより前にドライバーの制限が発生します。

- (オプション)この関数`RFX_Text`では、列のデータ型を指定するために 5 番目のパラメーターを使用することがあります。

詳細については、『*クラス ライブラリ リファレンス*』の[「マクロとグローバル」](../../mfc/reference/mfc-macros-and-globals.md)の RFX 関数を参照してください。 パラメーターを特別に使用する場合の例については、「[レコードセット: SUM およびその他の集計結果の取得 (ODBC)」](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)を参照してください。

## <a name="rfx-data-types"></a><a name="_core_rfx_data_types"></a>RFX データ型

クラス ライブラリには、データ ソースとレコードセットの間でさまざまなデータ型を転送するための RFX 関数が用意されています。 次の一覧は、データ型別の RFX 関数をまとめたものです。 独自の RFX 関数呼び出しを記述する必要がある場合は、データ型別にこれらの関数を選択します。

|機能|データ型|
|--------------|---------------|
|`RFX_Bool`|**Bool**|
|`RFX_Byte`|**バイト**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**double**|
|`RFX_Single`|**float**|
|`RFX_Int`|**int**|
|`RFX_Long`|**長い**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|

詳細については、『*クラス ライブラリ リファレンス*』の[「マクロとグローバル」](../../mfc/reference/mfc-macros-and-globals.md)の RFX 関数のドキュメントを参照してください。 C++ データ型を SQL データ型にマップする方法については、「SQL SQL データ型[(ODBC) の](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)C++ データ型にマップされた ANSI SQL データ型」を参照してください。

## <a name="see-also"></a>関連項目

[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[レコードセット: パラメーターを利用したレコードセット (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[レコードセット: データ列を動的に結びつける方法 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)<br/>
[クラス](../../mfc/reference/cfieldexchange-class.md)
