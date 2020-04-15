---
title: DDX_DHtml Helper マクロ
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
ms.openlocfilehash: f78a923a498713867c13ccc88e3e30c1f0a23885
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365865"
---
# <a name="ddx_dhtml-helper-macros"></a>DDX_DHtml Helper マクロ

DDX_DHtml ヘルパー マクロを使用すると、HTML ページ上のコントロールの一般的に使用されるプロパティに簡単にアクセスできます。

### <a name="data-exchange-macros"></a>データ交換マクロ

|||
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|選択したコントロールから Value プロパティを設定または取得します。|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|現在の要素の開始タグと終了タグの間のテキストを設定または取得します。|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|現在の要素の開始タグと終了タグの間の HTML を設定または取得します。|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|リンク先 URL またはアンカー ポイントを設定または取得します。|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|ターゲット ウィンドウまたはフレームを設定または取得します。|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|ドキュメント内のイメージまたはビデオ クリップの名前を設定または取得します。|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|関連付けられたフレームの URL を設定または取得します。|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|関連付けられたフレームの URL を設定または取得します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdhtml.h

## <a name="ddx_dhtml_anchor_href"></a><a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href

リンク先 URL またはアンカー ポイントを設定または取得します。

```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*Dx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*Var*<br/>
交換される値。

## <a name="remarks"></a>解説

このマクロは、DISPID_IHTMLANCHORELEMENT_HREF ディスパッチ ID を使用して[、CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)関数を呼び出します。

## <a name="ddx_dhtml_anchor_target"></a><a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target

ターゲット ウィンドウまたはフレームを設定または取得します。

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*Dx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*Var*<br/>
交換される値。

## <a name="remarks"></a>解説

このマクロは、DISPID_IHTMLANCHORELEMENT_TARGET ディスパッチ ID を使用して[、CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)関数を呼び出します。

## <a name="ddx_dhtml_elementinnerhtml"></a><a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml

現在の要素の開始タグと終了タグの間の HTML を設定または取得します。

```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*Dx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*Var*<br/>
交換される値。

## <a name="remarks"></a>解説

このマクロは、DISPID_IHTMLELEMENT_INNERHTMLディスパッチ ID を使用して[、CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)関数を呼び出します。

## <a name="ddx_dhtml_elementinnertext"></a><a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText

現在の要素の開始タグと終了タグの間のテキストを設定または取得します。

```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*Dx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*Var*<br/>
交換される値。

## <a name="remarks"></a>解説

このマクロは、DISPID_IHTMLELEMENT_INNERTEXT ディスパッチ ID を使用して[、CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)関数を呼び出します。

## <a name="ddx_dhtml_elementvalue"></a><a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue

選択したコントロールから Value プロパティを設定または取得します。

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>パラメーター

*Dx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*Var*<br/>
交換される値。 *値*を参照してください[:D。](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)

## <a name="remarks"></a>解説

このマクロは、Value プロパティを持つコントロールで実行する場合にのみ成功します。 Value プロパティを持つコントロールには、エディット ボックス、リスト ボックス、コンボ ボックスなどがあります。

このマクロは、DISPID_A_VALUE ディスパッチ ID を使用して[、CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)関数を呼び出します。

## <a name="ddx_dhtml_frame_src"></a><a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src

関連付けられたフレームの URL を設定または取得します。

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*Dx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*Var*<br/>
交換される値。

## <a name="remarks"></a>解説

このマクロは、DISPID_IHTMLFRAMEBASE_SRC ディスパッチ ID を使用して[、CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)関数を呼び出します。

## <a name="ddx_dhtml_iframe_src"></a><a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src

関連付けられたフレームの URL を設定または取得します。

```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*Dx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*Var*<br/>
交換される値。

## <a name="remarks"></a>解説

このマクロは、DISPID_IHTMLFRAMEBASE_SRC ディスパッチ ID を使用して[、CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)関数を呼び出します。

## <a name="ddx_dhtml_img_src"></a><a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src

ドキュメント内のイメージまたはビデオ クリップの名前を取得または取得します。

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>パラメーター

*Dx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*name*<br/>
HTML コントロールの ID パラメーターに指定した値。

*Var*<br/>
交換される値。

## <a name="remarks"></a>解説

DDX_DHtml_Img_Srcマクロを使用して IMAGE 要素の src プロパティを取得すると、Internet Explorer イメージ オブジェクトはイメージ ソースの完全エスケープ URL を返します。 たとえば、DDX_DHtml_Img_Srcマクロを使用して IMAGE 要素の src プロパティを文字列 "いくつかの興味深い画像" に設定すると、そのプロパティを取得すると、文字列 "res://d:\myapplication\myapp.exe/%20面白い%20picture" という文字列が返されます。

このマクロは、DISPID_IHTMLIMGELEMENT_SRC ディスパッチ ID を使用して[、CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)関数を呼び出します。

## <a name="see-also"></a>関連項目

[CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)
