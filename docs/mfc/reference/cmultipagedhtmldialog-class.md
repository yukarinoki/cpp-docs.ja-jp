---
title: CMultiPageDHtmlDialog クラス
ms.date: 03/27/2019
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
ms.openlocfilehash: 89e4830c3b5c6cb663ca2d2935adaaae3f356958
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319665"
---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog クラス

マルチページ ダイアログは、複数の HTML ページを順番に表示し、各ページのイベントを処理します。

## <a name="syntax"></a>構文

```
class CMultiPageDHtmlDialog : public CDHtmlDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログボックス:::ページドHtmlダイアログ](#cmultipagedhtmldialog)|マルチページ (ウィザード スタイルの) DHTML ダイアログ オブジェクトを構築します。|
|[ダイアログボックス::~CMultiページドHtmlダイアログ](#_dtorcmultipagedhtmldialog)|複数ページの DHTML ダイアログ オブジェクトを破棄します。|

## <a name="remarks"></a>解説

これを行うためのメカニズムは、各ページの埋め込みイベント マップを含む[DHTML と URL](dhtml-event-maps.md)イベント マップです。

## <a name="example"></a>例

この複数ページのダイアログでは、ウィザードのような単純な機能を定義する 3 つの HTML リソースを想定しています。 最初のページには **[次へ**]ボタン、2 番目の[**前へ**]ボタンと **[次へ**]ボタン、3 番目の[**前**へ]ボタンがあります。 ボタンの 1 つが押されると、ハンドラー関数が[CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource)を呼び出して、適切な新しいページを読み込みます。

クラス宣言の関連部分 (CMyMultiPageDlg.h)

[!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]

クラス実装の関連部分 (CMyMultipageDlg.cpp で):

[!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

`CMultiPageDHtmlDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdhtml.h

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="cmultipagedhtmldialog"></a>ダイアログボックス:::ページドHtmlダイアログ

マルチページ (ウィザード スタイルの) DHTML ダイアログ オブジェクトを構築します。

```
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID = NULL,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog();
```

### <a name="parameters"></a>パラメーター

*テンプレート名*<br/>
ダイアログ ボックス テンプレート リソースの名前である null で終わる文字列。

*を返します。*<br/>
HTML リソースの名前である null で終わる文字列。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクト ( [CWnd](../../mfc/reference/cwnd-class.md)型 ) へのポインター。 NULL の場合、ダイアログ オブジェクトの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

*テンプレート*<br/>
ダイアログ ボックス テンプレート リソースの ID 番号を格納します。

*を返します。*<br/>
HTML リソースの ID 番号を格納します。

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="_dtorcmultipagedhtmldialog"></a>ダイアログボックス::~CMultiページドHtmlダイアログ

複数ページの DHTML ダイアログ オブジェクトを破棄します。

```
virtual ~CMultiPageDHtmlDialog();
```

## <a name="see-also"></a>関連項目

[CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)
