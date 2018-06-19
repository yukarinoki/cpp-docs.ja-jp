---
title: レコード フィールド エクス チェンジ関数 |Microsoft ドキュメント
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
ms.openlocfilehash: 564d797a30e4b2d8518c73c5f7589aae205b6907
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378970"
---
# <a name="record-field-exchange-functions"></a>レコード フィールド エクスチェンジ (RFX) 関数
このトピックの一覧、レコード フィールド エクス チェンジ (RFX、バルク RFX と DFX) 関数をレコード セット オブジェクトとそのデータ ソース間のデータ転送を自動化して、データの他の操作を実行するために使用します。  
  
 ODBC ベースのクラスを使用し、バルク行フェッチを実装している場合は、データ ソース列に対応する各データ メンバーに対してバルク RFX 関数を呼び出すことによって、 `DoBulkFieldExchange` の `CRecordset` メンバー関数を手動でオーバーライドする必要があります。  
  
 ODBC ベースのクラスにバルク行フェッチを実装していない場合または DAO ベースのクラスを使用している場合は、ClassWizard で、レコードセットの各フィールド データ メンバーに対して RFX 関数 (ODBC クラスの場合) または DFX 関数 (DAO クラスの場合) を呼び出すことで、 `DoFieldExchange` または `CRecordset` の `CDaoRecordset` メンバー関数をオーバーライドします。  
  
 レコード フィールド エクスチェンジ関数は、フレームワークが `DoFieldExchange` または `DoBulkFieldExchange`を呼び出すたびにデータを転送します。 それぞれの関数が特定のデータ型を転送します。  
  
 これらの関数の使い方の詳細については、「 [レコード フィールド エクスチェンジ: RFX のしくみ (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 動的にバインドするデータの列では、RFX 関数または DFX 関数を手動で呼び出すこともできます。詳細については、「 [レコードセット: データ列を動的に結びつける方法 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。 また、独自のカスタム RFX ルーチンまたは DFX ルーチンを記述することもできます。詳細については、テクニカル ノート [43](../../mfc/tn043-rfx-routines.md) (ODBC の場合) およびテクニカル ノート [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (DAO の場合) を参照してください。  
  
 関数に示すようとバルク RFX の例については、`DoFieldExchange`と`DoBulkFieldExchange`関数を参照してください[RFX_Text](#rfx_text)と [RFX_Text_Bulk] #rfx_text_bulk)。 DFX 関数は RFX 関数によく似ています。  
  
### <a name="rfx-functions-odbc"></a>RFX 関数 (ODBC)  
  
|||  
|-|-|  
|[RFX_Binary](#rfx_binary)|[CByteArray](cbytearray-class.md)型のバイト配列を転送します。|  
|[RFX_Bool](#rfx_bool)|ブール型のデータを転送します。|  
|[RFX_Byte](#rfx_byte)|シングル バイトのデータを転送します。|  
|[RFX_Date](#rfx_date)|[CTime](../../atl-mfc-shared/reference/ctime-class.md) または **TIMESTAMP_STRUCT**を使用して時刻と日付のデータを転送します。|  
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
|[RFX_Date_Bulk](#rfx_date_bulk)|**TIMESTAMP_STRUCT**型のデータの配列を転送します。|  
|[RFX_Double_Bulk](#rfx_double_bulk)|倍精度浮動小数点型のデータの配列を転送します。|  
|[RFX_Int_Bulk](#rfx_int_bulk)|整数型のデータの配列を転送します。|  
|[RFX_Long_Bulk](#rfx_long_bulk)|長整数型のデータの配列を転送します。|  
|[RFX_Single_Bulk](#rfx_single_bulk)|浮動小数点型のデータの配列を転送します。|  
|[RFX_Text_Bulk](#rfx_text_bulk)|**LPSTR**型のデータの配列を転送します。|  
  
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
フィールド データ メンバーの間のバイト配列を転送する`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**sql_binary 型**、 **SQL_VARBINARY**、または**sql _LONGVARBINARY**です。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Binary(  
   CFieldExchange* pFX,  
   const char* szName,  
   CByteArray& value,  
   int nMaxLength = 255);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送[CByteArray](cbytearray-class.md)、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `nMaxLength`  
 文字列または転送される配列の長さが最大です。 既定値の`nMaxLength`は 255 です。 有効な値は 1 ~`INT_MAX`します。 この領域の量は、フレームワークは、データを割り当てます。 最適なパフォーマンスを期待する最大のデータ項目に対応するのに十分な大きさの値を渡します。  
  
### <a name="remarks"></a>コメント  
 型との間にこれらの型のデータ ソース内のデータがマップされている`CByteArray`レコード セットにします。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_bool"></a>  RFX_Bool
フィールド データ メンバーの間でのブール型のデータの転送、`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**SQL_BIT**です。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Bool(  
   CFieldExchange* pFX,  
   const char* szName,  
   BOOL& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**BOOL**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_byte"></a>  RFX_Byte
1 つのフィールド データ メンバーの間のバイト数の転送、`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**SQL_TINYINT**です。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Byte(  
   CFieldExchange* pFX,  
   const char* szName,  
   BYTE& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**バイト**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_date"></a>  RFX_Date
転送`CTime`または**TIMESTAMP_STRUCT**のフィールド データ メンバーの間のデータ、`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**SQL_DATE**、 **SQL_TIME**、または**SQL_TIMESTAMP**です。  
  
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
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーであるに格納される値転送する値。 関数のさまざまなバージョンは、異なるデータ型の値を実行します。  
  
 関数の最初のバージョンへの参照を受け取り、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。 レコード セットからデータ ソースへの転送では、この値は、指定されたデータ メンバーから取得します。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 関数の 2 番目のバージョンへの参照を受け取り、 **TIMESTAMP_STRUCT**構造体。 必要がありますこの構造体を自分で設定する呼び出しの前にします。 どちらのダイアログ データ エクス (チェンジ DDX) のサポートも、コード ウィザードのサポートはこのバージョンで使用できます。 関数の 3 番目のバージョンは最初のバージョンと同様に動作への参照を受け取る点を除いて、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CTime`関数のバージョンは、いくつかの中間処理のオーバーヘッドあり、制限の範囲です。 これらの要因は限定的すぎるのいずれかの場合は、関数の 2 番目のバージョンを使用します。 コード ウィザードおよび DDX サポート構造を自分で設定する、要件のされていないことに注意してください。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_double"></a>  RFX_Double
転送**倍精度浮動小数点**のフィールド データ メンバーの間のデータ、`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**SQL_DOUBLE**です。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Double(  
   CFieldExchange* pFX,  
   const char* szName,  
   double& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**二重**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_int"></a>  RFX_Int
フィールド データ メンバーの間で整数のデータ転送、`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**SQL_SMALLINT**です。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送`int`、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_long"></a>  RFX_Long
フィールド データ メンバーの間での長整数のデータ転送、`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**SQL_INTEGER**です。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Long(  
   CFieldExchange* pFX,  
   const char* szName,  
   LONG&   
value );  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**長い**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
## <a name="rfx_longbinary"></a>  RFX_LongBinary
クラスを使用してバイナリ ラージ オブジェクト (BLOB) データを転送[CLongBinary](clongbinary-class.md)のフィールド データ メンバーの間、`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**SQL_LONGVARBINARY**または**SQL_LONGVARCHAR**です。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_LongBinary(  
   CFieldExchange* pFX,  
   const char* szName,  
   CLongBinary& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送`CLongBinary`、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_single"></a>  RFX_Single
フィールド データ メンバーの間で浮動小数点のデータ転送、`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**SQL_REAL**です。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Single(  
   CFieldExchange* pFX,  
   const char* szName,  
   float& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**float**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  

## <a name="rfx_text"></a>  RFX_Text
転送`CString`のフィールド データ メンバーの間のデータ、`CRecordset`オブジェクトと ODBC の種類のデータ ソースのレコードの列**SQL_LONGVARCHAR**、 **SQL_CHAR**、 **sql _VARCHAR**、 **SQL_DECIMAL**、または**SQL_NUMERIC**です。  
  
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
 `pFX`  
 クラスのオブジェクトへのポインター`CFieldExchange`です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送`CString`、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `nMaxLength`  
 文字列または転送される配列の長さが最大です。 既定値の`nMaxLength`は 255 です。 有効な値は 1 ~ `INT_MAX`)。 この領域の量は、フレームワークは、データを割り当てます。 最適なパフォーマンスを期待する最大のデータ項目に対応するのに十分な大きさの値を渡します。  
  
 *nColumnType*  
 主にパラメーターを使用します。 パラメーターのデータ型を示す整数。 種類は、フォームの ODBC データ型**SQL_XXX**です。  
  
 `nScale`  
 ODBC 型の値の小数点以下桁数を示す**SQL_DECIMAL**または**SQL_NUMERIC**です。 `nScale` パラメーターの値を設定するときに役立ちますのみです。 詳細についてを参照してください「の有効桁数、小数点以下桁数、長さ、および表示サイズ」の付録 D、 *ODBC SDK プログラマ リファレンス*です。  
  
### <a name="remarks"></a>コメント  
 間にこれらの型のすべてのデータ ソース内のデータがマップされている`CString`レコード セットにします。  
  
### <a name="example"></a>例  
 この例を複数回呼び出します`RFX_Text`です。 2 つの呼び出しにも注意してください`CFieldExchange::SetFieldType`です。 パラメーターへの呼び出しを記述する必要があります`SetFieldType`と RFX 呼び出しです。 出力列の呼び出しとその関連する rfx 関数呼び出しは、通常、コード ウィザードで記述されます。  
  
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
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  


## <a name="rfx_binary_bulk"></a>  RFX_Binary_Bulk
ODBC データ ソースの列からの対応する配列に複数行のバイトのデータを転送する`CRecordset`-派生オブジェクト。  
  
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
 `pFX`  
 ポインター、 [CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 `prgByteVals`  
 配列へのポインター**バイト**値。 この配列では、データ ソースからレコード セットに転送するデータを格納します。  
  
 `prgLengths`  
 長整数の配列へのポインター。 この配列が指し示す配列内の各値のバイト単位の長さに保存`prgByteVals`です。 なお、値**SQL_NULL_DATA**対応するデータ項目には、Null 値が含まれている場合に格納されます。 詳細については、ODBC API 関数を参照してください。 **SQLBindCol**で、 *ODBC SDK プログラマ リファレンス*です。  
  
 `nMaxLength`  
 許容最大長が指す配列に格納されている値の`prgByteVals`します。 データは切り捨てられませんに期待する最大のデータ項目の対応するのに十分な大きさの値を渡します。  
  
### <a name="remarks"></a>コメント  
 データ ソースの列は、ODBC 型を持つことができます**sql_binary 型**、 **SQL_VARBINARY**、または**SQL_LONGVARBINARY**です。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**バイト**です。  
  
 初期化する場合`prgByteVals`と`prgLengths`に**NULL**をポイントしている配列が行セット サイズと同じサイズで、自動的に割り当てし、します。  
  
> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトをデータ ソースからデータを転送します。 レコード セットを更新できるようにするのには、ODBC API 関数を使用する必要があります**SQLSetPos**です。  
  
 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text_Bulk](#rfx_text_bulk)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_bool_bulk"></a>  RFX_Bool_Bulk
ODBC データ ソースの列からの対応する配列に複数行のブール型のデータを転送する`CRecordset`-派生オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Bool_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   BOOL** prgBoolVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 ポインター、 [CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 `prgBoolVals`  
 配列へのポインター **BOOL**値。 この配列では、データ ソースからレコード セットに転送するデータを格納します。  
  
 `prgLengths`  
 長整数の配列へのポインター。 この配列が指し示す配列内の各値のバイト単位の長さに保存`prgBoolVals`です。 なお、値**SQL_NULL_DATA**対応するデータ項目には、Null 値が含まれている場合に格納されます。 詳細については、ODBC API 関数を参照してください。 **SQLBindCol**で、 *ODBC SDK プログラマ リファレンス*です。  
  
### <a name="remarks"></a>コメント  
 データ ソース列には、ODBC 型の必要があります**SQL_BIT**です。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**BOOL**です。  
  
 初期化する場合`prgBoolVals`と`prgLengths`に**NULL**をポイントしている配列が行セット サイズと同じサイズで、自動的に割り当てし、します。  
  
> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトをデータ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります**SQLSetPos**です。  
  
 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text_Bulk](#rfx_text_bulk)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_byte_bulk"></a>  RFX_Byte_Bulk
ODBC データ ソースの列からの対応する配列に単一バイトの複数の行を転送する`CRecordset`-派生オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Byte_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   BYTE** prgByteVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 ポインター、 [CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 `prgByteVals`  
 配列へのポインター**バイト**値。 この配列では、データ ソースからレコード セットに転送するデータを格納します。  
  
 `prgLengths`  
 長整数の配列へのポインター。 この配列が指し示す配列内の各値のバイト単位の長さに保存`prgByteVals`です。 なお、値**SQL_NULL_DATA**対応するデータ項目には、Null 値が含まれている場合に格納されます。 詳細については、ODBC API 関数を参照してください。 **SQLBindCol**で、 *ODBC SDK プログラマ リファレンス*です。  
  
### <a name="remarks"></a>コメント  
 データ ソース列には、ODBC 型の必要があります**SQL_TINYINT**です。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**バイト**です。  
  
 初期化する場合`prgByteVals`と`prgLengths`に**NULL**をポイントしている配列が行セット サイズと同じサイズで、自動的に割り当てし、します。  
  
> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトをデータ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります**SQLSetPos**です。  
  
 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text_Bulk](#rfx_text_bulk)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
## <a name="rfx_date_bulk"></a>  RFX_Date_Bulk
複数行の転送**TIMESTAMP_STRUCT** ODBC データ ソースの列のデータに対応する配列に、 `CRecordset`-派生オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Date_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   TIMESTAMP_STRUCT** prgTSVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 ポインター、 [CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 `prgTSVals`  
 配列へのポインター **TIMESTAMP_STRUCT**値。 この配列では、データ ソースからレコード セットに転送するデータを格納します。 詳細については、 **TIMESTAMP_STRUCT**データ型を参照してください「C データ型」の付録 D、 *ODBC SDK プログラマ リファレンス*です。  
  
 `prgLengths`  
 長整数の配列へのポインター。 この配列が指し示す配列内の各値のバイト単位の長さに保存`prgTSVals`です。 なお、値**SQL_NULL_DATA**対応するデータ項目には、Null 値が含まれている場合に格納されます。 詳細については、ODBC API 関数を参照してください。 **SQLBindCol**で、 *ODBC SDK プログラマ リファレンス*です。  
  
### <a name="remarks"></a>コメント  
 データ ソースの列は、ODBC 型を持つことができます**SQL_DATE**、 **SQL_TIME**、または**SQL_TIMESTAMP**です。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**TIMESTAMP_STRUCT**です。  
  
 初期化する場合`prgTSVals`と`prgLengths`に**NULL**をポイントしている配列が行セット サイズと同じサイズで、自動的に割り当てし、します。  
  
> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトをデータ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります**SQLSetPos**です。  
  
 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text_Bulk](#rfx_text_bulk)です。  
  
### <a name="requirements"></a>要件  
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
 `pFX`  
 ポインター、 [CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 `prgDblVals`  
 配列へのポインター**二重**値。 この配列では、データ ソースからレコード セットに転送するデータを格納します。  
  
 `prgLengths`  
 長整数の配列へのポインター。 この配列が指し示す配列内の各値のバイト単位の長さに保存`prgDblVals`です。 なお、値**SQL_NULL_DATA**対応するデータ項目には、Null 値が含まれている場合に格納されます。 詳細については、ODBC API 関数を参照してください。 **SQLBindCol**で、 *ODBC SDK プログラマ リファレンス*です。  
  
### <a name="remarks"></a>コメント  
 データ ソース列には、ODBC 型の必要があります**SQL_DOUBLE**です。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**二重**です。  
  
 初期化する場合`prgDblVals`と`prgLengths`に**NULL**をポイントしている配列が行セット サイズと同じサイズで、自動的に割り当てし、します。  
  
> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトをデータ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります**SQLSetPos**です。  
  
 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text_Bulk](#rfx_text_bulk)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_int_bulk"></a>  RFX_Int_Bulk
フィールド データ メンバーの間で整数のデータ転送、`CRecordset`オブジェクトおよび ODBC の種類のデータ ソースのレコードの列**SQL_SMALLINT**です。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CFieldExchange](cfieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 操作の詳細については、 `CFieldExchange` 、記事を参照して、オブジェクトを指定できます[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送`int`、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text](#rfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="rfx_long_bulk"></a>  RFX_Long_Bulk
ODBC データ ソースの列からの対応する配列に複数行の長整数のデータを転送する`CRecordset`-派生オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```
void RFX_Long_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   long** prgLongVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 ポインター、 [CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 `prgLongVals`  
 長整数の配列へのポインター。 この配列では、データ ソースからレコード セットに転送するデータを格納します。  
  
 `prgLengths`  
 長整数の配列へのポインター。 この配列が指し示す配列内の各値のバイト単位の長さに保存`prgLongVals`です。 なお、値**SQL_NULL_DATA**対応するデータ項目には、Null 値が含まれている場合に格納されます。 詳細については、ODBC API 関数を参照してください。 **SQLBindCol**で、 *ODBC SDK プログラマ リファレンス*です。  
  
### <a name="remarks"></a>コメント  
 データ ソース列には、ODBC 型の必要があります**SQL_INTEGER**です。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**長い**です。  
  
 初期化する場合`prgLongVals`と`prgLengths`に**NULL**をポイントしている配列が行セット サイズと同じサイズで、自動的に割り当てし、します。  
  
> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトをデータ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります**SQLSetPos**です。  
  
 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text_Bulk](#rfx_text_bulk)です。  
  
### <a name="requirements"></a>要件  
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
 `pFX`  
 ポインター、 [CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 `prgFltVals`  
 配列へのポインター **float**値。 この配列では、データ ソースからレコード セットに転送するデータを格納します。  
  
 `prgLengths`  
 長整数の配列へのポインター。 この配列が指し示す配列内の各値のバイト単位の長さに保存`prgFltVals`です。 なお、値**SQL_NULL_DATA**対応するデータ項目には、Null 値が含まれている場合に格納されます。 詳細については、ODBC API 関数を参照してください。 **SQLBindCol**で、 *ODBC SDK プログラマ リファレンス*です。  
  
### <a name="remarks"></a>コメント  
 データ ソース列には、ODBC 型の必要があります**SQL_REAL**です。 レコード セットへのポインター型のフィールド データ メンバーを定義する必要があります**float**です。  
  
 初期化する場合`prgFltVals`と`prgLengths`に**NULL**をポイントしている配列が行セット サイズと同じサイズで、自動的に割り当てし、します。  
  
> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトをデータ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります**SQLSetPos**です。  
  
 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
### <a name="example"></a>例  
 参照してください[RFX_Text_Bulk](#rfx_text_bulk)です。  
  
### <a name="requirements"></a>要件  
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
 `pFX`  
 ポインター、 [CFieldExchange](cfieldexchange-class.md)オブジェクト。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。  
  
 `szName`  
 データ列の名前。  
  
 `prgStrVals`  
 配列へのポインター **LPSTR**値。 この配列では、データ ソースからレコード セットに転送するデータを格納します。 ODBC の現在のバージョンとなお、これらの値が Unicode にすることはできません。  
  
 `prgLengths`  
 長整数の配列へのポインター。 この配列が指し示す配列内の各値のバイト単位の長さに保存`prgStrVals`です。 この長さは、null 終端文字を除外します。 なお、値**SQL_NULL_DATA**対応するデータ項目には、Null 値が含まれている場合に格納されます。 詳細については、ODBC API 関数を参照してください。 **SQLBindCol**で、 *ODBC SDK プログラマ リファレンス*です。  
  
 `nMaxLength`  
 許容最大長が指す配列に格納されている値の`prgStrVals`終端の null 文字を含むです。 データは切り捨てられませんに期待する最大のデータ項目の対応するのに十分な大きさの値を渡します。  
  
### <a name="remarks"></a>コメント  
 データ ソースの列は、ODBC 型を持つことができます**SQL_LONGVARCHAR**、 **SQL_CHAR**、 **SQL_VARCHAR**、 **SQL_DECIMAL**、または**SQL_NUMERIC**です。 レコード セットは、型のフィールド データ メンバーを定義する必要があります**LPSTR**です。  
  
 初期化する場合`prgStrVals`と`prgLengths`に**NULL**をポイントしている配列が行セット サイズと同じサイズで、自動的に割り当てし、します。  
  
> [!NOTE]
>  バルク レコード フィールド エクス チェンジはのみ、レコード セット オブジェクトをデータ ソースからデータを転送します。 レコード セットを更新するためには、ODBC API 関数を使用する必要があります**SQLSetPos**です。  
  
 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)と[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
### <a name="example"></a>例  
 呼び出しを手動で記述する必要があります、`DoBulkFieldExchange`をオーバーライドします。 この例への呼び出しを示しています。 `RFX_Text_Bulk`、への呼び出しだけでなく`RFX_Long_Bulk`、データの転送します。 呼び出しによってこれらの呼び出しの前に、[つ](CFieldExchange::SetFieldType.md)です。 パラメーターに対してバルク RFX 関数ではなく RFX 関数を呼び出す必要がありますに注意してください。  
  
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
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

## <a name="dfx_binary"></a>  DFX_Binary
フィールド データ メンバーの間のバイト配列を転送する[CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。  
  
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
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送[CByteArray](cbytearray-class.md)、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `nPreAllocSize`  
 フレームワークでは、このメモリの量があらかじめ確保します。 データが大きい場合は、フレームワークは必要に応じて容量を割り当てられているされます。 パフォーマンス向上のためには、このサイズを再割り当てを防ぐために、十分大きな値に設定します。 既定のサイズは、AFXDAO で定義されます。H ファイルとして**AFX_DAO_BINARY_DEFAULT_SIZE**です。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、`AFX_DAO_DISABLE_FIELD_CACHE`いない使用ダブル バッファリングは、呼び出す必要があります[き](cdaorecordset-class.md#setfielddirty)と[な](cdaorecordset-class.md#setfieldnull)自分でします。 その他の考えられる値`AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用して、追加の作業フィールドをマークするいなくてもかまいませんダーティまたは Null。 パフォーマンスとメモリ上の理由から、バイナリ データが比較的少ない場合を除き、この値を回避します。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定ですべてのフィールドのバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間のデータのマップ**DAO_BYTES** DAO」と入力[CByteArray](cbytearray-class.md)レコード セットにします。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  

## <a name="dfx_bool"></a>  DFX_Bool
フィールド データ メンバーの間でのブール型のデータの転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。  
  
### <a name="syntax"></a>構文  
  
```
void AFXAPI DFX_Bool(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   BOOL& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**BOOL**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 `AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用します。 その他の考えられる値は`AFX_DAO_DISABLE_FIELD_CACHE`します。 この値を指定する場合は、MFC は行われませんこのフィールドを確認しています。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間のデータのマップ**DAO_BOOL** DAO」と入力**BOOL**レコード セットにします。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  

## <a name="dfx_byte"></a>  DFX_Byte
1 つのフィールド データ メンバーの間のバイト数の転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。  
  
### <a name="syntax"></a>構文  
  
```
void AFXAPI DFX_Byte(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   BYTE& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**バイト**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 `AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用します。 その他の考えられる値は`AFX_DAO_DISABLE_FIELD_CACHE`します。 この値を指定する場合は、MFC は行われませんこのフィールドを確認しています。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間のデータのマップ**DAO_BYTES** DAO」と入力**バイト**レコード セットにします。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  

## <a name="dfx_currency"></a>  DFX_Currency
フィールド データ メンバーの間で通貨のデータ転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。  
  
### <a name="syntax"></a>構文  
  
```
void AFXAPI DFX_Currency(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   COleCurrency& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースへの転送では、この値は型の指定されたデータ メンバーから取得[COleCurrency](colecurrency-class.md)です。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 `AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用します。 その他の考えられる値は`AFX_DAO_DISABLE_FIELD_CACHE`します。 この値を指定する場合は、MFC は行われませんこのフィールドを確認しています。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間のデータのマップ**DAO_CURRENCY** DAO」と入力[COleCurrency](colecurrency-class.md)レコード セットにします。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  

## <a name="dfx_datetime"></a>  DFX_DateTime
フィールド データ メンバーの間で日付と時刻のデータ転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。  
  
### <a name="syntax"></a>構文  
  
```
void AFXAPI DFX_DateTime(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   COleDateTime& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 関数が受け取るへの参照、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。 レコード セットからデータ ソースへの転送では、この値は、指定されたデータ メンバーから取得します。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 `AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用します。 その他の考えられる値は`AFX_DAO_DISABLE_FIELD_CACHE`します。 この値を指定する場合は、MFC は行われませんこのフィールドを確認しています。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間のデータのマップ**DAO_DATE** DAO」と入力[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)レコード セットにします。  
  
> [!NOTE]
>  `COleDateTime` 置換[CTime](../../atl-mfc-shared/reference/ctime-class.md)と**TIMESTAMP_STRUCT** DAO クラスでは、この目的のためです。 `CTime` および**TIMESTAMP_STRUCT**されて ODBC ベースのデータ アクセス クラスを使用します。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  

## <a name="dfx_double"></a>  DFX_Double
転送**倍精度浮動小数点**のフィールド データ メンバーの間のデータ、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。  
  
### <a name="syntax"></a>構文  
  
```
void AFXAPI DFX_Double(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   double& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**二重**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 `AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用します。 その他の考えられる値は`AFX_DAO_DISABLE_FIELD_CACHE`します。 この値を指定する場合は、MFC は行われませんこのフィールドを確認しています。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間のデータのマップ**DAO_R8** DAO」と入力**倍精度浮動小数点**レコード セットにします。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  

## <a name="dfx_long"></a>  DFX_Long
フィールド データ メンバーの間での長整数のデータ転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。  
  
### <a name="syntax"></a>構文  
  
```
void AFXAPI DFX_Long(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   long& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**長い**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 `AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用します。 その他の考えられる値は`AFX_DAO_DISABLE_FIELD_CACHE`します。 この値を指定する場合は、MFC は行われませんこのフィールドを確認しています。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間でデータがマップされている**DAO_I4** DAO」と入力**長い**レコード セットにします。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
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
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送[CLongBinary](clongbinary-class.md)、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 *dwPreAllocSize*  
 フレームワークでは、このメモリの量があらかじめ確保します。 データが大きい場合は、フレームワークは必要に応じて容量を割り当てられているされます。 パフォーマンス向上のためには、このサイズを再割り当てを防ぐために、十分大きな値に設定します。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 **AFX_DISABLE_FIELD_CACHE**、ダブル バッファリングを使用しません。 その他の考えられる値は`AFX_DAO_ENABLE_FIELD_CACHE`します。 ダブル バッファリングを使用して、追加の作業フィールドをマークするいなくてもかまいませんダーティまたは Null。 パフォーマンスとメモリ上の理由から、バイナリ データが比較的少ない場合を除き、この値を回避します。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 `DFX_LongBinary` MFC ODBC クラスとの互換性を指定できます。 `DFX_LongBinary`関数がクラスを使用してバイナリ ラージ オブジェクト (BLOB) データを転送`CLongBinary`のフィールド データ メンバーの間、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。 型の間のデータのマップ**DAO_BYTES** DAO」と入力[CLongBinary](clongbinary-class.md)レコード セットにします。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  

## <a name="dfx_short"></a>  DFX_Short
転送の短い、フィールド データ メンバーの間で整数データ、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。  
  
### <a name="syntax"></a>構文  
  
```
void AFXAPI DFX_Short(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   short& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**短い**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 `AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用します。 その他の考えられる値は`AFX_DAO_DISABLE_FIELD_CACHE`します。 この値を指定する場合は、MFC は行われませんこのフィールドを確認しています。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間のデータのマップ**DAO_I2** DAO」と入力**短い**レコード セットにします。  
  
> [!NOTE]
>  `DFX_Short` 等価[RFX_Int](#rfx_int) ODBC ベースのクラスにします。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  

## <a name="dfx_single"></a>  DFX_Single
フィールド データ メンバーの間で浮動小数点のデータ転送、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトおよびデータ ソースのレコードの列です。  
  
### <a name="syntax"></a>構文  
  
```
void AFXAPI DFX_Single(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   float& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送**float**、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 `AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用します。 その他の考えられる値は`AFX_DAO_DISABLE_FIELD_CACHE`します。 この値を指定する場合は、MFC は行われませんこのフィールドを確認しています。 呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間でデータがマップされている**DAO_R4** DAO」と入力**float**レコード セットにします。  
  
### <a name="example"></a>例  
 参照してください[DFX_Text](#dfx_text)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  

## <a name="dfx_text"></a>  DFX_Text
転送`CString`のフィールド データ メンバーの間のデータ、 [CDaoRecordset](cdaorecordset-class.md)オブジェクトとデータ ソースのレコードの列です。  
  
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
 `pFX`  
 クラスのオブジェクトへのポインター [CDaoFieldExchange](cdaofieldexchange-class.md)です。 このオブジェクトには、関数の各呼び出しのコンテキストを定義する情報が含まれています。  
  
 `szName`  
 データ列の名前。  
  
 *値*  
 指定されたデータ メンバーに格納される値: 転送する値。 レコード セットからデータ ソースの種類の値への転送[CString](../../atl-mfc-shared/reference/cstringt-class.md)、指定したデータ メンバーから取得されます。 データ ソースからレコード セットへの転送では、値は、指定したデータ メンバーに格納されます。  
  
 `nPreAllocSize`  
 フレームワークでは、このメモリの量があらかじめ確保します。 データが大きい場合は、フレームワークは必要に応じて容量を割り当てられているされます。 パフォーマンス向上のためには、このサイズを再割り当てを防ぐために、十分大きな値に設定します。  
  
 `dwBindOptions`  
 変更されたレコード セットのフィールドを検出するため、MFC のダブル バッファリングの機構を利用できるオプションです。 既定値、 `AFX_DAO_ENABLE_FIELD_CACHE`、ダブル バッファリングを使用します。 その他の考えられる値は`AFX_DAO_DISABLE_FIELD_CACHE`します。 この値を指定する場合は、MFC は行われませんこのフィールドを確認しています。 呼び出す必要があります[き](cdaorecordset-class.md#setfielddirty)と[な](cdaorecordset-class.md#setfieldnull)自分でします。  
  
> [!NOTE]
>  かどうかのデータは double を設定して、既定でバッファリングを制御する[CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)です。  
  
### <a name="remarks"></a>コメント  
 型の間のデータのマップ**DAO_CHAR** DAO での (またはの場合、シンボル **_UNICODE**が定義されている**DAO_WCHAR**) と型[CString](../../atl-mfc-shared/reference/cstringt-class.md)で、レコード セットです。  n
  
### <a name="example"></a>例  
 この例を複数回呼び出します`DFX_Text`です。 2 つの呼び出しにも注意してください[CDaoFieldExchange::SetFieldType](cdaofieldexchange-class.md#setfieldtype)です。 最初の呼び出しを記述する必要があります`SetFieldType`とその**DFX**呼び出します。 2 番目の呼び出しとそれに関連する**DFX**呼び出しは通常、クラスを生成するコード ウィザードによって書き込まれます。  
  
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
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [CRecordset::DoFieldExchange](crecordset-class.md#dofieldexchange)   
 [CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)   
 [CDaoRecordset::DoFieldExchange](cdaorecordset-class.md#dofieldexchange)

