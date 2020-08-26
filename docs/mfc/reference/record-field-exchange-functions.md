---
title: レコード フィールド エクスチェンジ (RFX) 関数
ms.date: 09/17/2019
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
ms.openlocfilehash: 9bb1b7bcbce16bba8029fcfbbeea7552b1d4a0ba
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843600"
---
# <a name="record-field-exchange-functions"></a>レコード フィールド エクスチェンジ (RFX) 関数

ここでは、レコードセット オブジェクトとそのデータ ソース間のデータ転送を自動化したり、データに対してその他の操作を実行したりするためのレコード フィールド エクスチェンジの関数 (RFX、バルク RFX、および DFX) の一覧を示します。

ODBC ベースのクラスを使用し、バルク行フェッチを実装している場合は、データ ソース列に対応する各データ メンバーに対してバルク RFX 関数を呼び出すことによって、 `DoBulkFieldExchange` の `CRecordset` メンバー関数を手動でオーバーライドする必要があります。

ODBC ベースのクラスにバルク行フェッチを実装していない場合、または DAO ベースのクラス (旧形式) を使用している場合、ClassWizard は、 `DoFieldExchange` `CRecordset` `CDaoRecordset` レコードセット内の各フィールドデータメンバーの RFX 関数 (ODBC クラスの場合) または DFX 関数 (DAO クラスの場合) を呼び出すことによって、のメンバー関数をオーバーライドします。

レコード フィールド エクスチェンジ関数は、フレームワークが `DoFieldExchange` または `DoBulkFieldExchange`を呼び出すたびにデータを転送します。 それぞれの関数が特定のデータ型を転送します。

