---
description: '詳細情報: COleUpdateDialog クラス'
title: COleUpdateDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
ms.openlocfilehash: e7f1d1e7f67fd80fd7042e53a7ccdee46dc6531f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226598"
---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog クラス

OLE の [リンクの編集] ダイアログ ボックスを使って、ドキュメント内の既存のリンク オブジェクトや埋め込みオブジェクトの更新のみを行います。これは、OLE の [リンクの編集] ダイアログ ボックスの特別な使い方です。

## <a name="syntax"></a>構文

```
class COleUpdateDialog : public COleLinksDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|`COleUpdateDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleUpdateDialog::D oModal](#domodal)|更新モードで [ **リンクの編集** ] ダイアログボックスを表示します。|

## <a name="remarks"></a>解説

OLE 固有のダイアログボックスの詳細については、 [ole の記事のダイアログボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

[COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

`COleUpdateDialog`

## <a name="requirements"></a>要件

**ヘッダー:** afxodlgs

## <a name="coleupdatedialogcoleupdatedialog"></a><a name="coleupdatedialog"></a> COleUpdateDialog::COleUpdateDialog

`COleUpdateDialog` オブジェクトを構築します。

```
explicit COleUpdateDialog(
    COleDocument* pDoc,
    BOOL bUpdateLinks = TRUE,
    BOOL bUpdateEmbeddings = FALSE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
更新が必要な可能性のあるリンクを含むドキュメントを指します。

*bUpdateLinks*<br/>
リンクオブジェクトを更新するかどうかを示すフラグです。

*bUpdateEmbeddings 込み*<br/>
埋め込みオブジェクトを更新するかどうかを決定するフラグ。

*pParentWnd*<br/>
ダイアログオブジェクトが属する親またはオーナーウィンドウオブジェクト (型) を指し `CWnd` ます。 NULL の場合は、ダイアログボックスの親ウィンドウがメインアプリケーションウィンドウに設定されます。

### <a name="remarks"></a>解説

この関数は、オブジェクトのみを構築 `COleUpdateDialog` します。 ダイアログボックスを表示するには、 [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)を呼び出します。 このクラスは、 `COleLinksDialog` 既存のリンクまたは埋め込まれた項目のみを更新する場合に、の代わりに使用する必要があります。

## <a name="coleupdatedialogdomodal"></a><a name="domodal"></a> COleUpdateDialog::D oModal

更新モードで [リンクの編集] ダイアログボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログボックスが正常に返された場合はです。

- 現在のドキュメント内のリンクされた項目または埋め込み項目が更新を必要としない場合は IDCANCEL。

- エラーが発生した場合は IDABORT。 IDABORT が返された場合は、 [COleDialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) メンバー関数を呼び出して、発生したエラーの種類に関する詳細情報を取得します。 考えられるエラーの一覧については、Windows SDK の [Oleuieditlinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) 関数に関するページを参照してください。

### <a name="remarks"></a>解説

ユーザーが [キャンセル] ボタンを選択しない限り、すべてのリンクや埋め込みが更新されます。

## <a name="see-also"></a>関連項目

[MFC サンプル OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleLinksDialog クラス](../../mfc/reference/colelinksdialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleLinksDialog クラス](../../mfc/reference/colelinksdialog-class.md)
