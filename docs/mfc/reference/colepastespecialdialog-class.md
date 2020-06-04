---
title: クラスをクリックします。
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
ms.openlocfilehash: 47fb421ef9dedcae7f92d33f55988dbbc2ea452d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753818"
---
# <a name="colepastespecialdialog-class"></a>クラスをクリックします。

OLE の [形式を選択して貼り付け] ダイアログ ボックス用に使用されます。

## <a name="syntax"></a>構文

```
class COlePasteSpecialDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クリックして、ダイアログ ボックス:::クリックして貼り付け特別なダイアログ をクリックします。](#colepastespecialdialog)|`COlePasteSpecialDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::フォーマットの追加](#addformat)|アプリケーションで貼り付けることができる形式の一覧にカスタム書式を追加します。|
|[クリックしてダイアログ を追加します。](#addlinkentry)|サポートされているクリップボード形式の一覧に新しいエントリを追加します。|
|[ダイアログボックス::標準書式の追加](#addstandardformats)|CF_BITMAP、CF_DIB、CF_METAFILEPICT、およびオプションでCF_LINKSOURCEをアプリケーションが貼り付けることができる形式の一覧に追加します。|
|[クリックメニュー::アイテムの作成](#createitem)|指定した形式を使用して、コンテナー ドキュメント内のアイテムを作成します。|
|[クリックして、次の値を :Dクリックします。](#domodal)|[OLE 形式を選択して貼り付け] ダイアログ ボックスを表示します。|
|[クリックしてダイアログ をクリックします。](#getdrawaspect)|アイテムをアイコンとして描画するかどうかを指定します。|
|[クリックメニュー::アイコンメタファイル](#geticonicmetafile)|このアイテムのアイコン形式に関連付けられているメタファイルへのハンドルを取得します。|
|[クリックしてダイアログ をクリックします。](#getpasteindex)|ユーザーが選択した使用可能な貼り付けオプションのインデックスを取得します。|
|[クリックしてダイアログ をクリックします。](#getselectiontype)|選択した選択の種類を取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[クリックして、ダイアログ::m_ps](#m_ps)|ダイアログ ボックスの機能を制御する OLEUIPASTESPECIAL 型の構造体。|

## <a name="remarks"></a>解説

このダイアログ ボックスを`COlePasteSpecialDialog`呼び出す場合は、クラスのオブジェクトを作成します。 オブジェクトを`COlePasteSpecialDialog`作成した後[、AddFormat](#addformat)および[AddStandardFormats](#addstandardformats)メンバー関数を使用して、クリップボード形式をダイアログ ボックスに追加できます。 ダイアログ ボックスのコントロールの値または状態を初期化するのに[m_ps](#m_ps)構造を使用することもできます。 構造体`m_ps`の型は OLEUIPASTESPECIAL です。

詳細については、Windows SDK の[「OLEUIPASTESPECIALSPECIAL」](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw)構造を参照してください。

OLE 固有のダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePasteSpecialDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

## <a name="colepastespecialdialogaddformat"></a><a name="addformat"></a>ダイアログボックス::フォーマットの追加

この関数を呼び出して、アプリケーションが [形式を選択して貼り付け] 操作でサポートできる形式の一覧に新しい形式を追加します。

```cpp
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

*Fmt*<br/>
追加するデータ型への参照。

*フォーマット*<br/>
ユーザーに対する形式を説明する文字列。

*結果を表示します。*<br/>
ダイアログ ボックスでこの形式が選択された場合の結果を説明する文字列です。

*フラグ*<br/>
この形式で使用できるさまざまなリンクと埋め込みオプション。 このフラグは、OLEUIPASTEFLAG 列挙型の 1 つ以上の異なる値のビットごとの組み合わせです。

*Cf*<br/>
追加するクリップボード形式。

*Tymed*<br/>
この形式で使用できるメディアの種類。 これは TYMED 列挙型の 1 つ以上の値のビットごとの組み合わせです。

*データを持つ*<br/>
この形式を識別する文字列の ID。 この文字列の形式は、2 つの個別の文字列を '\n' 文字で区切った文字列です。 最初の文字列は *、lpstrFormat*パラメーターで渡されるのと同じで、2 番目の文字列は*lpstrResult*パラメーターと同じです。

*アイコンをクリックします。*<br/>
この形式がリスト ボックスで選択されている場合に、[アイコンとして表示] チェック ボックスを有効にするかどうかを指定するフラグです。

*点滅*<br/>
リスト ボックスでこの形式が選択されている場合に、[リンク貼り付け] オプション ボタンを有効にするかどうかを指定するフラグです。

### <a name="remarks"></a>解説

この関数を呼び出して、アプリケーションがシステムに登録したCF_TEXT形式やCF_TIFF形式などの標準書式を追加したり、カスタムフォーマットを追加したりできます。 アプリケーションへのデータ オブジェクトの貼り付けの詳細については、「[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)」を参照してください。

詳細については、Windows SDK の[TYMED](/windows/win32/api/objidl/ne-objidl-tymed)列挙型と[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を参照してください。

詳細については、Windows SDK の[列挙](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag)型を参照してください。

## <a name="colepastespecialdialogaddlinkentry"></a><a name="addlinkentry"></a>クリックしてダイアログ を追加します。

サポートされているクリップボード形式の一覧に新しいエントリを追加します。

```
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```

### <a name="parameters"></a>パラメーター

*Cf*<br/>
追加するクリップボード形式。

### <a name="return-value"></a>戻り値

新しいリンク エントリの情報を含[む構造体。](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag)

## <a name="colepastespecialdialogaddstandardformats"></a><a name="addstandardformats"></a>ダイアログボックス::標準書式の追加

この関数を呼び出して、アプリケーションが [形式を選択して貼り付け] 操作でサポートできる形式の一覧に、次のクリップボード形式を追加します。

```cpp
void AddStandardFormats(BOOL bEnableLink = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効リンク*<br/>
アプリケーションで貼り付けることができる形式の一覧にCF_LINKSOURCEを追加するかどうかを指定するフラグ。

### <a name="remarks"></a>解説

- CF_BITMAP

- CF_DIB

- CF_METAFILEPICT

- **"埋め込みオブジェクト"**

- (オプション)**"リンクソース"**

これらの形式は、埋め込みとリンクをサポートするために使用されます。

## <a name="colepastespecialdialogcolepastespecialdialog"></a><a name="colepastespecialdialog"></a>クリックして、ダイアログ ボックス:::クリックして貼り付け特別なダイアログ をクリックします。

`COlePasteSpecialDialog` オブジェクトを構築します。

```
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,
    COleDataObject* pDataObject = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
作成フラグは、ビットごとの OR 演算子を使用して結合された次のフラグの任意の数を含みます。

- PSF_SELECTPASTE ダイアログ ボックスが呼び出されたときに、[貼り付け] オプション ボタンが最初にオンになることを指定します。 PSF_SELECTPASTELINKと組み合わせて使用することはできません。 これは既定値です。

- PSF_SELECTPASTELINK ダイアログ ボックスが呼び出されたときに、[リンクの貼り付け] オプション ボタンが最初にオンになることを指定します。 PSF_SELECTPASTEと組み合わせて使用することはできません。

- PSF_CHECKDISPLAYASICON ダイアログ ボックスが呼び出されたときに、[アイコンとして表示] チェック ボックスが最初にオンになることを指定します。

- PSF_SHOWHELP ダイアログ ボックスが呼び出されたときに [ヘルプ] ボタンが表示されるように指定します。

*オブジェクト*<br/>
貼り付け用[の COleDataObject](../../mfc/reference/coledataobject-class.md)へのポイント。 この値が NULL の場合、`COleDataObject`クリップボードからを取得します。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する (型`CWnd`) の親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクトへのポインター。 NULL の場合、ダイアログ ボックスの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

この関数は`COlePasteSpecialDialog`オブジェクトを構築するだけです。 ダイアログ ボックスを表示するには[、DoModal](#domodal)関数を呼び出します。

詳細については、Windows SDK の[列挙](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag)型を参照してください。

## <a name="colepastespecialdialogcreateitem"></a><a name="createitem"></a>クリックメニュー::アイテムの作成

[形式を選択して貼り付け] ダイアログ ボックスで選択した新しい項目を作成します。

```
BOOL CreateItem(COleClientItem* pNewItem);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
インスタンスへの`COleClientItem`ポイント。 Nll は指定できません。

### <a name="return-value"></a>戻り値

項目が正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は[、DOModal](#domodal)が IDOK を返した後にのみ呼び出す必要があります。

## <a name="colepastespecialdialogdomodal"></a><a name="domodal"></a>クリックして、次の値を :Dクリックします。

[OLE 形式を選択して貼り付け] ダイアログ ボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値:

- ダイアログ ボックスが正常に表示された場合は IDOK。

- ユーザーがダイアログ ボックスをキャンセルした場合は、IDCANCEL を指定します。

- エラーが発生した場合は、IDABORT を実行します。 IDABORT が返された場合は`COleDialog::GetLastError`、メンバー関数を呼び出して、発生したエラーの種類に関する詳細情報を取得します。 考えられるエラーの一覧については、Windows SDK の[「OleUIPaste の特別な](/windows/win32/api/oledlg/nf-oledlg-oleuipastespecialw)関数」を参照してください。

### <a name="remarks"></a>解説

[m_ps](#m_ps)構造体のメンバを設定してさまざまなダイアログ ボックス コントロールを初期化する場合は、ダイアログ オブジェクトを構築`DoModal`した後で呼び出す前に、この操作を行う必要があります。

IDOK が返された場合`DoModal`は、他のメンバー関数を呼び出して、ユーザーが入力した設定または情報をダイアログ ボックスに取得できます。

## <a name="colepastespecialdialoggetdrawaspect"></a><a name="getdrawaspect"></a>クリックしてダイアログ をクリックします。

選択した項目をアイコンとして表示するかどうかを指定します。

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>戻り値

オブジェクトのレンダリングに必要なメソッド。

- DVASPECT_CONTENT ダイアログ ボックスが閉じられたときに [アイコンで表示] チェック ボックスがオフの場合は返されます。

- DVASPECT_ICON ダイアログ ボックスが閉じられたときに [アイコンで表示] チェック ボックスがオンになっている場合は返されます。

### <a name="remarks"></a>解説

この関数は[、DoModal](#domodal)が IDOK を返した後にのみ呼び出します。

描画の側面の詳細については、Windows SDK の[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を参照してください。

## <a name="colepastespecialdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>クリックメニュー::アイコンメタファイル

ユーザーが選択した項目に関連付けられているメタファイルを取得します。

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスが閉じられたときに [アイコンとして表示] チェック ボックスが選択されている場合は **、[OK]** をクリックして、選択した項目のアイコンのアイコンを含むメタファイルへのハンドル。それ以外の場合は NULL。

## <a name="colepastespecialdialoggetpasteindex"></a><a name="getpasteindex"></a>クリックしてダイアログ をクリックします。

ユーザーが選択したエントリに関連付けられているインデックス値を取得します。

```
int GetPasteIndex() const;
```

### <a name="return-value"></a>戻り値

ユーザーが選択した構造体の`OLEUIPASTEENTRY`配列へのインデックス。 選択したインデックスに対応する形式は、貼り付け操作の実行時に使用する必要があります。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[「OLEUIPASTEENTRY」](/windows/win32/api/oledlg/ns-oledlg-oleuipasteentryw)構造を参照してください。

## <a name="colepastespecialdialoggetselectiontype"></a><a name="getselectiontype"></a>クリックしてダイアログ をクリックします。

ユーザーが行った選択の種類を決定します。

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>戻り値

選択した種類を返します。

### <a name="remarks"></a>解説

戻り値の型の値は`Selection`、クラスで宣言された`COlePasteSpecialDialog`列挙型によって指定されます。

```
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };
```

これらの値の簡潔なデッチリップは次のとおりです。

- `COlePasteSpecialDialog::pasteLink`[リンク貼り付け] オプション ボタンがオンになっており、選択した形式は標準の OLE 形式でした。

- `COlePasteSpecialDialog::pasteNormal`[貼り付け] オプション ボタンがオンになっており、選択した形式は標準の OLE 形式でした。

- `COlePasteSpecialDialog::pasteOther`選択した形式は、標準の OLE 形式ではありません。

- `COlePasteSpecialDialog::pasteStatic`選択された形式はメタファイルでした。

## <a name="colepastespecialdialogm_ps"></a><a name="m_ps"></a>クリックして、ダイアログ::m_ps

OLEUIPASTE の型の構造体を使用して、形式を選択して貼り付け] ダイアログ ボックスの動作を制御します。

```
OLEUIPASTESPECIAL m_ps;
```

### <a name="remarks"></a>解説

この構造体のメンバーは、直接またはメンバー関数を通じて変更できます。

詳細については、Windows SDK の[「OLEUIPASTESPECIALSPECIAL」](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw)構造を参照してください。

## <a name="see-also"></a>関連項目

[サンプル O クライアント](../../overview/visual-cpp-samples.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
