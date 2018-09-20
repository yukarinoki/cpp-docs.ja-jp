---
title: OLE コントロールのダイアログ データの交換関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- OLE controls [MFC], DDX functions
- DDX (dialog data exchange), OLE support
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a24bac5e27b0a3e0b1c011b1bb6019be2160d281
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382311"
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE コントロールのダイアログ データ エクスチェンジ (DDX) 関数

このトピックでは、OLE コントロールのプロパティ ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーとの間のデータを交換するために使用する DDX_OC 関数を使用します。

### <a name="ddxoc-functions"></a>DDX_OC 関数

|||
|-|-|
|[DDX_OCBool](#ddx_ocbool)|転送を管理**BOOL** OLE コントロールのプロパティの間のデータと**BOOL**データ メンバー。|
|[DDX_OCBoolRO](#ddx_ocboolro)|転送を管理**BOOL** OLE コントロールの読み取り専用プロパティの間でデータと**BOOL**データ メンバー。|
|[DDX_OCColor](#ddx_occolor)|転送を管理**OLE_COLOR** OLE コントロールのプロパティの間のデータと**OLE_COLOR**データ メンバー。|
|[DDX_OCColorRO](#ddx_occolorro)|転送を管理**OLE_COLOR** OLE コントロールの読み取り専用プロパティの間でデータと**OLE_COLOR**データ メンバー。|
|[DDX_OCFloat](#ddx_ocfloat)|転送を管理**float** (または**二重**) OLE コントロールのプロパティの間のデータと**float** (または**二重**) データ メンバー。|
|[DDX_OCFloatRO](#ddx_ocfloatro)|転送を管理**float** (または**二重**) OLE コントロールの読み取り専用プロパティの間でデータと**float** (または**二重**) データメンバー。|
|[DDX_OCInt](#ddx_ocint)|転送を管理**int** (または**長い**) OLE コントロールのプロパティの間のデータと**int** (または**長い**) データ メンバー。|
|[DDX_OCIntRO](#ddx_ocintro)|転送を管理**int** (または**長い**) OLE コントロールの読み取り専用プロパティの間でデータと**int** (または**長い**) データ メンバー。|
|[DDX_OCShort](#ddx_ocshort)|転送を管理**短い**OLE コントロールのプロパティの間のデータと**短い**データ メンバー。|
|[DDX_OCShortRO](#ddx_ocshortro)|転送を管理**短い**OLE コントロールの読み取り専用プロパティの間でデータと**短い**データ メンバー。|
|[DDX_OCText](#ddx_octext)|転送を管理**CString** OLE コントロールのプロパティの間のデータと**CString**データ メンバー。|
|[DDX_OCTextRO](#ddx_octextro)|転送を管理**CString** OLE コントロールの読み取り専用プロパティの間でデータと**CString**データ メンバー。|

##  <a name="ddx_ocbool"></a>  DDX_OCBool

`DDX_OCBool`関数の転送を管理**BOOL**  ダイアログ ボックスでは、OLE コントロールのプロパティの間のデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**BOOL**  ダイアログ ボックス、フォーム ビューのデータ メンバーまたはコントロール ビュー オブジェクト。

```
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー :** afxdisp.h

##  <a name="ddx_ocboolro"></a>  DDX_OCBoolRO

`DDX_OCBoolRO`関数の転送を管理**BOOL**  ダイアログ ボックスでは、OLE コントロールの読み取り専用プロパティの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**BOOL**のダイアログ ボックスで、データ メンバーフォーム ビュー、またはコントロール ビュー オブジェクト。

```
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_occolor"></a>  DDX_OCColor

`DDX_OCColor` OLE_COLOR データのプロパティ ダイアログ ボックスで、フォーム ビューでは、OLE コントロールの間の転送を管理またはコントロール ビュー オブジェクトと、ダイアログ ボックスの OLE_COLOR データ メンバーは、フォーム ビュー、またはコントロール ビュー オブジェクト。

```
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_occolorro"></a>  DDX_OCColorRO

`DDX_OCColorRO`関数は、ダイアログ ボックスで、フォーム ビューでは、OLE コントロールの読み取り専用プロパティ間の OLE_COLOR データの転送を管理またはコントロール ビュー オブジェクトと、ダイアログ ボックスの OLE_COLOR データ メンバーは、フォーム ビュー、またはコントロール ビュー オブジェクト。

```
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_ocfloat"></a>  DDX_OCFloat

`DDX_OCFloat`関数の転送を管理**float** (または**二重**) ダイアログ ボックスでは、OLE コントロールのプロパティの間のデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**float**(または**二重**) ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバー。

```
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
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_ocfloatro"></a>  DDX_OCFloatRO

`DDX_OCFloatRO`関数の転送を管理**float** (または**二重**) ダイアログ ボックスでは、OLE コントロールの読み取り専用プロパティの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**float** (または**二重**) ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバー。

```
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
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_ocint"></a>  DDX_OCInt

`DDX_OCInt`関数の転送を管理**int** (または**長い**) ダイアログ ボックスでは、OLE コントロールのプロパティの間のデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**int**(または**長い**) ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバー。

```
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
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_ocintro"></a>  DDX_OCIntRO

`DDX_OCIntRO`関数の転送を管理**int** (または**長い**) ダイアログ ボックスでは、OLE コントロールの読み取り専用プロパティの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**int**(または**長い**) ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバー。

```
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
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_ocshort"></a>  DDX_OCShort

`DDX_OCShort`  ダイアログ ボックスで、フォーム ビューでは、OLE コントロールのプロパティの間の短いデータの転送を管理またはコントロール ビュー オブジェクトと、ダイアログ ボックスの短いデータ メンバーは、フォーム ビュー、またはコントロール ビュー オブジェクト。

```
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_ocshortro"></a>  DDX_OCShortRO

`DDX_OCShortRO`関数は、ダイアログ ボックスで、フォーム ビューでは、OLE コントロールの読み取り専用プロパティ間の短いデータの転送を管理またはコントロール ビュー オブジェクトと、ダイアログ ボックスの短いデータ メンバーは、フォーム ビュー、またはコントロール ビュー オブジェクト。

```
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_octext"></a>  DDX_OCText

**DDX_OCText**関数の転送を管理**CString**  ダイアログ ボックスでは、OLE コントロールのプロパティの間のデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**CString**データダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバーです。

```
void AFXAPI DDX_OCText(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
ポインターを**CDataExchange**オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

##  <a name="ddx_octextro"></a>  DDX_OCTextRO

`DDX_OCTextRO` 関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの `CString` データ メンバーの間の `CString` データ転送を管理します。

```
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*各*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。

*dispid*<br/>
コントロールのプロパティのディスパッチ ID。

*値*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>Remarks

DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
