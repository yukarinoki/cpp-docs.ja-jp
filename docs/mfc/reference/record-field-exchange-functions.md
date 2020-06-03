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
ms.openlocfilehash: bfd3ba64a33547b8a27e0f3bc896f39c94486464
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372985"
---
# <a name="record-field-exchange-functions"></a>レコード フィールド エクスチェンジ (RFX) 関数

ここでは、レコードセット オブジェクトとそのデータ ソース間のデータ転送を自動化したり、データに対してその他の操作を実行したりするためのレコード フィールド エクスチェンジの関数 (RFX、バルク RFX、および DFX) の一覧を示します。

ODBC ベースのクラスを使用し、バルク行フェッチを実装している場合は、データ ソース列に対応する各データ メンバーに対してバルク RFX 関数を呼び出すことによって、 `DoBulkFieldExchange` の `CRecordset` メンバー関数を手動でオーバーライドする必要があります。

ODBC ベースのクラスでバルク行フェッチを実装していない場合、または DAO ベースのクラス (廃止) を使用している場合、ClassWizard は、`DoFieldExchange`レコードセット内`CRecordset`の`CDaoRecordset`各フィールド データ メンバーの RFX 関数 (ODBC クラスの場合) または DFX 関数 (DAO クラスの場合) のメンバー関数をオーバーライドします。

レコード フィールド エクスチェンジ関数は、フレームワークが `DoFieldExchange` または `DoBulkFieldExchange`を呼び出すたびにデータを転送します。 それぞれの関数が特定のデータ型を転送します。

