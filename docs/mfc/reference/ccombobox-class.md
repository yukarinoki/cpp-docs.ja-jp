---
title: CComboBox クラス
ms.date: 11/04/2016
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
ms.openlocfilehash: e7472b808d8b5d743d884d9e3806df7ffe499836
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178780"
---
# <a name="ccombobox-class"></a>CComboBox クラス

Windows のコンボ ボックスの機能が用意されています。

## <a name="syntax"></a>構文

```
class CComboBox : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComboBox::CComboBox](#ccombobox)|`CComboBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComboBox::AddString](#addstring)|リスト ボックス、コンボ ボックスまたは CBS_SORT スタイルを使用してリスト ボックスの並べ替えの位置にあるリストの末尾に文字列を追加します。|
|[CComboBox::Clear](#clear)|削除 (クリア) 現在の選択範囲の編集コントロールに存在する場合。|
|[CComboBox::CompareItem](#compareitem)|並べ替えられたオーナー描画コンボ ボックスで新しいリスト アイテムの相対位置を決定するためにフレームワークによって呼び出されます。|
|[CComboBox::Copy](#copy)|されているテキスト形式でクリップボードに存在する場合は、現在の選択範囲をコピーします。|
|[CComboBox::Create](#create)|コンボ ボックスを作成し、それにアタッチします、`CComboBox`オブジェクト。|
|[CComboBox::Cut](#cut)|(切り取り) 現在の選択範囲のいずれかの編集コントロールし、されているテキスト形式で、削除されたテキストをクリップボードにコピー場合。|
|[CComboBox::DeleteItem](#deleteitem)|リスト項目がオーナー描画コンボ ボックスから削除されたときに、フレームワークによって呼び出されます。|
|[オーナー](#deletestring)|コンボ ボックスのリスト ボックスから文字列を削除します。|
|[CComboBox::Dir](#dir)|コンボ ボックスのリスト ボックスにファイル名の一覧を追加します。|
|[CComboBox::DrawItem](#drawitem)|ビジュアルな部分のオーナー描画コンボ ボックスが変更されたときにフレームワークによって呼び出されます。|
|[Ccombobox::findstring](#findstring)|コンボ ボックスの一覧ボックスで指定したプレフィックスを含む最初の文字列を検索します。|
|[CComboBox::FindStringExact](#findstringexact)|指定した文字列と一致する、(コンボ ボックス) でのボックスの一覧の最初文字列を検索します。|
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|に関する情報を取得、`CComboBox`オブジェクト。|
|[CComboBox::GetCount](#getcount)|コンボ ボックスのリスト ボックス内の項目の数を取得します。|
|[CComboBox::GetCueBanner](#getcuebanner)|コンボ ボックス コントロールに表示されるヒントのテキストを取得します。|
|[CComboBox::GetCurSel](#getcursel)|コンボ ボックスの一覧ボックスで、存在する場合は、現在選択されている項目のインデックスを取得します。|
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|ドロップダウン コンボ ボックスの表示 (ドロップ ダウン) リスト ボックスの画面座標を取得します。|
|[CComboBox::GetDroppedState](#getdroppedstate)|かどうか、リスト ボックスのドロップダウン コンボ ボックスを表示 (ドロップダウン) を決定します。|
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|最小のコンボ ボックスのドロップダウン リスト ボックス部分の幅を取得します。|
|[CComboBox::GetEditSel](#geteditsel)|コンボ ボックスの編集コントロールに現在の選択範囲の開始と終了文字位置を取得します。|
|[CComboBox::GetExtendedUI](#getextendedui)|コンボ ボックスが既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスであるかどうかを判断します。|
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|コンボ ボックスの一覧ボックスが水平方向にスクロールするピクセルの幅を返します。|
|[CComboBox::GetItemData](#getitemdata)|指定されたコンボ ボックス アイテムに関連付けられたアプリケーションによって提供される 32 ビット値を取得します。|
|[CComboBox::GetItemDataPtr](#getitemdataptr)|指定されたコンボ ボックス項目に関連付けられているアプリケーションによって提供される 32 ビット ポインターを取得します。|
|[CComboBox::GetItemHeight](#getitemheight)|コンボ ボックスのリスト項目の高さを取得します。|
|[CComboBox::GetLBText](#getlbtext)|コンボ ボックスのリスト ボックスから文字列を取得します。|
|[CComboBox::GetLBTextLen](#getlbtextlen)|コンボ ボックスの一覧ボックスで、文字列の長さを取得します。|
|[CComboBox::GetLocale](#getlocale)|コンボ ボックスのロケール識別子を取得します。|
|[CComboBox::GetMinVisible](#getminvisible)|現在のコンボ ボックスのドロップダウン リストで表示される項目の最小数を取得します。|
|[CComboBox::GetTopIndex](#gettopindex)|コンボ ボックスの一覧ボックスの部分では、最初に表示される項目のインデックスを返します。|
|[CComboBox::InitStorage](#initstorage)|項目とコンボ ボックスの一覧ボックス部分文字列のメモリのブロックは事前に割り当てます。|
|[CComboBox::InsertString](#insertstring)|コンボ ボックスのリスト ボックスに文字列を挿入します。|
|[CComboBox::LimitText](#limittext)|ユーザーがコンボ ボックスの編集コントロールに入力できるテキストの長さを制限します。|
|[CComboBox::MeasureItem](#measureitem)|オーナー描画コンボ ボックスが作成されたときに、コンボ ボックスのサイズを決定するためにフレームワークによって呼び出されます。|
|[CComboBox::Paste](#paste)|クリップボードから現在のカーソル位置にある編集コントロールにデータを挿入します。 クリップボードにされているテキスト形式のデータが含まれている場合にのみデータが挿入されます。|
|[CComboBox::ResetContent](#resetcontent)|一覧からすべての項目のボックスし、コンボ ボックスのコントロールの編集を削除します。|
|[CComboBox::SelectString](#selectstring)|コンボ ボックスのリスト ボックス内の文字列を検索し、文字列が見つかった場合、リスト ボックスで、文字列を選択し、編集コントロールに文字列をコピーします。|
|[CComboBox::SetCueBanner](#setcuebanner)|コンボ ボックス コントロールに表示されるヒントのテキストを設定します。|
|[CComboBox::SetCurSel](#setcursel)|コンボ ボックスのリスト ボックスに文字列を選択します。|
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|最小のコンボ ボックスのドロップダウン リスト ボックス部分の幅を設定します。|
|[CComboBox::SetEditSel](#seteditsel)|コンボ ボックスの編集コントロール内の文字を選択します。|
|[CComboBox::SetExtendedUI](#setextendedui)|既定のユーザー インターフェイスまたは CBS_DROPDOWN または CBS_DROPDOWNLIST スタイルがコンボ ボックスの拡張ユーザー インターフェイスのいずれかを選択します。|
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|コンボ ボックスの一覧ボックスが水平方向にスクロールするピクセルの幅に設定します。|
|[CComboBox::SetItemData](#setitemdata)|コンボ ボックスで指定した項目に関連付けられている 32 ビット値を設定します。|
|[CComboBox::SetItemDataPtr](#setitemdataptr)|コンボ ボックスで指定した項目に関連付けられている 32 ビット ポインターを設定します。|
|[CComboBox::SetItemHeight](#setitemheight)|コンボ ボックスまたはコンボ ボックスの編集コントロール (または静的なテキスト) の部分の高さでリスト項目の高さを設定します。|
|[CComboBox::SetLocale](#setlocale)|コンボ ボックスのロケール識別子を設定します。|
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|現在のコンボ ボックスのドロップダウン リストで表示される項目の最小数を設定します。|
|[CComboBox::SetTopIndex](#settopindex)|上部にある指定したインデックスを持つ項目を表示するコンボ ボックスの一覧ボックスの部分に指示します。|
|[CComboBox::ShowDropDown](#showdropdown)|CBS_DROPDOWN または CBS_DROPDOWNLIST スタイルがコンボ ボックスのリスト ボックスの表示と非表示を切り替えます。|

## <a name="remarks"></a>Remarks

コンボ ボックスは、スタティック コントロールまたは編集コントロールのいずれかを組み合わせて、リスト ボックスで構成されます。 コントロールのリスト ボックスの部分が常に表示されますまたは可能性がありますのみドロップダウン リスト コントロールの横にあるドロップダウン矢印を選択するとします。

リスト ボックスで現在選択されている項目 (ある場合) は、静的に表示されるまたはコントロールを編集します。 さらに、コンボ ボックスがドロップダウン リストのスタイル、ユーザーは、一覧で、項目のいずれかの最初の文字を入力でき、リスト ボックス、表示されている場合をその最初の文字では、次の項目が強調表示します。

次の表に、次の 3 つのコンボ ボックス[スタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)します。

|スタイル|ときにリスト ボックスを表示|コントロールの種類|
|-----------|-------------------------------|-----------------------------|
|[シンプル]|Always|編集|
|Drop-down|にドロップされたとき|編集|
|ドロップダウン リスト|にドロップされたとき|スタティック|

作成することができます、`CComboBox`ダイアログ テンプレートのいずれかから、またはコードで直接オブジェクト。 どちらの場合も、コンス トラクターを呼び出す最初`CComboBox`を構築する、`CComboBox`オブジェクト; を呼び出して、[作成](#create)メンバー関数は、コントロールを作成し、アタッチ先、`CComboBox`オブジェクト。

コンボ ボックスからその親に送信される Windows 通知メッセージを処理する場合 (通常はから派生したクラス`CDialog`)、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。

各メッセージ マップ エントリは、次の形式をとります。

**ON\_**_通知_ **(** _id_、 _memberFxn_ **)**

場所`id`通知を送信するコンボ ボックス コントロールの子ウィンドウ ID を指定および`memberFxn`通知を処理するために記述した親メンバー関数の名前を指定します。

親の関数のプロトタイプは次のとおりです。

**afx_msg** `void` `memberFxn` **();**

特定の通知を送信する順序を予測することはできません。 具体的には前、にまたは後 CBN_CLOSEUP 通知 CBN_SELCHANGE 通知が発生する可能性があります。

潜在的なメッセージ マップ エントリ以下のとおりです。

- ON_CBN_CLOSEUP (Windows 3.1 以降)コンボ ボックスの一覧ボックスが閉じられます。 コンボ ボックスを持つはこの通知メッセージは送信されません、 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。

- ON_CBN_DBLCLK、ユーザーは、コンボ ボックスのリスト ボックス内の文字列をダブルクリックします。 この通知メッセージは、CBS_SIMPLE スタイルのコンボ ボックスにのみ送信されます。 使用してコンボ ボックス、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、ダブルクリックが発生することはできませんので、1 回のクリック、リスト ボックスを非表示にします。

- コンボ ボックスのリスト ボックスのドロップダウンは ON_CBN_DROPDOWN (表示するようにする)。 この通知メッセージは、CBS_DROPDOWN または CBS_DROPDOWNLIST スタイルのコンボ ボックスに対してのみ発生します。

- ON_CBN_EDITCHANGE、ユーザーは、アクションのコンボ ボックス編集コントロールの部分のテキストが変更される可能性がありますをしました。 CBN_EDITUPDATE メッセージとは異なり Windows 画面を更新した後、このメッセージが送信されます。 コンボ ボックスに CBS_DROPDOWNLIST スタイルが設定されている場合は送信されません。

- ON_CBN_EDITUPDATE テキスト表示の変更については、コンボ ボックスの編集コントロールの部分。 コントロールがテキストを書式設定後は、テキストを表示する前に、この通知メッセージが送信されます。 コンボ ボックスに CBS_DROPDOWNLIST スタイルが設定されている場合は送信されません。

- ON_CBN_ERRSPACE コンボ ボックスには、特定の要求を満たすために十分なメモリを割り当てることができません。

- ON_CBN_SELENDCANCEL (Windows 3.1 以降)ユーザーの選択を取り消す必要があることを示します。 ユーザーが項目をクリックし、別のウィンドウまたはコンボ ボックスのリスト ボックスを非表示にするコントロールをクリックします。 ユーザーの選択を無視することを示す CBN_CLOSEUP 通知メッセージの前に、この通知メッセージが送信されます。 (CBS_SIMPLE スタイルのコンボ ボックス) 場合に、CBN_CLOSEUP 通知メッセージが送信されなかった場合でも、CBN_SELENDCANCEL または CBN_SELENDOK 通知メッセージが送信されます。

- ON_CBN_SELENDOK、ユーザーが項目を選択し ENTER キーを押したかコンボ ボックスのリスト ボックスを非表示に下方向キーをクリックします。 示すこと、ユーザーの選択が有効と見なされる CBN_CLOSEUP メッセージの前に、この通知メッセージが送信されます。 (CBS_SIMPLE スタイルのコンボ ボックス) 場合に、CBN_CLOSEUP 通知メッセージが送信されなかった場合でも、CBN_SELENDCANCEL または CBN_SELENDOK 通知メッセージが送信されます。

- ON_CBN_KILLFOCUS コンボ ボックスには、入力フォーカスが失われています。

- ON_CBN_SELCHANGE コンボ ボックスの一覧ボックスの選択項目では、矢印キーを使用して選択を変更するか、リスト ボックス内をクリックすると、ユーザーの結果として変更される直前にします。 このメッセージを処理する際のコンボ ボックス編集コントロール内のテキストのみを取得できます`GetLBText`または別のような関数です。 `GetWindowText` 使用できません。

- ON_CBN_SETFOCUS コンボ ボックスでは、入力フォーカスを受け取ります。

作成する場合、 `CComboBox` (ダイアログ リソースの場合) を使ってダイアログ ボックス内のオブジェクト、 `CComboBox`  ダイアログ ボックスを閉じると、オブジェクトが自動的に破棄されます。

埋め込む場合、`CComboBox`別のウィンドウ内のオブジェクトがオブジェクトを破棄する必要はありません。 作成する場合、`CComboBox`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CComboBox`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を Windows のコンボ ボックスが破棄されるときに破棄するオブジェクト。

**注**コンボ ボックスの編集、リスト ボックス コントロールからクラスを派生サブクラスにある WM_KEYDOWN および WM_CHAR メッセージを処理する場合は、`CEdit`と`CListBox`、派生クラスにそれらのメッセージのハンドラーを追加します。 詳細については、次を参照してください。 [CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="addstring"></a>  Ccombobox:

コンボ ボックスのリスト ボックスに文字列を追加します。

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*lpszString*<br/>
追加するのには null で終わる文字列へのポインター。

### <a name="return-value"></a>戻り値

戻り値が 0 以上の場合は、リスト ボックス内の文字列の 0 から始まるインデックス。 エラーが発生した場合、戻り値は CB_ERR新しい文字列を格納する十分な空き領域がある場合は、CB_ERRSPACE を返します。

### <a name="remarks"></a>Remarks

リスト ボックスが作成されていない場合、 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、文字列はリストの末尾に追加されます。 それ以外の場合、一覧に、文字列が挿入され、リストの並べ替え。

> [!NOTE]
>  この関数は、Windows ではサポートされていない`ComboBoxEx`コントロール。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](/windows/desktop/Controls/comboboxex-controls)Windows SDK に含まれています。

リスト内の特定の場所には、文字列を挿入するには、使用、 [InsertString](#insertstring)メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

##  <a name="ccombobox"></a>  CComboBox::CComboBox

`CComboBox` オブジェクトを構築します。

```
CComboBox();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

##  <a name="clear"></a>  CComboBox::Clear

削除 (クリア) 現在の選択、コンボ ボックスの編集コントロールに存在する場合。

```
void Clear();
```

### <a name="remarks"></a>Remarks

現在の選択範囲を削除し、削除された内容をクリップボードに配置、使用、[切り取り](#cut)メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

##  <a name="compareitem"></a>  CComboBox::CompareItem

並べ替えられたオーナー描画コンボ ボックスの一覧ボックスの部分で新しい項目の相対位置を決定するためにフレームワークによって呼び出されます。

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpCompareItemStruct*<br/>
Long ポインター、 [COMPAREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcompareitemstruct)構造体。

### <a name="return-value"></a>戻り値

説明されている 2 つの項目の相対位置を示す、`COMPAREITEMSTRUCT`構造体。 次の値のいずれかを指定できます。

|[値]|説明|
|-----------|-------------|
|- 1|項目 1 は、項目 2 の前に並べ替えます。|
|0|アイテム 1 とアイテム 2 は、同じを並べ替えます。|
|1|項目 1 は、項目 2 の後に並べ替えられます。|

参照してください[CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)の説明については`COMPAREITEMSTRUCT`します。

### <a name="remarks"></a>Remarks

既定では、このメンバー関数は何もしません。 LBS_SORT スタイルとオーナー描画のコンボ ボックスを作成する場合は、リスト ボックスに追加された新しい項目の並べ替えでフレームワークを支援するためにこのメンバー関数をオーバーライドする必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

##  <a name="copy"></a>  CComboBox::Copy

コンボ ボックスの上にされているテキスト形式でクリップボードのエディット コントロールである場合は、現在の選択範囲をコピーします。

```
void Copy();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

##  <a name="create"></a>  CComboBox::Create

コンボ ボックスを作成し、それにアタッチします、`CComboBox`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
コンボ ボックスのスタイルを指定します。 任意の組み合わせを適用[コンボ ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)します。

*rect*<br/>
コンボ ボックスのサイズと位置を指します。 [RECT 構造体](/windows/desktop/api/windef/ns-windef-tagrect)または`CRect`オブジェクト。

*pParentWnd*<br/>
コンボ ボックスの親ウィンドウを指定します (通常、 `CDialog`)。 NULL は指定できません。

*nID*<br/>
コンボ ボックスのコントロール ID を指定します

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

構築する、 `CComboBox` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出して`Create`、Windows のコンボ ボックスを作成しにアタッチする`CComboBox`オブジェクト。

ときに`Create`実行されると、Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)コンボ ボックスにメッセージです。

既定でこれらのメッセージが処理されます、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数`CWnd`基本クラス。 既定のメッセージ処理を拡張するには、派生クラスを`CComboBox`メッセージ マップを新しいクラスに追加し、前のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`、たとえば、新しいクラスに必要な初期化を実行します。

次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)コンボ ボックス コントロールにします。 :

- WS_CHILD 常に

- WS_VISIBLE 通常

- WS_DISABLED ことはほとんどありません。

- WS_VSCROLL をコンボ ボックスで、リスト ボックスに垂直スクロール機能を追加します。

- WS_HSCROLL を追加、リスト ボックス、コンボ ボックスで水平方向にスクロール

- WS_GROUP コントロールをグループ化

- WS_TABSTOP するには、タブ オーダーにコンボ ボックスを含める

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

##  <a name="cut"></a>  CComboBox::Cut

削除 (切り取り) 現在の選択、コンボ ボックスで編集している場合は、制御し、されているテキスト形式で、削除されたテキストをクリップボードにコピーします。

```
void Cut();
```

### <a name="remarks"></a>Remarks

を、削除されたテキストをクリップボードに配置することがなく現在の選択範囲を削除する、[クリア](#clear)メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

##  <a name="deleteitem"></a>  CComboBox::DeleteItem

ユーザーがオーナー描画から項目を削除するときに、フレームワークによって呼び出されます`CComboBox`オブジェクトまたはコンボ ボックスを破棄します。

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDeleteItemStruct*<br/>
Windows への long ポインター [DELETEITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdeleteitemstruct)削除された項目に関する情報を含む構造体。 参照してください[構造体](../../mfc/reference/cwnd-class.md#ondeleteitem)この構造体の説明についてはします。

### <a name="remarks"></a>Remarks

この関数の既定の実装は、何も行いません。 必要に応じて、コンボ ボックスを描画するには、この関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

##  <a name="deletestring"></a>  オーナー

位置に項目を削除します*nIndex*コンボ ボックスから。

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
インデックスを削除するのには、文字列を指定します。

### <a name="return-value"></a>戻り値

戻り値が 0 以上の場合は、一覧に残っている文字列の数が、します。 場合、戻り値は CB_ERR *nIndex*一覧の項目の数より大きいインデックスを指定します。

### <a name="remarks"></a>Remarks

次のすべての項目*nIndex*現在位置を 1 つ下へ移動します。 たとえば、コンボ ボックスに 2 つの項目が含まれている場合の最初の項目を削除によりを今すぐ最初の位置で残りの項目。 *nIndex*の最初の位置の項目の 0 を = です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

##  <a name="dir"></a>  CComboBox::Dir

コンボ ボックスのリスト ボックスに、またはドライブ名の一覧を追加します。

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>パラメーター

*attr*<br/>
任意の組み合わせにすることができます、 **enum**で説明されている値[cfile::getstatus](../../mfc/reference/cfile-class.md#getstatus)または、次の値の任意の組み合わせ。

- DDL_READWRITE ファイルの読み取りし、書き込むことができます。

- DDL_READONLY ファイルから読み取ることができますには書き込まれません。

- DDL_HIDDEN ファイルを非表示にし、ディレクトリの一覧に表示されません。

- DDL_SYSTEM ファイルは、システム ファイルです。

- DDL_DIRECTORY で指定された名前*lpszWildCard*ディレクトリを指定します。

- DDL_ARCHIVE ファイルがアーカイブされています。

- 指定された名前と一致するすべてのドライブは含まれません含んだ*lpszWildCard*します。

- DDL_EXCLUSIVE 排他フラグ。 排他のフラグを設定すると、指定した種類のファイルのみが一覧表示されます。 それ以外の場合、「通常」のファイルだけでなく、指定した型のファイルが一覧表示されます。

*lpszWildCard*<br/>
ファイルの仕様の文字列を指します。 文字列にワイルドカードを含めることができます (たとえば、*.\*)。

### <a name="return-value"></a>戻り値

戻り値が 0 以上の場合は、最後に、リストに追加されたファイル名の 0 から始まるインデックス。 エラーが発生した場合、戻り値は CB_ERR新しい文字列を保存する十分な空き領域がある場合は、CB_ERRSPACE を返します。

### <a name="remarks"></a>Remarks

この関数は、Windows ではサポートされていない`ComboBoxEx`コントロール。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](/windows/desktop/Controls/comboboxex-controls)Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

##  <a name="drawitem"></a>  CComboBox::DrawItem

ビジュアルな部分のオーナー描画コンボ ボックスが変更されたときにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
ポインターを[DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)のために必要な図面の種類に関する情報を含む構造体。

### <a name="remarks"></a>Remarks

`itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行する描画の動作を定義します。 参照してください[体](../../mfc/reference/cwnd-class.md#ondrawitem)この構造体の説明についてはします。

既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CComboBox`オブジェクト。 このメンバー関数が終了する前に、アプリケーションがで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

##  <a name="findstring"></a>  Ccombobox::findstring

検出されるしますが、コンボ ボックスの一覧ボックスで指定したプレフィックスを含む最初の文字列を選択しません。

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>パラメーター

*nStartAfter*<br/>
最初の項目を検索する前にある項目の 0 から始まるインデックスが含まれています。 指定された項目に、リスト ボックスの上部から続行、検索では、リスト ボックスの下部に達すると、 *nStartAfter*します。 -1 の場合、最初からリスト ボックス全体が検索されます。

*lpszString*<br/>
検索対象のプレフィックスを含む null で終わる文字列へのポインター。 検索では独立しており、ケースを指定するため、この文字列は、任意の大文字と小文字を含めることができます。

### <a name="return-value"></a>戻り値

戻り値が 0 以上の場合は、一致する項目の 0 から始まるインデックス。 検索が成功した場合は、CB_ERR を勧めします。

### <a name="remarks"></a>Remarks

この関数は、Windows ではサポートされていない`ComboBoxEx`コントロール。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](/windows/desktop/Controls/comboboxex-controls)Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

##  <a name="findstringexact"></a>  CComboBox::FindStringExact

呼び出す、`FindStringExact`メンバー関数は、最初リスト ボックスで指定された文字列と一致する文字列 (コンボ ボックス内を検索する*されて*します。

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>パラメーター

*nIndexStart*<br/>
最初の項目を検索する前にある項目の 0 から始まるインデックスを指定します。 指定された項目に、リスト ボックスの上部から続行、検索では、リスト ボックスの下部に達すると、 *nIndexStart*します。 場合*nIndexStart* -1 で、最初からリスト ボックス全体が検索されます。

*中から*<br/>
検索する null で終わる文字列へのポインター。 この文字列は、拡張子を含む、完全なファイル名を含めることができます。 検索は大文字小文字が区別はないため、この文字列は、任意の大文字と小文字を含めることができます。

### <a name="return-value"></a>戻り値

CB_ERR 検索が成功した場合、一致する項目の 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

コンボ ボックスがオーナー描画スタイルで作成された場合、 [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、`FindStringExact`ダブルワード値、値との比較を照合しようと*されて*します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

##  <a name="getcomboboxinfo"></a>  CComboBox::GetComboBoxInfo

情報を取得、`CComboBox`オブジェクト。

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>パラメーター

*pcbi*<br/>
ポインター、 [COMBOBOXINFO](/windows/desktop/api/winuser/ns-winuser-tagcomboboxinfo)構造体。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

このメンバー関数の機能をエミュレートする、 [CB_GETCOMBOBOXINFO](/windows/desktop/Controls/cb-getcomboboxinfo)メッセージ、Windows SDK で説明されているとします。

##  <a name="getcount"></a>  CComboBox::GetCount

コンボ ボックスの一覧ボックスの部分で項目の数を取得するには、このメンバー関数を呼び出します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

項目の数。 返されるカウントは、1 (インデックスは 0 から始まる) の最後の項目のインデックス値よりも大きいです。 エラーが発生した場合は、CB_ERR を勧めします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

##  <a name="getcuebanner"></a>  CComboBox::GetCueBanner

コンボ ボックス コントロールに表示されるヒントのテキストを取得します。

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpszText*|[out]キュー バナー テキストを受け取るバッファーへのポインター。|
|*cchText*|[in]バッファーのサイズを*lpszText*パラメーターを指します。|

### <a name="return-value"></a>戻り値

最初のオーバー ロードで、 [CString](../../atl-mfc-shared/using-cstring.md)オブジェクトが存在する場合は、キュー バナー テキストを格納するそれ以外の場合、`CString`長さ 0 のオブジェクト。

- または -

2 番目のオーバー ロードでは、このメソッドが成功した場合は TRUE します。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ヒントのテキストは、コンボ ボックス コントロールの入力領域に表示されるプロンプトです。 ユーザーが入力されるまで、ヒントのテキストが表示されます。

このメソッドは、送信、 [CB_GETCUEBANNER](/windows/desktop/Controls/cb-getcuebanner)メッセージは、Windows SDK で説明します。

##  <a name="getcursel"></a>  CComboBox::GetCurSel

コンボ ボックス内のどのアイテムが選択されているかを判断するには、このメンバー関数を呼び出します。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックス、または CB_ERR 項目が選択されていない場合のリスト ボックスで現在選択されている項目の 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

`GetCurSel` リストにインデックスを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

##  <a name="getdroppedcontrolrect"></a>  CComboBox::GetDroppedControlRect

呼び出す、`GetDroppedControlRect`ドロップダウン コンボ ボックスの表示 (ドロップダウン) リスト ボックスの画面座標を取得します。

```
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>パラメーター

*lprect*<br/>
指す、 [RECT 構造体](/windows/desktop/api/windef/ns-windef-tagrect)座標を受信します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

##  <a name="getdroppedstate"></a>  CComboBox::GetDroppedState

呼び出す、`GetDroppedState`かどうか、リスト ボックスのドロップダウン コンボ ボックスを表示 (ドロップダウン) を調べます。

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>戻り値

リスト ボックスを表示する場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

##  <a name="getdroppedwidth"></a>  CComboBox::GetDroppedWidth

コンボ ボックスのリスト ボックスのピクセル単位では、最小許容幅を取得するには、この関数を呼び出します。

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>戻り値

成功した場合、最小許容される幅 (ピクセル単位)。それ以外の場合、返します。

### <a name="remarks"></a>Remarks

この関数は、コンボ ボックスにのみ適用されます、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。

既定では、ドロップダウン リスト ボックスの許容される最小の幅は 0 です。 許容される最小の幅を呼び出すことによって設定できる[SetDroppedWidth](#setdroppedwidth)します。 コンボ ボックスの一覧ボックスの部分が表示されるときに、幅が許容される最小の幅またはコンボ ボックスの幅のうち、大きい方。

### <a name="example"></a>例

  例をご覧ください[SetDroppedWidth](#setdroppedwidth)します。

##  <a name="geteditsel"></a>  CComboBox::GetEditSel

コンボ ボックスの編集コントロールに現在の選択範囲の開始と終了文字位置を取得します。

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>戻り値

下位ワード内の開始位置と選択されていない最初の文字の位置を含む上位の単語の選択範囲の終了後に 32 ビット値。 コンボ ボックス編集コントロールなしでこの関数を使用する場合は、CB_ERR が返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

##  <a name="getextendedui"></a>  CComboBox::GetExtendedUI

呼び出す、`GetExtendedUI`コンボ ボックスが既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスであるかどうかを調べます。

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックスに、拡張ユーザー インターフェイスがある場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

拡張ユーザー インターフェイスは、次の方法で識別できます。

- 静的コントロールをクリックすると、コンボ ボックスの場合のみ、リスト ボックスを表示、 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。

- 下方向キーを押すと、(f4 キーは無効です)、リスト ボックスが表示されます。

項目リストが表示される (矢印キーが無効になっている) 場合に、静的コントロールでのスクロールは無効になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

##  <a name="gethorizontalextent"></a>  CComboBox::GetHorizontalExtent

コンボ ボックスから、これによって、コンボ ボックスの一覧ボックスの部分を水平方向にスクロールすることができます (ピクセル単位) の幅を取得します。

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>戻り値

スクロール可能な (ピクセル単位)、コンボ ボックスの一覧ボックス部分の幅。

### <a name="remarks"></a>Remarks

これは、コンボ ボックスの一覧ボックスの部分に水平スクロール バーがある場合にのみ当てはまります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

##  <a name="getitemdata"></a>  CComboBox::GetItemData

指定されたコンボ ボックス アイテムに関連付けられたアプリケーションによって提供される 32 ビット値を取得します。

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
コンボ ボックスのリスト ボックス内の項目の 0 から始まるインデックスが含まれています。

### <a name="return-value"></a>戻り値

エラーが発生した場合は、項目、または CB_ERR に関連付けられている 32 ビット値。

### <a name="remarks"></a>Remarks

32 ビット値を設定することができます、 *dwItemData*のパラメーターを[SetItemData](#setitemdata)メンバー関数の呼び出し。 使用して、`GetItemDataPtr`メンバー関数を取得する 32 ビット値がポインターの場合 (**void** <strong>\*</strong>)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

##  <a name="getitemdataptr"></a>  CComboBox::GetItemDataPtr

ポインターとして指定されたコンボ ボックス アイテムに関連付けられたアプリケーションによって提供される 32 ビット値を取得します (**void** <strong>\*</strong>)。

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
コンボ ボックスのリスト ボックス内の項目の 0 から始まるインデックスが含まれています。

### <a name="return-value"></a>戻り値

エラーが発生した場合は、ポインター、または-1 を取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

##  <a name="getitemheight"></a>  CComboBox::GetItemHeight

呼び出す、`GetItemHeight`コンボ ボックスのリスト項目の高さを取得します。

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
高さを取得するが、コンボ ボックスのコンポーネントを指定します。 場合、 *nIndex*パラメーターが-1、コンボ ボックスの編集コントロール (または静的なテキスト) の部分の高さを取得します。 コンボ ボックスがある場合、 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、 *nIndex*の高さを取得するリスト アイテムの 0 から始まるインデックスを指定します。 それ以外の場合、 *nIndex*を 0 に設定する必要があります。

### <a name="return-value"></a>戻り値

コンボ ボックスで指定した項目のピクセル単位の高さ。 エラーが発生した場合は、CB_ERR を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

##  <a name="getlbtext"></a>  CComboBox::GetLBText

コンボ ボックスのリスト ボックスから文字列を取得します。

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
コピーするリスト ボックスの文字列の 0 から始まるインデックスが含まれています。

*lpszText*<br/>
文字列を受け取るバッファーへのポインター。 バッファーには、文字列と終端の null 文字に対して十分な領域が必要です。

*rString*<br/>
参照、`CString`します。

### <a name="return-value"></a>戻り値

終端の null 文字を除く、文字列の長さをバイト単位で。 場合*nIndex*有効なインデックスで指定されていない戻り値は、返します。

### <a name="remarks"></a>Remarks

このメンバーの 2 番目の形式の関数の塗りつぶしを`CString`項目のテキストを持つオブジェクト。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

##  <a name="getlbtextlen"></a>  CComboBox::GetLBTextLen

コンボ ボックスの一覧ボックスで、文字列の長さを取得します。

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックスの文字列の 0 から始まるインデックスが含まれています。

### <a name="return-value"></a>戻り値

(バイト)、終端の null 文字を除く、文字列の長さ。 場合*nIndex*有効なインデックスで指定されていない戻り値は、返します。

### <a name="example"></a>例

  例をご覧ください[CComboBox::GetLBText](#getlbtext)します。

##  <a name="getlocale"></a>  CComboBox::GetLocale

コンボ ボックスによって使用されるロケールを取得します。

```
LCID GetLocale() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックス内の文字列のロケール識別子 (LCID) 値。

### <a name="remarks"></a>Remarks

ロケールが使用、たとえば、並べ替えられたコンボ ボックス内の文字列の並べ替え順序を決定します。

### <a name="example"></a>例

  例をご覧ください[CComboBox::SetLocale](#setlocale)します。

##  <a name="getminvisible"></a>  CComboBox::GetMinVisible

現在のコンボ ボックス コントロールのドロップダウン リストで表示される項目の最小数を取得します。

```
int GetMinVisible() const;
```

### <a name="return-value"></a>戻り値

現在のドロップダウン リストに表示される項目の最小数。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [CB_GETMINVISIBLE](/windows/desktop/Controls/cb-setminvisible)メッセージは、Windows SDK で説明します。

##  <a name="gettopindex"></a>  CComboBox::GetTopIndex

コンボ ボックスの一覧ボックス部分に表示される最初の項目の 0 から始まるインデックスを取得します。

```
int GetTopIndex() const;
```

### <a name="return-value"></a>戻り値

成功した場合、コンボ ボックスの一覧ボックス部分に表示される最初の項目の 0 から始まるインデックス返します。

### <a name="remarks"></a>Remarks

最初に、項目 0 は、リスト ボックスの上部にあるが上部にある別の項目があります、リスト ボックスがスクロール可能な場合。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

##  <a name="initstorage"></a>  CComboBox::InitStorage

コンボ ボックスの一覧ボックスの部分でリスト ボックス項目を格納するためにメモリを割り当てます。

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

成功すると、メモリを再割り当てする前に、コンボ ボックスの一覧ボックスの部分を格納できる項目の最大数が必要に応じて、それ以外の場合 CB_ERRSPACE、十分なメモリが使用可能な意味ありません。

### <a name="remarks"></a>Remarks

多数のアイテムをリスト ボックスの部分に追加する前にこの関数を呼び出し、`CComboBox`します。

Windows 95/98 のみ:*WParam*パラメーターは 16 ビット値に制限されます。 つまり、リスト ボックスは、32,767 を超える項目を含めることはできません。 項目の数が制限されているが、リスト ボックス内の項目の合計サイズは、使用可能なメモリによってのみ制限されます。

この関数は、高速化する多数のアイテム (100 個以上) を持つリスト ボックスの初期化を使用します。 したがって後続のメモリ量の指定が事前に割り当てる[AddString](#addstring)、 [InsertString](#insertstring)、および[Dir](#dir)関数は、最短時間を取得します。 見積もりは、パラメーターを使用できます。 多くを指定した場合は、余分なメモリが割り当てられます。過小を評価する場合、通常の割り当てを事前に割り当てられる量を超える項目に対して使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

##  <a name="insertstring"></a>  CComboBox::InsertString

コンボ ボックスのリスト ボックスに文字列を挿入します。

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
文字列を受け取るリスト ボックス内の位置を示す 0 から始まるインデックスです。 このパラメーターが-1 の場合、文字列はリストの末尾に追加されます。

*lpszString*<br/>
挿入される null で終わる文字列を指します。

### <a name="return-value"></a>戻り値

文字列が挿入された位置の 0 から始まるインデックス。 エラーが発生した場合は、CB_ERR を返します。 新しい文字列を格納する十分な空き領域がある場合は、CB_ERRSPACE を返します。

### <a name="remarks"></a>Remarks

[AddString](#addstring) メンバー関数とは異なり、 `InsertString` メンバー関数では、 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) スタイルのリストが並べ替えられることはありません。

> [!NOTE]
>  この関数は、Windows ではサポートされていない`ComboBoxEx`コントロール。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](/windows/desktop/Controls/comboboxex-controls)Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

##  <a name="limittext"></a>  CComboBox::LimitText

ユーザーがコンボ ボックスの編集コントロールに入力できるテキストの長さ (バイト単位) を制限します。

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>パラメーター

*nMaxChars*<br/>
ユーザーが入力できるテキストの長さ (バイト) を指定します。 このパラメーターが 0 の場合は、テキストの長さが 65,535 バイトに設定されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値。 スタイルのコンボ ボックスに対して呼び出された場合[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)コンボ ボックス編集コントロールなしには、戻り値は CB_ERR またはします。

### <a name="remarks"></a>Remarks

コンボ ボックス スタイルを持たない場合[CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)、テキスト制限 エディット コントロールのサイズより大きくするのには影響しません。

`LimitText` ユーザーが入力できるテキストのみを制限します。 影響を与えません任意のテキストで既に編集コントロールにリスト ボックス内の文字列が選択されているときに、編集コントロールにコピーするテキストの長さに影響は、メッセージを送信するとき。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

##  <a name="measureitem"></a>  CComboBox::MeasureItem

オーナー描画スタイルでコンボ ボックスが作成されるときに、フレームワークによって呼び出されます。

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpMeasureItemStruct*<br/>
Long ポインター、 [MEASUREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagmeasureitemstruct)構造体。

### <a name="remarks"></a>Remarks

既定では、このメンバー関数は何もしません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`コンボ ボックスの一覧の各次元の Windows のボックスに通知する構造体。 コンボ ボックスが作成された場合、 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)リスト ボックス内の各項目のスタイル、フレームワークの呼び出し、このメンバー関数。 それ以外の場合、このメンバーは、1 回だけ呼び出されます。

CBS_OWNERDRAWFIXED スタイルを使用して、オーナー描画のコンボ ボックス内で作成された、 [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem)のメンバー関数`CWnd`さらにプログラミングの考慮事項が含まれます。 説明を参照[テクニカル ノート 14: カスタム](../../mfc/tn014-custom-controls.md)します。

参照してください[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)の説明については、`MEASUREITEMSTRUCT`構造体。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

##  <a name="paste"></a>  CComboBox::Paste

現在のカーソル位置にあるコンボ ボックス編集コントロールに、クリップボードからデータを挿入します。

```
void Paste();
```

### <a name="remarks"></a>Remarks

クリップボードにされているテキスト形式のデータが含まれている場合にのみデータが挿入されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

##  <a name="resetcontent"></a>  CComboBox::ResetContent

一覧からすべての項目のボックスし、コンボ ボックスのコントロールの編集を削除します。

```
void ResetContent();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

##  <a name="selectstring"></a>  CComboBox::SelectString

コンボ ボックスのリスト ボックス内の文字列を検索し、文字列が見つかった場合、リスト ボックスで、文字列を選択し、編集コントロールにコピーします。

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*nStartAfter*<br/>
最初の項目を検索する前にある項目の 0 から始まるインデックスが含まれています。 指定された項目に、リスト ボックスの上部から続行、検索では、リスト ボックスの下部に達すると、 *nStartAfter*します。 -1 の場合、最初からリスト ボックス全体が検索されます。

*lpszString*<br/>
検索対象のプレフィックスを含む null で終わる文字列へのポインター。 検索では独立しており、ケースを指定するため、この文字列は、任意の大文字と小文字を含めることができます。

### <a name="return-value"></a>戻り値

文字列が見つかった場合は、選択した項目の 0 から始まるインデックス。 検索が成功した場合、戻り値は CB_ERR と現在の選択は変更されません。

### <a name="remarks"></a>Remarks

文字列の先頭の文字 (始点) からのプレフィックス文字列内の文字を一致する場合にのみが選択されます。

なお、`SelectString`と`FindString`メンバー関数、文字列を検索するが、`SelectString`メンバー関数は、文字列も選択します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

##  <a name="setcuebanner"></a>  CComboBox::SetCueBanner

コンボ ボックス コントロールに表示されるヒントのテキストを設定します。

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpszText*|[in]ヒントのテキストを含む null で終わるバッファーへのポインター。|

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ヒントのテキストは、コンボ ボックス コントロールの入力領域に表示されるプロンプトです。 ユーザーが入力されるまで、ヒントのテキストが表示されます。

このメソッドは、送信、 [CB_SETCUEBANNER](/windows/desktop/Controls/cb-setcuebanner)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 *m_combobox*、つまり、コンボ ボックス コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>例

次のコード例では、コンボ ボックス コントロールのキュー バナーを設定します。

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="setcursel"></a>  CComboBox::SetCurSel

コンボ ボックスのリスト ボックスに文字列を選択します。

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>パラメーター

*nSelect*<br/>
選択する文字列の 0 から始まるインデックスを指定します。 -1 の場合は、リスト ボックスの現在の選択項目が削除され、編集コントロールがクリアされます。

### <a name="return-value"></a>戻り値

メッセージが成功した場合に選択した項目の 0 から始まるインデックス。 場合、戻り値は CB_ERR *nSelect*がリスト内の項目の数よりも大きい場合、または*nSelect*が-1 で、選択を解除に設定します。

### <a name="remarks"></a>Remarks

必要に応じて、リスト ボックスは (リスト ボックスが表示されている場合)、ビューに、文字列をスクロールします。 コンボ ボックスの編集コントロール内のテキストが新しい選択を反映するように変更します。 リスト ボックスの前の選択項目が削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

##  <a name="setdroppedwidth"></a>  CComboBox::SetDroppedWidth

コンボ ボックスのリスト ボックスのピクセル単位で設定できる最小幅を設定するには、この関数を呼び出します。

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
ピクセル単位で、コンボ ボックスの一覧ボックス部分の許容される最小幅。

### <a name="return-value"></a>戻り値

成功した場合、リスト ボックス、それ以外の場合 CB_ERR の新しい幅。

### <a name="remarks"></a>Remarks

この関数は、コンボ ボックスにのみ適用されます、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。

既定では、ドロップダウン リスト ボックスの許容される最小の幅は 0 です。 コンボ ボックスの一覧ボックスの部分が表示されるときに、幅が許容される最小の幅またはコンボ ボックスの幅のうち、大きい方。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

##  <a name="seteditsel"></a>  CComboBox::SetEditSel

コンボ ボックスの編集コントロール内の文字を選択します。

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>パラメーター

*nStartChar*<br/>
開始位置を指定します。 開始位置が-1 に設定されている場合は既存の選択項目が削除されます。

*nEndChar*<br/>
終了位置を指定します。 終了位置が最後の開始位置からのすべてのテキスト、-1 に設定されている場合、編集コントロール内の文字が選択されます。

### <a name="return-value"></a>戻り値

メンバー関数が成功した場合、0 以外の場合それ以外の場合 0 を返します。 場合は CB_ERR`CComboBox`が、 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)のスタイル設定やリスト ボックスではありません。

### <a name="remarks"></a>Remarks

位置は、0 から始まる。 編集コントロールの最初の文字を選択するには、0 の開始位置を指定します。 終了位置は、選択する最後の文字の直後後の文字。 たとえば、エディット コントロールの最初の 4 つの文字を選択する 0 の開始位置と終了位置に 4 を使用しては。

> [!NOTE]
>  この関数は、Windows ではサポートされていない`ComboBoxEx`コントロール。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](/windows/desktop/Controls/comboboxex-controls)Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CComboBox::GetEditSel](#geteditsel)します。

##  <a name="setextendedui"></a>  CComboBox::SetExtendedUI

呼び出す、`SetExtendedUI`メンバー関数は、既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスを持つコンボ ボックスの選択、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>パラメーター

*bExtended*<br/>
コンボ ボックスで、拡張ユーザー インターフェイスまたは既定のユーザー インターフェイスを使用する必要があるかどうかを指定します。 TRUE の値は、拡張ユーザー インターフェイスを選択します。FALSE の値は、標準のユーザー インターフェイスを選択します。

### <a name="return-value"></a>戻り値

操作が成功した場合、正常または CB_ERR エラーが発生した場合。

### <a name="remarks"></a>Remarks

拡張ユーザー インターフェイスは、次の方法で識別できます。

- 静的コントロールをクリックすると、CBS_DROPDOWNLIST スタイル コンボ ボックスの場合のみ、リスト ボックスが表示されます。

- 下方向キーを押すと、(f4 キーは無効です)、リスト ボックスが表示されます。

項目の一覧が表示されていないときに、スタティック コントロールのスクロールを無効 (方向キーが無効になります)。

### <a name="example"></a>例

  例をご覧ください[CComboBox::GetExtendedUI](#getextendedui)します。

##  <a name="sethorizontalextent"></a>  CComboBox::SetHorizontalExtent

これによって、コンボ ボックスの一覧ボックスの部分を水平方向にスクロールすることができます (ピクセル単位)、幅を設定します。

```
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>パラメーター

*nExtent*<br/>
これによって、コンボ ボックスの一覧ボックスの部分を水平方向にスクロールすることができますのピクセル数を指定します。

### <a name="remarks"></a>Remarks

リスト ボックスの幅がこの値よりも小さい場合は、水平スクロール バーはリスト ボックス内の項目を横方向にスクロールします。 水平スクロール バーが非表示になってリスト ボックスの幅がこの値以上の場合、または、コンボ ボックスがある場合、 [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを無効になっています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

##  <a name="setitemdata"></a>  CComboBox::SetItemData

コンボ ボックスで指定した項目に関連付けられている 32 ビット値を設定します。

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
設定する項目の 0 から始まるインデックスが含まれています。

*dwItemData*<br/>
項目に関連付ける新しい値が含まれています。

### <a name="return-value"></a>戻り値

エラーが発生した場合を返します。

### <a name="remarks"></a>Remarks

使用して、`SetItemDataPtr`メンバー関数は 32 ビットの項目のポインターである場合。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

##  <a name="setitemdataptr"></a>  CComboBox::SetItemDataPtr

指定したポインターのコンボ ボックス内の指定した項目に関連付けられている 32 ビット値の設定 (**void** <strong>\*</strong>)。

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の 0 から始まるインデックスが含まれています。

*pData*<br/>
項目に関連付けるへのポインターが含まれています。

### <a name="return-value"></a>戻り値

エラーが発生した場合を返します。

### <a name="remarks"></a>Remarks

このポインターは項目の追加または削除コンボ ボックス内の項目の相対位置を変更する可能性がありますが、コンボ ボックスの有効期間有効です。 そのため、ボックス内の項目のインデックスを変更できますが、ポインターが信頼性の高いは残ります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

##  <a name="setitemheight"></a>  CComboBox::SetItemHeight

呼び出す、`SetItemHeight`コンボ ボックスまたはコンボ ボックスの編集コントロール (または静的なテキスト) の部分の高さにリスト項目の高さを設定するメンバー関数。

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト項目の高さまたはコンボ ボックスの編集コントロール (または静的なテキスト) の部分の高さが設定されているかどうかを指定します。

コンボ ボックスがある場合、 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、 *nIndex*設定それ以外を高さがリスト項目の 0 から始まるインデックスを指定します*nIndex* 0 にする必要があります。なり、すべてのリスト アイテムの高さが設定されます。

場合*nIndex* -1 で、編集コントロールの高さまたはコンボ ボックスの静的なテキスト部分が設定されます。

*cyItemHeight*<br/>
高さを指定します (ピクセル単位) で識別されるコンボ ボックス コンポーネントの*nIndex*します。

### <a name="return-value"></a>戻り値

CB_ERR インデックスまたは高さが無効である場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

コンボ ボックスの編集コントロール (または静的なテキスト) の部分の高さは、リスト項目の高さとは無関係に設定されます。 アプリケーションは、編集コントロール (または静的なテキスト) の部分の高さは、特定のリスト ボックス項目の高さよりも小さくしない必要がありますを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

##  <a name="setlocale"></a>  CComboBox::SetLocale

このコンボ ボックスのロケール識別子を設定します。

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>パラメーター

*nNewLocale*<br/>
コンボ ボックスに設定する新しい値のロケール識別子 (LCID)。

### <a name="return-value"></a>戻り値

このコンボ ボックスの以前のロケール識別子 (LCID) 値。

### <a name="remarks"></a>Remarks

場合`SetLocale`を呼び出さない、既定のロケールがシステムから取得します。 コントロール パネル を使用して、この既定のシステム ロケールを変更できる地域 (または国際) アプリケーションです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

##  <a name="setminvisibleitems"></a>  CComboBox::SetMinVisibleItems

現在のコンボ ボックスの一覧ボックス コントロールで表示される項目の最小数を設定します。

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*iMinVisible*|[in]表示される項目の最小数を指定します。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [CB_SETMINVISIBLE](/windows/desktop/Controls/cb-setminvisible)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 *m_combobox*、つまり、コンボ ボックス コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>例

次のコード例では、コンボ ボックス コントロールのドロップダウン リストに 20 個の項目を挿入します。 ドロップダウン矢印を押すと最低 10 個の項目が表示されることを指定します。

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

##  <a name="settopindex"></a>  CComboBox::SetTopIndex

により、特定のアイテムがコンボ ボックスの一覧ボックスの部分に表示されます。

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

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

##  <a name="showdropdown"></a>  CComboBox::ShowDropDown

表示またはを含むコンボ ボックスのリスト ボックスを非表示、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。

```
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>パラメーター

*bShowIt*<br/>
ドロップダウン リスト ボックスを表示/非表示かどうかを指定します。 TRUE の値は、リスト ボックスを表示します。 FALSE の値には、リスト ボックスが非表示にします。

### <a name="remarks"></a>Remarks

既定では、このスタイルのコンボ ボックスは、リスト ボックスに表示されます。

このメンバー関数はで作成されたコンボ ボックスに影響を与えません、 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。

### <a name="example"></a>例

  例をご覧ください[CComboBox::GetDroppedState](#getdroppedstate)します。

## <a name="see-also"></a>関連項目

[MFC サンプル CTRLBARS](../../visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic クラス](../../mfc/reference/cstatic-class.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)
