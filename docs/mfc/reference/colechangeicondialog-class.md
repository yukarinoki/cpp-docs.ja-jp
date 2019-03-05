---
title: COleChangeIconDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
ms.openlocfilehash: eb5fe38d7cf4058e8de31da3de39dca906671a85
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288975"
---
# <a name="colechangeicondialog-class"></a>COleChangeIconDialog クラス

OLE の [アイコンの変更] ダイアログ ボックスに使用します。

## <a name="syntax"></a>構文

```
class COleChangeIconDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|`COleChangeIconDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|ダイアログ ボックスで指定した変更を実行します。|
|[COleChangeIconDialog::DoModal](#domodal)|OLE 2 アイコンの変更 ダイアログ ボックスが表示されます。|
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|この項目の象徴的な形式に関連付けられているメタファイルを識別するハンドルを取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleChangeIconDialog::m_ci](#m_ci)|ダイアログ ボックスの動作を制御する構造体。|

## <a name="remarks"></a>Remarks

クラスのオブジェクトを作成`COleChangeIconDialog`をこのダイアログ ボックスを呼び出す場合します。 後に、`COleChangeIconDialog`オブジェクトが構築された、使用することができます、[各](#m_ci)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_ci`型 OLEUICHANGEICON 構造です。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。

詳細については、次を参照してください。、 [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) Windows SDK の構造体。

OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeIconDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

##  <a name="colechangeicondialog"></a>  COleChangeIconDialog::COleChangeIconDialog

この関数の作成のみを`COleChangeIconDialog`オブジェクト。

```
explicit COleChangeIconDialog(
    COleClientItem* pItem,
    DWORD dwFlags = CIF_SELECTCURRENT,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
変換する項目へのポインター。

*dwFlags*<br/>
作成フラグは、次の値の任意の数が含まれていますが、ビットごとの使用を組み合わせるの or 演算子。

- CIF_SELECTCURRENT 指定、現在のラジオ ボタンとなる最初に選択 ダイアログ ボックスが呼び出された場合。 既定値です。

- CIF_SELECTDEFAULT 指定既定のオプション ボタンとなる最初に選択 ダイアログ ボックスが呼び出された場合。

- CIF_SELECTFROMFILE 指定からファイルのオプション ボタンとなる最初に選択 ダイアログ ボックスが呼び出された場合。

- CIF_SHOWHELP では、ダイアログ ボックスが呼び出されたときに、[ヘルプ] ボタンが表示されることを指定します。

- CIF_USEICONEXE のアイコンがで指定された実行可能ファイルから抽出することを指定します、`szIconExe`フィールド[各](#m_ci)の代わりに、型から取得します。 これは、埋め込みまたは非 OLE ファイルへのリンクに便利です。

*pParentWnd*<br/>
親またはオーナー ウィンドウのオブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ ボックスの親ウィンドウは、メイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>Remarks

ダイアログ ボックスを表示するには[DoModal](#domodal)関数。

詳細については、次を参照してください。、 [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) Windows SDK の構造体。

##  <a name="dochangeicon"></a>  COleChangeIconDialog::DoChangeIcon

後のダイアログ ボックスで選択されている 1 つに項目を表すアイコンに変更するには、この関数を呼び出す[DoModal](#domodal) IDOK を返します。

```
BOOL DoChangeIcon(COleClientItem* pItem);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
そのアイコンを変更する項目へのポインター。

### <a name="return-value"></a>戻り値

変更に成功した場合は 0 以外それ以外の場合 0 を返します。

##  <a name="domodal"></a>  COleChangeIconDialog::DoModal

OLE の [アイコンの変更] ダイアログ ボックスを表示するには、この関数を呼び出します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログ ボックスが正常に表示されている場合。

- ユーザーには、ダイアログ ボックスが取り消された場合は IDCANCEL。

- IDABORT 場合は、エラーが発生しました。 IDABORT が返される場合、`COleDialog::GetLastError`発生したエラーの種類に関する詳細を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIChangeIcon](/windows/desktop/api/oledlg/nf-oledlg-oleuichangeicona) Windows SDK 内の関数。

### <a name="remarks"></a>Remarks

メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、[各](#m_ci)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。

場合`DoModal`返します IDOK、他のメンバーの設定や、ダイアログ ボックスに、ユーザーが入力した情報を取得する関数を呼び出すことができます。

##  <a name="geticonicmetafile"></a>  COleChangeIconDialog::GetIconicMetafile

選択した項目のアイコンの外観を含むメタファイルを識別するハンドルを取得するには、この関数を呼び出します。

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>戻り値

選択して、ダイアログ ボックスを閉じた場合、新しいアイコンのアイコンの外観を持つメタファイルを識別するハンドル**OK**。 それ以外とアイコンが、ダイアログ ボックスが表示される前にします。

##  <a name="m_ci"></a>  COleChangeIconDialog::m_ci

OLEUICHANGEICON 型の構造体、アイコンの変更 ダイアログ ボックスの動作を制御するために使用します。

```
OLEUICHANGEICON m_ci;
```

### <a name="remarks"></a>Remarks

この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。

詳細については、次を参照してください。、 [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) Windows SDK の構造体。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
