---
title: OLE コントロールのダイアログ データ交換関数 |Microsoft ドキュメント
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
ms.openlocfilehash: 542afe8ba67e1d9c6138998320483a964a08724a
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121826"
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE コントロールのダイアログ データ エクスチェンジ (DDX) 関数
このトピックでは、OLE コントロールのプロパティ ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーの間でデータを交換するために使用 DDX_OC 関数が一覧表示します。  
  
### <a name="ddxoc-functions"></a>DDX_OC 関数  
  
|||  
|-|-|  
|[DDX_OCBool](#ddx_ocbool)|転送を受け持ち**BOOL** OLE コントロールのプロパティの間でデータと**BOOL**データ メンバーです。|  
|[DDX_OCBoolRO](#ddx_ocboolro)|転送を受け持ち**BOOL** OLE コントロールの読み取り専用プロパティの間でデータと**BOOL**データ メンバーです。|  
|[DDX_OCColor](#ddx_occolor)|転送を受け持ち**OLE_COLOR** OLE コントロールのプロパティの間でデータと**OLE_COLOR**データ メンバーです。|  
|[DDX_OCColorRO](#ddx_occolorro)|転送を受け持ち**OLE_COLOR** OLE コントロールの読み取り専用プロパティの間でデータと**OLE_COLOR**データ メンバーです。|  
|[DDX_OCFloat](#ddx_ocfloat)|転送を受け持ち**float** (または**二重**) OLE コントロールのプロパティの間でデータと**float** (または**二重**) データ メンバーです。|  
|[DDX_OCFloatRO](#ddx_ocfloatro)|転送を受け持ち**float** (または**二重**) OLE コントロールの読み取り専用プロパティの間でデータと**float** (または**二重**) データメンバー。|  
|[DDX_OCInt](#ddx_ocint)|転送を受け持ち**int** (または**長い**) OLE コントロールのプロパティの間でデータと**int** (または**長い**) データ メンバーです。|  
|[DDX_OCIntRO](#ddx_ocintro)|転送を受け持ち**int** (または**長い**) OLE コントロールの読み取り専用プロパティの間でデータと**int** (または**長い**) データ メンバーです。|  
|[DDX_OCShort](#ddx_ocshort)|転送を受け持ち**短い**OLE コントロールのプロパティの間でデータと**短い**データ メンバーです。|  
|[DDX_OCShortRO](#ddx_ocshortro)|転送を受け持ち**短い**OLE コントロールの読み取り専用プロパティの間でデータと**短い**データ メンバーです。|  
|[DDX_OCText](#ddx_octext)|転送を受け持ち**CString** OLE コントロールのプロパティの間でデータと**CString**データ メンバーです。|  
|[DDX_OCTextRO](#ddx_octextro)|転送を受け持ち**CString** OLE コントロールの読み取り専用プロパティの間でデータと**CString**データ メンバーです。|  
  
##  <a name="ddx_ocbool"></a>  DDX_OCBool  
 `DDX_OCBool`関数の転送を管理**BOOL**  ダイアログ ボックスでは、OLE コントロールのプロパティの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**BOOL**  ダイアログ ボックス、フォーム ビューのデータ メンバーまたはコントロール ビュー オブジェクト。  
  
```   
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー :** afxdisp.h  
  
##  <a name="ddx_ocboolro"></a>  DDX_OCBoolRO  
 `DDX_OCBoolRO`関数の転送を管理**BOOL**ビュー、またはコントロール ビュー オブジェクトに読み取り専用のプロパティ ダイアログ ボックスでは、OLE コントロールの間でデータがフォームと**BOOL**  ダイアログ ボックスのデータ メンバーフォーム ビュー、またはコントロール ビュー オブジェクト。  
  
```   
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_occolor"></a>  DDX_OCColor  
 `DDX_OCColor`関数は、ダイアログ ボックスで、フォーム ビューでは、OLE コントロールのプロパティ間 OLE_COLOR データの転送を管理またはコントロール ビュー オブジェクトと、ダイアログ ボックスの OLE_COLOR データ メンバーは、フォーム ビュー、またはコントロール ビュー オブジェクト。  
  
```   
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_occolorro"></a>  DDX_OCColorRO  
 `DDX_OCColorRO`関数は、読み取り専用のプロパティ ダイアログ ボックスで、フォーム ビューでは、OLE コントロールの間の OLE_COLOR データの転送を管理またはコントロール ビュー オブジェクトと、ダイアログ ボックスの OLE_COLOR データ メンバーは、フォーム ビュー、またはコントロール ビュー オブジェクト。  
  
```   
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocfloat"></a>  DDX_OCFloat  
 `DDX_OCFloat`関数の転送を管理**float** (または**二重**) ダイアログ ボックスでは、OLE コントロールのプロパティの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**float**(または**二重**) ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
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
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocfloatro"></a>  DDX_OCFloatRO  
 `DDX_OCFloatRO`関数の転送を管理**float** (または**二重**) 読み取り専用のプロパティ ダイアログ ボックスでは、OLE コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**float** (または**二重**) ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
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
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocint"></a>  DDX_OCInt  
 `DDX_OCInt`関数の転送を管理**int** (または**長い**) ダイアログ ボックスでは、OLE コントロールのプロパティの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**int**(または**長い**) ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
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
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocintro"></a>  DDX_OCIntRO  
 `DDX_OCIntRO`関数の転送を管理**int** (または**長い**) 読み取り専用のプロパティ ダイアログ ボックスでは、OLE コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**int**(または**長い**) ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
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
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocshort"></a>  DDX_OCShort  
 `DDX_OCShort`関数は、ダイアログ ボックスで、フォーム ビューでは、OLE コントロールのプロパティ間の短いデータの転送を管理またはコントロール ビュー オブジェクトと、ダイアログ ボックスの短いデータ メンバーは、フォーム ビュー、またはコントロール ビュー オブジェクト。  
  
```   
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocshortro"></a>  DDX_OCShortRO  
 `DDX_OCShortRO`関数は、読み取り専用のプロパティ ダイアログ ボックスで、フォーム ビューでは、OLE コントロールの間の短いデータの転送を管理またはコントロール ビュー オブジェクトと、ダイアログ ボックスの短いデータ メンバーは、フォーム ビュー、またはコントロール ビュー オブジェクト。  
  
```   
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_octext"></a>  DDX_OCText  
 **DDX_OCText**関数の転送を管理**CString**  ダイアログ ボックスでは、OLE コントロールのプロパティの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと**CString**データダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバーです。  
  
```   
void AFXAPI DDX_OCText(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    CString& value); 
```  
  
### <a name="parameters"></a>パラメーター  
 *pDX*  
 ポインター、 **CDataExchange**オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>必要条件  
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
 *pDX*  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 *dispid*  
 コントロールのプロパティのディスパッチ ID。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>Remarks  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  

### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdisp.h
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
