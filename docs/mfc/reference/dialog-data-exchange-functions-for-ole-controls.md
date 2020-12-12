---
description: 詳細については、「OLE コントロールのダイアログデータエクスチェンジ関数」を参照してください。
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
ms.openlocfilehash: ed2a3c36655ce5fccf482c0a7dedad0a4c67baa5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219955"
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE コントロールのダイアログ データ エクスチェンジ (DDX) 関数

このトピックでは、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールのプロパティと、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間でデータを交換するために使用される DDX_OC 関数の一覧を示します。

### <a name="ddx_oc-functions"></a>DDX_OC 関数

|名前|説明|
|-|-|
|[DDX_OCBool](#ddx_ocbool)|OLE コントロールのプロパティと **bool** データメンバーとの間の **ブール** データの転送を管理します。|
|[DDX_OCBoolRO](#ddx_ocboolro)|OLE コントロールの読み取り専用プロパティと **ブール** データメンバーとの間の **ブール** データの転送を管理します。|
|[DDX_OCColor](#ddx_occolor)|OLE コントロールのプロパティと **OLE_COLOR** データメンバーの間の **OLE_COLOR** データの転送を管理します。|
|[DDX_OCColorRO](#ddx_occolorro)|OLE コントロールの読み取り専用プロパティと **OLE_COLOR** データメンバーの間の **OLE_COLOR** データの転送を管理します。|
|[DDX_OCFloat](#ddx_ocfloat)|**`float`** **`double`** OLE コントロールのプロパティと **`float`** (または) データメンバーの間の (または) データの転送を管理し **`double`** ます。|
|[DDX_OCFloatRO](#ddx_ocfloatro)|**`float`** **`double`** OLE コントロールの読み取り専用プロパティと **`float`** (または) データメンバーとの間での (または) データの転送を管理し **`double`** ます。|
|[DDX_OCInt](#ddx_ocint)|**`int`** **`long`** OLE コントロールのプロパティと **`int`** (または) データメンバーの間の (または) データの転送を管理し **`long`** ます。|
|[DDX_OCIntRO](#ddx_ocintro)|**`int`** **`long`** OLE コントロールの読み取り専用プロパティと **`int`** (または) データメンバーとの間での (または) データの転送を管理し **`long`** ます。|
|[DDX_OCShort](#ddx_ocshort)|**`short`** OLE コントロールのプロパティとデータメンバーの間のデータ転送を管理し **`short`** ます。|
|[DDX_OCShortRO](#ddx_ocshortro)|**`short`** OLE コントロールの読み取り専用プロパティとデータメンバーの間のデータ転送を管理し **`short`** ます。|
|[DDX_OCText](#ddx_octext)|OLE コントロールのプロパティと **cstring** データメンバーとの間での **cstring** データの転送を管理します。|
|[DDX_OCTextRO](#ddx_octextro)|OLE コントロールの読み取り専用プロパティと **cstring** データメンバーとの間での **cstring** データの転送を管理します。|

## <a name="ddx_ocbool"></a><a name="ddx_ocbool"></a> DDX_OCBool

この `DDX_OCBool` 関数は、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールのプロパティと、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの **ブール** データメンバーとの間で、**ブール** データの転送を管理します。

```cpp
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー :** afxdisp.h

## <a name="ddx_ocboolro"></a><a name="ddx_ocboolro"></a> DDX_OCBoolRO

この `DDX_OCBoolRO` 関数は、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの **ブール** データメンバーとの間で、**ブール** データの転送を管理します。

```cpp
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_occolor"></a><a name="ddx_occolor"></a> DDX_OCColor

この `DDX_OCColor` 関数は、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールのプロパティと、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE_COLOR データメンバーの間で OLE_COLOR データの転送を管理します。

```cpp
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_occolorro"></a><a name="ddx_occolorro"></a> DDX_OCColorRO

この `DDX_OCColorRO` 関数は、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE_COLOR データメンバーの間で OLE_COLOR データの転送を管理します。

```cpp
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocfloat"></a><a name="ddx_ocfloat"></a> DDX_OCFloat

この `DDX_OCFloat` 関数は、 **`float`** **`double`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールのプロパティと、 **`float`** **`double`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの (または) データメンバーの間の (または) データの転送を管理します。

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

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocfloatro"></a><a name="ddx_ocfloatro"></a> DDX_OCFloatRO

この `DDX_OCFloatRO` 関数は、 **`float`** **`double`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールの読み取り専用プロパティと、 **`float`** **`double`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの (または) データメンバーの間で、(または) データの転送を管理します。

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

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocint"></a><a name="ddx_ocint"></a> DDX_OCInt

この `DDX_OCInt` 関数は、 **`int`** **`long`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールのプロパティと、 **`int`** **`long`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの (または) データメンバーの間の (または) データの転送を管理します。

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

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocintro"></a><a name="ddx_ocintro"></a> DDX_OCIntRO

この `DDX_OCIntRO` 関数は、 **`int`** **`long`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールの読み取り専用プロパティと、 **`int`** **`long`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの (または) データメンバーの間で、(または) データの転送を管理します。

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

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocshort"></a><a name="ddx_ocshort"></a> DDX_OCShort

この `DDX_OCShort` 関数は、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールのプロパティと、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの短いデータメンバーとの間で、短いデータの転送を管理します。

```cpp
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_ocshortro"></a><a name="ddx_ocshortro"></a> DDX_OCShortRO

この `DDX_OCShortRO` 関数は、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの短いデータメンバーとの間で、短いデータの転送を管理します。

```cpp
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_octext"></a><a name="ddx_octext"></a> DDX_OCText

**DDX_OCText** 関数は、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの OLE コントロールのプロパティと、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの **cstring** データメンバーとの間での **cstring** データの転送を管理します。

```cpp
void AFXAPI DDX_OCText(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
**CDataExchange** オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="ddx_octextro"></a><a name="ddx_octextro"></a> DDX_OCTextRO

`DDX_OCTextRO` 関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの `CString` データ メンバーの間の `CString` データ転送を管理します。

```cpp
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
