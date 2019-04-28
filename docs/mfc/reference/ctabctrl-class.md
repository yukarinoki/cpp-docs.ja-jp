---
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
ms.openlocfilehash: ccf35c7a036a69487d5138baf8c017f9c5995bef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323714"
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
|[CTabCtrl::CTabCtrl](#ctabctrl)|`CTabCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTabCtrl::AdjustRect](#adjustrect)|ウィンドウの四角形の指定、タブ コントロールの表示領域を計算または、特定の表示領域に対応するウィンドウの四角形を計算します。|
|[CTabCtrl::Create](#create)|タブ コントロールを作成のインスタンスに接続されると、`CTabCtrl`オブジェクト。|
|[CTabCtrl::CreateEx](#createex)|指定された Windows の拡張スタイルでタブ コントロールを作成します。 のインスタンスに接続されると、`CTabCtrl`オブジェクト。|
|[CTabCtrl::DeleteAllItems](#deleteallitems)|タブ コントロールからすべての項目を削除します。|
|[CTabCtrl::DeleteItem](#deleteitem)|タブ コントロールから項目を削除します。|
|[CTabCtrl::DeselectAll](#deselectall)|いずれかの押されたキーがオフにすると、タブ コントロール内の項目をリセットします。|
|[CTabCtrl::DrawItem](#drawitem)|タブ コントロールの指定した項目を描画します。|
|[CTabCtrl::GetCurFocus](#getcurfocus)|タブ コントロールの現在のフォーカスを持つタブを取得します。|
|[CTabCtrl::GetCurSel](#getcursel)|タブ コントロールで現在選択されているタブを決定します。|
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|タブ コントロールで使用される拡張スタイルを取得します。|
|[CTabCtrl::GetImageList](#getimagelist)|タブ コントロールに関連付けられているイメージ リストを取得します。|
|[CTabCtrl::GetItem](#getitem)|タブ コントロールのタブについての情報を取得します。|
|[CTabCtrl::GetItemCount](#getitemcount)|タブ コントロールのタブの数を取得します。|
|[CTabCtrl::GetItemRect](#getitemrect)|タブ コントロール内のタブの外接する四角形を取得します。|
|[CTabCtrl::GetItemState](#getitemstate)|指定されたタブ コントロール項目の状態を取得します。|
|[CTabCtrl::GetRowCount](#getrowcount)|タブ コントロールのタブの行の現在の数を取得します。|
|[CTabCtrl::GetToolTips](#gettooltips)|タブ コントロールに関連付けられたツール ヒント コントロールのハンドルを取得します。|
|[CTabCtrl::HighlightItem](#highlightitem)|タブ項目の強調表示状態を設定します。|
|[CTabCtrl::HitTest](#hittest)|どのタブがある場合、指定した画面位置を決定します。|
|[CTabCtrl::InsertItem](#insertitem)|タブ コントロールの新しいタブを挿入します。|
|[CTabCtrl::RemoveImage](#removeimage)|タブ コントロールのイメージ リストからイメージを削除します。|
|[CTabCtrl::SetCurFocus](#setcurfocus)|タブ コントロール内の指定したタブにフォーカスを設定します。|
|[CTabCtrl::SetCurSel](#setcursel)|タブ コントロールでタブを選択します。|
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|タブ コントロールの拡張スタイルを設定します。|
|[CTabCtrl::SetImageList](#setimagelist)|イメージ リストをタブ コントロールに割り当てます。|
|[CTabCtrl::SetItem](#setitem)|タブの属性の一部またはすべてを設定します。|
|[CTabCtrl::SetItemExtra](#setitemextra)|タブ コントロール内のアプリケーションで定義されたデータ用に予約をタブごとのバイト数を設定します。|
|[CTabCtrl::SetItemSize](#setitemsize)|項目の高さと幅を設定します。|
|[CTabCtrl::SetItemState](#setitemstate)|指定されたタブ コントロール項目の状態を設定します。|
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|タブ コントロール項目の最小の幅を設定します。|
|[CTabCtrl::SetPadding](#setpadding)|各タブのアイコンとラベルのタブ コントロールの周囲には、(埋め込み) 領域の量を設定します。|
|[CTabCtrl::SetToolTips](#settooltips)|ツール ヒント コントロールをタブ コントロールに割り当てます。|

## <a name="remarks"></a>Remarks

「タブ コントロール」は、ノートの仕切ページまたはファイル キャビネットのラベルに似ています。 タブ コントロールを使用すると、アプリケーションでウィンドウまたはダイアログ ボックスの同じ領域に複数のページを定義できます。 各ページは、一連の情報またはユーザーが、対応するタブを選択すると、アプリケーションで表示するコントロールのグループで構成されます。特殊な種類のタブ コントロールには、ボタンのようなタブが表示されます。 ボタンをクリックしてページを表示するのではなく、コマンドが実行されます。

このコントロール (つまり、`CTabCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。

使用しての詳細については`CTabCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CTabCtrl](../../mfc/using-ctabctrl.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

##  <a name="adjustrect"></a>  CTabCtrl::AdjustRect

ウィンドウの四角形の指定、タブ コントロールの表示領域を計算または、特定の表示領域に対応するウィンドウの四角形を計算します。

```
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*き*<br/>
実行する操作を示します。 このパラメーターが TRUE の場合*lpRect*表示の四角形を指定し、対応するウィンドウの四角形を受信します。 このパラメーターが FALSE の場合*lpRect*ウィンドウ四角形を指定し、対応する表示する四角形を受信します。

*lpRect*<br/>
ポインターを[RECT](/previous-versions/dd162897\(v=vs.85\))を指定した四角形を指定し、計算される四角形を受け取る構造体。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

##  <a name="create"></a>  CTabCtrl::Create

タブ コントロールを作成のインスタンスに接続されると、`CTabCtrl`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
タブ コントロールのスタイルを指定します。 任意の組み合わせを適用[タブ コントロールのスタイル](/windows/desktop/Controls/tab-control-styles)Windows SDK で説明します。 参照してください**解説**に対して一連のコントロールに適用することもできます。 ウィンドウ スタイル。

*rect*<br/>
タブ コントロールのサイズと位置を指定します。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/previous-versions/dd162897\(v=vs.85\))構造体。

*pParentWnd*<br/>
タブ コントロールの親ウィンドウを通常を指定します、`CDialog`します。 NULL は指定できません。

*nID*<br/>
タブ コントロールの ID を指定します

### <a name="return-value"></a>戻り値

オブジェクトの初期化が成功した場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

構築する、 `CTabCtrl` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出してを呼び出して`Create`、タブ コントロールを作成しにアタッチする`CTabCtrl`オブジェクト。

タブ コントロールのスタイルに加え、タブ コントロールを次のウィンドウ スタイルを適用できます。

- WS_CHILD は、タブ コントロールを表す子ウィンドウを作成します。 WS_POPUP スタイルでは使用できません。

- WS_VISIBLE は、最初に表示されるタブ コントロールを作成します。

- WS_DISABLED は、最初に無効になっているウィンドウを作成します。

- WS_GROUP では、最初のコントロールをユーザーに移動できます 1 つのコントロールから、[次へ] 矢印キーでコントロールのグループを指定します。 最初のコントロールが同じグループに属している後に WS_GROUP スタイルで定義されたすべてのコントロール。 WS_GROUP スタイルでは、次のコントロールは、スタイルのグループを終了し、[次へ] のグループ (は、1 つのグループの末尾が次の開始位置) を開始します。

- WS_TABSTOP を指定します任意の数のいずれかのコントロールにより、ユーザーが TAB キーを使用して移動できます。 TAB キーでは、WS_TABSTOP スタイルで指定された次のコントロールにユーザーを移動します。

拡張ウィンドウ スタイルを使用して、タブ コントロールを作成するには、呼び出す[CTabCtrl::CreateEx](#createex)の代わりに`Create`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

##  <a name="createex"></a>  CTabCtrl::CreateEx

コントロール (子ウィンドウ) を作成しに関連付けます、`CTabCtrl`オブジェクト。

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
作成されるコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK に含まれています。

*dwStyle*<br/>
タブ コントロールのスタイルを指定します。 任意の組み合わせを適用[タブ コントロールのスタイル](/windows/desktop/Controls/tab-control-styles)Windows SDK で説明します。 参照してください**解説**で[作成](#create)に対して一連のコントロールに適用することもできます。 ウィンドウ スタイル。

*rect*<br/>
参照を[RECT](/previous-versions/dd162897\(v=vs.85\))のクライアント座標で、作成するには、ウィンドウの位置とサイズを記述する構造体*pParentWnd*します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。 それ以外の場合は 0。

### <a name="remarks"></a>Remarks

使用`CreateEx`の代わりに[作成](#create)、Windows の拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。

`CreateEx` 指定された拡張の Windows スタイルでコントロールを作成します。 *dwExStyle*します。 拡張を使用してコントロールに固有のスタイル セット[SetExtendedStyle](#setextendedstyle)します。 たとえば、使用して`CreateEx`WS_EX_CONTEXTHELP、としてこのようなスタイルの設定が使用する`SetExtendedStyle`TCS_EX_FLATSEPARATORS としてこのようなスタイルを設定します。 詳細についてで説明されているスタイルを参照してください。[タブ コントロールの拡張スタイル](/windows/desktop/Controls/tab-control-extended-styles)Windows SDK に含まれています。

##  <a name="ctabctrl"></a>  CTabCtrl::CTabCtrl

`CTabCtrl` オブジェクトを構築します。

```
CTabCtrl();
```

##  <a name="deleteallitems"></a>  CTabCtrl::DeleteAllItems

タブ コントロールからすべての項目を削除します。

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="deleteitem"></a>  CTabCtrl::DeleteItem

タブ コントロールから指定した項目を削除します。

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
削除する項目の 0 から始まる値。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

##  <a name="deselectall"></a>  CTabCtrl::DeselectAll

いずれかの押されたキーがオフにすると、タブ コントロール内の項目をリセットします。

```
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>パラメーター

*fExcludeFocus*<br/>
項目の選択解除のスコープを指定するフラグ。 このパラメーターが FALSE に設定されている場合は、すべてのタブのボタンがリセットされます。 すべてのタブの項目が現在選択されている 1 つを除く、TRUE に設定されている場合はリセットされます。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[TCM_DESELECTALL](/windows/desktop/Controls/tcm-deselectall)」の説明に従って、Windows SDK。

##  <a name="drawitem"></a>  CTabCtrl::DrawItem

ビジュアルな部分のオーナー描画タブ コントロールが変更されたときにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
ポインターを[DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)構造体を描画する項目を記述します。

### <a name="remarks"></a>Remarks

`itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行する描画の動作を定義します。

既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CTabCtrl`オブジェクト。

アプリケーションで提供されるディスプレイ コンテキスト用に選択したすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*このメンバーの前に、関数が終了します。

##  <a name="getcurfocus"></a>  CTabCtrl::GetCurFocus

現在フォーカスがあるタブのインデックスを取得します。

```
int GetCurFocus() const;
```

### <a name="return-value"></a>戻り値

現在フォーカスがあるタブの 0 から始まるインデックス。

##  <a name="getcursel"></a>  CTabCtrl::GetCurSel

タブ コントロールで現在選択されているタブを取得します。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、選択されているタブまたはタブが選択されていない場合は 1 の 0 から始まるインデックス。

##  <a name="getextendedstyle"></a>  CTabCtrl::GetExtendedStyle

タブ コントロールで使用される拡張スタイルを取得します。

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>戻り値

タブ コントロールで使用されている拡張スタイルを表します。 この値の組み合わせである[タブ コントロールのスタイルを拡張](/windows/desktop/Controls/tab-control-extended-styles)」の説明に従って、Windows SDK。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[TCM_GETEXTENDEDSTYLE](/windows/desktop/Controls/tcm-getextendedstyle)」の説明に従って、Windows SDK。

##  <a name="getimagelist"></a>  CTabCtrl::GetImageList

タブ コントロールに関連付けられているイメージ リストを取得します。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

成功した場合、タブのイメージ リストへのポインターを制御します。それ以外の場合は NULL です。

##  <a name="getitem"></a>  CTabCtrl::GetItem

タブ コントロールのタブについての情報を取得します。

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
タブの 0 から始まるインデックス。

*pTabCtrlItem*<br/>
ポインターを[TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema)構造体を取得する情報を指定するために使用します。 タブの情報を受信するも使用されます。この構造体を併用、 `InsertItem`、 `GetItem`、および`SetItem`メンバー関数。

### <a name="return-value"></a>戻り値

成功した場合、TRUE を返しますFALSE それ以外の場合。

### <a name="remarks"></a>Remarks

メッセージが送信されるときに、`mask`メンバーが返される属性を指定します。 場合、`mask`メンバー TCIF_TEXT 値を指定する、`pszText`メンバーは、項目のテキストを受け取るバッファーのアドレスを含める必要があります、`cchTextMax`メンバーは、バッファーのサイズを指定する必要があります。

- `mask`

   これを指定する値`TCITEM`構造メンバーを取得または設定します。 このメンバーには、0 または次の値の組み合わせを指定できます。

   - TCIF_TEXT、`pszText`メンバーは有効です。

   - TCIF_IMAGE、`iImage`メンバーは有効です。

   - TCIF_PARAM、`lParam`メンバーは有効です。

   - TCIF_RTLREADING テキストの`pszText`ヘブライ語やアラビア語のシステムで右から左への読み取り順序を使用して表示されます。

   - TCIF_STATE、`dwState`メンバーは有効です。

- `pszText`

   構造体には、タブについての情報が含まれている場合は、タブのテキストを含む null で終わる文字列へのポインター。構造情報の受信は、このメンバーは、タブのテキストを受け取るバッファーのアドレスを指定します。

- `cchTextMax`

   バッファーのサイズが指す`pszText`します。 このメンバーには、構造体は、情報を受信していない場合は無視されます。

- `iImage` タブの画像がない場合は、タブ コントロールのイメージ リスト、または 1 をインデックスです。

- `lParam`

   タブに関連付けられているアプリケーション定義のデータ。4 バイトを超えるタブごとのアプリケーション定義のデータがある場合は、アプリケーションする必要があります構造体を定義しの代わりに使用、`TCITEM`構造体。 アプリケーション定義の構造体の最初のメンバーである必要があります、[アプリケーション定義](/windows/desktop/api/commctrl/ns-commctrl-tagtcitemheadera)構造体。 `TCITEMHEADER`構造体のと同じですが、`TCITEM`構造体が、`lParam`メンバー。 構造のサイズとのサイズの差、`TCITEMHEADER`構造はタブごとの追加のバイト数と等しく必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

##  <a name="getitemcount"></a>  CTabCtrl::GetItemCount

タブ コントロールのタブの数を取得します。

```
int GetItemCount() const;
```

### <a name="return-value"></a>戻り値

タブ コントロール内の項目の数。

### <a name="example"></a>例

  例をご覧ください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。

##  <a name="getitemrect"></a>  CTabCtrl::GetItemRect

タブ コントロール内の指定したタブの外接する四角形を取得します。

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
タブ アイテムの 0 から始まるインデックス。

*lpRect*<br/>
ポインターを[RECT](/previous-versions/dd162897\(v=vs.85\))  タブの外接する四角形を受け取る。これらの座標は、ビューポートの現在のマッピング モードを使用します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  例をご覧ください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。

##  <a name="getitemstate"></a>  CTabCtrl::GetItemState

識別されるタブ コントロール項目の状態を取得*nItem*します。

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
状態情報を取得する対象の項目の 0 から始まるインデックス番号。

*dwMask*<br/>
返される項目の状態のフラグを指定するマスク。 値の一覧は、のマスクのメンバーを参照してください、 [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Windows SDK」の説明に従って、構造体します。

### <a name="return-value"></a>戻り値

状態情報を受け取る DWORD 値への参照。 次のいずれかの値になります。

|[値]|説明|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|タブ コントロールの項目が選択されます。|
|TCIS_HIGHLIGHTED|タブ コントロールの項目が強調表示されているし、タブとテキストは現在強調表示色を使用して描画します。 強調表示色を使用する場合は true。 補間、ディザリングされた色ではないになります。|

### <a name="remarks"></a>Remarks

項目の状態がで指定された、`dwState`のメンバー、`TCITEM`構造体。

##  <a name="getrowcount"></a>  CTabCtrl::GetRowCount

現在のタブ コントロールの行の数を取得します。

```
int GetRowCount() const;
```

### <a name="return-value"></a>戻り値

タブ コントロールのタブの行の数。

### <a name="remarks"></a>Remarks

TCS_MULTILINE スタイルのタブ コントロールだけでは、複数行のタブを持つことができます。

##  <a name="gettooltips"></a>  CTabCtrl::GetToolTips

タブ コントロールに関連付けられたツール ヒント コントロールのハンドルを取得します。

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>戻り値

成功した場合のツール ヒント コントロールのハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

タブ コントロールは、TCS_TOOLTIPS スタイルがある場合、ツール ヒント コントロールを作成します。 使用して、タブ コントロールに、ツール ヒント コントロールを割り当てることができますも、`SetToolTips`メンバー関数。

##  <a name="highlightitem"></a>  CTabCtrl::HighlightItem

タブ項目の強調表示状態を設定します。

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>パラメーター

*idItem*<br/>
タブ コントロール項目の 0 から始まるインデックス。

*fHighlight*<br/>
強調表示状態の設定を指定する値。 この値が TRUE の場合、タブが強調表示されます。FALSE の場合、タブは、既定の状態に設定されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージを実装して[TCM_HIGHLIGHTITEM](/windows/desktop/Controls/tcm-highlightitem)」の説明に従って、Windows SDK。

##  <a name="hittest"></a>  CTabCtrl::HitTest

どのタブがある場合、指定した画面位置を決定します。

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>パラメーター

*pHitTestInfo*<br/>
ポインターを[TCHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtchittestinfo)をテストする画面位置を示す、Windows SDK に」の説明に従って、構造体します。

### <a name="return-value"></a>戻り値

指定した位置にタブがない場合は、タブ、または 1 の 0 から始まるインデックスを返します。

##  <a name="insertitem"></a>  CTabCtrl::InsertItem

既存のタブ コントロールで新しいタブを挿入します。

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
新しいタブの 0 から始まるインデックス。

*pTabCtrlItem*<br/>
ポインターを[TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema)構造 タブの属性を指定します。

*lpszItem*<br/>
タブのテキストを含む null で終わる文字列のアドレス。

*nImage*<br/>
イメージ リストから挿入するイメージの 0 から始まるインデックス。

*いる*<br/>
指定します`TCITEM`に設定する属性の構造体します。 0 または次の値の組み合わせを指定できます。

- TCIF_TEXT、`pszText`メンバーは有効です。

- TCIF_IMAGE、`iImage`メンバーは有効です。

- TCIF_PARAM、 *lParam*メンバーは有効です。

- TCIF_RTLREADING テキストの`pszText`ヘブライ語やアラビア語のシステムで右から左への読み取り順序を使用して表示されます。

- TCIF_STATE、 *dwState*メンバーは有効です。

*lParam*<br/>
タブに関連付けられているアプリケーション定義のデータ。

*dwState*<br/>
項目の状態の値を指定します。 詳細については、次を参照してください。 [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Windows SDK に含まれています。

*dwStateMask*<br/>
どの状態に設定するのを指定します。 詳細については、次を参照してください。 [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

成功した場合は、新しいタブの 0 から始まるインデックスそれ以外の場合 - 1。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

##  <a name="removeimage"></a>  CTabCtrl::RemoveImage

タブ コントロールのイメージ リストから、指定されたイメージを削除します。

```
void RemoveImage(int nImage);
```

### <a name="parameters"></a>パラメーター

*nImage*<br/>
削除するイメージの 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

タブ コントロールは、各タブは、同じイメージに関連付けられて保持されるように各タブのイメージのインデックスを更新します。

##  <a name="setcurfocus"></a>  CTabCtrl::SetCurFocus

タブ コントロール内の指定したタブにフォーカスを設定します。

```
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
フォーカスを取得するタブのインデックスを指定します。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[TCM_SETCURFOCUS](/windows/desktop/Controls/tcm-setcurfocus)」の説明に従って、Windows SDK。

##  <a name="setcursel"></a>  CTabCtrl::SetCurSel

タブ コントロールでタブを選択します。

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
選択する項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

成功した場合、以前に選択したタブの 0 から始まるインデックスそれ以外の場合 - 1。

### <a name="remarks"></a>Remarks

タブ コントロールは、この関数を使用して、タブを選択した場合は、または TCN_SELCHANGE 通知メッセージを送信しません。 WM_NOTIFY を使用して、ユーザーがクリックするか、キーボードを使用して、タブを変更するときにこれらの通知が送信されます。

##  <a name="setextendedstyle"></a>  CTabCtrl::SetExtendedStyle

タブ コントロールの拡張スタイルを設定します。

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>パラメーター

*dwNewStyle*<br/>
タブの組み合わせを指定する値は、拡張スタイルを制御します。

*dwExMask*<br/>
スタイルを示す DWORD 値*dwNewStyle*が影響を受けます。 拡張スタイルのみ*dwExMask*変更されます。 その他のすべてのスタイルは、現状維持されます。 このパラメーターが 0 の場合、すべてのスタイルの場合*dwNewStyle*を受けます。

### <a name="return-value"></a>戻り値

以前の DWORD 値[タブ コントロールのスタイルを拡張](/windows/desktop/Controls/tab-control-extended-styles)」の説明に従って、Windows SDK。

### <a name="return-value"></a>戻り値

このメンバー関数は、Win32 メッセージの動作を実装[TCM_SETEXTENDEDSTYLE](/windows/desktop/Controls/tcm-setextendedstyle)」の説明に従って、Windows SDK。

##  <a name="setimagelist"></a>  CTabCtrl::SetImageList

イメージ リストをタブ コントロールに割り当てます。

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*pImageList*<br/>
タブ コントロールに割り当てられるイメージ リストへのポインター。

### <a name="return-value"></a>戻り値

前のイメージ リストが存在しない場合は、直前のイメージ リストまたは NULL にポインターを返します。

##  <a name="setitem"></a>  CTabCtrl::SetItem

タブの属性の一部またはすべてを設定します。

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
項目の 0 から始まるインデックス。

*pTabCtrlItem*<br/>
ポインターを[TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema)アイテムの新しい属性を含む構造体。 `mask`メンバーを設定する属性を指定します。 場合、`mask`メンバー TCIF_TEXT 値を指定する、`pszText`メンバーが null で終わる文字列のアドレスと`cchTextMax`メンバーは無視されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  例をご覧ください[GetItem](#getitem)します。

##  <a name="setitemextra"></a>  CTabCtrl::SetItemExtra

タブ コントロール内のアプリケーションで定義されたデータ用に予約をタブごとのバイト数を設定します。

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
設定する追加のバイト数。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[TCM_SETITEMEXTRA](/windows/desktop/Controls/tcm-setitemextra)」の説明に従って、Windows SDK。

##  <a name="setitemsize"></a>  CTabCtrl::SetItemSize

タブ コントロール項目の幅と高さを設定します。

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
タブ コントロール項目の新しい幅と高さ (ピクセル単位)。

### <a name="return-value"></a>戻り値

タブ コントロール項目の古い幅と高さを返します。

##  <a name="setitemstate"></a>  CTabCtrl::SetItemState

識別されるタブ コントロール項目の状態を設定*nItem*します。

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
状態情報を設定する対象の項目の 0 から始まるインデックス番号。

*dwMask*<br/>
項目の状態のフラグ設定を指定するマスク。 値の一覧は、のマスクのメンバーを参照してください、 [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Windows SDK」の説明に従って、構造体します。

*dwState*<br/>
状態情報を含む DWORD 値への参照。 次のいずれかの値になります。

|[値]|説明|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|タブ コントロールの項目が選択されます。|
|TCIS_HIGHLIGHTED|タブ コントロールの項目が強調表示されているし、タブとテキストは現在強調表示色を使用して描画します。 強調表示色を使用する場合は true。 補間、ディザリングされた色ではないになります。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="setmintabwidth"></a>  CTabCtrl::SetMinTabWidth

タブ コントロール項目の最小の幅を設定します。

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>パラメーター

*cx*<br/>
タブ コントロールの項目の設定に最小の幅。 このパラメーターが-1 に設定されている場合、コントロールは既定のタブ幅を使用します。

### <a name="return-value"></a>戻り値

前のタブの最小の幅。

### <a name="return-value"></a>戻り値

このメンバー関数は、Win32 メッセージの動作を実装[TCM_SETMINTABWIDTH](/windows/desktop/Controls/tcm-setmintabwidth)」の説明に従って、Windows SDK。

##  <a name="setpadding"></a>  CTabCtrl::SetPadding

各タブのアイコンとラベルのタブ コントロールの周囲には、(埋め込み) 領域の量を設定します。

```
void SetPadding(CSize size);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
各タブのアイコンとラベルのタブ コントロールの周囲には、(埋め込み) 領域の量を設定します。

##  <a name="settooltips"></a>  CTabCtrl::SetToolTips

ツール ヒント コントロールをタブ コントロールに割り当てます。

```
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>パラメーター

*pWndTip*<br/>
ツール ヒント コントロールのハンドル。

### <a name="remarks"></a>Remarks

呼び出すことによって、タブ コントロールに関連付けられたツール ヒント コントロールを取得する`GetToolTips`します。

### <a name="example"></a>例

  例をご覧ください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CHeaderCtrl クラス](../../mfc/reference/cheaderctrl-class.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)
