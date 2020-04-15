---
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
ms.openlocfilehash: f120678c822749c8f27c3c56c95fcdd54647aca3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374930"
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
|[ダイアログボックス::コレクスリンクダイアログ](#colelinksdialog)|`COleLinksDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス:Do モーダル](#domodal)|[OLE リンクの編集] ダイアログ ボックスを表示します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ::m_el](#m_el)|ダイアログ ボックスの動作を制御する OLEUIEDITLINKS 型の構造体。|

## <a name="remarks"></a>解説

このダイアログ ボックスを`COleLinksDialog`呼び出す場合は、クラスのオブジェクトを作成します。 オブジェクトを`COleLinksDialog`構築した後[、m_el](#m_el)構造を使用して、ダイアログ ボックス内のコントロールの値または状態を初期化できます。 構造体`m_el`の型は OLEUIEDIT リンクです。 このダイアログ クラスの使用方法の詳細については[、DoModal](#domodal)メンバー関数を参照してください。

> [!NOTE]
> アプリケーション ウィザードで生成されたコンテナー コードでは、このクラスを使用します。

詳細については、Windows SDK の[「OLEUIEDITLINKS」](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw)の構造を参照してください。

OLE 固有のダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

## <a name="colelinksdialogdomodal"></a><a name="domodal"></a>ダイアログ ボックス:Do モーダル

[OLE リンクの編集] ダイアログ ボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値:

- ダイアログ ボックスが正常に表示された場合は IDOK。

- ユーザーがダイアログ ボックスをキャンセルした場合は、IDCANCEL を指定します。

- エラーが発生した場合は、IDABORT を実行します。 IDABORT が返された場合は`COleDialog::GetLastError`、メンバー関数を呼び出して、発生したエラーの種類に関する詳細情報を取得します。 考えられるエラーの一覧については、Windows SDK の[「OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw)関数」を参照してください。

### <a name="remarks"></a>解説

[m_el](#m_el)構造体のメンバを設定してさまざまなダイアログ ボックス コントロールを初期化する場合は、ダイアログ オブジェクトを構築`DoModal`した後で呼び出す前に、この操作を行う必要があります。

## <a name="colelinksdialogcolelinksdialog"></a><a name="colelinksdialog"></a>ダイアログボックス::コレクスリンクダイアログ

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
編集するリンクを含む OLE ドキュメントへのリンク。

*pビュー*<br/>
*pDoc*上の現在のビューへのポイント

*dwFlags*<br/>
作成フラグは、ダイアログ ボックスが表示されたときに [ヘルプ] ボタンを表示するかどうかを指定する 0 またはELF_SHOWHELPを含みます。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する (型`CWnd`) の親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクトへのポインター。 NULL の場合、ダイアログ ボックスの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

この関数は`COleLinksDialog`オブジェクトのみを構築します。 ダイアログ ボックスを表示するには[、DoModal](#domodal)関数を呼び出します。

## <a name="colelinksdialogm_el"></a><a name="m_el"></a>ダイアログ::m_el

[リンクの編集] ダイアログ ボックスの動作を制御するために使用される OLEUIEDITLINKS 型の構造体。

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>解説

この構造体のメンバーは、直接またはメンバー関数を通じて変更できます。

詳細については、Windows SDK の[「OLEUIEDITLINKS」](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw)の構造を参照してください。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
