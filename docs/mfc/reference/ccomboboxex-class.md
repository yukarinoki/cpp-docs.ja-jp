---
title: CComboBoxEx クラス
ms.date: 11/04/2016
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
ms.openlocfilehash: 7d46f175a62cda7f1ff08327830f1dffe2967727
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865549"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx クラス

イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。

## <a name="syntax"></a>構文

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CComboBoxEx:: CComboBoxEx](#ccomboboxex)|`CComboBoxEx` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CComboBoxEx:: Create](#create)|コンボボックスを作成し、`CComboBoxEx` オブジェクトにアタッチします。|
|[CComboBoxEx:: CreateEx](#createex)|指定した Windows 拡張スタイルを使用してコンボボックスを作成し、`ComboBoxEx` オブジェクトにアタッチします。|
|[CComboBoxEx::D eleteItem](#deleteitem)|`ComboBoxEx` コントロールから項目を削除します。|
|[CComboBoxEx:: GetComboBoxCtrl](#getcomboboxctrl)|子コンボボックスコントロールへのポインターを取得します。|
|[CComboBoxEx:: GetEditCtrl](#geteditctrl)|`ComboBoxEx` コントロールの編集コントロール部分へのハンドルを取得します。|
|[CComboBoxEx:: GetExtendedStyle](#getextendedstyle)|`ComboBoxEx` コントロールに使用されている拡張スタイルを取得します。|
|[CComboBoxEx:: GetImageList](#getimagelist)|`ComboBoxEx` コントロールに割り当てられたイメージリストへのポインターを取得します。|
|[CComboBoxEx:: GetItem](#getitem)|指定された `ComboBoxEx` 項目の項目情報を取得します。|
|[CComboBoxEx:: HasEditChanged](#haseditchanged)|ユーザーがを入力して `ComboBoxEx` 編集コントロールの内容を変更したかどうかを判断します。|
|[CComboBoxEx:: InsertItem](#insertitem)|`ComboBoxEx` コントロールに新しい項目を挿入します。|
|[CComboBoxEx:: SetExtendedStyle](#setextendedstyle)|`ComboBoxEx` コントロール内に拡張スタイルを設定します。|
|[CComboBoxEx:: SetImageList](#setimagelist)|`ComboBoxEx` コントロールのイメージリストを設定します。|
|[CComboBoxEx:: SetItem](#setitem)|`ComboBoxEx` コントロールの項目の属性を設定します。|
|[CComboBoxEx:: SetWindowTheme](#setwindowtheme)|拡張コンボボックスコントロールの視覚スタイルを設定します。|

## <a name="remarks"></a>コメント

`CComboBoxEx` を使用してコンボボックスコントロールを作成すると、独自のイメージ描画コードを実装する必要がなくなります。 代わりに、`CComboBoxEx` を使用してイメージリストのイメージにアクセスします。

## <a name="image-list-support"></a>イメージリストのサポート

標準のコンボボックスでは、コンボボックスの所有者は、コンボボックスをオーナー描画コントロールとして作成することによって、イメージを描画します。 `CComboBoxEx`を使用する場合、描画 CBS_HASSTRINGS CBS_OWNERDRAWFIXED スタイルを設定する必要はありません。これらは暗黙的に使用されるためです。 それ以外の場合は、描画操作を実行するコードを記述する必要があります。 `CComboBoxEx` コントロールは、項目ごとに最大3つのイメージをサポートします。1つは選択された状態、1つは非選択状態、もう1つはオーバーレイイメージ用です。

## <a name="styles"></a>スタイル

`CComboBoxEx` では、CBS_SIMPLE、CBS_DROPDOWN、CBS_DROPDOWNLIST、および WS_CHILD のスタイルがサポートされています。 ウィンドウの作成時に渡された他のすべてのスタイルは、コントロールによって無視されます。 ウィンドウが作成されたら、`CComboBoxEx` メンバー関数[SetExtendedStyle](#setextendedstyle)を呼び出すことによって、他のコンボボックスのスタイルを指定できます。 これらのスタイルを使用すると、次のことができます。

- リスト内の文字列検索に大文字と小文字を区別するように設定します。

- 区切り記号としてスラッシュ ('/')、円記号 ('\\')、およびピリオド ('. ') を使用するコンボボックスコントロールを作成します。 これにより、キーボードショートカットの CTRL キーを押しながら矢印キーを使用して、word から word にジャンプすることができます。

- コンボボックスコントロールが画像を表示するかどうかを設定します。 イメージが表示されない場合は、コンボボックスで、画像に対応するテキストインデントを削除できます。

- 幅が広くなっているコンボボックスをクリップするようにサイズを変更するなど、ナローコンボボックスコントロールを作成します。

これらのスタイルフラグの詳細については、「 [CComboBoxEx の使用](../../mfc/using-ccomboboxex.md)」を参照してください。

## <a name="item-retention-and-callback-item-attributes"></a>項目の保持とコールバック項目の属性

項目とイメージのインデックス、インデント値、テキスト文字列などの項目情報は、Windows SDK で説明されているように、Win32 構造体の[COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)に格納されます。 構造体には、コールバックフラグに対応するメンバーも含まれます。

概念に関する詳細な説明については、「 [Using CComboBoxEx](../../mfc/using-ccomboboxex.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>要件

**ヘッダー:** afxcmn.h

##  <a name="ccomboboxex"></a>CComboBoxEx:: CComboBoxEx

`CComboBoxEx` オブジェクトを作成するには、このメンバー関数を呼び出します。

```
CComboBoxEx();
```

##  <a name="create"></a>CComboBoxEx:: Create

コンボボックスを作成し、`CComboBoxEx` オブジェクトにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
コンボボックスに適用されるコンボボックススタイルの組み合わせを指定します。 スタイルの詳細については、以下の「**解説**」を参照してください。

*rect*<br/>
コンボボックスの位置とサイズである、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照。

*pParentWnd*<br/>
コンボボックスの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター (通常は `CDialog`)。 NULL にすることはできません。

*nID*<br/>
コンボボックスのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

`CComboBoxEx` オブジェクトを作成するには、次の2つの手順を実行します。

1. [CComboBoxEx](#ccomboboxex)を呼び出して、`CComboBoxEx` オブジェクトを構築します。

1. このメンバー関数を呼び出します。これにより、拡張 Windows コンボボックスが作成され、`CComboBoxEx` オブジェクトにアタッチされます。

`Create`を呼び出すと、MFC はコモンコントロールを初期化します。

コンボボックスを作成するときに、次のコンボボックススタイルのいずれかまたはすべてを指定できます。

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

ウィンドウの作成時に渡された他のすべてのスタイルは無視されます。 `ComboBoxEx` コントロールは、追加の機能を提供する拡張スタイルもサポートしています。 これらのスタイルについては、Windows SDK の「 [ComboBoxEx コントロールの拡張スタイル](/windows/win32/Controls/comboboxex-control-extended-styles)」を参照してください。 これらのスタイルを設定するには、 [SetExtendedStyle](#setextendedstyle)を呼び出します。

拡張 windows スタイルをコントロールで使用する場合は、`Create`ではなく[CreateEx](#createex)を呼び出します。

##  <a name="createex"></a>CComboBoxEx:: CreateEx

この関数を呼び出して、拡張コンボボックスコントロール (子ウィンドウ) を作成し、`CComboBoxEx` オブジェクトに関連付けます。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwExStyle*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の[CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の*dwexstyle*パラメーターを参照してください。

*dwStyle*<br/>
コンボボックスコントロールのスタイル。 スタイルの一覧については、「[作成](#create)」を参照してください。

*rect*<br/>
*PParentWnd*のクライアント座標で、作成されるウィンドウのサイズと位置を記述する[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

Windows の拡張スタイルの先頭**WS_EX_** によって指定された拡張 Windows スタイルを適用するには、`Create` ではなく `CreateEx` を使用します。

`CreateEx` は、 *Dwexstyle*によって指定された拡張 Windows スタイルを使用してコントロールを作成します。 拡張されたコンボボックスコントロールに固有の拡張スタイルは、 [SetExtendedStyle](#setextendedstyle)を使用して設定する必要があります。 たとえば、このようなスタイルを WS_EX_CONTEXTHELP として設定するには `CreateEx` を使用しますが、このようなスタイルを CBES_EX_CASESENSITIVE として設定するには `SetExtendedStyle` を使用します。 詳細については、トピック「 [ComboBoxEx Control Extended styles](/windows/win32/Controls/comboboxex-control-extended-styles) in the Windows SDK」に記載されているスタイルを参照してください。

##  <a name="deleteitem"></a>CComboBoxEx::D eleteItem

`ComboBoxEx` コントロールから項目を削除します。

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
削除する項目の0から始まるインデックス。

### <a name="return-value"></a>戻り値

コントロール内の残りの項目の数。 *IIndex*が無効である場合、関数は CB_ERR を返します。

### <a name="remarks"></a>コメント

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem)の機能を実装します。 DeleteItem を呼び出すと、CBEN_DELETEITEM 通知を含む[WM_NOTIFY](/windows/win32/controls/wm-notify)メッセージが親ウィンドウに送信されます。

##  <a name="getcomboboxctrl"></a>CComboBoxEx:: GetComboBoxCtrl

このメンバー関数を呼び出して、`CComboBoxEx` オブジェクト内のコンボボックスコントロールへのポインターを取得します。

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>戻り値

`CComboBox` オブジェクトを指すポインターです。

### <a name="remarks"></a>コメント

`CComboBoxEx` コントロールは、`CComboBox`をカプセル化する親ウィンドウで構成されます。

戻り値が指す `CComboBox` オブジェクトは一時オブジェクトであり、次のアイドル処理時に破棄されます。

##  <a name="geteditctrl"></a>CComboBoxEx:: GetEditCtrl

コンボボックスのエディットコントロールへのポインターを取得するには、このメンバー関数を呼び出します。

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>戻り値

[CEdit](../../mfc/reference/cedit-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>コメント

`CComboBoxEx` コントロールは、CBS_DROPDOWN スタイルを使用して作成されるときに、エディットボックスを使用します。

戻り値が指す `CEdit` オブジェクトは一時オブジェクトであり、次のアイドル処理時に破棄されます。

##  <a name="getextendedstyle"></a>CComboBoxEx:: GetExtendedStyle

このメンバー関数を呼び出して、`CComboBoxEx` コントロールに使用される拡張スタイルを取得します。

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>戻り値

コンボボックスコントロールに使用される拡張スタイルを含む DWORD 値。

### <a name="remarks"></a>コメント

これらのスタイルの詳細については、「 [ComboBoxEx Control Extended styles](/windows/win32/Controls/comboboxex-control-extended-styles) in the Windows SDK」を参照してください。

##  <a name="getimagelist"></a>CComboBoxEx:: GetImageList

`CComboBoxEx` コントロールによって使用されるイメージリストへのポインターを取得するには、このメンバー関数を呼び出します。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトへのポインター。 失敗した場合、このメンバー関数は NULL を返します。

### <a name="remarks"></a>コメント

戻り値が指す `CImageList` オブジェクトは一時オブジェクトであり、次のアイドル処理時に破棄されます。

##  <a name="getitem"></a>CComboBoxEx:: GetItem

指定された `ComboBoxEx` 項目の項目情報を取得します。

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>パラメーター

*pCBItem*<br/>
項目情報を受け取る[COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)構造体へのポインター。

### <a name="return-value"></a>戻り値

操作が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_GETITEM](/windows/win32/Controls/cbem-getitem)の機能を実装します。

##  <a name="haseditchanged"></a>CComboBoxEx:: HasEditChanged

ユーザーがを入力して `ComboBoxEx` 編集コントロールの内容を変更したかどうかを判断します。

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>戻り値

ユーザーがコントロールのエディットボックスに入力した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged)の機能を実装します。

##  <a name="insertitem"></a>CComboBoxEx:: InsertItem

`ComboBoxEx` コントロールに新しい項目を挿入します。

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>パラメーター

*pCBItem*<br/>
項目情報を受け取る[COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)構造体へのポインター。 この構造体には、項目のコールバックフラグの値が含まれています。

### <a name="return-value"></a>戻り値

成功した場合は、新しい項目が挿入された位置のインデックス。それ以外の場合は-1。

### <a name="remarks"></a>コメント

`InsertItem`を呼び出すと、 [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem)通知を含む[WM_NOTIFY](/windows/win32/controls/wm-notify)メッセージが親ウィンドウに送信されます。

##  <a name="setextendedstyle"></a>CComboBoxEx:: SetExtendedStyle

このメンバー関数を呼び出して、コンボボックス拡張コントロールに使用される拡張スタイルを設定します。

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>パラメーター

*dwExMask*<br/>
*Dwexstyles*で影響を受けるスタイルを示す DWORD 値。 *Dwexmask*の拡張スタイルのみが変更されます。 その他のすべてのスタイルはそのまま維持されます。 このパラメーターが0の場合、 *Dwexstyles*のすべてのスタイルが影響を受けます。

*dwExStyles*<br/>
コントロールに設定するコンボボックスコントロールの拡張スタイルを含む DWORD 値です。

### <a name="return-value"></a>戻り値

コントロールに以前に使用されていた拡張スタイルを含む DWORD 値。

### <a name="remarks"></a>コメント

これらのスタイルの詳細については、「 [ComboBoxEx Control Extended styles](/windows/win32/Controls/comboboxex-control-extended-styles) in the Windows SDK」を参照してください。

拡張 windows スタイルを使用してコンボボックス拡張コントロールを作成するには、 [CreateEx](#createex)を使用します。

##  <a name="setimagelist"></a>CComboBoxEx:: SetImageList

`ComboBoxEx` コントロールのイメージリストを設定します。

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*pImageList*<br/>
`CComboBoxEx` コントロールで使用するイメージを格納している `CImageList` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

`CComboBoxEx` コントロールによって以前に使用されたイメージを格納している[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトへのポインター。 以前に設定されたイメージリストがない場合は NULL です。

### <a name="remarks"></a>コメント

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist)の機能を実装します。 既定の編集コントロールの高さを変更する場合は、`SetImageList`を呼び出した後に、Win32 関数[SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos)を呼び出してコントロールのサイズを変更するか、正しく表示されません。

戻り値が指す `CImageList` オブジェクトは一時オブジェクトであり、次のアイドル処理時に破棄されます。

##  <a name="setitem"></a>CComboBoxEx:: SetItem

`ComboBoxEx` コントロールの項目の属性を設定します。

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>パラメーター

*pCBItem*<br/>
項目情報を受け取る[COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)構造体へのポインター。

### <a name="return-value"></a>戻り値

操作が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_SETITEM](/windows/win32/Controls/cbem-setitem)の機能を実装します。

##  <a name="setwindowtheme"></a>CComboBoxEx:: SetWindowTheme

拡張コンボボックスコントロールの視覚スタイルを設定します。

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>パラメーター

*pszSubAppName*<br/>
設定する拡張コンボボックスの visual スタイルを含む Unicode 文字列へのポインター。

### <a name="return-value"></a>戻り値

戻り値は使用されません。

### <a name="remarks"></a>コメント

このメンバー関数は、Windows SDK で説明されているように、 [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme)メッセージの機能をエミュレートします。

## <a name="see-also"></a>参照

[MFC サンプル MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)
