---
title: COleConvertDialog クラス
ms.date: 11/04/2016
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
ms.openlocfilehash: e1e13f96eb90c81127723afcacf463478b75a894
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569755"
---
# <a name="coleconvertdialog-class"></a>COleConvertDialog クラス

詳細については、次を参照してください。、 [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) Windows SDK の構造体。

## <a name="syntax"></a>構文

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|`COleConvertDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleConvertDialog::DoConvert](#doconvert)|ダイアログ ボックスで指定した変換を実行します。|
|[COleConvertDialog::DoModal](#domodal)|OLE の [項目の変更] ダイアログ ボックスが表示されます。|
|[COleConvertDialog::GetClassID](#getclassid)|選択した項目に関連付けられた CLSID を取得します。|
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|アイテムをアイコンとして描画するかどうかを指定します。|
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|この項目の象徴的な形式に関連付けられているメタファイルを識別するハンドルを取得します。|
|[COleConvertDialog::GetSelectionType](#getselectiontype)|選択の種類を取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleConvertDialog::m_cv](#m_cv)|ダイアログ ボックスの動作を制御する構造体。|

## <a name="remarks"></a>Remarks

> [!NOTE]
>  アプリケーション コンテナーのウィザードで生成されたコードでは、このクラスを使用します。

OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxodlgs.h

##  <a name="coleconvertdialog"></a>  COleConvertDialog::COleConvertDialog

のみを構築、`COleConvertDialog`オブジェクト。

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
アクティブ化または変換する項目へのポインター。

*dwFlags*<br/>
作成フラグは、次の値の任意の数が含まれていますが、ビットごとの使用を組み合わせるの or 演算子。

- CF_SELECTCONVERTTO 指定に変換するオプション ボタンとなる最初に選択 ダイアログ ボックスが呼び出された場合。 既定値です。

- CF_SELECTACTIVATEAS 指定オプション ボタンとなる最初に選択 ダイアログ ボックスが呼び出された場合。

- CF_SETCONVERTDEFAULT を指定する、クラスの CLSID がで指定された、`clsidConvertDefault`のメンバー、`m_cv`変換 ラジオ ボタンを選択すると、クラスのリスト ボックスで、既定の選択として使用される構造体。

- CF_SETACTIVATEDEFAULT を指定する、クラスの CLSID がで指定された、`clsidActivateDefault`のメンバー、`m_cv`構造のオプション ボタンを選択すると、クラスのリスト ボックスで、既定の選択として使用されます。

- CF_SHOWHELPBUTTON では、ダイアログ ボックスが呼び出されたときに、[ヘルプ] ボタンが表示されることを指定します。

*pClassID*<br/>
アクティブ化または変換する項目の CLSID を指します。 NULL の場合、CLSID に関連付けられている*pItem*使用されます。

*pParentWnd*<br/>
親またはオーナー ウィンドウのオブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ ボックスの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。

### <a name="remarks"></a>Remarks

ダイアログ ボックスを表示するには[DoModal](#domodal)関数。

詳細については、次を参照してください。 [CLSID キー](/windows/desktop/com/clsid-key-hklm)と[OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta)構造体。

##  <a name="doconvert"></a>  COleConvertDialog::DoConvert

この関数の呼び出しから正常に戻った後[DoModal](#domodal), に変換する、または型のオブジェクトをアクティブ化するか、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)。

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
アクティブ化または変換する項目へのポインター。 Nll は指定できません。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

項目が変換または変換のダイアログ ボックスでユーザーが選択されている情報に従ってアクティブにします。

##  <a name="domodal"></a>  COleConvertDialog::DoModal

OLE の [変換] ダイアログ ボックスを表示するには、この関数を呼び出します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値です。

- IDOK ダイアログ ボックスが正常に表示されている場合。

- ユーザーには、ダイアログ ボックスが取り消された場合は IDCANCEL。

- IDABORT 場合は、エラーが発生しました。 IDABORT が返される場合、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)発生したエラーの種類に関する詳細を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIConvert](/windows/desktop/api/oledlg/nf-oledlg-oleuiconverta) Windows SDK 内の関数。

### <a name="remarks"></a>Remarks

メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、 [m_cv](#m_cv)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。

場合`DoModal`返します IDOK、他のメンバーの設定や、ダイアログ ボックスに、ユーザーが入力した情報を取得する関数を呼び出すことができます。

##  <a name="getclassid"></a>  COleConvertDialog::GetClassID

[変換] ダイアログ ボックスで選択したユーザー、項目に関連付けられた、CLSID を取得するには、この関数の呼び出し。

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>戻り値

[変換] ダイアログ ボックスで選択した項目に関連付けられた CLSID。

### <a name="remarks"></a>Remarks

後でのみこの関数の呼び出し[DoModal](#domodal) IDOK を返します。

詳細については、次を参照してください。 [CLSID キー](/windows/desktop/com/clsid-key-hklm) Windows SDK に含まれています。

##  <a name="getdrawaspect"></a>  COleConvertDialog::GetDrawAspect

ユーザーがアイコンとして選択した項目を表示する選択したかどうかを判断するには、この関数を呼び出します。

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>戻り値

メソッドは、オブジェクトを表示するために必要です。

- アイコンで表示 チェック ボックスがオフの場合、DVASPECT_CONTENT が返されます。

- アイコンで表示 チェック ボックスがオンにした場合、DVASPECT_ICON が返されます。

### <a name="remarks"></a>Remarks

後でのみこの関数の呼び出し[DoModal](#domodal) IDOK を返します。

描画の側面の詳細については、次を参照してください。、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK 内のデータ構造。

##  <a name="geticonicmetafile"></a>  COleConvertDialog::GetIconicMetafile

選択した項目のアイコンの外観を含むメタファイルを識別するハンドルを取得するには、この関数を呼び出します。

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>戻り値

Ok; を選択して、ダイアログが終了したときにアイコンで表示する チェック ボックスをオンにした場合は、選択した項目のアイコンの外観を含むメタファイルを識別するハンドルのチェックそれ以外の場合は NULL です。

##  <a name="getselectiontype"></a>  COleConvertDialog::GetSelectionType

[変換] ダイアログ ボックスで選択した変換の種類を決定するには、この関数を呼び出します。

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>戻り値

選択された型。

### <a name="remarks"></a>Remarks

戻り値の型の値がで指定された、`Selection`で宣言された列挙型、`COleConvertDialog`クラス。

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

これらの値の簡単な説明に従います。

- `COleConvertDialog::noConversion` かどうかは、ダイアログ ボックスが取り消されたまたは、ユーザーが選択されていない変換いずれかが返されます。 場合`COleConvertDialog::DoModal`IDOK が返されることは、ユーザーが既に選択されている 1 つとは異なるアイコンを選択します。

- `COleConvertDialog::convertItem` ユーザーに変換するさまざまな項目を選択して変換 ラジオ ボタンがオンにした場合に返されると`DoModal`IDOK が返されます。

- `COleConvertDialog::activateAs` ユーザーをアクティブ化する別の項目を選択したオプション ボタンがオンにした場合に返されると`DoModal`IDOK が返されます。

##  <a name="m_cv"></a>  COleConvertDialog::m_cv

OLEUICONVERT 型の構造体 [変換] ダイアログ ボックスの動作を制御するために使用します。

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>Remarks

この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。

詳細については、次を参照してください。、 [OLEUICONVERT](/windows/desktop/api/oledlg/ns-oledlg-tagoleuiconverta) Windows SDK の構造体。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
