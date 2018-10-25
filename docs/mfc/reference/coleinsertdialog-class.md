---
title: COleInsertDialog クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8687826734439532ecc429f6ecd61adf4aeb4ca
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077258"
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
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|`COleInsertDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クリック](#createitem)|ダイアログ ボックスで選択した項目を作成します。|
|[COleInsertDialog::DoModal](#domodal)|OLE の [オブジェクトの挿入] ダイアログ ボックスが表示されます。|
|[COleInsertDialog::GetClassID](#getclassid)|選択した項目に関連付けられた CLSID を取得します。|
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|アイコンとして項目を描画するかどうかを通知します。|
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|この項目の象徴的な形式に関連付けられているメタファイルを識別するハンドルを取得します。|
|[COleInsertDialog::GetPathName](#getpathname)|ダイアログ ボックスで選択したファイルへの完全パスを取得します。|
|[COleInsertDialog::GetSelectionType](#getselectiontype)|選択したオブジェクトの種類を取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleInsertDialog::m_io](#m_io)|ダイアログ ボックスの動作を制御する使う型の構造体。|

## <a name="remarks"></a>Remarks

クラスのオブジェクトを作成`COleInsertDialog`をこのダイアログ ボックスを呼び出す場合します。 後に、`COleInsertDialog`オブジェクトが構築された、使用することができます、 [m_io](#m_io)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_io`構造が使う型。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。

> [!NOTE]
>  アプリケーション コンテナーのウィザードで生成されたコードでは、このクラスを使用します。

詳細については、次を参照してください。、[使う](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta)Windows SDK の構造体。

OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。

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

##  <a name="coleinsertdialog"></a>  COleInsertDialog::COleInsertDialog

この関数の作成のみを`COleInsertDialog`オブジェクト。

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
任意の数のビットごとの OR 演算子を使用して結合するのには、次の値を含む作成フラグ:

- IOF_SHOWHELP では、ダイアログ ボックスが呼び出されたときに、[ヘルプ] ボタンが表示されることを指定します。

- IOF_SELECTCREATENEW 指定新規作成のオプション ボタンとなる最初に選択 ダイアログ ボックスが呼び出された場合。 これは、既定であり、IOF_SELECTCREATEFROMFILE では使用できません。

- IOF_SELECTCREATEFROMFILE 指定からファイルの作成のオプション ボタンとなる最初に選択 ダイアログ ボックスが呼び出された場合。 IOF_SELECTCREATENEW では使用できません。

- IOF_CHECKLINK では、リンクする チェック ボックスをオンになることを指定しますチェック最初に、ダイアログ ボックスが呼び出された場合。

- ダイアログ ボックスが呼び出されたときに IOF_DISABLELINK 指定リンク チェック ボックスをオンを無効化されます。

- IOF_CHECKDISPLAYASICON では、アイコンで表示 チェック ボックスを最初にチェックが、現在のアイコンが表示されますおよび ダイアログ ボックスが呼び出されたときに、アイコンの変更 ボタンが有効にすることを指定します。

- ダイアログ ボックスが表示される前に、登録情報データベースで指定されたサーバーが存在することを確認して、リスト ボックスに追加 IOF_VERIFYSERVERSEXIST では、ダイアログ ボックスが、クラスを検証する必要がありますを指定します。 このフラグを設定すると、パフォーマンスが低下することができますが大幅にします。

*pParentWnd*<br/>
親またはオーナー ウィンドウのオブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログのオブジェクトの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。

### <a name="remarks"></a>Remarks

