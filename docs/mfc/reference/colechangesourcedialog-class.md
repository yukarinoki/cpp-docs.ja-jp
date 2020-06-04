---
title: COleChangeSourceDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
ms.openlocfilehash: 78da0a495de6ea951deab984550756a2d6f3e2bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321872"
---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog クラス

OLE の [ソースの変更] ダイアログ ボックスに使用します。

## <a name="syntax"></a>構文

```
class COleChangeSourceDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ:::コントロールソース](#colechangesourcedialog)|`COleChangeSourceDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ::Do モーダル](#domodal)|[OLE の変更] ダイアログ ボックスを表示します。|
|[ダイアログ ボックス::表示名を取得します。](#getdisplayname)|完全なソース表示名を取得します。|
|[ダイアログボックス::ファイル名を取得します。](#getfilename)|ソース名からファイル名を取得します。|
|[ダイアログ::取得のプレフィックス](#getfromprefix)|前のソースのプレフィックスを取得します。|
|[ダイアログボックス::アイテム名を取得します。](#getitemname)|ソース名から項目名を取得します。|
|[ダイアログ::取得プレフィックス](#gettoprefix)|新しいソースのプレフィックスを取得します。|
|[ダイアログ::IsValidソース](#isvalidsource)|ソースが有効かどうかを示します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ::m_cs](#m_cs)|ダイアログ ボックスの動作を制御する構造体。|

## <a name="remarks"></a>解説

このダイアログ ボックスを`COleChangeSourceDialog`呼び出す場合は、クラスのオブジェクトを作成します。 オブジェクトを`COleChangeSourceDialog`構築した後[、m_cs](#m_cs)構造を使用して、ダイアログ ボックス内のコントロールの値または状態を初期化できます。 構造体`m_cs`の型は[OLEUI 変更ソースです](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)。 このダイアログ クラスの使用方法の詳細については[、DoModal](#domodal)メンバー関数を参照してください。

詳細については、Windows SDK の[「OLEUI 変更ソース](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)」を参照してください。

OLE 固有のダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

## <a name="colechangesourcedialogcolechangesourcedialog"></a><a name="colechangesourcedialog"></a>ダイアログ:::コントロールソース

この関数はオブジェクトを`COleChangeSourceDialog`構築します。

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
ソースを更新するリンクされた[COleClientItem](../../mfc/reference/coleclientitem-class.md)へのポインター。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する (型`CWnd`) の親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクトへのポインター。 NULL の場合、ダイアログ ボックスの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

ダイアログ ボックスを表示するには[、DoModal](#domodal)関数を呼び出します。

詳細については、Windows SDK の[「OLEUI 変更ソース](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)」および[「OLEUI 変更ソース](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew)」を参照してください。

## <a name="colechangesourcedialogdomodal"></a><a name="domodal"></a>ダイアログ::Do モーダル

OLE の [ソースの変更] ダイアログ ボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値:

- ダイアログ ボックスが正常に表示された場合は IDOK。

- ユーザーがダイアログ ボックスをキャンセルした場合は、IDCANCEL を指定します。

- エラーが発生した場合は、IDABORT を実行します。 IDABORT が返された場合は、発生したエラーの種類に関する詳細情報を取得するのには[、COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)メンバー関数を呼び出します。 考えられるエラーの一覧については、Windows SDK の[「OleUIChangeSource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew)関数」を参照してください。

### <a name="remarks"></a>解説

[m_cs](#m_cs)構造体のメンバを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合は、ダイアログ オブジェクトを`DoModal`作成した後で呼び出す前に、この操作を行う必要があります。

IDOK が返された場合`DoModal`は、メンバー関数を呼び出して、ダイアログ ボックスからユーザーが入力した設定または情報を取得できます。 次の一覧では、一般的なクエリ関数を挙します。

- [GetFileName](#getfilename)

- [表示名を取得します。](#getdisplayname)

- [アイテム名を取得します。](#getitemname)

## <a name="colechangesourcedialoggetdisplayname"></a><a name="getdisplayname"></a>ダイアログ ボックス::表示名を取得します。

リンクされたクライアント アイテムの完全な表示名を取得します。

```
CString GetDisplayName();
```

### <a name="return-value"></a>戻り値

コンストラクターで指定された[COleClientItem](../../mfc/reference/coleclientitem-class.md)の完全なソース表示名 (モニカー)。

## <a name="colechangesourcedialoggetfilename"></a><a name="getfilename"></a>ダイアログボックス::ファイル名を取得します。

リンクされたクライアント アイテムの表示名のファイル モニカ部分を取得します。

```
CString GetFileName();
```

### <a name="return-value"></a>戻り値

コンストラクターで指定された[COleClientItem](../../mfc/reference/coleclientitem-class.md)のソース表示名のファイル モニカ部分。

### <a name="remarks"></a>解説

ファイル モニカーとアイテム モニカーは、完全な表示名を示します。

## <a name="colechangesourcedialoggetfromprefix"></a><a name="getfromprefix"></a>ダイアログ::取得のプレフィックス

ソースの前のプレフィックス文字列を取得します。

```
CString GetFromPrefix();
```

### <a name="return-value"></a>戻り値

ソースの前のプレフィックス文字列。

### <a name="remarks"></a>解説

この関数を呼び出すのは[、DoModal](#domodal)が IDOK を返した後だけです。

この値は`lpszFrom`[、OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)構造体のメンバーから直接取得されます。

詳細については、Windows SDK の[「OLEUI 変更ソース](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)」を参照してください。

## <a name="colechangesourcedialoggetitemname"></a><a name="getitemname"></a>ダイアログボックス::アイテム名を取得します。

リンクされたクライアント アイテムの表示名の項目モニカ部分を取得します。

```
CString GetItemName();
```

### <a name="return-value"></a>戻り値

コンストラクターで指定された[COleClientItem](../../mfc/reference/coleclientitem-class.md)のソース表示名の項目モニカー部分。

### <a name="remarks"></a>解説

ファイル モニカーとアイテム モニカーは、完全な表示名を示します。

## <a name="colechangesourcedialoggettoprefix"></a><a name="gettoprefix"></a>ダイアログ::取得プレフィックス

ソースの新しいプレフィックス文字列を取得します。

```
CString GetToPrefix();
```

### <a name="return-value"></a>戻り値

ソースの新しいプレフィックス文字列。

### <a name="remarks"></a>解説

この関数を呼び出すのは[、DoModal](#domodal)が IDOK を返した後だけです。

この値は`lpszTo`[、OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)構造体のメンバーから直接取得されます。

詳細については、Windows SDK の[「OLEUI 変更ソース](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)」を参照してください。

## <a name="colechangesourcedialogm_cs"></a><a name="m_cs"></a>ダイアログ::m_cs

このデータ メンバは[、OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)型の構造体です。

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>解説

`OLEUICHANGESOURCE`は、[OLE ソースの変更] ダイアログ ボックスの動作を制御するために使用します。 この構造体のメンバーは、直接変更できます。

詳細については、Windows SDK の[「OLEUI 変更ソース](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)」を参照してください。

## <a name="colechangesourcedialogisvalidsource"></a><a name="isvalidsource"></a>ダイアログ::IsValidソース

新しいソースが有効かどうかを確認します。

```
BOOL IsValidSource();
```

### <a name="return-value"></a>戻り値

新しいソースが有効な場合は 0 以外、それ以外の場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

この関数を呼び出すのは[、DoModal](#domodal)が IDOK を返した後だけです。

詳細については、Windows SDK の[「OLEUI 変更ソース](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)」を参照してください。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
