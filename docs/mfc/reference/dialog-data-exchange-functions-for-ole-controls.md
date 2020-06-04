---
title: OLE コントロールのダイアログ データ エクスチェンジ (DDX) 関数
ms.date: 11/04/2016
f1_keywords:
- AFXDISP/DDX_OCBool
- AFXDISP/DDX_OCBoolRO
- AFXDISP/DDX_OCColor
- AFXDISP/DDX_OCColorRO
- AFXDISP/DDX_OCFloat
- AFXDISP/DDX_OCFloatRO
- AFXDISP/DDX_OCInt
- AFXDISP/DDX_OCIntRO
- AFXDISP/DDX_OCShort
- AFXDISP/DDX_OCShortRO
- AFXDISP/DDX_OCText
- AFXDISP/DDX_OCTextRO
helpviewer_keywords:
- OLE controls [MFC], DDX functions
- DDX (dialog data exchange), OLE support
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
ms.openlocfilehash: 61a5983eec13902ed4b0e397e3befca4860977d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365760"
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE コントロールのダイアログ データ エクスチェンジ (DDX) 関数

ここでは、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールのプロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバとの間でデータを交換するために使用するDDX_OC関数を示します。

### <a name="ddx_oc-functions"></a>DDX_OC関数

|||
|-|-|
|[DDX_OCBool](#ddx_ocbool)|OLE コントロールのプロパティと**BOOL**データ メンバー間での**BOOL**データの転送を管理します。|
|[DDX_OCBoolRO](#ddx_ocboolro)|OLE コントロールの読み取り専用プロパティと**BOOL**データ メンバー間の**BOOL**データの転送を管理します。|
|[DDX_OCColor](#ddx_occolor)|OLE コントロールのプロパティと**OLE_COLOR**データ メンバー間の**OLE_COLOR**データの転送を管理します。|
|[DDX_OCColorRO](#ddx_occolorro)|OLE コントロールの読み取り専用プロパティと**OLE_COLOR**データ メンバー間の**OLE_COLOR**データの転送を管理します。|
|[DDX_OCFloat](#ddx_ocfloat)|OLE コントロールのプロパティと**フロート**(**または倍精度**浮動小数点) データ メンバー間の**フロート**(または**倍**精度浮動小数点数) のデータ転送を管理します。|
|[DDX_OCFloatRO](#ddx_ocfloatro)|OLE コントロールの読み取り専用プロパティと**フロート**(または**倍精度**浮動小数点数) のデータ メンバとの間で**のフロート**(または**倍**精度浮動小数点数) のデータ転送を管理します。|
|[DDX_OCInt](#ddx_ocint)|OLE コントロールのプロパティと**int** (**または long)** データ メンバとの間**での int** (または**long)** データの転送を管理します。|
|[DDX_OCIntRO](#ddx_ocintro)|OLE コントロールの読み取り専用プロパティと**int** (または**long)** データ メンバとの間**での int** (または**long)** データの転送を管理します。|
|[DDX_OCShort](#ddx_ocshort)|OLE コントロールのプロパティと**短い**データ メンバ間の**短い**データの転送を管理します。|
|[DDX_OCShortRO](#ddx_ocshortro)|OLE コントロールの読み取り専用プロパティと**短い**データ メンバー間の**短い**データの転送を管理します。|
|[DDX_OCText](#ddx_octext)|OLE コントロールのプロパティと**CString**データ メンバー間の**CString**データの転送を管理します。|
|[DDX_OCTextRO](#ddx_octextro)|OLE コントロールの読み取り専用プロパティと**CString**データ メンバー間の**CString**データの転送を管理します。|

## <a name="ddx_ocbool"></a><a name="ddx_ocbool"></a>DDX_OCBool

この`DDX_OCBool`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールのプロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの BOOL データ メンバ間で**の BOOL**データの転送を管理します。 **BOOL**

```cpp
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー :** afxdisp.h

## <a name="ddx_ocboolro"></a><a name="ddx_ocboolro"></a>DDX_OCBoolRO

この`DDX_OCBoolRO`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの BOOL データ メンバとの間で**の BOOL**データの転送を管理します。 **BOOL**

```cpp
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_occolor"></a><a name="ddx_occolor"></a>DDX_OCColor

この`DDX_OCColor`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールのプロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのOLE_COLORデータ メンバ間でのOLE_COLORデータ転送を管理します。

```cpp
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_occolorro"></a><a name="ddx_occolorro"></a>DDX_OCColorRO

この`DDX_OCColorRO`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのOLE_COLORデータ メンバとの間でのOLE_COLORデータの転送を管理します。

```cpp
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocfloat"></a><a name="ddx_ocfloat"></a>DDX_OCFloat

この`DDX_OCFloat`関数は、OLE コントロールのプロパティとダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**フロー****ト**(または**倍**精度浮動小数点数) の**double**データ転送を管理します。

```cpp
void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    float& value);

void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    double& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocfloatro"></a><a name="ddx_ocfloatro"></a>DDX_OCFloatRO

この`DDX_OCFloatRO`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**フロート**(または**倍精度**浮動小数点) データ メンバ間での**フロート**(または**倍**精度浮動小数点) データの転送を管理します。

```cpp
void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    float& value);

void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    double& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocint"></a><a name="ddx_ocint"></a>DDX_OCInt

この`DDX_OCInt`関数は、OLE コントロールのプロパティとダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**int** (または**int****long)** データの転送を**long**管理します。

```cpp
void AFXAPI DDX_OCInt(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    int& value);

void AFXAPI DDX_OCInt(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    long& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocintro"></a><a name="ddx_ocintro"></a>DDX_OCIntRO

この`DDX_OCIntRO`関数は、OLE コントロールの読み取り専用プロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**int** (または**long)** データ メンバ間での**int** (または**long)** データの転送を管理します。

```cpp
void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    int& value);

void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    long& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocshort"></a><a name="ddx_ocshort"></a>DDX_OCShort

この`DDX_OCShort`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールのプロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの短いデータ メンバとの間での短いデータ転送を管理します。

```cpp
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocshortro"></a><a name="ddx_ocshortro"></a>DDX_OCShortRO

この`DDX_OCShortRO`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの短いデータ メンバとの間での短いデータの転送を管理します。

```cpp
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_octext"></a><a name="ddx_octext"></a>DDX_OCText

**DDX_OCText**関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールのプロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**CString**データ メンバとの間で**CString**データを転送します。

```cpp
void AFXAPI DDX_OCText(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
**オブジェクト**へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="ddx_octextro"></a><a name="ddx_octextro"></a>DDX_OCTextRO

`DDX_OCTextRO` 関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの `CString` データ メンバーの間の `CString` データ転送を管理します。

```cpp
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*Dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
