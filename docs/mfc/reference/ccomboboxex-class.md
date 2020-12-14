---
description: '詳細情報: CComboBoxEx クラス'
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
ms.openlocfilehash: 6d5b8a520fe62cbc60883370ec92abe4d978b5bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265520"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx クラス

イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。

## <a name="syntax"></a>構文

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComboBoxEx:: CComboBoxEx](#ccomboboxex)|`CComboBoxEx` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComboBoxEx:: Create](#create)|コンボボックスを作成し、オブジェクトにアタッチし `CComboBoxEx` ます。|
|[CComboBoxEx:: CreateEx](#createex)|指定された Windows 拡張スタイルを使用してコンボボックスを作成し、オブジェクトにアタッチし `ComboBoxEx` ます。|
|[CComboBoxEx::D eleteItem](#deleteitem)|コントロールから項目を削除 `ComboBoxEx` します。|
|[CComboBoxEx:: GetComboBoxCtrl](#getcomboboxctrl)|子コンボボックスコントロールへのポインターを取得します。|
|[CComboBoxEx:: GetEditCtrl](#geteditctrl)|コントロールの編集コントロール部分へのハンドルを取得し `ComboBoxEx` ます。|
|[CComboBoxEx:: GetExtendedStyle](#getextendedstyle)|コントロールに使用されている拡張スタイルを取得し `ComboBoxEx` ます。|
|[CComboBoxEx:: GetImageList](#getimagelist)|コントロールに割り当てられたイメージリストへのポインターを取得 `ComboBoxEx` します。|
|[CComboBoxEx:: GetItem](#getitem)|指定された項目の項目情報を取得 `ComboBoxEx` します。|
|[CComboBoxEx:: HasEditChanged](#haseditchanged)|ユーザーが「」と入力して、エディットコントロールの内容を変更したかどうかを判断し `ComboBoxEx` ます。|
|[CComboBoxEx:: InsertItem](#insertitem)|コントロールに新しい項目を挿入 `ComboBoxEx` します。|
|[CComboBoxEx:: SetExtendedStyle](#setextendedstyle)|コントロール内に拡張スタイルを設定 `ComboBoxEx` します。|
|[CComboBoxEx:: SetImageList](#setimagelist)|コントロールのイメージリストを設定 `ComboBoxEx` します。|
|[CComboBoxEx:: SetItem](#setitem)|コントロール内の項目の属性を設定 `ComboBoxEx` します。|
|[CComboBoxEx:: SetWindowTheme](#setwindowtheme)|拡張コンボボックスコントロールの視覚スタイルを設定します。|

## <a name="remarks"></a>解説

を使用して `CComboBoxEx` コンボボックスコントロールを作成すると、独自のイメージ描画コードを実装する必要がなくなります。 代わりに、を使用して `CComboBoxEx` イメージリストのイメージにアクセスします。

## <a name="image-list-support"></a>イメージリストのサポート

標準のコンボボックスでは、コンボボックスの所有者は、コンボボックスをオーナー描画コントロールとして作成することによって、イメージを描画します。 を使用する場合は `CComboBoxEx` 、描画スタイル CBS_OWNERDRAWFIXED と CBS_HASSTRINGS を設定する必要はありません。これらは暗黙的に使用されるためです。 それ以外の場合は、描画操作を実行するコードを記述する必要があります。 コントロールは、 `CComboBoxEx` 項目ごとに最大3つのイメージをサポートします。1つは選択された状態、1つは非選択状態、もう1つはオーバーレイイメージ用です。

## <a name="styles"></a>スタイル

`CComboBoxEx` では、CBS_SIMPLE、CBS_DROPDOWN、CBS_DROPDOWNLIST、および WS_CHILD のスタイルがサポートされています。 ウィンドウの作成時に渡された他のすべてのスタイルは、コントロールによって無視されます。 ウィンドウが作成されたら、メンバー関数 SetExtendedStyle を呼び出すことによって、他のコンボボックスのスタイルを指定でき `CComboBoxEx` ます。 [](#setextendedstyle) これらのスタイルを使用すると、次のことができます。

- リスト内の文字列検索に大文字と小文字を区別するように設定します。

- 区切り記号としてスラッシュ ('/')、円記号 (' \\ ')、ピリオド ('. ') を使用するコンボボックスコントロールを作成します。 これにより、キーボードショートカットの CTRL キーを押しながら矢印キーを使用して、word から word にジャンプすることができます。

- コンボボックスコントロールが画像を表示するかどうかを設定します。 イメージが表示されない場合は、コンボボックスで、画像に対応するテキストインデントを削除できます。

- 幅が広くなっているコンボボックスをクリップするようにサイズを変更するなど、ナローコンボボックスコントロールを作成します。

これらのスタイルフラグの詳細については、「 [CComboBoxEx の使用](../../mfc/using-ccomboboxex.md)」を参照してください。

## <a name="item-retention-and-callback-item-attributes"></a>項目の保持とコールバック項目の属性

項目とイメージのインデックス、インデント値、テキスト文字列などの項目情報は、Windows SDK で説明されているように、Win32 構造体の [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)に格納されます。 構造体には、コールバックフラグに対応するメンバーも含まれます。

概念に関する詳細な説明については、「 [Using CComboBoxEx](../../mfc/using-ccomboboxex.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>要件

**ヘッダー:** afxcmn.h

## <a name="ccomboboxexccomboboxex"></a><a name="ccomboboxex"></a> CComboBoxEx:: CComboBoxEx

オブジェクトを作成するには、このメンバー関数を呼び出し `CComboBoxEx` ます。

```
CComboBoxEx();
```

## <a name="ccomboboxexcreate"></a><a name="create"></a> CComboBoxEx:: Create

コンボボックスを作成し、オブジェクトにアタッチし `CComboBoxEx` ます。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
コンボボックスに適用されるコンボボックススタイルの組み合わせを指定します。 スタイルの詳細については、以下の「 **解説** 」を参照してください。

*rect*<br/>
コンボボックスの位置とサイズである、 [CRect](../../atl-mfc-shared/reference/crect-class.md) オブジェクトまたは [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体への参照。

*pParentWnd*<br/>
コンボボックスの親ウィンドウである [CWnd](../../mfc/reference/cwnd-class.md) オブジェクトへのポインター (通常は `CDialog` )。 NULL にすることはできません。

*nID*<br/>
コンボボックスのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

オブジェクトを作成するには、 `CComboBoxEx` 次の2つの手順を実行します。

1. [CComboBoxEx](#ccomboboxex)を呼び出して、 `CComboBoxEx` オブジェクトを構築します。

1. このメンバー関数を呼び出します。これにより、拡張 Windows コンボボックスが作成され、オブジェクトにアタッチさ `CComboBoxEx` れます。

を呼び出すと `Create` 、MFC はコモンコントロールを初期化します。

コンボボックスを作成するときに、次のコンボボックススタイルのいずれかまたはすべてを指定できます。

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

ウィンドウの作成時に渡された他のすべてのスタイルは無視されます。 コントロールは、 `ComboBoxEx` 追加の機能を提供する拡張スタイルもサポートしています。 これらのスタイルについては、Windows SDK の「 [ComboBoxEx コントロールの拡張スタイル](/windows/win32/Controls/comboboxex-control-extended-styles)」を参照してください。 これらのスタイルを設定するには、 [SetExtendedStyle](#setextendedstyle)を呼び出します。

拡張 windows スタイルをコントロールで使用する場合は、ではなく [CreateEx](#createex) を呼び出し `Create` ます。

## <a name="ccomboboxexcreateex"></a><a name="createex"></a> CComboBoxEx:: CreateEx

この関数を呼び出して、拡張コンボボックスコントロール (子ウィンドウ) を作成し、オブジェクトに関連付け `CComboBoxEx` ます。

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
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の *dwexstyle* パラメーターを参照してください。

*dwStyle*<br/>
コンボボックスコントロールのスタイル。 スタイルの一覧については、「 [作成](#create) 」を参照してください。

*rect*<br/>
*PParentWnd* のクライアント座標で、作成されるウィンドウのサイズと位置を記述する [RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`CreateEx` `Create` Windows 拡張スタイルの先頭 **WS_EX_** によって指定された拡張 windows スタイルを適用するには、の代わりにを使用します。

`CreateEx`*Dwexstyle* によって指定された拡張 Windows スタイルを使用して、コントロールを作成します。 拡張されたコンボボックスコントロールに固有の拡張スタイルは、 [SetExtendedStyle](#setextendedstyle)を使用して設定する必要があります。 たとえば、を使用し `CreateEx` て、このようなスタイルを WS_EX_CONTEXTHELP として設定します。ただし、を使用し `SetExtendedStyle` て、そのようなスタイルを CBES_EX_CASESENSITIVE として設定します。 詳細については、トピック「 [ComboBoxEx Control Extended styles](/windows/win32/Controls/comboboxex-control-extended-styles) in the Windows SDK」に記載されているスタイルを参照してください。

## <a name="ccomboboxexdeleteitem"></a><a name="deleteitem"></a> CComboBoxEx::D eleteItem

コントロールから項目を削除 `ComboBoxEx` します。

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>パラメーター

*iIndex*<br/>
削除する項目の0から始まるインデックス。

### <a name="return-value"></a>戻り値

コントロール内の残りの項目の数。 *IIndex* が無効である場合、関数は CB_ERR を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ [CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem)の機能を実装します。 DeleteItem を呼び出すと、CBEN_DELETEITEM 通知を含む [WM_NOTIFY](/windows/win32/controls/wm-notify) メッセージが親ウィンドウに送信されます。

## <a name="ccomboboxexgetcomboboxctrl"></a><a name="getcomboboxctrl"></a> CComboBoxEx:: GetComboBoxCtrl

オブジェクト内のコンボボックスコントロールへのポインターを取得するには、このメンバー関数を呼び出し `CComboBoxEx` ます。

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>戻り値

`CComboBox` オブジェクトを指すポインターです。

### <a name="remarks"></a>解説

コントロールは、 `CComboBoxEx` をカプセル化する親ウィンドウで構成され `CComboBox` ます。

`CComboBox`戻り値が指すオブジェクトは一時オブジェクトであり、次のアイドル処理時に破棄されます。

## <a name="ccomboboxexgeteditctrl"></a><a name="geteditctrl"></a> CComboBoxEx:: GetEditCtrl

コンボボックスのエディットコントロールへのポインターを取得するには、このメンバー関数を呼び出します。

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>戻り値

[CEdit](../../mfc/reference/cedit-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

コントロールは、 `CComboBoxEx` CBS_DROPDOWN スタイルを使用して作成されるときに、エディットボックスを使用します。

`CEdit`戻り値が指すオブジェクトは一時オブジェクトであり、次のアイドル処理時に破棄されます。

## <a name="ccomboboxexgetextendedstyle"></a><a name="getextendedstyle"></a> CComboBoxEx:: GetExtendedStyle

コントロールに使用される拡張スタイルを取得するには、このメンバー関数を呼び出し `CComboBoxEx` ます。

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>戻り値

コンボボックスコントロールに使用される拡張スタイルを含む DWORD 値。

### <a name="remarks"></a>解説

これらのスタイルの詳細については、「 [ComboBoxEx Control Extended styles](/windows/win32/Controls/comboboxex-control-extended-styles) in the Windows SDK」を参照してください。

## <a name="ccomboboxexgetimagelist"></a><a name="getimagelist"></a> CComboBoxEx:: GetImageList

コントロールによって使用されるイメージリストへのポインターを取得するには、このメンバー関数を呼び出し `CComboBoxEx` ます。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトへのポインター。 失敗した場合、このメンバー関数は NULL を返します。

### <a name="remarks"></a>解説

`CImageList`戻り値が指すオブジェクトは一時オブジェクトであり、次のアイドル処理時に破棄されます。

## <a name="ccomboboxexgetitem"></a><a name="getitem"></a> CComboBoxEx:: GetItem

指定された項目の項目情報を取得 `ComboBoxEx` します。

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>パラメーター

*pCBItem*<br/>
項目情報を受け取る [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 構造体へのポインター。

### <a name="return-value"></a>戻り値

操作が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ [CBEM_GETITEM](/windows/win32/Controls/cbem-getitem)の機能を実装します。

## <a name="ccomboboxexhaseditchanged"></a><a name="haseditchanged"></a> CComboBoxEx:: HasEditChanged

ユーザーが「」と入力して、エディットコントロールの内容を変更したかどうかを判断し `ComboBoxEx` ます。

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>戻り値

ユーザーがコントロールのエディットボックスに入力した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ [CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged)の機能を実装します。

## <a name="ccomboboxexinsertitem"></a><a name="insertitem"></a> CComboBoxEx:: InsertItem

コントロールに新しい項目を挿入 `ComboBoxEx` します。

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>パラメーター

*pCBItem*<br/>
項目情報を受け取る [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 構造体へのポインター。 この構造体には、項目のコールバックフラグの値が含まれています。

### <a name="return-value"></a>戻り値

成功した場合は、新しい項目が挿入された位置のインデックス。それ以外の場合は-1。

### <a name="remarks"></a>解説

を呼び出すと `InsertItem` 、 [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem)通知を含む[WM_NOTIFY](/windows/win32/controls/wm-notify)メッセージが親ウィンドウに送信されます。

## <a name="ccomboboxexsetextendedstyle"></a><a name="setextendedstyle"></a> CComboBoxEx:: SetExtendedStyle

このメンバー関数を呼び出して、コンボボックス拡張コントロールに使用される拡張スタイルを設定します。

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>パラメーター

*dwExMask*<br/>
*Dwexstyles* で影響を受けるスタイルを示す DWORD 値。 *Dwexmask* の拡張スタイルのみが変更されます。 その他のすべてのスタイルはそのまま維持されます。 このパラメーターが0の場合、 *Dwexstyles* のすべてのスタイルが影響を受けます。

*dwExStyles*<br/>
コントロールに設定するコンボボックスコントロールの拡張スタイルを含む DWORD 値です。

### <a name="return-value"></a>戻り値

コントロールに以前に使用されていた拡張スタイルを含む DWORD 値。

### <a name="remarks"></a>解説

これらのスタイルの詳細については、「 [ComboBoxEx Control Extended styles](/windows/win32/Controls/comboboxex-control-extended-styles) in the Windows SDK」を参照してください。

拡張 windows スタイルを使用してコンボボックス拡張コントロールを作成するには、 [CreateEx](#createex)を使用します。

## <a name="ccomboboxexsetimagelist"></a><a name="setimagelist"></a> CComboBoxEx:: SetImageList

コントロールのイメージリストを設定 `ComboBoxEx` します。

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*pImageList*<br/>
`CImageList`コントロールで使用するイメージを格納しているオブジェクトへのポインター `CComboBoxEx` 。

### <a name="return-value"></a>戻り値

コントロールによって以前に使用されたイメージを格納している [CImageList](../../mfc/reference/cimagelist-class.md) オブジェクトへのポインター `CComboBoxEx` 。 以前に設定されたイメージリストがない場合は NULL です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ [CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist)の機能を実装します。 既定の編集コントロールの高さを変更する場合は、を呼び出した後に Win32 関数 [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) を呼び出してコントロールのサイズを変更する `SetImageList` か、正しく表示されません。

`CImageList`戻り値が指すオブジェクトは一時オブジェクトであり、次のアイドル処理時に破棄されます。

## <a name="ccomboboxexsetitem"></a><a name="setitem"></a> CComboBoxEx:: SetItem

コントロール内の項目の属性を設定 `ComboBoxEx` します。

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>パラメーター

*pCBItem*<br/>
項目情報を受け取る [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 構造体へのポインター。

### <a name="return-value"></a>戻り値

操作が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ [CBEM_SETITEM](/windows/win32/Controls/cbem-setitem)の機能を実装します。

## <a name="ccomboboxexsetwindowtheme"></a><a name="setwindowtheme"></a> CComboBoxEx:: SetWindowTheme

拡張コンボボックスコントロールの視覚スタイルを設定します。

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>パラメーター

*pszSubAppName*<br/>
設定する拡張コンボボックスの visual スタイルを含む Unicode 文字列へのポインター。

### <a name="return-value"></a>戻り値

戻り値は使用されません。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、 [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme) メッセージの機能をエミュレートします。

## <a name="see-also"></a>関連項目

[MFC サンプル MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)
