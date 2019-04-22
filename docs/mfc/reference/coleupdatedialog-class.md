---
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
ms.openlocfilehash: b8e580130b025f07b8f85a624b7f5a224a00e49e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58771109"
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
|[COleUpdateDialog::DoModal](#domodal)|表示、**リンクの編集**更新モードでのダイアログ ボックス。|

## <a name="remarks"></a>Remarks

OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

[COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

`COleUpdateDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

##  <a name="coleupdatedialog"></a>  COleUpdateDialog::COleUpdateDialog

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
更新が必要なリンクを含むドキュメントを指します。

*bUpdateLinks*<br/>
リンク オブジェクトを更新するかどうかを決定するフラグ。

*bUpdateEmbeddings*<br/>
埋め込みオブジェクトを更新するかどうかを決定するフラグ。

*pParentWnd*<br/>
親またはオーナー ウィンドウのオブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ ボックスの親ウィンドウは、メイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>Remarks

この関数の作成のみを`COleUpdateDialog`オブジェクト。 ダイアログ ボックスを表示するには、呼び出す[DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)します。 このクラスは、の代わりに使用する必要があります`COleLinksDialog`リンクまたは埋め込みアイテムの既存ののみを更新する場合。

##  <a name="domodal"></a>  COleUpdateDialog::DoModal

モードを更新するリンクの編集 ダイアログ ボックスが表示されます。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログ ボックスが正常に返された場合。

- 現在のドキュメントでリンクまたは埋め込み項目を更新する必要がある場合は IDCANCEL。

- IDABORT 場合は、エラーが発生しました。 IDABORT が返される場合、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)発生したエラーの種類に関する詳細を取得します。 考えられるエラーの一覧については、次を参照してください。、[される](/windows/desktop/api/oledlg/nf-oledlg-oleuieditlinksa)Windows SDK 内の関数。

### <a name="remarks"></a>Remarks

ユーザーが [キャンセル] ボタンを選択しない限り、すべてのリンクや埋め込みが更新されます。

## <a name="see-also"></a>関連項目

[MFC サンプルの OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleLinksDialog クラス](../../mfc/reference/colelinksdialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleLinksDialog クラス](../../mfc/reference/colelinksdialog-class.md)
