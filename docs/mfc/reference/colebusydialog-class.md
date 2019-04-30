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
ms.openlocfilehash: 08e482e6900e96f1d02c34efddc7635bb8e0120e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400709"
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
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|`COleBusyDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleBusyDialog::DoModal](#domodal)|サーバー ビジー状態のダイアログ ボックスが表示されます。|
|[COleBusyDialog::GetSelectionType](#getselectiontype)|ダイアログ ボックスで行った選択を決定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleBusyDialog::m_bz](#m_bz)|ダイアログ ボックスの動作を制御する OLEUIBUSY 型の構造体。|

## <a name="remarks"></a>Remarks

クラスのオブジェクトを作成`COleBusyDialog`をこれらのダイアログ ボックスを呼び出す場合します。 後に、`COleBusyDialog`オブジェクトが構築された、使用することができます、[各](#m_bz)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_bz`型 OLEUIBUSY 構造です。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。

> [!NOTE]
>  アプリケーション コンテナーのウィザードで生成されたコードでは、このクラスを使用します。

詳細については、次を参照してください。、 [OLEUIBUSY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuibusya) Windows SDK の構造体。

OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。

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

##  <a name="colebusydialog"></a>  COleBusyDialog::COleBusyDialog

この関数は、`COleBusyDialog`オブジェクト。

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*htaskBusy*<br/>
ビジー状態であるサーバーのタスクへのハンドルします。

*bNotResponding*<br/>
TRUE の場合は、サーバーがビジー状態のダイアログ ボックスではなく、応答していません ダイアログ ボックスを呼び出します。 応答していません ダイアログ ボックスの内容は、サーバーがビジー状態 ダイアログ ボックスの内容と若干異なると、キャンセル ボタンが無効になっています。

*dwFlags*<br/>
作成フラグ。 0 個以上のビットごとの OR 演算子と組み合わせて、次の値を含めることができます。

- BZ_DISABLECANCELBUTTON では、ダイアログ ボックスを呼び出すときに、[キャンセル] ボタンが無効にします。

- BZ_DISABLESWITCHTOBUTTON の無効化 ダイアログ ボックスを呼び出すときにスイッチをクリックします。

- BZ_DISABLERETRYBUTTON では、ダイアログ ボックスを呼び出すときに、[再試行] ボタンが無効にします。

*pParentWnd*<br/>
親またはオーナー ウィンドウのオブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログのオブジェクトの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。

### <a name="remarks"></a>Remarks

ダイアログ ボックスを表示するには、呼び出す[DoModal](#domodal)します。

詳細については、次を参照してください。、 [OLEUIBUSY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuibusya) Windows SDK の構造体。

##  <a name="domodal"></a>  COleBusyDialog::DoModal

サーバー ビジー状態であるか、サーバーが応答しません ダイアログ ボックスを表示するには、この関数を呼び出します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログ ボックスが正常に表示されている場合。

- ユーザーには、ダイアログ ボックスが取り消された場合は IDCANCEL。

- IDABORT 場合は、エラーが発生しました。 IDABORT が返される場合、`COleDialog::GetLastError`発生したエラーの種類に関する詳細を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIBusy](/windows/desktop/api/oledlg/nf-oledlg-oleuibusya) Windows SDK 内の関数。

### <a name="remarks"></a>Remarks

メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、[各](#m_bz)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。

場合`DoModal`返します IDOK、他のメンバーの設定や、ダイアログ ボックスに、ユーザーが入力した情報を取得する関数を呼び出すことができます。

##  <a name="getselectiontype"></a>  COleBusyDialog::GetSelectionType

サーバーがビジー状態のダイアログ ボックスでユーザーが選択した型を取得するには、この関数を呼び出します。

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>戻り値

選択された型。

### <a name="remarks"></a>Remarks

戻り値の型の値がで指定された、`Selection`で宣言された列挙型、`COleBusyDialog`クラス。

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

これらの値の簡単な説明に従います。

- `COleBusyDialog::switchTo` 切り替えボタンが押されました。

- `COleBusyDialog::retry` [再試行] ボタンが押されました。

- `COleBusyDialog::callUnblocked` サーバーをアクティブ化する呼び出しがブロックされていません。

##  <a name="m_bz"></a>  COleBusyDialog::m_bz

OLEUIBUSY 型の構造体、サーバーがビジー状態 ダイアログ ボックスの動作を制御するために使用します。

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>Remarks

この構造体のメンバーは、直接またはメンバー関数を使用して変更できます。

詳細については、次を参照してください。、 [OLEUIBUSY](/windows/desktop/api/oledlg/ns-oledlg-tagoleuibusya) Windows SDK の構造体。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
