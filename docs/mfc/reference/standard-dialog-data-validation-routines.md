---
title: 標準的なダイアログ データ バリデーション ルーチン |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17b99d87db2fee3cf80c25157cdb2b2d2b54903b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376043"
---
# <a name="standard-dialog-data-validation-routines"></a>標準的なダイアログ データ検証ルーチン
このトピックでは、共通の MFC ダイアログ コントロールの使用される標準的なダイアログ データ バリデーション (DDV) ルーチンを示します。  
  
> [!NOTE]
>  標準的なダイアログ データ エクス チェンジ ルーチンは、ヘッダー ファイル afxdd_.h で定義されます。 ただし、アプリケーションでは、afxwin.h を含める必要があります。  
  
### <a name="ddv-functions"></a>DDV 関数  
  
|||  
|-|-|  
|[DDV_MaxChars](#ddv_maxchars)|特定の制御文字の数が指定された最大値を超えていないことを確認します。|  
|[DDV_MinMaxByte](#ddv_minmaxbyte)|指定されたコントロールの値を超えていないことを確認、指定された**バイト**範囲です。|  
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|指定したコントロールの値が指定した時間範囲を超えていないことを確認します。|  
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|指定されたコントロールの値を超えていないことを確認、指定された**二重**範囲です。|  
|[DDV_MinMaxDWord](#ddv_minmaxdword)|指定されたコントロールの値を超えていないことを確認、指定された**DWORD**範囲です。|  
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|指定されたコントロールの値を超えていないことを確認、指定された**float**範囲です。|  
|[DDV_MinMaxInt](#ddv_minmaxint)|指定されたコントロールの値を超えていないことを確認、指定された**int**範囲です。|  
|[DDV_MinMaxLong](#ddv_minmaxlong)|指定されたコントロールの値を超えていないことを確認、指定された**長い**範囲です。|  
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|指定されたコントロールの値を超えていないことを確認、指定された**LONGLONG**範囲です。|  
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|指定したコントロールの値が指定した日付範囲を超えていないことを確認します。|  
|[DDV_MinMaxShort](#ddv_minmaxshort)|指定されたコントロールの値を超えていないことを確認、指定された**短い**範囲です。|  
|[DDV_MinMaxSlider](#ddv_minmaxslider)|指定された範囲内に特定のスライダー コントロールの値を確認します。|  
|[DDV_MinMaxUInt](#ddv_minmaxuint)|指定されたコントロールの値を超えていないことを確認、指定された**UINT**範囲です。|  
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|特定のコントロールの値が 2 つの指定した値があることを確認します。| 
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|指定されたコントロールの値を超えていないことを確認、指定された**使い**範囲です。|  
  

  
##  <a name="ddv_maxchars"></a>  DDV_MaxChars  
 呼び出す`DDV_MaxChars`コントロール内の文字の量に関連付けられていることを確認する*値*を超えない*文字数*です。  
  
```   
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,  
    CString const& value,  
    int nChars); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `nChars`  
 使用できる文字の最大数。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxbyte"></a>  DDV_MinMaxByte  
 呼び出す`DDV_MinMaxByte`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,  
    BYTE value,  
    BYTE minVal,  
    BYTE maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**バイト**) 許可します。  
  
 `maxVal`  
 最大値 (型の**バイト**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxdatetime"></a>  DDV_MinMaxDateTime  
 呼び出す`DDV_MinMaxDateTime`日付と時刻の選択で日付/時刻値を制御することを確認する ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) に関連付けられている*refValue*間`refMinRange`と`refMaxRange`です。  
  
```   
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
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。  
  
 *refValue*  
 参照、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)または[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数に関連付けられているオブジェクト。 このオブジェクトには、検証に使用するデータが含まれています。  
  
 `refMinRange`  
 最小許容される値の日付/時刻です。  
  
 `refMaxRange`  
 許容される最大の日付/時刻値。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxdouble"></a>  DDV_MinMaxDouble  
 呼び出す`DDV_MinMaxDouble`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,  
    double const& value,  
    double minVal,  
    double maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**二重**) 許可します。  
  
 `maxVal`  
 最大値 (型の**二重**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxdword"></a>  DDV_MinMaxDWord  
 呼び出す`DDV_MinMaxDWord`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,  
    DWORD const& value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の`DWORD`) 許可します。  
  
 `maxVal`  
 最大値 (型の`DWORD`) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxfloat"></a>  DDV_MinMaxFloat  
 呼び出す`DDV_MinMaxFloat`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,  
    float value,  
    float minVal,  
    float maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**float**) 許可します。  
  
 `maxVal`  
 最大値 (型の**float**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxint"></a>  DDV_MinMaxInt  
 呼び出す`DDV_MinMaxInt`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,  
    int value,  
    int minVal,  
    int maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の`int`) 許可します。  
  
 `maxVal`  
 最大値 (型の`int`) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxlong"></a>  DDV_MinMaxLong  
 呼び出す`DDV_MinMaxLong`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,  
    long value,  
    long minVal,  
    long maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**長い**) 許可します。  
  
 `maxVal`  
 最大値 (型の**長い**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxlonglong"></a>  DDV_MinMaxLongLong  
 呼び出す`DDV_MinMaxLongLong`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,  
    LONGLONG value,  
    LONGLONG minVal,  
    LONGLONG maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**LONGLONG**) 許可します。  
  
 `maxVal`  
 最大値 (型の**LONGLONG**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxmonth"></a>  DDV_MinMaxMonth  
 呼び出す`DDV_MinMaxMonth`月間予定表で日付/時刻値を制御することを確認する ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) に関連付けられている*refValue*間`refMinRange`と`refMaxRange`です。  
  
```   
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
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *refValue*  
 型のオブジェクトへの参照を`CTime`または`COleDateTime` ダイアログ ボックスのメンバー変数に関連付けられている、フォーム ビュー、またはオブジェクトの表示を制御します。 このオブジェクトには、検証に使用するデータが含まれています。 この参照時に MFC パス`DDV_MinMaxMonth`と呼びます。  
  
 `refMinRange`  
 最小許容される値の日付/時刻です。  
  
 `refMaxRange`  
 許容される最大の日付/時刻値。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxshort"></a>  DDV_MinMaxShort  
 呼び出す`DDV_MinMaxShort`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,  
    short value,  
    short minVal,  
    short maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**短い**) 許可します。  
  
 `maxVal`  
 最大値 (型の**短い**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxslider"></a>  DDV_MinMaxSlider  
 呼び出す`DDV_MinMaxSlider`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,  
    DWORD value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 検証に使用する値への参照。 このパラメーターを保持またはスライダー コントロールのつまみの現在の位置を設定します。  
  
 `minVal`  
 許容される最小値。  
  
 `maxVal`  
 許容される最大値。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 スライダー コントロールの概要については、次を参照してください。[を使用して CSliderCtrl](../../mfc/using-csliderctrl.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxuint"></a>  DDV_MinMaxUInt  
 呼び出す`DDV_MinMaxUInt`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,  
    UINT value,  
    UINT minVal,  
    UINT maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**UINT**) 許可します。  
  
 `maxVal`  
 最大値 (型の**UINT**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddv_minmaxulonglong"></a>  DDV_MinMaxULongLong  
 呼び出す`DDV_MinMaxULongLong`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,  
    ULONGLONG value,  
    ULONGLONG  minVal ,  
    ULONGLONG  maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**使い**) 許可します。  
  
 `maxVal`  
 最大値 (型の**使い**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
    
## <a name="see-also"></a>関連項目  
 [標準的なダイアログ データ エクス チェンジ ルーチン](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

 ## <a name="ddvminmaxunsigned"></a>DDV_MinMaxUnsigned
呼び出す`DDV_MinMaxUnsigned`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
   
### <a name="syntax"></a>構文    
```
   void AFXAPI DDV_MinMaxUnsigned(  
       CDataExchange* pDX,  
       unsigned value,  
       unsigned minVal,  
       unsigned maxVal );  
```
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータの検証をコントロール ビュー オブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**符号なし**) 許可します。  
  
 `maxVal`  
 最大値 (型の**符号なし**) 許可します。  
   
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../dialog-data-exchange-and-validation.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdd_.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [DDX_Slider](#ddx_slider)   
 [DDX_FieldSlider](#ddx_fieldslider)
 


