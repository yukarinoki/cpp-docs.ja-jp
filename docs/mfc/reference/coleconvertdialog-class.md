---
title: クラスを変換します。
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
ms.openlocfilehash: 6d6690b8d06df29ce9fcd323eb8724009ee3cca9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366172"
---
# <a name="coleconvertdialog-class"></a>クラスを変換します。

詳細については、Windows SDK の[「OLEUICONVERT」](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw)の構造を参照してください。

## <a name="syntax"></a>構文

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::コレクル変換ダイアログ](#coleconvertdialog)|`COleConvertDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス:Do 変換](#doconvert)|ダイアログ ボックスで指定された変換を実行します。|
|[ダイアログ ボックス::Do モーダル](#domodal)|[OLE アイテムの変更] ダイアログ ボックスを表示します。|
|[ダイアログボックス::クラスIDを取得します。](#getclassid)|選択した項目に関連付けられている CLSID を取得します。|
|[ダイアログボックス::アスペクトを取得します。](#getdrawaspect)|アイテムをアイコンとして描画するかどうかを指定します。|
|[ダイアログボックス::取得アイコンメタファイル](#geticonicmetafile)|このアイテムのアイコン形式に関連付けられているメタファイルへのハンドルを取得します。|
|[ダイアログボックス::選択タイプ](#getselectiontype)|選択した選択の種類を取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ:m_cv](#m_cv)|ダイアログ ボックスの動作を制御する構造体。|

## <a name="remarks"></a>解説

> [!NOTE]
> アプリケーション ウィザードで生成されたコンテナー コードでは、このクラスを使用します。

OLE 固有のダイアログ ボックスの詳細については[、「OLE](../../mfc/dialog-boxes-in-ole.md)のダイアログ ボックス」を参照してください。

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

## <a name="coleconvertdialogcoleconvertdialog"></a><a name="coleconvertdialog"></a>ダイアログボックス::コレクル変換ダイアログ

`COleConvertDialog`オブジェクトのみを構築します。

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
変換またはアクティブ化する項目へのポインター。

*dwFlags*<br/>
作成フラグは、ビットごとのまたは演算子を使用して組み合わせた次の値の任意の数を含みます。

- CF_SELECTCONVERTTO ダイアログ ボックスが呼び出されたときに、[変換] ラジオ ボタンが最初に選択されるように指定します。 これは既定値です。

- CF_SELECTACTIVATEAS ダイアログ ボックスが呼び出されたときに、[名前を付ける] ラジオ ボタンが最初に選択されるように指定します。

- CF_SETCONVERTDEFAULT変換オプション ボタンが選択されている場合`clsidConvertDefault``m_cv`、CLSID が構造体のメンバーによって指定されているクラスをクラス リスト ボックスの既定の選択として使用することを指定します。

- CF_SETACTIVATEDEFAULT[別のユーザーとしてアクティブ化]ラジオ ボタン`clsidActivateDefault`が選択されている`m_cv`場合、CLSID が構造体のメンバーによって指定されているクラスが、クラス リスト ボックスの既定の選択として使用されるように指定します。

- CF_SHOWHELPBUTTON ダイアログ ボックスが呼び出されたときに [ヘルプ] ボタンが表示されるように指定します。

*クラスID*<br/>
変換またはアクティブ化する項目の CLSID へのポインター。 NULL の場合は *、pItem*に関連付けられた CLSID が使用されます。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する (型`CWnd`) の親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクトへのポインター。 NULL の場合、ダイアログ ボックスの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

ダイアログ ボックスを表示するには[、DoModal](#domodal)関数を呼び出します。

詳細については[、「CLSID キー](/windows/win32/com/clsid-key-hklm) 」および[「OLEUICONVERT](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw)構造体」を参照してください。

## <a name="coleconvertdialogdoconvert"></a><a name="doconvert"></a>ダイアログ ボックス:Do 変換

[DoModal](#domodal)から正常に返された後、この関数を呼び出して[、COleClientItem](../../mfc/reference/coleclientitem-class.md)型のオブジェクトを変換するか、アクティブにします。

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
変換またはアクティブ化する項目へのポインター。 Nll は指定できません。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

項目は、ユーザーが [変換] ダイアログ ボックスで選択した情報に従って変換またはアクティブ化されます。

## <a name="coleconvertdialogdomodal"></a><a name="domodal"></a>ダイアログ ボックス::Do モーダル

OLE 変換ダイアログ ボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスの完了ステータス。 次のいずれかの値:

- ダイアログ ボックスが正常に表示された場合は IDOK。

- ユーザーがダイアログ ボックスをキャンセルした場合は、IDCANCEL を指定します。

- エラーが発生した場合は、IDABORT を実行します。 IDABORT が返された場合は、発生したエラーの種類に関する詳細情報を取得するのには[、COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)メンバー関数を呼び出します。 考えられるエラーの一覧については、Windows SDK の[「OleUIConvert](/windows/win32/api/oledlg/nf-oledlg-oleuiconvertw)関数」を参照してください。

### <a name="remarks"></a>解説

[m_cv](#m_cv)構造体のメンバを設定してさまざまなダイアログ ボックス コントロールを初期化する場合は、ダイアログ オブジェクトを作成`DoModal`した後で呼び出す前に、この操作を行う必要があります。

IDOK が返された場合`DoModal`は、他のメンバー関数を呼び出して、ユーザーがダイアログ ボックスに入力した設定または情報を取得できます。

## <a name="coleconvertdialoggetclassid"></a><a name="getclassid"></a>ダイアログボックス::クラスIDを取得します。

[変換] ダイアログ ボックスでユーザーが選択した項目に関連付けられた CLSID を取得します。

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>戻り値

[変換] ダイアログ ボックスで選択した項目に関連付けられた CLSID。

### <a name="remarks"></a>解説

この関数を呼び出すのは[、DoModal](#domodal)が IDOK を返した後だけです。

詳細については、Windows SDK[の CLSID キー](/windows/win32/com/clsid-key-hklm)を参照してください。

## <a name="coleconvertdialoggetdrawaspect"></a><a name="getdrawaspect"></a>ダイアログボックス::アスペクトを取得します。

選択した項目をアイコンとして表示するかどうかを確認します。

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>戻り値

オブジェクトのレンダリングに必要なメソッド。

- DVASPECT_CONTENT アイコンとして表示] チェック ボックスがオフの場合は返されます。

- DVASPECT_ICON アイコンとして表示 チェックボックスがオンの場合に返されます。

### <a name="remarks"></a>解説

この関数を呼び出すのは[、DoModal](#domodal)が IDOK を返した後だけです。

描画の側面の詳細については、Windows SDK の[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)データ構造を参照してください。

## <a name="coleconvertdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>ダイアログボックス::取得アイコンメタファイル

選択した項目のアイコン的な側面を含むメタファイルへのハンドルを取得します。

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>戻り値

ダイアログボックスが閉じられたときに [アイコンとして表示] チェックボックスがオンの場合は、[OK] をクリックして、選択した項目のアイコンを含むメタファイルへのハンドル。それ以外の場合は NULL。

## <a name="coleconvertdialoggetselectiontype"></a><a name="getselectiontype"></a>ダイアログボックス::選択タイプ

[変換] ダイアログ ボックスで選択した変換の種類を調べます。

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>戻り値

選択の種類です。

### <a name="remarks"></a>解説

戻り値の型の値は`Selection`、クラスで宣言された`COleConvertDialog`列挙型によって指定されます。

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

これらの値の簡単な説明は次のとおりです。

- `COleConvertDialog::noConversion`ダイアログ ボックスがキャンセルされた場合、またはユーザーが変換を選択しなかった場合に返されます。 返`COleConvertDialog::DoModal`された IDOK の場合、ユーザーが以前に選択したアイコンとは異なるアイコンを選択した可能性があります。

- `COleConvertDialog::convertItem`[変換先] オプション ボタンがオンの場合に返される、ユーザーは変換する別`DoModal`の項目を選択し、IDOK を返しました。

- `COleConvertDialog::activateAs`[別のユーザーとしてアクティブ化] ラジオ ボタンがオンの場合に返され、`DoModal`ユーザーはアクティブ化する別の項目を選択し、IDOK を返しました。

## <a name="coleconvertdialogm_cv"></a><a name="m_cv"></a>ダイアログ:m_cv

[変換] ダイアログ ボックスの動作を制御するために使用される OLEUICONVERT 型の構造体。

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>解説

この構造体のメンバーは、直接またはメンバー関数を通じて変更できます。

詳細については、Windows SDK の[「OLEUICONVERT」](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw)の構造を参照してください。

## <a name="see-also"></a>関連項目

[COleDialog クラス](../../mfc/reference/coledialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDialog クラス](../../mfc/reference/coledialog-class.md)
