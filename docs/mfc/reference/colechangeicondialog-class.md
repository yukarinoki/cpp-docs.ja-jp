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
ms.openlocfilehash: 6cdc0ed6bfa4765817de8b7628f339db5e7e5bf5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369630"
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
|[ダイアログボックス:::コントロールアイコンダイアログ](#colechangeicondialog)|`COleChangeIconDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス::D](#dochangeicon)|ダイアログ ボックスで指定した変更を実行します。|
|[ダイアログ ボックスを:Do モーダル](#domodal)|[OLE 2 アイコンの変更] ダイアログ ボックスを表示します。|
|[ダイアログボックス::イコニックメタファイル](#geticonicmetafile)|このアイテムのアイコン形式に関連付けられているメタファイルへのハンドルを取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ::m_ci](#m_ci)|ダイアログ ボックスの動作を制御する構造体。|

## <a name="remarks"></a>解説

このダイアログ ボックスを`COleChangeIconDialog`呼び出す場合は、クラスのオブジェクトを作成します。 オブジェクトを`COleChangeIconDialog`構築した後[、m_ci](#m_ci)構造を使用して、ダイアログ ボックス内のコントロールの値または状態を初期化できます。 構造体`m_ci`の型は OLEUICHANGEICON です。 このダイアログ クラスの使用方法の詳細については[、DoModal](#domodal)メンバー関数を参照してください。

詳細については、Windows SDK の[「OLEUICHANGEICON」](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw)構造を参照してください。

OLE 固有のダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

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

## <a name="colechangeicondialogcolechangeicondialog"></a><a name="colechangeicondialog"></a>ダイアログボックス:::コントロールアイコンダイアログ

この関数は`COleChangeIconDialog`オブジェクトのみを構築します。

```
explicit COleChangeIconDialog(
    COleClientItem* pItem,
    DWORD dwFlags = CIF_SELECTCURRENT,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
変換する項目へのポイント。

*dwFlags*<br/>
作成フラグは、ビットごとのまたは演算子を使用して組み合わせた次の値の任意の数を含みます。

- CIF_SELECTCURRENT ダイアログ ボックスが呼び出されたときに、[現在] ラジオ ボタンが最初に選択されるように指定します。 これは既定値です。

- CIF_SELECTDEFAULT ダイアログ ボックスが呼び出されたときに、[既定] ラジオ ボタンが最初に選択されるように指定します。

- CIF_SELECTFROMFILE ダイアログ ボックスが呼び出されたときに、[ファイルから] オプション ボタンが最初に選択されるように指定します。

- CIF_SHOWHELP ダイアログ ボックスが呼び出されたときに [ヘルプ] ボタンが表示されるように指定します。

- CIF_USEICONEXE型から取得するのではなく`szIconExe`[、m_ci](#m_ci)のフィールドで指定された実行可能ファイルからアイコンを抽出することを指定します。 この機能は、OLE 以外のファイルを埋め込んだり、リンクしたりする場合に便利です。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する (型`CWnd`) の親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクトへのポインター。 NULL の場合、ダイアログ ボックスの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

ダイアログ ボックスを表示するには[、DoModal](#domodal)関数を呼び出します。

詳細については、Windows SDK の[「OLEUICHANGEICON」](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw)構造を参照してください。

## <a name="colechangeicondialogdochangeicon"></a><a name="dochangeicon"></a>ダイアログ ボックス::D

この関数を呼び出して[、DoModal](#domodal)が IDOK を返した後、ダイアログ ボックスで選択したアイコンに項目を表すアイコンを変更します。

```
BOOL DoChangeIcon(COleClientItem* pItem);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
アイコンが変更される項目へのポイント。

### <a name="return-value"></a>戻り値

変更が成功した場合は 0 以外。それ以外の場合は 0。

## <a name="colechangeicondialogdomodal"></a><a name="domodal"></a>ダイアログ ボックスを:Do モーダル

[OLE のアイコンの変更] ダイアログ ボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値:

- ダイアログ ボックスが正常に表示された場合は IDOK。

- ユーザーがダイアログ ボックスをキャンセルした場合は、IDCANCEL を指定します。

- エラーが発生した場合は、IDABORT を実行します。 IDABORT が返された場合は`COleDialog::GetLastError`、メンバー関数を呼び出して、発生したエラーの種類に関する詳細情報を取得します。 考えられるエラーの一覧については、Windows SDK の[「OleUIChangeIcon](/windows/win32/api/oledlg/nf-oledlg-oleuichangeiconw)関数」を参照してください。

### <a name="remarks"></a>解説

[m_ci](#m_ci)構造体のメンバを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合は、ダイアログ オブジェクトを`DoModal`構築した後で呼び出す前に、この操作を行う必要があります。

IDOK が返された場合`DoModal`は、他のメンバー関数を呼び出して、ユーザーがダイアログ ボックスに入力した設定または情報を取得できます。

## <a name="colechangeicondialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>ダイアログボックス::イコニックメタファイル

選択した項目のアイコン的な側面を含むメタファイルへのハンドルを取得します。

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスが閉じられた場合は、新しいアイコンのアイコンのアイコンを含むメタファイルへのハンドルを**選択**します。それ以外の場合は、ダイアログが表示される前のアイコン。

## <a name="colechangeicondialogm_ci"></a><a name="m_ci"></a>ダイアログ::m_ci

[アイコンの変更] ダイアログ ボックスの動作を制御するために使用される OLEUICHANGEICON 型の構造体。

```
OLEUICHANGEICON m_ci;
```

### <a name="remarks"></a>解説

この構造体のメンバーは、直接またはメンバー関数を通じて変更できます。

詳細については、Windows SDK の[「OLEUICHANGEICON」](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw)構造を参照してください。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
