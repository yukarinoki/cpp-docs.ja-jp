---
title: CDBVariant クラス
ms.date: 11/04/2016
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
ms.openlocfilehash: 9bb70acb43f2e73ade86b753ebbb7949759ce88d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754603"
---
# <a name="cdbvariant-class"></a>CDBVariant クラス

MFC ODBC クラスのバリアント型を表します。

## <a name="syntax"></a>構文

```
class CDBVariant
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を使用します。](#cdbvariant)|`CDBVariant` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDB バリアント::クリア](#clear)|オブジェクトをクリア`CDBVariant`します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[次の式を m_dwType使用します。](#m_dwtype)|現在格納されている値のデータ型を格納します。 「`DWORD`」と入力します。|

### <a name="public-union-members"></a>公的組合員

|名前|説明|
|----------|-----------------|
|[次の値をm_boolVal](#m_boolval)|BOOL 型の**BOOL**値を含みます。|
|[CDBバリアント:m_chVal](#m_chval)|**符号なし char**型の値を含みます。|
|[次の値がm_dblVal](#m_dblval)|**倍**精度浮動小数点型の値を含みます。|
|[m_fltVal](#m_fltval)|float**型の**値を含みます。|
|[CDBバリアント:m_iVal](#m_ival)|short**型の**値を含みます。|
|[次の値がm_lVal](#m_lval)|長**整数型の**値を含みます。|
|[次の値がm_pbinary](#m_pbinary)|型のオブジェクトへのポインターを格納します`CLongBinary`。|
|[次の値をm_pdate](#m_pdate)|型のオブジェクトへのポインター **TIMESTAMP_STRUCT。**|
|[M_pstring](#m_pstring)|型のオブジェクトへのポインターを格納します`CString`。|
|[M_pstringA](#m_pstringa)|ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへのポインターを格納します。|
|[次の値がm_pstringW](#m_pstringw)|幅の広い[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへのポインターを格納します。|

## <a name="remarks"></a>解説

`CDBVariant`は基本クラスを持っていません。

`CDBVariant`は[、COle のバリアント型に](../../mfc/reference/colevariant-class.md)似ています。ただし、OLE`CDBVariant`は使用されません。 `CDBVariant`では、値のデータ型を気にせずに値を格納できます。 `CDBVariant`は、現在の値のデータ型を追跡します。

CRecordset クラスは`CDBVariant`、 `GetFieldValue`、 、`GetBookmark`および 3`SetBookmark`つのメンバー関数のオブジェクトを利用します。 [CRecordset](../../mfc/reference/crecordset-class.md) たとえば、`GetFieldValue`列のデータを動的にフェッチできます。 列のデータ型は実行時に不明な場合があるため、`GetFieldValue`オブジェクトを`CDBVariant`使用して列のデータを格納します。

## <a name="inheritance-hierarchy"></a>継承階層

`CDBVariant`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="cdbvariantcdbvariant"></a><a name="cdbvariant"></a>を使用します。

NULL`CDBVariant`オブジェクトを作成します。

```
CDBVariant();
```

### <a name="remarks"></a>解説

[m_dwType](#m_dwtype)データ メンバーをDBVT_NULLに設定します。

## <a name="cdbvariantclear"></a><a name="clear"></a>CDB バリアント::クリア

オブジェクトをクリアするには、このメンバー`CDBVariant`関数を呼び出します。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

[m_dwType](#m_dwtype)データ メンバーの値がDBVT_DATE、DBVT_STRING、またはDBVT_BINARY場合、`Clear`共用体ポインター メンバーに関連付けられたメモリを解放します。 `Clear`DBVT_NULL`m_dwType`に設定されます。

デス`CDBVariant`トラクターは`Clear`を呼び出します。

## <a name="cdbvariantm_boolval"></a><a name="m_boolval"></a>次の値をm_boolVal

BOOL 型の値を格納します。

### <a name="remarks"></a>解説

データ`m_boolVal`メンバーは共用体に属しています。 にアクセスする`m_boolVal`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_BOOL`m_dwType`に設定されている場合`m_boolVal`は、有効な値が含まれます。そうしないと、アクセスすると`m_boolVal`信頼性の低い結果が生成されます。

## <a name="cdbvariantm_chval"></a><a name="m_chval"></a>CDBバリアント:m_chVal

**型が符号なし char**の値を格納します。

### <a name="remarks"></a>解説

データ`m_chVal`メンバーは共用体に属しています。 にアクセスする`m_chVal`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_UCHAR`m_dwType`に設定されている場合は、`m_chVal`有効な値が含まれます。そうしないと、アクセスすると`m_chVal`信頼性の低い結果が生成されます。

## <a name="cdbvariantm_dblval"></a><a name="m_dblval"></a>次の値がm_dblVal

**倍**精度浮動小数点型の値を格納します。

### <a name="remarks"></a>解説

データ`m_dblVal`メンバーは共用体に属しています。 にアクセスする`m_dblVal`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_DOUBLE`m_dwType`に設定されている場合`m_dblVal`は、有効な値が含まれます。そうしないと、アクセスすると`m_dblVal`信頼性の低い結果が生成されます。

## <a name="cdbvariantm_dwtype"></a><a name="m_dwtype"></a>次の式を m_dwType使用します。

このデータ メンバーには、オブジェクトの共用体データ メンバーに現在格納`CDBVariant`されている値のデータ型が含まれます。

### <a name="remarks"></a>解説

この共用体にアクセスする前に、アクセスする共用`m_dwType`体データ・メンバーを判別するために、の値を確認する必要があります。 次の表に、使用可能な値`m_dwType`と対応する共用体データ メンバーを示します。

|m_dwType|ユニオン データ メンバー|
|---------------|-----------------------|
|DBVT_NULL|アクセスに対して有効な共用体メンバーがありません。|
|DBVT_BOOL|[m_boolVal](#m_boolval)|
|DBVT_UCHAR|[m_chVal](#m_chval)|
|DBVT_SHORT|[m_iVal](#m_ival)|
|DBVT_LONG|[m_lVal](#m_lval)|
|DBVT_SINGLE|[m_fltVal](#m_fltval)|
|DBVT_DOUBLE|[m_dblVal](#m_dblval)|
|DBVT_DATE|[m_pdate](#m_pdate)|
|DBVT_STRING|[m_pstring](#m_pstring)|
|DBVT_BINARY|[m_pbinary](#m_pbinary)|
|DBVT_ASTRING|[m_pstringA](#m_pstringa)|
|DBVT_WSTRING|[m_pstringW](#m_pstringw)|

## <a name="cdbvariantm_fltval"></a><a name="m_fltval"></a>m_fltVal

**float**型の値を格納します。

### <a name="remarks"></a>解説

データ`m_fltVal`メンバーは共用体に属しています。 にアクセスする`m_fltVal`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_SINGLE`m_dwType`に設定されている場合`m_fltVal`は、有効な値が含まれます。そうしないと、アクセスすると`m_fltVal`信頼性の低い結果が生成されます。

## <a name="cdbvariantm_ival"></a><a name="m_ival"></a>CDBバリアント:m_iVal

**short**型の値を格納します。

### <a name="remarks"></a>解説

データ`m_iVal`メンバーは共用体に属しています。 にアクセスする`m_iVal`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_SHORT`m_dwType`に設定されている場合`m_iVal`は、有効な値が含まれます。そうしないと、アクセスすると`m_iVal`信頼性の低い結果が生成されます。

## <a name="cdbvariantm_lval"></a><a name="m_lval"></a>次の値がm_lVal

**long**型の値を格納します。

### <a name="remarks"></a>解説

データ`m_lVal`メンバーは共用体に属しています。 にアクセスする`m_lVal`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_LONG`m_dwType`に設定されている場合`m_lVal`は、有効な値が含まれます。そうしないと、アクセスすると`m_lVal`信頼性の低い結果が生成されます。

## <a name="cdbvariantm_pbinary"></a><a name="m_pbinary"></a>次の値がm_pbinary

型のオブジェクトへのポインターを[格納](../../mfc/reference/clongbinary-class.md)します。

### <a name="remarks"></a>解説

データ`m_pbinary`メンバーは共用体に属しています。 にアクセスする`m_pbinary`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_BINARY`m_dwType`に設定されている場合は、`m_pbinary`有効なポインターを含みます。そうしないと、アクセスすると`m_pbinary`信頼性の低い結果が生成されます。

## <a name="cdbvariantm_pdate"></a><a name="m_pdate"></a>次の値をm_pdate

TIMESTAMP_STRUCT型のオブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

データ`m_pdate`メンバーは共用体に属しています。 にアクセスする`m_pdate`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_DATE`m_dwType`に設定されている場合は、`m_pdate`有効なポインターを含みます。そうしないと、アクセスすると`m_pdate`信頼性の低い結果が生成されます。

TIMESTAMP_STRUCTデータ型の詳細については、Windows SDK の *「ODBC プログラマ リファレンス*」の「付録 D」の[「C データ型](/sql/odbc/reference/appendixes/c-data-types)」を参照してください。

## <a name="cdbvariantm_pstring"></a><a name="m_pstring"></a>M_pstring

[CString](../../atl-mfc-shared/reference/cstringt-class.md)型のオブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

データ`m_pstring`メンバーは共用体に属しています。 にアクセスする`m_pstring`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_STRING`m_dwType`に設定されている場合は、`m_pstring`有効なポインターを含みます。そうしないと、アクセスすると`m_pstring`信頼性の低い結果が生成されます。

## <a name="cdbvariantm_pstringa"></a><a name="m_pstringa"></a>M_pstringA

ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

データ`m_pstringA`メンバーは共用体に属しています。 にアクセスする`m_pstringA`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_ASTRING`m_dwType`に設定されている場合は、`m_pstringA`有効なポインターを含みます。そうしないと、アクセスすると`m_pstringA`信頼性の低い結果が生成されます。

## <a name="cdbvariantm_pstringw"></a><a name="m_pstringw"></a>次の値がm_pstringW

幅の広い[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

データ`m_pstringW`メンバーは共用体に属しています。 にアクセスする`m_pstringW`前に、まず[CDBVariant::m_dwType](#m_dwtype)の値を確認します。 DBVT_WSTRING`m_dwType`に設定されている場合は`m_pstringW`、有効なポインターを含みます。そうしないと、アクセスすると`m_pstringW`信頼性の低い結果が生成されます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)
