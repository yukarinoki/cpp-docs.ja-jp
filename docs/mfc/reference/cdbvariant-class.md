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
ms.openlocfilehash: 45a478a5ca6cfb4d9b976a29eae2ae7d98fdd6ee
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223084"
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
|[CDBVariant:: CDBVariant](#cdbvariant)|`CDBVariant` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDBVariant:: Clear](#clear)|オブジェクトをクリア `CDBVariant` します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CDBVariant:: m_dwType](#m_dwtype)|現在格納されている値のデータ型を格納します。 「`DWORD`」と入力します。|

### <a name="public-union-members"></a>パブリック共用体のメンバー

|名前|説明|
|----------|-----------------|
|[CDBVariant:: m_boolVal](#m_boolval)|**BOOL**型の値が含まれています。|
|[CDBVariant:: m_chVal](#m_chval)|型の値を格納 **`unsigned char`** します。|
|[CDBVariant:: m_dblVal](#m_dblval)|型の値を格納 **`double`** します。|
|[CDBVariant:: m_fltVal](#m_fltval)|型の値を格納 **`float`** します。|
|[CDBVariant:: m_iVal](#m_ival)|型の値を格納 **`short`** します。|
|[CDBVariant:: m_lVal](#m_lval)|型の値を格納 **`long`** します。|
|[CDBVariant:: m_pbinary](#m_pbinary)|型のオブジェクトへのポインターを格納 `CLongBinary` します。|
|[CDBVariant:: m_pdate](#m_pdate)|**TIMESTAMP_STRUCT**型のオブジェクトへのポインターを格納します。|
|[CDBVariant:: m_pstring](#m_pstring)|型のオブジェクトへのポインターを格納 `CString` します。|
|[CDBVariant:: m_pstringA](#m_pstringa)|ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへのポインターを格納します。|
|[CDBVariant:: m_pstringW](#m_pstringw)|ワイド[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへのポインターを格納します。|

## <a name="remarks"></a>解説

`CDBVariant`に基底クラスがありません。

`CDBVariant`は[COleVariant](../../mfc/reference/colevariant-class.md)に似ています。ただし、で `CDBVariant` は OLE が使用されません。 `CDBVariant`値のデータ型を気にせずに値を格納できます。 `CDBVariant`共用体に格納されている現在の値のデータ型を追跡します。

クラス[CRecordset](../../mfc/reference/crecordset-class.md)は `CDBVariant` 、、、およびの3つのメンバー関数内のオブジェクトを利用 `GetFieldValue` `GetBookmark` `SetBookmark` します。 たとえば、では、 `GetFieldValue` 列のデータを動的にフェッチできます。 列のデータ型は実行時に認識されない場合があるため、は `GetFieldValue` オブジェクトを使用し `CDBVariant` て列のデータを格納します。

## <a name="inheritance-hierarchy"></a>継承階層

`CDBVariant`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="cdbvariantcdbvariant"></a><a name="cdbvariant"></a>CDBVariant:: CDBVariant

NULL オブジェクトを作成し `CDBVariant` ます。

```
CDBVariant();
```

### <a name="remarks"></a>解説

[M_dwType](#m_dwtype)データメンバーを DBVT_NULL に設定します。

## <a name="cdbvariantclear"></a><a name="clear"></a>CDBVariant:: Clear

オブジェクトをクリアするには、このメンバー関数を呼び出し `CDBVariant` ます。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

[M_dwType](#m_dwtype)データメンバーの値が DBVT_DATE、DBVT_STRING、または DBVT_BINARY の場合、は `Clear` 共用体ポインターメンバーに関連付けられているメモリを解放します。 `Clear``m_dwType`を DBVT_NULL に設定します。

`CDBVariant`デストラクターは `Clear` を呼び出します。

## <a name="cdbvariantm_boolval"></a><a name="m_boolval"></a>CDBVariant:: m_boolVal

BOOL 型の値を格納します。

### <a name="remarks"></a>解説

`m_boolVal`データメンバーが共用体に属しています。 にアクセスする前に `m_boolVal` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 が DBVT_BOOL に設定されている場合 `m_dwType` 、に `m_boolVal` は有効な値が含まれます。それ以外の場合は、にアクセスする `m_boolVal` と、信頼性の低い結果が生成されます。

## <a name="cdbvariantm_chval"></a><a name="m_chval"></a>CDBVariant:: m_chVal

型の値を格納 **`unsigned char`** します。

### <a name="remarks"></a>解説

`m_chVal`データメンバーが共用体に属しています。 にアクセスする前に `m_chVal` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_UCHAR に設定されている場合、には `m_chVal` 有効な値が含まれます。それ以外の場合、にアクセスする `m_chVal` と、信頼性の低い結果が生成されます。

## <a name="cdbvariantm_dblval"></a><a name="m_dblval"></a>CDBVariant:: m_dblVal

型の値を格納 **`double`** します。

### <a name="remarks"></a>解説

`m_dblVal`データメンバーが共用体に属しています。 にアクセスする前に `m_dblVal` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_DOUBLE に設定されている場合、には `m_dblVal` 有効な値が含まれます。それ以外の場合、にアクセスする `m_dblVal` と、信頼性の低い結果が生成されます。

## <a name="cdbvariantm_dwtype"></a><a name="m_dwtype"></a>CDBVariant:: m_dwType

このデータメンバーには、 `CDBVariant` オブジェクトの共用体データメンバーに現在格納されている値のデータ型が含まれています。

### <a name="remarks"></a>解説

この共用体にアクセスする前に、の値を確認して、 `m_dwType` どの共用体データメンバーにアクセスするかを判断する必要があります。 次の表に、 `m_dwType` および対応する共用体データメンバーに使用できる値を示します。

|m_dwType|共用体データメンバー|
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

## <a name="cdbvariantm_fltval"></a><a name="m_fltval"></a>CDBVariant:: m_fltVal

型の値を格納 **`float`** します。

### <a name="remarks"></a>解説

`m_fltVal`データメンバーが共用体に属しています。 にアクセスする前に `m_fltVal` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_SINGLE に設定されている場合、には `m_fltVal` 有効な値が含まれます。それ以外の場合、にアクセスする `m_fltVal` と、信頼性の低い結果が生成されます。

## <a name="cdbvariantm_ival"></a><a name="m_ival"></a>CDBVariant:: m_iVal

型の値を格納 **`short`** します。

### <a name="remarks"></a>解説

`m_iVal`データメンバーが共用体に属しています。 にアクセスする前に `m_iVal` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_SHORT に設定されている場合、には `m_iVal` 有効な値が含まれます。それ以外の場合、にアクセスする `m_iVal` と、信頼性の低い結果が生成されます。

## <a name="cdbvariantm_lval"></a><a name="m_lval"></a>CDBVariant:: m_lVal

型の値を格納 **`long`** します。

### <a name="remarks"></a>解説

`m_lVal`データメンバーが共用体に属しています。 にアクセスする前に `m_lVal` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_LONG に設定されている場合、には `m_lVal` 有効な値が含まれます。それ以外の場合、にアクセスする `m_lVal` と、信頼性の低い結果が生成されます。

## <a name="cdbvariantm_pbinary"></a><a name="m_pbinary"></a>CDBVariant:: m_pbinary

[CLongBinary](../../mfc/reference/clongbinary-class.md)型のオブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

`m_pbinary`データメンバーが共用体に属しています。 にアクセスする前に `m_pbinary` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_BINARY に設定されている場合、には `m_pbinary` 有効なポインターが含まれます。それ以外の場合、にアクセスする `m_pbinary` と、信頼性の低い結果が生成されます。

## <a name="cdbvariantm_pdate"></a><a name="m_pdate"></a>CDBVariant:: m_pdate

TIMESTAMP_STRUCT 型のオブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

`m_pdate`データメンバーが共用体に属しています。 にアクセスする前に `m_pdate` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_DATE に設定されている場合、には `m_pdate` 有効なポインターが含まれます。それ以外の場合、にアクセスする `m_pdate` と、信頼性の低い結果が生成されます。

TIMESTAMP_STRUCT データ型の詳細については、「」 Windows SDK の「 [C データ型](/sql/odbc/reference/appendixes/c-data-types)」を*参照し*てください。

## <a name="cdbvariantm_pstring"></a><a name="m_pstring"></a>CDBVariant:: m_pstring

[CString](../../atl-mfc-shared/reference/cstringt-class.md)型のオブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

`m_pstring`データメンバーが共用体に属しています。 にアクセスする前に `m_pstring` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_STRING に設定されている場合、には `m_pstring` 有効なポインターが含まれます。それ以外の場合、にアクセスする `m_pstring` と、信頼性の低い結果が生成されます。

## <a name="cdbvariantm_pstringa"></a><a name="m_pstringa"></a>CDBVariant:: m_pstringA

ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

`m_pstringA`データメンバーが共用体に属しています。 にアクセスする前に `m_pstringA` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_ASTRING に設定されている場合、には `m_pstringA` 有効なポインターが含まれます。それ以外の場合、にアクセスする `m_pstringA` と、信頼性の低い結果が生成されます。

## <a name="cdbvariantm_pstringw"></a><a name="m_pstringw"></a>CDBVariant:: m_pstringW

ワイド[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

`m_pstringW`データメンバーが共用体に属しています。 にアクセスする前に `m_pstringW` 、まず[CDBVariant:: m_dwType](#m_dwtype)の値を確認してください。 `m_dwType`が DBVT_WSTRING に設定されている場合、には `m_pstringW` 有効なポインターが含まれます。それ以外の場合、にアクセスする `m_pstringW` と、信頼性の低い結果が生成されます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)
