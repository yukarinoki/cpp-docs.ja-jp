---
title: 標準的なダイアログ データ交換ルーチン |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6c79a96439605bcf9ab670c1f75dda2d50169f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377656"
---
# <a name="standard-dialog-data-exchange-routines"></a>標準的なダイアログ データ エクスチェンジ ルーチン
このトピックでは、一般的な MFC のダイアログ コントロールに使用される標準的なダイアログ データ エクス (チェンジ DDX) ルーチンを示します。  
  
> [!NOTE]
>  標準的なダイアログ データ エクス チェンジ ルーチンは、ヘッダー ファイル afxdd_.h で定義されます。 ただし、アプリケーションでは、afxwin.h を含める必要があります。  
  
### <a name="ddx-functions"></a>DDX 関数  
  
|||  
|-|-|  
|[DDX_CBIndex](#ddx_cbindex)|初期化またはコンボ ボックス コントロールの現在の選択範囲のインデックスを取得します。|  
|[DDX_CBString](#ddx_cbstring)|初期化またはコンボ ボックス コントロールの編集 フィールドの現在の内容を取得します。|  
|[DDX_CBStringExact](#ddx_cbstringexact)|初期化またはコンボ ボックス コントロールの編集 フィールドの現在の内容を取得します。|  
|[DDX_Check](#ddx_check)|初期化またはチェック ボックス コントロールの現在の状態を取得します。|  
|[DDX_Control](#ddx_control)|サブクラス ダイアログ ボックス内で指定されたコントロール。|  
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|初期化または日付と時刻の選択コントロールの日付/時刻のデータを取得します。|  
|[DDX_IPAddress](#ddx_ipaddress)|初期化または IP アドレス コントロールの現在の値を取得します。|  
|[DDX_LBIndex](#ddx_lbindex)|初期化またはリスト ボックス コントロールの現在の選択範囲のインデックスを取得します。|  
|[DDX_LBString](#ddx_lbstring)|初期化またはリスト ボックス コントロール内の現在の選択範囲を取得します。|  
|[DDX_LBStringExact](#ddx_lbstringexact)|初期化またはリスト ボックス コントロール内の現在の選択範囲を取得します。|
|[DDX_ManagedControl](#ddx_managedcontrol)|コントロールのリソース ID に一致する .NET コントロールを作成します|  
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|初期化または、月間予定表コントロールの現在の値を取得します。|  
|[DDX_Radio](#ddx_radio)|初期化またはオプション ボタン コントロールのグループ内で現在チェックされているオプションのコントロールの 0 から始まるインデックスを取得します。|  
|[DDX_Scroll](#ddx_scroll)|初期化またはスクロール コントロールのスクロール ボックスの現在の位置を取得します。|  
|[DDX_Slider](#ddx_slider)|初期化またはスライダー コントロールのスクロール ボックスの現在の位置を取得します。|  
|[DDX_Text](#ddx_text)|初期化またはエディット コントロールの現在の値を取得します。|  
  
##  <a name="ddx_cbindex"></a>  DDX_CBIndex  
 `DDX_CBIndex`関数の転送を管理`int` ダイアログ ボックスでは、コンボ ボックス コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているコンボ ボックス コントロールのリソース ID です。  
  
 *index*  
 ダイアログ ボックス、フォーム ビュー、またはデータとで交換される、コントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_CBIndex`が呼び出されると、*インデックス*コンボ ボックスの現在の選択範囲のインデックスを設定します。 項目が選択されていない場合*インデックス*は 0 に設定します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_cbstring"></a>  DDX_CBString  
 `DDX_CBString`関数の転送を管理`CString` ダイアログ ボックスでは、コンボ ボックス コントロールのエディット コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`CString` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_CBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているコンボ ボックス コントロールのリソース ID です。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータとで交換される、コントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_CBString`が呼び出されると、*値*コンボ ボックスの現在の選択に設定されています。 項目が選択されていない場合*値*が長さ 0 の文字列に設定します。  
  
> [!NOTE]
>  コンボ ボックスがドロップダウン リスト ボックスの場合は、交換される値は 255 文字に制限されます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_cbstringexact"></a>  DDX_CBStringExact  
 `DDX_CBStringExact`関数の転送を管理`CString` ダイアログ ボックスでは、コンボ ボックス コントロールのエディット コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`CString` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているコンボ ボックス コントロールのリソース ID です。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータとで交換される、コントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_CBStringExact`が呼び出されると、*値*コンボ ボックスの現在の選択に設定されています。 項目が選択されていない場合*値*が長さ 0 の文字列に設定します。  
  
> [!NOTE]
>  コンボ ボックスがドロップダウン リスト ボックスの場合は、交換される値は 255 文字に制限されます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_check"></a>  DDX_Check  
 `DDX_Check`関数の転送を管理`int` ダイアログ ボックスでは、チェック ボックス コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_Check(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているチェック ボックス コントロールのリソース ID です。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータとで交換される、コントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_Check`が呼び出されると、*値* チェック ボックス コントロールの現在の状態に設定されています。 可能な状態の値の一覧は、次を参照してください。 [BM_GETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775986) Windows SDK に含まれています。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_control"></a>  DDX_Control  
 `DDX_Control`関数で指定された、コントロールのサブクラス`nIDC`のダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクト。  
  
```  
void AFXAPI DDX_Control(
    CDataExchange* pDX,  
    int nIDC,  
    CWnd& rControl);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `nIDC`  
 サブクラス化される、コントロールのリソース ID です。  
  
 *rControl*  
 ダイアログ ボックス、フォーム ビュー、または指定したコントロールに関連するコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `pDX`オブジェクトは、フレームワークによって提供されるときに、`DoDataExchange`関数が呼び出されます。 したがって、`DDX_Control`のオーバーライド内でのみ呼び出す必要があります`DoDataExchange`です。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_datetimectrl"></a>  DDX_DateTimeCtrl  
 `DDX_DateTimeCtrl`関数が日付と時刻の選択コントロール間の日付/時刻のデータの転送を管理 ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) いずれかのダイアログ ボックスまたはフォーム ビューのオブジェクトで、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)または、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  ダイアログ ボックスまたはフォーム ビューのオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。  
  
 `nIDC`  
 メンバー変数に関連付けられた日付と時刻の選択コントロールのリソース ID です。  
  
 *値*  
 最初の 2 つのバージョンへの参照、`CTime`または`COleDateTime`メンバー変数、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトを使用するには、データを交換します。 3 番目のバージョンへの参照、`CString`データ メンバーのコントロール ビュー オブジェクト。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_DateTimeCtrl`が呼び出されると、*値*現在設定されている日付と日時指定コントロール、またはコントロールの状態が に設定されている*値*exchange の方向に応じて、します。  
  
 上記の 3 番目のバージョンで`DDX_DateTimeCtrl`の転送を管理`CString`日付の間でデータがコントロールを時間と[CString](../../atl-mfc-shared/reference/cstringt-class.md)コントロール ビュー オブジェクトのデータ メンバーです。 文字列の日付と時刻の書式設定の現在のロケールの規則を使用して設定します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  

   

 
## <a name="ddx_managedcontrol"></a>  DDX_ManagedControl
コントロールのリソース ID に一致する .NET コントロールを作成します  
   
### <a name="syntax"></a>構文  
  ```  
template <typename T>  
void DDX_ManagedControl(  
     CDataExchange* pDX,   
     int nIDC,   
     CWinFormsControl<T>& control );  
```
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange クラス](cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられたコントロールのリソース ID です。  
  
 `control`  
 参照、[関数クラス](cwinformscontrol-class.md)オブジェクト。  
   
### <a name="remarks"></a>コメント  
 `DDX_ManagedControl` 呼び出し[CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)リソース コントロール ID に一致するコントロールを作成するには 使用して`DDX_ManagedControl`内のリソース Id からコントロールを作成する[CDialog::OnInitDialog](cdialog-class.md#oninitdialog)です。 データ交換における、Windows フォーム コントロールで DDX/DDV 関数を使用する必要はありません。  
  
 詳細については、次を参照してください。[する方法: Windows フォームで DDX/DDV データ バインドを行う](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h  
   
### <a name="see-also"></a>関連項目  
 [CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)   
 [CDialog::OnInitDialog](cdialog-class.md#oninitdialog)
 

  
##  <a name="ddx_ipaddress"></a>  DDX_IPAddress  
 `DDX_IPAddress`関数は、IP アドレス コントロールと、コントロール ビュー オブジェクトのデータ メンバーの間でデータの転送を管理します。  
  
```  
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられている IP アドレス コントロールのリソース ID です。  
  
 *値*  
 参照、 `DWORD` IP アドレス コントロールの 4 つのフィールド値を格納します。 フィールドが設定または次のように読み込まれます。  
  
|フィールド|ビット フィールドの値を含む|  
|-----------|-------------------------------------|  
|3|0 ~ 7|  
|2|8 ~ 15|  
|1|16 ~ 23|  
|0|24 31 ~|  
  
 Win32 を使用して[IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378) 、値の読み取りや使用を[IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380)値を入力します。 これらのメッセージは、Windows SDK に記述されます。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_IPAddress`が呼び出されると、*値*がいずれかから読み取られる IP アドレス コントロールまたは*値*は、exchange の方向に応じて、コントロールに書き込まれます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_lbindex"></a>  DDX_LBIndex  
 `DDX_LBIndex`関数の転送を管理`int` ダイアログ ボックスでは、リスト ボックス コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているリスト ボックス コントロールのリソース ID です。  
  
 *index*  
 ダイアログ ボックス、フォーム ビュー、またはデータとで交換される、コントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_LBIndex`が呼び出されると、*インデックス*が現在のリスト ボックスの選択範囲のインデックスに設定します。 項目が選択されていない場合*インデックス*が-1 に設定します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_lbstring"></a>  DDX_LBString  
 `DDX_LBString`関数の転送を管理`CString` ダイアログ ボックスでは、リスト ボックス コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`CString` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_LBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているリスト ボックス コントロールのリソース ID です。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータとで交換される、コントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_LBString`リスト ボックス コントロール、先頭に一致するコントロールの最初の項目にデータを転送するために呼び出される*値*が選択されています。 (プレフィックスだけではなく、アイテム全体と一致させる場合、 [DDX_LBStringExact](#ddx_lbstringexact))。一致しない場合は、項目が選択されていません。 一致する小文字が区別されません。  
  
 ときに`DDX_LBString`がリスト ボックス コントロールからデータを転送するために呼び出される*値*が現在のリスト ボックスの選択に設定します。 項目が選択されていない場合*値*が長さ 0 の文字列に設定します。  
  
> [!NOTE]
>  リスト ボックスがドロップダウン リスト ボックスの場合は、交換される値は 255 文字に制限されます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_lbstringexact"></a>  DDX_LBStringExact  
 `DDX_CBStringExact`関数の転送を管理`CString` ダイアログ ボックスでは、リスト ボックス コントロールのエディット コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`CString` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているリスト ボックス コントロールのリソース ID です。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータとで交換される、コントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_LBStringExact`と一致するコントロールの最初の項目、リスト ボックス コントロールにデータを転送するために呼び出される*値*が選択されています。 (項目全体ではなくプレフィックスだけを一致する、 [DDX_LBString](#ddx_lbstring))。一致しない場合は、項目が選択されていません。 一致する小文字が区別されません。  
  
 ときに`DDX_CBStringExact`がリスト ボックス コントロールからデータを転送するために呼び出される*値*が現在のリスト ボックスの選択に設定します。 項目が選択されていない場合*値*が長さ 0 の文字列に設定します。  
  
> [!NOTE]
>  リスト ボックスがドロップダウン リスト ボックスの場合は、交換される値は 255 文字に制限されます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_monthcalctrl"></a>  DDX_MonthCalCtrl  
 `DDX_MonthCalCtrl`関数が、月間予定表コントロールの間での日付データの転送を管理 ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのいずれかに、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)または、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。  
  
 `nIDC`  
 月間予定表コントロールのリソース ID は、メンバー変数に関連付けられています。  
  
 *値*  
 参照、`CTime`または`COleDateTime`メンバー変数のダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロールは、日付の値のみを管理します。 時刻フィールド時のオブジェクトには、コントロールのウィンドウの作成時刻を反映するように設定または任意の時間を設定してあるコントロールへの呼び出しに`CMonthCalCtrl::SetCurSel`です。  
  
 ときに`DDX_MonthCalCtrl`が呼び出されると、*値*月間予定表コントロールの現在の状態に設定されています。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_radio"></a>  DDX_Radio  
 `DDX_Radio`関数の転送を管理`int` ダイアログ ボックスでオプション ボタン コントロール グループの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。 値、`int`どのオプションに従って、グループ内のボタンが選択されているデータ メンバーが決定されます。  
  
```  
void AFXAPI DDX_Radio(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 グループの最初のラジオ コントロールのリソース ID です。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはデータとで交換される、コントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_Radio`が呼び出されると、*値*オプション ボタン コントロール グループの現在の状態に設定されています。 現在チェックされているオプション ボタン コントロールの 0 から始まるインデックスとして値を設定またはないラジオ コントロールの場合は-1 がチェックされます。  
  
 たとえば、グループ内の最初のラジオ ボタンがある場合で (WS_GROUP スタイルのボタン) の値をオンになって、`int`メンバーが 0 です。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_scroll"></a>  DDX_Scroll  
 `DDX_Scroll`関数の転送を管理`int` ダイアログ ボックスでは、スクロール バー コントロールの間でデータ ビュー、またはコントロール ビュー オブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられたスクロール バー コントロールのリソース ID です。  
  
 *値*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_Scroll`が呼び出されると、*値*コントロールのスクロール ボックスの現在の位置に設定されています。 コントロールのスクロール ボックスの現在の位置に関連付けられている値の詳細については、次を参照してください。 [GetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787585) Windows SDK に含まれています。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_slider"></a>  DDX_Slider  
 `DDX_Slider`関数の転送を管理`int` ダイアログ ボックスやフォーム ビュー内のスライダー コントロールの間でデータと`int` ダイアログ ボックスまたはフォーム ビューのオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_Slider(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 スライダー コントロールのリソース ID です。  
  
 *値*  
 交換する値への参照。 このパラメーターを保持またはスライダー コントロールの現在位置を設定します。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_Slider`が呼び出されると、*値*コントロールのスクロール ボックスの現在の位置に設定されているまたは値が、exchange の方向に応じて、位置を取得します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。 スライダー コントロールの概要については、次を参照してください。[を使用して CSliderCtrl](../../mfc/using-csliderctrl.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="ddx_text"></a>  DDX_Text  
 `DDX_Text`関数の転送を管理`int`、 **UINT**、**長い**、 `DWORD`、 `CString`、 **float**、または**二重** ダイアログ ボックスでは、エディット コントロールの間でデータがフォーム ビュー、または表示を制御し、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)  ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    BYTE& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    short& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    UINT& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    long& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    float& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    double& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleCurrency& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのエディット コントロールの ID。  
  
 *値*  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバーへの参照。 データ型*値*のどのオーバー ロードされたバージョンに依存`DDX_Text`を使用します。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)です。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  

## <a name="see-also"></a>関連項目  
 [標準的なダイアログ データ バリデーション ルーチン](../../mfc/reference/standard-dialog-data-validation-routines.md)   
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
