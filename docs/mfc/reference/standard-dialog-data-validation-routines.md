---
title: 標準的なダイアログ データ検証ルーチン
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 2511e2ec6dbd4e27c0e12e35bdc1cd671bf72eaa
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213984"
---
# <a name="standard-dialog-data-validation-routines"></a>標準的なダイアログ データ検証ルーチン

このトピックでは、一般的な MFC ダイアログコントロールに使用される標準のダイアログデータ検証 (DDV) ルーチンの一覧を示します。

> [!NOTE]
> 標準的なダイアログデータ交換ルーチンは、ヘッダーファイル afxdd_ .h に定義されています。 ただし、アプリケーションには afxwin.h を含める必要があります。

### <a name="ddv-functions"></a>DDV 関数

|||
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|指定されたコントロール値の文字数が、指定された最大値を超えていないことを確認します。|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|指定されたコントロールの値が、指定された**バイト**範囲を超えていないことを検証します。|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|指定された制御値が、指定された時間範囲を超えていないことを確認します。|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|指定されたコントロールの値が、指定された範囲を超えていないことを確認 **`double`** します。|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|指定されたコントロールの値が、指定された**DWORD**の範囲を超えていないことを確認します。|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|指定されたコントロールの値が、指定された範囲を超えていないことを確認 **`float`** します。|
|[DDV_MinMaxInt](#ddv_minmaxint)|指定されたコントロールの値が、指定された範囲を超えていないことを確認 **`int`** します。|
|[DDV_MinMaxLong](#ddv_minmaxlong)|指定されたコントロールの値が、指定された範囲を超えていないことを確認 **`long`** します。|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|指定された制御値が、指定された**Longlong**範囲を超えていないことを確認します。|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|指定されたコントロールの値が、指定された日付の範囲を超えていないことを検証します。|
|[DDV_MinMaxShort](#ddv_minmaxshort)|指定されたコントロールの値が、指定された範囲を超えていないことを確認 **`short`** します。|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|指定されたスライダーコントロールの値が、指定された範囲内にあることを検証します。|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|指定された制御値が、指定された**UINT**範囲を超えていないことを検証します。|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|指定したコントロールの値が、指定した2つの値の間にあることを検証します。|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|指定されたコントロールの値が、指定された**ULONGLONG**の範囲を超えていないことを確認します。|

## <a name="ddv_maxchars"></a><a name="ddv_maxchars"></a>DDV_MaxChars

を呼び出して、 `DDV_MaxChars` *値*に関連付けられているコントロールの文字数が*nchars*を超えていないことを確認します。

```cpp
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*nChars*<br/>
許可される最大文字数。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxbyte"></a><a name="ddv_minmaxbyte"></a>DDV_MinMaxByte

を呼び出して、 `DDV_MinMaxByte` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
許容される最小値 (BYTE 型)。

*maxVal*<br/>
許容される最大値 (BYTE 型)。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxdatetime"></a><a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime

を呼び出して、 `DDV_MinMaxDateTime` *refvalue*に関連付けられた日付と時刻の選択コントロール ( [cdatetimectrl 使い方](../../mfc/reference/cdatetimectrl-class.md)) の時刻/日付の値が*refMinRange*と*refMaxRange*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。

*refValue*<br/>
ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数に関連付けられている[CTime](../../atl-mfc-shared/reference/ctime-class.md)または[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへの参照。 このオブジェクトには、検証するデータが含まれています。

*refMinRange*<br/>
使用できる日付/時刻の最小値。

*refMaxRange*<br/>
使用できる日付/時刻の最大値。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxdouble"></a><a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble

を呼び出して、 `DDV_MinMaxDouble` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
許容される最小値 (型 **`double`** )。

*maxVal*<br/>
許容される最大値 (型 **`double`** )。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxdword"></a><a name="ddv_minmaxdword"></a>DDV_MinMaxDWord

を呼び出して、 `DDV_MinMaxDWord` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
許容される最小値 (DWORD 型)。

*maxVal*<br/>
許容される最大値 (DWORD 型)。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxfloat"></a><a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat

を呼び出して、 `DDV_MinMaxFloat` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
許容される最小値 (型 **`float`** )。

*maxVal*<br/>
許容される最大値 (型 **`float`** )。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxint"></a><a name="ddv_minmaxint"></a>DDV_MinMaxInt

を呼び出して、 `DDV_MinMaxInt` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
許容される最小値 (型 **`int`** )。

*maxVal*<br/>
許容される最大値 (型 **`int`** )。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxlong"></a><a name="ddv_minmaxlong"></a>DDV_MinMaxLong

を呼び出して、 `DDV_MinMaxLong` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
許容される最小値 (型 **`long`** )。

*maxVal*<br/>
許容される最大値 (型 **`long`** )。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxlonglong"></a><a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong

を呼び出して、 `DDV_MinMaxLongLong` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
最小値 (LONGLONG 型) が許可されています。

*maxVal*<br/>
許容される最大値 (種類は LONGLONG)。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxmonth"></a><a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth

を呼び出して、 `DDV_MinMaxMonth` *refvalue*に関連付けられた month Calendar コントロール ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) の時刻と日付の値が*refMinRange*と*refMaxRange*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*refValue*<br/>
`CTime` `COleDateTime` ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数に関連付けられている型または型のオブジェクトへの参照。 このオブジェクトには、検証するデータが含まれています。 が呼び出されると、MFC はこの参照 `DDV_MinMaxMonth` を渡します。

*refMinRange*<br/>
使用できる日付/時刻の最小値。

*refMaxRange*<br/>
使用できる日付/時刻の最大値。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxshort"></a><a name="ddv_minmaxshort"></a>DDV_MinMaxShort

を呼び出して、 `DDV_MinMaxShort` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
許容される最小値 (型 **`short`** )。

*maxVal*<br/>
許容される最大値 (型 **`short`** )。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxslider"></a><a name="ddv_minmaxslider"></a>DDV_MinMaxSlider

を呼び出して、 `DDV_MinMaxSlider` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
検証する値への参照。 このパラメーターは、スライダーコントロールの現在のつまみの位置を保持または設定します。

*minVal*<br/>
許容される最小値。

*maxVal*<br/>
許容される最大値。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 スライダーコントロールの詳細については、「 [Using csliderctrl 使い方](../../mfc/using-csliderctrl.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxuint"></a><a name="ddv_minmaxuint"></a>DDV_MinMaxUInt

を呼び出して、 `DDV_MinMaxUInt` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
最小値 (UINT 型) が許可されています。

*maxVal*<br/>
許容される最大値 (UINT 型)。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxulonglong"></a><a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong

を呼び出して、 `DDV_MinMaxULongLong` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

```cpp
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
最小値 (ULONGLONG 型) が許可されます。

*maxVal*<br/>
許容される最大値 (ULONGLONG 型)。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddv_minmaxunsigned"></a>DDV_MinMaxUnsigned

を呼び出して、 `DDV_MinMaxUnsigned` *値*に関連付けられているコントロールの値が*Minval*と*maxval*の間にあることを確認します。

### <a name="syntax"></a>構文

```cpp
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

*minVal*<br/>
許容される最小値 (型 **`unsigned`** )。

*maxVal*<br/>
許容される最大値 (型 **`unsigned`** )。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログデータエクスチェンジと検証](../dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdd_

## <a name="see-also"></a>関連項目

[標準的なダイアログデータエクスチェンジルーチン](standard-dialog-data-exchange-routines.md)<br/>
[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