これらの関数の使い方の詳細については、「 [レコード フィールド エクスチェンジ: RFX のしくみ (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

動的にバインドするデータの列では、RFX 関数または DFX 関数を手動で呼び出すこともできます。詳細については、「 [レコードセット: データ列を動的に結びつける方法 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。 また、独自のカスタム RFX ルーチンまたは DFX ルーチンを記述することもできます。詳細については、テクニカル ノート [43](../../mfc/tn043-rfx-routines.md) (ODBC の場合) およびテクニカル ノート [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (DAO の場合) を参照してください。

関数と関数に表示される RFX 関数と Bulk RFX 関数の例については `DoFieldExchange` `DoBulkFieldExchange` 、「 [RFX_Text](#rfx_text) 」および「[RFX_Text_Bulk] #rfx_text_bulk)」を参照してください。 DFX 関数は RFX 関数によく似ています。

### <a name="rfx-functions-odbc"></a>RFX 関数 (ODBC)

|名前|説明|
|-|-|
|[RFX_Binary](#rfx_binary)|[CByteArray](cbytearray-class.md)型のバイト配列を転送します。|
|[RFX_Bool](#rfx_bool)|ブール型のデータを転送します。|
|[RFX_Byte](#rfx_byte)|シングル バイトのデータを転送します。|
|[RFX_Date](#rfx_date)|[CTime](../../atl-mfc-shared/reference/ctime-class.md)または TIMESTAMP_STRUCT を使用して、時刻と日付のデータを転送します。|
|[RFX_Double](#rfx_double)|倍精度浮動小数点型のデータを転送します。|
|[RFX_Int](#rfx_int)|整数型のデータを転送します。|
|[RFX_Long](#rfx_long)|長整数型のデータを転送します。|
|[RFX_LongBinary](#rfx_longbinary)|[CLongBinary](clongbinary-class.md) クラスのオブジェクトを使用して、バイナリ ラージ オブジェクト (BLOB) データを転送します。|
|[RFX_Single](#rfx_single)|浮動小数点型のデータを転送します。|
|[RFX_Text](#rfx_text)|文字列型のデータを転送します。|

### <a name="bulk-rfx-functions-odbc"></a>バルク RFX 関数 (ODBC)

|名前|説明|
|-|-|
|[RFX_Binary_Bulk](#rfx_binary_bulk)|バイト データの配列を転送します。|
|[RFX_Bool_Bulk](#rfx_bool_bulk)|ブール型のデータの配列を転送します。|
|[RFX_Byte_Bulk](#rfx_byte_bulk)|シングル バイトの配列を転送します。|
|[RFX_Date_Bulk](#rfx_date_bulk)|TIMESTAMP_STRUCT 型のデータの配列を転送します。|
|[RFX_Double_Bulk](#rfx_double_bulk)|倍精度浮動小数点型のデータの配列を転送します。|
|[RFX_Int_Bulk](#rfx_int_bulk)|整数型のデータの配列を転送します。|
|[RFX_Long_Bulk](#rfx_long_bulk)|長整数型のデータの配列を転送します。|
|[RFX_Single_Bulk](#rfx_single_bulk)|浮動小数点型のデータの配列を転送します。|
|[RFX_Text_Bulk](#rfx_text_bulk)|LPSTR 型のデータの配列を転送します。|

### <a name="dfx-functions-dao"></a>DFX 関数 (DAO)

|名前|説明|
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

## <a name="rfx_binary"></a><a name="rfx_binary"></a> RFX_Binary

オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC 型 SQL_BINARY、SQL_VARBINARY、または SQL_LONGVARBINARY のデータソースのレコードの列との間のバイト配列を転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、 [CByteArray](cbytearray-class.md)型の値が、指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*nMaxLength*<br/>
転送される文字列または配列の許容最大長。 *Nmaxlength*の既定値は255です。 有効な値は 1 ~ INT_MAX です。 フレームワークによって、データ用にこの容量の領域が割り当てられます。 最適なパフォーマンスを得るには、予想される最大のデータ項目に対応できる大きさの値を渡します。

### <a name="remarks"></a>解説

これらの型のデータソース内のデータは、レコードセット内の型との間でマップされ `CByteArray` ます。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_bool"></a><a name="rfx_bool"></a> RFX_Bool

オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC 型 SQL_BIT のデータソースのレコードの列との間でブールデータを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、ブール型の値が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_byte"></a><a name="rfx_byte"></a> RFX_Byte

オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC 型のデータソースのレコードの列との間で、1バイトを転送 SQL_TINYINT ます。

### <a name="syntax"></a>構文

```cpp
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、BYTE 型の値が、指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_date"></a><a name="rfx_date"></a> RFX_Date

`CTime`オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC 型 SQL_DATE、SQL_TIME、または SQL_TIMESTAMP のデータソースのレコードの列との間で、データを転送または TIMESTAMP_STRUCT します。

### <a name="syntax"></a>構文

```cpp
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

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値。転送される値。 関数のさまざまなバージョンは、値として異なるデータ型を受け取ります。

関数の最初のバージョンは、 [CTime](../../atl-mfc-shared/reference/ctime-class.md) オブジェクトへの参照を受け取ります。 レコードセットからデータソースへの転送では、この値は指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

関数の2番目のバージョンは、構造体への参照を受け取り `TIMESTAMP_STRUCT` ます。 この構造体は、呼び出しの前に自分で設定する必要があります。 このバージョンでは、ダイアログデータエクスチェンジ (DDX) のサポートもコードウィザードもサポートされていません。 関数の3番目のバージョンは、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) オブジェクトへの参照を受け取る点を除いて、最初のバージョンと同じように動作します。

### <a name="remarks"></a>解説

`CTime`関数のバージョンでは、一部の中間処理のオーバーヘッドが発生し、範囲が多少制限されています。 これらのいずれかの要因が制限を超えている場合は、関数の2番目のバージョンを使用します。 しかし、コードウィザードと DDX のサポートが不足していること、および自分で構造を設定する必要があることに注意してください。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_double"></a><a name="rfx_double"></a> RFX_Double

オブジェクト**double float**のフィールドデータメンバー `CRecordset` と、ODBC 型 SQL_DOUBLE のデータソースのレコードの列との間で、double float データを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 **`double`** が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_int"></a><a name="rfx_int"></a> RFX_Int

オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC 型 SQL_SMALLINT のデータソースのレコードの列との間で、整数データを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 **`int`** が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_long"></a><a name="rfx_long"></a> RFX_Long

オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC 型 SQL_INTEGER のデータソースのレコードの列との間で長整数データを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 **`long`** が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_longbinary"></a><a name="rfx_longbinary"></a> RFX_LongBinary

[CLongBinary](clongbinary-class.md)クラスを使用してバイナリラージオブジェクト (BLOB) データを転送します。これは、オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC 型 SQL_LONGVARBINARY または SQL_LONGVARCHAR のデータソースのレコードの列の間で使用されます。

### <a name="syntax"></a>構文

```cpp
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 `CLongBinary` が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_single"></a><a name="rfx_single"></a> RFX_Single

オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC 型のデータソースのレコードの列の間で、浮動小数点データを転送 SQL_REAL します。

### <a name="syntax"></a>構文

```cpp
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 **`float`** が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_text"></a><a name="rfx_text"></a> RFX_Text

`CString`オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC の種類 SQL_LONGVARCHAR、SQL_CHAR、SQL_VARCHAR、SQL_DECIMAL、または SQL_NUMERIC のデータソースのレコードの列との間でデータを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Text(
   CFieldExchange* pFX,
   const char* szName,
   CString& value,
   int nMaxLength = 255,
   int nColumnType = SQL_VARCHAR,
   short nScale = 0);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
クラスのオブジェクトへのポインター `CFieldExchange` 。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 `CString` が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*nMaxLength*<br/>
転送される文字列または配列の許容最大長。 *Nmaxlength*の既定値は255です。 有効な値は 1 ~ INT_MAX) です。 フレームワークによって、データ用にこの容量の領域が割り当てられます。 最適なパフォーマンスを得るには、予想される最大のデータ項目に対応できる大きさの値を渡します。

*nColumnType*<br/>
主にパラメーターに使用されます。 パラメーターのデータ型を示す整数。 この型は、 **SQL_XXX**形式の ODBC データ型です。

*nScale*<br/>
ODBC の種類 SQL_DECIMAL または SQL_NUMERIC の値の小数点以下桁数を指定します。 *Nscale* は、パラメーター値を設定する場合にのみ使用できます。 詳細については、 *ODBC SDK プログラマーズリファレンス*の付録 D のトピック「有効桁数、小数点以下桁数、長さ、および表示サイズ」を参照してください。

### <a name="remarks"></a>解説

これらのすべての種類のデータソース内のデータは、レコードセットとの間でマップされ `CString` ます。

### <a name="example"></a>例

この例では、の複数の呼び出しを示し `RFX_Text` ます。 の2つの呼び出しにも注目して `CFieldExchange::SetFieldType` ください。 パラメーターの場合、への呼び出しとその RFX 呼び出しを書き込む必要があり `SetFieldType` ます。 出力列呼び出しとそれに関連付けられている RFX 呼び出しは、通常、コードウィザードによって書き込まれます。

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

## <a name="rfx_binary_bulk"></a><a name="rfx_binary_bulk"></a> RFX_Binary_Bulk

ODBC データソースの列から派生したオブジェクト内の対応する配列に、バイトデータの複数の行を転送 `CRecordset` します。

### <a name="syntax"></a>構文

```cpp
void RFX_Binary_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)オブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 詳細については、「 [レコードフィールドエクスチェンジ: RFX の動作](../../data/odbc/record-field-exchange-how-rfx-works.md)のしくみ」を参照してください。

*szName*<br/>
データ列の名前。

*prgByteVals*<br/>
バイト値の配列へのポインター。 この配列には、データソースからレコードセットに転送されるデータが格納されます。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列は、 *prgByteVals*が指す配列の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合は、SQL_NULL_DATA 値が格納されることに注意してください。 詳細については、 `SQLBindCol` *Odbc SDK プログラマーズリファレンス*の odbc API 関数に関する説明を参照してください。

*nMaxLength*<br/>
*PrgByteVals*が指す配列に格納されている値の許容最大長。 データが切り捨てられないようにするには、予想される最も大きなデータ項目に対応できる大きさの値を渡します。

### <a name="remarks"></a>解説

データソース列には、SQL_BINARY、SQL_VARBINARY、または SQL_LONGVARBINARY の ODBC 型を使用できます。 レコードセットでは、BYTE へのポインター型のフィールドデータメンバーを定義する必要があります。

*PrgByteVals*と*prgLengths*を NULL に初期化すると、そのポインターが指す配列は、行セットのサイズと同じサイズで自動的に割り当てられます。

> [!NOTE]
> バルクレコードフィールドエクスチェンジは、データソースからレコードセットオブジェクトにデータを転送するだけです。 レコードセットを更新できるようにするには、ODBC API 関数を使用する必要があり `SQLSetPos` ます。

詳細については、「レコード [セット: 一括でレコードをフェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 」および「 [レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

### <a name="example"></a>例

「 [RFX_Text_Bulk](#rfx_text_bulk)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_bool_bulk"></a><a name="rfx_bool_bulk"></a> RFX_Bool_Bulk

ODBC データソースの列から派生したオブジェクトの対応する配列に、ブール型のデータの複数の行を転送 `CRecordset` します。

### <a name="syntax"></a>構文

```cpp
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)オブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 詳細については、「 [レコードフィールドエクスチェンジ: RFX の動作](../../data/odbc/record-field-exchange-how-rfx-works.md)のしくみ」を参照してください。

*szName*<br/>
データ列の名前。

*prgBoolVals*<br/>
ブール値の配列へのポインター。 この配列には、データソースからレコードセットに転送されるデータが格納されます。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列は、 *prgBoolVals*が指す配列の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合は、SQL_NULL_DATA 値が格納されることに注意してください。 詳細については、 `SQLBindCol` *Odbc SDK プログラマーズリファレンス*の odbc API 関数に関する説明を参照してください。

### <a name="remarks"></a>解説

データソース列には SQL_BIT の ODBC 型が必要です。 レコードセットでは、BOOL へのポインター型のフィールドデータメンバーを定義する必要があります。

*PrgBoolVals*と*prgLengths*を NULL に初期化すると、そのポインターが指す配列は、行セットのサイズと同じサイズで自動的に割り当てられます。

> [!NOTE]
> バルクレコードフィールドエクスチェンジは、データソースからレコードセットオブジェクトにデータを転送するだけです。 レコードセットを更新できるようにするには、ODBC API 関数を使用する必要があり `SQLSetPos` ます。

詳細については、「レコード [セット: 一括でレコードをフェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 」および「 [レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

### <a name="example"></a>例

「 [RFX_Text_Bulk](#rfx_text_bulk)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_byte_bulk"></a><a name="rfx_byte_bulk"></a> RFX_Byte_Bulk

ODBC データソースの列から、から派生したオブジェクト内の対応する配列に、1バイトの複数行を転送 `CRecordset` します。

### <a name="syntax"></a>構文

```cpp
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)オブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 詳細については、「 [レコードフィールドエクスチェンジ: RFX の動作](../../data/odbc/record-field-exchange-how-rfx-works.md)のしくみ」を参照してください。

*szName*<br/>
データ列の名前。

*prgByteVals*<br/>
バイト値の配列へのポインター。 この配列には、データソースからレコードセットに転送されるデータが格納されます。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列は、 *prgByteVals*が指す配列の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合は、SQL_NULL_DATA 値が格納されることに注意してください。 詳細については、 `SQLBindCol` *Odbc SDK プログラマーズリファレンス*の odbc API 関数に関する説明を参照してください。

### <a name="remarks"></a>解説

データソース列には SQL_TINYINT の ODBC 型が必要です。 レコードセットでは、BYTE へのポインター型のフィールドデータメンバーを定義する必要があります。

*PrgByteVals*と*prgLengths*を NULL に初期化すると、そのポインターが指す配列は、行セットのサイズと同じサイズで自動的に割り当てられます。

> [!NOTE]
> バルクレコードフィールドエクスチェンジは、データソースからレコードセットオブジェクトにデータを転送するだけです。 レコードセットを更新できるようにするには、ODBC API 関数を使用する必要があり `SQLSetPos` ます。

詳細については、「レコード [セット: 一括でレコードをフェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 」および「 [レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

### <a name="example"></a>例

「 [RFX_Text_Bulk](#rfx_text_bulk)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_date_bulk"></a><a name="rfx_date_bulk"></a> RFX_Date_Bulk

ODBC データソースの列から派生したオブジェクトの対応する配列に、TIMESTAMP_STRUCT の複数行のデータを転送 `CRecordset` します。

### <a name="syntax"></a>構文

```cpp
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)オブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 詳細については、「 [レコードフィールドエクスチェンジ: RFX の動作](../../data/odbc/record-field-exchange-how-rfx-works.md)のしくみ」を参照してください。

*szName*<br/>
データ列の名前。

*prgTSVals*<br/>
TIMESTAMP_STRUCT 値の配列へのポインター。 この配列には、データソースからレコードセットに転送されるデータが格納されます。 TIMESTAMP_STRUCT データ型の詳細については、 *ODBC SDK プログラマーズリファレンス*の付録 D の「C データ型」を参照してください。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列は、 *prgTSVals*が指す配列の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合は、SQL_NULL_DATA 値が格納されることに注意してください。 詳細については、 `SQLBindCol` *Odbc SDK プログラマーズリファレンス*の odbc API 関数に関する説明を参照してください。

### <a name="remarks"></a>解説

データソース列には、SQL_DATE、SQL_TIME、または SQL_TIMESTAMP の ODBC 型を使用できます。 レコードセットは、TIMESTAMP_STRUCT へのポインター型のフィールドデータメンバーを定義する必要があります。

*PrgTSVals*と*prgLengths*を NULL に初期化すると、そのポインターが指す配列は、行セットのサイズと同じサイズで自動的に割り当てられます。

> [!NOTE]
> バルクレコードフィールドエクスチェンジは、データソースからレコードセットオブジェクトにデータを転送するだけです。 レコードセットを更新できるようにするには、ODBC API 関数を使用する必要があり `SQLSetPos` ます。

詳細については、「レコード [セット: 一括でレコードをフェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 」および「 [レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

### <a name="example"></a>例

「 [RFX_Text_Bulk](#rfx_text_bulk)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_double_bulk"></a><a name="rfx_double_bulk"></a> RFX_Double_Bulk

ODBC データソースの列から、から派生したオブジェクトの対応する配列に、倍精度浮動小数点データの複数行を転送 `CRecordset` します。

### <a name="syntax"></a>構文

```cpp
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)オブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 詳細については、「 [レコードフィールドエクスチェンジ: RFX の動作](../../data/odbc/record-field-exchange-how-rfx-works.md)のしくみ」を参照してください。

*szName*<br/>
データ列の名前。

*prgDblVals*<br/>
値の配列へのポインター **`double`** 。 この配列には、データソースからレコードセットに転送されるデータが格納されます。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列は、 *prgDblVals*が指す配列の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合は、SQL_NULL_DATA 値が格納されることに注意してください。 詳細については、 `SQLBindCol` *Odbc SDK プログラマーズリファレンス*の odbc API 関数に関する説明を参照してください。

### <a name="remarks"></a>解説

データソース列には SQL_DOUBLE の ODBC 型が必要です。 レコードセットでは、へのポインター型のフィールドデータメンバーを定義する必要があり **`double`** ます。

*PrgDblVals*と*prgLengths*を NULL に初期化すると、そのポインターが指す配列は、行セットのサイズと同じサイズで自動的に割り当てられます。

> [!NOTE]
> バルクレコードフィールドエクスチェンジは、データソースからレコードセットオブジェクトにデータを転送するだけです。 レコードセットを更新できるようにするには、ODBC API 関数を使用する必要があり `SQLSetPos` ます。

詳細については、「レコード [セット: 一括でレコードをフェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 」および「 [レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

### <a name="example"></a>例

「 [RFX_Text_Bulk](#rfx_text_bulk)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_int_bulk"></a><a name="rfx_int_bulk"></a> RFX_Int_Bulk

オブジェクトのフィールドデータメンバー `CRecordset` と、ODBC 型 SQL_SMALLINT のデータソースのレコードの列との間で、整数データを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については `CFieldExchange` 、「 [レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 **`int`** が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

### <a name="example"></a>例

「 [RFX_Text](#rfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_long_bulk"></a><a name="rfx_long_bulk"></a> RFX_Long_Bulk

ODBC データソースの列から派生したオブジェクト内の対応する配列に、長い整数型のデータを複数行転送 `CRecordset` します。

### <a name="syntax"></a>構文

```cpp
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)オブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 詳細については、「 [レコードフィールドエクスチェンジ: RFX の動作](../../data/odbc/record-field-exchange-how-rfx-works.md)のしくみ」を参照してください。

*szName*<br/>
データ列の名前。

*prgLongVals*<br/>
長整数の配列へのポインター。 この配列には、データソースからレコードセットに転送されるデータが格納されます。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列は、 *prgLongVals*が指す配列の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合は、SQL_NULL_DATA 値が格納されることに注意してください。 詳細については、 `SQLBindCol` *Odbc SDK プログラマーズリファレンス*の odbc API 関数に関する説明を参照してください。

### <a name="remarks"></a>解説

データソース列には SQL_INTEGER の ODBC 型が必要です。 レコードセットでは、へのポインター型のフィールドデータメンバーを定義する必要があり **`long`** ます。

*PrgLongVals*と*prgLengths*を NULL に初期化すると、そのポインターが指す配列は、行セットのサイズと同じサイズで自動的に割り当てられます。

> [!NOTE]
> バルクレコードフィールドエクスチェンジは、データソースからレコードセットオブジェクトにデータを転送するだけです。 レコードセットを更新できるようにするには、ODBC API 関数を使用する必要があり `SQLSetPos` ます。

詳細については、「レコード [セット: 一括でレコードをフェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 」および「 [レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

### <a name="example"></a>例

「 [RFX_Text_Bulk](#rfx_text_bulk)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_single_bulk"></a><a name="rfx_single_bulk"></a> RFX_Single_Bulk

ODBC データソースの列から、から派生したオブジェクトの対応する配列に、浮動小数点データの複数の行を転送 `CRecordset` します。

### <a name="syntax"></a>構文

```cpp
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)オブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 詳細については、「 [レコードフィールドエクスチェンジ: RFX の動作](../../data/odbc/record-field-exchange-how-rfx-works.md)のしくみ」を参照してください。

*szName*<br/>
データ列の名前。

*prgFltVals*<br/>
値の配列へのポインター **`float`** 。 この配列には、データソースからレコードセットに転送されるデータが格納されます。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列は、 *prgFltVals*が指す配列の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合は、SQL_NULL_DATA 値が格納されることに注意してください。 詳細については、 `SQLBindCol` *Odbc SDK プログラマーズリファレンス*の odbc API 関数に関する説明を参照してください。

### <a name="remarks"></a>解説

データソース列には SQL_REAL の ODBC 型が必要です。 レコードセットでは、へのポインター型のフィールドデータメンバーを定義する必要があり **`float`** ます。

*PrgFltVals*と*prgLengths*を NULL に初期化すると、そのポインターが指す配列は、行セットのサイズと同じサイズで自動的に割り当てられます。

> [!NOTE]
> バルクレコードフィールドエクスチェンジは、データソースからレコードセットオブジェクトにデータを転送するだけです。 レコードセットを更新できるようにするには、ODBC API 関数を使用する必要があり `SQLSetPos` ます。

詳細については、「レコード [セット: 一括でレコードをフェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 」および「 [レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

### <a name="example"></a>例

「 [RFX_Text_Bulk](#rfx_text_bulk)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_text_bulk"></a><a name="rfx_text_bulk"></a> RFX_Text_Bulk

ODBC データソースの列から、から派生したオブジェクトの対応する配列に、文字データの複数の行を転送 `CRecordset` します。

### <a name="syntax"></a>構文

```cpp
void RFX_Text_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   LPSTR* prgStrVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](cfieldexchange-class.md)オブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。 詳細については、「 [レコードフィールドエクスチェンジ: RFX の動作](../../data/odbc/record-field-exchange-how-rfx-works.md)のしくみ」を参照してください。

*szName*<br/>
データ列の名前。

*prgStrVals*<br/>
LPSTR 値の配列へのポインター。 この配列には、データソースからレコードセットに転送されるデータが格納されます。 ODBC の現在のバージョンでは、これらの値を Unicode にすることはできません。

*prgLengths*<br/>
長整数の配列へのポインター。 この配列は、 *prgStrVals*が指す配列の各値の長さをバイト単位で格納します。 この長さは、null 終了文字を除外します。 対応するデータ項目に Null 値が含まれている場合は、SQL_NULL_DATA 値が格納されることに注意してください。 詳細については、 `SQLBindCol` *Odbc SDK プログラマーズリファレンス*の odbc API 関数に関する説明を参照してください。

*nMaxLength*<br/>
*PrgStrVals*が指す配列に格納されている値の許容最大長 (null 終了文字を含む)。 データが切り捨てられないようにするには、予想される最も大きなデータ項目に対応できる大きさの値を渡します。

### <a name="remarks"></a>解説

データソース列には、SQL_LONGVARCHAR、SQL_CHAR、SQL_VARCHAR、SQL_DECIMAL、または SQL_NUMERIC の ODBC 型を使用できます。 レコードセットでは、型 LPSTR のフィールドデータメンバーを定義する必要があります。

*PrgStrVals*と*prgLengths*を NULL に初期化すると、そのポインターが指す配列は、行セットのサイズと同じサイズで自動的に割り当てられます。

> [!NOTE]
> バルクレコードフィールドエクスチェンジは、データソースからレコードセットオブジェクトにデータを転送するだけです。 レコードセットを更新できるようにするには、ODBC API 関数を使用する必要があり `SQLSetPos` ます。

詳細については、「レコード [セット: 一括でレコードをフェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 」および「 [レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

### <a name="example"></a>例

オーバーライドでは、手動で呼び出しを書き込む必要があり `DoBulkFieldExchange` ます。 この例では、 `RFX_Text_Bulk` データ転送のの呼び出しとの呼び出しを示して `RFX_Long_Bulk` います。 これらの呼び出しの前に、 [CFieldExchange:: SetFieldType](cfieldexchange-class.md#setfieldtype)を呼び出します。 パラメーターの場合、Bulk RFX 関数ではなく、RFX 関数を呼び出す必要があることに注意してください。

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

## <a name="dfx_binary"></a><a name="dfx_binary"></a> DFX_Binary

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールドデータメンバーと、データソース上のレコードの列との間でバイト配列を転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Binary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CByteArray& value,
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、 [CByteArray](cbytearray-class.md)型の値が、指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*nPreAllocSize*<br/>
フレームワークは、この量のメモリを事前します。 データが大きい場合は、必要に応じて、フレームワークにより多くの領域が割り当てられます。 パフォーマンスを向上させるには、このサイズを再割り当てを防ぐのに十分な大きさの値に設定します。 既定のサイズは、AFXDAO で定義されています。H ファイル (AFX_DAO_BINARY_DEFAULT_SIZE)。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_DISABLE_FIELD_CACHE は、ダブルバッファリングを使用しないため、 [SetFieldDirty](cdaorecordset-class.md#setfielddirty) と [SetFieldNull](cdaorecordset-class.md#setfieldnull) を自分で呼び出す必要があります。 もう1つの値である AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。また、フィールドのダーティまたは Null をマークするために余分な作業を行う必要はありません。 パフォーマンスとメモリの理由から、バイナリデータが比較的小さい場合を除き、この値は避けてください。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することにより、すべてのフィールドに対してデータをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型 DAO_BYTES とレコードセットの [CByteArray](cbytearray-class.md) 型の間でマップされます。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_bool"></a><a name="dfx_bool"></a> DFX_Bool

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールドデータメンバーと、データソース上のレコードの列との間でブールデータを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、ブール型の値が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。 その他の有効な値は AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定した場合、MFC ではこのフィールドに対するチェックは行われません。 `SetFieldDirty`とを自分で呼び出す必要があり `SetFieldNull` ます。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型 DAO_BOOL とレコードセットの BOOL 型の間でマップされます。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_byte"></a><a name="dfx_byte"></a> DFX_Byte

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールドデータメンバーとデータソース上のレコードの列との間で、1バイトを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、BYTE 型の値が、指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。 その他の有効な値は AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定した場合、MFC ではこのフィールドに対するチェックは行われません。 `SetFieldDirty`とを自分で呼び出す必要があり `SetFieldNull` ます。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型 DAO_BYTES とレコードセットの BYTE 型の間でマップされます。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_currency"></a><a name="dfx_currency"></a> DFX_Currency

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールドデータメンバーとデータソース上のレコードの列との間で通貨データを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、この値は [COleCurrency](colecurrency-class.md)型の指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。 その他の有効な値は AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定した場合、MFC ではこのフィールドに対するチェックは行われません。 `SetFieldDirty`とを自分で呼び出す必要があり `SetFieldNull` ます。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型 DAO_CURRENCY とレコードセットの [COleCurrency](colecurrency-class.md) 型の間でマップされます。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_datetime"></a><a name="dfx_datetime"></a> DFX_DateTime

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールドデータメンバーとデータソース上のレコードの列との間で、時刻と日付のデータを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 関数は、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) オブジェクトへの参照を受け取ります。 レコードセットからデータソースへの転送では、この値は指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。 その他の有効な値は AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定した場合、MFC ではこのフィールドに対するチェックは行われません。 `SetFieldDirty`とを自分で呼び出す必要があり `SetFieldNull` ます。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型 DAO_DATE とレコードセットの型 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) の間でマップされます。

> [!NOTE]
> `COleDateTime` DAO クラスでこの目的のために、 [CTime](../../atl-mfc-shared/reference/ctime-class.md) と TIMESTAMP_STRUCT を置き換えます。 `CTime` および TIMESTAMP_STRUCT は、ODBC ベースのデータアクセスクラスでも使用されます。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_double"></a><a name="dfx_double"></a> DFX_Double

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールドデータメンバーとデータソース上のレコードの列との間で、 **double float 型**のデータを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 **`double`** が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。 その他の有効な値は AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定した場合、MFC ではこのフィールドに対するチェックは行われません。 `SetFieldDirty`とを自分で呼び出す必要があり `SetFieldNull` ます。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型 DAO_R8 とレコードセットの **double float** 型の間でマップされます。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_long"></a><a name="dfx_long"></a> DFX_Long

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールドデータメンバーとデータソース上のレコードの列との間で長整数データを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 **`long`** が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。 その他の有効な値は AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定した場合、MFC ではこのフィールドに対するチェックは行われません。 `SetFieldDirty`とを自分で呼び出す必要があり `SetFieldNull` ます。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型 DAO_I4 とレコードセットの型の間でマップされ **`long`** ます。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_longbinary"></a><a name="dfx_longbinary"></a> DFX_LongBinary

**重要** この関数の代わりに [DFX_Binary](#dfx_binary) を使用することをお勧めします。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_LongBinary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CLongBinary& value,
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、 [CLongBinary](clongbinary-class.md)型の値が、指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*dwPreAllocSize*<br/>
フレームワークは、この量のメモリを事前します。 データが大きい場合は、必要に応じて、フレームワークにより多くの領域が割り当てられます。 パフォーマンスを向上させるには、このサイズを再割り当てを防ぐのに十分な大きさの値に設定します。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DISABLE_FIELD_CACHE では、ダブルバッファリングは使用されません。 その他の有効な値は AFX_DAO_ENABLE_FIELD_CACHE です。 では、ダブルバッファリングが使用されます。また、フィールドのダーティまたは Null をマークするために余分な作業を行う必要はありません。 パフォーマンスとメモリの理由から、バイナリデータが比較的小さい場合を除き、この値は避けてください。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

`DFX_LongBinary` は、MFC ODBC クラスとの互換性を維持するために用意されています。 関数は、 `DFX_LongBinary` クラスを使用して、 `CLongBinary` [CDaoRecordset](cdaorecordset-class.md) オブジェクトのフィールドデータメンバーとデータソース上のレコードの列の間で、バイナリラージオブジェクト (BLOB) データを転送します。 データは、DAO の型 DAO_BYTES とレコードセットの [CLongBinary](clongbinary-class.md) 型の間でマップされます。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_short"></a><a name="dfx_short"></a> DFX_Short

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールドデータメンバーとデータソース上のレコードの列との間で short 整数データを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 **`short`** が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。 その他の有効な値は AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定した場合、MFC ではこのフィールドに対するチェックは行われません。 `SetFieldDirty`とを自分で呼び出す必要があり `SetFieldNull` ます。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型 DAO_I2 とレコードセットの型の間でマップされ **`short`** ます。

> [!NOTE]
> `DFX_Short` は、ODBC ベースのクラスの [RFX_Int](#rfx_int) に相当します。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_single"></a><a name="dfx_single"></a> DFX_Single

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールドデータメンバーとデータソース上のレコードの列との間で、浮動小数点データを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、型の値 **`float`** が指定されたデータメンバーから取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。 その他の有効な値は AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定した場合、MFC ではこのフィールドに対するチェックは行われません。 `SetFieldDirty`とを自分で呼び出す必要があり `SetFieldNull` ます。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型 DAO_R4 とレコードセットの型の間でマップされ **`float`** ます。

### <a name="example"></a>例

「 [DFX_Text](#dfx_text)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="dfx_text"></a><a name="dfx_text"></a> DFX_Text

は、 `CString` [CDaoRecordset](cdaorecordset-class.md) オブジェクトのフィールドデータメンバーと、データソース上のレコードの列の間でデータを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Text(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CString& value,
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)クラスのオブジェクトへのポインター。 このオブジェクトには、関数の各呼び出しのコンテキストを定義するための情報が含まれています。

*szName*<br/>
データ列の名前。

*value*<br/>
指定されたデータメンバーに格納されている値 (転送される値)。 レコードセットからデータソースへの転送では、指定されたデータメンバーから [CString](../../atl-mfc-shared/reference/cstringt-class.md)型の値が取得されます。 データソースからレコードセットへの転送では、値は指定されたデータメンバーに格納されます。

*nPreAllocSize*<br/>
フレームワークは、この量のメモリを事前します。 データが大きい場合は、必要に応じて、フレームワークにより多くの領域が割り当てられます。 パフォーマンスを向上させるには、このサイズを再割り当てを防ぐのに十分な大きさの値に設定します。

*dwBindOptions*<br/>
変更されたレコードセットフィールドを検出するために、MFC のダブルバッファリング機構を利用できるようにするオプション。 既定の AFX_DAO_ENABLE_FIELD_CACHE は、ダブルバッファリングを使用します。 その他の有効な値は AFX_DAO_DISABLE_FIELD_CACHE です。 この値を指定した場合、MFC ではこのフィールドに対するチェックは行われません。 [SetFieldDirty](cdaorecordset-class.md#setfielddirty)と[SetFieldNull](cdaorecordset-class.md#setfieldnull)を自分で呼び出す必要があります。

> [!NOTE]
> 既定では、 [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することによって、データをダブルバッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO 内の DAO_CHAR 型の間でマップされます (または、シンボル _UNICODE が定義されている場合は DAO_WCHAR)。また、レコードセットに [CString](../../atl-mfc-shared/reference/cstringt-class.md) を入力します。  n

### <a name="example"></a>例

この例では、の複数の呼び出しを示し `DFX_Text` ます。 [CDaoFieldExchange:: SetFieldType](cdaofieldexchange-class.md#setfieldtype)の2つの呼び出しにも注目してください。 への最初の呼び出しと、 `SetFieldType` その **DFX** 呼び出しを記述する必要があります。 2番目の呼び出しとそれに関連付けられている **DFX** 呼び出しは、通常、クラスを生成したコードウィザードによって書き込まれます。

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

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CRecordset::D oFieldExchange](crecordset-class.md#dofieldexchange)<br/>
[CRecordset::D oBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)<br/>
[CDaoRecordset::D oFieldExchange](cdaorecordset-class.md#dofieldexchange)
