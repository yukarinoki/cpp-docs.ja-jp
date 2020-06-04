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
ms.openlocfilehash: 42d4b24222b1760bc418e904881edb2bb0e5a1f4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752313"
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
|[CタブCtrl::CタブCtrl](#ctabctrl)|`CTabCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CタブCtrl::アジャストレック](#adjustrect)|ウィンドウ四角形を指定したタブ コントロールの表示領域を計算するか、指定した表示領域に対応するウィンドウ四角形を計算します。|
|[CタブCtrl::作成](#create)|タブ コントロールを作成し、`CTabCtrl`オブジェクトのインスタンスにアタッチします。|
|[CタブCtrl::作成Ex](#createex)|指定した Windows 拡張スタイルを持つタブ コントロールを作成し、`CTabCtrl`オブジェクトのインスタンスにアタッチします。|
|[:Dエレテアイテム](#deleteallitems)|タブ コントロールからすべての項目を削除します。|
|[:D](#deleteitem)|タブ コントロールから項目を削除します。|
|[すべてを選択:D](#deselectall)|タブ コントロール内の項目をリセットし、押された項目をクリアします。|
|[:Dローアイテム](#drawitem)|タブ コントロールの指定した項目を描画します。|
|[CタブCtrl::ゲットカーフォーカス](#getcurfocus)|タブ コントロールの現在のフォーカスを持つタブを取得します。|
|[CタブCtrl::ゲットカーセル](#getcursel)|タブ コントロールで現在選択されているタブを決定します。|
|[を使用します。](#getextendedstyle)|タブ コントロールで現在使用されている拡張スタイルを取得します。|
|[をクリックします。](#getimagelist)|タブ コントロールに関連付けられているイメージ リストを取得します。|
|[をクリックします。](#getitem)|タブ コントロール内のタブに関する情報を取得します。|
|[を使用します。](#getitemcount)|タブ コントロール内のタブの数を取得します。|
|[をクリックします。](#getitemrect)|タブ コントロール内のタブに外接する四角形を取得します。|
|[をクリックします。](#getitemstate)|指定されたタブ コントロール項目の状態を取得します。|
|[を行います。](#getrowcount)|タブ コントロール内のタブの現在の行数を取得します。|
|[ヒントを取得します。](#gettooltips)|タブ コントロールに関連付けられているツール ヒント コントロールのハンドルを取得します。|
|[CタブCtrl::ハイライトアイテム](#highlightitem)|タブ項目の強調表示状態を設定します。|
|[ヒットテスト](#hittest)|指定した画面位置にタブがある場合に、そのタブを決定します。|
|[アイテムを挿入します。](#insertitem)|タブ コントロールに新しいタブを挿入します。|
|[イメージの削除](#removeimage)|タブ コントロールのイメージ リストからイメージを削除します。|
|[CタブCtrl::セットカーフォーカス](#setcurfocus)|タブ コントロール内の指定されたタブにフォーカスを設定します。|
|[CタブCtrl::セットカーセル](#setcursel)|タブ コントロール内のタブを選択します。|
|[CタブCtrl::セットエクステンドスタイル](#setextendedstyle)|タブ コントロールの拡張スタイルを設定します。|
|[を使用します。](#setimagelist)|タブ コントロールにイメージ リストを割り当てます。|
|[を設定します。](#setitem)|タブの属性の一部またはすべてを設定します。|
|[CタブCtrl::セットアイテムエクストラ](#setitemextra)|タブ コントロール内のアプリケーション定義データ用に予約されているタブあたりのバイト数を設定します。|
|[を切り離します。](#setitemsize)|アイテムの幅と高さを設定します。|
|[をクリックします。](#setitemstate)|指定されたタブ コントロール項目の状態を設定します。|
|[タブCtrl::セットミンタブ幅](#setmintabwidth)|タブ コントロール内の項目の最小幅を設定します。|
|[を切り替えます。](#setpadding)|タブ コントロール内の各タブのアイコンとラベルの周囲のスペース (パディング) の量を設定します。|
|[CタブCtrl::セットヒント](#settooltips)|ツール ヒント コントロールをタブ コントロールに割り当てます。|

## <a name="remarks"></a>解説

"タブコントロール" は、ノートブックの仕切りやファイル キャビネットのラベルに似ています。 タブ コントロールを使用すると、アプリケーションでウィンドウまたはダイアログ ボックスの同じ領域に複数のページを定義できます。 各ページは、ユーザーが対応するタブを選択したときにアプリケーションに表示される情報のセットまたはコントロールのグループで構成されます。特殊なタブ コントロールには、ボタンのようなタブが表示されます。 ボタンをクリックすると、ページを表示する代わりに、すぐにコマンドが実行されます。

このコントロール (および`CTabCtrl`クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

の詳細`CTabCtrl`については、「[コントロール](../../mfc/controls-mfc.md)と[CTabCtrl](../../mfc/using-ctabctrl.md)の使用 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="ctabctrladjustrect"></a><a name="adjustrect"></a>CタブCtrl::アジャストレック

ウィンドウ四角形を指定したタブ コントロールの表示領域を計算するか、指定した表示領域に対応するウィンドウ四角形を計算します。

```cpp
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*大きく*<br/>
実行する操作を示します。 このパラメーターが TRUE の場合 *、lpRect*は表示用の四角形を指定し、対応するウィンドウ四角形を受け取ります。 このパラメーターが FALSE の場合 *、lpRect*はウィンドウの四角形を指定し、対応する表示四角形を受け取ります。

*Lprect*<br/>
指定された四角形を指定し、計算された四角形を受け取る[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

## <a name="ctabctrlcreate"></a><a name="create"></a>CタブCtrl::作成

タブ コントロールを作成し、`CTabCtrl`オブジェクトのインスタンスにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
タブ コントロールのスタイルを指定します。 Windows SDK で説明されている[タブ コントロール スタイル](/windows/win32/Controls/tab-control-styles)の任意の組み合わせを適用します。 コントロールに適用できるウィンドウ スタイルの一覧については、「**解説」** を参照してください。

*Rect*<br/>
タブ コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。

*pParentWnd*<br/>
タブ コントロールの親ウィンドウを指定します`CDialog`。 NULL にすることはできません。

*nID*<br/>
タブ コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

オブジェクトの初期化が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトは`CTabCtrl`2 つの手順で作成します。 まず、コンストラクターを呼び出し、`Create`次に タブ コントロールを作成して`CTabCtrl`オブジェクトにアタッチするを呼び出します。

タブ コントロールスタイルに加えて、タブ コントロールに次のウィンドウ スタイルを適用できます。

- WS_CHILD タブ コントロールを表す子ウィンドウを作成します。 WS_POPUPスタイルでは使用できません。

- WS_VISIBLE最初に表示されるタブ コントロールを作成します。

- WS_DISABLED最初に無効になっているウィンドウを作成します。

- WS_GROUP方向キーを使用してユーザーがコントロールを移動できるコントロールのグループの最初のコントロールを指定します。 最初のコントロールの後にWS_GROUPスタイルで定義されたすべてのコントロールが同じグループに属します。 WS_GROUPスタイルの次のコントロールは、スタイル グループを終了し、次のグループ (つまり、次のグループが開始する位置で 1 つのグループが終了する) を開始します。

- WS_TABSTOP Tab キーを使用してユーザーが移動できるコントロールの任意の数のいずれかを指定します。 Tab キーは、WS_TABSTOP スタイルで指定された次のコントロールにユーザーを移動します。

拡張ウィンドウ スタイルを持つタブ コントロールを作成するには、代わりに[CTabCtrl::CreateEx](#createex)を呼び出`Create`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

## <a name="ctabctrlcreateex"></a><a name="createex"></a>CタブCtrl::作成Ex

コントロール (子ウィンドウ) を作成し、オブジェクトに関連`CTabCtrl`付けます。

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
タブ コントロールのスタイルを指定します。 Windows SDK で説明されている[タブ コントロール スタイル](/windows/win32/Controls/tab-control-styles)の任意の組み合わせを適用します。 コントロールに適用できるウィンドウ スタイルの一覧については、「[作成](#create)」の**解説**を参照してください。

*Rect*<br/>
作成するウィンドウのサイズと位置を記述する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照を *、 pParentWnd*のクライアント座標で指定します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

[`CreateEx`[作成]](#create)の代わりに、Windows 拡張スタイルの序文で指定された拡張 Windows スタイル**を適用WS_EX_。**

`CreateEx`によって指定された拡張 Windows スタイルを持つコントロール*が作成されます*。 コントロールに固有の拡張スタイルを設定するには、[次の操作を行います](#setextendedstyle)。 たとえば、WS_EX_CONTEXTHELPなどの`CreateEx`スタイルを設定するのには、TCS_EX_FLATSEPARATORSなどのスタイル`SetExtendedStyle`を設定するために使用します。 詳細については、「Windows SDK の[タブ コントロール拡張スタイル](/windows/win32/Controls/tab-control-extended-styles)」で説明されているスタイルを参照してください。

## <a name="ctabctrlctabctrl"></a><a name="ctabctrl"></a>CタブCtrl::CタブCtrl

`CTabCtrl` オブジェクトを構築します。

```
CTabCtrl();
```

## <a name="ctabctrldeleteallitems"></a><a name="deleteallitems"></a>:Dエレテアイテム

タブ コントロールからすべての項目を削除します。

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="ctabctrldeleteitem"></a><a name="deleteitem"></a>:D

タブ コントロールから指定した項目を削除します。

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
削除する項目の 0 から始まる値。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

## <a name="ctabctrldeselectall"></a><a name="deselectall"></a>すべてを選択:D

タブ コントロール内の項目をリセットし、押された項目をクリアします。

```cpp
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>パラメーター

*フォーカスを除外します。*<br/>
項目の選択解除のスコープを指定するフラグ。 このパラメータを FALSE に設定すると、すべてのタブ ボタンがリセットされます。 TRUE に設定されている場合、現在選択されているタブ項目を除くすべてのタブ項目がリセットされます。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TCM_DESELECTALL](/windows/win32/Controls/tcm-deselectall)の動作を実装します。

## <a name="ctabctrldrawitem"></a><a name="drawitem"></a>:Dローアイテム

オーナー描画タブ コントロールの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
描画する項目を記述する[DRAWITEMSTRUCT 構造体](/windows/win32/api/winuser/ns-winuser-drawitemstruct)へのポインター。

### <a name="remarks"></a>解説

構造`itemAction`のメンバーは`DRAWITEMSTRUCT`、実行される描画アクションを定義します。

既定では、このメンバー関数は何も実行しません。 オーナー描画`CTabCtrl`オブジェクトの描画を実装するには、このメンバー関数をオーバーライドします。

アプリケーションは、このメンバー関数が終了する前に *、lpDrawItemStruct*で提供される表示コンテキストに選択されているすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります。

## <a name="ctabctrlgetcurfocus"></a><a name="getcurfocus"></a>CタブCtrl::ゲットカーフォーカス

現在フォーカスのあるタブのインデックスを取得します。

```
int GetCurFocus() const;
```

### <a name="return-value"></a>戻り値

現在フォーカスのあるタブの 0 から始まるインデックス。

## <a name="ctabctrlgetcursel"></a><a name="getcursel"></a>CタブCtrl::ゲットカーセル

タブ コントロールで現在選択されているタブを取得します。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

正常終了した場合は選択したタブの 0 から始まるインデックス、またはタブが選択されていない場合は - 1。

## <a name="ctabctrlgetextendedstyle"></a><a name="getextendedstyle"></a>を使用します。

タブ コントロールで現在使用されている拡張スタイルを取得します。

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>戻り値

タブ コントロールで現在使用されている拡張スタイルを表します。 この値は、Windows SDK で説明されているように[、タブ コントロールの拡張スタイル](/windows/win32/Controls/tab-control-extended-styles)を組み合わせた値です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TCM_GETEXTENDEDSTYLE](/windows/win32/Controls/tcm-getextendedstyle)の動作を実装します。

## <a name="ctabctrlgetimagelist"></a><a name="getimagelist"></a>をクリックします。

タブ コントロールに関連付けられているイメージ リストを取得します。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

成功した場合、タブ コントロールのイメージ リストへのポインター。それ以外の場合は、NULL。

## <a name="ctabctrlgetitem"></a><a name="getitem"></a>をクリックします。

タブ コントロール内のタブに関する情報を取得します。

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
タブの 0 から始まるインデックス。

*をクリックします。*<br/>
取得する情報を指定するために使用される[TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw)構造体へのポインター。 タブに関する情報を受け取るためにも使用されます。この構造体は`InsertItem`、 、`GetItem`および メンバー`SetItem`関数で使用されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

メッセージが送信されると、`mask`メンバーは返す属性を指定します。 メンバーが`mask`TCIF_TEXT値を指定する場合、`pszText`そのメンバーには項目テキストを受け取るバッファーのアドレスが含まれ`cchTextMax`、メンバーはバッファーのサイズを指定する必要があります。

- `mask`

   取得または設定する`TCITEM`構造体メンバーを指定する値。 このメンバーは、ゼロまたは以下の値の組み合わせにすることができます。

  - TCIF_TEXT`pszText`メンバーが有効です。

  - TCIF_IMAGE`iImage`メンバーが有効です。

  - TCIF_PARAM`lParam`メンバーが有効です。

  - TCIF_RTLREADING のテキスト`pszText`は、ヘブライ語またはアラビア語のシステムで右から左への読み取り順序を使用して表示されます。

  - TCIF_STATE`dwState`メンバーが有効です。

- `pszText`

   構造にタブに関する情報が含まれている場合、タブ テキストを含む null で終わる文字列へのポインター。構造体が情報を受信している場合、このメンバーはタブ テキストを受け取るバッファーのアドレスを指定します。

- `cchTextMax`

   が`pszText`指すバッファのサイズ 。 構造体が情報を受け取っていない場合、このメンバーは無視されます。

- `iImage`タブ コントロールのイメージ リストにインデックスを付けます。

- `lParam`

   タブに関連付けられたアプリケーション定義データ。タブごとに 4 バイトを超えるアプリケーション定義データがある場合、アプリケーションは構造体を定義し、構造体の代わりにそれを`TCITEM`使用する必要があります。 アプリケーション定義構造体の最初のメンバーは[、TCITEMHEADER](/windows/win32/api/commctrl/ns-commctrl-tcitemheaderw)構造体である必要があります。 構造体`TCITEMHEADER`は`TCITEM`構造体と同じですが、メンバーは含`lParam`みないです。 構造体のサイズと構造体のサイズ`TCITEMHEADER`の違いは、タブあたりの追加バイト数と同じである必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

## <a name="ctabctrlgetitemcount"></a><a name="getitemcount"></a>を使用します。

タブ コントロール内のタブの数を取得します。

```
int GetItemCount() const;
```

### <a name="return-value"></a>戻り値

タブ コントロール内の項目の数。

### <a name="example"></a>例

  次の例[を](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)参照してください。

## <a name="ctabctrlgetitemrect"></a><a name="getitemrect"></a>をクリックします。

タブ コントロール内の指定されたタブに外接する四角形を取得します。

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
タブ項目の 0 から始まるインデックス。

*Lprect*<br/>
タブの外接する四角形を受け取る[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポインター。これらの座標は、ビューポートの現在のマッピング モードを使用します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  次の例[を](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)参照してください。

## <a name="ctabctrlgetitemstate"></a><a name="getitemstate"></a>をクリックします。

*nItem*で識別されるタブ コントロール項目の状態を取得します。

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
状態情報を取得する項目の 0 から始まるインデックス番号。

*Dwmask*<br/>
返す項目の状態フラグを指定するマスク。 値の一覧については、Windows SDK で説明されているように[、TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw)構造体のマスク メンバーを参照してください。

### <a name="return-value"></a>戻り値

状態情報を受け取る DWORD 値への参照。 次の値のいずれかです。

|値|説明|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|タブ コントロール項目が選択されます。|
|TCIS_HIGHLIGHTED|タブ コントロール項目が強調表示され、タブとテキストが現在の強調表示色で描画されます。 ハイライトカラーを使用する場合、これはディザリングカラーではなく、真の補間になります。|

### <a name="remarks"></a>解説

アイテムの状態は、`dwState``TCITEM`構造体のメンバーによって指定されます。

## <a name="ctabctrlgetrowcount"></a><a name="getrowcount"></a>を行います。

タブ コントロール内の現在の行数を取得します。

```
int GetRowCount() const;
```

### <a name="return-value"></a>戻り値

タブ コントロール内のタブの行数。

### <a name="remarks"></a>解説

TCS_MULTILINEスタイルを持つタブ コントロールのみが複数の行のタブを持つことができます。

## <a name="ctabctrlgettooltips"></a><a name="gettooltips"></a>ヒントを取得します。

タブ コントロールに関連付けられているツール ヒント コントロールのハンドルを取得します。

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>戻り値

成功した場合はツール ヒント コントロールのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

タブ コントロールは、ツール ヒント コントロールがTCS_TOOLTIPS スタイルを持つ場合に作成されます。 また、メンバー関数を使用して、ツール ヒント コントロールをタブ`SetToolTips`コントロールに割り当てることもできます。

## <a name="ctabctrlhighlightitem"></a><a name="highlightitem"></a>CタブCtrl::ハイライトアイテム

タブ項目の強調表示状態を設定します。

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>パラメーター

*idItem*<br/>
タブ コントロール項目の 0 から始まるインデックス。

*fハイライト*<br/>
設定するハイライト状態を指定する値。 この値が TRUE の場合、タブは強調表示されます。FALSE の場合、タブはデフォルトの状態に設定されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように Win32 メッセージ[TCM_HIGHLIGHTITEM](/windows/win32/Controls/tcm-highlightitem)を実装します。

## <a name="ctabctrlhittest"></a><a name="hittest"></a>ヒットテスト

指定した画面位置にタブがある場合に、そのタブを決定します。

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>パラメーター

*テスト情報*<br/>
テストする画面の位置を指定する Windows SDK で説明されているように[、TCHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-tchittestinfo)構造体へのポインター。

### <a name="return-value"></a>戻り値

タブの 0 から始まるインデックスを返します。

## <a name="ctabctrlinsertitem"></a><a name="insertitem"></a>アイテムを挿入します。

既存のタブ コントロールに新しいタブを挿入します。

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

*Nitem*<br/>
新しいタブの 0 から始まるインデックス。

*をクリックします。*<br/>
タブの属性を指定する[TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw)構造体へのポインター。

*をクリックします。*<br/>
タブのテキストを含む null で終わる文字列のアドレス。

*nイメージ*<br/>
イメージ リストから挿入するイメージの 0 から始まるインデックス。

*nマスク*<br/>
設定する`TCITEM`構造体属性を指定します。 0 または次の値の組み合わせを指定できます。

- TCIF_TEXT`pszText`メンバーが有効です。

- TCIF_IMAGE`iImage`メンバーが有効です。

- TCIF_PARAM *lParam*メンバーが有効です。

- TCIF_RTLREADING のテキスト`pszText`は、ヘブライ語またはアラビア語のシステムで右から左への読み取り順序を使用して表示されます。

- TCIF_STATE *dwState*メンバーが有効です。

*lParam*<br/>
タブに関連付けられたアプリケーション定義データ。

*dwステート*<br/>
項目の状態の値を指定します。 詳細については、Windows SDK[の TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw)を参照してください。

*ドウステートマスク*<br/>
設定する状態を指定します。 詳細については、Windows SDK[の TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw)を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は、新しいタブの 0 から始まるインデックス。それ以外の場合 - 1。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

## <a name="ctabctrlremoveimage"></a><a name="removeimage"></a>イメージの削除

タブ コントロールのイメージ リストから指定したイメージを削除します。

```cpp
void RemoveImage(int nImage);
```

### <a name="parameters"></a>パラメーター

*nイメージ*<br/>
削除するイメージの 0 から始まるインデックス。

### <a name="remarks"></a>解説

タブ コントロールは、各タブのイメージ インデックスを更新して、各タブが同じイメージに関連付けられたままになるようにします。

## <a name="ctabctrlsetcurfocus"></a><a name="setcurfocus"></a>CタブCtrl::セットカーフォーカス

タブ コントロール内の指定されたタブにフォーカスを設定します。

```cpp
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
フォーカスを取得するタブのインデックスを指定します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TCM_SETCURFOCUS](/windows/win32/Controls/tcm-setcurfocus)の動作を実装します。

## <a name="ctabctrlsetcursel"></a><a name="setcursel"></a>CタブCtrl::セットカーセル

タブ コントロール内のタブを選択します。

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
選択する項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

正常終了した場合は、以前に選択したタブの 0 から始まるインデックスを指定します。

### <a name="remarks"></a>解説

タブ コントロールは、この関数を使用してタブが選択されている場合、TCN_SELCHANGINGまたはTCN_SELCHANGE通知メッセージを送信しません。 これらの通知は、ユーザーがキーボードをクリックするか、キーボードを使用してタブを変更したときに、WM_NOTIFYを使用して送信されます。

## <a name="ctabctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CタブCtrl::セットエクステンドスタイル

タブ コントロールの拡張スタイルを設定します。

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>パラメーター

*ドウニュースタイル*<br/>
タブ コントロールの拡張スタイルの組み合わせを指定する値。

*ドウエックスマスク*<br/>
*dwNewStyle*のどのスタイルが影響を受けるかを示す DWORD 値。 *dwExMask*の拡張スタイルのみが変更されます。 他のすべてのスタイルはそのまま維持されます。 このパラメータが 0 の場合 *、dwNewStyle*のすべてのスタイルが影響を受けます。

### <a name="return-value"></a>戻り値

Windows SDK で説明したように、以前の[タブ コントロール拡張スタイル](/windows/win32/Controls/tab-control-extended-styles)を含む DWORD 値。

### <a name="return-value"></a>戻り値

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TCM_SETEXTENDEDSTYLE](/windows/win32/Controls/tcm-setextendedstyle)の動作を実装します。

## <a name="ctabctrlsetimagelist"></a><a name="setimagelist"></a>を使用します。

タブ コントロールにイメージ リストを割り当てます。

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
タブ コントロールに割り当てるイメージ リストへのポインター。

### <a name="return-value"></a>戻り値

前のイメージ リストへのポインターを返します。

## <a name="ctabctrlsetitem"></a><a name="setitem"></a>を設定します。

タブの属性の一部またはすべてを設定します。

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
項目の 0 から始まるインデックス。

*をクリックします。*<br/>
新しい項目属性を含む[TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw)構造体へのポインター。 メンバー`mask`は、設定する属性を指定します。 メンバーが`mask`TCIF_TEXT値を指定する`pszText`場合、メンバーは null で終わる文字列のアドレスであり、`cchTextMax`メンバーは無視されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [GetItem](#getitem)の例を参照してください。

## <a name="ctabctrlsetitemextra"></a><a name="setitemextra"></a>CタブCtrl::セットアイテムエクストラ

タブ コントロール内のアプリケーション定義データ用に予約されているタブあたりのバイト数を設定します。

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>パラメーター

*Nbytes*<br/>
設定する追加バイト数。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TCM_SETITEMEXTRA](/windows/win32/Controls/tcm-setitemextra)の動作を実装します。

## <a name="ctabctrlsetitemsize"></a><a name="setitemsize"></a>を切り離します。

タブ コントロール項目の幅と高さを設定します。

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
タブ コントロール項目の新しい幅と高さ (ピクセル単位)。

### <a name="return-value"></a>戻り値

タブ コントロール項目の古い幅と高さを返します。

## <a name="ctabctrlsetitemstate"></a><a name="setitemstate"></a>をクリックします。

*nItem*で識別されるタブ コントロール項目の状態を設定します。

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
状態情報を設定する項目の 0 から始まるインデックス番号。

*Dwmask*<br/>
設定する項目の状態フラグを指定するマスク。 値の一覧については、Windows SDK で説明されているように[、TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw)構造体のマスク メンバーを参照してください。

*dwステート*<br/>
状態情報を含む DWORD 値への参照。 次の値のいずれかです。

|値|説明|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|タブ コントロール項目が選択されます。|
|TCIS_HIGHLIGHTED|タブ コントロール項目が強調表示され、タブとテキストが現在の強調表示色で描画されます。 ハイライトカラーを使用する場合、これはディザリングカラーではなく、真の補間になります。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="ctabctrlsetmintabwidth"></a><a name="setmintabwidth"></a>タブCtrl::セットミンタブ幅

タブ コントロール内の項目の最小幅を設定します。

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>パラメーター

*Cx*<br/>
タブ コントロール項目に設定する最小幅。 このパラメーターを -1 に設定すると、コントロールは既定のタブ幅を使用します。

### <a name="return-value"></a>戻り値

直前の最小タブ幅。

### <a name="return-value"></a>戻り値

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TCM_SETMINTABWIDTH](/windows/win32/Controls/tcm-setmintabwidth)の動作を実装します。

## <a name="ctabctrlsetpadding"></a><a name="setpadding"></a>を切り替えます。

タブ コントロール内の各タブのアイコンとラベルの周囲のスペース (パディング) の量を設定します。

```cpp
void SetPadding(CSize size);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
タブ コントロール内の各タブのアイコンとラベルの周囲のスペース (パディング) の量を設定します。

## <a name="ctabctrlsettooltips"></a><a name="settooltips"></a>CタブCtrl::セットヒント

ツール ヒント コントロールをタブ コントロールに割り当てます。

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>パラメーター

*プーンドチップ*<br/>
ツール ヒント コントロールのハンドル。

### <a name="remarks"></a>解説

タブ コントロールに関連付けられたツール ヒント コントロールを取得するには、`GetToolTips`を呼び出します。

### <a name="example"></a>例

  次の例[を](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)参照してください。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cheaderctrl-class.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)
