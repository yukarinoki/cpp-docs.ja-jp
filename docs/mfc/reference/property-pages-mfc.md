---
title: プロパティ ページ (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
ms.openlocfilehash: 6456a192a502a0fcc032eaefc667c90ecec86d42
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751145"
---
# <a name="property-pages-mfc"></a>プロパティ ページ (MFC)

プロパティ ページには、ダイアログ データ エクスチェンジ (DDX) に基づくデータ マッピング メカニズムをサポートすることにより、表示および編集するためのカスタマイズ可能なグラフィカル インターフェイスで、特定の OLE コントロール プロパティの現在の値が表示されます。

このデータ マッピング機構は、プロパティ ページ コントロールを OLE コントロールの個々のプロパティにマップします。 コントロール プロパティの値は、プロパティ ページ コントロールの状態または内容を反映します。 プロパティ ページ のコントロールとプロパティの間の**DDP_** マッピングは、プロパティ ページの`DoDataExchange`メンバー関数でDDP_関数呼び出しによって指定されます。 コントロールのプロパティ ページを使用して入力されたデータを交換する**DDP_** 関数の一覧を次に示します。

### <a name="property-page-data-transfer"></a>プロパティ ページのデータ転送

|||
|-|-|
|[DDP_CBIndex](#ddp_cbindex)|コンボ ボックス内の選択した文字列のインデックスをコントロールのプロパティとリンクします。|
|[DDP_CBString](#ddp_cbstring)|コンボ ボックス内の選択した文字列をコントロールのプロパティにリンクします。 選択した文字列は、プロパティの値と同じ文字で始めることができますが、完全に一致する必要はありません。|
|[DDP_CBStringExact](#ddp_cbstringexact)|コンボ ボックス内の選択した文字列をコントロールのプロパティにリンクします。 選択した文字列とプロパティの文字列値は、正確に一致する必要があります。|
|[DDP_Check](#ddp_check)|コントロールのプロパティ ページのチェック ボックスをコントロールのプロパティにリンクします。|
|[DDP_LBIndex](#ddp_lbindex)|リスト ボックス内の選択した文字列のインデックスをコントロールのプロパティにリンクします。|
|[DDP_LBString](#ddp_lbstring)|リスト ボックス内の選択した文字列をコントロールのプロパティにリンクします。 選択した文字列は、プロパティの値と同じ文字で始めることができますが、完全に一致する必要はありません。|
|[DDP_LBStringExact](#ddp_lbstringexact)|リスト ボックス内の選択した文字列をコントロールのプロパティにリンクします。 選択した文字列とプロパティの文字列値は、正確に一致する必要があります。|
|[DDP_PostProcessing](#ddp_postprocessing)|コントロールからのプロパティ値の転送を完了します。|
|[DDP_Radio](#ddp_radio)|コントロールのプロパティ ページのオプション ボタン グループをコントロールのプロパティにリンクします。|
|[DDP_Text](#ddp_text)|コントロールのプロパティ ページ内のコントロールをコントロールのプロパティにリンクします。 この関数は **、double** **、short**、BSTR、long などのさまざまな種類の**long**プロパティを処理します。|

関数とプロパティ ページ`DoDataExchange`の詳細については、「 [ActiveX コントロール : プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)」を参照してください。

OLE コントロールのプロパティ ページを作成および管理するために使用するマクロの一覧を次に示します。

### <a name="property-pages"></a>[プロパティ ページ]

|||
|-|-|
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|プロパティ ページ ID のリストを開始します。|
|[END_PROPPAGEIDS](#end_proppageids)|プロパティ ページ ID のリストを終了します。|
|[PROPPAGEID](#proppageid)|コントロール クラスのプロパティ ページを宣言します。|

## <a name="ddp_cbindex"></a><a name="ddp_cbindex"></a>DDP_CBIndex

プロパティ ページのプロパティ ページの`DoDataExchange`コンボ ボックス内の現在の選択範囲のインデックスと整数プロパティの値を同期するには、プロパティ ページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
指定されたコントロール プロパティに関連付けられているコンボ ボックス コントロールのリソース*ID*です。

*メンバー*<br/>
*id*で指定されたプロパティ ページ コントロールと、指定されたプロパティに関連付けられているメンバー変数*pszPropName*。

*名前を変更します。*<br/>
*id*で指定されたコンボ ボックス コントロールと交換するコントロール プロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する`DDX_CBIndex`関数呼び出しの前に呼び出す必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_cbstring"></a><a name="ddp_cbstring"></a>DDP_CBString

プロパティ ページの`DoDataExchange`コンボ ボックスで現在選択されている文字列プロパティの値とを同期するには、プロパティ ページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_CBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
指定されたコントロール プロパティに関連付けられているコンボ ボックス コントロールのリソース*ID*です。

*メンバー*<br/>
*id*で指定されたプロパティ ページ コントロールと、指定されたプロパティに関連付けられているメンバー変数*pszPropName*。

*名前を変更します。*<br/>
*id*で指定されたコンボ ボックス文字列と交換されるコントロール プロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する`DDX_CBString`関数呼び出しの前に呼び出す必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_cbstringexact"></a><a name="ddp_cbstringexact"></a>DDP_CBStringExact

プロパティ ページのコンボ ボックスで現在`DoDataExchange`の選択項目と完全に一致する文字列プロパティの値を同期するには、プロパティ ページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
指定されたコントロール プロパティに関連付けられているコンボ ボックス コントロールのリソース*ID*です。

*メンバー*<br/>
*id*で指定されたプロパティ ページ コントロールと、指定されたプロパティに関連付けられているメンバー変数*pszPropName*。

*名前を変更します。*<br/>
*id*で指定されたコンボ ボックス文字列と交換されるコントロール プロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する`DDX_CBStringExact`関数呼び出しの前に呼び出す必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_check"></a><a name="ddp_check"></a>DDP_Check

プロパティの値を関連付けられたプロパティ`DoDataExchange`ページのチェック ボックス コントロールと同期するには、プロパティ ページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_Check(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
*pszPropName*で指定されたコントロール プロパティに関連付けられているチェック ボックス コントロールのリソース ID。

*メンバー*<br/>
*id*で指定されたプロパティ ページ コントロールと、指定されたプロパティに関連付けられているメンバー変数*pszPropName*。

*名前を変更します。*<br/>
*id*で指定されたチェック ボックス コントロールと交換されるコントロール プロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する`DDX_Check`関数呼び出しの前に呼び出す必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_lbindex"></a><a name="ddp_lbindex"></a>DDP_LBIndex

プロパティ ページのリスト ボックス内の`DoDataExchange`現在の選択範囲のインデックスと整数プロパティの値を同期するには、プロパティ ページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
指定されたコントロール プロパティに関連付けられているリスト ボックス コントロールのリソース*ID*です。

*メンバー*<br/>
*id*で指定されたプロパティ ページ コントロールと、指定されたプロパティに関連付けられているメンバー変数*pszPropName*。

*名前を変更します。*<br/>
*id*で指定されたリスト ボックス文字列と交換されるコントロール プロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する`DDX_LBIndex`関数呼び出しの前に呼び出す必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_lbstring"></a><a name="ddp_lbstring"></a>DDP_LBString

プロパティ ページの`DoDataExchange`リスト ボックスで現在選択されている文字列プロパティの値と同期するには、プロパティ ページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_LBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
指定されたコントロール プロパティに関連付けられているリスト ボックス コントロールのリソース*ID*です。

*メンバー*<br/>
*id*で指定されたプロパティ ページ コントロールと、指定されたプロパティに関連付けられているメンバー変数*pszPropName*。

*名前を変更します。*<br/>
*id*で指定されたリスト ボックス文字列と交換されるコントロール プロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する`DDX_LBString`関数呼び出しの前に呼び出す必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_lbstringexact"></a><a name="ddp_lbstringexact"></a>DDP_LBStringExact

プロパティ ページのリスト ボックスの現在`DoDataExchange`の選択と完全に一致する文字列プロパティの値を同期するには、プロパティ ページの関数でこの関数を呼び出します。

```cpp
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
指定されたコントロール プロパティに関連付けられているリスト ボックス コントロールのリソース*ID*です。

*メンバー*<br/>
*id*で指定されたプロパティ ページ コントロールと、指定されたプロパティに関連付けられているメンバー変数*pszPropName*。

*名前を変更します。*<br/>
*id*で指定されたリスト ボックス文字列と交換されるコントロール プロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する`DDX_LBStringExact`関数呼び出しの前に呼び出す必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_postprocessing"></a><a name="ddp_postprocessing"></a>DDP_PostProcessing

プロパティページの`DoDataExchange`関数でこの関数を呼び出して、プロパティ値を保存するときにプロパティ ページからコントロールへのプロパティ値の転送を完了します。

```cpp
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

### <a name="remarks"></a>解説

この関数は、すべてのデータ交換関数が完了した後に呼び出す必要があります。 次に例を示します。

[!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_radio"></a><a name="ddp_radio"></a>DDP_Radio

コントロールの`DoPropExchange`関数でこの関数を呼び出して、プロパティの値を関連付けられたプロパティ ページのオプション ボタン コントロールと同期させます。

```cpp
void AFXAPI DDP_Radio(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
指定されたコントロール プロパティに関連付けられているオプション ボタン コントロールのリソース*ID*です。

*メンバー*<br/>
*id*で指定されたプロパティ ページ コントロールと、指定されたプロパティに関連付けられているメンバー変数*pszPropName*。

*名前を変更します。*<br/>
*id*で指定されたオプション ボタン コントロールと交換されるコントロール プロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する`DDX_Radio`関数呼び出しの前に呼び出す必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="ddp_text"></a><a name="ddp_text"></a>DDP_Text

コントロールの`DoDataExchange`関数でこの関数を呼び出して、プロパティの値を関連付けられたプロパティ ページ コントロールと同期させます。

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

*Pdx*<br/>
`CDataExchange`オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。

*id*<br/>
指定されたコントロール プロパティに関連付けられているコントロールのリソース*ID*です。

*メンバー*<br/>
*id*で指定されたプロパティ ページ コントロールと、指定されたプロパティに関連付けられているメンバー変数*pszPropName*。

*名前を変更します。*<br/>
*id*で指定されたコントロールと交換するコントロール プロパティのプロパティ名。

### <a name="remarks"></a>解説

この関数は、対応する`DDX_Text`関数呼び出しの前に呼び出す必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="begin_proppageids"></a><a name="begin_proppageids"></a>BEGIN_PROPPAGEIDS

コントロールのプロパティ ページ ID の一覧の定義を開始します。

```
BEGIN_PROPPAGEIDS(class_name,  count)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
プロパティ ページを指定するコントロール クラスの名前。

*count*<br/>
コントロール クラスで使用されるプロパティ ページの数。

### <a name="remarks"></a>解説

クラスのメンバー関数を定義する実装 (.cpp) ファイルで、BEGIN_PROPPAGEIDS マクロを使用してプロパティ ページの一覧を開始し、各プロパティ ページのマクロ エントリを追加し、END_PROPPAGEIDS マクロを使用してプロパティ ページの一覧を完成させます。

プロパティ ページの詳細については、「 [ActiveX コントロール : プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="end_proppageids"></a><a name="end_proppageids"></a>END_PROPPAGEIDS

プロパティ ページ ID リストの定義を終了します。

```
END_PROPPAGEIDS(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
プロパティ ページを所有するコントロール クラスの名前。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="proppageid"></a><a name="proppageid"></a>プロップページID

OLE コントロールで使用するプロパティ ページを追加します。

```
PROPPAGEID(clsid)
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
プロパティ ページの一意のクラス ID。

### <a name="remarks"></a>解説

すべての PROPPAGEID マクロは、コントロールの実装ファイル内のBEGIN_PROPPAGEIDSとEND_PROPPAGEIDSマクロの間に配置する必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxctl.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
