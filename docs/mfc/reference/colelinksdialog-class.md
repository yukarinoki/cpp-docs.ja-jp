---
description: '詳細情報: COleLinksDialog クラス'
title: COleLinksDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
ms.openlocfilehash: 036fc2b97fe4ad529e87c3573e280c99ac157848
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226923"
---
# <a name="colelinksdialog-class"></a>COleLinksDialog クラス

OLE の [リンクの編集] ダイアログ ボックスに使用します。

## <a name="syntax"></a>構文

```
class COleLinksDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|`COleLinksDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleLinksDialog::D oModal](#domodal)|OLE の [リンクの編集] ダイアログボックスを表示します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleLinksDialog:: m_el](#m_el)|ダイアログボックスの動作を制御する OLEUIEDITLINKS 型の構造体。|

## <a name="remarks"></a>解説

このダイアログボックスを呼び出す必要がある場合は、クラスのオブジェクトを作成 `COleLinksDialog` します。 `COleLinksDialog`オブジェクトが構築されたら、 [m_el](#m_el)構造体を使用して、ダイアログボックス内のコントロールの値または状態を初期化できます。 `m_el`構造体の型は OLEUIEDITLINKS です。 このダイアログクラスの使用方法の詳細については、「 [DoModal](#domodal) メンバー関数」を参照してください。

> [!NOTE]
> アプリケーションウィザードで生成されたコンテナーコードは、このクラスを使用します。

詳細については、Windows SDK の [Oleuieditlinks](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) 構造体を参照してください。

OLE 固有のダイアログボックスの詳細については、 [ole の記事のダイアログボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>要件

**ヘッダー:** afxodlgs

## <a name="colelinksdialogdomodal"></a><a name="domodal"></a> COleLinksDialog::D oModal

OLE の [リンクの編集] ダイアログボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログボックスが正常に表示された場合は。

- ユーザーがダイアログボックスをキャンセルした場合は IDCANCEL。

- エラーが発生した場合は IDABORT。 IDABORT が返された場合は、メンバー関数を呼び出して、発生した `COleDialog::GetLastError` エラーの種類に関する詳細情報を取得します。 考えられるエラーの一覧については、Windows SDK の [Oleuieditlinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) 関数に関するページを参照してください。

### <a name="remarks"></a>解説

[M_el](#m_el)構造体のメンバーを設定してさまざまなダイアログボックスコントロールを初期化する場合は、を呼び出す前に `DoModal` 、ダイアログオブジェクトが構築された後に実行する必要があります。

## <a name="colelinksdialogcolelinksdialog"></a><a name="colelinksdialog"></a> COleLinksDialog::COleLinksDialog

`COleLinksDialog` オブジェクトを構築します。

```
COleLinksDialog (
    COleDocument* pDoc,
    CView* pView,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
編集するリンクが含まれている OLE ドキュメントを指します。

*pView*<br/>
*Pdoc* の現在のビューを指します。

*dwFlags*<br/>
作成フラグ。ダイアログボックスが表示されたときに [ヘルプ] ボタンを表示するかどうかを指定するために、0または ELF_SHOWHELP が含まれています。

*pParentWnd*<br/>
ダイアログオブジェクトが属する親またはオーナーウィンドウオブジェクト (型) を指し `CWnd` ます。 NULL の場合は、ダイアログボックスの親ウィンドウがメインアプリケーションウィンドウに設定されます。

### <a name="remarks"></a>解説

この関数は、オブジェクトのみを構築 `COleLinksDialog` します。 ダイアログボックスを表示するには、 [DoModal](#domodal) 関数を呼び出します。

## <a name="colelinksdialogm_el"></a><a name="m_el"></a> COleLinksDialog:: m_el

[リンクの編集] ダイアログボックスの動作を制御するために使用される OLEUIEDITLINKS 型の構造体。

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>解説

この構造体のメンバーは、直接またはメンバー関数を使用して変更できます。

詳細については、Windows SDK の [Oleuieditlinks](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) 構造体を参照してください。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
