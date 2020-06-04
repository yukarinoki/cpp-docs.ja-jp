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
ms.openlocfilehash: b5de4ff5daa80e1d8727444a4cfd275597e18c08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374970"
---
# <a name="coleinsertdialog-class"></a>COleInsertDialog クラス

OLE の [オブジェクトの挿入] ダイアログ ボックスで使用されます。

## <a name="syntax"></a>構文

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::コレクル挿入ダイアログ](#coleinsertdialog)|`COleInsertDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::アイテムの作成](#createitem)|ダイアログ ボックスで選択した項目を作成します。|
|[ダイアログ ボックスを:Do モーダル](#domodal)|[OLE オブジェクトの挿入] ダイアログ ボックスを表示します。|
|[ダイアログボックス::クラスIDを取得します。](#getclassid)|選択した項目に関連付けられている CLSID を取得します。|
|[ダイアログ::取得ドローアスペクト](#getdrawaspect)|アイテムをアイコンとして描画するかどうかを指定します。|
|[ダイアログボックス::取得アイコンメタファイル](#geticonicmetafile)|このアイテムのアイコン形式に関連付けられているメタファイルへのハンドルを取得します。|
|[ダイアログボックス::パス名を取得します。](#getpathname)|ダイアログ ボックスで選択したファイルへの完全パスを取得します。|
|[ダイアログボックス::選択タイプを取得します。](#getselectiontype)|選択されたオブジェクトの種類を取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ::m_io](#m_io)|ダイアログ ボックスの動作を制御する OLEUIINSERT オブジェクト型の構造体。|

## <a name="remarks"></a>解説

このダイアログ ボックスを`COleInsertDialog`呼び出す場合は、クラスのオブジェクトを作成します。 オブジェクトを`COleInsertDialog`構築した後[、m_io](#m_io)構造を使用して、ダイアログ ボックス内のコントロールの値または状態を初期化できます。 構造体`m_io`の型は OLEUIINSERT オブジェクトです。 このダイアログ クラスの使用方法の詳細については[、DoModal](#domodal)メンバー関数を参照してください。

> [!NOTE]
> アプリケーション ウィザードで生成されたコンテナー コードでは、このクラスを使用します。

詳細については、Windows SDK の[「OLEUIINSERT オブジェクト](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw)」構造を参照してください。

OLE 固有のダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

## <a name="coleinsertdialogcoleinsertdialog"></a><a name="coleinsertdialog"></a>ダイアログボックス::コレクル挿入ダイアログ

この関数は`COleInsertDialog`オブジェクトのみを構築します。

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
ビットごとの OR 演算子を使用して結合される次の値の任意の数を含む作成フラグ。

- IOF_SHOWHELP ダイアログ ボックスが呼び出されたときに [ヘルプ] ボタンが表示されるように指定します。

- IOF_SELECTCREATENEW ダイアログ ボックスが呼び出されたときに、[新規作成] ラジオ ボタンが最初に選択されるように指定します。 これはデフォルトであり、IOF_SELECTCREATEFROMFILEと一緒に使用することはできません。

- IOF_SELECTCREATEFROMFILE ダイアログ ボックスが呼び出されたときに、[ファイルから作成] オプション ボタンが最初に選択されるように指定します。 IOF_SELECTCREATENEWと併用することはできません。

- IOF_CHECKLINK ダイアログ ボックスが呼び出されたときに、[リンク] チェック ボックスが最初にオンになることを指定します。

- IOF_DISABLELINK ダイアログ ボックスが呼び出されたときに[リンク]チェック ボックスが無効になります。

- IOF_CHECKDISPLAYASICON アイコンとして表示チェックボックスを最初にオンにし、現在のアイコンが表示され、ダイアログ ボックスが呼び出されたときに [アイコンの変更] ボタンが有効になります。

- IOF_VERIFYSERVERSEXIST登録データベースに指定されたサーバーがダイアログ ボックスを表示する前に存在することを確認して、ダイアログ ボックスに追加するクラスをリスト ボックスに検証するように指定します。 このフラグを設定すると、パフォーマンスが大幅に低下する可能性があります。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する (型`CWnd`) の親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクトへのポインター。 NULL の場合、ダイアログ オブジェクトの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

ダイアログ ボックスを表示するには[、DoModal](#domodal)関数を呼び出します。

## <a name="coleinsertdialogcreateitem"></a><a name="createitem"></a>ダイアログボックス::アイテムの作成

この関数を呼び出して、型[の](../../mfc/reference/coleclientitem-class.md)オブジェクトを作成する場合に限り[、操作は](#domodal)IDOK を返します。

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
作成するアイテムへのポイント。

### <a name="return-value"></a>戻り値

項目が作成された場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数を呼`COleClientItem`び出す前に、オブジェクトを割り当てる必要があります。

## <a name="coleinsertdialogdomodal"></a><a name="domodal"></a>ダイアログ ボックスを:Do モーダル

OLE オブジェクトの挿入] ダイアログ ボックスを表示します。

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
次のいずれかの値:

`COleInsertDialog::DocObjectsOnly`は、Doc オブジェクトのみを挿入します。

`COleInsertDialog::ControlsOnly`は ActiveX コントロールのみを挿入します。

ゼロは、DocObject コントロールも ActiveX コントロールも挿入されません。 この値は、上記の最初のプロトタイプと同じ実装になります。

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値:

- ダイアログ ボックスが正常に表示された場合は IDOK。

- ユーザーがダイアログ ボックスをキャンセルした場合は、IDCANCEL を指定します。

- エラーが発生した場合は、IDABORT を実行します。 IDABORT が返された場合は、発生したエラーの種類に関する詳細情報を取得するのには[、COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)メンバー関数を呼び出します。 考えられるエラーの一覧については、Windows SDK の[「OleUIInsertObject](/windows/win32/api/oledlg/nf-oledlg-oleuiinsertobjectw)関数」を参照してください。

### <a name="remarks"></a>解説

[m_io](#m_io)構造体のメンバを設定してさまざまなダイアログ ボックス コントロールを初期化する場合は、ダイアログ オブジェクトを作成`DoModal`した後で呼び出す前に、この操作を行う必要があります。

IDOK が返された場合`DoModal`は、他のメンバー関数を呼び出して、ユーザーがダイアログ ボックスに入力した設定または情報を取得できます。

## <a name="coleinsertdialoggetclassid"></a><a name="getclassid"></a>ダイアログボックス::クラスIDを取得します。

[DoModal](#domodal)が IDOK を返し、選択タイプが`COleInsertDialog::createNewItem`の場合にのみ、選択した項目に関連付けられた CLSID を取得します。

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>戻り値

選択した項目に関連付けられている CLSID を返します。

### <a name="remarks"></a>解説

詳細については、Windows SDK[の CLSID キー](/windows/win32/com/clsid-key-hklm)を参照してください。

## <a name="coleinsertdialoggetdrawaspect"></a><a name="getdrawaspect"></a>ダイアログ::取得ドローアスペクト

選択した項目をアイコンとして表示するかどうかを調べます。

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>戻り値

オブジェクトのレンダリングに必要なメソッド。

- DVASPECT_CONTENT アイコンとして表示] チェック ボックスがオフの場合は返されます。

- DVASPECT_ICON アイコンとして表示 チェックボックスがオンの場合に返されます。

### <a name="remarks"></a>解説

この関数は[、DoModal](#domodal)が IDOK を返す場合にのみ呼び出されます。

描画の側面の詳細については、Windows SDK[の FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)データ構造を参照してください。

## <a name="coleinsertdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>ダイアログボックス::取得アイコンメタファイル

選択した項目のアイコン的な側面を含むメタファイルへのハンドルを取得します。

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>戻り値

ダイアログボックスが閉じられたときに [アイコンで表示] チェック ボックスがオンの場合は **、[OK]** をクリックして、選択した項目のアイコンを含むメタファイルへのハンドル。それ以外の場合は NULL。

## <a name="coleinsertdialoggetpathname"></a><a name="getpathname"></a>ダイアログボックス::パス名を取得します。

[DoModal](#domodal)が IDOK を返し、選択タイプがでない`COleInsertDialog::createNewItem`場合にのみ、選択したファイルの完全なパスを取得します。

```
CString GetPathName() const;
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスで選択したファイルへの完全パス。 選択の種類が`createNewItem`の場合、この関数はリリース`CString`モードでは無意味を返すか、デバッグ モードでアサーションを発生させます。

## <a name="coleinsertdialoggetselectiontype"></a><a name="getselectiontype"></a>ダイアログボックス::選択タイプを取得します。

**[OK]** をクリックして [オブジェクトの挿入] ダイアログ ボックスが閉じられたときに選択した種類を取得します。

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>戻り値

選択の種類です。

### <a name="remarks"></a>解説

戻り値の型の値は`Selection`、クラスで宣言された`COleInsertDialog`列挙型によって指定されます。

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

これらの値の簡単な説明は次のとおりです。

- `COleInsertDialog::createNewItem`[新規作成] ラジオ ボタンが選択されました。

- `COleInsertDialog::insertFromFile`[ファイルから作成] オプション ボタンが選択され、[リンク] チェック ボックスがオフになっていません。

- `COleInsertDialog::linkToFile`[ファイルから作成] ラジオ ボタンが選択され、[リンク] チェック ボックスがオンになっています。

## <a name="coleinsertdialogm_io"></a><a name="m_io"></a>ダイアログ::m_io

オブジェクトの挿入ダイアログ ボックスの動作を制御するために使用される OLEUIINSERT オブジェクト型の構造体。

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>解説

この構造体のメンバーは、直接またはメンバー関数を通じて変更できます。

詳細については、Windows SDK の[「OLEUIINSERT オブジェクト](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw)」構造を参照してください。

## <a name="see-also"></a>関連項目

[サンプル O クライアント](../../overview/visual-cpp-samples.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
