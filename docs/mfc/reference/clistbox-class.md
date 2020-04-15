---
title: CListBox クラス
description: MFC CListBox クラスとそのメンバー関数の説明。
ms.date: 01/22/2020
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
ms.openlocfilehash: 5bc66ab2775ebb9023c65c9decae205604c978c6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372224"
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
|[Cリストボックス::Cリストボックス](#clistbox)|`CListBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CListBox::AddString](#addstring)|リスト ボックスに文字列を追加します。|
|[リストボックス::シャルトアイテム](#chartoitem)|文字列を持たないオーナー描画リスト ボックスのカスタムWM_CHAR処理を提供する場合はオーバーライドします。|
|[Cリストボックス::比較アイテム](#compareitem)|並べ替えられたオーナー描画リスト ボックス内の新しい項目の位置を決定するために、フレームワークによって呼び出されます。|
|[Cリストボックス::作成](#create)|Windows リスト ボックスを作成し、オブジェクトに`CListBox`アタッチします。|
|[:Dリストボックス:eleteItem](#deleteitem)|ユーザーがオーナー描画リスト ボックスから項目を削除したときに、フレームワークによって呼び出されます。|
|[:D文字列](#deletestring)|リスト ボックスから文字列を削除します。|
|[リストボックス::Dir](#dir)|現在のディレクトリからファイル名、ドライブ、またはその両方をリスト ボックスに追加します。|
|[:Dローアイテム](#drawitem)|オーナー描画リスト ボックスの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。|
|[リストボックス::文字列を検索します。](#findstring)|リスト ボックス内の文字列を検索します。|
|[リストボックス::文字列を正確に見つける](#findstringexact)|指定した文字列に一致する最初のリスト ボックス文字列を検索します。|
|[リストボックス::ゲットアンカーインデックス](#getanchorindex)|リスト ボックス内の現在のアンカー項目の 0 から始まるインデックスを取得します。|
|[リストボックス::ゲットキャレットインデックス](#getcaretindex)|複数選択リスト ボックス内のフォーカス四角形を持つ項目のインデックスを決定します。|
|[リストボックス::カウントを取得します。](#getcount)|リスト ボックス内の文字列の数を返します。|
|[リストボックス::ゲットカーセル](#getcursel)|リスト ボックス内で現在選択されている文字列の 0 から始まるインデックスを返します。|
|[Cリストボックス::ゲス水平範囲](#gethorizontalextent)|リスト ボックスを水平方向にスクロールできる幅をピクセル単位で返します。|
|[をクリックします。](#getitemdata)|リスト ボックスの項目に関連付けられた値を返します。|
|[をクリックします。](#getitemdataptr)|リスト ボックス項目へのポインターを返します。|
|[リストボックス::ゲットアイテムの高さ](#getitemheight)|リスト ボックス内の項目の高さを指定します。|
|[リストボックス::ゲットアイテムレクト](#getitemrect)|現在表示されているリスト ボックス項目の外接する四角形を返します。|
|[リストボックス::リストボックス情報](#getlistboxinfo)|列ごとの項目数を取得します。|
|[リストボックス::ゲットロケール](#getlocale)|リスト ボックスのロケール識別子を取得します。|
|[リストボックス::ゲットセル](#getsel)|リスト ボックス項目の選択状態を返します。|
|[リストボックス::ゲットセルカウント](#getselcount)|複数選択リスト ボックスで現在選択されている文字列の数を返します。|
|[リストボックス::ゲットセルアイテム](#getselitems)|リスト ボックスで現在選択されている文字列のインデックスを返します。|
|[リストボックス::テキストを取得します。](#gettext)|リスト ボックスの項目をバッファーにコピーします。|
|[リストボックス::ゲットテキストレン](#gettextlen)|リスト ボックス項目の長さ (バイト単位) を返します。|
|[リストボックス::ゲットトップインデックス](#gettopindex)|リスト ボックス内の最初に表示される文字列のインデックスを返します。|
|[リストボックス::イニトストレージ](#initstorage)|リスト ボックス項目と文字列のメモリ ブロックを事前に割り当てます。|
|[CListBox::InsertString](#insertstring)|リスト ボックス内の特定の位置に文字列を挿入します。|
|[リストボックス::アイテムソースポイント](#itemfrompoint)|ポイントに最も近いリスト ボックス項目のインデックスを返します。|
|[Cリストボックス::メジャーアイテム](#measureitem)|リスト ボックスのディメンションを決定するために、オーナー描画リスト ボックスが作成されるときに、フレームワークによって呼び出されます。|
|[コンテンツをリセットします。](#resetcontent)|リスト ボックスからすべてのエントリをクリアします。|
|[Cリストボックス::選択文字列](#selectstring)|単一選択リスト ボックス内の文字列を検索して選択します。|
|[リストボックス::セルアイテムレンジ](#selitemrange)|複数選択リスト ボックス内の文字列の範囲を選択または選択解除します。|
|[Cリストボックス::セットアンカーインデックス](#setanchorindex)|複数選択リスト ボックスのアンカーを設定して、拡張選択を開始します。|
|[リストボックス::セットキャレットインデックス](#setcaretindex)|フォーカスの四角形を、複数選択リスト ボックス内の指定したインデックス位置にある項目に設定します。|
|[箇条書きのボックス::列幅の設定](#setcolumnwidth)|複数列リスト ボックスの列幅を設定します。|
|[リストボックス::セットカーセル](#setcursel)|リスト ボックス文字列を選択します。|
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|リスト ボックスを水平方向にスクロールできる幅をピクセル単位で設定します。|
|[リストボックス::セットアイテムデータ](#setitemdata)|リスト ボックスの項目に関連付けられた値を設定します。|
|[をクリックします。](#setitemdataptr)|リスト ボックス項目へのポインターを設定します。|
|[リストボックス::セットアイテムの高さ](#setitemheight)|リスト ボックス内の項目の高さを設定します。|
|[リストボックス::セットロケール](#setlocale)|リスト ボックスのロケール識別子を設定します。|
|[リストボックス::セットセル](#setsel)|複数選択リスト ボックスのリスト ボックス項目を選択または選択解除します。|
|[箇条書きのセットボックス](#settabstops)|リスト ボックス内のタブ位置を設定します。|
|[リストボックス::セットトップインデックス](#settopindex)|リスト ボックス内の最初に表示される文字列の 0 から始まるインデックスを設定します。|
|[リストボックス::VKeyToItem](#vkeytoitem)|LBS_WANTKEYBOARDINPUT スタイル セットを使用してリスト ボックスのカスタム WM_KEYDOWN処理を提供する場合は、オーバーライドします。|

## <a name="remarks"></a>解説

リスト ボックスには、ユーザーが表示および選択できる項目 (ファイル名など) のリストが表示されます。

単一選択リスト ボックスでは、ユーザーは 1 つの項目のみを選択できます。 複数選択リスト ボックスでは、一定範囲の項目を選択できます。 ユーザーが項目を選択すると、項目が強調表示され、リスト ボックスから親ウィンドウに通知メッセージが送信されます。

リスト ボックスは、ダイアログ テンプレートから作成することも、コード内で直接作成することもできます。 オブジェクトを直接作成するには、オブジェクト`CListBox`を構築し[、Create](#create)メンバー関数を呼び出して Windows リスト ボックス コントロール`CListBox`を作成し、オブジェクトにアタッチします。 ダイアログ テンプレートでリスト ボックスを使用するには、ダイアログ ボックス クラスでリスト ボックス変数を宣言し`DDX_Control`、ダイアログ ボックス クラスの`DoDataExchange`関数でメンバー変数をコントロールに接続します。 (これは、ダイアログ ボックス クラスにコントロール変数を追加すると自動的に行われます)。

構築は、 から`CListBox`派生したクラスの 1 段階のプロセスです。 派生クラスのコンストラクターを記述し、コンストラクター`Create`内から呼び出します。

リスト ボックスから親に送信される Windows 通知メッセージ (通常[は CDialog](../../mfc/reference/cdialog-class.md)から派生したクラス) を処理する場合は、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。

各メッセージ マップ エントリは、次の形式をとります。

`ON_Notification( id, memberFxn )`

通知`id`を送信するリスト ボックス コントロールの子ウィンドウ ID を`memberFxn`指定します。

親の関数プロトタイプは次のとおりです。

`afx_msg void memberFxn( );`

次に、メッセージ マップエントリの候補と、それらが親に送信されるケースの説明を示します。

- ON_LBN_DBLCLK ユーザーがリスト ボックス内の文字列をダブルクリックします。 この通知メッセージは[、LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルを持つリスト ボックスのみが送信されます。

- ON_LBN_ERRSPACE リスト ボックスが要求を満たすのに十分なメモリを割り当てられません。

- ON_LBN_KILLFOCUS リスト ボックスが入力フォーカスを失っています。

- ON_LBN_SELCANCEL 現在のリスト ボックスの選択が取り消されます。 このメッセージは、リスト ボックスにLBS_NOTIFYスタイルが設定されている場合にのみ送信されます。

- ON_LBN_SELCHANGE リスト ボックスの選択内容が変更されました。 この通知は[、CListBox::SetCurSel](#setcursel)メンバー関数によって選択が変更された場合は送信されません。 この通知は、LBS_NOTIFY スタイルを持つリスト ボックスにのみ適用されます。 LBN_SELCHANGE通知メッセージは、選択が変更されない場合でも、ユーザーが矢印キーを押すと常に複数選択リストボックスに送信されます。

- ON_LBN_SETFOCUS リスト ボックスが入力フォーカスを受け取っています。

- ON_WM_CHARTOITEM 文字列のないオーナー描画リスト ボックスがWM_CHAR メッセージを受け取ります。

- ON_WM_VKEYTOITEM LBS_WANTKEYBOARDINPUT スタイルのリスト ボックスがWM_KEYDOWNメッセージを受信します。

ダイアログ ボックス内`CListBox`で (ダイアログ リソースを使用して) オブジェクト`CListBox`を作成すると、ユーザーがダイアログ ボックスを閉じると、オブジェクトは自動的に破棄されます。

ウィンドウ内にオブジェクト`CListBox`を作成する場合は、`CListBox`オブジェクトを破棄する必要があります。 スタック上にオブジェクト`CListBox`を作成すると、オブジェクトは自動的に破棄されます。 **新しい**関数を`CListBox`使用してヒープ上にオブジェクトを作成する場合は、ユーザーが親ウィンドウを閉じたときに破棄するために、オブジェクトの**delete**を呼び出す必要があります。

オブジェクトにメモリを`CListBox`割り当てる場合は、`CListBox`デストラクタをオーバーライドして割り当てを破棄します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="clistboxaddstring"></a><a name="addstring"></a>Cリストボックス::追加文字列

リスト ボックスに文字列を追加します。

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
追加する null で終わる文字列へのポイント。

### <a name="return-value"></a>戻り値

リスト ボックス内の文字列の 0 から始まるインデックス。 エラーが発生した場合は、戻り値がLB_ERR。新しい文字列を格納するために十分な領域がない場合は、戻り値がLB_ERRSPACEされます。

### <a name="remarks"></a>解説

リスト ボックスが[LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルで作成されなかった場合、文字列はリストの末尾に追加されます。 それ以外の場合は、文字列がリストに挿入され、リストが並べ替えられます。 リスト ボックスがLBS_SORT スタイルではなく[、LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルで作成された場合、フレームワークは、メンバー関数の 1 つ以上`CompareItem`の呼び出しによってリストを並べ替えます。

リスト ボックス内の特定の位置に文字列を挿入するには[、InsertString](#insertstring)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

## <a name="clistboxchartoitem"></a><a name="chartoitem"></a>リストボックス::シャルトアイテム

リスト ボックスの親ウィンドウがリスト ボックスからWM_CHARTOITEMメッセージを受信したときに、フレームワークによって呼び出されます。

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>パラメーター

*nキー*<br/>
ユーザーが入力した文字の ANSI コード。

*nIndex*<br/>
リスト ボックス キャレットの現在位置。

### <a name="return-value"></a>戻り値

それ以上のアクションがない場合は - 1 または - 2 を返し、キーストロークの既定のアクションを実行するリスト ボックス項目のインデックスを指定する場合は負でない数を返します。 デフォルトの実装は 1 を返します。

### <a name="remarks"></a>解説

WM_CHARTOITEM メッセージは、リスト ボックスがWM_CHARメッセージを受信したときに、リスト ボックスが次の条件をすべて満たしている場合にのみ送信されます。

- オーナー描画リストボックスです。

- [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルセットがありません。

- 少なくとも 1 つの項目があります。

この関数を自分で呼び出してはいけません。 キーボード メッセージの独自のカスタム処理を提供するには、この関数をオーバーライドします。

オーバーライドでは、どのようなアクションを実行したかをフレームワークに伝える値を返す必要があります。 戻り値が - 1 または - 2 の場合、項目の選択のすべての側面を処理し、リスト ボックスでそれ以上の操作を行う必要がないことを示します。 - 1 または - 2 を返す前に、選択を設定するか、キャレットを移動するか、またはその両方を行います。 選択を設定するには、[設定セル](#setcursel)または[セットセル](#setsel)を使用します。 キャレットを移動するには[、SetCaretIndex](#setcaretindex)を使用します。

戻り値が 0 以上の場合は、リスト ボックス内の項目のインデックスを指定し、リスト ボックスが指定された項目に対してキーストロークの既定のアクションを実行することを示します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

## <a name="clistboxclistbox"></a><a name="clistbox"></a>Cリストボックス::Cリストボックス

`CListBox` オブジェクトを構築します。

```
CListBox();
```

### <a name="remarks"></a>解説

オブジェクトは`CListBox`2 つの手順で作成します。 まず、コンストラクタ`ClistBox`を呼び出し`Create`、次に Windows リスト ボックスを初期化して に`CListBox`アタッチする を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

## <a name="clistboxcompareitem"></a><a name="compareitem"></a>Cリストボックス::比較アイテム

並べ替えられたオーナー描画リスト ボックス内の新しい項目の相対位置を決定するために、フレームワークによって呼び出されます。

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
構造体への長い`COMPAREITEMSTRUCT`ポインター。

### <a name="return-value"></a>戻り値

[構造体で](/windows/win32/api/winuser/ns-winuser-compareitemstruct)記述されている 2 つの項目の相対位置を示します。 次のいずれかの値を指定できます。

|[値]|意味|
|-----------|-------------|
|-1|項目 1 は、項目 2 の前に並べ替えます。|
|0|項目 1 と項目 2 は同じ並べ替えです。|
|1|項目 1 は、項目 2 の後に並べ替えます。|

`COMPAREITEMSTRUCT`構造体の説明については[、CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)を参照してください。

### <a name="remarks"></a>解説

既定では、このメンバー関数は何も実行しません。 LBS_SORT スタイルを持つオーナー描画リスト ボックスを作成する場合は、このメンバー関数をオーバーライドして、リスト ボックスに追加された新しい項目をフレームワークで並べ替える手助けをする必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

## <a name="clistboxcreate"></a><a name="create"></a>Cリストボックス::作成

Windows リスト ボックスを作成し、オブジェクトに`CListBox`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
リスト ボックスのスタイルを指定します。 [リスト ボックススタイル](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)の任意の組み合わせをボックスに適用します。

*Rect*<br/>
リスト ボックスのサイズと位置を指定します。 `CRect`オブジェクトまたは構造体のいずれか`RECT`です。

*pParentWnd*<br/>
リスト ボックスの親ウィンドウ (通常はオブジェクト`CDialog`) を指定します。 NULL にすることはできません。

*nID*<br/>
リスト ボックスのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

オブジェクトは`CListBox`2 つの手順で作成します。 まず、コンストラクタを呼び出し`Create`、次に Windows リスト ボックスを初期化して`CListBox`オブジェクトにアタッチする を呼び出します。

実行時`Create`に、WM_NCCREATE [、](../../mfc/reference/cwnd-class.md#onnccreate) [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)のメッセージがリスト ボックス コントロールに送信されます。

これらのメッセージは、`CWnd`既定では、基本クラスの[OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate) [、OnCreate、OnNcCalcSize](../../mfc/reference/cwnd-class.md#oncreate)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数によって処理されます。 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize) 既定のメッセージ処理を拡張するには、 から`CListBox`クラスを派生し、新しいクラスにメッセージ マップを追加し、上記のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`(たとえば、新しいクラスに必要な初期化を実行する場合)。

リスト ボックス コントロールに次の[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を適用します。

- WS_CHILD常に

- WS_VISIBLE通常

- WS_DISABLEDまれ

- WS_VSCROLL垂直スクロール バーを追加するには

- WS_HSCROLL 水平スクロール バーを追加するには

- WS_GROUP グループ コントロールへ

- WS_TABSTOP このコントロールへのタブ移動を許可するには

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

## <a name="clistboxdeleteitem"></a><a name="deleteitem"></a>:Dリストボックス:eleteItem

ユーザーがオーナー描画`CListBox`オブジェクトから項目を削除するか、リスト ボックスを破棄したときに、フレームワークによって呼び出されます。

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
削除された項目に関する情報を格納する Windows[の DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct)構造体への長いポインター。

### <a name="remarks"></a>解説

この関数の既定の実装は、何も行いません。 必要に応じてオーナー描画リストボックスを再描画するには、この関数をオーバーライドします。

構造体の説明については[、CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) `DELETEITEMSTRUCT`を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

## <a name="clistboxdeletestring"></a><a name="deletestring"></a>:D文字列

リスト ボックスから*nIndex*の位置にある項目を削除します。

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する文字列の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

リストに残っている文字列の数。 *nIndex*がリスト内の項目数より大きいインデックスを指定した場合、戻り値はLB_ERRされます。

### <a name="remarks"></a>解説

*nIndex*に続くすべての項目が 1 つ下の位置に移動するようになりました。 たとえば、リスト ボックスに 2 つの項目が含まれている場合、最初の項目を削除すると、残りの項目が最初の位置になります。 *nIndex*=0 最初の位置の項目。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

## <a name="clistboxdir"></a><a name="dir"></a>リストボックス::Dir

ファイル名、ドライブ、またはその両方のリストをリスト ボックスに追加します。

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>パラメーター

*Attr*<br/>
`CFile::GetStatu` [s](../../mfc/reference/cfile-class.md#getstatus)で説明されている**列挙**値の任意の組み合わせ、または次の値の任意の組み合わせを指定できます。

|[値]|意味|
|-----------|-------------|
|0x0000|ファイルの読み取りまたは書き込みが可能です。|
|0x0001|ファイルは読み取り可能ですが、書き込みできません。|
|0x0002|ファイルは非表示で、ディレクトリ一覧には表示されません。|
|0x0004|ファイルはシステムファイルです。|
|0x0010|*lpszWildCard*で指定された名前はディレクトリを指定します。|
|0x0020|ファイルがアーカイブされました。|
|0x4000|*lpszWildCard*で指定された名前に一致するすべてのドライブを含めます。|
|0x8000|排他フラグ。 排他フラグが設定されている場合は、指定したタイプのファイルのみがリストされます。 それ以外の場合は、指定された種類のファイルが「通常の」ファイルに加えてリストされます。|

*lpszワイルドカード*<br/>
ファイル指定文字列へのポイント。 文字列にはワイルドカードを使用できます (*.\*

### <a name="return-value"></a>戻り値

リストに追加された最後のファイル名の 0 から始まるインデックス。 エラーが発生した場合は、戻り値がLB_ERR。新しい文字列を格納するために十分な領域がない場合は、戻り値がLB_ERRSPACE。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

## <a name="clistboxdrawitem"></a><a name="drawitem"></a>:Dローアイテム

オーナー描画リスト ボックスの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
必要な描画の種類に関する情報を含む[DRAWITEMSTRUCT 構造体](/windows/win32/api/winuser/ns-winuser-drawitemstruct)への長いポインター。

### <a name="remarks"></a>解説

`itemAction`構造体の`itemState`および`DRAWITEMSTRUCT`メンバーは、実行する描画アクションを定義します。

既定では、このメンバー関数は何も実行しません。 オーナー描画`CListBox`オブジェクトの描画を実装するには、このメンバー関数をオーバーライドします。 アプリケーションは、このメンバー関数が終了する前に *、lpDrawItemStruct*で提供される表示コンテキストに選択されているすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります。

構造体の説明については[、CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) `DRAWITEMSTRUCT`を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

## <a name="clistboxfindstring"></a><a name="findstring"></a>リストボックス::文字列を検索します。

リスト ボックスの選択を変更せずに、指定したプレフィックスを含むリスト ボックス内の最初の文字列を検索します。

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>パラメーター

*開始後*<br/>
検索される最初の項目の前の項目の 0 から始まるインデックスが含まれます。 検索がリスト ボックスの一番下に到達すると、リスト ボックスの一番上から*nStartAfter*で指定された項目まで検索が続きます。 *nStartAfter*が -1 の場合、リスト ボックス全体が先頭から検索されます。

*をクリックします。*<br/>
検索するプレフィックスを含む null で終わる文字列へのポイント。 検索は大文字と小文字に依存しない検索なので、この文字列には大文字と小文字の組み合わせが含まれる場合があります。

### <a name="return-value"></a>戻り値

一致する項目の 0 から始まるインデックス、または検索が失敗した場合LB_ERR。

### <a name="remarks"></a>解説

[SelectString](#selectstring)メンバー関数を使用して、文字列を検索および選択します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

## <a name="clistboxfindstringexact"></a><a name="findstringexact"></a>リストボックス::文字列を正確に見つける

*lpszFind*で指定された文字列に一致する最初のリスト ボックス文字列を検索します。

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>パラメーター

*インデックススタート*<br/>
検索する最初の項目の前の項目の 0 から始まるインデックスを指定します。 検索がリスト ボックスの一番下に到達すると、リスト ボックスの一番上から*nIndexStart*で指定された項目まで検索が続きます。 *nIndexStart*が -1 の場合、リスト ボックス全体が先頭から検索されます。

*lpsz検索*<br/>
検索する null で終わる文字列へのポイント。 この文字列には、拡張子を含む完全なファイル名を含めることができます。 検索では大文字と小文字が区別されないので、文字列には大文字と小文字を組み合わせて指定できます。

### <a name="return-value"></a>戻り値

一致するアイテムのインデックス、または検索が失敗した場合LB_ERR。

### <a name="remarks"></a>解説

リスト ボックスがオーナー描画スタイルで作成されたが[、LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルがない場合、`FindStringExact`メンバー関数はダブルワード値を*lpszFind*の値と照合しようとします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

## <a name="clistboxgetanchorindex"></a><a name="getanchorindex"></a>リストボックス::ゲットアンカーインデックス

リスト ボックス内の現在のアンカー項目の 0 から始まるインデックスを取得します。

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、現在のアンカー項目のインデックス。それ以外の場合はLB_ERR。

### <a name="remarks"></a>解説

複数選択リスト ボックスでは、アンカー項目は、連続する選択項目のブロック内の最初または最後の項目です。

### <a name="example"></a>例

  [次](#setanchorindex)の例を参照してください。

## <a name="clistboxgetcaretindex"></a><a name="getcaretindex"></a>リストボックス::ゲットキャレットインデックス

複数選択リスト ボックス内のフォーカス四角形を持つ項目のインデックスを決定します。

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内にフォーカス四角形がある項目の 0 から始まるインデックス。 リスト ボックスが単一選択リスト ボックスの場合、戻り値は選択されている項目のインデックスです。.。

### <a name="remarks"></a>解説

項目が選択されている場合と選択されない場合があります。

### <a name="example"></a>例

  [次](#setcaretindex)の例を参照してください。

## <a name="clistboxgetcount"></a><a name="getcount"></a>リストボックス::カウントを取得します。

リスト ボックス内の項目数を取得します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内の項目数、またはエラーが発生した場合LB_ERR。

### <a name="remarks"></a>解説

返されるカウントは、最後の項目のインデックス値より 1 大きい値です (インデックスは 0 から始まります)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

## <a name="clistboxgetcursel"></a><a name="getcursel"></a>リストボックス::ゲットカーセル

単一選択リスト ボックス内の現在選択されている項目の 0 から始まるインデックスを取得します (存在する場合)。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

単一選択リスト ボックスの場合、現在選択されている項目の 0 から始まるインデックス。 現在選択されている項目がない場合は、LB_ERRされます。

複数選択リスト ボックスで、フォーカスのある項目のインデックス。

### <a name="remarks"></a>解説

複数選択リスト`GetCurSel`ボックスを呼び出しません。 代わりに[C リストボックスを使用します](#getselitems)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

## <a name="clistboxgethorizontalextent"></a><a name="gethorizontalextent"></a>Cリストボックス::ゲス水平範囲

水平方向にスクロールできる幅をリスト ボックスから取得します(ピクセル単位)。

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>戻り値

リスト ボックスのスクロール可能な幅 (ピクセル単位)。

### <a name="remarks"></a>解説

これは、リスト ボックスに水平スクロール バーがある場合にのみ適用されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

## <a name="clistboxgetitemdata"></a><a name="getitemdata"></a>をクリックします。

指定したリスト ボックス項目に関連付けられているアプリケーション指定のダブルワード値を取得します。

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス内の項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

アイテムに関連付けられている値、またはエラーが発生した場合LB_ERR。

### <a name="remarks"></a>解説

ダブルワード値は、呼び出しの*dwItemData*パラメーター[でした](#setitemdata)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

## <a name="clistboxgetitemdataptr"></a><a name="getitemdataptr"></a>をクリックします。

指定されたリスト ボックス項目に関連付けられているアプリケーション提供の 32 ビット値をポインター (**void** <strong>\*</strong>) として取得します。

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス内の項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

ポインターを取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

## <a name="clistboxgetitemheight"></a><a name="getitemheight"></a>リストボックス::ゲットアイテムの高さ

リスト ボックス内の項目の高さを指定します。

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス内の項目の 0 から始まるインデックスを指定します。 このパラメーターは、リスト ボックスにLBS_OWNERDRAWVARIABLEスタイルがある場合にのみ使用されます。それ以外の場合は、0 に設定する必要があります。

### <a name="return-value"></a>戻り値

リスト ボックス内の項目の高さ (ピクセル単位)。 リスト ボックスに[LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルが設定されている場合、戻り値は*nIndex*で指定された項目の高さになります。 エラーが発生した場合は、戻り値がLB_ERR。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

## <a name="clistboxgetitemrect"></a><a name="getitemrect"></a>リストボックス::ゲットアイテムレクト

リスト ボックス ウィンドウに現在表示されている場合に、リスト ボックス項目に境界を持つ四角形のサイズを取得します。

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の 0 から始まるインデックスを指定します。

*Lprect*<br/>
項目のリスト ボックス クライアント座標を受け取る[RECT 構造体](/windows/win32/api/windef/ns-windef-rect)への long ポインターを指定します。

### <a name="return-value"></a>戻り値

エラーが発生した場合にLB_ERRします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

## <a name="clistboxgetlistboxinfo"></a><a name="getlistboxinfo"></a>リストボックス::リストボックス情報

列ごとの項目数を取得します。

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>戻り値

オブジェクトの列あたりのアイテム数`CListBox`。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように[、LB_GETLISTBOXINFO](/windows/win32/Controls/lb-getlistboxinfo)メッセージの機能をエミュレートします。

## <a name="clistboxgetlocale"></a><a name="getlocale"></a>リストボックス::ゲットロケール

リスト ボックスで使用されているロケールを取得します。

```
LCID GetLocale() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内の文字列のロケール識別子 (LCID) 値。

### <a name="remarks"></a>解説

ロケールは、ソートされたリスト ボックス内の文字列の並べ替え順序を決定するために使用されます。

### <a name="example"></a>例

  [次](#setlocale)の例を参照してください。

## <a name="clistboxgetsel"></a><a name="getsel"></a>リストボックス::ゲットセル

項目の選択状態を取得します。

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

指定された項目が選択されている場合は正の数を返します。それ以外の場合は 0 です。 エラーが発生した場合は、戻り値がLB_ERR。

### <a name="remarks"></a>解説

このメンバー関数は、単一選択リスト ボックスと複数選択リスト ボックスの両方で使用できます。

現在選択されているリスト ボックス項目のインデックスを取得するには[、CListBox::GetCurSel](#getcursel)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

## <a name="clistboxgetselcount"></a><a name="getselcount"></a>リストボックス::ゲットセルカウント

複数選択リスト ボックス内の選択項目の総数を取得します。

```
int GetSelCount() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内の選択項目の数。 リスト ボックスが単一選択リスト ボックスの場合、戻り値はLB_ERR。

### <a name="example"></a>例

  [次](#getselitems)の例を参照してください。

## <a name="clistboxgetselitems"></a><a name="getselitems"></a>リストボックス::ゲットセルアイテム

複数選択リスト ボックス内の選択項目の項目番号を指定する整数の配列をバッファーに格納します。

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>パラメーター

*数個のアイテム*<br/>
選択した項目の最大数を指定します。

*rgIndex*<br/>
*nMaxItems*で指定された整数の数に十分な大きさのバッファーへのポインターを指定します。

### <a name="return-value"></a>戻り値

バッファーに配置された実際の項目数。 リスト ボックスが単一選択リスト ボックスの場合、戻り値`LB_ERR`は です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

## <a name="clistboxgettext"></a><a name="gettext"></a>リストボックス::テキストを取得します。

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

*バッファ*<br/>
文字列を受け取るバッファーへのポイント。 バッファーには、文字列と終端の NULL 文字に十分な領域が必要です。 文字列のサイズは、メンバー関数を呼び出すことによって事前に`GetTextLen`決定できます。

*文字列*<br/>
`CString` オブジェクトへの参照です。

### <a name="return-value"></a>戻り値

終端の NULL 文字を除く文字列の長さ (バイト単位)。 *nIndex が*有効なインデックスを指定しない場合、戻り値はLB_ERR。

### <a name="remarks"></a>解説

このメンバー関数の 2 番目の形式`CString`では、文字列テキストをオブジェクトに入力します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

## <a name="clistboxgettextlen"></a><a name="gettextlen"></a>リストボックス::ゲットテキストレン

リスト ボックス項目内の文字列の長さを取得します。

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
文字列の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

終端の NULL 文字を除く文字列の長さ (文字数)。 *nIndex が*有効なインデックスを指定しない場合、戻り値はLB_ERR。

### <a name="example"></a>例

  [次](#gettext)の例を参照してください。

## <a name="clistboxgettopindex"></a><a name="gettopindex"></a>リストボックス::ゲットトップインデックス

リスト ボックス内の最初に表示される項目の 0 から始まるインデックスを取得します。

```
int GetTopIndex() const;
```

### <a name="return-value"></a>戻り値

リスト ボックス内の最初に表示されている項目の 0 から始まるインデックスが正常に実行された場合は、LB_ERR。

### <a name="remarks"></a>解説

最初は、項目 0 はリスト ボックスの上部に表示されますが、リスト ボックスがスクロールされている場合は、別の項目が上部に表示されることがあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

## <a name="clistboxinitstorage"></a><a name="initstorage"></a>リストボックス::イニトストレージ

リスト ボックス項目を格納するためのメモリを割り当てます。

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>パラメーター

*nアイテム*<br/>
追加する項目の数を指定します。

*Nbytes*<br/>
項目文字列に割り当てるメモリの量をバイト単位で指定します。

### <a name="return-value"></a>戻り値

正常に実行された場合は、メモリの再割り当てが必要になる前にリスト ボックスに格納できる項目の最大数が、それ以外の場合はLB_ERRSPACE、メモリが不足していることを意味します。

### <a name="remarks"></a>解説

多数の項目を に追加する前に、この`CListBox`関数を呼び出します。

この関数は、項目数が多いリスト ボックス (100 を超える) の初期化を高速化します。 指定されたメモリ量が事前に割り当てられ、後続の[AddString](#addstring) [、InsertString](#insertstring)、[および Dir](#dir)関数は、可能な限り短い時間を取ります。 パラメータの見積を使用できます。 過大評価すると、余分なメモリが割り当てられます。過小評価すると、事前割当量を超える品目に対して通常の割り当てが使用されます。

Windows 95/98 のみ: *nItems*パラメーターは 16 ビットの値に制限されています。 つまり、リスト ボックスに 32,767 個を超える項目を含めることはできません。 項目数は制限されますが、リスト ボックス内の項目の合計サイズは、使用可能なメモリによってのみ制限されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

## <a name="clistboxinsertstring"></a><a name="insertstring"></a>文字列を挿入します。

リスト ボックスに文字列を挿入します。

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
文字列を挿入する位置の 0 から始まるインデックスを指定します。 このパラメーターが -1 の場合、文字列はリストの末尾に追加されます。

*をクリックします。*<br/>
挿入される null で終わる文字列を指します。

### <a name="return-value"></a>戻り値

文字列が挿入された位置の 0 から始まるインデックス。 エラーが発生した場合は、戻り値がLB_ERR。新しい文字列を格納するために十分な領域がない場合は、戻り値がLB_ERRSPACEされます。

### <a name="remarks"></a>解説

メンバー関数の[AddString](#addstring) `InsertString`とは異なり[、LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルのリストは並べ替えられません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

## <a name="clistboxitemfrompoint"></a><a name="itemfrompoint"></a>リストボックス::アイテムソースポイント

*pt*で指定したポイントに最も近いリスト ボックス項目を決定します。

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
リスト ボックスのクライアント領域の左上隅を基準にして指定された、最も近い項目を検索するポイント。

*bアウトサイド*<br/>
*pt*がリスト ボックスのクライアント領域の外側にある場合は TRUE に設定される BOOL 変数への*pt*参照。

### <a name="return-value"></a>戻り値

*pt*で指定されたポイントに最も近い項目のインデックス。

### <a name="remarks"></a>解説

この関数を使用して、マウス カーソルが移動するリスト ボックスの項目を特定できます。

### <a name="example"></a>例

  [次](#setanchorindex)の例を参照してください。

## <a name="clistboxmeasureitem"></a><a name="measureitem"></a>Cリストボックス::メジャーアイテム

オーナー描画スタイルを持つリスト ボックスが作成されるときに、フレームワークによって呼び出されます。

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
[構造体への](/windows/win32/api/winuser/ns-winuser-measureitemstruct)長いポインター。

### <a name="remarks"></a>解説

既定では、このメンバー関数は何も実行しません。 このメンバー関数をオーバーライドし、リスト`MEASUREITEMSTRUCT`ボックスのディメンションを Windows に通知する構造体を入力します。 リスト ボックスが[LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルで作成された場合、フレームワークはリスト ボックス内の各項目に対してこのメンバー関数を呼び出します。 それ以外の場合、このメンバーは 1 回だけ呼び出されます。

のメンバー関数`CWnd`で作成されたオーナー描画リストボックスで[LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルを`SubclassDlgItem`使用する方法の詳細については、『テクニカル ノート[14』](../../mfc/tn014-custom-controls.md)の説明を参照してください。

構造体の説明については[、CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT`を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

## <a name="clistboxresetcontent"></a><a name="resetcontent"></a>コンテンツをリセットします。

リスト ボックスからすべての項目を削除します。

```
void ResetContent();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

## <a name="clistboxselectstring"></a><a name="selectstring"></a>Cリストボックス::選択文字列

指定した文字列に一致するリスト ボックス項目を検索し、一致する項目が見つかった場合は、その項目を選択します。

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>パラメーター

*開始後*<br/>
検索される最初の項目の前の項目の 0 から始まるインデックスが含まれます。 検索がリスト ボックスの一番下に到達すると、リスト ボックスの一番上から*nStartAfter*で指定された項目まで検索が続きます。 *nStartAfter*が -1 の場合、リスト ボックス全体が先頭から検索されます。

*をクリックします。*<br/>
検索するプレフィックスを含む null で終わる文字列へのポイント。 検索は大文字と小文字に依存しない検索なので、この文字列には大文字と小文字の組み合わせが含まれる場合があります。

### <a name="return-value"></a>戻り値

検索が成功した場合に選択した項目のインデックス。 検索が失敗した場合、戻り値はLB_ERRされ、現在の選択は変更されません。

### <a name="remarks"></a>解説

必要に応じてリスト ボックスがスクロールされ、選択した項目が表示されます。

このメンバー関数は[、LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルを持つリスト ボックスでは使用できません。

項目は、開始点から始まる文字が*lpszItem*で指定された文字列の文字と一致する場合にのみ選択されます。

このメンバー`FindString`関数を使用して、項目を選択せずに文字列を検索します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

## <a name="clistboxselitemrange"></a><a name="selitemrange"></a>リストボックス::セルアイテムレンジ

複数選択リスト ボックス内の複数の連続した項目を選択します。

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>パラメーター

*b選択*<br/>
選択範囲の設定方法を指定します。 *bSelect*が TRUE の場合、文字列が選択され、強調表示されます。FALSE の場合、ハイライトは削除され、文字列は選択されなくなります。

*最初のアイテム*<br/>
設定する最初の項目の 0 から始まるインデックスを指定します。

*ラストアイテム*<br/>
設定する最後の項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

エラーが発生した場合にLB_ERRします。

### <a name="remarks"></a>解説

このメンバー関数は、複数選択リスト ボックスでのみ使用します。 複数選択リスト ボックス内の項目を 1 つだけ選択する必要がある場合、つまり*nFirstItem*が*nLastItem*に等しい場合は、代わりに[SetSel](#setsel)メンバー関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

## <a name="clistboxsetanchorindex"></a><a name="setanchorindex"></a>Cリストボックス::セットアンカーインデックス

複数選択リスト ボックスのアンカーを設定して、拡張選択を開始します。

```
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
アンカーとなるリスト ボックス項目の 0 から始まるインデックスを指定します。

### <a name="remarks"></a>解説

複数選択リスト ボックスでは、アンカー項目は、連続する選択項目のブロック内の最初または最後の項目です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

## <a name="clistboxsetcaretindex"></a><a name="setcaretindex"></a>リストボックス::セットキャレットインデックス

フォーカスの四角形を、複数選択リスト ボックス内の指定したインデックス位置にある項目に設定します。

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス内のフォーカス四角形を受け取る項目の 0 から始まるインデックスを指定します。

*スクロール*<br/>
この値が 0 の場合、項目は完全に表示されるまでスクロールされます。 この値が 0 でない場合、項目は少なくとも部分的に表示されるまでスクロールされます。

### <a name="return-value"></a>戻り値

エラーが発生した場合にLB_ERRします。

### <a name="remarks"></a>解説

アイテムが表示されない場合は、スクロールして表示されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

## <a name="clistboxsetcolumnwidth"></a><a name="setcolumnwidth"></a>箇条書きのボックス::列幅の設定

複数列リスト ボックス[(LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルで作成) 内のすべての列の幅をピクセル単位で設定します。

```
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>パラメーター

*幅*<br/>
すべての列の幅をピクセル単位で指定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

## <a name="clistboxsetcursel"></a><a name="setcursel"></a>リストボックス::セットカーセル

文字列を選択し、必要に応じてスクロールして表示します。

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>パラメーター

*n選択*<br/>
選択する文字列の 0 から始まるインデックスを指定します。 *nSelect*が -1 の場合、リスト ボックスは選択を持たない状態に設定されます。

### <a name="return-value"></a>戻り値

エラーが発生した場合にLB_ERRします。

### <a name="remarks"></a>解説

新しい文字列を選択すると、リスト ボックスは、以前に選択した文字列からハイライトを削除します。

このメンバー関数は、単一選択リスト ボックスでのみ使用します。

複数選択リスト ボックスの選択を設定または削除するには[、CListBox::SetSel](#setsel)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

## <a name="clistboxsethorizontalextent"></a><a name="sethorizontalextent"></a>Cリストボックス::セット水平エクステント

リスト ボックスを水平方向にスクロールできる幅をピクセル単位で設定します。

```
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>パラメーター

*cx範囲*<br/>
リスト ボックスを水平方向にスクロールできるピクセル数を指定します。

### <a name="remarks"></a>解説

リスト ボックスのサイズがこの値より小さい場合、水平スクロール バーはリスト ボックス内の項目を水平方向にスクロールします。 リスト ボックスがこの値より大きい場合、水平スクロール バーは非表示になります。

への`SetHorizontalExtent`呼び出しに応答するには、リスト ボックスが[WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles)スタイルで定義されている必要があります。

このメンバー関数は、複数列のリスト ボックスには役立ちません。 複数列のリスト ボックスの場合`SetColumnWidth`は、メンバー関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

## <a name="clistboxsetitemdata"></a><a name="setitemdata"></a>リストボックス::セットアイテムデータ

リスト ボックス内の指定した項目に関連付けられた値を設定します。

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の 0 から始まるインデックスを指定します。

*データ*<br/>
項目に関連付ける値を指定します。

### <a name="return-value"></a>戻り値

エラーが発生した場合にLB_ERRします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

## <a name="clistboxsetitemdataptr"></a><a name="setitemdataptr"></a>をクリックします。

リスト ボックス内の指定された項目に関連付けられた 32 ビット値を、指定したポインタ ( **void** <strong>\*</strong>) に設定します。

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の 0 から始まるインデックスを指定します。

*Pdata*<br/>
項目に関連付けるポインターを指定します。

### <a name="return-value"></a>戻り値

エラーが発生した場合にLB_ERRします。

### <a name="remarks"></a>解説

このポインターは、リスト ボックス内の項目の相対位置が項目の追加または削除に応じて変更される場合でも、リスト ボックスの有効期間に対して有効です。 したがって、ボックス内の項目のインデックスは変更できますが、ポインタは信頼できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

## <a name="clistboxsetitemheight"></a><a name="setitemheight"></a>リストボックス::セットアイテムの高さ

リスト ボックス内の項目の高さを設定します。

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス内の項目の 0 から始まるインデックスを指定します。 このパラメーターは、リスト ボックスにLBS_OWNERDRAWVARIABLEスタイルがある場合にのみ使用されます。それ以外の場合は、0 に設定する必要があります。

*アイテムの高さ*<br/>
項目の高さをピクセル単位で指定します。

### <a name="return-value"></a>戻り値

インデックスまたは高さが無効な場合にLB_ERRします。

### <a name="remarks"></a>解説

リスト ボックスに[LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルが設定されている場合、この関数は*nIndex*で指定された項目の高さを設定します。 それ以外の場合は、リスト ボックス内のすべての項目の高さを設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

## <a name="clistboxsetlocale"></a><a name="setlocale"></a>リストボックス::セットロケール

このリスト ボックスのロケール識別子を設定します。

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>パラメーター

*n新しいロケール*<br/>
リスト ボックスに設定する新しいロケール識別子 (LCID) 値。

### <a name="return-value"></a>戻り値

このリスト ボックスの以前のロケール識別子 (LCID) 値。

### <a name="remarks"></a>解説

呼`SetLocale`び出されない場合、デフォルトのロケールはシステムから取得されます。 このシステムの既定のロケールは、コントロール パネルの地域 (または国際) アプリケーションを使用して変更できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

## <a name="clistboxsetsel"></a><a name="setsel"></a>リストボックス::セットセル

複数選択リスト ボックス内の文字列を選択します。

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
設定する文字列の 0 から始まるインデックスを格納します。 -1 の場合、選択項目は*bSelect*の値に応じて、すべての文字列に追加または削除されます。

*b選択*<br/>
選択範囲の設定方法を指定します。 *bSelect*が TRUE の場合、文字列が選択され、強調表示されます。FALSE の場合、ハイライトは削除され、文字列は選択されなくなります。 指定した文字列が選択され、既定で強調表示されます。

### <a name="return-value"></a>戻り値

エラーが発生した場合にLB_ERRします。

### <a name="remarks"></a>解説

このメンバー関数は、複数選択リスト ボックスでのみ使用します。

単一選択リスト ボックスから項目を選択するには[、CListBox::SetCurSel](#setcursel)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

## <a name="clistboxsettabstops"></a><a name="settabstops"></a>箇条書きのセットボックス

リスト ボックス内のタブ位置を設定します。

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>パラメーター

*お互いの停止*<br/>
タブストップは、各*cxEachStop*ダイアログユニットで設定されます。 ダイアログ ユニットの説明については*rgTabStops*を参照してください。

*nタブストップ*<br/>
リスト ボックスに表示するタブ位置の数を指定します。

*rgタブストップ*<br/>
ダイアログ単位のタブストップ位置を含む整数の配列の最初のメンバーを指します。 ダイアログ単位は、水平または垂直の距離です。 1 つの水平ダイアログ単位は現在のダイアログ ベースの幅単位の 4 分の 1 に等しく、1 つの垂直ダイアログ 単位は現在のダイアログ ベースの高さの単位の 8 分の 1 に等しくなります。 ダイアログベースの単位は、現在のシステムフォントの高さと幅に基づいて計算されます。 Windows`GetDialogBaseUnits`関数は、現在のダイアログベースの単位をピクセル単位で返します。 タブ位置は昇順に並べ替える必要があります。バック タブは使用できません。

### <a name="return-value"></a>戻り値

すべてのタブが設定されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

タブストップを既定のサイズの 2 ダイアログ ユニットに設定するには、このメンバー関数のパラメーターなしのバージョンを呼び出します。 タブストップを 2 以外のサイズに設定するには *、cxEachStop*引数を指定してバージョンを呼び出します。

タブ位置をサイズの配列に設定するには、*引数 rgTabStops*および*nTabStops*を指定してバージョンを使用します。 タブストップは *、nTabStops*で指定された数まで rgTabStops の各値に設定*されます*。

`SetTabStops`メンバー関数の呼び出しに応答するには、リスト ボックスが[LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルで作成されている必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

## <a name="clistboxsettopindex"></a><a name="settopindex"></a>リストボックス::セットトップインデックス

特定のリスト ボックス項目が表示されるようにします。

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

成功した場合は 0 を、エラーが発生した場合はLB_ERR。

### <a name="remarks"></a>解説

nIndex で指定された項目がリスト ボックスの先頭*nIndex*に表示されるか、最大スクロール範囲に達するまで、リスト ボックスがスクロールされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

## <a name="clistboxvkeytoitem"></a><a name="vkeytoitem"></a>リストボックス::VKeyToItem

リスト ボックスの親ウィンドウがリスト ボックスからWM_VKEYTOITEMメッセージを受信したときに、フレームワークによって呼び出されます。

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>パラメーター

*nキー*<br/>
ユーザーが押したキーの仮想キー コード。 標準の仮想キー コードの一覧については、Winuser.h を参照してください。

*nIndex*<br/>
リスト ボックス キャレットの現在位置。

### <a name="return-value"></a>戻り値

それ以上のアクションの場合は 2、既定のアクションの場合は 1、キーストロークの既定のアクションを実行するリスト ボックス項目のインデックスを指定する場合は負でない数を返します。

### <a name="remarks"></a>解説

WM_VKEYTOITEM メッセージは、リスト ボックスがWM_KEYDOWNメッセージを受信したときに、リスト ボックスが次の両方に一致する場合にのみ送信されます。

- [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルセットを持っています。

- 少なくとも 1 つの項目があります。

この関数を自分で呼び出してはいけません。 キーボード メッセージの独自のカスタム処理を提供するには、この関数をオーバーライドします。

オーバーライドが実行したアクションをフレームワークに伝えるために、値を返す必要があります。 戻り値 -2 は、アプリケーションが項目の選択のすべての側面を処理し、リスト ボックスによるそれ以上のアクションを必要とすることを示します。 2 を返す前に、選択を設定するか、キャレットを移動するか、またはその両方を行います。 選択を設定するには、[設定セル](#setcursel)または[セットセル](#setsel)を使用します。 キャレットを移動するには[、SetCaretIndex](#setcaretindex)を使用します。

戻り値が -1 の場合、リスト ボックスはキーストロークに対する応答として既定のアクションを実行する必要があることを示します。デフォルトの実装は 1 を返します。

戻り値が 0 以上の場合は、リスト ボックス内の項目のインデックスを指定し、リスト ボックスが指定された項目に対してキーストロークの既定のアクションを実行することを示します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CTRL テスト](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[Cコンボボックスクラス](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic クラス](../../mfc/reference/cstatic-class.md)
