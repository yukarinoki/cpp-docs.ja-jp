---
title: CListBox クラス
ms.date: 11/04/2016
f1_keywords:
- CListBox
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
helpviewer_keywords:
- CListBox [MFC], CListBox
- CListBox [MFC], AddString
- CListBox [MFC], CharToItem
- CListBox [MFC], CompareItem
- CListBox [MFC], Create
- CListBox [MFC], DeleteItem
- CListBox [MFC], DeleteString
- CListBox [MFC], Dir
- CListBox [MFC], DrawItem
- CListBox [MFC], FindString
- CListBox [MFC], FindStringExact
- CListBox [MFC], GetAnchorIndex
- CListBox [MFC], GetCaretIndex
- CListBox [MFC], GetCount
- CListBox [MFC], GetCurSel
- CListBox [MFC], GetHorizontalExtent
- CListBox [MFC], GetItemData
- CListBox [MFC], GetItemDataPtr
- CListBox [MFC], GetItemHeight
- CListBox [MFC], GetItemRect
- CListBox [MFC], GetListBoxInfo
- CListBox [MFC], GetLocale
- CListBox [MFC], GetSel
- CListBox [MFC], GetSelCount
- CListBox [MFC], GetSelItems
- CListBox [MFC], GetText
- CListBox [MFC], GetTextLen
- CListBox [MFC], GetTopIndex
- CListBox [MFC], InitStorage
- CListBox [MFC], InsertString
- CListBox [MFC], ItemFromPoint
- CListBox [MFC], MeasureItem
- CListBox [MFC], ResetContent
- CListBox [MFC], SelectString
- CListBox [MFC], SelItemRange
- CListBox [MFC], SetAnchorIndex
- CListBox [MFC], SetCaretIndex
- CListBox [MFC], SetColumnWidth
- CListBox [MFC], SetCurSel
- CListBox [MFC], SetHorizontalExtent
- CListBox [MFC], SetItemData
- CListBox [MFC], SetItemDataPtr
- CListBox [MFC], SetItemHeight
- CListBox [MFC], SetLocale
- CListBox [MFC], SetSel
- CListBox [MFC], SetTabStops
- CListBox [MFC], SetTopIndex
- CListBox [MFC], VKeyToItem
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
ms.openlocfilehash: 17ff89fde3ef893c2cfcd8beeb8482722af60358
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280317"
---
# <a name="clistbox-class"></a>CListBox クラス

Windows のリスト ボックスの機能を提供します。

## <a name="syntax"></a>構文