これらの関数の使い方の詳細については、「 [レコード フィールド エクスチェンジ: RFX のしくみ (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

動的にバインドするデータの列では、RFX 関数または DFX 関数を手動で呼び出すこともできます。詳細については、「 [レコードセット: データ列を動的に結びつける方法 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。 また、独自のカスタム RFX ルーチンまたは DFX ルーチンを記述することもできます。詳細については、テクニカル ノート [43](../../mfc/tn043-rfx-routines.md) (ODBC の場合) およびテクニカル ノート [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (DAO の場合) を参照してください。

関数および関数に表示される RFX および Bulk RFX `DoFieldExchange` `DoBulkFieldExchange`関数の例については[、「RFX_Text](#rfx_text)と [RFX_Text_Bulk]#rfx_text_bulk)」を参照してください。 DFX 関数は RFX 関数によく似ています。

### <a name="rfx-functions-odbc"></a>RFX 関数 (ODBC)

|||
|-|-|
|[RFX_Binary](#rfx_binary)|[CByteArray](cbytearray-class.md)型のバイト配列を転送します。|
|[RFX_Bool](#rfx_bool)|ブール型のデータを転送します。|
|[RFX_Byte](#rfx_byte)|シングル バイトのデータを転送します。|
|[RFX_Date](#rfx_date)|[CTime](../../atl-mfc-shared/reference/ctime-class.md)またはTIMESTAMP_STRUCTを使用して、時刻と日付のデータを転送します。|
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
|[RFX_Date_Bulk](#rfx_date_bulk)|TIMESTAMP_STRUCT 型のデータの配列を転送します。|
|[RFX_Double_Bulk](#rfx_double_bulk)|倍精度浮動小数点型のデータの配列を転送します。|
|[RFX_Int_Bulk](#rfx_int_bulk)|整数型のデータの配列を転送します。|
|[RFX_Long_Bulk](#rfx_long_bulk)|長整数型のデータの配列を転送します。|
|[RFX_Single_Bulk](#rfx_single_bulk)|浮動小数点型のデータの配列を転送します。|
|[RFX_Text_Bulk](#rfx_text_bulk)|LPSTR 型のデータの配列を転送します。|

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

## <a name="rfx_binary"></a><a name="rfx_binary"></a>RFX_Binary

`CRecordset`オブジェクトのフィールド データ メンバーと、ODBC 型 SQL_BINARY、SQL_VARBINARY、またはSQL_LONGVARBINARYのデータ ソース上のレコードの列との間でバイト配列を転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では[、CByteArray](cbytearray-class.md)型の値は、指定されたデータ メンバーから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*長さ*<br/>
転送される文字列または配列の最大許容長。 *nMaxLength*の既定値は 255 です。 有効値は 1 からINT_MAXです。 フレームワークは、このデータの領域を割り当てます。 最適なパフォーマンスを得るためには、予想される最大のデータ項目に対応できる大きさの値を渡します。

### <a name="remarks"></a>解説

これらの型のデータ ソースのデータは、レコードセット内の型`CByteArray`との間でマップされます。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_bool"></a><a name="rfx_bool"></a>RFX_Bool

`CRecordset`オブジェクトのフィールド データ メンバーと、ODBC 型 SQL_BIT のデータ ソース上のレコードの列との間でブール型データを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では、BOOL 型の値は、指定されたデータ メンバーから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_byte"></a><a name="rfx_byte"></a>RFX_Byte

`CRecordset`オブジェクトのフィールド データ メンバーと、ODBC 型のデータ ソースのレコードの列との間で、1 バイトSQL_TINYINT転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では、BYTE 型の値は指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_date"></a><a name="rfx_date"></a>RFX_Date

ODBC `CTime` SQL_DATE 型、SQL_TIME型、またはSQL_TIMESTAMPのデータ ソース上のフィールド データ メンバーとレコードの列との間でデータを転送またはTIMESTAMP_STRUCTします。 `CRecordset`

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

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値。転送される値。 関数のさまざまなバージョンでは、値に対して異なるデータ型を使用します。

関数の最初のバージョンは[、CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照を受け取ります。 レコードセットからデータ ソースへの転送では、この値は指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

関数の 2 番目のバージョンは、構造体`TIMESTAMP_STRUCT`への参照を受け取ります。 呼び出しの前に、この構造を自分で設定する必要があります。 このバージョンでは、ダイアログ データ エクスチェンジ (DDX) のサポートもコード ウィザードのサポートも提供していません。 関数の 3 番目のバージョンは[、COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへの参照を受け取る点を除いて、最初のバージョンと同様に動作します。

### <a name="remarks"></a>解説

関数`CTime`のバージョンは、いくつかの中間処理のオーバーヘッドを課し、やや限られた範囲を持っています。 これらの要因のいずれかが制限されすぎている場合は、2 番目のバージョンの関数を使用します。 ただし、コード ウィザードと DDX のサポートが不足していること、および自分で構造を設定する必要があることに注意してください。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_double"></a><a name="rfx_double"></a>RFX_Double

オブジェクトのフィールド データ メンバーと、ODBC 型 SQL_DOUBLEのデータ ソース上のレコードの列との間で **、倍数の浮動**データを転送します。 `CRecordset`

### <a name="syntax"></a>構文

```cpp
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では **、double**型の値は指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_int"></a><a name="rfx_int"></a>RFX_Int

`CRecordset`オブジェクトのフィールド データ メンバーと、ODBC 型 SQL_SMALLINTのデータ ソース上のレコードの列との間で整数データを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では **、int**型の値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_long"></a><a name="rfx_long"></a>RFX_Long

`CRecordset`オブジェクトのフィールド データ メンバーと、ODBC 型のデータ ソースのレコードの列との間で長整数データSQL_INTEGER転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では **、long**型の値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_longbinary"></a><a name="rfx_longbinary"></a>RFX_LongBinary

オブジェクトのフィールド データ メンバーと ODBC 型のデータ ソースのレコードの列と`CRecordset`の間でクラス[CLongBinary](clongbinary-class.md)を使用してバイナリ ラージ オブジェクト (BLOB) データを転送SQL_LONGVARBINARYまたはSQL_LONGVARCHARします。

### <a name="syntax"></a>構文

```cpp
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では、type`CLongBinary`の値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_single"></a><a name="rfx_single"></a>RFX_Single

`CRecordset`オブジェクトのフィールド データ メンバーと、ODBC 型 SQL_REAL のデータ ソース上のレコードの列との間で浮動小数点データを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では、float**型の**値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_text"></a><a name="rfx_text"></a>RFX_Text

ODBC`CString`型 SQL_LONGVARCHAR、SQL_CHAR、SQL_VARCHAR、SQL_DECIMAL、またはSQL_NUMERICのデータ ソース上のレコードのオブジェクトのフィールド データ メンバーと列の間でデータを転送します。 `CRecordset`

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

*Pfx*<br/>
クラス`CFieldExchange`のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では、type`CString`の値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*長さ*<br/>
転送される文字列または配列の最大許容長。 *nMaxLength*の既定値は 255 です。 有効値は 1 ~ INT_MAX) です。 フレームワークは、このデータの領域を割り当てます。 最適なパフォーマンスを得るためには、予想される最大のデータ項目に対応できる大きさの値を渡します。

*n列の種類*<br/>
主にパラメータに使用されます。 パラメーターのデータ型を示す整数。 型は、 フォーム SQL_XXX の ODBC データ型**です**。

*nスケール*<br/>
ODBC タイプ SQL_DECIMALまたはSQL_NUMERICの値のスケールを指定します。 *nScale*はパラメータ値を設定する場合にのみ便利です。 詳細については *、「ODBC SDK プログラマ リファレンス*」の「付録 D 」の「精度、倍率、長さ、および表示サイズ」を参照してください。

### <a name="remarks"></a>解説

これらの型のデータ ソースのデータは、レコードセット`CString`内でマップされます。

### <a name="example"></a>例

この例では、 への`RFX_Text`いくつかの呼び出しを示します。 また、2 つの呼`CFieldExchange::SetFieldType`び出しにも注意してください。 パラメータの場合は、呼び出`SetFieldType`しとその RFX 呼び出しを記述する必要があります。 出力列呼び出しとそれに関連する RFX 呼び出しは、通常、コード ウィザードによって記述されます。

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

## <a name="rfx_binary_bulk"></a><a name="rfx_binary_bulk"></a>RFX_Binary_Bulk

ODBC データ ソースの列から、複数行のバイト データを`CRecordset`、派生オブジェクトの対応する配列に転送します。

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

*Pfx*<br/>
[オブジェクト](cfieldexchange-class.md)へのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 詳細については、「レコード フィールド[エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。

*Szname*<br/>
データ列の名前。

*プルグバイトバル*<br/>
BYTE 値の配列へのポインター。 この配列は、データ ソースからレコードセットに転送されるデータを格納します。

*長さ*<br/>
長整数の配列へのポインター。 この配列は *、prgByteVals*が指す配列内の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合、SQL_NULL_DATA値が格納されることに注意してください。 詳細については、『ODBC SDK プログラマ`SQLBindCol`リファレンス』の ODBC API 関数*を参照*してください。

*長さ*<br/>
*prgByteVals*が指す配列に格納されている値の最大許容長。 データが切り捨てられないようにするには、予想される最大のデータ項目に対応できる大きさの値を渡します。

### <a name="remarks"></a>解説

データ ソース列には、SQL_BINARY、SQL_VARBINARY、またはSQL_LONGVARBINARYの ODBC 型を使用できます。 レコードセットは、BYTE へのポインター型のフィールド データ メンバーを定義する必要があります。

*prgByteVals*と*prgLengths*を NULL に初期化すると、それらが指す配列は自動的に割り当てられます。

> [!NOTE]
> バルク レコード フィールドエクスチェンジでは、データ ソースからレコードセット オブジェクトにデータが転送されるだけです。 レコードセットを更新可能にするには、ODBC API 関数`SQLSetPos`を使用する必要があります。

詳細については、「[レコードセット : レコードを一括 (ODBC) にフェッチする 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)および「[レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

### <a name="example"></a>例

[RFX_Text_Bulk](#rfx_text_bulk)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_bool_bulk"></a><a name="rfx_bool_bulk"></a>RFX_Bool_Bulk

ODBC データ ソースの列から、複数の行のブール型データを`CRecordset`、派生オブジェクトの対応する配列に転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
[オブジェクト](cfieldexchange-class.md)へのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 詳細については、「レコード フィールド[エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。

*Szname*<br/>
データ列の名前。

*プルグブールヴァル*<br/>
BOOL 値の配列へのポインター。 この配列は、データ ソースからレコードセットに転送されるデータを格納します。

*長さ*<br/>
長整数の配列へのポインター。 この配列は *、prgBoolVals*が指す配列内の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合、SQL_NULL_DATA値が格納されることに注意してください。 詳細については、『ODBC SDK プログラマ`SQLBindCol`リファレンス』の ODBC API 関数*を参照*してください。

### <a name="remarks"></a>解説

データ ソース列には、ODBC 型のSQL_BITが必要です。 レコードセットは、BOOL へのポインター型のフィールド データ メンバーを定義する必要があります。

*prgBoolVals*と*prgLengths*を NULL に初期化すると、それらが指す配列は自動的に割り当てられ、サイズは行セットのサイズと同じになります。

> [!NOTE]
> バルク レコード フィールドエクスチェンジでは、データ ソースからレコードセット オブジェクトにデータが転送されるだけです。 レコードセットを更新可能にするには、ODBC API 関数`SQLSetPos`を使用する必要があります。

詳細については、「[レコードセット : レコードを一括 (ODBC) にフェッチする 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)および「[レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

### <a name="example"></a>例

[RFX_Text_Bulk](#rfx_text_bulk)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_byte_bulk"></a><a name="rfx_byte_bulk"></a>RFX_Byte_Bulk

ODBC データ ソースの列から、1 バイトの複数行を、派生オブジェクトの対応`CRecordset`する配列に転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
[オブジェクト](cfieldexchange-class.md)へのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 詳細については、「レコード フィールド[エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。

*Szname*<br/>
データ列の名前。

*プルグバイトバル*<br/>
BYTE 値の配列へのポインター。 この配列は、データ ソースからレコードセットに転送されるデータを格納します。

*長さ*<br/>
長整数の配列へのポインター。 この配列は *、prgByteVals*が指す配列内の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合、SQL_NULL_DATA値が格納されることに注意してください。 詳細については、『ODBC SDK プログラマ`SQLBindCol`リファレンス』の ODBC API 関数*を参照*してください。

### <a name="remarks"></a>解説

データ ソース列には、ODBC 型のSQL_TINYINTが必要です。 レコードセットは、BYTE へのポインター型のフィールド データ メンバーを定義する必要があります。

*prgByteVals*と*prgLengths*を NULL に初期化すると、それらが指す配列は自動的に割り当てられます。

> [!NOTE]
> バルク レコード フィールドエクスチェンジでは、データ ソースからレコードセット オブジェクトにデータが転送されるだけです。 レコードセットを更新可能にするには、ODBC API 関数`SQLSetPos`を使用する必要があります。

詳細については、「[レコードセット : レコードを一括 (ODBC) にフェッチする 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)および「[レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

### <a name="example"></a>例

[RFX_Text_Bulk](#rfx_text_bulk)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_date_bulk"></a><a name="rfx_date_bulk"></a>RFX_Date_Bulk

ODBC データ ソースの列から複数の行TIMESTAMP_STRUCTデータを`CRecordset`、派生オブジェクトの対応する配列に転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
[オブジェクト](cfieldexchange-class.md)へのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 詳細については、「レコード フィールド[エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。

*Szname*<br/>
データ列の名前。

*プットヴァル*<br/>
TIMESTAMP_STRUCT値の配列へのポインター。 この配列は、データ ソースからレコードセットに転送されるデータを格納します。 TIMESTAMP_STRUCTデータ型の詳細については *、「ODBC SDK プログラマ リファレンス*」の「付録 D 」の「C データ型」を参照してください。

*長さ*<br/>
長整数の配列へのポインター。 この配列は *、prgTVals*が指す配列内の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合、SQL_NULL_DATA値が格納されることに注意してください。 詳細については、『ODBC SDK プログラマ`SQLBindCol`リファレンス』の ODBC API 関数*を参照*してください。

### <a name="remarks"></a>解説

データ ソース列には、SQL_DATE、SQL_TIME、またはSQL_TIMESTAMPの ODBC 型を使用できます。 レコードセットは、TIMESTAMP_STRUCTへのポインター型のフィールド データ メンバーを定義する必要があります。

*prgTSVals*と*prgLengths*を NULL に初期化すると、それらが指す配列は自動的に割り当てられ、サイズは行セットのサイズと同じになります。

> [!NOTE]
> バルク レコード フィールドエクスチェンジでは、データ ソースからレコードセット オブジェクトにデータが転送されるだけです。 レコードセットを更新可能にするには、ODBC API 関数`SQLSetPos`を使用する必要があります。

詳細については、「[レコードセット : レコードを一括 (ODBC) にフェッチする 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)および「[レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

### <a name="example"></a>例

[RFX_Text_Bulk](#rfx_text_bulk)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_double_bulk"></a><a name="rfx_double_bulk"></a>RFX_Double_Bulk

ODBC データ ソースの列から、派生オブジェクトの対応する配列に倍精度浮動小数点データの複数の行を`CRecordset`転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
[オブジェクト](cfieldexchange-class.md)へのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 詳細については、「レコード フィールド[エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。

*Szname*<br/>
データ列の名前。

*プリュドブルヴァル*<br/>
**倍精度**浮動小数点数型の値の配列へのポインター。 この配列は、データ ソースからレコードセットに転送されるデータを格納します。

*長さ*<br/>
長整数の配列へのポインター。 この配列は *、prgDblVals*が指す配列内の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合、SQL_NULL_DATA値が格納されることに注意してください。 詳細については、『ODBC SDK プログラマ`SQLBindCol`リファレンス』の ODBC API 関数*を参照*してください。

### <a name="remarks"></a>解説

データ ソース列には、ODBC 型のSQL_DOUBLEが必要です。 レコードセットは、 **double**型ポインタのフィールド データ メンバを定義する必要があります。

*prgDblVals*と*prgLengths*を NULL に初期化すると、それらが指す配列は自動的に割り当てられ、サイズは行セットのサイズと同じになります。

> [!NOTE]
> バルク レコード フィールドエクスチェンジでは、データ ソースからレコードセット オブジェクトにデータが転送されるだけです。 レコードセットを更新可能にするには、ODBC API 関数`SQLSetPos`を使用する必要があります。

詳細については、「[レコードセット : レコードを一括 (ODBC) にフェッチする 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)および「[レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

### <a name="example"></a>例

[RFX_Text_Bulk](#rfx_text_bulk)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_int_bulk"></a><a name="rfx_int_bulk"></a>RFX_Int_Bulk

`CRecordset`オブジェクトのフィールド データ メンバーと、ODBC 型 SQL_SMALLINTのデータ ソース上のレコードの列との間で整数データを転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CFieldExchange](cfieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 オブジェクトが指定できる操作の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 `CFieldExchange`

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では **、int**型の値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

### <a name="example"></a>例

[RFX_Text](#rfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_long_bulk"></a><a name="rfx_long_bulk"></a>RFX_Long_Bulk

ODBC データ ソースの列から、派生オブジェクトの対応する配列に長整数データの複数の`CRecordset`行を転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
[オブジェクト](cfieldexchange-class.md)へのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 詳細については、「レコード フィールド[エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。

*Szname*<br/>
データ列の名前。

*prgLongVals*<br/>
長整数の配列へのポインター。 この配列は、データ ソースからレコードセットに転送されるデータを格納します。

*長さ*<br/>
長整数の配列へのポインター。 この配列は *、prgLongVals*が指す配列内の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合、SQL_NULL_DATA値が格納されることに注意してください。 詳細については、『ODBC SDK プログラマ`SQLBindCol`リファレンス』の ODBC API 関数*を参照*してください。

### <a name="remarks"></a>解説

データ ソース列には、ODBC 型の SQL_INTEGER が必要です。 レコードセットは、 **long**型のポインターのフィールド データ メンバーを定義する必要があります。

*prgLongVals*と*prgLengths*を NULL に初期化すると、それらが指す配列は自動的に割り当てられ、サイズは行セットのサイズと同じになります。

> [!NOTE]
> バルク レコード フィールドエクスチェンジでは、データ ソースからレコードセット オブジェクトにデータが転送されるだけです。 レコードセットを更新可能にするには、ODBC API 関数`SQLSetPos`を使用する必要があります。

詳細については、「[レコードセット : レコードを一括 (ODBC) にフェッチする 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)および「[レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

### <a name="example"></a>例

[RFX_Text_Bulk](#rfx_text_bulk)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_single_bulk"></a><a name="rfx_single_bulk"></a>RFX_Single_Bulk

ODBC データ ソースの列から、複数行の浮動小数点データを`CRecordset`、派生オブジェクトの対応する配列に転送します。

### <a name="syntax"></a>構文

```cpp
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
[オブジェクト](cfieldexchange-class.md)へのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 詳細については、「レコード フィールド[エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。

*Szname*<br/>
データ列の名前。

*prgFltVals*<br/>
**浮動小数点**値の配列へのポインター。 この配列は、データ ソースからレコードセットに転送されるデータを格納します。

*長さ*<br/>
長整数の配列へのポインター。 この配列は *、prgFltVals*が指す配列内の各値の長さをバイト単位で格納します。 対応するデータ項目に Null 値が含まれている場合、SQL_NULL_DATA値が格納されることに注意してください。 詳細については、『ODBC SDK プログラマ`SQLBindCol`リファレンス』の ODBC API 関数*を参照*してください。

### <a name="remarks"></a>解説

データ ソース列には、ODBC 型のSQL_REALが必要です。 レコードセットは **、float**型のポインターのフィールド データ メンバーを定義する必要があります。

*prgFltVals*と*prgLengths*を NULL に初期化すると、それらが指す配列は自動的に割り当てられ、サイズは行セットのサイズと同じになります。

> [!NOTE]
> バルク レコード フィールドエクスチェンジでは、データ ソースからレコードセット オブジェクトにデータが転送されるだけです。 レコードセットを更新可能にするには、ODBC API 関数`SQLSetPos`を使用する必要があります。

詳細については、「[レコードセット : レコードを一括 (ODBC) にフェッチする 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)および「[レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

### <a name="example"></a>例

[RFX_Text_Bulk](#rfx_text_bulk)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="rfx_text_bulk"></a><a name="rfx_text_bulk"></a>RFX_Text_Bulk

ODBC データ ソースの列から、複数行の文字データを、派生オブジェクトの対応する`CRecordset`配列に転送します。

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

*Pfx*<br/>
[オブジェクト](cfieldexchange-class.md)へのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。 詳細については、「レコード フィールド[エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。

*Szname*<br/>
データ列の名前。

*プルグストルヴァル*<br/>
LPSTR 値の配列へのポインター。 この配列は、データ ソースからレコードセットに転送されるデータを格納します。 ODBC の現在のバージョンでは、これらの値を Unicode にすることはできません。

*長さ*<br/>
長整数の配列へのポインター。 この配列は *、prgStrVals*が指す配列内の各値の長さをバイト単位で格納します。 この長さは、NULL 終了文字を除きます。 対応するデータ項目に Null 値が含まれている場合、SQL_NULL_DATA値が格納されることに注意してください。 詳細については、『ODBC SDK プログラマ`SQLBindCol`リファレンス』の ODBC API 関数*を参照*してください。

*長さ*<br/>
*prgStrVals*が指す配列に格納されている値の最大許容長 (null 終了文字を含む)。 データが切り捨てられないようにするには、予想される最大のデータ項目に対応できる大きさの値を渡します。

### <a name="remarks"></a>解説

データ ソース列には、ODBC 型の SQL_LONGVARCHAR、SQL_CHAR、SQL_VARCHAR、SQL_DECIMAL、またはSQL_NUMERICを使用できます。 レコードセットは、LPSTR 型のフィールド データ メンバーを定義する必要があります。

*prgStrVals*と*prgLengths*を NULL に初期化すると、それらが指す配列は自動的に割り当てられ、サイズは行セットのサイズと同じになります。

> [!NOTE]
> バルク レコード フィールドエクスチェンジでは、データ ソースからレコードセット オブジェクトにデータが転送されるだけです。 レコードセットを更新可能にするには、ODBC API 関数`SQLSetPos`を使用する必要があります。

詳細については、「[レコードセット : レコードを一括 (ODBC) にフェッチする 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)および「[レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

### <a name="example"></a>例

オーバーライドで手動で呼び出`DoBulkFieldExchange`しを書き込む必要があります。 この例では、データ転送`RFX_Text_Bulk`の 呼び出しと`RFX_Long_Bulk`、 への呼び出しを示します。 これらの呼び出しの前に[、CFieldExchange::SetFieldType](cfieldexchange-class.md#setfieldtype)への呼び出しが行われます。 パラメータの場合は、バルク RFX 関数の代わりに RFX 関数を呼び出す必要があります。

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

## <a name="dfx_binary"></a><a name="dfx_binary"></a>DFX_Binary

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソース上のレコードの列との間でバイト配列を転送します。

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

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では[、CByteArray](cbytearray-class.md)型の値は、指定されたデータ メンバーから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*大きさの大きさ*<br/>
フレームワークは、このメモリ量を事前に割り当てます。 データが大きい場合、フレームワークは必要に応じてより多くの領域を割り当てます。 パフォーマンスを向上させるには、このサイズを再割り当てを防ぐのに十分な大きさに設定します。 デフォルトのサイズは AFXDAO で定義されています。h ファイルをAFX_DAO_BINARY_DEFAULT_SIZE。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 既定のAFX_DAO_DISABLE_FIELD_CACHEはダブル バッファリングを使用しないため、自分で[SetFieldDirty](cdaorecordset-class.md#setfielddirty)と[SetFieldNull を](cdaorecordset-class.md#setfieldnull)呼び出す必要があります。 もう 1 つの値AFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用するため、フィールドをダーティまたは Null にマークするために余分な作業を行う必要はありません。 パフォーマンスとメモリの理由から、バイナリ データが比較的小さい場合を除き、この値は使用しないでください。

> [!NOTE]
> 既定では[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定することで、すべてのフィールドに対してデータをダブル バッファリングするかどうかを制御できます。

### <a name="remarks"></a>解説

データは、DAO の型DAO_BYTESとレコードセットの[CByteArray](cbytearray-class.md)型の間でマップされます。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_bool"></a><a name="dfx_bool"></a>DFX_Bool

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソースのレコードの列との間でブール型データを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では、BOOL 型の値は、指定されたデータ メンバーから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用します。 もう 1 つの値はAFX_DAO_DISABLE_FIELD_CACHE。 この値を指定すると、MFC はこのフィールドをチェックしません。 あなたは電話して`SetFieldDirty`自分自身`SetFieldNull`を呼び出す必要があります。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

データは、DAO の型DAO_BOOLとレコードセットの BOOL 型の間でマップされます。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_byte"></a><a name="dfx_byte"></a>DFX_Byte

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソースのレコードの列との間で、単一バイトを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では、BYTE 型の値は指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用します。 もう 1 つの値はAFX_DAO_DISABLE_FIELD_CACHE。 この値を指定すると、MFC はこのフィールドをチェックしません。 あなたは電話して`SetFieldDirty`自分自身`SetFieldNull`を呼び出す必要があります。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

データは、DAO の型DAO_BYTESとレコードセットの BYTE 型の間でマップされます。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_currency"></a><a name="dfx_currency"></a>DFX_Currency

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソースのレコードの列との間で通貨データを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送の場合、この値は、指定された型[の COleCurrency](colecurrency-class.md)から取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用します。 もう 1 つの値はAFX_DAO_DISABLE_FIELD_CACHE。 この値を指定すると、MFC はこのフィールドをチェックしません。 あなたは電話して`SetFieldDirty`自分自身`SetFieldNull`を呼び出す必要があります。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

データは、DAO の型DAO_CURRENCYとレコードセットの[COleCurrency](colecurrency-class.md)型の間でマップされます。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_datetime"></a><a name="dfx_datetime"></a>DFX_DateTime

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソースのレコードの列との間で時刻と日付のデータを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 この関数は、[オブジェクト](../../atl-mfc-shared/reference/coledatetime-class.md)への参照を受け取ります。 レコードセットからデータ ソースへの転送では、この値は指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用します。 もう 1 つの値はAFX_DAO_DISABLE_FIELD_CACHE。 この値を指定すると、MFC はこのフィールドをチェックしません。 あなたは電話して`SetFieldDirty`自分自身`SetFieldNull`を呼び出す必要があります。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

データは、DAO の型DAO_DATEとレコードセットの[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)型の間でマップされます。

> [!NOTE]
> `COleDateTime`は、DAO クラスのこの目的のために[、CTime](../../atl-mfc-shared/reference/ctime-class.md)とTIMESTAMP_STRUCTを置き換えます。 `CTime`TIMESTAMP_STRUCTは、ODBC ベースのデータ アクセス クラスに対して引き続き使用されます。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_double"></a><a name="dfx_double"></a>DFX_Double

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソースのレコードの列との間で **、倍数の浮動**データを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では **、double**型の値は指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用します。 もう 1 つの値はAFX_DAO_DISABLE_FIELD_CACHE。 この値を指定すると、MFC はこのフィールドをチェックしません。 あなたは電話して`SetFieldDirty`自分自身`SetFieldNull`を呼び出す必要があります。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

データは、DAO の型DAO_R8とレコードセットの**中の二重浮動小数点**型の間でマップされます。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_long"></a><a name="dfx_long"></a>DFX_Long

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソースのレコードの列との間で長整数データを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では **、long**型の値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用します。 もう 1 つの値はAFX_DAO_DISABLE_FIELD_CACHE。 この値を指定すると、MFC はこのフィールドをチェックしません。 あなたは電話して`SetFieldDirty`自分自身`SetFieldNull`を呼び出す必要があります。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

データは、DAO の型DAO_I4とレコードセット内の**long**型の間でマップされます。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_longbinary"></a><a name="dfx_longbinary"></a>DFX_LongBinary

**重要**この関数の代わりに[DFX_Binary](#dfx_binary)を使用することをお勧めします。

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

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では[、CLongBinary](clongbinary-class.md)型の値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*サイズを変更します。*<br/>
フレームワークは、このメモリ量を事前に割り当てます。 データが大きい場合、フレームワークは必要に応じてより多くの領域を割り当てます。 パフォーマンスを向上させるには、このサイズを再割り当てを防ぐのに十分な大きさに設定します。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DISABLE_FIELD_CACHEはダブル バッファリングを使用しません。 もう 1 つの値はAFX_DAO_ENABLE_FIELD_CACHE。 ダブル バッファリングを使用し、フィールドをダーティまたは Null にマークするために余分な作業を行う必要はありません。 パフォーマンスとメモリの理由から、バイナリ データが比較的小さい場合を除き、この値は使用しないでください。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

`DFX_LongBinary`MFC ODBC クラスとの互換性を保つために用意されています。 この`DFX_LongBinary`関数は[、CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ`CLongBinary`メンバーとデータ ソース上のレコードの列との間でクラスを使用して、バイナリ ラージ オブジェクト (BLOB) データを転送します。 データは、DAO の型DAO_BYTESとレコードセットの[CLongBinary](clongbinary-class.md)型の間でマップされます。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_short"></a><a name="dfx_short"></a>DFX_Short

[CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソースのレコードの列との間で短い整数データを転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では **、short**型の値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用します。 もう 1 つの値はAFX_DAO_DISABLE_FIELD_CACHE。 この値を指定すると、MFC はこのフィールドをチェックしません。 あなたは電話して`SetFieldDirty`自分自身`SetFieldNull`を呼び出す必要があります。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

データは、DAO の DAO_I2型とレコードセット内の**short**型の間でマップされます。

> [!NOTE]
> `DFX_Short`は、ODBC ベースのクラスの[RFX_Int](#rfx_int)と同等です。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_single"></a><a name="dfx_single"></a>DFX_Single

浮動小数点データを[、CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソースのレコードの列との間で転送します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では、float**型の**値は、指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用します。 もう 1 つの値はAFX_DAO_DISABLE_FIELD_CACHE。 この値を指定すると、MFC はこのフィールドをチェックしません。 あなたは電話して`SetFieldDirty`自分自身`SetFieldNull`を呼び出す必要があります。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

データは、DAO の型DAO_R4とレコードセットの**float**型の間でマップされます。

### <a name="example"></a>例

[DFX_Text](#dfx_text)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="dfx_text"></a><a name="dfx_text"></a>DFX_Text

`CString` [CDaoRecordset](cdaorecordset-class.md)オブジェクトのフィールド データ メンバーとデータ ソース上のレコードの列との間でデータを転送します。

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

*Pfx*<br/>
クラス[CDaoFieldExchange](cdaofieldexchange-class.md)のオブジェクトへのポインター。 このオブジェクトには、関数の呼び出しごとにコンテキストを定義するための情報が含まれています。

*Szname*<br/>
データ列の名前。

*value*<br/>
指定されたデータ メンバーに格納されている値 — 転送される値。 レコードセットからデータ ソースへの転送では[、CString](../../atl-mfc-shared/reference/cstringt-class.md)型の値は指定されたデータ メンバから取得されます。 データ ソースからレコードセットへの転送では、値は指定されたデータ メンバに格納されます。

*大きさの大きさ*<br/>
フレームワークは、このメモリ量を事前に割り当てます。 データが大きい場合、フレームワークは必要に応じてより多くの領域を割り当てます。 パフォーマンスを向上させるには、このサイズを再割り当てを防ぐのに十分な大きさに設定します。

*オプション*<br/>
変更されたレコードセット フィールドを検出するための MFC のダブル バッファリング機構を利用できるようにするオプション。 デフォルトのAFX_DAO_ENABLE_FIELD_CACHEはダブル バッファリングを使用します。 もう 1 つの値はAFX_DAO_DISABLE_FIELD_CACHE。 この値を指定すると、MFC はこのフィールドをチェックしません。 [自分で設定フィールドダーティ](cdaorecordset-class.md#setfielddirty)と[セットフィールドNullを](cdaorecordset-class.md#setfieldnull)呼び出す必要があります。

> [!NOTE]
> 既定でデータをダブル バッファに格納するかどうかを制御する場合は[、CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)を設定します。

### <a name="remarks"></a>解説

データは、DAO の型DAO_CHAR (シンボル _UNICODEが定義されている場合はDAO_WCHAR) とレコードセット内の[CString](../../atl-mfc-shared/reference/cstringt-class.md)型の間でマップされます。  n

### <a name="example"></a>例

この例では、 への`DFX_Text`いくつかの呼び出しを示します。 また、2 つの呼び出し[に注意してください](cdaofieldexchange-class.md#setfieldtype)。 最初の呼び出しとその`SetFieldType` **DFX**呼び出しを記述する必要があります。 2 番目の呼び出しと関連付けられた**DFX**呼び出しは、通常、クラスを生成したコード ウィザードによって記述されます。

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
[レコードセット::Dフィールドエクスチェンジ](crecordset-class.md#dofieldexchange)<br/>
[:Dレコードセット::Dバルクフィールドエクスチェンジ](crecordset-class.md#dobulkfieldexchange)<br/>
[コダオレコードセット::Dフィールドエクスチェンジ](cdaorecordset-class.md#dofieldexchange)