ダイアログ ボックスを表示するには[DoModal](#domodal)関数。

##  <a name="createitem"></a>  クリック

型のオブジェクトを作成するには、この関数を呼び出す[COleClientItem](../../mfc/reference/coleclientitem-class.md)場合にのみ[DoModal](#domodal) IDOK を返します。

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
作成される項目へのポインター。

### <a name="return-value"></a>戻り値

アイテムが作成された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

割り当てる必要があります、`COleClientItem`オブジェクトの前に、この関数を呼び出すことができます。

##  <a name="domodal"></a>  COleInsertDialog::DoModal

OLE の [オブジェクトの挿入] ダイアログ ボックスを表示するには、この関数を呼び出します。

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
次のいずれかの値です。

`COleInsertDialog::DocObjectsOnly` DocObjects のみを挿入します。

`COleInsertDialog::ControlsOnly` ActiveX コントロールのみを挿入します。

0 は、DocObject も ActiveX コントロールを挿入します。 上記の最初のプロトタイプとして同じ実装にこの値は結果が表示されます。

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログ ボックスが正常に表示されている場合。

- ユーザーには、ダイアログ ボックスが取り消された場合は IDCANCEL。

- IDABORT 場合は、エラーが発生しました。 IDABORT が返される場合、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)発生したエラーの種類に関する詳細を取得します。 考えられるエラーの一覧については、次を参照してください。、[使う](/windows/desktop/api/oledlg/nf-oledlg-oleuiinsertobjecta)Windows SDK 内の関数。

### <a name="remarks"></a>Remarks

メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、 [m_io](#m_io)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。

場合`DoModal`返します IDOK、他のメンバーの設定またはユーザーがダイアログ ボックスに情報の入力を取得する関数を呼び出すことができます。

##  <a name="getclassid"></a>  COleInsertDialog::GetClassID

選択した項目のみの場合に関連付けられている CLSID を取得するには、この関数を呼び出す[DoModal](#domodal) IDOK、選択の種類が返されます`COleInsertDialog::createNewItem`します。

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>戻り値

選択した項目に関連付けられている CLSID を返します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [CLSID キー](/windows/desktop/com/clsid-key-hklm) Windows SDK に含まれています。

##  <a name="getdrawaspect"></a>  COleInsertDialog::GetDrawAspect

ユーザーがアイコンとして選択した項目を表示する選択したかどうかを判断するには、この関数を呼び出します。

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>戻り値

メソッドは、オブジェクトを表示するために必要です。

- アイコンで表示 チェック ボックスがオフの場合、DVASPECT_CONTENT が返されます。

- アイコンで表示 チェック ボックスがオンにした場合、DVASPECT_ICON が返されます。

### <a name="remarks"></a>Remarks

場合にのみ、この関数を呼び出す[DoModal](#domodal) IDOK を返します。

描画の側面の詳細については、次を参照してください。 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK 内のデータ構造。

##  <a name="geticonicmetafile"></a>  COleInsertDialog::GetIconicMetafile

選択した項目のアイコンの外観を含むメタファイルを識別するハンドルを取得するには、この関数を呼び出します。

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>戻り値

アイコンで表示する チェック ボックスをオンにした場合は、選択した項目のアイコンの外観を含むメタファイルを識別するハンドルを選択して、ダイアログが終了したときにオンになって**OK**null それ以外の場合。

##  <a name="getpathname"></a>  COleInsertDialog::GetPathName

場合にのみ、選択したファイルの完全なパスを取得するには、この関数を呼び出す[DoModal](#domodal) IDOK、選択の種類がないが返されます`COleInsertDialog::createNewItem`します。

```
CString GetPathName() const;
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスで選択されたファイルの完全パスです。 選択の種類がある場合`createNewItem`、この関数は、意味のない返します`CString`リリース モードでやアサーションをデバッグ モードで発生します。

##  <a name="getselectiontype"></a>  COleInsertDialog::GetSelectionType

選択して、オブジェクトの挿入 ダイアログ ボックスが終了したときに選択した型を取得するには、この関数を呼び出す**OK**します。

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>戻り値

選択された型。

### <a name="remarks"></a>Remarks

戻り値の型の値がで指定された、`Selection`で宣言された列挙型、`COleInsertDialog`クラス。

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

これらの値の簡単な説明に従います。

- `COleInsertDialog::createNewItem` 新規作成のラジオ ボタンが選択されました。

- `COleInsertDialog::insertFromFile` ファイルからのラジオ ボタンを選択し、[リンク] チェック ボックスがオフです。

- `COleInsertDialog::linkToFile` ファイルからのラジオ ボタンを選択し、リンク チェック ボックスがオンにします。

##  <a name="m_io"></a>  COleInsertDialog::m_io

使う型の構造体オブジェクトの挿入 ダイアログ ボックスの動作を制御するために使用します。

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>Remarks

この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。

詳細については、次を参照してください。、[使う](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiinsertobjecta)Windows SDK の構造体。

## <a name="see-also"></a>関連項目

[MFC サンプルの OCLIENT](../../visual-cpp-samples.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
