---
title: 標準的なダイアログ データ エクスチェンジ ルーチン
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
ms.openlocfilehash: 83d4a66cd3ec41008506b55f0b351fd9bcbc24b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372931"
---
# <a name="standard-dialog-data-exchange-routines"></a>標準的なダイアログ データ エクスチェンジ ルーチン

ここでは、MFC のコモン ダイアログ コントロールで使用される標準のダイアログ データ エクスチェンジ (DDX) ルーチンを示します。

> [!NOTE]
> 標準のダイアログ データ交換ルーチンは、ヘッダー ファイル afxdd_.h で定義されます。 ただし、アプリケーションには afxwin.h を含める必要があります。

### <a name="ddx-functions"></a>DDX 関数

|||
|-|-|
|[DDX_CBIndex](#ddx_cbindex)|コンボ ボックス コントロールの現在の選択部分のインデックスを初期化または取得します。|
|[DDX_CBString](#ddx_cbstring)|コンボ ボックス コントロールのエディット フィールドの現在の内容を初期化または取得します。|
|[DDX_CBStringExact](#ddx_cbstringexact)|コンボ ボックス コントロールのエディット フィールドの現在の内容を初期化または取得します。|
|[DDX_Check](#ddx_check)|チェック ボックス コントロールの現在の状態を初期化または取得します。|
|[DDX_Control](#ddx_control)|ダイアログ ボックス内の特定のコントロールをサブクラスします。|
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|日付と時刻の指定コントロールの日付データまたは時刻データを初期化または取得します。|
|[DDX_IPAddress](#ddx_ipaddress)|IP アドレス コントロールの現在の値を初期化または取得します。|
|[DDX_LBIndex](#ddx_lbindex)|リスト ボックス コントロールの現在の選択部分のインデックスを初期化または取得します。|
|[DDX_LBString](#ddx_lbstring)|リスト ボックス コントロール内の現在の選択範囲を初期化または取得します。|
|[DDX_LBStringExact](#ddx_lbstringexact)|リスト ボックス コントロール内の現在の選択範囲を初期化または取得します。|
|[DDX_ManagedControl](#ddx_managedcontrol)|コントロールのリソース ID に一致する .NET コントロールを作成します。|
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|月間予定表コントロールの現在の値を初期化または取得します。|
|[DDX_Radio](#ddx_radio)|ラジオ コントロール グループ内で現在チェックされている無線コントロールの 0 ベースのインデックスを初期化または取得します。|
|[DDX_Scroll](#ddx_scroll)|スクロール コントロールのつまみの現在位置を初期化または取得します。|
|[DDX_Slider](#ddx_slider)|スライダー コントロールのつまみの現在位置を初期化または取得します。|
|[DDX_Text](#ddx_text)|エディット コントロールの現在の値を初期化または取得します。|

## <a name="ddx_cbindex"></a><a name="ddx_cbindex"></a>DDX_CBIndex

この`DDX_CBIndex`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのコンボ ボックス コントロールと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**int**データ メンバとの間で**int**データを転送する処理を管理します。

```cpp
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているコンボ ボックス コントロールのリソース ID。

*index*<br/>
データを交換するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

呼`DDX_CBIndex`び出されると *、index*は現在のコンボ ボックス選択のインデックスに設定されます。 項目が選択されていない場合、*インデックス*は 0 に設定されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_cbstring"></a><a name="ddx_cbstring"></a>DDX_CBString

この`DDX_CBString`関数は、ダイアログ ボックス`CString`、フォーム ビュー、またはコントロール ビュー オブジェクトのコンボ ボックス コントロールのエディット コントロールと、`CString`ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバ間でのデータ転送を管理します。

```cpp
void AFXAPI DDX_CBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているコンボ ボックス コントロールのリソース ID。

*value*<br/>
データを交換するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

呼`DDX_CBString`び出されると、現在選択されているコンボ ボックスに*値*が設定されます。 項目が選択されていない場合、*値*は長さ 0 の文字列に設定されます。

> [!NOTE]
> コンボ ボックスがドロップダウン リスト ボックスの場合、交換される値は 255 文字に制限されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_cbstringexact"></a><a name="ddx_cbstringexact"></a>DDX_CBStringExact

この`DDX_CBStringExact`関数は、ダイアログ ボックス`CString`、フォーム ビュー、またはコントロール ビュー オブジェクトのコンボ ボックス コントロールのエディット コントロールと、`CString`ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバ間でのデータ転送を管理します。

```cpp
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているコンボ ボックス コントロールのリソース ID。

*value*<br/>
データを交換するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

呼`DDX_CBStringExact`び出されると、現在選択されているコンボ ボックスに*値*が設定されます。 項目が選択されていない場合、*値*は長さ 0 の文字列に設定されます。

> [!NOTE]
> コンボ ボックスがドロップダウン リスト ボックスの場合、交換される値は 255 文字に制限されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_check"></a><a name="ddx_check"></a>DDX_Check

この`DDX_Check`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのチェック ボックス コントロールと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**int**データ メンバとの間で**int**データを転送する処理を管理します。

```cpp
void AFXAPI DDX_Check(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているチェック ボックス コントロールのリソース ID。

*value*<br/>
データを交換するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

呼`DDX_Check`び出されると *、value*はチェック ボックス コントロールの現在の状態に設定されます。 可能な状態値の一覧については、Windows SDK の[BM_GETCHECK](/windows/win32/Controls/bm-getcheck)を参照してください。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_control"></a><a name="ddx_control"></a>DDX_Control

この`DDX_Control`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの*nIDC*で指定されたコントロールをサブクラス化します。

```cpp
void AFXAPI DDX_Control(
    CDataExchange* pDX,
    int nIDC,
    CWnd& rControl);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*nIDC*<br/>
サブクラス化するコントロールのリソース ID。

*コントロール*<br/>
指定したコントロールに関連するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

*pDX*オブジェクトは、`DoDataExchange`関数が呼び出されたときにフレームワークによって提供されます。 したがって、`DDX_Control`のオーバーライドの中でのみ呼び`DoDataExchange`出す必要があります。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_datetimectrl"></a><a name="ddx_datetimectrl"></a>DDX_DateTimeCtrl

この`DDX_DateTimeCtrl`関数は、ダイアログ ボックスまたはフォーム ビュー オブジェクトの日付と時刻の選択コントロール ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) と、ダイアログ ボックスまたはフォーム ビュー オブジェクトの[CTime](../../atl-mfc-shared/reference/ctime-class.md)または[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)データ メンバー間での日付データや時刻データの転送を管理します。

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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。

*nIDC*<br/>
メンバー変数に関連付けられている日時指定コントロールのリソース ID。

*value*<br/>
最初の 2 つのバージョンでは、または`CTime``COleDateTime`メンバ変数、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトへの参照を使用します。 3 番目のバージョンでは、`CString`データ メンバー コントロール ビュー オブジェクトへの参照。

### <a name="remarks"></a>解説

呼`DDX_DateTimeCtrl`び出されると *、value*は日時指定コントロールの現在の状態に設定されるか、交換の方向に応じてコントロールが*value*に設定されます。

上記の 3 番目`DDX_DateTimeCtrl`のバージョンでは、日付`CString`時刻コントロールとコントロール ビュー オブジェクトの[CString](../../atl-mfc-shared/reference/cstringt-class.md)データ メンバー間のデータ転送を管理します。 文字列は、日付と時刻の書式設定に関する現在のロケールの規則を使用して書式設定されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_managedcontrol"></a><a name="ddx_managedcontrol"></a>DDX_ManagedControl

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

*Pdx*<br/>
[クラス](cdataexchange-class.md)オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているコントロールのリソース ID。

*コントロール*<br/>
[クラス](cwinformscontrol-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

`DDX_ManagedControl`を呼び出して、リソース[コントロール](cwinformscontrol-class.md#createmanagedcontrol)ID に一致するコントロールを作成します。 `DDX_ManagedControl` [CDialog::OnInitDialog](cdialog-class.md#oninitdialog)でリソース ID からコントロールを作成するために使用します。 データ交換の場合、Windows フォーム コントロールで DDX/DDV 関数を使用する必要はありません。

詳細については、「[方法 : Windows フォームを使用して DDX/DDV データ バインディングを実行](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)する 」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h

## <a name="ddx_ipaddress"></a><a name="ddx_ipaddress"></a>DDX_IPAddress

この`DDX_IPAddress`関数は、IP アドレス コントロールとコントロール ビュー オブジェクトのデータ メンバー間のデータ転送を管理します。

```cpp
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられている IP アドレス コントロールのリソース ID。

*value*<br/>
IP アドレス コントロールの 4 フィールド値を含む DWORD への参照。 フィールドは次のように入力または読み取られます。

|フィールド|フィールド値を含むビット|
|-----------|-------------------------------------|
|3|0 から 7|
|2|8から15まで|
|1|16から23まで|
|0|24 から 31|

Win32 [IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress)を使用して値を読み取るか、値を入力[IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress)使用します。 これらのメッセージは Windows SDK で説明されています。

### <a name="remarks"></a>解説

呼`DDX_IPAddress`び出されると、*値*は IP アドレス コントロールから読み取られるか、交換の方向に応じて*コントロールに値*が書き込まれます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_lbindex"></a><a name="ddx_lbindex"></a>DDX_LBIndex

この`DDX_LBIndex`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのリスト ボックス コントロールと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**int**データ メンバとの間で**int**データを転送する処理を管理します。

```cpp
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているリスト ボックス コントロールのリソース ID。

*index*<br/>
データを交換するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

呼`DDX_LBIndex`び出されると *、index*は現在のリスト ボックス選択のインデックスに設定されます。 項目が選択されていない場合、*インデックス*は -1 に設定されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_lbstring"></a><a name="ddx_lbstring"></a>Ddx_lbstring

この`DDX_LBString`関数は、ダイアログ ボックス`CString`、フォーム ビュー、またはコントロール ビュー オブジェクトのリスト ボックス コントロールと、ダイアログ`CString`ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバ間でのデータ転送を管理します。

```cpp
void AFXAPI DDX_LBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているリスト ボックス コントロールのリソース ID。

*value*<br/>
データを交換するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

リスト`DDX_LBString`ボックス コントロールにデータを転送するために呼び出されると、開始値*と一致*するコントロールの最初の項目が選択されます。 (単なる接頭辞ではなく項目全体にマッチするには[、DDX_LBStringExact](#ddx_lbstringexact)を使用します。一致するものがない場合、項目は選択されません。 一致は大文字と小文字を区別しません。

リスト`DDX_LBString`ボックス コントロールからデータを転送するために呼び出されると、*値*は現在のリスト ボックス選択に設定されます。 項目が選択されていない場合、*値*は長さ 0 の文字列に設定されます。

> [!NOTE]
> リスト ボックスがドロップダウン リスト ボックスの場合、交換される値は 255 文字に制限されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_lbstringexact"></a><a name="ddx_lbstringexact"></a>DDX_LBStringExact

この`DDX_CBStringExact`関数は、ダイアログ ボックス`CString`、フォーム ビュー、またはコントロール ビュー オブジェクトのリスト ボックス コントロールのエディット コントロールと、`CString`ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのデータ メンバ間でのデータ転送を管理します。

```cpp
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているリスト ボックス コントロールのリソース ID。

*value*<br/>
データを交換するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

リスト`DDX_LBStringExact`ボックス コントロールにデータを転送するために呼び出されると、*値*に一致するコントロールの最初の項目が選択されます。 (項目全体ではなく、単なる接頭辞を一致させる場合は[、DDX_LBString](#ddx_lbstring)を使用します。一致するものがない場合、項目は選択されません。 一致は大文字と小文字を区別しません。

リスト`DDX_CBStringExact`ボックス コントロールからデータを転送するために呼び出されると、*値*は現在のリスト ボックス選択に設定されます。 項目が選択されていない場合、*値*は長さ 0 の文字列に設定されます。

> [!NOTE]
> リスト ボックスがドロップダウン リスト ボックスの場合、交換される値は 255 文字に制限されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_monthcalctrl"></a><a name="ddx_monthcalctrl"></a>DDX_MonthCalCtrl

この`DDX_MonthCalCtrl`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの月間予定表コントロール ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) と、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの[CTime](../../atl-mfc-shared/reference/ctime-class.md)または[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)データ メンバー間での日付データの転送を管理します。

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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。

*nIDC*<br/>
メンバー変数に関連付けられている月間予定表コントロールのリソース ID。

*value*<br/>
データを交換する`CTime`ダイアログ`COleDateTime`ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのまたはメンバー変数への参照。

### <a name="remarks"></a>解説

> [!NOTE]
> コントロールは日付値のみを管理します。 time オブジェクトの time フィールドは、コントロール ウィンドウの作成時刻、または コントロールでの設定時刻を反映するように`CMonthCalCtrl::SetCurSel`設定されます。

呼`DDX_MonthCalCtrl`び出されると、*値*は月間予定表コントロールの現在の状態に設定されます。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_radio"></a><a name="ddx_radio"></a>DDX_Radio

この`DDX_Radio`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの無線制御グループと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**int**データ メンバ間での**int**データの転送を管理します。 **int**データ メンバーの値は、グループ内で選択されたラジオ ボタンによって決まります。

```cpp
void AFXAPI DDX_Radio(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
グループ内の最初の無線コントロールのリソース ID。

*value*<br/>
データを交換するダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

呼`DDX_Radio`び出されると、*値*は無線制御グループの現在の状態に設定されます。 この値は、現在チェックされている無線コントロールの 0 ベースのインデックスとして設定されます。

たとえば、グループ内の最初のラジオ ボタンがオンになっている場合 (WS_GROUPスタイルのボタン **)、int**メンバの値は 0 になります。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_scroll"></a><a name="ddx_scroll"></a>DDX_Scroll

この`DDX_Scroll`関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのスクロール バー コントロールと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの**int**データ メンバー間での**int**データの転送を管理します。

```cpp
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange` オブジェクトを指すポインターです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
コントロール プロパティに関連付けられているスクロール バー コントロールのリソース ID。

*value*<br/>
データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。

### <a name="remarks"></a>解説

呼`DDX_Scroll`び出されると *、value*はコントロールのつまみの現在位置に設定されます。 コントロールのつまみの現在の位置に関連付けられている値の詳細については、Windows SDK の[「GetScrollPos」](/windows/win32/api/winuser/nf-winuser-getscrollpos)を参照してください。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_slider"></a><a name="ddx_slider"></a>DDX_Slider

この`DDX_Slider`関数は、ダイアログ ボックスまたはフォーム**ビューのスライダー**コントロールと、ダイアログ ボックスまたはフォーム ビュー オブジェクトの int データ メンバーとの間で**int**データを転送する処理を管理します。

```cpp
void AFXAPI DDX_Slider(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
スライダー コントロールのリソース ID。

*value*<br/>
交換する値への参照。 このパラメータは、スライダー コントロールの現在位置を保持または設定します。

### <a name="remarks"></a>解説

呼`DDX_Slider`び出されると *、value*はコントロールのつまみの現在位置に設定されるか、交換の方向に応じて値が位置を受け取ります。

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 スライダー コントロールの詳細については、「 [CSliderCtrl](../../mfc/using-csliderctrl.md)の使用 」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="ddx_text"></a><a name="ddx_text"></a>DDX_Text

この`DDX_Text`関数は、ダイアログ ボックス、フォーム ビュー、`CString`またはコントロール ビューの編集コントロールと、ダイアログ**double**ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの[CString](../../atl-mfc-shared/reference/cstringt-class.md)データ メンバとの間で **、int**、UINT、long、DWORD、float、またはダブル データの転送を管理します。 **UINT** **long** **float**

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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*nIDC*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクト内のエディット コントロールの ID。

*value*<br/>
ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクト内のデータ メンバへの参照。 *値*のデータ型は、使用するオーバーロードされたバージョンによって`DDX_Text`異なります。

### <a name="remarks"></a>解説

DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdd_.h

## <a name="see-also"></a>関連項目

[標準ダイアログ データ検証ルーチン](standard-dialog-data-validation-routines.md)<br/>
[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[コントロールを作成します。](cwinformscontrol-class.md#createmanagedcontrol)<br/>
[CDialog::OnInitDialog](cdialog-class.md#oninitdialog)
