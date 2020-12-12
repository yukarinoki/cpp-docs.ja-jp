---
description: '詳細情報: CTabCtrl クラス'
title: CTabCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
ms.openlocfilehash: 363e97ec848976b78b1c75b70997ff6f4b4b5c36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318573"
---
# <a name="ctabctrl-class"></a>CTabCtrl クラス

Windows のコモン タブ コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CTabCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CTabCtrl:: CTabCtrl](#ctabctrl)|`CTabCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTabCtrl:: AdjustRect](#adjustrect)|ウィンドウの四角形を指定してタブコントロールの表示領域を計算するか、特定の表示領域に対応するウィンドウの四角形を計算します。|
|[CTabCtrl:: Create](#create)|タブコントロールを作成し、オブジェクトのインスタンスにアタッチし `CTabCtrl` ます。|
|[CTabCtrl:: CreateEx](#createex)|指定された Windows 拡張スタイルを使用してタブコントロールを作成し、オブジェクトのインスタンスにアタッチし `CTabCtrl` ます。|
|[CTabCtrl::D eleteAllItems](#deleteallitems)|タブコントロールからすべての項目を削除します。|
|[CTabCtrl::D eleteItem](#deleteitem)|タブコントロールから項目を削除します。|
|[CTabCtrl::D eselectAll](#deselectall)|タブコントロール内の項目をリセットし、押された項目をクリアします。|
|[CTabCtrl::D rawItem](#drawitem)|タブコントロールの指定された項目を描画します。|
|[CTabCtrl:: GetCurFocus](#getcurfocus)|タブコントロールの現在のフォーカスがあるタブを取得します。|
|[CTabCtrl:: GetCurSel](#getcursel)|タブコントロールで現在選択されているタブを確認します。|
|[CTabCtrl:: GetExtendedStyle](#getextendedstyle)|現在タブコントロールに使用されている拡張スタイルを取得します。|
|[CTabCtrl:: GetImageList](#getimagelist)|タブコントロールに関連付けられているイメージリストを取得します。|
|[CTabCtrl:: GetItem](#getitem)|タブコントロールのタブに関する情報を取得します。|
|[CTabCtrl:: GetItemCount](#getitemcount)|タブコントロールのタブの数を取得します。|
|[CTabCtrl:: GetItemRect](#getitemrect)|タブコントロールのタブの外接する四角形を取得します。|
|[CTabCtrl:: GetItemState](#getitemstate)|指定されたタブコントロール項目の状態を取得します。|
|[CTabCtrl:: GetRowCount](#getrowcount)|タブコントロールのタブの現在の行数を取得します。|
|[CTabCtrl:: GetToolTips ヒント](#gettooltips)|タブコントロールに関連付けられているツールヒントコントロールのハンドルを取得します。|
|[CTabCtrl:: HighlightItem](#highlightitem)|タブアイテムの強調表示の状態を設定します。|
|[CTabCtrl:: System.windows.media.visualtreehelper.hittest](#hittest)|指定した画面位置にタブがある場合は、そのタブを決定します。|
|[CTabCtrl:: InsertItem](#insertitem)|タブコントロールに新しいタブを挿入します。|
|[CTabCtrl:: RemoveImage](#removeimage)|タブコントロールのイメージリストからイメージを削除します。|
|[CTabCtrl:: SetCurFocus](#setcurfocus)|フォーカスをタブコントロールの指定したタブに設定します。|
|[CTabCtrl:: SetCurSel](#setcursel)|タブコントロールのタブを選択します。|
|[CTabCtrl:: SetExtendedStyle](#setextendedstyle)|タブコントロールの拡張スタイルを設定します。|
|[CTabCtrl:: SetImageList](#setimagelist)|イメージリストをタブコントロールに割り当てます。|
|[CTabCtrl:: SetItem](#setitem)|タブの属性の一部またはすべてを設定します。|
|[CTabCtrl:: SetItemExtra](#setitemextra)|タブコントロール内のアプリケーション定義データ用に予約されているタブあたりのバイト数を設定します。|
|[CTabCtrl:: SetItemSize](#setitemsize)|項目の幅と高さを設定します。|
|[CTabCtrl:: SetItemState](#setitemstate)|指定されたタブコントロール項目の状態を設定します。|
|[CTabCtrl:: SetMinTabWidth](#setmintabwidth)|タブコントロール内の項目の最小の幅を設定します。|
|[CTabCtrl:: SetPadding](#setpadding)|タブコントロール内の各タブのアイコンとラベルの周囲のスペース (埋め込み) のサイズを設定します。|
|[CTabCtrl:: SetToolTips ヒント](#settooltips)|ツールヒントコントロールをタブコントロールに割り当てます。|

## <a name="remarks"></a>解説

"タブコントロール" は、ノートブック内の区切り線またはファイルキャビネットのラベルに似ています。 タブ コントロールを使用すると、アプリケーションでウィンドウまたはダイアログ ボックスの同じ領域に複数のページを定義できます。 各ページは、ユーザーが対応するタブを選択したときにアプリケーションによって表示される情報のセットまたはコントロールのグループで構成されます。特殊な種類のタブコントロールには、ボタンのようなタブが表示されます。 ボタンをクリックすると、ページを表示するのではなく、すぐにコマンドが実行されます。

このコントロール (および `CTabCtrl` クラス) は、windows 95/98 および WINDOWS NT バージョン3.51 以降で実行されているプログラムに対してのみ使用できます。

の使用方法の詳細について `CTabCtrl` は、「 [コントロール](../../mfc/controls-mfc.md) 」および「 [CTabCtrl の使用](../../mfc/using-ctabctrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>要件

**ヘッダー:** afxcmn.h

## <a name="ctabctrladjustrect"></a><a name="adjustrect"></a> CTabCtrl:: AdjustRect

ウィンドウの四角形を指定してタブコントロールの表示領域を計算するか、特定の表示領域に対応するウィンドウの四角形を計算します。

```cpp
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*bLarger*<br/>
実行する操作を示します。 このパラメーターが TRUE の場合、 *lpRect* は表示用の四角形を指定し、対応するウィンドウの四角形を受け取ります。 このパラメーターが FALSE の場合、 *lpRect* はウィンドウの四角形を指定し、対応する表示四角形を受け取ります。

*lpRect*<br/>
指定された四角形を指定し、計算された四角形を受け取る [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

## <a name="ctabctrlcreate"></a><a name="create"></a> CTabCtrl:: Create

タブコントロールを作成し、オブジェクトのインスタンスにアタッチし `CTabCtrl` ます。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
タブコントロールのスタイルを指定します。 Windows SDK で説明されている [タブコントロールスタイル](/windows/win32/Controls/tab-control-styles)の任意の組み合わせを適用します。 コントロールに適用できるウィンドウスタイルの一覧については、「 **解説** 」を参照してください。

*rect*<br/>
タブコントロールのサイズと位置を指定します。 これは、 [CRect](../../atl-mfc-shared/reference/crect-class.md) オブジェクトまたは [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体のいずれかになります。

*pParentWnd*<br/>
タブコントロールの親ウィンドウ (通常は) を指定し `CDialog` ます。 NULL にすることはできません。

*nID*<br/>
タブコントロールの ID を指定します。

### <a name="return-value"></a>戻り値

オブジェクトの初期化に成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトを構築するには、 `CTabCtrl` 2 つの手順を実行します。 まず、コンストラクターを呼び出し、次に `Create` を呼び出します。これにより、タブコントロールが作成され、オブジェクトにアタッチさ `CTabCtrl` れます。

タブコントロールスタイルに加えて、次のウィンドウスタイルをタブコントロールに適用できます。

- WS_CHILD、タブコントロールを表す子ウィンドウを作成します。 WS_POPUP スタイルと共に使用することはできません。

- WS_VISIBLE、最初に表示されるタブコントロールを作成します。

- WS_DISABLED は、最初は無効になっているウィンドウを作成します。

- WS_GROUP は、ユーザーが方向キーを使用して1つのコントロールから次のコントロールに移動できる、コントロールのグループの最初のコントロールを指定します。 最初のコントロールの後に WS_GROUP スタイルで定義されているすべてのコントロールが同じグループに属しています。 WS_GROUP スタイルの次のコントロールは、スタイルグループを終了し、次のグループを開始します (つまり、次の開始位置にある1つのグループが終了します)。

- WS_TABSTOP は、TAB キーを使用してユーザーが移動できるコントロールの1つを指定します。 Tab キーは、WS_TABSTOP スタイルで指定された次のコントロールにユーザーを移動します。

拡張ウィンドウスタイルを使用してタブコントロールを作成するには、ではなく、 [CTabCtrl:: CreateEx](#createex) を呼び出し `Create` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

## <a name="ctabctrlcreateex"></a><a name="createex"></a> CTabCtrl:: CreateEx

コントロール (子ウィンドウ) を作成し、オブジェクトに関連付け `CTabCtrl` ます。

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
タブコントロールのスタイルを指定します。 Windows SDK で説明されている [タブコントロールスタイル](/windows/win32/Controls/tab-control-styles)の任意の組み合わせを適用します。 コントロールに適用できるウィンドウスタイルの一覧については、「 [Create](#create) 」の「**解説**」を参照してください。

*rect*<br/>
*PParentWnd* のクライアント座標で、作成されるウィンドウのサイズと位置を記述する [RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

成功した場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

`CreateEx`Windows 拡張スタイルの先頭 **WS_EX_** によって指定された拡張 windows スタイルを適用するには、[[作成](#create)] ではなくを使用します。

`CreateEx`*Dwexstyle* によって指定された拡張 Windows スタイルを使用して、コントロールを作成します。 [SetExtendedStyle](#setextendedstyle)を使用して、コントロールに固有の拡張スタイルを設定します。 たとえば、を使用し `CreateEx` て、このようなスタイルを WS_EX_CONTEXTHELP として設定します。ただし、を使用し `SetExtendedStyle` て、そのようなスタイルを TCS_EX_FLATSEPARATORS として設定します。 詳細については、「 [タブコントロールの拡張スタイル](/windows/win32/Controls/tab-control-extended-styles) 」で説明されている Windows SDK のスタイルに関するページを参照してください。

## <a name="ctabctrlctabctrl"></a><a name="ctabctrl"></a> CTabCtrl:: CTabCtrl

`CTabCtrl` オブジェクトを構築します。

```
CTabCtrl();
```

## <a name="ctabctrldeleteallitems"></a><a name="deleteallitems"></a> CTabCtrl::D eleteAllItems

タブコントロールからすべての項目を削除します。

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="ctabctrldeleteitem"></a><a name="deleteitem"></a> CTabCtrl::D eleteItem

指定された項目をタブコントロールから削除します。

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
削除する項目の0から始まる値。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

## <a name="ctabctrldeselectall"></a><a name="deselectall"></a> CTabCtrl::D eselectAll

タブコントロール内の項目をリセットし、押された項目をクリアします。

```cpp
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>パラメーター

*fExcludeFocus*<br/>
項目のスコープを指定するフラグ deselection。 このパラメーターが FALSE に設定されている場合は、すべてのタブボタンがリセットされます。 TRUE に設定されている場合、現在選択されている項目以外のすべてのタブ項目がリセットされます。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージの [TCM_DESELECTALL](/windows/win32/Controls/tcm-deselectall)の動作を実装します。

## <a name="ctabctrldrawitem"></a><a name="drawitem"></a> CTabCtrl::D rawItem

オーナー描画タブコントロールの外観が変化したときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
描画する項目を記述する [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 構造体へのポインター。

### <a name="remarks"></a>解説

`itemAction`構造体のメンバーは、 `DRAWITEMSTRUCT` 実行する描画アクションを定義します。

既定では、このメンバー関数は何も行いません。 オーナー描画オブジェクトの描画を実装するには、このメンバー関数をオーバーライドし `CTabCtrl` ます。

このメンバー関数が終了する前に、アプリケーションでは、 *lpDrawItemStruct* で指定された表示コンテキスト用に選択されたすべてのグラフィックスデバイスインターフェイス (GDI) オブジェクトを復元する必要があります。

## <a name="ctabctrlgetcurfocus"></a><a name="getcurfocus"></a> CTabCtrl:: GetCurFocus

現在フォーカスがあるタブのインデックスを取得します。

```
int GetCurFocus() const;
```

### <a name="return-value"></a>戻り値

現在のフォーカスがあるタブの0から始まるインデックス。

## <a name="ctabctrlgetcursel"></a><a name="getcursel"></a> CTabCtrl:: GetCurSel

タブコントロールで現在選択されているタブを取得します。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

正常に終了した場合は、選択したタブの0から始まるインデックス。タブが選択されていない場合は-1。

## <a name="ctabctrlgetextendedstyle"></a><a name="getextendedstyle"></a> CTabCtrl:: GetExtendedStyle

現在タブコントロールに使用されている拡張スタイルを取得します。

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>戻り値

タブコントロールに現在使用されている拡張スタイルを表します。 この値は、Windows SDK で説明されているように、 [タブコントロールの拡張スタイル](/windows/win32/Controls/tab-control-extended-styles)を組み合わせたものです。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TCM_GETEXTENDEDSTYLE](/windows/win32/Controls/tcm-getextendedstyle)の動作を実装します。

## <a name="ctabctrlgetimagelist"></a><a name="getimagelist"></a> CTabCtrl:: GetImageList

タブ コントロールに関連付けられているイメージ リストを取得します。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

成功した場合、タブ コントロールのイメージ リストへのポインター。それ以外の場合は、NULL。

## <a name="ctabctrlgetitem"></a><a name="getitem"></a> CTabCtrl:: GetItem

タブコントロールのタブに関する情報を取得します。

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
タブの0から始まるインデックス。

*pTabCtrlItem*<br/>
取得する情報を指定するために使用される [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 構造体へのポインター。 タブに関する情報を受信するためにも使用されます。この構造体は `InsertItem` 、、、およびの各メンバー関数と共に使用され `GetItem` `SetItem` ます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

メッセージが送信されると、 `mask` メンバーは返す属性を指定します。 メンバーが TCIF_TEXT 値を指定する場合、メンバーには `mask` `pszText` 項目テキストを受け取るバッファーのアドレスを含める必要があり、 `cchTextMax` メンバーはバッファーのサイズを指定する必要があります。

- `mask`

   `TCITEM`取得または設定する構造体メンバーを指定する値。 このメンバーは、0または次の値の組み合わせにすることができます。

  - TCIF_TEXT `pszText` メンバーが有効であることを示します。

  - TCIF_IMAGE `iImage` メンバーが有効であることを示します。

  - TCIF_PARAM `lParam` メンバーが有効であることを示します。

  - `pszText`ヘブライ語またはアラビア語のシステムで右から左への読み取り順序を使用して、のテキスト TCIF_RTLREADING 表示されます。

  - TCIF_STATE `dwState` メンバーが有効であることを示します。

- `pszText`

   タブに関する情報が構造体に含まれている場合、タブテキストを含む null で終わる文字列へのポインター。構造体が情報を受け取っている場合、このメンバーはタブテキストを受け取るバッファーのアドレスを指定します。

- `cchTextMax`

   が指すバッファーのサイズ `pszText` 。 構造体が情報を受け取っていない場合、このメンバーは無視されます。

- `iImage` タブコントロールのイメージリストのインデックス。タブのイメージがない場合は-1。

- `lParam`

   タブに関連付けられているアプリケーション定義データ。タブごとにアプリケーション定義データが4バイトを超える場合は、アプリケーションで構造を定義し、構造の代わりに使用する必要があり `TCITEM` ます。 アプリケーション定義構造体の最初のメンバーは、 [Tcitemheader](/windows/win32/api/commctrl/ns-commctrl-tcitemheaderw)構造体である必要があります。 `TCITEMHEADER`構造体は構造体と同じです `TCITEM` が、メンバーは含まれませ `lParam` ん。 構造体のサイズと構造体のサイズの違いは、 `TCITEMHEADER` タブごとに余分なバイト数と同じにする必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

## <a name="ctabctrlgetitemcount"></a><a name="getitemcount"></a> CTabCtrl:: GetItemCount

タブコントロールのタブの数を取得します。

```
int GetItemCount() const;
```

### <a name="return-value"></a>戻り値

タブコントロール内の項目の数。

### <a name="example"></a>例

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)の例を参照してください。

## <a name="ctabctrlgetitemrect"></a><a name="getitemrect"></a> CTabCtrl:: GetItemRect

タブコントロール内の指定したタブの外接する四角形を取得します。

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
タブ項目の0から始まるインデックス。

*lpRect*<br/>
タブの外接する四角形を受け取る [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体へのポインター。これらの座標は、ビューポートの現在のマッピングモードを使用します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)の例を参照してください。

## <a name="ctabctrlgetitemstate"></a><a name="getitemstate"></a> CTabCtrl:: GetItemState

*NItem* によって識別されるタブコントロール項目の状態を取得します。

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
状態情報を取得する項目の0から始まるインデックス番号。

*dwMask*<br/>
返す項目の状態フラグのうち、どれを返すかを指定するマスク。 値の一覧については、「Windows SDK」で説明されているように、 [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 構造体の mask メンバーを参照してください。

### <a name="return-value"></a>戻り値

状態情報を受け取る DWORD 値への参照。 次の値のいずれかです。

|値|説明|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|タブコントロール項目が選択されています。|
|TCIS_HIGHLIGHTED|タブコントロール項目が強調表示され、現在の強調表示色を使用してタブとテキストが描画されます。 強調表示色を使用すると、これはディザーの色ではなく、真の補間になります。|

### <a name="remarks"></a>解説

項目の状態は、構造体のメンバーによって指定され `dwState` `TCITEM` ます。

## <a name="ctabctrlgetrowcount"></a><a name="getrowcount"></a> CTabCtrl:: GetRowCount

タブコントロールの現在の行数を取得します。

```
int GetRowCount() const;
```

### <a name="return-value"></a>戻り値

タブコントロールのタブの行数。

### <a name="remarks"></a>解説

TCS_MULTILINE スタイルを持つタブコントロールにのみ、タブの複数の行を含めることができます。

## <a name="ctabctrlgettooltips"></a><a name="gettooltips"></a> CTabCtrl:: GetToolTips ヒント

タブコントロールに関連付けられているツールヒントコントロールのハンドルを取得します。

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、ツールヒントコントロールのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

タブコントロールに TCS_TOOLTIPS スタイルがある場合は、ツールヒントコントロールが作成されます。 また、メンバー関数を使用して、ツールヒントコントロールをタブコントロールに割り当てることもでき `SetToolTips` ます。

## <a name="ctabctrlhighlightitem"></a><a name="highlightitem"></a> CTabCtrl:: HighlightItem

タブアイテムの強調表示の状態を設定します。

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>パラメーター

*idItem*<br/>
タブコントロール項目の0から始まるインデックス。

*fHighlight 表示*<br/>
設定する強調表示の状態を指定する値。 この値が TRUE の場合、タブは強調表示されます。FALSE の場合、タブは既定の状態に設定されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TCM_HIGHLIGHTITEM](/windows/win32/Controls/tcm-highlightitem)を実装します。

## <a name="ctabctrlhittest"></a><a name="hittest"></a> CTabCtrl:: System.windows.media.visualtreehelper.hittest

指定した画面位置にタブがある場合は、そのタブを確認します。

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>パラメーター

*pHitTestInfo*<br/>
テストする画面位置を指定する Windows SDK で説明されているように、 [TCHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-tchittestinfo) 構造体へのポインター。

### <a name="return-value"></a>戻り値

タブの0から始まるインデックスを返します。指定した位置にタブがない場合は-1 を返します。

## <a name="ctabctrlinsertitem"></a><a name="insertitem"></a> CTabCtrl:: InsertItem

既存のタブコントロールに新しいタブを挿入します。

```
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam,
    DWORD dwState,
    DWORD dwStateMask);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
新しいタブの0から始まるインデックス。

*pTabCtrlItem*<br/>
タブの属性を指定する [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 構造体へのポインター。

*lpszItem*<br/>
タブのテキストを含む、null で終わる文字列のアドレス。

*nImage*<br/>
イメージリストから挿入するイメージの0から始まるインデックス。

*nMask*<br/>
`TCITEM`設定する構造体の属性を指定します。 0または次の値の組み合わせを指定できます。

- TCIF_TEXT `pszText` メンバーが有効であることを示します。

- TCIF_IMAGE `iImage` メンバーが有効であることを示します。

- TCIF_PARAM、 *lParam* メンバーが有効であることを示します。

- `pszText`ヘブライ語またはアラビア語のシステムで右から左への読み取り順序を使用して、のテキスト TCIF_RTLREADING 表示されます。

- TCIF_STATE *Dwstate* メンバーが有効であることを示します。

*lParam*<br/>
タブに関連付けられているアプリケーション定義データ。

*dwState*<br/>
項目の状態の値を指定します。 詳細については、Windows SDK の「 [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 」を参照してください。

*dwStateMask*<br/>
設定する状態を指定します。 詳細については、Windows SDK の「 [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 」を参照してください。

### <a name="return-value"></a>戻り値

成功した場合は、新しいタブの0から始まるインデックス。それ以外の場合は-1。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

## <a name="ctabctrlremoveimage"></a><a name="removeimage"></a> CTabCtrl:: RemoveImage

指定したイメージをタブコントロールのイメージリストから削除します。

```cpp
void RemoveImage(int nImage);
```

### <a name="parameters"></a>パラメーター

*nImage*<br/>
削除するイメージの0から始まるインデックス。

### <a name="remarks"></a>解説

タブコントロールは各タブのイメージインデックスを更新するため、各タブは同じイメージに関連付けられたままになります。

## <a name="ctabctrlsetcurfocus"></a><a name="setcurfocus"></a> CTabCtrl:: SetCurFocus

フォーカスをタブコントロールの指定したタブに設定します。

```cpp
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
フォーカスを取得するタブのインデックスを指定します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TCM_SETCURFOCUS](/windows/win32/Controls/tcm-setcurfocus)の動作を実装します。

## <a name="ctabctrlsetcursel"></a><a name="setcursel"></a> CTabCtrl:: SetCurSel

タブコントロールのタブを選択します。

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
選択する項目の0から始まるインデックス。

### <a name="return-value"></a>戻り値

成功した場合は、以前に選択されたタブの0から始まるインデックス。それ以外の場合は-1。

### <a name="remarks"></a>解説

この関数を使用してタブを選択した場合、タブコントロールは TCN_SELCHANGING または TCN_SELCHANGE 通知メッセージを送信しません。 これらの通知は、ユーザーがキーボードをクリックまたは使用してタブを変更したときに、WM_NOTIFY を使用して送信されます。

## <a name="ctabctrlsetextendedstyle"></a><a name="setextendedstyle"></a> CTabCtrl:: SetExtendedStyle

タブコントロールの拡張スタイルを設定します。

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>パラメーター

*dwNewStyle*<br/>
タブコントロールの拡張スタイルの組み合わせを指定する値。

*dwExMask*<br/>
*Dwnewstyle* で影響を受けるスタイルを示す DWORD 値です。 *Dwexmask* の拡張スタイルのみが変更されます。 その他のすべてのスタイルはそのまま維持されます。 このパラメーターが0の場合、 *Dwnewstyle* のすべてのスタイルが影響を受けます。

### <a name="return-value"></a>戻り値

Windows SDK で説明されているように、前の [タブコントロールの拡張スタイル](/windows/win32/Controls/tab-control-extended-styles)を含む DWORD 値です。

### <a name="return-value"></a>戻り値

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TCM_SETEXTENDEDSTYLE](/windows/win32/Controls/tcm-setextendedstyle)の動作を実装します。

## <a name="ctabctrlsetimagelist"></a><a name="setimagelist"></a> CTabCtrl:: SetImageList

イメージリストをタブコントロールに割り当てます。

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*pImageList*<br/>
タブコントロールに割り当てられるイメージリストへのポインター。

### <a name="return-value"></a>戻り値

前のイメージリストへのポインターを返します。前のイメージリストがない場合は NULL を返します。

## <a name="ctabctrlsetitem"></a><a name="setitem"></a> CTabCtrl:: SetItem

タブの属性の一部またはすべてを設定します。

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
項目の0から始まるインデックス。

*pTabCtrlItem*<br/>
新しい項目の属性が格納されている [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 構造体へのポインター。 メンバーは、 `mask` 設定する属性を指定します。 メンバーが `mask` TCIF_TEXT 値を指定した場合、 `pszText` メンバーは null で終わる文字列のアドレスであり、 `cchTextMax` メンバーは無視されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [GetItem](#getitem)の例を参照してください。

## <a name="ctabctrlsetitemextra"></a><a name="setitemextra"></a> CTabCtrl:: SetItemExtra

タブコントロール内のアプリケーション定義データ用に予約されているタブあたりのバイト数を設定します。

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
設定する余分なバイト数。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TCM_SETITEMEXTRA](/windows/win32/Controls/tcm-setitemextra)の動作を実装します。

## <a name="ctabctrlsetitemsize"></a><a name="setitemsize"></a> CTabCtrl:: SetItemSize

タブ コントロール項目の幅と高さを設定します。

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
タブ コントロール項目の新しい幅と高さ (ピクセル単位)。

### <a name="return-value"></a>戻り値

タブ コントロール項目の古い幅と高さを返します。

## <a name="ctabctrlsetitemstate"></a><a name="setitemstate"></a> CTabCtrl:: SetItemState

*NItem* によって識別されるタブコントロール項目の状態を設定します。

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
状態情報を設定する項目の0から始まるインデックス番号。

*dwMask*<br/>
設定する項目の状態フラグを指定するマスク。 値の一覧については、「Windows SDK」で説明されているように、 [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 構造体の mask メンバーを参照してください。

*dwState*<br/>
状態情報を格納している DWORD 値への参照。 次の値のいずれかです。

|値|説明|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|タブコントロール項目が選択されています。|
|TCIS_HIGHLIGHTED|タブコントロール項目が強調表示され、現在の強調表示色を使用してタブとテキストが描画されます。 強調表示色を使用すると、これはディザーの色ではなく、真の補間になります。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="ctabctrlsetmintabwidth"></a><a name="setmintabwidth"></a> CTabCtrl:: SetMinTabWidth

タブコントロール内の項目の最小の幅を設定します。

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>パラメーター

*シリーズ*<br/>
タブコントロール項目に設定される最小の幅。 このパラメーターが-1 に設定されている場合、コントロールは既定のタブ幅を使用します。

### <a name="return-value"></a>戻り値

前の最小タブ幅。

### <a name="return-value"></a>戻り値

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TCM_SETMINTABWIDTH](/windows/win32/Controls/tcm-setmintabwidth)の動作を実装します。

## <a name="ctabctrlsetpadding"></a><a name="setpadding"></a> CTabCtrl:: SetPadding

タブコントロール内の各タブのアイコンとラベルの周囲のスペース (埋め込み) のサイズを設定します。

```cpp
void SetPadding(CSize size);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
タブコントロール内の各タブのアイコンとラベルの周囲のスペース (埋め込み) のサイズを設定します。

## <a name="ctabctrlsettooltips"></a><a name="settooltips"></a> CTabCtrl:: SetToolTips ヒント

ツールヒントコントロールをタブコントロールに割り当てます。

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>パラメーター

*pWndTip*<br/>
ツールヒントコントロールのハンドル。

### <a name="remarks"></a>解説

を呼び出すことによって、タブコントロールに関連付けられているツールヒントコントロールを取得でき `GetToolTips` ます。

### <a name="example"></a>例

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)の例を参照してください。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CHeaderCtrl クラス](../../mfc/reference/cheaderctrl-class.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)
