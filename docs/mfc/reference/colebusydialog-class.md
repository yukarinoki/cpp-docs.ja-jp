---
title: COleBusyDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
ms.openlocfilehash: 5be42463c08cacd83de84900fb4d98771774e897
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364239"
---
# <a name="colebusydialog-class"></a>COleBusyDialog クラス

OLE の [サーバーが応答しません] ダイアログ ボックスまたは [サーバーを使用できません] ダイアログ ボックスに使用されます。

## <a name="syntax"></a>構文

```
class COleBusyDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ::コレクビジーダイアログ](#colebusydialog)|`COleBusyDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス::Do モーダル](#domodal)|[OLE サーバーのビジー状態] ダイアログ ボックスを表示します。|
|[ダイアログボックス::選択タイプ](#getselectiontype)|ダイアログ ボックスでの選択を決定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ::m_bz](#m_bz)|ダイアログ ボックスの動作を制御する OLEUIBUSY 型の構造体。|

## <a name="remarks"></a>解説

これらのダイアログ ボックスを`COleBusyDialog`呼び出す場合は、クラスのオブジェクトを作成します。 オブジェクトを`COleBusyDialog`構築した後[、m_bz](#m_bz)構造を使用して、ダイアログ ボックス内のコントロールの値または状態を初期化できます。 構造体`m_bz`の型は、OLEUIBUSY です。 このダイアログ クラスの使用方法の詳細については[、DoModal](#domodal)メンバー関数を参照してください。

> [!NOTE]
> アプリケーション ウィザードで生成されたコンテナー コードでは、このクラスを使用します。

詳細については、Windows SDK の[「OLEUIBUSY」](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw)の構造体を参照してください。

OLE 固有のダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleBusyDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

## <a name="colebusydialogcolebusydialog"></a><a name="colebusydialog"></a>ダイアログ::コレクビジーダイアログ

この関数は`COleBusyDialog`オブジェクトを構築するだけです。

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*タスクビジー*<br/>
ビジー状態のサーバー タスクへのハンドル。

*応答しない*<br/>
TRUE の場合は、[サーバービジー状態] ダイアログ ボックスではなく 、[応答なし] ダイアログ ボックスを呼び出します。 [応答なし] ダイアログ ボックスの表示方法は、[サーバービジー状態] ダイアログ ボックスの文言とは少し異なり、[キャンセル] ボタンは無効になっています。

*dwFlags*<br/>
作成フラグ。 ビットごとの OR 演算子と組み合わせて、次の値を 0 個以上含めることができます。

- BZ_DISABLECANCELBUTTON ダイアログ ボックスを呼び出すときに [キャンセル] ボタンを無効にします。

- BZ_DISABLESWITCHTOBUTTON ダイアログ ボックスを呼び出すときに [切り替え] ボタンを無効にします。

- BZ_DISABLERETRYBUTTON ダイアログ ボックスを呼び出すときに [再試行] ボタンを無効にします。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する (型`CWnd`) の親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクトへのポインター。 NULL の場合、ダイアログ オブジェクトの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

ダイアログ ボックスを表示するには[、DoModal](#domodal)を呼び出します。

詳細については、Windows SDK の[「OLEUIBUSY」](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw)の構造体を参照してください。

## <a name="colebusydialogdomodal"></a><a name="domodal"></a>ダイアログ ボックス::Do モーダル

[OLE サーバーがビジー状態] ダイアログ ボックスまたは [サーバーに応答していません] ダイアログ ボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値:

- ダイアログ ボックスが正常に表示された場合は IDOK。

- ユーザーがダイアログ ボックスをキャンセルした場合は、IDCANCEL を指定します。

- エラーが発生した場合は、IDABORT を実行します。 IDABORT が返された場合は`COleDialog::GetLastError`、メンバー関数を呼び出して、発生したエラーの種類に関する詳細情報を取得します。 考えられるエラーの一覧については、Windows SDK の[「OleUIBusy](/windows/win32/api/oledlg/nf-oledlg-oleuibusyw)関数」を参照してください。

### <a name="remarks"></a>解説

[m_bz](#m_bz)構造体のメンバを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合は、ダイアログ オブジェクトを`DoModal`構築した後で呼び出す前に、この操作を行う必要があります。

IDOK が返された場合`DoModal`は、他のメンバー関数を呼び出して、ユーザーがダイアログ ボックスに入力した設定または情報を取得できます。

## <a name="colebusydialoggetselectiontype"></a><a name="getselectiontype"></a>ダイアログボックス::選択タイプ

この関数は、[サーバービジー状態] ダイアログ ボックスでユーザーが選択した選択の種類を取得します。

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>戻り値

選択の種類です。

### <a name="remarks"></a>解説

戻り値の型の値は`Selection`、クラスで宣言された`COleBusyDialog`列挙型によって指定されます。

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

これらの値の簡単な説明は次のとおりです。

- `COleBusyDialog::switchTo`[切り替え] ボタンが押されました。

- `COleBusyDialog::retry`再試行ボタンが押されました。

- `COleBusyDialog::callUnblocked`サーバーをアクティブ化するための呼び出しはブロック解除されました。

## <a name="colebusydialogm_bz"></a><a name="m_bz"></a>ダイアログ::m_bz

[サーバー ビジー状態] ダイアログ ボックスの動作を制御するために使用される OLEUIBUSY 型の構造体。

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>解説

この構造体のメンバーは、直接またはメンバー関数を通じて変更できます。

詳細については、Windows SDK の[「OLEUIBUSY」](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw)の構造体を参照してください。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
