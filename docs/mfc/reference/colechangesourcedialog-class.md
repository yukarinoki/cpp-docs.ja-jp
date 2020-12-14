---
description: '詳細情報: COleChangeSourceDialog クラス'
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
ms.openlocfilehash: 2962534b5c1e85e274d134a347821a94d646b66d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209933"
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
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|`COleChangeSourceDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleChangeSourceDialog::D oModal](#domodal)|[OLE 変更ソース] ダイアログボックスを表示します。|
|[COleChangeSourceDialog:: GetDisplayName](#getdisplayname)|ソースの完全な表示名を取得します。|
|[COleChangeSourceDialog:: GetFileName](#getfilename)|ソース名からファイル名を取得します。|
|[COleChangeSourceDialog:: GetFromPrefix](#getfromprefix)|前のソースのプレフィックスを取得します。|
|[COleChangeSourceDialog::GetItemName](#getitemname)|ソース名から項目名を取得します。|
|[COleChangeSourceDialog:: GetToPrefix](#gettoprefix)|新しいソースのプレフィックスを取得します。|
|[COleChangeSourceDialog:: IsValidSource](#isvalidsource)|ソースが有効かどうかを示します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleChangeSourceDialog:: m_cs](#m_cs)|ダイアログボックスの動作を制御する構造体。|

## <a name="remarks"></a>解説

このダイアログボックスを呼び出す必要がある場合は、クラスのオブジェクトを作成 `COleChangeSourceDialog` します。 `COleChangeSourceDialog`オブジェクトが構築されたら、 [m_cs](#m_cs)構造体を使用して、ダイアログボックス内のコントロールの値または状態を初期化できます。 `m_cs`構造体の型は[OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)です。 このダイアログクラスの使用方法の詳細については、「 [DoModal](#domodal) メンバー関数」を参照してください。

詳細については、Windows SDK の [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 構造体を参照してください。

OLE 固有のダイアログボックスの詳細については、 [ole の記事のダイアログボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>要件

**ヘッダー:** afxodlgs

## <a name="colechangesourcedialogcolechangesourcedialog"></a><a name="colechangesourcedialog"></a> COleChangeSourceDialog::COleChangeSourceDialog

この関数は、 `COleChangeSourceDialog` オブジェクトを構築します。

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
ソースが更新されるリンクされた [COleClientItem](../../mfc/reference/coleclientitem-class.md) へのポインター。

*pParentWnd*<br/>
ダイアログオブジェクトが属する親またはオーナーウィンドウオブジェクト (型) を指し `CWnd` ます。 NULL の場合は、ダイアログボックスの親ウィンドウがメインアプリケーションウィンドウに設定されます。

### <a name="remarks"></a>解説

ダイアログボックスを表示するには、 [DoModal](#domodal) 関数を呼び出します。

詳細については、Windows SDK の「 [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) Structure and [OLEUICHANGESOURCE](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) 関数」を参照してください。

## <a name="colechangesourcedialogdomodal"></a><a name="domodal"></a> COleChangeSourceDialog::D oModal

OLE の [ソースの変更] ダイアログボックスを表示するには、この関数を呼び出します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログボックスが正常に表示された場合は。

- ユーザーがダイアログボックスをキャンセルした場合は IDCANCEL。

- エラーが発生した場合は IDABORT。 IDABORT が返された場合は、 [COleDialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) メンバー関数を呼び出して、発生したエラーの種類に関する詳細情報を取得します。 考えられるエラーの一覧については、Windows SDK の「 [OleUIChangeSource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) 関数」を参照してください。

### <a name="remarks"></a>解説

[M_cs](#m_cs)構造体のメンバーを設定してさまざまなダイアログボックスコントロールを初期化する場合は、を呼び出す前に `DoModal` 、ダイアログオブジェクトが構築された後にこの操作を行う必要があります。

が IDOK を返す場合は、 `DoModal` メンバー関数を呼び出して、ダイアログボックスからユーザーが入力した設定または情報を取得できます。 一般的なクエリ関数の名前は次のとおりです。

- [GetFileName](#getfilename)

- [GetDisplayName](#getdisplayname)

- [GetItemName](#getitemname)

## <a name="colechangesourcedialoggetdisplayname"></a><a name="getdisplayname"></a> COleChangeSourceDialog:: GetDisplayName

この関数を呼び出して、リンクされたクライアントアイテムの完全な表示名を取得します。

```
CString GetDisplayName();
```

### <a name="return-value"></a>戻り値

コンストラクターで指定された [COleClientItem](../../mfc/reference/coleclientitem-class.md) の完全なソース表示名 (モニカー)。

## <a name="colechangesourcedialoggetfilename"></a><a name="getfilename"></a> COleChangeSourceDialog:: GetFileName

この関数を呼び出して、リンクされたクライアント項目の表示名のファイルモニカーの部分を取得します。

```
CString GetFileName();
```

### <a name="return-value"></a>戻り値

コンストラクターで指定された [COleClientItem](../../mfc/reference/coleclientitem-class.md) のソース表示名のファイルモニカー部分。

### <a name="remarks"></a>解説

ファイルモニカーと項目モニカーは、完全な表示名を示します。

## <a name="colechangesourcedialoggetfromprefix"></a><a name="getfromprefix"></a> COleChangeSourceDialog:: GetFromPrefix

この関数を呼び出して、ソースの前のプレフィックス文字列を取得します。

```
CString GetFromPrefix();
```

### <a name="return-value"></a>戻り値

ソースの前のプレフィックス文字列。

### <a name="remarks"></a>解説

[DoModal](#domodal)が IDOK を返す場合にのみ、この関数を呼び出します。

この値は、 `lpszFrom` [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 構造体のメンバーから直接取得されます。

詳細については、Windows SDK の [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 構造体を参照してください。

## <a name="colechangesourcedialoggetitemname"></a><a name="getitemname"></a> COleChangeSourceDialog::GetItemName

この関数を呼び出して、リンクされたクライアント項目の表示名の項目モニカーの部分を取得します。

```
CString GetItemName();
```

### <a name="return-value"></a>戻り値

コンストラクターで指定された [COleClientItem](../../mfc/reference/coleclientitem-class.md) のソース表示名の項目モニカー部分。

### <a name="remarks"></a>解説

ファイルモニカーと項目モニカーは、完全な表示名を示します。

## <a name="colechangesourcedialoggettoprefix"></a><a name="gettoprefix"></a> COleChangeSourceDialog:: GetToPrefix

この関数を呼び出して、ソースの新しいプレフィックス文字列を取得します。

```
CString GetToPrefix();
```

### <a name="return-value"></a>戻り値

ソースの新しいプレフィックス文字列。

### <a name="remarks"></a>解説

[DoModal](#domodal)が IDOK を返す場合にのみ、この関数を呼び出します。

この値は、 `lpszTo` [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 構造体のメンバーから直接取得されます。

詳細については、Windows SDK の [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 構造体を参照してください。

## <a name="colechangesourcedialogm_cs"></a><a name="m_cs"></a> COleChangeSourceDialog:: m_cs

このデータメンバーは、 [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)型の構造体です。

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>解説

`OLEUICHANGESOURCE` は、[OLE 変更ソース] ダイアログボックスの動作を制御するために使用されます。 この構造体のメンバーは、直接変更できます。

詳細については、Windows SDK の [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 構造体を参照してください。

## <a name="colechangesourcedialogisvalidsource"></a><a name="isvalidsource"></a> COleChangeSourceDialog:: IsValidSource

この関数を呼び出して、新しいソースが有効かどうかを確認します。

```
BOOL IsValidSource();
```

### <a name="return-value"></a>戻り値

新しいソースが有効な場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

[DoModal](#domodal)が IDOK を返す場合にのみ、この関数を呼び出します。

詳細については、Windows SDK の [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 構造体を参照してください。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
