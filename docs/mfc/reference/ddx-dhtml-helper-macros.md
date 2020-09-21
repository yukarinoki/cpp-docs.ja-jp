---
title: DDX_DHtml ヘルパーマクロ
ms.date: 11/04/2016
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
helpviewer_keywords:
- macros [MFC], exchanging data with HMTL pages
- DDX macros [MFC]
- HTML pages [MFC], helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros [MFC], DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
ms.openlocfilehash: eeea85872422edcf421ba2fe254c8f03c093fe3c
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743452"
---
# <a name="ddx_dhtml-helper-macros"></a>DDX_DHtml ヘルパーマクロ

DDX_DHtml ヘルパーマクロを使用すると、HTML ページ上のコントロールの一般的に使用されるプロパティに簡単にアクセスできます。

### <a name="data-exchange-macros"></a>データ交換マクロ

|名前|説明|
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|選択したコントロールの値プロパティを設定または取得します。|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|現在の要素の開始タグと終了タグの間のテキストを設定または取得します。|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|現在の要素の開始タグと終了タグの間にある HTML を設定または取得します。|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|送信先 URL またはアンカーポイントを設定または取得します。|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|対象のウィンドウまたはフレームを設定または取得します。|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|ドキュメント内のイメージまたはビデオクリップの名前を設定または取得します。|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|関連付けられたフレームの URL を設定または取得します。|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|関連付けられたフレームの URL を設定または取得します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdhtml

## <a name="ddx_dhtml_anchor_href"></a><a name="ddx_dhtml_anchor_href"></a> DDX_DHtml_Anchor_Href

送信先 URL またはアンカーポイントを設定または取得します。

```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*var*<br/>
交換される値。

### <a name="remarks"></a>注釈

このマクロは、DISPID_IHTMLANCHORELEMENT_HREF ディスパッチ ID を使用して、 [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 関数を呼び出します。

## <a name="ddx_dhtml_anchor_target"></a><a name="ddx_dhtml_anchor_target"></a> DDX_DHtml_Anchor_Target

対象のウィンドウまたはフレームを設定または取得します。

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*var*<br/>
交換される値。

### <a name="remarks"></a>注釈

このマクロは、DISPID_IHTMLANCHORELEMENT_TARGET ディスパッチ ID を使用して、 [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 関数を呼び出します。

## <a name="ddx_dhtml_elementinnerhtml"></a><a name="ddx_dhtml_elementinnerhtml"></a> DDX_DHtml_ElementInnerHtml

現在の要素の開始タグと終了タグの間にある HTML を設定または取得します。

```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*var*<br/>
交換される値。

### <a name="remarks"></a>注釈

このマクロは、DISPID_IHTMLELEMENT_INNERHTML ディスパッチ ID を使用して、 [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 関数を呼び出します。

## <a name="ddx_dhtml_elementinnertext"></a><a name="ddx_dhtml_elementinnertext"></a> DDX_DHtml_ElementInnerText

現在の要素の開始タグと終了タグの間のテキストを設定または取得します。

```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*var*<br/>
交換される値。

### <a name="remarks"></a>注釈

このマクロは、DISPID_IHTMLELEMENT_INNERTEXT ディスパッチ ID を使用して、 [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 関数を呼び出します。

## <a name="ddx_dhtml_elementvalue"></a><a name="ddx_dhtml_elementvalue"></a> DDX_DHtml_ElementValue

選択したコントロールの値プロパティを設定または取得します。

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>パラメーター

*dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*var*<br/>
交換される値。 「 [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)」の*値*を参照してください。

### <a name="remarks"></a>注釈

このマクロは、Value プロパティを持つコントロールに対して実行した場合にのみ成功します。 値プロパティを持つコントロールには、エディットボックス、リストボックス、およびコンボボックスが含まれます。

このマクロは、DISPID_A_VALUE ディスパッチ ID を使用して、 [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 関数を呼び出します。

## <a name="ddx_dhtml_frame_src"></a><a name="ddx_dhtml_frame_src"></a> DDX_DHtml_Frame_Src

関連付けられたフレームの URL を設定または取得します。

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*var*<br/>
交換される値。

### <a name="remarks"></a>注釈

このマクロは、DISPID_IHTMLFRAMEBASE_SRC ディスパッチ ID を使用して、 [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 関数を呼び出します。

## <a name="ddx_dhtml_iframe_src"></a><a name="ddx_dhtml_iframe_src"></a> DDX_DHtml_IFrame_Src

関連付けられたフレームの URL を設定または取得します。

```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*var*<br/>
交換される値。

### <a name="remarks"></a>注釈

このマクロは、DISPID_IHTMLFRAMEBASE_SRC ディスパッチ ID を使用して、 [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 関数を呼び出します。

## <a name="ddx_dhtml_img_src"></a><a name="ddx_dhtml_img_src"></a> DDX_DHtml_Img_Src

ドキュメント内のイメージまたはビデオクリップの名前を取得または取得します。

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*dx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトへのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*var*<br/>
交換される値。

### <a name="remarks"></a>注釈

DDX_DHtml_Img_Src マクロを使用してイメージ要素の Src プロパティを取得すると、Internet Explorer のイメージオブジェクトは、イメージソースの完全にエスケープされた URL を返します。 たとえば、DDX_DHtml_Img_Src マクロを使用して IMAGE 要素の Src プロパティを "some おもしろい picture" という文字列に設定した場合、Internet Explorer は "res://d:\myapplication\myapp.exe/some%20interesting%20picture." という文字列を返します。

このマクロは、DISPID_IHTMLIMGELEMENT_SRC ディスパッチ ID を使用して、 [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) 関数を呼び出します。

## <a name="see-also"></a>関連項目

[CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)
