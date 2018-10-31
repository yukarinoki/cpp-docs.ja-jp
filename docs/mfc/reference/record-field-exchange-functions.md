---
title: レコード フィールド エクス チェンジ関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXDB/RFX_Binary
- AFXDB/RFX_Bool
- AFXDB/RFX_Byte
- AFXDB/RFX_Date
- AFXDB/RFX_Double
- AFXDB/RFX_Int
- AFXDB/RFX_Long
- AFXDB/RFX_LongBinary
- AFXDB/RFX_Single
- AFXDB/RFX_Text
- AFXDB/RFX_Binary_Bulk
- AFXDB/RFX_Bool_Bulk
- AFXDB/RFX_Byte_Bulk
- AFXDB/RFX_Date_Bulk
- AFXDB/RFX_Double_Bulk
- AFXDB/RFX_Int_Bulk
- AFXDB/RFX_Long_Bulk
- AFXDB/RFX_Single_Bulk
- AFXDB/RFX_Text_Bulk
- AFXDB/DFX_Binary
- AFXDB/DFX_Bool
- AFXDB/DFX_Byte
- AFXDB/DFX_Currency
- AFXDB/DFX_DateTime
- AFXDB/DFX_Double
- AFXDB/DFX_Long
- AFXDB/DFX_LongBinary
- AFXDB/DFX_Short
- AFXDB/DFX_Single
- AFXDB/DFX_Text
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), record field exchange (DFX)
- ODBC, bulk RFX data exchange functions [MFC]
- RFX (record field exchange), ODBC classes
- DFX (DAO record field exchange), data exchange functions [MFC]
- DFX functions [MFC]
- bulk RFX functions [MFC]
- DFX (DAO record field exchange)
- RFX (record field exchange), DAO classes
- ODBC, RFX
- RFX (record field exchange), data exchange functions [MFC]
- RFX (record field exchange)
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fba2e8d949745f694973f2d7b29c5244ab30db4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50058909"
---
# <a name="record-field-exchange-functions"></a>レコード フィールド エクスチェンジ (RFX) 関数

このトピックでは、レコード フィールド エクス チェンジ (RFX、バルク rfx 関数と DFX) 関数をレコード セット オブジェクトとそのデータ ソース間のデータの転送を自動化し、データの他の操作を実行するために使用します。

ODBC ベースのクラスを使用し、バルク行フェッチを実装している場合は、データ ソース列に対応する各データ メンバーに対してバルク RFX 関数を呼び出すことによって、 `DoBulkFieldExchange` の `CRecordset` メンバー関数を手動でオーバーライドする必要があります。

ODBC ベースのクラスにバルク行フェッチを実装していない場合または DAO ベースのクラスを使用している場合は、ClassWizard で、レコードセットの各フィールド データ メンバーに対して RFX 関数 (ODBC クラスの場合) または DFX 関数 (DAO クラスの場合) を呼び出すことで、 `DoFieldExchange` または `CRecordset` の `CDaoRecordset` メンバー関数をオーバーライドします。

レコード フィールド エクスチェンジ関数は、フレームワークが `DoFieldExchange` または `DoBulkFieldExchange`を呼び出すたびにデータを転送します。 それぞれの関数が特定のデータ型を転送します。

