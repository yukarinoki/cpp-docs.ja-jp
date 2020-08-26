---
title: 標準的なダイアログ データ エクスチェンジ ルーチン
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
ms.openlocfilehash: bed60094b25bcc3b1994aa904a8c20324be2abae
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844497"
---
# <a name="standard-dialog-data-exchange-routines"></a>標準的なダイアログ データ エクスチェンジ ルーチン

このトピックでは、一般的な MFC ダイアログコントロールに使用される標準のダイアログデータエクスチェンジ (DDX) ルーチンの一覧を示します。

> [!NOTE]
> 標準的なダイアログデータ交換ルーチンは、ヘッダーファイル afxdd_ .h に定義されています。 ただし、アプリケーションには afxwin.h を含める必要があります。

### <a name="ddx-functions"></a>DDX 関数

|名前|説明|
|-|-|
|[DDX_CBIndex](#ddx_cbindex)|コンボボックスコントロールの現在の選択範囲のインデックスを初期化または取得します。|
|[DDX_CBString](#ddx_cbstring)|コンボボックスコントロールの編集フィールドの現在の内容を初期化または取得します。|
|[DDX_CBStringExact](#ddx_cbstringexact)|コンボボックスコントロールの編集フィールドの現在の内容を初期化または取得します。|
|[DDX_Check](#ddx_check)|チェックボックスコントロールの現在の状態を初期化または取得します。|
|[DDX_Control](#ddx_control)|ダイアログボックス内の特定のコントロールをサブクラス化します。|
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|日付と時刻の選択コントロールの日付または時刻のデータを初期化または取得します。|
|[DDX_IPAddress](#ddx_ipaddress)|IP アドレスコントロールの現在の値を初期化または取得します。|
|[DDX_LBIndex](#ddx_lbindex)|リストボックスコントロールの現在の選択範囲のインデックスを初期化または取得します。|
|[DDX_LBString](#ddx_lbstring)|リストボックスコントロール内の現在の選択項目を初期化または取得します。|
|[DDX_LBStringExact](#ddx_lbstringexact)|リストボックスコントロール内の現在の選択項目を初期化または取得します。|
|[DDX_ManagedControl](#ddx_managedcontrol)|コントロールのリソース ID に一致する .NET コントロールを作成します。|
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|月間予定表コントロールの現在の値を初期化または取得します。|
|[DDX_Radio](#ddx_radio)|ラジオコントロールグループ内で現在チェックされているラジオコントロールの0から始まるインデックスを初期化または取得します。|
|[DDX_Scroll](#ddx_scroll)|スクロールコントロールのつまみの現在位置を初期化または取得します。|
|[DDX_Slider](#ddx_slider)|スライダーコントロールのつまみの現在位置を初期化または取得します。|
|[DDX_Text](#ddx_text)|エディットコントロールの現在の値を初期化または取得します。|

## <a name="ddx_cbindex"></a><a name="ddx_cbindex"></a> DDX_CBIndex

この `DDX_CBIndex` 関数は、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのコンボボックスコントロールと、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられているコンボボックスコントロールのリソース ID。

*インデックス*<br/>
データの交換に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

`DDX_CBIndex`が呼び出されると、 *index*は、現在のコンボボックスの選択項目のインデックスに設定されます。 項目が選択されていない場合、 *index* は0に設定されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_cbstring"></a><a name="ddx_cbstring"></a> DDX_CBString

この `DDX_CBString` 関数は、 `CString` ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのコンボボックスコントロールの編集コントロールと、 `CString` ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_CBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられているコンボボックスコントロールのリソース ID。

*value*<br/>
データの交換に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

`DDX_CBString`を呼び出すと、 *value*が現在のコンボボックスの選択項目に設定されます。 項目が選択されていない場合、 *値* は長さが0の文字列に設定されます。

> [!NOTE]
> コンボボックスがドロップダウンリストボックスの場合、交換される値は255文字に制限されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_cbstringexact"></a><a name="ddx_cbstringexact"></a> DDX_CBStringExact

この `DDX_CBStringExact` 関数は、 `CString` ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのコンボボックスコントロールの編集コントロールと、 `CString` ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられているコンボボックスコントロールのリソース ID。

*value*<br/>
データの交換に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

`DDX_CBStringExact`を呼び出すと、 *value*が現在のコンボボックスの選択項目に設定されます。 項目が選択されていない場合、 *値* は長さが0の文字列に設定されます。

> [!NOTE]
> コンボボックスがドロップダウンリストボックスの場合、交換される値は255文字に制限されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_check"></a><a name="ddx_check"></a> DDX_Check

この `DDX_Check` 関数は、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのチェックボックスコントロールと、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_Check(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられているチェックボックスコントロールのリソース ID。

*value*<br/>
データの交換に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

`DDX_Check`が呼び出されると、*値*はチェックボックスコントロールの現在の状態に設定されます。 使用可能な状態の値の一覧については、Windows SDK の「 [BM_GETCHECK](/windows/win32/Controls/bm-getcheck) 」を参照してください。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_control"></a><a name="ddx_control"></a> DDX_Control

この `DDX_Control` 関数は、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの *nidc*によって指定されたコントロールをサブクラス化します。

```cpp
void AFXAPI DDX_Control(
    CDataExchange* pDX,
    int nIDC,
    CWnd& rControl);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。

*nIDC*<br/>
サブクラス化するコントロールのリソース ID。

*rControl*<br/>
指定したコントロールに関連するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

*PDX*オブジェクトは、関数が呼び出されたときにフレームワークによって提供され `DoDataExchange` ます。 したがって、は、 `DDX_Control` のオーバーライド内でのみ呼び出す必要があり `DoDataExchange` ます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_datetimectrl"></a><a name="ddx_datetimectrl"></a> DDX_DateTimeCtrl

この `DDX_DateTimeCtrl` 関数は、ダイアログボックスまたはフォームビューオブジェクトの日付と時刻の選択コントロール ( [cdatetimectrl 使い方](../../mfc/reference/cdatetimectrl-class.md)) と、ダイアログボックスまたはフォームビューオブジェクトの [CTime](../../atl-mfc-shared/reference/ctime-class.md) データメンバーまたは [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) データメンバーの間で、日付と時刻のデータの転送を管理します。

```cpp
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

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。

*nIDC*<br/>
メンバー変数に関連付けられている日付と時刻の選択コントロールのリソース ID。

*value*<br/>
最初の2つのバージョンで `CTime` は、データの `COleDateTime` 交換に使用されるまたはメンバー変数、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトへの参照。 3番目のバージョンでは、 `CString` データメンバーコントロールビューオブジェクトへの参照です。

### <a name="remarks"></a>解説

`DDX_DateTimeCtrl`が呼び出されると、*値*が日付と時刻の選択コントロールの現在の状態に設定されるか、または exchange の方向に応じてコントロールが*value*に設定されます。

上の3番目のバージョンでは、は、 `DDX_DateTimeCtrl` `CString` 日付と時刻のコントロールと、コントロールビューオブジェクトの [CString](../../atl-mfc-shared/reference/cstringt-class.md) データメンバーとの間のデータ転送を管理します。 文字列は、日付と時刻の書式設定に現在のロケールの規則を使用して書式設定されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_managedcontrol"></a><a name="ddx_managedcontrol"></a> DDX_ManagedControl

コントロールのリソース ID に一致する .NET コントロールを作成します。

### <a name="syntax"></a>構文

```cpp
template <typename T>
void DDX_ManagedControl(
   CDataExchange* pDX,
   int nIDC,
   CWinFormsControl<T>& control );
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
[CDataExchange クラス](cdataexchange-class.md)オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられているコントロールのリソース ID。

*control*<br/>
[CWinFormsControl クラス](cwinformscontrol-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

`DDX_ManagedControl`[CWinFormsControl:: CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)を呼び出して、リソースコントロール ID に一致するコントロールを作成します。 を使用して、 `DDX_ManagedControl` [CDialog:: OnInitDialog](cdialog-class.md#oninitdialog)のリソース id からコントロールを作成します。 データ交換では、Windows フォームコントロールで DDX/DDV 関数を使用する必要はありません。

詳細については、「 [方法: Windows フォームで DDX/DDV データバインディングを実行する](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms

## <a name="ddx_ipaddress"></a><a name="ddx_ipaddress"></a> DDX_IPAddress

関数は、 `DDX_IPAddress` IP アドレスコントロールと、コントロールビューオブジェクトのデータメンバーとの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられた IP アドレスコントロールのリソース ID。

*value*<br/>
IP アドレスコントロールの4つのフィールドの値を格納している DWORD への参照。 フィールドは次のように入力または読み取られます。

|フィールド|フィールド値を含むビット|
|-----------|-------------------------------------|
|3|0 ~ 7|
|2|8 ~ 15|
|1|16 ~ 23|
|0|24 ~ 31|

値を読み取るには Win32 [IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress) を使用し、値を入力するには [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress) を使用します。 これらのメッセージについては、Windows SDK を参照してください。

### <a name="remarks"></a>解説

`DDX_IPAddress`が呼び出されると、IP アドレスコントロールから*値*が読み取られるか、または exchange の方向に応じて*値*がコントロールに書き込まれます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_lbindex"></a><a name="ddx_lbindex"></a> DDX_LBIndex

この `DDX_LBIndex` 関数は、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのリストボックスコントロールと、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられているリストボックスコントロールのリソース ID。

*インデックス*<br/>
データの交換に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

`DDX_LBIndex`が呼び出されると、 *index*は現在のリストボックスの選択項目のインデックスに設定されます。 項目が選択されていない場合、 *index* は-1 に設定されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_lbstring"></a><a name="ddx_lbstring"></a> DDX_LBString

この `DDX_LBString` 関数は、 `CString` ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのリストボックスコントロールと、 `CString` ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_LBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられているリストボックスコントロールのリソース ID。

*value*<br/>
データの交換に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

を `DDX_LBString` 呼び出してリストボックスコントロールにデータを転送すると、コントロール内の先頭に一致する *値* を持つ最初の項目が選択されます。 (プレフィックスだけでなく、項目全体に一致させるには、 [DDX_LBStringExact](#ddx_lbstringexact)を使用します)。一致する項目がない場合は、項目が選択されません。 照合では大文字と小文字が区別されません。

`DDX_LBString`が呼び出され、リストボックスコントロールからデータが転送されるときに、現在のリストボックスの選択に*値*が設定されます。 項目が選択されていない場合、 *値* は長さが0の文字列に設定されます。

> [!NOTE]
> リストボックスがドロップダウンリストボックスの場合、交換される値は255文字に制限されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_lbstringexact"></a><a name="ddx_lbstringexact"></a> DDX_LBStringExact

この `DDX_CBStringExact` 関数は、 `CString` ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのリストボックスコントロールの編集コントロールと、 `CString` ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられているリストボックスコントロールのリソース ID。

*value*<br/>
データの交換に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

を `DDX_LBStringExact` 呼び出してリストボックスコントロールにデータを転送すると、コントロール内の *値* に一致する最初の項目が選択されます。 (項目全体ではなくプレフィックスだけを一致させるには、 [DDX_LBString](#ddx_lbstring)を使用します。)一致する項目がない場合は、項目が選択されません。 照合では大文字と小文字が区別されません。

`DDX_CBStringExact`が呼び出され、リストボックスコントロールからデータが転送されるときに、現在のリストボックスの選択に*値*が設定されます。 項目が選択されていない場合、 *値* は長さが0の文字列に設定されます。

> [!NOTE]
> リストボックスがドロップダウンリストボックスの場合、交換される値は255文字に制限されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_monthcalctrl"></a><a name="ddx_monthcalctrl"></a> DDX_MonthCalCtrl

この `DDX_MonthCalCtrl` 関数は、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの月間予定表コントロール ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) と、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの [CTime](../../atl-mfc-shared/reference/ctime-class.md) または [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) データメンバーのどちらかで、日付データの転送を管理します。

```cpp
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

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。

*nIDC*<br/>
メンバー変数に関連付けられている月間予定表コントロールのリソース ID。

*value*<br/>
`CTime` `COleDateTime` データの交換に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのまたはメンバー変数への参照。

### <a name="remarks"></a>解説

> [!NOTE]
> コントロールは、日付値のみを管理します。 時間オブジェクトの時間フィールドは、コントロールウィンドウの作成時間を反映するように設定されます。また、がの呼び出しによってコントロールに設定された時間も反映され `CMonthCalCtrl::SetCurSel` ます。

`DDX_MonthCalCtrl`が呼び出されると、 *value*は月間予定表コントロールの現在の状態に設定されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_radio"></a><a name="ddx_radio"></a> DDX_Radio

この `DDX_Radio` 関数は、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのラジオコントロールグループと、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間のデータ転送を管理します。 データメンバーの値は、 **`int`** グループ内のどのオプションボタンが選択されているかに応じて決定されます。

```cpp
void AFXAPI DDX_Radio(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
グループ内の最初のラジオコントロールのリソース ID。

*value*<br/>
データの交換に使用するダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

`DDX_Radio`が呼び出されると、 *value*はラジオコントロールグループの現在の状態に設定されます。 値は、現在チェックされているラジオコントロールの0から始まるインデックスとして設定されます。ラジオコントロールがチェックされない場合は-1 になります。

たとえば、グループ内の最初のオプションボタンがオンになっている場合 (WS_GROUP スタイルのボタン)、メンバーの値 **`int`** は0になります。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_scroll"></a><a name="ddx_scroll"></a> DDX_Scroll

この `DDX_Scroll` 関数は、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのスクロールバーコントロールと、 **`int`** ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロールプロパティに関連付けられているスクロールバーコントロールのリソース ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

`DDX_Scroll`が呼び出されると、*値*はコントロールのつまみの現在位置に設定されます。 コントロールのつまみの現在位置に関連付けられている値の詳細については、Windows SDK の「 [Getscrollpos](/windows/win32/api/winuser/nf-winuser-getscrollpos) 」を参照してください。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_slider"></a><a name="ddx_slider"></a> DDX_Slider

この `DDX_Slider` 関数は、 **`int`** ダイアログボックスまたはフォームビューのスライダーコントロールと、 **`int`** ダイアログボックスまたはフォームビューオブジェクトのデータメンバーの間のデータ転送を管理します。

```cpp
void AFXAPI DDX_Slider(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
スライダーコントロールのリソース ID。

*value*<br/>
交換する値への参照。 このパラメーターは、スライダーコントロールの現在位置を保持または設定します。

### <a name="remarks"></a>解説

`DDX_Slider`が呼び出されたときに、*値*がコントロールのつまみの現在位置に設定されるか、または exchange の方向に応じて値が位置を受け取ります。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 スライダーコントロールの詳細については、「 [Using csliderctrl 使い方](../../mfc/using-csliderctrl.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="ddx_text"></a><a name="ddx_text"></a> DDX_Text

この `DDX_Text` 関数は **`int`** **UINT**、 **`long`** `CString` **`float`** **`double`** ダイアログボックス、フォームビュー、またはコントロールビューの編集コントロールと、ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの[CString](../../atl-mfc-shared/reference/cstringt-class.md)データメンバーの間で、、UINT、、DWORD、、、の各データの転送を管理します。

```cpp
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

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトの編集コントロールの ID。

*value*<br/>
ダイアログボックス、フォームビュー、またはコントロールビューオブジェクトのデータメンバーへの参照。 *値*のデータ型は、使用するのオーバーロードされたバージョンによって異なり `DDX_Text` ます。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_

## <a name="see-also"></a>関連項目

[標準的なダイアログデータ検証ルーチン](standard-dialog-data-validation-routines.md)<br/>
[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)<br/>
[CDialog::OnInitDialog](cdialog-class.md#oninitdialog)
