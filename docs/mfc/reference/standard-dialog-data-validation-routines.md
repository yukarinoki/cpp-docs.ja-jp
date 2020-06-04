---
title: 標準的なダイアログ データ検証ルーチン
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 83e3e215ec8d66321bbac5a4a308b04ef69dc68c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372899"
---
# <a name="standard-dialog-data-validation-routines"></a>標準的なダイアログ データ検証ルーチン

ここでは、MFC のコモン ダイアログ コントロールで使用される標準のダイアログ データ検証 (DDV) ルーチンを示します。

> [!NOTE]
> 標準のダイアログ データ交換ルーチンは、ヘッダー ファイル afxdd_.h で定義されます。 ただし、アプリケーションには afxwin.h を含める必要があります。

### <a name="ddv-functions"></a>DDV 関数

|||
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|指定されたコントロール値の文字数が、指定された最大値を超えていないかどうかを確認します。|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|指定されたコントロール値が、指定された**BYTE**範囲を超えていないかどうかを検証します。|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|指定されたコントロール値が指定された時間範囲を超えていないかどうかを確認します。|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|指定されたコントロール値が、指定された**倍精度**範囲を超えていないかどうかを検証します。|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|指定されたコントロール値が、指定された**DWORD**範囲を超えていないかどうかを確認します。|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|指定されたコントロール値が、指定された**浮動小数点**数の範囲を超えていないかどうかを検証します。|
|[DDV_MinMaxInt](#ddv_minmaxint)|指定されたコントロール値が、指定された**int**範囲を超えていないことを検証します。|
|[DDV_MinMaxLong](#ddv_minmaxlong)|指定されたコントロール値が、指定された**long**範囲を超えていないかどうかを検証します。|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|指定されたコントロール値が、指定された**LONGLONG**範囲を超えていないかどうかを確認します。|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|指定されたコントロール値が指定された日付範囲を超えていないかどうかを確認します。|
|[DDV_MinMaxShort](#ddv_minmaxshort)|指定されたコントロール値が、指定された**短い**範囲を超えていないかどうかを検証します。|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|指定されたスライダー コントロール値が指定された範囲内にあることを確認します。|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|指定されたコントロール値が、指定された**UINT**範囲を超えていないことを確認します。|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|指定されたコントロール値が指定された 2 つの値の間に収まれるかどうかを確認します。|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|指定されたコントロール値が、指定された**ULONG**範囲を超えていないかどうかを確認します。|

## <a name="ddv_maxchars"></a><a name="ddv_maxchars"></a>DDV_MaxChars

`DDV_MaxChars`*値*に関連付けられたコントロールの文字数が*nChars*を超えていないことを確認するために呼び出します。

```cpp
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*nChars*<br/>
最大文字数。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxbyte"></a><a name="ddv_minmaxbyte"></a>DDV_MinMaxByte

値`DDV_MinMaxByte`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
(BYTE 型の) 最小値が許可されます。

*最大値*<br/>
(BYTE 型の) 最大値が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxdatetime"></a><a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime

`DDV_MinMaxDateTime` *refValue*に関連付けられている日時指定コントロール ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) の時刻/日付値が*refMinRange*と*refMaxRange*の間にあることを確認します。

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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。

*値*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数に関連付けられた[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトまたは[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへの参照。 このオブジェクトには、検証するデータが含まれています。

*レミンレンジ*<br/>
最小日付/時刻値が許可されます。

*最大レンジ*<br/>
許可される日付/時刻の最大値。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxdouble"></a><a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble

値`DDV_MinMaxDouble`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
最小値 (**ダブル**型) が許可されます。

*最大値*<br/>
最大値 (**ダブル**型) が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxdword"></a><a name="ddv_minmaxdword"></a>DDV_MinMaxDWord

値`DDV_MinMaxDWord`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
(DWORD 型の) 最小値が許可されます。

*最大値*<br/>
(DWORD 型の) 最大値が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxfloat"></a><a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat

値`DDV_MinMaxFloat`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
最小値 **(float**型) が許可されます。

*最大値*<br/>
最大値 **(float**型) が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxint"></a><a name="ddv_minmaxint"></a>DDV_MinMaxInt

値`DDV_MinMaxInt`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
最小値 ( **int**型 ) が許可されます。

*最大値*<br/>
最大値 ( **int**型 ) が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxlong"></a><a name="ddv_minmaxlong"></a>DDV_MinMaxLong

値`DDV_MinMaxLong`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
(long 型の**long**) 最小値が許可されます。

*最大値*<br/>
最大値 **(long**型) が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxlonglong"></a><a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong

値`DDV_MinMaxLongLong`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
(LONGLONG 型の) 最小値が許可されます。

*最大値*<br/>
最大値 (LONGLONG 型) が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxmonth"></a><a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth

参照`DDV_MinMaxMonth`値に関連付けられている月の予定表コントロール ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) の時刻/日付値が*refMinRange*と*refMaxRange*の間にあることを確認します。 *refValue*

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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*値*<br/>
型`CTime`のオブジェクト、または`COleDateTime`ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数に関連付けられたオブジェクトへの参照。 このオブジェクトには、検証するデータが含まれています。 MFC は呼び出`DDV_MinMaxMonth`されたときにこの参照を渡します。

*レミンレンジ*<br/>
最小日付/時刻値が許可されます。

*最大レンジ*<br/>
許可される日付/時刻の最大値。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxshort"></a><a name="ddv_minmaxshort"></a>DDV_MinMaxShort

値`DDV_MinMaxShort`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
最小値 **(short**型) が許可されます。

*最大値*<br/>
最大値 **(short**型) が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxslider"></a><a name="ddv_minmaxslider"></a>DDV_MinMaxSlider

値`DDV_MinMaxSlider`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
検証する値への参照。 このパラメータは、スライダー コントロールの現在のつまみ位置を保持または設定します。

*ミンヴァル*<br/>
最小値が許容されます。

*最大値*<br/>
最大値が許容されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 スライダー コントロールの詳細については、「 [CSliderCtrl](../../mfc/using-csliderctrl.md)の使用 」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxuint"></a><a name="ddv_minmaxuint"></a>DDV_MinMaxUInt

値`DDV_MinMaxUInt`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
最小値 (UINT 型) が許可されます。

*最大値*<br/>
許可される最大値 (UINT 型) です。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxulonglong"></a><a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong

値`DDV_MinMaxULongLong`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

```cpp
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
(タイプ ULONG) の最小値が許可されます。

*最大値*<br/>
(タイプ ULONG) の最大値が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddv_minmaxunsigned"></a>DDV_MinMaxUnsigned

値`DDV_MinMaxUnsigned`に関連*付けられたコントロール*の値が*minVal*と*maxVal*の間にあることを確認するために呼び出します。

### <a name="syntax"></a>構文

```cpp
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*value*<br/>
データの検証に使用するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

*ミンヴァル*<br/>
最小値 (**符号なし**) が許可されます。

*最大値*<br/>
最大値 (**符号なし**のタイプ) が許可されます。

### <a name="remarks"></a>解説

DDV の詳細については、「[ダイアログ データ エクスチェンジおよび検証](../dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdd_.h

## <a name="see-also"></a>関連項目

[標準的なダイアログ データ エクスチェンジ ルーチン](standard-dialog-data-exchange-routines.md)<br/>
[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