これらの関数の使い方の詳細については、「 [レコード フィールド エクスチェンジ: RFX のしくみ (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

動的にバインドするデータの列では、RFX 関数または DFX 関数を手動で呼び出すこともできます。詳細については、「 [レコードセット: データ列を動的に結びつける方法 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。 また、独自のカスタム RFX ルーチンまたは DFX ルーチンを記述することもできます。詳細については、テクニカル ノート [43](../../mfc/tn043-rfx-routines.md) (ODBC の場合) およびテクニカル ノート [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (DAO の場合) を参照してください。

表示される関数とバルク RFX の例について、`DoFieldExchange`と`DoBulkFieldExchange`関数を参照してください[RFX_Text](#rfx_text)と [RFX_Text_Bulk] #rfx_text_bulk)。 DFX 関数は RFX 関数によく似ています。

### <a name="rfx-functions-odbc"></a>RFX 関数 (ODBC)

|||
|-|-|
|[RFX_Binary](#rfx_binary)|[CByteArray](cbytearray-class.md)型のバイト配列を転送します。|
|[RFX_Bool](#rfx_bool)|ブール型のデータを転送します。|
|[RFX_Byte](#rfx_byte)|シングル バイトのデータを転送します。|
|[RFX_Date](#rfx_date)|時刻と日付のデータを使用して転送[CTime](../../atl-mfc-shared/reference/ctime-class.md)または TIMESTAMP_STRUCT します。|
|[RFX_Double](#rfx_double)|倍精度浮動小数点型のデータを転送します。|
|[RFX_Int](#rfx_int)|整数型のデータを転送します。|
|[RFX_Long](#rfx_long)|長整数型のデータを転送します。|
|[RFX_LongBinary](#rfx_longbinary)|[CLongBinary](clongbinary-class.md) クラスのオブジェクトを使用して、バイナリ ラージ オブジェクト (BLOB) データを転送します。|
|[RFX_Single](#rfx_single)|浮動小数点型のデータを転送します。|
|[RFX_Text](#rfx_text)|文字列型のデータを転送します。|

### <a name="bulk-rfx-functions-odbc"></a>バルク RFX 関数 (ODBC)

|||
|-|-|
|[RFX_Binary_Bulk](#rfx_binary_bulk)|バイト データの配列を転送します。|
|[RFX_Bool_Bulk](#rfx_bool_bulk)|ブール型のデータの配列を転送します。|
|[RFX_Byte_Bulk](#rfx_byte_bulk)|シングル バイトの配列を転送します。|
|[RFX_Date_Bulk](#rfx_date_bulk)|TIMESTAMP_STRUCT の種類のデータの配列を転送します。|
|[RFX_Double_Bulk](#rfx_double_bulk)|倍精度浮動小数点型のデータの配列を転送します。|
|[RFX_Int_Bulk](#rfx_int_bulk)|整数型のデータの配列を転送します。|
|[RFX_Long_Bulk](#rfx_long_bulk)|長整数型のデータの配列を転送します。|
|[RFX_Single_Bulk](#rfx_single_bulk)|浮動小数点型のデータの配列を転送します。|
|[RFX_Text_Bulk](#rfx_text_bulk)|型 LPSTR のデータの配列を転送します。|

### <a name="dfx-functions-dao"></a>DFX 関数 (DAO)

|||
|-|-|
|[DFX_Binary](#dfx_binary)|[CByteArray](cbytearray-class.md)型のバイト配列を転送します。|
|[DFX_Bool](#dfx_bool)|ブール型のデータを転送します。|
|[DFX_Byte](#dfx_byte)|シングル バイトのデータを転送します。|
|[DFX_Currency](#dfx_currency)|[COleCurrency](colecurrency-class.md)型の通貨データを転送します。|
|[DFX_DateTime](#dfx_datetime)|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)型の時刻と日付データを転送します。|
|[DFX_Double](#dfx_double)|倍精度浮動小数点型のデータを転送します。|
|[DFX_Long](#dfx_long)|長整数型のデータを転送します。|
|[DFX_LongBinary](#dfx_longbinary)|`CLongBinary` クラスのオブジェクトを使用して、バイナリ ラージ オブジェクト (BLOB) データを転送します。 DAO の場合は、代わりに [DFX_Binary](#dfx_binary) を使用することをお勧めします。|
|[DFX_Short](#dfx_short)|短整数型のデータを転送します。|
|[DFX_Single](#dfx_single)|浮動小数点型のデータを転送します。|
|[DFX_Text](#dfx_text)|文字列型のデータを転送します。|

=============================================

## <a name="rfx_binary"></a>  RFX_Binary

フィールド データ メンバーの間でバイトの配列を転送、`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列が SQL_BINARY、SQL_VARBINARY、または SQL_LONGVARBINARY を入力します。

### <a name="syntax"></a>構文

```
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送[CByteArray](cbytearray-class.md)、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*格納*<br/>
文字列または転送される配列の長さが最大です。 既定値*格納*は 255 です。 有効な値は、INT_MAX に 1 です。 フレームワークは、データにこの量の領域を割り当てます。 最適なパフォーマンスを期待する最大のデータ項目の対応するために十分な大きさの値を渡します。

### <a name="remarks"></a>Remarks

型との間にこれらの型のデータ ソース内のデータがマップされている`CByteArray`レコード セット。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_bool"></a>  RFX_Bool

フィールド データ メンバーの間でのブール型のデータの転送、`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列が SQL_BIT を入力します。

### <a name="syntax"></a>構文

```
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットからデータ ソースへの転送、BOOL 型の値は、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_byte"></a>  RFX_Byte

1 バイトのフィールド データ メンバーの間の転送、`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列が SQL_TINYINT を入力します。

### <a name="syntax"></a>構文

```
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットからデータ ソースへの転送、BYTE、型の値は、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_date"></a>  RFX_Date

転送`CTime`または TIMESTAMP_STRUCT のフィールド データ メンバーの間でデータを`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列は、SQL_DATE、SQL_TIME、または SQL_TIMESTAMP を入力します。

### <a name="syntax"></a>構文

```
void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   CTime& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   TIMESTAMP_STRUCT& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   COleDateTime& value);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納された値転送する値。 関数のさまざまなバージョンでは、異なるデータ型の値を実行します。

関数の最初のバージョンへの参照を受け取り、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。 レコード セットからデータ ソースへの転送では、この値は、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

関数の 2 番目のバージョンへの参照を受け取り、`TIMESTAMP_STRUCT`構造体。 必要がありますこの構造体を自分で設定した呼び出しの前にします。 どちらのダイアログ データ エクス (チェンジ DDX) のサポートも、コード ウィザードのサポートは、このバージョンで利用可能です。 3 番目のバージョンの関数は最初のバージョンと同様に動作への参照を受け取る点を除いて、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

`CTime`関数のバージョンは、いくつかの中間処理のオーバーヘッドあり、多少の制限の範囲。 これらの要因は限定的すぎるのいずれかの場合は、関数の 2 番目のバージョンを使用します。 コード ウィザードと DDX のサポート構造を自分で設定する必要がないことに注意してください。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_double"></a>  RFX_Double

転送**倍精度浮動小数点**のフィールド データ メンバーの間でデータを`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列が SQL_DOUBLE を入力します。

### <a name="syntax"></a>構文

```
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送**二重**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_int"></a>  RFX_Int

フィールド データ メンバーの間で整数のデータ転送、`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列が SQL_SMALLINT を入力します。

### <a name="syntax"></a>構文

```
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送**int**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_long"></a>  RFX_Long

フィールド データ メンバーの間での長整数のデータ転送、`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列が SQL_INTEGER を入力します。

### <a name="syntax"></a>構文

```
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送**長い**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_longbinary"></a>  RFX_LongBinary

クラスを使用してバイナリ ラージ オブジェクト (BLOB) データを転送[CLongBinary](clongbinary-class.md)のフィールド データ メンバーの間、`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列は、SQL_LONGVARBINARY または SQL_LONGVARCHAR を入力します。

### <a name="syntax"></a>構文

```
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送`CLongBinary`、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_single"></a>  RFX_Single

フィールド データ メンバーの間で浮動小数点のデータ転送、`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列が SQL_REAL を入力します。

### <a name="syntax"></a>構文

```
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送**float**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_text"></a>  RFX_Text

転送`CString`のフィールド データ メンバーの間でデータを`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列は、SQL_LONGVARCHAR、SQL_CHAR、SQL_VARCHAR、SQL_DECIMAL、または SQL_NUMERIC を入力します。

### <a name="syntax"></a>構文

```
void RFX_Text(
   CFieldExchange* pFX,
   const char* szName,
   CString& value,
   int nMaxLength = 255,
   int nColumnType = SQL_VARCHAR,
   short nScale = 0);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター`CFieldExchange`します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送`CString`、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*格納*<br/>
文字列または転送される配列の長さが最大です。 既定値*格納*は 255 です。 有効な値は 1 に INT_MAX) です。 フレームワークは、データにこの量の領域を割り当てます。 最適なパフォーマンスを期待する最大のデータ項目の対応するために十分な大きさの値を渡します。

*nColumnType*<br/>
パラメーターには主に使用されます。 パラメーターのデータ型を示す整数。 種類は、フォームの ODBC データ型**SQL_XXX**します。

*nScale*<br/>
ODBC の SQL_DECIMAL または SQL_NUMERIC の種類の値の小数点以下桁数を指定します。 *nScale*はパラメーター値を設定する場合にのみ役立ちます。 詳細についてを参照してください「桁数、小数点、長さ、および表示サイズ」の付録 D、 *ODBC SDK プログラマー リファレンス*します。

### <a name="remarks"></a>Remarks

間にこれらの型のすべてのデータ ソース内のデータがマップされている`CString`レコード セット。

### <a name="example"></a>例

この例は、いくつかの呼び出しを示しています。`RFX_Text`します。 2 つの呼び出しにも注意してください`CFieldExchange::SetFieldType`します。 パラメーターへの呼び出しを記述する必要があります`SetFieldType`と rfx 関数の呼び出し。 出力列の呼び出しとその関連する rfx 関数呼び出しは、通常コード ウィザードによって書き込まれます。

```cpp
void CCustomer::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   // Macros such as RFX_Text() and RFX_Int() are dependent on the
   // type of the member variable, not the type of the field in the database.
   // ODBC will try to automatically convert the column value to the requested type
   RFX_Long(pFX, _T("[CustomerID]"), m_CustomerID);
   RFX_Text(pFX, _T("[ContactFirstName]"), m_ContactFirstName);
   RFX_Text(pFX, _T("[PostalCode]"), m_PostalCode);
   RFX_Text(pFX, _T("[L_Name]"), m_L_Name);
   RFX_Long(pFX, _T("[BillingID]"), m_BillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_binary_bulk"></a>  RFX_Binary_Bulk

対応する配列を ODBC データ ソースの列から複数行のバイトのデータを転送する`CRecordset`の派生オブジェクト。

### <a name="syntax"></a>構文

```
void RFX_Binary_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、この記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*prgByteVals*<br/>
バイト値の配列へのポインター。 この配列は、データ ソースからレコード セットに転送するデータを格納します。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列が指す配列内の各値のバイト単位の長さを格納*prgByteVals*します。 値 SQL_NULL_DATA が対応するデータ項目には、Null 値が含まれている場合のどちらで格納されることに注意してください。 詳細については、ODBC API 関数を参照してください。`SQLBindCol`で、 *ODBC SDK プログラマー リファレンス*します。

*格納*<br/>
指す配列に格納されている値の長さの上限、 *prgByteVals*します。 確実にデータが切り捨てられませんが、期待する最大のデータ項目の対応するために十分な大きさの値を渡します。

### <a name="remarks"></a>Remarks

データ ソースの列には、ODBC の SQL_BINARY、SQL_VARBINARY、または SQL_LONGVARBINARY 型を持つことができます。 レコード セットは、バイトをポインター型のフィールド データ メンバーを定義する必要があります。

初期化する場合*prgByteVals*と*prgLengths*を NULL にし、行セット サイズと同じサイズをポイントしている配列が自動的に割り当てられます。

> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトに、データ ソースからデータを転送します。 レコード セットを更新できるようにするために、ODBC API 関数を使用する必要があります`SQLSetPos`します。

詳細については、記事をご覧ください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。

### <a name="example"></a>例

参照してください[RFX_Text_Bulk](#rfx_text_bulk)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_bool_bulk"></a>  RFX_Bool_Bulk

対応する配列を ODBC データ ソースの列から複数行のブール型のデータを転送する`CRecordset`の派生オブジェクト。

### <a name="syntax"></a>構文

```
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、この記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*prgBoolVals*<br/>
ブール値の配列へのポインター。 この配列は、データ ソースからレコード セットに転送するデータを格納します。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列が指す配列内の各値のバイト単位の長さを格納*prgBoolVals*します。 値 SQL_NULL_DATA が対応するデータ項目には、Null 値が含まれている場合のどちらで格納されることに注意してください。 詳細については、ODBC API 関数を参照してください。`SQLBindCol`で、 *ODBC SDK プログラマー リファレンス*します。

### <a name="remarks"></a>Remarks

データ ソースの列には、ODBC 型 SQL_BIT の必要があります。 レコード セットは、ブール型にポインター型のフィールド データ メンバーを定義する必要があります。

初期化する場合*prgBoolVals*と*prgLengths*を NULL にし、行セット サイズと同じサイズをポイントしている配列が自動的に割り当てられます。

> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトに、データ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります`SQLSetPos`します。

詳細については、記事をご覧ください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。

### <a name="example"></a>例

参照してください[RFX_Text_Bulk](#rfx_text_bulk)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_byte_bulk"></a>  RFX_Byte_Bulk

対応する配列を ODBC データ ソースの列から複数行の 1 つのバイトを転送する`CRecordset`の派生オブジェクト。

### <a name="syntax"></a>構文

```
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、この記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*prgByteVals*<br/>
バイト値の配列へのポインター。 この配列は、データ ソースからレコード セットに転送するデータを格納します。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列が指す配列内の各値のバイト単位の長さを格納*prgByteVals*します。 値 SQL_NULL_DATA が対応するデータ項目には、Null 値が含まれている場合のどちらで格納されることに注意してください。 詳細については、ODBC API 関数を参照してください。`SQLBindCol`で、 *ODBC SDK プログラマー リファレンス*します。

### <a name="remarks"></a>Remarks

データ ソースの列には、ODBC 型 SQL_TINYINT の必要があります。 レコード セットは、バイトをポインター型のフィールド データ メンバーを定義する必要があります。

初期化する場合*prgByteVals*と*prgLengths*を NULL にし、行セット サイズと同じサイズをポイントしている配列が自動的に割り当てられます。

> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトに、データ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります`SQLSetPos`します。

詳細については、記事をご覧ください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。

### <a name="example"></a>例

参照してください[RFX_Text_Bulk](#rfx_text_bulk)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_date_bulk"></a>  RFX_Date_Bulk

ODBC データ ソースの列からに対応する配列に複数行の TIMESTAMP_STRUCT データを転送する`CRecordset`-派生オブジェクト。

### <a name="syntax"></a>構文

```
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、この記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*prgTSVals*<br/>
TIMESTAMP_STRUCT 値の配列へのポインター。 この配列は、データ ソースからレコード セットに転送するデータを格納します。 TIMESTAMP_STRUCT のデータ型の詳細についてを参照してください「C データ型」の付録 d、 *ODBC SDK プログラマー リファレンス*します。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列が指す配列内の各値のバイト単位の長さを格納*prgTSVals*します。 値 SQL_NULL_DATA が対応するデータ項目には、Null 値が含まれている場合のどちらで格納されることに注意してください。 詳細については、ODBC API 関数を参照してください。`SQLBindCol`で、 *ODBC SDK プログラマー リファレンス*します。

### <a name="remarks"></a>Remarks

データ ソースの列には、SQL_DATE、SQL_TIME、または SQL_TIMESTAMP の ODBC 型を持つことができます。 レコード セットは、TIMESTAMP_STRUCT にポインター型のフィールド データ メンバーを定義する必要があります。

初期化する場合*prgTSVals*と*prgLengths*を NULL にし、行セット サイズと同じサイズをポイントしている配列が自動的に割り当てられます。

> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトに、データ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります`SQLSetPos`します。

詳細については、記事をご覧ください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。

### <a name="example"></a>例

参照してください[RFX_Text_Bulk](#rfx_text_bulk)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_double_bulk"></a>  RFX_Double_Bulk

ODBC データ ソースの列からの対応する配列に複数行の倍精度の浮動小数点のデータを転送する`CRecordset`-派生オブジェクト。

### <a name="syntax"></a>構文

```
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、この記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*prgDblVals*<br/>
配列へのポインター**二重**値。 この配列は、データ ソースからレコード セットに転送するデータを格納します。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列が指す配列内の各値のバイト単位の長さを格納*prgDblVals*します。 値 SQL_NULL_DATA が対応するデータ項目には、Null 値が含まれている場合のどちらで格納されることに注意してください。 詳細については、ODBC API 関数を参照してください。`SQLBindCol`で、 *ODBC SDK プログラマー リファレンス*します。

### <a name="remarks"></a>Remarks

データ ソースの列には、ODBC の SQL_DOUBLE 種必要があります。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**二重**します。

初期化する場合*prgDblVals*と*prgLengths*を NULL にし、行セット サイズと同じサイズをポイントしている配列が自動的に割り当てられます。

> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトに、データ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります`SQLSetPos`します。

詳細については、記事をご覧ください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。

### <a name="example"></a>例

参照してください[RFX_Text_Bulk](#rfx_text_bulk)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_int_bulk"></a>  RFX_Int_Bulk

フィールド データ メンバーの間で整数のデータ転送、`CRecordset`オブジェクトと ODBC のデータ ソースのレコードの列が SQL_SMALLINT を入力します。

### <a name="syntax"></a>構文

```
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、`CFieldExchange`の資料を参照するオブジェクトを指定できます、[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送**int**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

### <a name="example"></a>例

参照してください[RFX_Text](#rfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_long_bulk"></a>  RFX_Long_Bulk

ODBC データ ソースの列からの対応する配列に複数行の長整数型のデータを転送する`CRecordset`-派生オブジェクト。

### <a name="syntax"></a>構文

```
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、この記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*prgLongVals*<br/>
長整数の配列へのポインター。 この配列は、データ ソースからレコード セットに転送するデータを格納します。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列が指す配列内の各値のバイト単位の長さを格納*prgLongVals*します。 値 SQL_NULL_DATA が対応するデータ項目には、Null 値が含まれている場合のどちらで格納されることに注意してください。 詳細については、ODBC API 関数を参照してください。`SQLBindCol`で、 *ODBC SDK プログラマー リファレンス*します。

### <a name="remarks"></a>Remarks

データ ソースの列には、ODBC 型 SQL_INTEGER の必要があります。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**長い**します。

初期化する場合*prgLongVals*と*prgLengths*を NULL にし、行セット サイズと同じサイズをポイントしている配列が自動的に割り当てられます。

> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトに、データ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります`SQLSetPos`します。

詳細については、記事をご覧ください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。

### <a name="example"></a>例

参照してください[RFX_Text_Bulk](#rfx_text_bulk)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_single_bulk"></a>  RFX_Single_Bulk

ODBC データ ソースの列からの対応する配列に複数行の浮動小数点のデータを転送する`CRecordset`-派生オブジェクト。

### <a name="syntax"></a>構文

```
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、この記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*prgFltVals*<br/>
配列へのポインター **float**値。 この配列は、データ ソースからレコード セットに転送するデータを格納します。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列が指す配列内の各値のバイト単位の長さを格納*prgFltVals*します。 値 SQL_NULL_DATA が対応するデータ項目には、Null 値が含まれている場合のどちらで格納されることに注意してください。 詳細については、ODBC API 関数を参照してください。`SQLBindCol`で、 *ODBC SDK プログラマー リファレンス*します。

### <a name="remarks"></a>Remarks

データ ソースの列には、ODBC 型 SQL_REAL の必要があります。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**float**します。

初期化する場合*prgFltVals*と*prgLengths*を NULL にし、行セット サイズと同じサイズをポイントしている配列が自動的に割り当てられます。

> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトに、データ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります`SQLSetPos`します。

詳細については、記事をご覧ください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。

### <a name="example"></a>例

参照してください[RFX_Text_Bulk](#rfx_text_bulk)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_text_bulk"></a>  RFX_Text_Bulk

ODBC データ ソースの列からの対応する配列に複数行の文字データを転送する`CRecordset`-派生オブジェクト。

### <a name="syntax"></a>構文

```
void RFX_Text_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   LPSTR* prgStrVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、この記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。

*szName*<br/>
データ列の名前。

*prgStrVals*<br/>
LPSTR 値の配列へのポインター。 この配列は、データ ソースからレコード セットに転送するデータを格納します。 ODBC の現在のバージョンでなお、これらの値が Unicode にすることはできません。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列が指す配列内の各値のバイト単位の長さを格納*prgStrVals*します。 この長さは、null 終端文字を除外します。 値 SQL_NULL_DATA が対応するデータ項目には、Null 値が含まれている場合のどちらで格納されることに注意してください。 詳細については、ODBC API 関数を参照してください。`SQLBindCol`で、 *ODBC SDK プログラマー リファレンス*します。

*格納*<br/>
指す配列に格納されている値の長さの上限、 *prgStrVals*終端の null 文字を含むです。 確実にデータが切り捨てられませんが、期待する最大のデータ項目の対応するために十分な大きさの値を渡します。

### <a name="remarks"></a>Remarks

データ ソースの列には、SQL_LONGVARCHAR、SQL_CHAR、SQL_VARCHAR、SQL_DECIMAL、または SQL_NUMERIC の ODBC 型を持つことができます。 レコード セットには、型 LPSTR のフィールド データ メンバーを定義する必要があります。

初期化する場合*prgStrVals*と*prgLengths*を NULL にし、行セット サイズと同じサイズをポイントしている配列が自動的に割り当てられます。

> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトに、データ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります`SQLSetPos`します。

詳細については、記事をご覧ください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。

### <a name="example"></a>例

呼び出しを手動で作成する必要があります、`DoBulkFieldExchange`をオーバーライドします。 この例への呼び出しを示しています。 `RFX_Text_Bulk`、への呼び出しと`RFX_Long_Bulk`、データ転送。 これらの呼び出しの前の呼び出しを[つ](CFieldExchange::SetFieldType.md)します。 パラメーターに対してバルク RFX 関数ではなく RFX 関数を呼び出す必要がありますに注意してください。

```cpp
void CMultiCustomer::DoBulkFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Long_Bulk(pFX, _T("[CustomerID]"), &m_pCustomerID, &m_pcCustomerID);
   RFX_Text_Bulk(pFX, _T("[ContactFirstName]"), &m_pContactFirstName, &m_pcContactFirstName, 50);
   RFX_Text_Bulk(pFX, _T("[PostalCode]"), &m_pPostalCode, &m_pcPostalCode, 50);
   RFX_Text_Bulk(pFX, _T("[L_Name]"), &m_pL_Name, &m_pcL_Name, 50);
   RFX_Long_Bulk(pFX, _T("[BillingID]"), &m_pBillingID, &m_pcBillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="dfx_binary"></a>  DFX_Binary

フィールド データ メンバーの間でバイトの配列を転送する[CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_Binary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CByteArray& value,
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送[CByteArray](cbytearray-class.md)、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*nPreAllocSize*<br/>
フレームワークには、このメモリ量が事前に割り当てます。 データが大きい場合は、フレームワークは必要に応じてより多くの領域を割り当てられているされます。 パフォーマンスの向上のためには、このサイズを再割り当てを回避するのに十分な大きさの値に設定します。 既定のサイズは、AFXDAO で定義されます。AFX_DAO_BINARY_DEFAULT_SIZE として H ファイルです。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_DISABLE_FIELD_CACHE、既定値は、ダブル バッファリングを使用しないと呼び出す必要があります[き](cdaorecordset-class.md#setfielddirty)と[な](cdaorecordset-class.md#setfieldnull)自分でします。 他の考えられる値 AFX_DAO_ENABLE_FIELD_CACHE、ダブル バッファリングを使用して、フィールドをマークする余分な作業を実行する必要はありませんダーティまたは Null。 パフォーマンスとメモリ上の理由から、バイナリ データが比較的少ない場合を除き、この値を回避します。

> [!NOTE]
>  かどうかからデータのすべてのフィールドを設定して、既定でバッファリング double を制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

Dao DAO_BYTES 型と型の間のデータのマップ[CByteArray](cbytearray-class.md)レコード セット。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_bool"></a>  DFX_Bool

フィールド データ メンバーの間でブール型のデータを転送する[CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットからデータ ソースへの転送、BOOL 型の値は、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_ENABLE_FIELD_CACHE、既定では、ダブル バッファリングを使用します。 その他の考えられる値は、AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定する場合は、MFC をチェックしませんこのフィールド。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

データは、型の DAO DAO_BOOL とレコード セットの BOOL 型の間にマップされます。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_byte"></a>  DFX_Byte

1 バイトのフィールド データ メンバーの間の転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットからデータ ソースへの転送、BYTE、型の値は、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_ENABLE_FIELD_CACHE、既定では、ダブル バッファリングを使用します。 その他の考えられる値は、AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定する場合は、MFC をチェックしませんこのフィールド。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

データは、型 dao DAO_BYTES とレコード セットの BYTE 型の間にマップされます。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_currency"></a>  DFX_Currency

フィールド データ メンバーの間で通貨のデータ転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットからデータ ソースへの転送では、この値は型の指定されたデータ メンバーから取得[COleCurrency](colecurrency-class.md)します。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_ENABLE_FIELD_CACHE、既定では、ダブル バッファリングを使用します。 その他の考えられる値は、AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定する場合は、MFC をチェックしませんこのフィールド。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

Dao DAO_CURRENCY 型と型の間のデータのマップ[COleCurrency](colecurrency-class.md)レコード セット。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_datetime"></a>  DFX_DateTime

フィールド データ メンバーの間で日付と時刻のデータ転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 関数への参照を受け取り、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。 レコード セットからデータ ソースへの転送では、この値は、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_ENABLE_FIELD_CACHE、既定では、ダブル バッファリングを使用します。 その他の考えられる値は、AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定する場合は、MFC をチェックしませんこのフィールド。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

Dao DAO_DATE 型と型の間のデータのマップ[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)レコード セット。

> [!NOTE]
>  `COleDateTime` 置換[CTime](../../atl-mfc-shared/reference/ctime-class.md) TIMESTAMP_STRUCT DAO クラスでは、この目的とします。 `CTime` および ODBC ベースのデータ アクセス クラス TIMESTAMP_STRUCT が使用されます。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_double"></a>  DFX_Double

転送**倍精度浮動小数点**のフィールド データ メンバーの間でデータを[CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送**二重**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_ENABLE_FIELD_CACHE、既定では、ダブル バッファリングを使用します。 その他の考えられる値は、AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定する場合は、MFC をチェックしませんこのフィールド。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

DAO DAO_R8 型と型の間のデータのマップ**倍精度浮動小数点**レコード セット。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_long"></a>  DFX_Long

フィールド データ メンバーの間での長整数のデータ転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送**長い**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_ENABLE_FIELD_CACHE、既定では、ダブル バッファリングを使用します。 その他の考えられる値は、AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定する場合は、MFC をチェックしませんこのフィールド。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

DAO DAO_I4 型と型の間のデータのマップ**長い**レコード セット。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_longbinary"></a>  DFX_LongBinary

**重要な**を使用することをお勧め[DFX_Binary](#dfx_binary)この関数の代わりにします。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_LongBinary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CLongBinary& value,
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送[CLongBinary](clongbinary-class.md)、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*dwPreAllocSize*<br/>
フレームワークには、このメモリ量が事前に割り当てます。 データが大きい場合は、フレームワークは必要に応じてより多くの領域を割り当てられているされます。 パフォーマンスの向上のためには、このサイズを再割り当てを回避するのに十分な大きさの値に設定します。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 既定値、AFX_DISABLE_FIELD_CACHE、ダブル バッファリングを使用しません。 その他の考えられる値は、AFX_DAO_ENABLE_FIELD_CACHE です。 ダブル バッファリングを使用してフィールドをマークする余分な作業を行う必要はないダーティまたは Null。 パフォーマンスとメモリ上の理由から、バイナリ データが比較的少ない場合を除き、この値を回避します。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

`DFX_LongBinary` MFC ODBC クラスと互換性のために提供されます。 `DFX_LongBinary`関数がクラスを使用してバイナリ ラージ オブジェクト (BLOB) データを転送`CLongBinary`のフィールド データ メンバーの間、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。 Dao DAO_BYTES 型と型の間のデータのマップ[CLongBinary](clongbinary-class.md)レコード セット。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_short"></a>  DFX_Short

転送の短い間のフィールド データ メンバーの整数データ、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送**短い**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_ENABLE_FIELD_CACHE、既定では、ダブル バッファリングを使用します。 その他の考えられる値は、AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定する場合は、MFC をチェックしませんこのフィールド。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

DAO DAO_I2 型と型の間のデータのマップ**短い**レコード セット。

> [!NOTE]
>  `DFX_Short` 等価[RFX_Int](#rfx_int) ODBC ベースのクラスにします。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_single"></a>  DFX_Single

フィールド データ メンバーの間で浮動小数点のデータ転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送**float**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_ENABLE_FIELD_CACHE、既定では、ダブル バッファリングを使用します。 その他の考えられる値は、AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定する場合は、MFC をチェックしませんこのフィールド。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

DAO DAO_R4 型と型の間のデータのマップ**float**レコード セット。

### <a name="example"></a>例

参照してください[DFX_Text](#dfx_text)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_text"></a>  DFX_Text

転送`CString`のフィールド データ メンバーの間でデータを[CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列。

### <a name="syntax"></a>構文

```
void AFXAPI DFX_Text(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CString& value,
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)します。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。

*szName*<br/>
データ列の名前。

*値*<br/>
指定されたデータ メンバーに格納されている値: 転送する値。 レコード セットから、データ ソースの種類の値への転送[CString](../../atl-mfc-shared/reference/cstringt-class.md)、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。

*nPreAllocSize*<br/>
フレームワークには、このメモリ量が事前に割り当てます。 データが大きい場合は、フレームワークは必要に応じてより多くの領域を割り当てられているされます。 パフォーマンスの向上のためには、このサイズを再割り当てを回避するのに十分な大きさの値に設定します。

*dwBindOptions*<br/>
オプションが変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用することができます。 AFX_DAO_ENABLE_FIELD_CACHE、既定では、ダブル バッファリングを使用します。 その他の考えられる値は、AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定する場合は、MFC をチェックしませんこのフィールド。 呼び出す必要があります[き](cdaorecordset-class.md#setfielddirty)と[な](cdaorecordset-class.md#setfieldnull)自分でします。

> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御できます[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)します。

### <a name="remarks"></a>Remarks

Dao DAO_CHAR 型間のデータのマップ (シンボル _UNICODE が定義されている場合や、DAO_WCHAR) と種類[CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード セット内。  n

### <a name="example"></a>例

この例は、いくつかの呼び出しを示しています。`DFX_Text`します。 2 つの呼び出しにも注意してください[CDaoFieldExchange::SetFieldType](cdaofieldexchange-class.md#setfieldtype)します。 最初の呼び出しを記述する必要があります`SetFieldType`とその**DFX**呼び出します。 2 番目の呼び出しとその関連付けられた**DFX**呼び出しは通常、クラスを生成するコード ウィザードによって書き込まれます。

```cpp
void CCustSet::DoFieldExchange(CDaoFieldExchange* pFX)
{
   pFX->SetFieldType(CDaoFieldExchange::param);
   DFX_Text(pFX, _T("Param"), m_strParam);
   pFX->SetFieldType(CDaoFieldExchange::outputColumn);
   DFX_Short(pFX, _T("EmployeeID"), m_EmployeeID);
   DFX_Text(pFX, _T("LastName"), m_LastName);
   DFX_Short(pFX, _T("Age"), m_Age);
   DFX_DateTime(pFX, _T("hire_date"), m_hire_date);
   DFX_DateTime(pFX, _T("termination_date"), m_termination_date);

   CDaoRecordset::DoFieldExchange(pFX);
}
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CRecordset::DoFieldExchange](crecordset-class.md#dofieldexchange)<br/>
[CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)<br/>
[CDaoRecordset::DoFieldExchange](cdaorecordset-class.md#dofieldexchange)

