---
title: プロパティ ページ (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
ms.openlocfilehash: 9a04395aec8c2eb968e5cefaf410643a1ce03e32
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843587"
---
# <a name="property-pages-mfc"></a>プロパティ ページ (MFC)

プロパティページには、ダイアログデータエクスチェンジ (DDX) に基づくデータマッピング機構をサポートすることにより、特定の OLE コントロールのプロパティの現在の値がカスタマイズ可能なグラフィカルインターフェイスに表示されます。

このデータマップ機構は、プロパティページコントロールを OLE コントロールの個々のプロパティにマップします。 コントロールプロパティの値には、プロパティページコントロールの状態または内容が反映されます。 プロパティページのコントロールとプロパティ間のマッピングは、プロパティページのメンバー関数の **DDP_** 関数呼び出しによって指定され `DoDataExchange` ます。 次に示すのは、コントロールのプロパティページを使用して入力されたデータを交換する **DDP_** 関数の一覧です。

### <a name="property-page-data-transfer"></a>プロパティページデータ転送

|名前|説明|
|-|-|
|[DDP_CBIndex](#ddp_cbindex)|コンボボックス内の選択した文字列のインデックスをコントロールのプロパティにリンクします。|
|[DDP_CBString](#ddp_cbstring)|コンボボックス内の選択した文字列をコントロールのプロパティにリンクします。 選択した文字列は、プロパティの値と同じ文字で始まることができますが、完全に一致する必要はありません。|
|[DDP_CBStringExact](#ddp_cbstringexact)|コンボボックス内の選択した文字列をコントロールのプロパティにリンクします。 選択した文字列とプロパティの文字列値が正確に一致している必要があります。|
|[DDP_Check](#ddp_check)|コントロールのプロパティページのチェックボックスをコントロールのプロパティにリンクします。|
|[DDP_LBIndex](#ddp_lbindex)|リストボックス内の選択した文字列のインデックスをコントロールのプロパティにリンクします。|
|[DDP_LBString](#ddp_lbstring)|リストボックス内の選択した文字列をコントロールのプロパティにリンクします。 選択した文字列は、プロパティの値と同じ文字で始まることができますが、完全に一致している必要はありません。|
|[DDP_LBStringExact](#ddp_lbstringexact)|リストボックス内の選択した文字列をコントロールのプロパティにリンクします。 選択した文字列とプロパティの文字列値が正確に一致している必要があります。|
|[DDP_PostProcessing](#ddp_postprocessing)|コントロールからのプロパティ値の転送を完了します。|
|[DDP_Radio](#ddp_radio)|コントロールのプロパティページのラジオボタングループをコントロールのプロパティとリンクします。|
|[DDP_Text](#ddp_text)|コントロールのプロパティページ内のコントロールを、コントロールのプロパティを使用してリンクします。 この関数は、、、BSTR、など、いくつかの異なる種類のプロパティを処理し **`double`** **`short`** **`long`** ます。|

関数およびプロパティページの詳細については、 `DoDataExchange` 「 [ActiveX コントロール: プロパティページ](../../mfc/mfc-activex-controls-property-pages.md)」を参照してください。

OLE コントロールのプロパティページを作成および管理するために使用するマクロの一覧を次に示します。

### <a name="property-pages"></a>[プロパティ ページ]

|名前|説明|
|-|-|
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|プロパティページ Id の一覧を開始します。|
|[END_PROPPAGEIDS](#end_proppageids)|プロパティページ Id の一覧を終了します。|
|[PROPPAGEID](#proppageid)|コントロールクラスのプロパティページを宣言します。|

## <a name="ddp_cbindex"></a><a name="ddp_cbindex"></a> DDP_CBIndex

プロパティページの関数でこの関数を呼び出して、 `DoDataExchange` プロパティページのコンボボックス内の現在の選択範囲のインデックスと整数プロパティの値を同期します。

```cpp
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*PszPropName*によって指定されたコントロールプロパティに関連付けられているコンボボックスコントロールのリソース ID。

*レプリカ*<br/>
*Id*で指定されたプロパティページコントロールと、 *pszPropName*によって指定されたプロパティに関連付けられているメンバー変数。

*pszPropName*<br/>
*Id*で指定されたコンボボックスコントロールと交換されるコントロールプロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する関数呼び出しの前に呼び出す必要があり `DDX_CBIndex` ます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_cbstring"></a><a name="ddp_cbstring"></a> DDP_CBString

プロパティページの関数でこの関数を呼び出して、 `DoDataExchange` 文字列プロパティの値を、プロパティページのコンボボックスで現在選択されている値と同期します。

```cpp
void AFXAPI DDP_CBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*PszPropName*によって指定されたコントロールプロパティに関連付けられているコンボボックスコントロールのリソース ID。

*レプリカ*<br/>
*Id*で指定されたプロパティページコントロールと、 *pszPropName*によって指定されたプロパティに関連付けられているメンバー変数。

*pszPropName*<br/>
*Id*で指定されたコンボボックスの文字列と交換されるコントロールプロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する関数呼び出しの前に呼び出す必要があり `DDX_CBString` ます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_cbstringexact"></a><a name="ddp_cbstringexact"></a> DDP_CBStringExact

プロパティページの `DoDataExchange` コンボボックスで現在選択されている項目と完全に一致する文字列プロパティの値を同期するには、プロパティページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*PszPropName*によって指定されたコントロールプロパティに関連付けられているコンボボックスコントロールのリソース ID。

*レプリカ*<br/>
*Id*で指定されたプロパティページコントロールと、 *pszPropName*によって指定されたプロパティに関連付けられているメンバー変数。

*pszPropName*<br/>
*Id*で指定されたコンボボックスの文字列と交換されるコントロールプロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する関数呼び出しの前に呼び出す必要があり `DDX_CBStringExact` ます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_check"></a><a name="ddp_check"></a> DDP_Check

プロパティページの関数でこの関数を呼び出して、プロパティ `DoDataExchange` の値を、関連付けられているプロパティページのチェックボックスコントロールと同期します。

```cpp
void AFXAPI DDP_Check(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*PszPropName*によって指定されたコントロールプロパティに関連付けられているチェックボックスコントロールのリソース ID。

*レプリカ*<br/>
*Id*で指定されたプロパティページコントロールと、 *pszPropName*によって指定されたプロパティに関連付けられているメンバー変数。

*pszPropName*<br/>
*Id*で指定されたチェックボックスコントロールと交換されるコントロールプロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する関数呼び出しの前に呼び出す必要があり `DDX_Check` ます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_lbindex"></a><a name="ddp_lbindex"></a> DDP_LBIndex

プロパティページの関数でこの関数を呼び出して、 `DoDataExchange` プロパティページのリストボックス内の現在の選択範囲のインデックスと整数プロパティの値を同期します。

```cpp
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*PszPropName*によって指定されたコントロールプロパティに関連付けられているリストボックスコントロールのリソース ID。

*レプリカ*<br/>
*Id*で指定されたプロパティページコントロールと、 *pszPropName*によって指定されたプロパティに関連付けられているメンバー変数。

*pszPropName*<br/>
*Id*で指定されたリストボックス文字列と交換されるコントロールプロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する関数呼び出しの前に呼び出す必要があり `DDX_LBIndex` ます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_lbstring"></a><a name="ddp_lbstring"></a> DDP_LBString

プロパティページの関数でこの関数を呼び出して、 `DoDataExchange` プロパティページのリストボックス内の現在の選択項目と文字列プロパティの値を同期します。

```cpp
void AFXAPI DDP_LBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*PszPropName*によって指定されたコントロールプロパティに関連付けられているリストボックスコントロールのリソース ID。

*レプリカ*<br/>
*Id*で指定されたプロパティページコントロールと、 *pszPropName*によって指定されたプロパティに関連付けられているメンバー変数。

*pszPropName*<br/>
*Id*で指定されたリストボックス文字列と交換されるコントロールプロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する関数呼び出しの前に呼び出す必要があり `DDX_LBString` ます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_lbstringexact"></a><a name="ddp_lbstringexact"></a> DDP_LBStringExact

プロパティページの `DoDataExchange` リストボックスで現在選択されている項目と完全に一致する文字列プロパティの値を同期するには、プロパティページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*PszPropName*によって指定されたコントロールプロパティに関連付けられているリストボックスコントロールのリソース ID。

*レプリカ*<br/>
*Id*で指定されたプロパティページコントロールと、 *pszPropName*によって指定されたプロパティに関連付けられているメンバー変数。

*pszPropName*<br/>
*Id*で指定されたリストボックス文字列と交換されるコントロールプロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する関数呼び出しの前に呼び出す必要があり `DDX_LBStringExact` ます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_postprocessing"></a><a name="ddp_postprocessing"></a> DDP_PostProcessing

プロパティ `DoDataExchange` 値が保存されている場合、プロパティページからコントロールへのプロパティ値の転送を完了するには、プロパティページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

### <a name="remarks"></a>解説

すべてのデータ交換関数が完了した後に、この関数を呼び出す必要があります。 次に例を示します。

[!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_radio"></a><a name="ddp_radio"></a> DDP_Radio

`DoPropExchange`プロパティの値を、関連付けられているプロパティページのラジオボタンコントロールと同期するには、コントロールの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_Radio(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*PszPropName*によって指定されたコントロールプロパティに関連付けられているオプションボタンコントロールのリソース ID。

*レプリカ*<br/>
*Id*で指定されたプロパティページコントロールと、 *pszPropName*によって指定されたプロパティに関連付けられているメンバー変数。

*pszPropName*<br/>
*Id*で指定されたオプションボタンコントロールと交換されるコントロールプロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する関数呼び出しの前に呼び出す必要があり `DDX_Radio` ます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_text"></a><a name="ddp_text"></a> DDP_Text

`DoDataExchange`プロパティの値を、関連付けられているプロパティページコントロールと同期するには、コントロールの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    BYTE & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    UINT & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    long & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    DWORD & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    float & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    double & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    CString & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
オブジェクトへのポインター `CDataExchange` 。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*PszPropName*によって指定されたコントロールプロパティに関連付けられているコントロールのリソース ID。

*レプリカ*<br/>
*Id*で指定されたプロパティページコントロールと、 *pszPropName*によって指定されたプロパティに関連付けられているメンバー変数。

*pszPropName*<br/>
*Id*で指定されたコントロールと交換されるコントロールプロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する関数呼び出しの前に呼び出す必要があり `DDX_Text` ます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="begin_proppageids"></a><a name="begin_proppageids"></a> BEGIN_PROPPAGEIDS

コントロールのプロパティページ Id のリストの定義を開始します。

```
BEGIN_PROPPAGEIDS(class_name,  count)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
プロパティページを指定するコントロールクラスの名前。

*count*<br/>
コントロールクラスによって使用されるプロパティページの数。

### <a name="remarks"></a>解説

クラスのメンバー関数を定義する実装 (.cpp) ファイルで、BEGIN_PROPPAGEIDS マクロを使用してプロパティページリストを起動し、各プロパティページにマクロエントリを追加して、END_PROPPAGEIDS マクロを使用してプロパティページリストを完成させます。

プロパティページの詳細については、「 [ActiveX コントロール: プロパティページ](../../mfc/mfc-activex-controls-property-pages.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="end_proppageids"></a><a name="end_proppageids"></a> END_PROPPAGEIDS

プロパティページ ID リストの定義を終了します。

```
END_PROPPAGEIDS(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
プロパティページを所有するコントロールクラスの名前。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="proppageid"></a><a name="proppageid"></a> PROPPAGEID

OLE コントロールで使用するプロパティページを追加します。

```
PROPPAGEID(clsid)
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
プロパティページの一意のクラス ID。

### <a name="remarks"></a>解説

すべての PROPPAGEID マクロは、コントロールの実装ファイルの BEGIN_PROPPAGEIDS と END_PROPPAGEIDS のマクロの間に配置する必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
