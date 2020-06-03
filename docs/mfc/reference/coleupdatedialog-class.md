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
ms.openlocfilehash: 9e2c7a8d79ebf5e6483a06354b280e474d7b8e61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374838"
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
|[ダイアログ::コレク更新ダイアログ](#coleupdatedialog)|`COleUpdateDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス::Do モーダル](#domodal)|更新モードで **[リンクの編集**] ダイアログ ボックスを表示します。|

## <a name="remarks"></a>解説

OLE 固有のダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

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

## <a name="coleupdatedialogcoleupdatedialog"></a><a name="coleupdatedialog"></a>ダイアログ::コレク更新ダイアログ

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
更新が必要なリンクを含むドキュメントへのポイント。

*をクリックします。*<br/>
リンク オブジェクトを更新するかどうかを決定するフラグ。

*b更新埋め込み*<br/>
埋め込みオブジェクトを更新するかどうかを決定するフラグ。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する (型`CWnd`) の親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクトへのポインター。 NULL の場合、ダイアログ ボックスの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

この関数は`COleUpdateDialog`オブジェクトのみを構築します。 ダイアログ ボックスを表示するには[、DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)を呼び出します。 既存のリンクアイテムまたは埋め`COleLinksDialog`込みアイテムのみを更新する場合ではなく、このクラスを使用する必要があります。

## <a name="coleupdatedialogdomodal"></a><a name="domodal"></a>ダイアログ ボックス::Do モーダル

更新モードで [リンクの編集] ダイアログ ボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値:

- ダイアログ ボックスが正常に返された場合は IDOK。

- 現在のドキュメント内のリンクアイテムまたは埋め込みアイテムのどれも更新する必要がない場合は、IDCANCEL を指定します。

- エラーが発生した場合は、IDABORT を実行します。 IDABORT が返された場合は、発生したエラーの種類に関する詳細情報を取得するのには[、COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)メンバー関数を呼び出します。 考えられるエラーの一覧については、Windows SDK の[「OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw)関数」を参照してください。

### <a name="remarks"></a>解説

ユーザーが [キャンセル] ボタンを選択しない限り、すべてのリンクや埋め込みが更新されます。

## <a name="see-also"></a>関連項目

[サンプル O クライアント](../../overview/visual-cpp-samples.md)<br/>
[COleLinksDialog クラス](../../mfc/reference/colelinksdialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleLinksDialog クラス](../../mfc/reference/colelinksdialog-class.md)
