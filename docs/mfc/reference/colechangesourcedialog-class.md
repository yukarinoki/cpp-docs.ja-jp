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
ms.openlocfilehash: 1d118b132fc110402967e9c7f2b1d74a2164d7c8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304614"
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
|[COleChangeSourceDialog::DoModal](#domodal)|OLE の [ソースの変更] ダイアログ ボックスが表示されます。|
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|完全なソースの表示名を取得します。|
|[COleChangeSourceDialog::GetFileName](#getfilename)|元の名前のファイル名を取得します。|
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|以前のソースのプレフィックスを取得します。|
|[COleChangeSourceDialog::GetItemName](#getitemname)|元の名前、項目の名前を取得します。|
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|新しいソースのプレフィックスを取得します。|
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|ソースが有効であることを示します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleChangeSourceDialog::m_cs](#m_cs)|ダイアログ ボックスの動作を制御する構造体。|

## <a name="remarks"></a>Remarks

クラスのオブジェクトを作成`COleChangeSourceDialog`をこのダイアログ ボックスを呼び出す場合します。 後に、`COleChangeSourceDialog`オブジェクトが構築された、使用することができます、 [m_cs](#m_cs)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_cs`型の構造は、 [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea)します。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。

詳細については、次を参照してください。、 [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK の構造体。

OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。

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

##  <a name="colechangesourcedialog"></a>  COleChangeSourceDialog::COleChangeSourceDialog

この関数を作成、`COleChangeSourceDialog`オブジェクト。

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
リンクへのポインター [COleClientItem](../../mfc/reference/coleclientitem-class.md)を更新するにはソース。

*pParentWnd*<br/>
親またはオーナー ウィンドウのオブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ ボックスの親ウィンドウは、メイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>Remarks

ダイアログ ボックスを表示するには[DoModal](#domodal)関数。

詳細については、次を参照してください。、 [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea)構造と[OleUIChangeSource](/windows/desktop/api/oledlg/nf-oledlg-oleuichangesourcea) Windows SDK 内の関数。

##  <a name="domodal"></a>  COleChangeSourceDialog::DoModal

OLE の [ソースの変更] ダイアログ ボックスを表示するには、この関数を呼び出します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログ ボックスが正常に表示されている場合。

- ユーザーには、ダイアログ ボックスが取り消された場合は IDCANCEL。

- IDABORT 場合は、エラーが発生しました。 IDABORT が返される場合、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)発生したエラーの種類に関する詳細を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIChangeSource](/windows/desktop/api/oledlg/nf-oledlg-oleuichangesourcea) Windows SDK 内の関数。

### <a name="remarks"></a>Remarks

メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、 [m_cs](#m_cs)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。

場合`DoModal`IDOK を返しますメンバー、ダイアログ ボックスからユーザーが入力した設定や情報を取得する関数を呼び出すことができます。 一般的なクエリ関数の名前を次の一覧に。

- [GetFileName](#getfilename)

- [GetDisplayName](#getdisplayname)

- [GetItemName](#getitemname)

##  <a name="getdisplayname"></a>  COleChangeSourceDialog::GetDisplayName

リンクされたクライアント アイテムの完全な表示名を取得するには、この関数を呼び出します。

```
CString GetDisplayName();
```

### <a name="return-value"></a>戻り値

完全なソース表示名 (モニカー)、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)コンス トラクターで指定します。

##  <a name="getfilename"></a>  COleChangeSourceDialog::GetFileName

リンクされたクライアントの項目の表示名のファイルのモニカーの部分を取得するには、この関数を呼び出します。

```
CString GetFileName();
```

### <a name="return-value"></a>戻り値

ソースの表示名のファイルのモニカーの部分、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)コンス トラクターで指定します。

### <a name="remarks"></a>Remarks

アイテム モニカーと共にファイル モニカーは、完全な表示名を示します。

##  <a name="getfromprefix"></a>  COleChangeSourceDialog::GetFromPrefix

この関数では、ソースの以前のプレフィックス文字列を取得します。

```
CString GetFromPrefix();
```

### <a name="return-value"></a>戻り値

ソースの以前のプレフィックス文字列。

### <a name="remarks"></a>Remarks

後でのみこの関数の呼び出し[DoModal](#domodal) IDOK を返します。

この値はから直接、`lpszFrom`のメンバー、 [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea)構造体。

詳細については、次を参照してください。、 [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK の構造体。

##  <a name="getitemname"></a>  COleChangeSourceDialog::GetItemName

アイテム モニカーのリンクされたクライアントの項目の表示名の部分を取得するには、この関数を呼び出します。

```
CString GetItemName();
```

### <a name="return-value"></a>戻り値

アイテム モニカーの一部分のソースの表示名、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)コンス トラクターで指定します。

### <a name="remarks"></a>Remarks

アイテム モニカーと共にファイル モニカーは、完全な表示名を示します。

##  <a name="gettoprefix"></a>  COleChangeSourceDialog::GetToPrefix

この関数では、ソースの新しいプレフィックス文字列を取得します。

```
CString GetToPrefix();
```

### <a name="return-value"></a>戻り値

ソースの新しいプレフィックス文字列。

### <a name="remarks"></a>Remarks

後でのみこの関数の呼び出し[DoModal](#domodal) IDOK を返します。

この値はから直接、`lpszTo`のメンバー、 [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea)構造体。

詳細については、次を参照してください。、 [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK の構造体。

##  <a name="m_cs"></a>  COleChangeSourceDialog::m_cs

このデータ メンバーが型の構造体[OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea)します。

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>Remarks

`OLEUICHANGESOURCE` OLE の [ソースの変更] ダイアログ ボックスの動作の制御に使用されます。 この構造体のメンバーを直接変更できます。

詳細については、次を参照してください。、 [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK の構造体。

##  <a name="isvalidsource"></a>  COleChangeSourceDialog::IsValidSource

新しいソースが有効なかどうかを判断するには、この関数を呼び出します。

```
BOOL IsValidSource();
```

### <a name="return-value"></a>戻り値

新しいソースが、有効な場合は 0 以外。 それ以外の場合 0。

### <a name="remarks"></a>Remarks

後でのみこの関数の呼び出し[DoModal](#domodal) IDOK を返します。

詳細については、次を参照してください。、 [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) Windows SDK の構造体。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
