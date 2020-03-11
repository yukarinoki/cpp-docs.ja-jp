---
title: COleInsertDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
ms.openlocfilehash: a884f946b60be0567f39477f434db8efe041e393
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855601"
---
# <a name="coleinsertdialog-class"></a>COleInsertDialog クラス

OLE の [オブジェクトの挿入] ダイアログ ボックスで使用されます。

## <a name="syntax"></a>構文

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|`COleInsertDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[COleInsertDialog:: CreateItem](#createitem)|ダイアログボックスで選択した項目を作成します。|
|[COleInsertDialog::D oModal](#domodal)|[OLE オブジェクトの挿入] ダイアログボックスを表示します。|
|[COleInsertDialog:: GetClassID](#getclassid)|選択した項目に関連付けられている CLSID を取得します。|
|[COleInsertDialog:: GetDrawAspect](#getdrawaspect)|項目をアイコンとして描画するかどうかを示します。|
|[COleInsertDialog:: Geが Onicmetafile](#geticonicmetafile)|この項目のアイコン化形式に関連付けられているメタファイルへのハンドルを取得します。|
|[COleInsertDialog:: GetPathName](#getpathname)|ダイアログボックスで選択されたファイルへの完全パスを取得します。|
|[COleInsertDialog:: GetSelectionType](#getselectiontype)|選択されたオブジェクトの型を取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|説明|
|----------|-----------------|
|[COleInsertDialog:: m_io](#m_io)|ダイアログボックスの動作を制御する OLEUIINSERTOBJECT 型の構造体。|

## <a name="remarks"></a>コメント

このダイアログボックスを呼び出す必要がある場合は `COleInsertDialog` クラスのオブジェクトを作成します。 `COleInsertDialog` オブジェクトが構築されたら、 [m_io](#m_io)構造を使用して、ダイアログボックス内のコントロールの値または状態を初期化できます。 `m_io` 構造体の型は OLEUIINSERTOBJECT です。 このダイアログクラスの使用方法の詳細については、「 [DoModal](#domodal)メンバー関数」を参照してください。

> [!NOTE]
>  アプリケーションウィザードで生成されたコンテナーコードは、このクラスを使用します。

詳細については、Windows SDK の[OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw)構造体を参照してください。

OLE 固有のダイアログボックスの詳細については、 [ole の記事のダイアログボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>要件

**ヘッダー:** afxodlgs

##  <a name="coleinsertdialog"></a>COleInsertDialog::COleInsertDialog

この関数は、`COleInsertDialog` オブジェクトのみを構築します。

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
ビットごとの OR 演算子を使用して結合する次の値の任意の数を含む作成フラグ。

- IOF_SHOWHELP、ダイアログボックスが呼び出されたときに [ヘルプ] ボタンが表示されることを指定します。

- IOF_SELECTCREATENEW、ダイアログボックスが呼び出されたときに、[新規作成] オプションボタンが最初に選択されることを指定します。 これは既定値であり、IOF_SELECTCREATEFROMFILE と共に使用することはできません。

- IOF_SELECTCREATEFROMFILE、ダイアログボックスが呼び出されたときに、最初に [ファイルから作成] オプションボタンが選択されることを指定します。 IOF_SELECTCREATENEW と共に使用することはできません。

- [IOF_CHECKLINK] ダイアログボックスが呼び出されたときに、最初に [リンク] チェックボックスがオンになるように指定します。

- [IOF_DISABLELINK] ダイアログボックスが呼び出されると、[リンク] チェックボックスが無効になることを指定します。

- IOF_CHECKDISPLAYASICON [アイコンとして表示] チェックボックスが最初にオンになり、現在のアイコンが表示され、ダイアログボックスが呼び出されると [アイコンの変更] ボタンが有効になります。

- IOF_VERIFYSERVERSEXIST、ダイアログボックスが表示される前に、登録データベースに指定されているサーバーが存在することを確認して、ダイアログボックスがリストボックスに追加するクラスを検証することを指定します。 このフラグを設定すると、パフォーマンスが大幅に低下する可能性があります。

*pParentWnd*<br/>
ダイアログオブジェクトが属する親またはオーナーウィンドウオブジェクト (`CWnd`型) を指します。 NULL の場合は、ダイアログオブジェクトの親ウィンドウがメインアプリケーションウィンドウに設定されます。

### <a name="remarks"></a>コメント

ダイアログボックスを表示するには、 [DoModal](#domodal)関数を呼び出します。

##  <a name="createitem"></a>COleInsertDialog:: CreateItem

[DoModal](#domodal)が IDOK を返す場合にのみ、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)型のオブジェクトを作成するには、この関数を呼び出します。

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
作成する項目をポイントします。

### <a name="return-value"></a>戻り値

項目が作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

この関数を呼び出す前に、`COleClientItem` オブジェクトを割り当てる必要があります。

##  <a name="domodal"></a>COleInsertDialog::D oModal

[OLE 挿入オブジェクト] ダイアログボックスを表示するには、この関数を呼び出します。

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
次のいずれかの値:

`COleInsertDialog::DocObjectsOnly` は DocObjects のみを挿入します。

`COleInsertDialog::ControlsOnly` は、ActiveX コントロールのみを挿入します。

0の場合、DocObject も ActiveX コントロールも挿入されません。 この値は、上記の最初のプロトタイプと同じ実装になります。

### <a name="return-value"></a>戻り値

ダイアログボックスの完了ステータス。 次のいずれかの値:

- IDOK ダイアログボックスが正常に表示された場合は。

- ユーザーがダイアログボックスをキャンセルした場合は IDCANCEL。

- エラーが発生した場合は IDABORT。 IDABORT が返された場合は、 [COleDialog:: GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)メンバー関数を呼び出して、発生したエラーの種類に関する詳細情報を取得します。 考えられるエラーの一覧については、Windows SDK の「 [OleUIInsertObject](/windows/win32/api/oledlg/nf-oledlg-oleuiinsertobjectw)関数」を参照してください。

### <a name="remarks"></a>コメント

[M_io](#m_io)構造体のメンバーを設定してさまざまなダイアログボックスコントロールを初期化する場合は、`DoModal`を呼び出す前にこの操作を行う必要がありますが、ダイアログオブジェクトが構築された後に実行する必要があります。

`DoModal` が IDOK を返す場合は、他のメンバー関数を呼び出して、ユーザーがダイアログボックスの設定または情報入力を取得できます。

##  <a name="getclassid"></a>COleInsertDialog:: GetClassID

この関数を呼び出して、選択した項目に関連付けられている CLSID を取得します。これは、 [DoModal](#domodal)が IDOK を返し、選択の型が `COleInsertDialog::createNewItem`の場合のみです。

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>戻り値

選択された項目に関連付けられている CLSID を返します。

### <a name="remarks"></a>コメント

詳細については、Windows SDK の「 [CLSID キー](/windows/win32/com/clsid-key-hklm) 」を参照してください。

##  <a name="getdrawaspect"></a>COleInsertDialog:: GetDrawAspect

ユーザーが選択した項目をアイコンとして表示することを選択したかどうかを判断するには、この関数を呼び出します。

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>戻り値

オブジェクトを表示するために必要なメソッド。

- [アイコンとして表示] チェックボックスがオンになっていない場合は DVASPECT_CONTENT が返されます。

- [アイコンとして表示] チェックボックスがオンになっている場合に DVASPECT_ICON 返されます。

### <a name="remarks"></a>コメント

[DoModal](#domodal)が IDOK を返す場合にのみ、この関数を呼び出します。

アスペクトの描画の詳細については、Windows SDK の「 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) data structure」を参照してください。

##  <a name="geticonicmetafile"></a>COleInsertDialog:: Geが Onicmetafile

選択した項目のアイコンの側面を含むメタファイルへのハンドルを取得するには、この関数を呼び出します。

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>戻り値

**[OK**] をクリックしてダイアログを閉じたときに [アイコンとして表示] チェックボックスがオンになっていた場合に、選択した項目のアイコンの側面を含むメタファイルへのハンドル。それ以外の場合は NULL。

##  <a name="getpathname"></a>COleInsertDialog:: GetPathName

この関数を呼び出して、選択したファイルの完全パスを取得します。これは、 [DoModal](#domodal)が IDOK を返し、選択の型が `COleInsertDialog::createNewItem`でない場合のみです。

```
CString GetPathName() const;
```

### <a name="return-value"></a>戻り値

ダイアログボックスで選択されたファイルへの完全パスです。 選択型が `createNewItem`の場合、この関数は、リリースモードでは無意味な `CString` を返します。または、デバッグモードでアサーションを発生させます。

##  <a name="getselectiontype"></a>COleInsertDialog:: GetSelectionType

[オブジェクトの挿入] ダイアログボックスが閉じられたときに選択した選択の種類を取得するには、この関数を呼び出します。 **[OK]** をクリックします。

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>戻り値

選択された種類。

### <a name="remarks"></a>コメント

戻り値の型の値は、`COleInsertDialog` クラスで宣言された `Selection` 列挙型によって指定されます。

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

これらの値の簡単な説明を次に示します。

- `COleInsertDialog::createNewItem` [新規作成] ラジオボタンが選択されました。

- `COleInsertDialog::insertFromFile` [ファイルから作成] オプションボタンが選択されており、[リンク] チェックボックスがオンになっていません。

- `COleInsertDialog::linkToFile` [ファイルから作成] オプションボタンが選択されており、[リンク] チェックボックスがオンになっています。

##  <a name="m_io"></a>COleInsertDialog:: m_io

[オブジェクトの挿入] ダイアログボックスの動作を制御するために使用される OLEUIINSERTOBJECT 型の構造。

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>コメント

この構造体のメンバーは、直接またはメンバー関数を使用して変更できます。

詳細については、Windows SDK の[OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw)構造体を参照してください。

## <a name="see-also"></a>参照

[MFC サンプル OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
