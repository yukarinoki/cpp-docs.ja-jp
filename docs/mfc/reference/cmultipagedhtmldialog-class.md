---
description: '詳細情報: CMultiPageDHtmlDialog クラス'
title: CMultiPageDHtmlDialog クラス
ms.date: 03/27/2019
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
ms.openlocfilehash: 1f7f8c2081687c71a98e427bb5396cfa47a73deb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331524"
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
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|マルチページ (ウィザードスタイル) DHTML ダイアログオブジェクトを構築します。|
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#_dtorcmultipagedhtmldialog)|マルチページ DHTML ダイアログオブジェクトを破棄します。|

## <a name="remarks"></a>解説

これを行うためのメカニズムは、各ページの埋め込みイベントマップを含む [DHTML および URL イベントマップ](dhtml-event-maps.md)です。

## <a name="example"></a>例

このマルチページダイアログでは、ウィザードに似たシンプルな機能を定義する3つの HTML リソースが想定されています。 最初のページには、 **[次へ** ] ボタン、2番目の [ **前** へ] ボタン、 **[次へ** ] ボタン、3番目の [ **前** へ] ボタンがあります。 いずれかのボタンが押されると、ハンドラー関数は [CDHtmlDialog:: LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) を呼び出して、適切な新しいページを読み込みます。

クラス宣言の関連部分 (CMyMultiPageDlg 内):

[!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]

クラス実装の関連部分 (CMyMultipageDlg 内):

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

## <a name="requirements"></a>要件

**ヘッダー:** afxdhtml

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="cmultipagedhtmldialog"></a> CMultiPageDHtmlDialog::CMultiPageDHtmlDialog

マルチページ (ウィザードスタイル) DHTML ダイアログオブジェクトを構築します。

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

*lpszTemplateName*<br/>
ダイアログボックステンプレートリソースの名前である null で終わる文字列。

*szHtmlResID*<br/>
HTML リソースの名前を表す null で終わる文字列。

*pParentWnd*<br/>
ダイアログオブジェクトが属する親またはオーナーウィンドウオブジェクト ( [CWnd](../../mfc/reference/cwnd-class.md)型) へのポインター。 NULL の場合は、ダイアログオブジェクトの親ウィンドウがメインアプリケーションウィンドウに設定されます。

*nIDTemplate*<br/>
ダイアログボックステンプレートリソースの ID 番号を格納します。

*nHtmlResID*<br/>
HTML リソースの ID 番号を格納します。

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="_dtorcmultipagedhtmldialog"></a> CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog

マルチページ DHTML ダイアログオブジェクトを破棄します。

```
virtual ~CMultiPageDHtmlDialog();
```

## <a name="see-also"></a>関連項目

[CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)
