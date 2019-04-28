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
ms.openlocfilehash: c5069bc63d61016e6f3c2f983de23901b9f35814
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224437"
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
|[COleLinksDialog::DoModal](#domodal)|OLE の [リンクの編集] ダイアログ ボックスが表示されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleLinksDialog::m_el](#m_el)|ダイアログ ボックスの動作が制御される型の構造体。|

## <a name="remarks"></a>Remarks

クラスのオブジェクトを作成`COleLinksDialog`をこのダイアログ ボックスを呼び出す場合します。 後に、`COleLinksDialog`オブジェクトが構築された、使用することができます、[各](#m_el)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_el`型される構造です。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。

> [!NOTE]
>  アプリケーション コンテナーのウィザードで生成されたコードでは、このクラスを使用します。

詳細については、次を参照してください。、[される](/windows/desktop/api/oledlg/ns-oledlg-tagoleuieditlinksa)Windows SDK の構造体。

OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。

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

##  <a name="domodal"></a>  COleLinksDialog::DoModal

OLE の [リンクの編集] ダイアログ ボックスが表示されます。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログ ボックスが正常に表示されている場合。

- ユーザーには、ダイアログ ボックスが取り消された場合は IDCANCEL。

- IDABORT 場合は、エラーが発生しました。 IDABORT が返される場合、`COleDialog::GetLastError`発生したエラーの種類に関する詳細を取得します。 考えられるエラーの一覧については、次を参照してください。、[される](/windows/desktop/api/oledlg/nf-oledlg-oleuieditlinksa)Windows SDK 内の関数。

### <a name="remarks"></a>Remarks

メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、[各](#m_el)構造、行う必要があります、呼び出す前に`DoModal`はダイアログ オブジェクトを構築します。

##  <a name="colelinksdialog"></a>  COleLinksDialog::COleLinksDialog

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
編集するリンクを含む OLE ドキュメントへのポインター。

*pView*<br/>
上の現在のビューを指す*pDoc*します。

*dwFlags*<br/>
作成フラグには、0 またはダイアログ ボックスが表示されたら、[ヘルプ] ボタンが表示されるかどうかを指定するのいずれかが含まれています。

*pParentWnd*<br/>
親またはオーナー ウィンドウのオブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ ボックスの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。

### <a name="remarks"></a>Remarks

この関数の作成のみを`COleLinksDialog`オブジェクト。 ダイアログ ボックスを表示するには[DoModal](#domodal)関数。

##  <a name="m_el"></a>  COleLinksDialog::m_el

リンクの編集 ダイアログ ボックスの動作を制御するために使用される型の構造体。

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>Remarks

この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。

詳細については、次を参照してください。、[される](/windows/desktop/api/oledlg/ns-oledlg-tagoleuieditlinksa)Windows SDK の構造体。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
