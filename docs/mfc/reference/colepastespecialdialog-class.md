---
title: COlePasteSpecialDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
ms.openlocfilehash: f4174369620f14f2d1ac410aa5d756c75097ad0f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855606"
---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog クラス

OLE の [形式を選択して貼り付け] ダイアログ ボックス用に使用されます。

## <a name="syntax"></a>構文

```
class COlePasteSpecialDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|`COlePasteSpecialDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[COlePasteSpecialDialog:: AddFormat](#addformat)|アプリケーションで貼り付けることができる形式の一覧にカスタム書式を追加します。|
|[COlePasteSpecialDialog:: AddLinkEntry](#addlinkentry)|サポートされているクリップボード形式の一覧に新しいエントリを追加します。|
|[COlePasteSpecialDialog:: AddStandardFormats](#addstandardformats)|アプリケーションで貼り付けることができる形式の一覧に、CF_BITMAP、CF_DIB、CF_METAFILEPICT、および必要に応じて CF_LINKSOURCE を追加します。|
|[COlePasteSpecialDialog:: CreateItem](#createitem)|指定された書式を使用して、コンテナードキュメントに項目を作成します。|
|[COlePasteSpecialDialog::D oModal](#domodal)|OLE の [特殊な貼り付け] ダイアログボックスを表示します。|
|[COlePasteSpecialDialog:: GetDrawAspect](#getdrawaspect)|項目をアイコンとして描画するかどうかを示します。|
|[COlePasteSpecialDialog:: Geが Onicmetafile](#geticonicmetafile)|この項目のアイコン化形式に関連付けられているメタファイルへのハンドルを取得します。|
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|ユーザーによって選択された使用可能な貼り付けオプションのインデックスを取得します。|
|[COlePasteSpecialDialog:: GetSelectionType](#getselectiontype)|選択された選択の種類を取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|Description|
|----------|-----------------|
|[COlePasteSpecialDialog:: m_ps](#m_ps)|ダイアログボックスの機能を制御する OLEUIPASTESPECIAL 型の構造体。|

## <a name="remarks"></a>解説

このダイアログボックスを呼び出す必要がある場合は `COlePasteSpecialDialog` クラスのオブジェクトを作成します。 `COlePasteSpecialDialog` オブジェクトが構築されたら、 [Addformat](#addformat)および[addstandardformats](#addstandardformats)メンバー関数を使用して、ダイアログボックスにクリップボード形式を追加できます。 また、 [m_ps](#m_ps)構造を使用して、ダイアログボックス内のコントロールの値または状態を初期化することもできます。 `m_ps` 構造体の型は OLEUIPASTESPECIAL です。

詳細については、Windows SDK の[OLEUIPASTESPECIAL](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw)構造体を参照してください。

OLE 固有のダイアログボックスの詳細については、 [ole の記事のダイアログボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePasteSpecialDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs

##  <a name="addformat"></a>COlePasteSpecialDialog:: AddFormat

この関数を呼び出して、アプリケーションが貼り付けの特別な操作でサポートできる形式の一覧に新しい形式を追加します。

```
void AddFormat(
    const FORMATETC& formatEtc,
    LPTSTR lpszFormat,
    LPTSTR lpszResult,
    DWORD flags);

void AddFormat(
    UINT cf,
    DWORD tymed,
    UINT nFormatID,
    BOOL bEnableIcon,
    BOOL bLink);
```

### <a name="parameters"></a>パラメーター

*fmt*<br/>
追加するデータ型への参照。

*lpszFormat*<br/>
ユーザーの形式を説明する文字列。

*lpszResult*<br/>
ダイアログボックスでこの形式を選択した場合の結果を説明する文字列。

*flags*<br/>
この形式では、さまざまなリンクおよび埋め込みオプションを使用できます。 このフラグは、OLEUIPASTEFLAG 列挙型の1つ以上の異なる値のビットごとの組み合わせです。

*cf*<br/>
追加するクリップボード形式。

*tymed*<br/>
この形式で使用できるメディアの種類。 これは、列挙型の型の1つ以上の値のビットごとの組み合わせです。

*nFormatID*<br/>
この形式を識別する文字列の ID。 この文字列の形式は、' \n ' 文字で区切られた2つの個別の文字列です。 最初の文字列は、 *Lpstrformat*パラメーターで渡されるものと同じで、2番目の文字列は*lpstrformat*パラメーターと同じです。

*bEnableIcon*<br/>
この形式がリストボックスで選択されている場合に、[アイコンとして表示] チェックボックスがオンになっているかどうかを示すフラグです。

*間隔*<br/>
この形式がリストボックスで選択されている場合に [リンクを貼り付ける] オプションボタンが有効かどうかを示すフラグです。

### <a name="remarks"></a>解説

この関数を呼び出して、CF_TEXT、CF_TIFF などの標準形式、またはアプリケーションがシステムに登録したカスタム形式を追加できます。 アプリケーションへのデータオブジェクトの貼り付けの詳細については、「[データオブジェクトとデータソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)」を参照してください。

詳細については、Windows SDK の「 [Tymed](/windows/win32/api/objidl/ne-objidl-tymed)列挙型」と「 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体」を参照してください。

詳細については、Windows SDK の「 [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag)列挙型」を参照してください。

##  <a name="addlinkentry"></a>COlePasteSpecialDialog:: AddLinkEntry

サポートされているクリップボード形式の一覧に新しいエントリを追加します。

```
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```

### <a name="parameters"></a>パラメーター

*cf*<br/>
追加するクリップボード形式。

### <a name="return-value"></a>戻り値

新しいリンクエントリの情報を格納している[OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag)構造体。

##  <a name="addstandardformats"></a>COlePasteSpecialDialog:: AddStandardFormats

次のクリップボード形式を、貼り付けの特殊な操作でアプリケーションがサポートできる形式の一覧に追加するには、この関数を呼び出します。

```
void AddStandardFormats(BOOL bEnableLink = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnableLink*<br/>
アプリケーションで貼り付けることができる形式の一覧に CF_LINKSOURCE を追加するかどうかを決定するフラグ。

### <a name="remarks"></a>解説

- CF_BITMAP

- CF_DIB

- CF_METAFILEPICT

- **"埋め込みオブジェクト"**

- オプション **"リンクソース"**

これらの形式は、埋め込みとリンクをサポートするために使用されます。

##  <a name="colepastespecialdialog"></a>COlePasteSpecialDialog::COlePasteSpecialDialog

`COlePasteSpecialDialog` オブジェクトを構築します。

```
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,
    COleDataObject* pDataObject = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
作成フラグ。ビットごとの OR 演算子を使用して、次のフラグを組み合わせて指定します。

- PSF_SELECTPASTE、ダイアログボックスが呼び出されたときに、[貼り付け] オプションボタンが最初にチェックされるように指定します。 PSF_SELECTPASTELINK と組み合わせて使用することはできません。 これは既定値です。

- PSF_SELECTPASTELINK、ダイアログボックスが呼び出されたときに、[リンクの貼り付け] オプションボタンが最初にチェックされるように指定します。 PSF_SELECTPASTE と組み合わせて使用することはできません。

- PSF_CHECKDISPLAYASICON、ダイアログボックスが呼び出されたときに、[アイコンとして表示] チェックボックスが最初にオンになるように指定します。

- PSF_SHOWHELP、ダイアログボックスが呼び出されたときに [ヘルプ] ボタンが表示されることを指定します。

*pDataObject*<br/>
貼り付ける[COleDataObject](../../mfc/reference/coledataobject-class.md)をポイントします。 この値が NULL の場合は、クリップボードから `COleDataObject` を取得します。

*pParentWnd*<br/>
ダイアログオブジェクトが属する親またはオーナーウィンドウオブジェクト (`CWnd`型) を指します。 NULL の場合は、ダイアログボックスの親ウィンドウがメインアプリケーションウィンドウに設定されます。

### <a name="remarks"></a>解説

この関数は、`COlePasteSpecialDialog` オブジェクトのみを構築します。 ダイアログボックスを表示するには、 [DoModal](#domodal)関数を呼び出します。

詳細については、Windows SDK の「 [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag)列挙型」を参照してください。

##  <a name="createitem"></a>COlePasteSpecialDialog:: CreateItem

[特殊な貼り付け] ダイアログボックスで選択された新しい項目を作成します。

```
BOOL CreateItem(COleClientItem* pNewItem);
```

### <a name="parameters"></a>パラメーター

*pNewItem*<br/>
`COleClientItem` インスタンスを指します。 NULL にすることはできません。

### <a name="return-value"></a>戻り値

項目が正常に作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、 [DoModal](#domodal)から IDOK が返された後にのみ呼び出す必要があります。

##  <a name="domodal"></a>COlePasteSpecialDialog::D oModal

OLE の [特殊な貼り付け] ダイアログボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログボックスの完了ステータス。 次のいずれかの値:

- IDOK ダイアログボックスが正常に表示された場合は。

- ユーザーがダイアログボックスをキャンセルした場合は IDCANCEL。

- エラーが発生した場合は IDABORT。 IDABORT が返された場合は、`COleDialog::GetLastError` メンバー関数を呼び出して、発生したエラーの種類に関する詳細情報を取得します。 考えられるエラーの一覧については、Windows SDK の「 [OleUIPasteSpecial](/windows/win32/api/oledlg/nf-oledlg-oleuipastespecialw)関数」を参照してください。

### <a name="remarks"></a>解説

[M_ps](#m_ps)構造体のメンバーを設定してさまざまなダイアログボックスコントロールを初期化する場合は、`DoModal`を呼び出す前にこの操作を行う必要がありますが、ダイアログオブジェクトが構築された後に実行する必要があります。

`DoModal` が IDOK を返す場合は、他のメンバー関数を呼び出して、ダイアログボックスにユーザーが入力した設定または情報を取得できます。

##  <a name="getdrawaspect"></a>COlePasteSpecialDialog:: GetDrawAspect

選択した項目をアイコンとして表示することをユーザーが選択したかどうかを判断します。

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>戻り値

オブジェクトを表示するために必要なメソッド。

- ダイアログボックスが閉じられたときに [アイコンとして表示] チェックボックスがオンになっていない場合に DVASPECT_CONTENT 返されます。

- ダイアログボックスが閉じられたときに [アイコンとして表示] チェックボックスがオンになっている場合に DVASPECT_ICON 返されます。

### <a name="remarks"></a>解説

[DoModal](#domodal)が IDOK を返す場合にのみ、この関数を呼び出します。

アスペクトの描画の詳細については、Windows SDK の[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を参照してください。

##  <a name="geticonicmetafile"></a>COlePasteSpecialDialog:: Geが Onicmetafile

ユーザーによって選択された項目に関連付けられたメタファイルを取得します。

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>戻り値

**[OK**] をクリックしてダイアログボックスを閉じたときに [アイコンとして表示] チェックボックスをオンにした場合に、選択した項目のアイコンの側面を含むメタファイルへのハンドル。それ以外の場合は NULL。

##  <a name="getpasteindex"></a>COlePasteSpecialDialog::GetPasteIndex

ユーザーが選択したエントリに関連付けられているインデックス値を取得します。

```
int GetPasteIndex() const;
```

### <a name="return-value"></a>戻り値

ユーザーによって選択された `OLEUIPASTEENTRY` 構造体の配列内のインデックス。 貼り付け操作を実行するときに、選択したインデックスに対応する形式を使用する必要があります。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[OLEUIPASTEENTRY](/windows/win32/api/oledlg/ns-oledlg-oleuipasteentryw)構造体を参照してください。

##  <a name="getselectiontype"></a>COlePasteSpecialDialog:: GetSelectionType

ユーザーが選択した選択の種類を決定します。

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>戻り値

選択された型を返します。

### <a name="remarks"></a>解説

戻り値の型の値は、`COlePasteSpecialDialog` クラスで宣言された `Selection` 列挙型によって指定されます。

```
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };
```

これらの値の Brief desccriptions は次のとおりです。

- `COlePasteSpecialDialog::pasteLink`、[リンクの貼り付け] オプションがオンになっており、選択した形式が標準の OLE 形式でした。

- `COlePasteSpecialDialog::pasteNormal` 貼り付ける オプションボタンがオンになっており、選択した形式が標準の OLE 形式でした。

- 選択した形式は、標準の OLE 形式ではありません `COlePasteSpecialDialog::pasteOther`。

- 選択された形式がメタファイルである `COlePasteSpecialDialog::pasteStatic` ます。

##  <a name="m_ps"></a>COlePasteSpecialDialog:: m_ps

[特殊な貼り付け] ダイアログボックスの動作を制御するために使用される OLEUIPASTESPECIAL 型の構造。

```
OLEUIPASTESPECIAL m_ps;
```

### <a name="remarks"></a>解説

この構造体のメンバーは、直接、またはメンバー関数を使用して変更できます。

詳細については、Windows SDK の[OLEUIPASTESPECIAL](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw)構造体を参照してください。

## <a name="see-also"></a>参照

[MFC サンプル OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