```
class CListBox : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CListBox::CListBox](#clistbox)|`CListBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CListBox::AddString](#addstring)|リスト ボックスに文字列を追加します。|
|[CListBox::CharToItem](#chartoitem)|カスタムの WM_CHAR 文字列を持たないオーナー描画リスト ボックスの処理を提供するオーバーライドです。|
|[CListBox::CompareItem](#compareitem)|並べ替えられたオーナー描画リスト ボックスに新しい項目の位置を決定するためにフレームワークによって呼び出されます。|
|[CListBox::Create](#create)|Windows のリスト ボックスを作成しにアタッチします、`CListBox`オブジェクト。|
|[CListBox::DeleteItem](#deleteitem)|ユーザーが、オーナー描画リスト ボックスから項目を削除するときに、フレームワークによって呼び出されます。|
|[CListBox::DeleteString](#deletestring)|リスト ボックスから文字列を削除します。|
|[CListBox::Dir](#dir)|リスト ボックスに、ファイル名、ドライブ、またはその両方、現在のディレクトリからを追加します。|
|[CListBox::DrawItem](#drawitem)|ビジュアルな部分のオーナー描画リスト ボックスが変更されたときにフレームワークによって呼び出されます。|
|[CListBox::FindString](#findstring)|リスト ボックス内の文字列を検索します。|
|[CListBox::FindStringExact](#findstringexact)|指定した文字列と一致する最初のボックスの一覧で文字列を検索します。|
|[CListBox::GetAnchorIndex](#getanchorindex)|リスト ボックスの現在のアンカー項目の 0 から始まるインデックスを取得します。|
|[CListBox::GetCaretIndex](#getcaretindex)|複数選択のリスト ボックスにフォーカス四角形を持つ項目のインデックスを調べます。|
|[CListBox::GetCount](#getcount)|リスト ボックスで、文字列の数を返します。|
|[CListBox::GetCurSel](#getcursel)|リスト ボックスで現在選択されている文字列の 0 から始まるインデックスを返します。|
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|リスト ボックスが水平方向にスクロールできることをピクセル単位の幅を返します。|
|[CListBox::GetItemData](#getitemdata)|リスト ボックス項目に関連付けられている 32 ビット値を返します。|
|[CListBox::GetItemDataPtr](#getitemdataptr)|リスト ボックス項目へのポインターを返します。|
|[CListBox::GetItemHeight](#getitemheight)|リスト ボックス内の項目の高さを決定します。|
|[CListBox::GetItemRect](#getitemrect)|現在表示されている、リスト ボックス項目の外接する四角形を返します。|
|[CListBox::GetListBoxInfo](#getlistboxinfo)|列あたりの項目の数を取得します。|
|[CListBox::GetLocale](#getlocale)|リスト ボックスのロケール識別子を取得します。|
|[CListBox::GetSel](#getsel)|リスト ボックス項目の選択状態を返します。|
|[CListBox::GetSelCount](#getselcount)|複数選択のリスト ボックスで現在選択されている文字列の数を返します。|
|[CListBox::GetSelItems](#getselitems)|リスト ボックスで現在選択されている文字列のインデックスを返します。|
|[CListBox::GetText](#gettext)|リスト ボックス項目をバッファーにコピーします。|
|[CListBox::GetTextLen](#gettextlen)|リスト ボックス項目のバイト単位の長さを返します。|
|[CListBox::GetTopIndex](#gettopindex)|リスト ボックスに表示される文字列の最初のインデックスを返します。|
|[CListBox::InitStorage](#initstorage)|リスト ボックス項目および文字列用のメモリ ブロックは事前に割り当てます。|
|[CListBox::InsertString](#insertstring)|リスト ボックス内の特定位置に文字列を挿入します。|
|[CListBox::ItemFromPoint](#itemfrompoint)|ポイントに最も近いリスト ボックス項目のインデックスを返します。|
|[CListBox::MeasureItem](#measureitem)|リスト ボックスのサイズを決定する、オーナー描画リスト ボックスが作成されるときに、フレームワークによって呼び出されます。|
|[CListBox::ResetContent](#resetcontent)|リスト ボックスからすべてのエントリをクリアします。|
|[CListBox::SelectString](#selectstring)|検索し、単一選択のリスト ボックスで文字列を選択します。|
|[CListBox::SelItemRange](#selitemrange)|選択または複数選択のリスト ボックス内の文字列の範囲の選択を解除します。|
|[CListBox::SetAnchorIndex](#setanchorindex)|拡張選択を開始する複数選択のリスト ボックスで、アンカーを設定します。|
|[CListBox::SetCaretIndex](#setcaretindex)|複数選択のリスト ボックスで、指定したインデックス位置にある項目にフォーカス四角形を設定します。|
|[CListBox::SetColumnWidth](#setcolumnwidth)|複数列のリスト ボックスの列の幅を設定します。|
|[CListBox::SetCurSel](#setcursel)|リスト ボックスの文字列を選択します。|
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|リスト ボックスが水平方向にスクロールできることをピクセル単位の幅を設定します。|
|[CListBox::SetItemData](#setitemdata)|リスト ボックス項目に関連付けられている 32 ビット値を設定します。|
|[CListBox::SetItemDataPtr](#setitemdataptr)|リスト ボックス項目へのポインターを設定します。|
|[CListBox::SetItemHeight](#setitemheight)|リスト ボックス内の項目の高さを設定します。|
|[CListBox::SetLocale](#setlocale)|リスト ボックスのロケール識別子を設定します。|
|[CListBox::SetSel](#setsel)|選択または複数選択のリスト ボックスで、リスト ボックス項目の選択を解除します。|
|[CListBox::SetTabStops](#settabstops)|リスト ボックスのタブ ストップの位置を設定します。|
|[CListBox::SetTopIndex](#settopindex)|リスト ボックスに表示される文字列の最初の 0 から始まるインデックスを設定します。|
|[CListBox::VKeyToItem](#vkeytoitem)|オーバーライドすると、カスタムの WM_KEYDOWN LBS_WANTKEYBOARDINPUT スタイル設定された、リスト ボックスの処理を提供します。|

## <a name="remarks"></a>Remarks

リスト ボックスには、ユーザーが表示および選択するとファイル名などの項目の一覧が表示されます。

単一選択のリスト ボックスでは、ユーザーは、1 つだけの項目を選択できます。 複数選択のリスト ボックスでは、項目の範囲を選択できます。 ユーザーは、項目を選択してが強調表示されて、リスト ボックスを親ウィンドウに通知メッセージを送信します。

リスト ボックスは、ダイアログ テンプレートから、またはコードで直接作成できます。 直接作成するには、構築、`CListBox`オブジェクトを呼び出して、[作成](#create)Windows リスト ボックス コントロールを作成し、アタッチ先のメンバー関数、`CListBox`オブジェクト。 ダイアログ テンプレートでリスト ボックスを使用するには、ダイアログ ボックス クラスでボックスの一覧で変数を宣言し、使用して、、 `DDX_Control`  ダイアログ ボックス クラスで`DoDataExchange`コントロールにメンバー変数を接続する関数。 (これが自動的にダイアログ ボックス クラスをコントロール変数を追加するとします。)

派生したクラスの 1 ステップのプロセスは、構築`CListBox`します。 呼び出しと派生クラスのコンス トラクターを記述`Create`からコンス トラクター内。

リスト ボックスからその親に送信される Windows 通知メッセージを処理する場合 (通常はから派生したクラス[CDialog](../../mfc/reference/cdialog-class.md))、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。

各メッセージ マップ エントリは、次の形式をとります。

`ON_Notification( id, memberFxn )`

場所`id`通知を送信するリスト ボックス コントロールの子ウィンドウ ID を指定および`memberFxn`通知を処理するために記述した親メンバー関数の名前を指定します。

親の関数のプロトタイプは次のとおりです。

`afx_msg void memberFxn( );`

次は、潜在的なメッセージ マップ エントリと親に送信するケースの説明の一覧に示します。

- ON_LBN_DBLCLK、ユーザーは、リスト ボックス内の文字列をダブルクリックします。 のみがリスト ボックス、 [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルでは、この通知メッセージを送信します。

- ON_LBN_ERRSPACE リスト ボックスには、要求を満たすために十分なメモリを割り当てることができません。

- ON_LBN_KILLFOCUS リスト ボックスには、入力フォーカスが失われています。

- ON_LBN_SELCANCEL リスト ボックスの現在の選択が取り消されました。 リスト ボックスに LBS_NOTIFY スタイルがある場合は、このメッセージは送信のみ。

- ON_LBN_SELCHANGE リスト ボックス内の選択が変更されました。 選択が変更された場合、この通知は送信されませんが、 [CListBox::SetCurSel](#setcursel)メンバー関数。 この通知は、LBS_NOTIFY スタイルがリスト ボックスにのみ適用されます。 LBN_SELCHANGE 通知メッセージが送信複数選択のリスト ボックスの方向キーを押すたびに、選択が変更されない場合でもです。

- ON_LBN_SETFOCUS リスト ボックスが入力フォーカスを受信します。

- ON_WM_CHARTOITEM 文字列がオーナー描画リスト ボックスでは、WM_CHAR メッセージを受信しません。

- LBS_WANTKEYBOARDINPUT スタイル ON_WM_VKEYTOITEM するリスト ボックスでは、WM_KEYDOWN メッセージを受信します。

作成する場合、 `CListBox` (ダイアログ リソースの場合) を使ってダイアログ ボックス内のオブジェクト、 `CListBox`  ダイアログ ボックスを閉じると、オブジェクトが自動的に破棄されます。

作成する場合、`CListBox`オブジェクトを破棄する必要があります、ウィンドウ内で、`CListBox`オブジェクト。 作成する場合、`CListBox`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CListBox`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を親ウィンドウを閉じると破棄するオブジェクト。

メモリを割り当てることがある場合、`CListBox`オブジェクト、オーバーライド、`CListBox`割り当てを破棄するデストラクター。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="addstring"></a>  CListBox::AddString

リスト ボックスに文字列を追加します。

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>パラメーター

*lpszItem*<br/>
追加するのには null で終わる文字列へのポインター。

### <a name="return-value"></a>戻り値

リスト ボックス内の文字列の 0 から始まるインデックス。 エラーが発生した場合、戻り値は返します新しい文字列を格納する十分な空き領域がある場合は、返しますを返します。

### <a name="remarks"></a>Remarks

リスト ボックスが作成されていない場合、 [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル、文字列はリストの末尾に追加されます。 それ以外の場合、一覧に、文字列が挿入され、リストの並べ替え。 LBS_SORT スタイルを使用して、リスト ボックスが作成されたかどうかはなく、 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル、フレームワークで、1 つまたは複数の呼び出しで、一覧が並べ替えられます、`CompareItem`メンバー関数。

使用[InsertString](#insertstring)リスト ボックス内の指定位置に文字列を挿入します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

##  <a name="chartoitem"></a>  CListBox::CharToItem

リスト ボックスの親ウィンドウは、リスト ボックスから WM_CHARTOITEM メッセージを受信すると、フレームワークによって呼び出されます。

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>パラメーター

*nKey*<br/>
ユーザーが入力した文字の ANSI コード。

*nIndex*<br/>
リスト ボックスのキャレットの現在の位置。

### <a name="return-value"></a>戻り値

1 または 2 操作はこれ以上またはキーストロークの既定のアクションを実行するリスト ボックス項目のインデックスを指定する正の数値を返します。 既定の実装 - 1 を返します。

### <a name="remarks"></a>Remarks

WM_CHAR メッセージを受信すると、リスト ボックスには、これらの条件をすべて満たしている場合にのみ、リスト ボックスにより WM_CHARTOITEM メッセージが送信されます。

- オーナー描画リスト ボックスです。

- [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)一連のスタイルを設定します。

- 少なくとも 1 つの項目があります。

自分でがこの関数を呼び出す必要がありますはことはありません。 キーボード メッセージの独自のカスタム処理を提供するには、この関数をオーバーライドします。

オーバーライドでは、実行するアクションをフレームワークに指示する値を返す必要があります。 戻り値の項目を選択してすべての側面を処理して、リスト ボックスでさらに操作は必要ありませんを 1 または 2 示します。 -を返す前に 1 - 2、する可能性があります選択範囲を設定またはカレットを移動します。 選択範囲を設定する[SetCurSel](#setcursel)または[SetSel](#setsel)します。 カレットを移動するには使用[には](#setcaretindex)します。

0 以上の戻り値は、リスト ボックスで、項目のインデックスを指定し、リスト ボックスがで指定したアイテムのキーストロークの既定のアクションを実行する必要がありますを示します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

##  <a name="clistbox"></a>  CListBox::CListBox

`CListBox` オブジェクトを構築します。

```
CListBox();
```

### <a name="remarks"></a>Remarks

構築する、 `CListBox` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出す`ClistBox`を呼び出して`Create`、Windows のリスト ボックスを初期化しにアタッチする`CListBox`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

##  <a name="compareitem"></a>  CListBox::CompareItem

並べ替えられたオーナー描画リスト ボックスに新しい項目の相対位置を決定するためにフレームワークによって呼び出されます。

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpCompareItemStruct*<br/>
Long ポインター、`COMPAREITEMSTRUCT`構造体。

### <a name="return-value"></a>戻り値

説明されている 2 つの項目の相対位置を示す、 [COMPAREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcompareitemstruct)構造体。 次の値のいずれかがある可能性があります。

|[値]|説明|
|-----------|-------------|
|-1|項目 1 は、項目 2 の前に並べ替えます。|
|0|アイテム 1 とアイテム 2 は、同じを並べ替えます。|
|1|項目 1 は、項目 2 の後に並べ替えられます。|

参照してください[CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)の説明については、`COMPAREITEMSTRUCT`構造体。

### <a name="remarks"></a>Remarks

既定では、このメンバー関数は何もしません。 LBS_SORT スタイルとオーナー描画のリスト ボックスを作成する場合は、リスト ボックスに追加された新しい項目の並べ替えでフレームワークを支援するためにこのメンバー関数をオーバーライドする必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

##  <a name="create"></a>  CListBox::Create

Windows のリスト ボックスを作成しにアタッチします、`CListBox`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
リスト ボックスのスタイルを指定します。 任意の組み合わせを適用[リスト ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)します。

*rect*<br/>
リスト ボックスのサイズと位置を指定します。 いずれかになります、`CRect`オブジェクトまたは`RECT`構造体。

*pParentWnd*<br/>
リスト ボックスの親ウィンドウを指定します (通常、`CDialog`オブジェクト)。 NULL は指定できません。

*nID*<br/>
リスト ボックスのコントロール ID を指定します

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

構築する、 `CListBox` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出して`Create`、Windows リスト ボックスを初期化しにアタッチする`CListBox`オブジェクト。

ときに`Create`実行されると、Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メッセージをリスト ボックス コントロール。

既定でこれらのメッセージが処理されます、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数`CWnd`基本クラス。 既定のメッセージ処理を拡張するには、派生クラスを`CListBox`メッセージ マップを新しいクラスに追加し、前のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`、たとえば、新しいクラスに必要な初期化を実行します。

次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)リスト ボックス コントロールにします。

- WS_CHILD 常に

- WS_VISIBLE 通常

- WS_DISABLED ことはほとんどありません。

- WS_VSCROLL に垂直スクロール バーを追加します。

- WS_HSCROLL に水平スクロール バーを追加します。

- WS_GROUP コントロールをグループ化

- WS_TABSTOP にこのコントロールにタブ移動を許可します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

##  <a name="deleteitem"></a>  CListBox::DeleteItem

ユーザーがオーナー描画から項目を削除するときに、フレームワークによって呼び出されます`CListBox`オブジェクトまたはリスト ボックスを破棄します。

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDeleteItemStruct*<br/>
Windows への long ポインター [DELETEITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdeleteitemstruct)削除された項目に関する情報を含む構造体。

### <a name="remarks"></a>Remarks

この関数の既定の実装は、何も行いません。 必要に応じて、オーナー描画リスト ボックスを再描画するには、この関数をオーバーライドします。

参照してください[構造体](../../mfc/reference/cwnd-class.md#ondeleteitem)の説明については、`DELETEITEMSTRUCT`構造体。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

##  <a name="deletestring"></a>  CListBox::DeleteString

位置に項目を削除します*nIndex*リスト ボックスから。

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する文字列の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

一覧に残っている文字列の数。 場合、戻り値は返します*nIndex*一覧の項目の数より大きいインデックスを指定します。

### <a name="remarks"></a>Remarks

次のすべての項目*nIndex*現在位置を 1 つ下へ移動します。 たとえば、リスト ボックスに 2 つの項目が含まれている場合の最初の項目を削除するによりを今すぐ最初の位置で残りの項目。 *nIndex*の最初の位置の項目の 0 を = です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

##  <a name="dir"></a>  CListBox::Dir

ファイル名、ドライブ、またはその両方をリスト ボックスの一覧を追加します。

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>パラメーター

*attr*<br/>
任意の組み合わせにすることができます、 **enum**で説明されている値`CFile::GetStatu` [s](../../mfc/reference/cfile-class.md#getstatus)、または、次の値の任意の組み合わせ。

|[値]|説明|
|-----------|-------------|
|0x0000|ファイルから読み取りまたは書き込みをすることができます。|
|0x0001|ファイルを読み取ったりできますには書き込まれません。|
|0x0002|ファイルが非表示し、ディレクトリの一覧に表示されません。|
|0x0004|ファイルは、システム ファイルです。|
|0x0010|指定された名前*lpszWildCard*ディレクトリを指定します。|
|0x0020|ファイルがアーカイブされました。|
|0x4000|指定された名前と一致するすべてのドライブを含める*lpszWildCard*します。|
|0x8000|排他フラグ。 排他のフラグを設定すると、指定した種類のファイルのみが一覧表示されます。 それ以外の場合、「通常」のファイルだけでなく、指定した型のファイルが一覧表示されます。|

*lpszWildCard*<br/>
ファイルの仕様の文字列を指します。 文字列にワイルドカードを含めることができます (たとえば、*.\*)。

### <a name="return-value"></a>戻り値

最後に、リストに追加されたファイル名の 0 から始まるインデックス。 エラーが発生した場合、戻り値は返します新しい文字列を保存する十分な空き領域がある場合は、返しますを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

##  <a name="drawitem"></a>  CListBox::DrawItem

ビジュアルな部分のオーナー描画リスト ボックスが変更されたときにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
Long ポインター、 [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)のために必要な図面の種類に関する情報を含む構造体。

### <a name="remarks"></a>Remarks

`itemAction`と`itemState`のメンバー、`DRAWITEMSTRUCT`構造を実行する描画の動作を定義します。

既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CListBox`オブジェクト。 アプリケーションで提供されるディスプレイ コンテキスト用に選択したすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*このメンバーの前に、関数が終了します。

参照してください[体](../../mfc/reference/cwnd-class.md#ondrawitem)の説明については、`DRAWITEMSTRUCT`構造体。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

##  <a name="findstring"></a>  CListBox::FindString

ボックスの一覧で選択を変更することがなく、指定したプレフィックスを含むリスト ボックス内の最初の文字列を検索します。

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>パラメーター

*nStartAfter*<br/>
最初の項目を検索する前にある項目の 0 から始まるインデックスが含まれています。 指定された項目に、リスト ボックスの上部から続行、検索では、リスト ボックスの下部に達すると、 *nStartAfter*します。 場合*nStartAfter* -1 で、最初からリスト ボックス全体が検索されます。

*lpszItem*<br/>
検索対象のプレフィックスを含む null で終わる文字列へのポインター。 検索では独立しており、ケースを指定するため、この文字列は、任意の大文字と小文字を含めることができます。

### <a name="return-value"></a>戻り値

返しますが、検索が成功した場合、一致する項目の 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

使用して、 [SelectString](#selectstring)メンバー関数を検索して、文字列を選択します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

##  <a name="findstringexact"></a>  CListBox::FindStringExact

指定された文字列と一致する最初のボックスの一覧で文字列を検索*されて*します。

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>パラメーター

*nIndexStart*<br/>
最初の項目を検索する前にある項目の 0 から始まるインデックスを指定します。 指定された項目に、リスト ボックスの上部から続行、検索では、リスト ボックスの下部に達すると、 *nIndexStart*します。 場合*nIndexStart* -1 で、最初からリスト ボックス全体が検索されます。

*lpszFind*<br/>
検索する null で終わる文字列へのポインター。 この文字列は、拡張子を含む、完全なファイル名を含めることができます。 検索は大文字小文字が区別はないため、文字列は、任意の大文字と小文字を含めることができます。

### <a name="return-value"></a>戻り値

返します、検索が成功した場合、一致する項目のインデックス。

### <a name="remarks"></a>Remarks

リスト ボックスがオーナー描画スタイルで作成された場合、 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 、スタイル、`FindStringExact`メンバー関数の値に対してダブルワード値を照合しようとしています。*されている*します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

##  <a name="getanchorindex"></a>  CListBox::GetAnchorIndex

リスト ボックスで、現在のアンカー項目の 0 から始まるインデックスを取得します。

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>戻り値

成功した場合は現在のアンカー項目のインデックスそれ以外の場合返します。

### <a name="remarks"></a>Remarks

複数選択のリスト ボックスでは、アンカー項目は、選択した項目を連続するブロックの最初または最後の項目が。

### <a name="example"></a>例

  例をご覧ください[CListBox::SetAnchorIndex](#setanchorindex)します。

##  <a name="getcaretindex"></a>  CListBox::GetCaretIndex

複数選択のリスト ボックスにフォーカス四角形を持つ項目のインデックスを調べます。

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>戻り値

リスト ボックスにフォーカス四角形をされている項目の 0 から始まるインデックス。 リスト ボックスは、単一選択のリスト ボックスは、戻り値が存在する場合、選択されている項目のインデックスの対象にします。

### <a name="remarks"></a>Remarks

項目は、選択されていない可能性があります。

### <a name="example"></a>例

  例をご覧ください[CListBox::SetCaretIndex](#setcaretindex)します。

##  <a name="getcount"></a>  CListBox::GetCount

リスト ボックス内の項目の数を取得します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス、またはエラーが発生した場合に返します内の項目の数。

### <a name="remarks"></a>Remarks

返されるカウントは、1 (インデックスは 0 から始まる) の最後の項目のインデックス値よりも大きいです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

##  <a name="getcursel"></a>  CListBox::GetCurSel

単一選択のリスト ボックスで、存在する場合は、現在選択されている項目の 0 から始まるインデックスを取得します。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

単一選択のリスト ボックスの場合は、現在選択されている項目の 0 から始まるインデックス。 項目が現在選択されていない場合は、返しますです。

複数選択のリスト ボックスでは、フォーカスがある項目のインデックス。

### <a name="remarks"></a>Remarks

呼び出さない`GetCurSel`複数選択のリスト ボックス。 使用[CListBox::GetSelItems](#getselitems)代わりにします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

##  <a name="gethorizontalextent"></a>  CListBox::GetHorizontalExtent

リスト ボックスから、使用されるスクロール可能水平方向にピクセル単位の幅を取得します。

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>戻り値

スクロール可能な幅 (ピクセル単位)、リスト ボックスの。

### <a name="remarks"></a>Remarks

これは、リスト ボックスに水平スクロール バーがある場合にのみ当てはまります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

##  <a name="getitemdata"></a>  CListBox::GetItemData

指定したリスト ボックス項目に関連付けられたアプリケーションによって提供されるダブルワード値を取得します。

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックスで、項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

32 ビット値は、エラーが発生した場合に関連付けられた項目、または返します。

### <a name="remarks"></a>Remarks

ダブルワード値は、 *dwItemData*のパラメーターを[SetItemData](#setitemdata)呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

##  <a name="getitemdataptr"></a>  CListBox::GetItemDataPtr

ポインターとして指定されたリスト ボックス項目に関連付けられたアプリケーションによって提供される 32 ビット値を取得します (**void** <strong>\*</strong>)。

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックスで、項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

エラーが発生した場合は、ポインター、または-1 を取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

##  <a name="getitemheight"></a>  CListBox::GetItemHeight

リスト ボックス内の項目の高さを決定します。

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックスで、項目の 0 から始まるインデックスを指定します。 このパラメーターは、リスト ボックスに LBS_OWNERDRAWVARIABLE スタイル; がある場合にのみ使用します。それ以外の場合、0 に設定する必要があります。

### <a name="return-value"></a>戻り値

リスト ボックス内の項目 (ピクセル) の高さ。 リスト ボックスがある場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル、戻り値がで指定された項目の高さ*nIndex*します。 エラーが発生する場合は、返しますを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

##  <a name="getitemrect"></a>  CListBox::GetItemRect

ボックスの一覧 ウィンドウで現在表示されて、その境界ボックスの一覧の項目の四角形の寸法を取得します。

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の 0 から始まるインデックスを指定します。

*lpRect*<br/>
Long ポインターを指定します、 [RECT 構造体](/windows/desktop/api/windef/ns-windef-tagrect)項目のリスト ボックスのクライアント座標を受け取る。

### <a name="return-value"></a>戻り値

エラーが発生した場合を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

##  <a name="getlistboxinfo"></a>  CListBox::GetListBoxInfo

列あたりの項目の数を取得します。

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>戻り値

各列の項目の数、`CListBox`オブジェクト。

### <a name="remarks"></a>Remarks

このメンバー関数の機能をエミュレートする、 [LB_GETLISTBOXINFO](/windows/desktop/Controls/lb-getlistboxinfo)メッセージ、Windows SDK で説明されているとします。

##  <a name="getlocale"></a>  CListBox::GetLocale

リスト ボックスによって使用されるロケールを取得します。

```
LCID GetLocale() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内の文字列のロケール識別子 (LCID) 値。

### <a name="remarks"></a>Remarks

ロケールが使用、たとえば、並べ替えられたリスト ボックス内の文字列の並べ替え順序を決定します。

### <a name="example"></a>例

  例をご覧ください[CListBox::SetLocale](#setlocale)します。

##  <a name="getsel"></a>  CListBox::GetSel

項目の選択状態を取得します。

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

指定した項目がオンの場合は正の数それ以外の場合は 0 です。 エラーが発生した場合は、返しますを返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、両方の単一と複数選択リスト ボックスで動作します。

現在選択されているリスト ボックスの項目のインデックスを取得する[CListBox::GetCurSel](#getcursel)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

##  <a name="getselcount"></a>  CListBox::GetSelCount

複数選択のリスト ボックスで選択したアイテムの合計数を取得します。

```
int GetSelCount() const;
```

### <a name="return-value"></a>戻り値

リスト ボックスで選択したアイテムの数。 リスト ボックスに、単一選択のリスト ボックスがある場合は、返しますを返します。

### <a name="example"></a>例

  例をご覧ください[CListBox::GetSelItems](#getselitems)します。

##  <a name="getselitems"></a>  CListBox::GetSelItems

複数選択のリスト ボックスで選択した項目の項目番号を指定する整数の配列をバッファーします。

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>パラメーター

*nMaxItems*<br/>
項目番号は、バッファーに配置するのには、選択した項目の最大数を指定します。

*rgIndex*<br/>
指定された整数の数に対して十分な大きさのバッファーへのポインターを指定します*nMaxItems*します。

### <a name="return-value"></a>戻り値

項目の実際の数は、バッファーに格納します。 戻り値は、リスト ボックスが、単一選択のリスト ボックスの場合は、`LB_ERR`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

##  <a name="gettext"></a>  CListBox::GetText

リスト ボックスから文字列を取得します。

```
int GetText(
    int nIndex,
    LPTSTR lpszBuffer) const;

void GetText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得する文字列の 0 から始まるインデックスを指定します。

*lpszBuffer*<br/>
文字列を受け取るバッファーへのポインター。 バッファーには、文字列と終端の null 文字に対して十分な領域が必要です。 文字列のサイズは、呼び出すことによって事前に決定できます、`GetTextLen`メンバー関数。

*rString*<br/>
`CString` オブジェクトへの参照。

### <a name="return-value"></a>戻り値

終端の null 文字を除く、文字列の長さをバイト単位で。 場合*nIndex*有効なインデックスで指定されていない戻り値は、返します。

### <a name="remarks"></a>Remarks

このメンバーの 2 番目の形式の関数の塗りつぶしを`CString`文字列テキストを含むオブジェクト。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

##  <a name="gettextlen"></a>  CListBox::GetTextLen

リスト ボックス項目では、文字列の長さを取得します。

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
文字列の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

文字列の終端の null 文字を除いた文字の長さ。 場合*nIndex*有効なインデックスで指定されていない戻り値は、返します。

### <a name="example"></a>例

  例をご覧ください[CListBox::GetText](#gettext)します。

##  <a name="gettopindex"></a>  CListBox::GetTopIndex

リスト ボックスに表示される最初の項目の 0 から始まるインデックスを取得します。

```
int GetTopIndex() const;
```

### <a name="return-value"></a>戻り値

成功した場合、リスト ボックスに表示される最初の項目の 0 から始まるインデックス返します。

### <a name="remarks"></a>Remarks

最初に、項目 0 は、リスト ボックスの上部にあるが上部にある別の項目があります、リスト ボックスがスクロール可能な場合。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

##  <a name="initstorage"></a>  CListBox::InitStorage

リスト ボックス項目を格納するためにメモリを割り当てます。

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>パラメーター

*nItems*<br/>
追加する項目の数を指定します。

*nBytes*<br/>
項目の文字列を割り当てることをバイト単位でメモリの量を指定します。

### <a name="return-value"></a>戻り値

成功すると、メモリを再割り当てする前に、リスト ボックスに格納できる項目の最大数が必要に応じて、それ以外の場合返します、十分なメモリが使用可能な意味ありません。

### <a name="remarks"></a>Remarks

多数の項目を追加する前にこの関数を呼び出して、`CListBox`します。

この関数は、高速化する多数のアイテム (100 個以上) を持つリスト ボックスの初期化を使用します。 したがって後続のメモリ量の指定が事前に割り当てる[AddString](#addstring)、 [InsertString](#insertstring)、および[Dir](#dir)関数は、最短時間を取得します。 見積もりは、パラメーターを使用できます。 多くを指定した場合は、余分なメモリが割り当てられます。過小を評価する場合、通常の割り当てを事前に割り当てられる量を超える項目に対して使用されます。

Windows 95/98 のみ:*NItems*パラメーターは 16 ビット値に制限されます。 つまり、リスト ボックスは、32,767 を超える項目を含めることはできません。 項目の数が制限されているが、リスト ボックス内の項目の合計サイズは、使用可能なメモリによってのみ制限されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

##  <a name="insertstring"></a>  CListBox::InsertString

リスト ボックスに、文字列を挿入します。

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
文字列を挿入する位置の 0 から始まるインデックスを指定します。 このパラメーターが-1 の場合、文字列はリストの末尾に追加されます。

*lpszItem*<br/>
挿入される null で終わる文字列を指します。

### <a name="return-value"></a>戻り値

文字列が挿入された位置の 0 から始まるインデックス。 エラーが発生した場合、戻り値は返します新しい文字列を格納する十分な空き領域がある場合は、返しますを返します。

### <a name="remarks"></a>Remarks

異なり、 [AddString](#addstring)メンバー関数は、`InsertString`のリストは発生しません、 [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルを並べ替えることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

##  <a name="itemfrompoint"></a>  CListBox::ItemFromPoint

指定した位置に最も近いリスト ボックス項目を決定します。 *pt*します。

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
リスト ボックスのクライアント領域の左上隅に対して相対的に指定された、最も近い項目を検索対象となるポイントです。

*bOutside*<br/>
場合は TRUE に設定されますが、ブール値変数への参照*pt*が最も近いリスト ボックス項目のクライアント領域外場合は FALSE *pt*が最も近いリスト ボックス項目のクライアント領域内。

### <a name="return-value"></a>戻り値

指定されたポイントに最も近い項目のインデックス*pt*します。

### <a name="remarks"></a>Remarks

上にマウス カーソルを移動するリスト ボックス アイテムを確認するのには、この関数を使用する可能性があります。

### <a name="example"></a>例

  例をご覧ください[CListBox::SetAnchorIndex](#setanchorindex)します。

##  <a name="measureitem"></a>  CListBox::MeasureItem

オーナー描画スタイルでリスト ボックスが作成されるときに、フレームワークによって呼び出されます。

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpMeasureItemStruct*<br/>
Long ポインター、 [MEASUREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagmeasureitemstruct)構造体。

### <a name="remarks"></a>Remarks

既定では、このメンバー関数は何もしません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`リスト ボックスのサイズの Windows に通知する構造体。 リスト ボックスが作成された場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)リスト ボックス内の各項目のスタイル、フレームワークの呼び出し、このメンバー関数。 それ以外の場合、このメンバーは、1 回だけ呼び出されます。

詳細についてを使用して、 [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルで作成されたオーナー描画リスト ボックスで、`SubclassDlgItem`のメンバー関数`CWnd`、説明を参照[テクニカル ノート 14: カスタム](../../mfc/tn014-custom-controls.md).

参照してください[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)の説明については、`MEASUREITEMSTRUCT`構造体。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

##  <a name="resetcontent"></a>  CListBox::ResetContent

リスト ボックスからすべての項目を削除します。

```
void ResetContent();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

##  <a name="selectstring"></a>  CListBox::SelectString

検索ボックスの一覧で項目の指定した文字列に一致して一致する項目が見つかった場合、その項目を選択します。

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>パラメーター

*nStartAfter*<br/>
最初の項目を検索する前にある項目の 0 から始まるインデックスが含まれています。 指定された項目に、リスト ボックスの上部から続行、検索では、リスト ボックスの下部に達すると、 *nStartAfter*します。 場合*nStartAfter* -1 で、最初からリスト ボックス全体が検索されます。

*lpszItem*<br/>
検索対象のプレフィックスを含む null で終わる文字列へのポインター。 検索では独立しており、ケースを指定するため、この文字列は、任意の大文字と小文字を含めることができます。

### <a name="return-value"></a>戻り値

検索が成功した場合は、選択した項目のインデックス。 検索が成功した場合、戻り値は返し、現在の選択は変更されません。

### <a name="remarks"></a>Remarks

リスト ボックスをスクロールすると、必要に応じて、選択した項目を表示します。

このメンバー関数を持つリスト ボックスでは使用できません、 [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル。

項目が選択されます (始点) から、先頭の文字で指定された文字列内の文字を一致する場合にのみ*lpszItem*します。

使用して、`FindString`メンバー関数は、項目を選択せずに文字列を検索します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

##  <a name="selitemrange"></a>  CListBox::SelItemRange

複数選択のリスト ボックス内の複数の連続する項目を選択します。

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>パラメーター

*選択*<br/>
選択範囲を設定する方法を指定します。 場合*選択*が true の場合、文字列を選択し、強調表示されます。 FALSE の場合、強調表示が削除され、文字列が選択されていません。

*nFirstItem*<br/>
設定する最初の項目の 0 から始まるインデックスを指定します。

*nLastItem*<br/>
設定する最後の項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

エラーが発生した場合を返します。

### <a name="remarks"></a>Remarks

このメンバー関数を複数選択のリスト ボックスでのみ使用します。 複数選択のリスト ボックスで 1 つの項目を選択する必要がある場合は場合、 *nFirstItem*と等しい*nLastItem* — を呼び出す、 [SetSel](#setsel)メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

##  <a name="setanchorindex"></a>  CListBox::SetAnchorIndex

拡張選択を開始する複数選択のリスト ボックスで、アンカーを設定します。

```
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
アンカーとなるリスト ボックス項目の 0 から始まるインデックスを指定します。

### <a name="remarks"></a>Remarks

複数選択のリスト ボックスでは、アンカー項目は、選択した項目を連続するブロックの最初または最後の項目が。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

##  <a name="setcaretindex"></a>  CListBox::SetCaretIndex

複数選択のリスト ボックスで、指定したインデックス位置にある項目にフォーカス四角形を設定します。

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックスにフォーカス四角形を表示する項目の 0 から始まるインデックスを指定します。

*bScroll*<br/>
この値が 0 の場合は、完全に表示されるまで、項目がスクロールされます。 この値がない場合 0 の場合、項目までスクロールが少なくとも部分的に表示されています。

### <a name="return-value"></a>戻り値

エラーが発生した場合を返します。

### <a name="remarks"></a>Remarks

項目が表示されない場合、ビューにスクロールされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

##  <a name="setcolumnwidth"></a>  CListBox::SetColumnWidth

複数列のリスト ボックス内のすべての列のピクセル単位の幅を設定 (で作成された、 [LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル)。

```
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>パラメーター

*cxWidth*<br/>
すべての列のピクセル単位の幅を指定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

##  <a name="setcursel"></a>  CListBox::SetCurSel

文字列を選択し、必要に応じて、ビューにスクロールします。

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>パラメーター

*nSelect*<br/>
選択する文字列の 0 から始まるインデックスを指定します。 場合*nSelect* -1 で、リスト ボックスが選択範囲がないように設定します。

### <a name="return-value"></a>戻り値

エラーが発生した場合を返します。

### <a name="remarks"></a>Remarks

新しい文字列を選択すると、リスト ボックスは、以前に選択した文字列から強調表示を削除します。

このメンバー関数は、単一選択のリスト ボックスでのみ使用します。

を設定または複数選択のリスト ボックスで選択を削除するには使用[CListBox::SetSel](#setsel)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

##  <a name="sethorizontalextent"></a>  CListBox::SetHorizontalExtent

これによって、リスト ボックスを水平方向にスクロールすることができます (ピクセル単位)、幅を設定します。

```
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>パラメーター

*cxExtent*<br/>
これによって、リスト ボックスを水平方向にスクロールすることができますのピクセル数を指定します。

### <a name="remarks"></a>Remarks

リスト ボックスのサイズがこの値よりも小さい場合は、水平スクロール バーはリスト ボックス内の項目を横方向にスクロールします。 リスト ボックスが、大規模またはこの値より大きい場合は、水平スクロール バーは表示されません。

呼び出しに応答する`SetHorizontalExtent`、リスト ボックスがで定義されている必要があります、 [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles)スタイル。

このメンバー関数では、複数列のリスト ボックスを適していません。 複数列のリスト ボックス、呼び出し、`SetColumnWidth`メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

##  <a name="setitemdata"></a>  CListBox::SetItemData

リスト ボックスで指定した項目に関連付けられている 32 ビット値を設定します。

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の 0 から始まるインデックスを指定します。

*dwItemData*<br/>
項目に関連する値を指定します。

### <a name="return-value"></a>戻り値

エラーが発生した場合を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

##  <a name="setitemdataptr"></a>  CListBox::SetItemDataPtr

指定したポインターのリスト ボックスで指定した項目に関連付けられている 32 ビット値の設定 ( **void** <strong>\*</strong>)。

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の 0 から始まるインデックスを指定します。

*pData*<br/>
項目を関連付けるへのポインターを指定します。

### <a name="return-value"></a>戻り値

エラーが発生した場合を返します。

### <a name="remarks"></a>Remarks

このポインターは項目の追加または削除、リスト ボックス内の項目の相対位置を変更する可能性がありますが、リスト ボックスの有効期間中有効です。 そのため、ボックス内の項目のインデックスを変更できますが、ポインターが信頼性の高いは残ります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

##  <a name="setitemheight"></a>  CListBox::SetItemHeight

リスト ボックス内の項目の高さを設定します。

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックスで、項目の 0 から始まるインデックスを指定します。 このパラメーターは、リスト ボックスに LBS_OWNERDRAWVARIABLE スタイル; がある場合にのみ使用します。それ以外の場合、0 に設定する必要があります。

*cyItemHeight*<br/>
項目のピクセル、高さを指定します。

### <a name="return-value"></a>戻り値

インデックスまたは高さが有効でない場合を返します。

### <a name="remarks"></a>Remarks

リスト ボックスがある場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルでは、この関数の設定で指定された項目の高さ*nIndex*します。 それ以外の場合、この関数は、リスト ボックス内のすべての項目の高さを設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

##  <a name="setlocale"></a>  CListBox::SetLocale

このリスト ボックスのロケール識別子を設定します。

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>パラメーター

*nNewLocale*<br/>
リスト ボックスに設定する新しい値のロケール識別子 (LCID)。

### <a name="return-value"></a>戻り値

このリスト ボックスの以前のロケール識別子 (LCID) 値。

### <a name="remarks"></a>Remarks

場合`SetLocale`を呼び出さない、既定のロケールがシステムから取得します。 コントロール パネル を使用して、この既定のシステム ロケールを変更できる地域 (または国際) アプリケーションです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

##  <a name="setsel"></a>  CListBox::SetSel

複数選択のリスト ボックス内の文字列を選択します。

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
設定する文字列の 0 から始まるインデックスが含まれています。 かどうかは-1 で、選択範囲が追加または削除の値に応じて、すべての文字列から*選択*します。

*選択*<br/>
選択範囲を設定する方法を指定します。 場合*選択*が true の場合、文字列を選択し、強調表示されます。 FALSE の場合、強調表示が削除され、文字列が選択されていません。 指定した文字列が選択されているし、既定で強調表示されます。

### <a name="return-value"></a>戻り値

エラーが発生した場合を返します。

### <a name="remarks"></a>Remarks

このメンバー関数を複数選択のリスト ボックスでのみ使用します。

単一選択のリスト ボックスから項目を選択する[CListBox::SetCurSel](#setcursel)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

##  <a name="settabstops"></a>  CListBox::SetTabStops

リスト ボックスのタブ ストップの位置を設定します。

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>パラメーター

*cxEachStop*<br/>
タブ ストップすべて*cxEachStop*ダイアログ単位。 参照してください*rgTabStops*ダイアログ ユニットの説明についてはします。

*nTabStops*<br/>
リスト ボックスにタブ ストップの数を指定します。

*rgTabStops*<br/>
ダイアログ単位でタブ ストップの位置を格納している整数の配列の最初のメンバーを指します。 ダイアログ単位は、水平方向または垂直方向の距離です。 1 つの水平ダイアログ単位は現在のダイアログ ベースの幅の単位の 4 分の 1 と等しくと 1 つの垂直方向のダイアログ ユニットは、現在のダイアログ ベースの高さの単位の 8 分の 1 に等しい。 ダイアログの基本単位は、高さと幅の現在のシステム フォントに基づいて計算されます。 `GetDialogBaseUnits` Windows 関数はピクセル単位で現在のダイアログ ボックスにベース ユニットの数を返します。 タブ ストップを昇順に並べ替え; 並べ替える必要があります。バック タブを指定することはできません。

### <a name="return-value"></a>戻り値

すべてのタブが設定された場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

タブ ストップを 2 つのダイアログ単位の既定のサイズを設定するには、このメンバー関数のパラメーターなしのバージョンを呼び出します。 タブ ストップを 2 以外のサイズを設定するとバージョンを呼び出す、 *cxEachStop*引数。

サイズの配列にタブ ストップを設定するとバージョンを使用して、 *rgTabStops*と*nTabStops*引数。 タブ ストップはの各値に設定する*rgTabStops*で指定された数まで*nTabStops*します。

呼び出しに応答する、`SetTabStops`メンバー関数は、リスト ボックスする必要がありますが作成された、 [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

##  <a name="settopindex"></a>  CListBox::SetTopIndex

特定のリスト ボックス項目が表示されるようにします。

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

成功した場合、0、またはエラーが発生した場合に返します。

### <a name="remarks"></a>Remarks

システムで指定されたいずれかの項目まで、リスト ボックスをスクロールする*nIndex*表示一覧の上部にあるボックスまたは最大スクロールの範囲に達しています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

##  <a name="vkeytoitem"></a>  CListBox::VKeyToItem

リスト ボックスの親ウィンドウは、リスト ボックスから WM_VKEYTOITEM メッセージを受信すると、フレームワークによって呼び出されます。

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>パラメーター

*nKey*<br/>
ユーザーの押したキーの仮想キー コード。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。

*nIndex*<br/>
リスト ボックスのキャレットの現在の位置。

### <a name="return-value"></a>戻り値

それ以上のアクションの 2、既定のアクションを 1 またはキーストロークの既定のアクションを実行するリスト ボックス項目のインデックスを指定する正の数値を-返します。

### <a name="remarks"></a>Remarks

WM_KEYDOWN メッセージを受信すると、リスト ボックスでは、次の両方が満たしている場合にのみ、リスト ボックスにより WM_VKEYTOITEM メッセージが送信されます。

- [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)一連のスタイルを設定します。

- 少なくとも 1 つの項目があります。

自分でがこの関数を呼び出す必要がありますはことはありません。 キーボード メッセージの独自のカスタム処理を提供するには、この関数をオーバーライドします。

オーバーライドが実行されるアクションをフレームワークに指示する値を返す必要があります。 戻り値 - 2 は、アプリケーションは、アイテムの選択のすべての側面を処理し、リスト ボックスによってこれ以上操作は必要ありませんを示します。 -2 を返す前に、選択範囲を設定したり、カレットを移動します。 選択範囲を設定する[SetCurSel](#setcursel)または[SetSel](#setsel)します。 カレットを移動するには使用[には](#setcaretindex)します。

戻り値 1 は、キー操作への応答に、リスト ボックスが既定のアクションを実行することを示します。既定の実装 - 1 を返します。

0 以上の戻り値は、リスト ボックスで、項目のインデックスを指定し、リスト ボックスがで指定したアイテムのキーストロークの既定のアクションを実行する必要がありますを示します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CTRLTEST](../../visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic クラス](../../mfc/reference/cstatic-class.md)
