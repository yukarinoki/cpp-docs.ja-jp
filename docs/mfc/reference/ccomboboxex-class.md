---
title: クラス
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
ms.openlocfilehash: 4151ea17fd3223c126715742c6149f2cf55bcbc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369470"
---
# <a name="ccomboboxex-class"></a>クラス

イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。

## <a name="syntax"></a>構文

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cコンボボックスエクスックス::Cコンボボックスエックス](#ccomboboxex)|`CComboBoxEx` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cコンボボックスエクスックス::作成](#create)|コンボ ボックスを作成し、オブジェクトに`CComboBoxEx`アタッチします。|
|[Cコンボボックスエクスックス::作成します。](#createex)|指定した Windows 拡張スタイルを持つコンボ ボックスを作成し`ComboBoxEx`、オブジェクトにアタッチします。|
|[Cコンボボックスエックス::Dエレテアイテム](#deleteitem)|コントロールから項目を`ComboBoxEx`削除します。|
|[次の値を取得します。](#getcomboboxctrl)|子コンボ ボックス コントロールへのポインターを取得します。|
|[次の項目を使用します。](#geteditctrl)|コントロールのエディット コントロール部分へのハンドルを`ComboBoxEx`取得します。|
|[Cコンボボックスエクスックス::ゲットエクステンドスタイル](#getextendedstyle)|`ComboBoxEx`コントロールに使用されている拡張スタイルを取得します。|
|[を使用します。](#getimagelist)|コントロールに割り当てられたイメージ リストへのポインター`ComboBoxEx`を取得します。|
|[をクリックします。](#getitem)|指定`ComboBoxEx`した項目の項目情報を取得します。|
|[Cコンボボックスエクスックス::ハズエディット変更](#haseditchanged)|ユーザーがエディット コントロールの内容を変更`ComboBoxEx`したかどうかを調べます。|
|[を挿入します。](#insertitem)|コントロールに新しい項目を`ComboBoxEx`挿入します。|
|[Cコンボボックスエクスックス::セットエクステンドスタイル](#setextendedstyle)|コントロール内の拡張スタイル`ComboBoxEx`を設定します。|
|[を使用します。](#setimagelist)|コントロールのイメージ リストを`ComboBoxEx`設定します。|
|[を設定します。](#setitem)|コントロール内の項目の属性を`ComboBoxEx`設定します。|
|[Cコンボボックスエクスックス::セットウィンドウテーマ](#setwindowtheme)|拡張コンボ ボックス コントロールの表示スタイルを設定します。|

## <a name="remarks"></a>解説

を使用`CComboBoxEx`してコンボ ボックス コントロールを作成すると、独自のイメージ描画コードを実装する必要がなくなります。 代わりに、`CComboBoxEx`イメージ リストからイメージにアクセスするために使用します。

## <a name="image-list-support"></a>イメージ リストのサポート

標準コンボ ボックスでは、コンボ ボックスの所有者は、オーナー描画コントロールとしてコンボ ボックスを作成してイメージを描画します。 を使用`CComboBoxEx`する場合は、図面スタイルを暗黙的に設定CBS_OWNERDRAWFIXED、CBS_HASSTRINGSする必要はありません。 それ以外の場合は、描画操作を実行するコードを記述する必要があります。 コントロール`CComboBoxEx`は、項目ごとに最大 3 つのイメージをサポートします( 1 つは選択状態、もう 1 つは選択なしの状態、もう 1 つはオーバーレイ イメージ用)。

## <a name="styles"></a>スタイル

`CComboBoxEx`では、スタイル CBS_SIMPLE、CBS_DROPDOWN、CBS_DROPDOWNLIST、およびWS_CHILDをサポートします。 ウィンドウ作成時に渡される他のすべてのスタイルは、コントロールによって無視されます。 ウィンドウが作成されたら、メンバー関数[SetExtendedStyle](#setextendedstyle)を呼び出`CComboBoxEx`すことによって、他のコンボ ボックス スタイルを指定できます。 これらのスタイルを使用すると、次のことができます。

- リスト内の文字列検索を大文字と小文字を区別するように設定します。

- 単語区切り記号としてスラッシュ ('/')、円記号 (')、\\ピリオド (') 文字を使用するコンボ ボックス コントロールを作成します。 これにより、キーボード ショートカット Ctrl + 方向キーを使用して、単語間をジャンプできます。

- コンボ ボックス コントロールを、イメージの表示または表示しないのいずれかに設定します。 イメージが表示されない場合、コンボ ボックスはイメージに対応するテキストインデントを削除できます。

- 幅の広いコンボ ボックスをクリップするようにサイズ変更を含む、幅の狭いコンボ ボックス コントロールを作成します。

これらのスタイル フラグについては[、CComboBoxEx](../../mfc/using-ccomboboxex.md)の使用で詳しく説明します。

## <a name="item-retention-and-callback-item-attributes"></a>アイテムの保持とコールバックアイテムの属性

項目やイメージのインデックス、インデント値、テキスト文字列などの項目情報は、Windows SDK で説明されているように、Win32 構造体[COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)に格納されます。 この構造体には、コールバック フラグに対応するメンバーも含まれます。

詳細な概念的な説明については[、「CComboBoxEx の使用](../../mfc/using-ccomboboxex.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="ccomboboxexccomboboxex"></a><a name="ccomboboxex"></a>Cコンボボックスエクスックス::Cコンボボックスエックス

オブジェクトを作成するには、このメンバー`CComboBoxEx`関数を呼び出します。

```
CComboBoxEx();
```

## <a name="ccomboboxexcreate"></a><a name="create"></a>Cコンボボックスエクスックス::作成

コンボ ボックスを作成し、オブジェクトに`CComboBoxEx`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
コンボ ボックスに適用されるコンボ ボックス スタイルの組み合わせを指定します。 スタイルの詳細については、以下の **「解説」** を参照してください。

*Rect*<br/>
コンボ ボックスの位置とサイズを示す[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照。

*pParentWnd*<br/>
コンボ ボックスの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター ( 通常は`CDialog`a ) 。 NULL にすることはできません。

*nID*<br/>
コンボ ボックスのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

次の`CComboBoxEx`2 つの手順でオブジェクトを作成します。

1. オブジェクトを構築するために[CComboBoxEx](#ccomboboxex)を`CComboBoxEx`呼び出します。

1. 拡張 Windows コンボ ボックスを作成し、オブジェクトにアタッチするこのメンバー関数`CComboBoxEx`を呼び出します。

を呼び`Create`出すと、MFC はコモン コントロールを初期化します。

コンボ ボックスを作成するときに、次のコンボ ボックス スタイルの一部またはすべてを指定できます。

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- Ws_child

ウィンドウ作成時に渡される他のスタイルはすべて無視されます。 コントロール`ComboBoxEx`は、追加機能を提供する拡張スタイルもサポートしています。 これらのスタイルについては、Windows SDK の[「コンボボックスEx コントロール拡張スタイル](/windows/win32/Controls/comboboxex-control-extended-styles)」で説明されています。 これらのスタイルを設定するには[、SetExtendedStyle](#setextendedstyle)を呼び出します。

コントロールで拡張ウィンドウ スタイルを使用する場合は、 ではなく[CreateEx](#createex)を`Create`呼び出します。

## <a name="ccomboboxexcreateex"></a><a name="createex"></a>Cコンボボックスエクスックス::作成します。

拡張コンボ ボックス コントロール (子ウィンドウ) を作成し、`CComboBoxEx`オブジェクトに関連付けます。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*ドウェエクススタイル*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の*DwExStyle*パラメーター[を](/windows/win32/api/winuser/nf-winuser-createwindowexw)参照してください。

*Dwstyle*<br/>
コンボ ボックス コントロールのスタイル。 スタイルの一覧については、「[作成](#create)」を参照してください。

*Rect*<br/>
作成するウィンドウのサイズと位置を記述する[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照を *、 pParentWnd*のクライアント座標で指定します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

Windows`CreateEx`拡張`Create`スタイルの序文で指定された拡張 Windows スタイルを適用**する代わりに使用WS_EX_。**

`CreateEx`によって指定された拡張 Windows スタイルを持つコントロール*が作成されます*。 [SetExtendedStyle](#setextendedstyle)を使用して、拡張コンボ ボックス コントロールに固有の拡張スタイルを設定する必要があります。 たとえば、WS_EX_CONTEXTHELPなどの`CreateEx`スタイルを設定するのには、CBES_EX_CASESENSITIVEなどのスタイル`SetExtendedStyle`を設定するために使用します。 詳細については、トピックで説明されているスタイルを参照してください[コンボボックスExコントロール拡張スタイル](/windows/win32/Controls/comboboxex-control-extended-styles)Windows SDK で。

## <a name="ccomboboxexdeleteitem"></a><a name="deleteitem"></a>Cコンボボックスエックス::Dエレテアイテム

コントロールから項目を`ComboBoxEx`削除します。

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
削除する項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

コントロールに残っている項目の数。 *iIndex*が無効な場合、関数はCB_ERRを返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem)の機能を実装します。 DeleteItem を呼び出すと、CBEN_DELETEITEM通知を伴う[WM_NOTIFY](/windows/win32/controls/wm-notify)メッセージが親ウィンドウに送信されます。

## <a name="ccomboboxexgetcomboboxctrl"></a><a name="getcomboboxctrl"></a>次の値を取得します。

`CComboBoxEx`オブジェクト内のコンボ ボックス コントロールへのポインターを取得します。

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>戻り値

`CComboBox` オブジェクトを指すポインターです。

### <a name="remarks"></a>解説

コントロール`CComboBoxEx`は、親ウィンドウで構成され、. `CComboBox`

戻`CComboBox`り値によって指されるオブジェクトは一時オブジェクトであり、次のアイドル処理時間中に破棄されます。

## <a name="ccomboboxexgeteditctrl"></a><a name="geteditctrl"></a>次の項目を使用します。

コンボ ボックスのエディット コントロールへのポインターを取得します。

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>戻り値

[CEdit](../../mfc/reference/cedit-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

コントロール`CComboBoxEx`は、CBS_DROPDOWN スタイルで作成するときに、エディット ボックスを使用します。

戻`CEdit`り値によって指されるオブジェクトは一時オブジェクトであり、次のアイドル処理時間中に破棄されます。

## <a name="ccomboboxexgetextendedstyle"></a><a name="getextendedstyle"></a>Cコンボボックスエクスックス::ゲットエクステンドスタイル

`CComboBoxEx`コントロールに使用される拡張スタイルを取得します。

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックス コントロールに使用される拡張スタイルを含む DWORD 値。

### <a name="remarks"></a>解説

これらのスタイルの詳細については、Windows SDK の[「ComboBoxEx コントロール拡張スタイル](/windows/win32/Controls/comboboxex-control-extended-styles)」を参照してください。

## <a name="ccomboboxexgetimagelist"></a><a name="getimagelist"></a>を使用します。

`CComboBoxEx`コントロールで使用されるイメージ リストへのポインターを取得します。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

[オブジェクト](../../mfc/reference/cimagelist-class.md)へのポインター。 失敗した場合、このメンバー関数は NULL を返します。

### <a name="remarks"></a>解説

戻`CImageList`り値によって指されるオブジェクトは一時オブジェクトであり、次のアイドル処理時間中に破棄されます。

## <a name="ccomboboxexgetitem"></a><a name="getitem"></a>をクリックします。

指定`ComboBoxEx`した項目の項目情報を取得します。

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
項目情報を受け取る[コンボボックスEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)構造体へのポインター。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_GETITEM](/windows/win32/Controls/cbem-getitem)の機能を実装します。

## <a name="ccomboboxexhaseditchanged"></a><a name="haseditchanged"></a>Cコンボボックスエクスックス::ハズエディット変更

ユーザーがエディット コントロールの内容を変更`ComboBoxEx`したかどうかを調べます。

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>戻り値

ユーザーがコントロールのエディット ボックスに入力した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged)の機能を実装します。

## <a name="ccomboboxexinsertitem"></a><a name="insertitem"></a>を挿入します。

コントロールに新しい項目を`ComboBoxEx`挿入します。

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
項目情報を受け取る[コンボボックスEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)構造体へのポインター。 この構造体には、アイテムのコールバック フラグ値が含まれています。

### <a name="return-value"></a>戻り値

正常終了した場合は、新しい項目が挿入されたインデックス。それ以外の場合は -1。

### <a name="remarks"></a>解説

を呼び`InsertItem`出すと[、CBEN_INSERTITEM通知](/windows/win32/Controls/cben-insertitem)を含む[WM_NOTIFY](/windows/win32/controls/wm-notify)メッセージが親ウィンドウに送信されます。

## <a name="ccomboboxexsetextendedstyle"></a><a name="setextendedstyle"></a>Cコンボボックスエクスックス::セットエクステンドスタイル

コンボ ボックスの拡張コントロールに使用される拡張スタイルを設定します。

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>パラメーター

*ドウエックスマスク*<br/>
*dwExStyles*内のどのスタイルが影響を受けるかを示す DWORD 値。 *dwExMask*の拡張スタイルのみが変更されます。 他のすべてのスタイルはそのまま維持されます。 このパラメータが 0 の場合 *、dwExStyles*のすべてのスタイルが影響を受けます。

*ドウェエクススタイル*<br/>
コントロールに設定するコンボ ボックス コントロールの拡張スタイルを含む DWORD 値。

### <a name="return-value"></a>戻り値

コントロールで以前に使用されていた拡張スタイルを含む DWORD 値。

### <a name="remarks"></a>解説

これらのスタイルの詳細については、Windows SDK の[「ComboBoxEx コントロール拡張スタイル](/windows/win32/Controls/comboboxex-control-extended-styles)」を参照してください。

拡張ウィンドウ スタイルを持つコンボ ボックス拡張コントロールを作成するには[、CreateEx](#createex)を使用します。

## <a name="ccomboboxexsetimagelist"></a><a name="setimagelist"></a>を使用します。

コントロールのイメージ リストを`ComboBoxEx`設定します。

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
コントロールで使用する`CImageList`イメージを含むオブジェクトへのポインター。 `CComboBoxEx`

### <a name="return-value"></a>戻り値

`CComboBoxEx`コントロールで以前に使用されていたイメージを含む[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトへのポインター。 イメージ リストが以前に設定されていない場合は NULL。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist)の機能を実装します。 既定のエディット コントロールの高さを変更する場合は、Win32 関数[SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos)を呼び`SetImageList`出して、呼び出した後にコントロールのサイズを変更するか、正しく表示されません。

戻`CImageList`り値によって指されるオブジェクトは一時オブジェクトであり、次のアイドル処理時間中に破棄されます。

## <a name="ccomboboxexsetitem"></a><a name="setitem"></a>を設定します。

コントロール内の項目の属性を`ComboBoxEx`設定します。

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
項目情報を受け取る[コンボボックスEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)構造体へのポインター。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、メッセージ[CBEM_SETITEM](/windows/win32/Controls/cbem-setitem)の機能を実装します。

## <a name="ccomboboxexsetwindowtheme"></a><a name="setwindowtheme"></a>Cコンボボックスエクスックス::セットウィンドウテーマ

拡張コンボ ボックス コントロールの表示スタイルを設定します。

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
設定する拡張コンボ ボックスのビジュアル スタイルを含む Unicode 文字列へのポインター。

### <a name="return-value"></a>戻り値

戻り値は使用されません。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように[、CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme)メッセージの機能をエミュレートします。

## <a name="see-also"></a>関連項目

[MFC サンプル MFCIE](../../overview/visual-cpp-samples.md)<br/>
[Cコンボボックスクラス](../../mfc/reference/ccombobox-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[Cコンボボックスクラス](../../mfc/reference/ccombobox-class.md)
