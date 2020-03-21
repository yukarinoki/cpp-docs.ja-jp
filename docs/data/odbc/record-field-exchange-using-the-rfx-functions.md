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
ms.openlocfilehash: a54dbc10e80e19f744bb58c23639a4376156d2e7
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077092"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>レコード フィールド エクスチェンジ: RFX 関数の使い方

このトピックでは、`DoFieldExchange` オーバーライドの本体を構成する RFX 関数呼び出しの使用方法について説明します。

> [!NOTE]
>  このトピックは、一括行フェッチが実装されていない[CRecordset](../../mfc/reference/crecordset-class.md)から派生したクラスに適用されます。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ (Bulk RFX) が実装されます。 Bulk RFX は、RFX に似ています。 違いを理解するには、「レコード[セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

RFX グローバル関数は、データソースの列とレコードセットのフィールドデータメンバーの間でデータを交換します。 RFX 関数呼び出しをレコードセットの[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)メンバー関数に記述します。 このトピックでは、関数について簡単に説明し、RFX 関数を使用できるデータ型について説明します。 [テクニカルノート 43](../../mfc/tn043-rfx-routines.md)では、追加のデータ型用に独自の RFX 関数を記述する方法について説明します。

##  <a name="rfx-function-syntax"></a><a name="_core_rfx_function_syntax"></a>RFX 関数の構文

各 RFX 関数は、3つのパラメーター (および省略可能な4番目または5番目のパラメーターを受け取る) を受け取ります。

- [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクトへのポインター。 `DoFieldExchange`に渡された `pFX` ポインターに沿って渡すだけです。

- データソースに表示される列の名前。

- レコードセットクラスの対応するフィールドデータメンバーまたはパラメーターデータメンバーの名前。

- Optional一部の関数では、転送される文字列または配列の最大長を指定します。 既定値は255バイトですが、変更することもできます。 最大サイズは `CString` オブジェクトの最大サイズである**INT_MAX** (2147483647) バイトに基づいていますが、そのサイズの前にドライバーの制限が発生する可能性があります。

- Optional`RFX_Text` 関数では、5番目のパラメーターを使用して列のデータ型を指定することもできます。

詳細については、「*クラスライブラリリファレンス*」の「[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)」にある RFX 関数を参照してください。 パラメーターを特別に使用する場合の例については、「[レコードセット: 合計およびその他の集計結果の取得 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)」を参照してください。

##  <a name="rfx-data-types"></a><a name="_core_rfx_data_types"></a>RFX データ型

クラスライブラリには、データソースとレコードセットの間でさまざまなデータ型を転送するための RFX 関数が用意されています。 次の一覧は、RFX 関数をデータ型別にまとめたものです。 独自の RFX 関数呼び出しを記述する必要がある場合は、これらの関数からデータ型を選択します。

|Function|データ型|
|--------------|---------------|
|`RFX_Bool`|**BOOL**|
|`RFX_Byte`|**BYTE**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**double**|
|`RFX_Single`|**float**|
|`RFX_Int`|**int**|
|`RFX_Long`|**long**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|

詳細については、*クラスライブラリリファレンス*の「[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)」の RFX 関数のドキュメントを参照してください。 データ型を SQL C++データ型にマップする方法の詳細については、「SQL C++ [: SQL およびC++データ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)のデータ型にマップされる ANSI sql データ型」を参照してください。

## <a name="see-also"></a>参照

[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[レコードセット: パラメーターを利用したレコードセット (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[レコードセット: データ列を動的に結びつける方法 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)