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
ms.openlocfilehash: 4e7eba94084a96c833136e4c92de481fdc435c7e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87183111"
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
|[CComboBox:: CComboBox](#ccombobox)|`CComboBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComboBox::AddString](#addstring)|コンボボックスのリストボックス内のリストの末尾に文字列を追加するか、CBS_SORT スタイルを持つリストボックスの並べ替えられた位置に追加します。|
|[CComboBox:: Clear](#clear)|エディットコントロール内の現在の選択項目 (存在する場合) を削除 (クリア) します。|
|[CComboBox:: CompareItem](#compareitem)|並べ替えられたオーナー描画コンボボックス内の新しいリスト項目の相対位置を決定するために、フレームワークによって呼び出されます。|
|[CComboBox:: コピー](#copy)|現在の選択内容 (存在する場合) を CF_TEXT 形式でクリップボードにコピーします。|
|[CComboBox:: Create](#create)|コンボボックスを作成し、オブジェクトにアタッチし `CComboBox` ます。|
|[CComboBox:: Cut](#cut)|エディットコントロール内の現在の選択項目を削除 (切り取り) し、削除されたテキストを CF_TEXT 形式でクリップボードにコピーします。|
|[CComboBox::D eleteItem](#deleteitem)|オーナー描画コンボボックスからリスト項目が削除されたときに、フレームワークによって呼び出されます。|
|[CComboBox::D eleteString](#deletestring)|コンボボックスのリストボックスから文字列を削除します。|
|[CComboBox::D ir](#dir)|コンボボックスのリストボックスにファイル名のリストを追加します。|
|[CComboBox: rawItem:D](#drawitem)|オーナー描画コンボボックスの外観が変化したときにフレームワークによって呼び出されます。|
|[CComboBox:: FindString](#findstring)|コンボボックスのリストボックス内の指定したプレフィックスを含む最初の文字列を検索します。|
|[CComboBox:: FindStringExact](#findstringexact)|指定した文字列と一致する最初のリストボックスの文字列 (コンボボックス内) を検索します。|
|[CComboBox:: GetComboBoxInfo](#getcomboboxinfo)|オブジェクトに関する情報を取得 `CComboBox` します。|
|[CComboBox:: GetCount](#getcount)|コンボボックスのリストボックス内の項目の数を取得します。|
|[CComboBox:: GetCueBanner](#getcuebanner)|コンボボックスコントロールに表示されるキューテキストを取得します。|
|[CComboBox:: GetCurSel](#getcursel)|コンボボックスのリストボックス内で現在選択されている項目 (存在する場合) のインデックスを取得します。|
|[CComboBox:: GetDroppedControlRect](#getdroppedcontrolrect)|ドロップダウンコンボボックスの表示 (ドロップダウン) リストボックスの画面座標を取得します。|
|[CComboBox:: GetDroppedState](#getdroppedstate)|ドロップダウンコンボボックスのリストボックスを表示するかどうかを決定します (ドロップダウン)。|
|[CComboBox:: GetDroppedWidth](#getdroppedwidth)|コンボボックスのドロップダウンリストボックスの部分で許容される最小幅を取得します。|
|[CComboBox:: GetEditSel](#geteditsel)|コンボボックスの編集コントロールの現在の選択範囲の開始文字と終了文字の位置を取得します。|
|[CComboBox:: GetExtendedUI](#getextendedui)|コンボボックスに既定のユーザーインターフェイスまたは拡張ユーザーインターフェイスがあるかどうかを判断します。|
|[CComboBox:: GetHorizontalExtent](#gethorizontalextent)|コンボボックスのリストボックスの部分を水平方向にスクロールできる幅 (ピクセル単位) を返します。|
|[CComboBox:: GetItemData](#getitemdata)|指定したコンボボックス項目に関連付けられている、アプリケーションが提供した32ビット値を取得します。|
|[CComboBox:: GetItemDataPtr](#getitemdataptr)|指定したコンボボックス項目に関連付けられている、アプリケーションによって提供された32ビットポインターを取得します。|
|[CComboBox:: GetItemHeight](#getitemheight)|コンボボックス内のリスト項目の高さを取得します。|
|[CComboBox:: GetLBText](#getlbtext)|コンボボックスのリストボックスから文字列を取得します。|
|[CComboBox:: GetLBTextLen](#getlbtextlen)|コンボボックスのリストボックス内の文字列の長さを取得します。|
|[CComboBox:: GetLocale](#getlocale)|コンボボックスのロケール識別子を取得します。|
|[CComboBox:: GetMinVisible](#getminvisible)|現在のコンボボックスのドロップダウンリストに表示される項目の最小数を取得します。|
|[CComboBox:: GetTopIndex](#gettopindex)|コンボボックスのリストボックスの部分に表示される最初の項目のインデックスを返します。|
|[CComboBox:: InitStorage](#initstorage)|事前は、コンボボックスのリストボックスの部分に含まれる項目と文字列のメモリブロックを示します。|
|[CComboBox::InsertString](#insertstring)|コンボ ボックスのリスト ボックスに文字列を挿入します。|
|[CComboBox:: LimitText](#limittext)|ユーザーがコンボボックスのエディットコントロールに入力できるテキストの長さを制限します。|
|[CComboBox:: MeasureItem](#measureitem)|オーナー描画コンボボックスが作成されたときに、コンボボックスのサイズを決定するためにフレームワークによって呼び出されます。|
|[CComboBox::P aste](#paste)|クリップボードのデータを現在のカーソル位置にあるエディットコントロールに挿入します。 クリップボードに CF_TEXT 形式のデータが含まれている場合にのみ、データが挿入されます。|
|[CComboBox:: ResetContent](#resetcontent)|リストボックスからすべての項目を削除し、コンボボックスのコントロールを編集します。|
|[CComboBox:: SelectString](#selectstring)|コンボボックスのリストボックスで文字列を検索し、文字列が見つかった場合はリストボックス内の文字列を選択して、その文字列を編集コントロールにコピーします。|
|[CComboBox:: SetCueBanner](#setcuebanner)|コンボボックスコントロールに表示されるキューテキストを設定します。|
|[CComboBox:: SetCurSel](#setcursel)|コンボボックスのリストボックスで文字列を選択します。|
|[CComboBox:: SetDroppedWidth](#setdroppedwidth)|コンボボックスのドロップダウンリストボックスの部分に許可される最小の幅を設定します。|
|[CComboBox:: SetEditSel](#seteditsel)|コンボボックスの編集コントロールで文字を選択します。|
|[CComboBox:: SetExtendedUI](#setextendedui)|CBS_DROPDOWN または CBS_DROPDOWNLIST スタイルを持つコンボボックスの既定のユーザーインターフェイスまたは拡張ユーザーインターフェイスを選択します。|
|[CComboBox:: SetHorizontalExtent](#sethorizontalextent)|コンボボックスのリストボックスの部分を水平方向にスクロールできる幅 (ピクセル単位) を設定します。|
|[CComboBox:: SetItemData](#setitemdata)|コンボボックス内の指定した項目に関連付けられている32ビット値を設定します。|
|[CComboBox:: SetItemDataPtr](#setitemdataptr)|コンボボックス内の指定した項目に関連付けられている32ビットポインターを設定します。|
|[CComboBox:: SetItemHeight](#setitemheight)|コンボボックスのリスト項目の高さ、またはコンボボックスの編集コントロール (または静的テキスト) 部分の高さを設定します。|
|[CComboBox:: SetLocale](#setlocale)|コンボボックスのロケール識別子を設定します。|
|[CComboBox:: SetMinVisibleItems](#setminvisibleitems)|現在のコンボボックスのドロップダウンリストに表示される項目の最小数を設定します。|
|[CComboBox:: SetTopIndex](#settopindex)|コンボボックスのリストボックスの部分に、指定したインデックスを持つ項目を先頭に表示するように指示します。|
|[CComboBox:: ShowDropDown](#showdropdown)|CBS_DROPDOWN または CBS_DROPDOWNLIST スタイルを持つコンボボックスのリストボックスの表示と非表示を切り替えます。|

## <a name="remarks"></a>解説

コンボボックスは、スタティックコントロールまたは編集コントロールのいずれかと組み合わせたリストボックスで構成されます。 コントロールのリストボックスの部分は常に表示されるか、ユーザーがコントロールの横にあるドロップダウン矢印を選択したときにのみドロップダウンされることがあります。

リストボックス内の現在選択されている項目 (存在する場合) は、静的コントロールまたは編集コントロールに表示されます。 また、コンボボックスにドロップダウンリストのスタイルがある場合、ユーザーはリスト内のいずれかの項目の最初の文字を入力できます。リストボックスが表示されている場合は、その最初の文字が次の項目を強調表示します。

次の表は、3つのコンボボックス[スタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)を比較したものです。

|スタイル|リストボックスが表示されているとき|静的コントロールまたは編集コントロール|
|-----------|-------------------------------|-----------------------------|
|シンプル|Always (常に)|編集|
|Drop-down|ドロップダウンしたとき|編集|
|ドロップダウン リスト|ドロップダウンしたとき|静的|

オブジェクトを作成するには、ダイアログテンプレートを使用するか、 `CComboBox` コード内で直接作成します。 どちらの場合も、最初にコンストラクターを呼び出して `CComboBox` オブジェクトを構築 `CComboBox` し、次に[create](#create) member 関数を呼び出してコントロールを作成し、オブジェクトにアタッチし `CComboBox` ます。

コンボボックスから親 (通常はから派生したクラス) に送信される Windows 通知メッセージを処理する場合は `CDialog` 、各メッセージの親クラスにメッセージマップエントリとメッセージハンドラーメンバー関数を追加します。

各メッセージマップエントリには、次の形式があります。

`ON_Notification( id, memberFxn )`

ここで `id` は、通知を送信するコンボボックスコントロールの子ウィンドウ ID を指定し `memberFxn` ます。は、通知を処理するために記述した親メンバー関数の名前です。

親の関数プロトタイプは次のとおりです。

`afx_msg void memberFxn( );`

特定の通知を送信する順序を予測することはできません。 特に、CBN_CLOSEUP 通知の前または後に CBN_SELCHANGE 通知が発生する場合があります。

考えられるメッセージマップエントリは次のとおりです。

- ON_CBN_CLOSEUP (Windows 3.1 以降)コンボボックスのリストボックスが閉じられました。 この通知メッセージは、 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを持つコンボボックスには送信されません。

- ユーザーがコンボボックスのリストボックス内の文字列をダブルクリック ON_CBN_DBLCLK ます。 この通知メッセージは、CBS_SIMPLE スタイルが適用されたコンボボックスに対してのみ送信されます。 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルまたは[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを使用しているコンボボックスでは、シングルクリックでリストボックスが非表示になっているため、ダブルクリックを行うことはできません。

- コンボボックスのリストボックスがドロップダウンしている ON_CBN_DROPDOWN (表示されるようになります)。 この通知メッセージは、CBS_DROPDOWN または CBS_DROPDOWNLIST スタイルを持つコンボボックスに対してのみ発生します。

- コンボボックスの編集コントロール部分のテキストを変更した可能性のあるアクションをユーザーが実行した ON_CBN_EDITCHANGE。 CBN_EDITUPDATE メッセージとは異なり、このメッセージは Windows が画面を更新した後に送信されます。 コンボボックスに CBS_DROPDOWNLIST スタイルがある場合は送信されません。

- コンボボックスの編集コントロール部分で ON_CBN_EDITUPDATE 変更されたテキストを表示しようとしています。 この通知メッセージは、コントロールがテキストを書式設定した後、テキストを表示する前に送信されます。 コンボボックスに CBS_DROPDOWNLIST スタイルがある場合は送信されません。

- ON_CBN_ERRSPACE コンボボックスは、特定の要求を満たすのに十分なメモリを割り当てることができません。

- ON_CBN_SELENDCANCEL (Windows 3.1 以降)ユーザーの選択を取り消す必要があることを示します。 ユーザーが項目をクリックし、別のウィンドウまたはコントロールをクリックすると、コンボボックスのリストボックスが非表示になります。 この通知メッセージは、CBN_CLOSEUP 通知メッセージの前に送信され、ユーザーの選択が無視されることを示します。 CBN_SELENDCANCEL または CBN_SELENDOK 通知メッセージが送信されるのは、CBN_CLOSEUP 通知メッセージが送信されていない場合 (CBS_SIMPLE スタイルのコンボボックスの場合と同様) です。

- ユーザーが項目を選択し、ENTER キーを押すか、下方向キーをクリックすると、コンボボックスのリストボックスが非表示に ON_CBN_SELENDOK ます。 この通知メッセージは、CBN_CLOSEUP メッセージの前に送信され、ユーザーの選択が有効と見なされることを示します。 CBN_SELENDCANCEL または CBN_SELENDOK 通知メッセージが送信されるのは、CBN_CLOSEUP 通知メッセージが送信されていない場合 (CBS_SIMPLE スタイルのコンボボックスの場合と同様) です。

- コンボボックス ON_CBN_KILLFOCUS、入力フォーカスが失われています。

- コンボボックスのリストボックスで選択した内容が、ユーザーがリストボックスをクリックするか、方向キーを使用して選択を変更した結果として変更されることを ON_CBN_SELCHANGE します。 このメッセージを処理する場合、コンボボックスのエディットコントロール内のテキストは、 `GetLBText` または他の同様の関数を使用してのみ取得できます。 `GetWindowText`使用できません。

- コンボボックス ON_CBN_SETFOCUS 入力フォーカスを受け取ります。

ダイアログ `CComboBox` ボックス内で (ダイアログリソースを使用して) オブジェクトを作成すると、 `CComboBox` ユーザーがダイアログボックスを閉じたときにオブジェクトが自動的に破棄されます。

オブジェクトを別のウィンドウオブジェクト内に埋め込む場合は `CComboBox` 、そのオブジェクトを破棄する必要はありません。 スタックにオブジェクトを作成すると `CComboBox` 、そのオブジェクトは自動的に破棄されます。 関数を使用してヒープにオブジェクトを作成する場合 `CComboBox` **`new`** 、 **`delete`** Windows のコンボボックスが破棄されたときにオブジェクトを破棄するには、オブジェクトでを呼び出す必要があります。

**メモ**WM_KEYDOWN メッセージと WM_CHAR メッセージを処理する場合は、コンボボックスの [編集] コントロールと [リストボックス] コントロールをサブクラス化し、およびからクラスを派生させ、 `CEdit` `CListBox` それらのメッセージのハンドラーを派生クラスに追加する必要があります。 詳細については、「 [CWnd:: SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="ccomboboxaddstring"></a><a name="addstring"></a>CComboBox:: AddString

コンボボックスのリストボックスに文字列を追加します。

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*lpszString*<br/>
は、追加する null で終わる文字列を指します。

### <a name="return-value"></a>戻り値

戻り値が0以上の場合は、リストボックス内の文字列に対する0から始まるインデックスです。 エラーが発生した場合、戻り値は CB_ERR ます。新しい文字列を格納するのに十分な領域がない場合、戻り値は CB_ERRSPACE ます。

### <a name="remarks"></a>解説

リストボックスが[CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルで作成されなかった場合、文字列はリストの末尾に追加されます。 それ以外の場合は、文字列がリストに挿入され、リストが並べ替えられます。

> [!NOTE]
> この関数は、Windows コントロールではサポートされていません `ComboBoxEx` 。 このコントロールの詳細については、Windows SDK の「 [ComboBoxEx Controls](/windows/win32/Controls/comboboxex-controls) 」を参照してください。

リスト内の特定の位置に文字列を挿入するには、 [Insertstring](#insertstring)メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

## <a name="ccomboboxccombobox"></a><a name="ccombobox"></a>CComboBox:: CComboBox

`CComboBox` オブジェクトを構築します。

```
CComboBox();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

## <a name="ccomboboxclear"></a><a name="clear"></a>CComboBox:: Clear

コンボボックスのエディットコントロール内の現在の選択項目を削除 (クリア) します。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

現在の選択範囲を削除し、削除された内容をクリップボードに配置するには、 [Cut](#cut)メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

## <a name="ccomboboxcompareitem"></a><a name="compareitem"></a>CComboBox:: CompareItem

並べ替えられたオーナー描画コンボボックスのリストボックスの部分における新しい項目の相対位置を決定するために、フレームワークによって呼び出されます。

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpCompareItemStruct*<br/>
[COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct)構造体への long ポインター。

### <a name="return-value"></a>戻り値

構造体で記述されている2つの項目の相対位置を示し `COMPAREITEMSTRUCT` ます。 次のいずれかの値を指定できます。

|値|意味|
|-----------|-------------|
|- 1|項目1は項目2の前に並べ替えられます。|
|0|項目1と項目2は同じように並べ替えられます。|
|1|項目1は項目2の後に並べ替えます。|

の説明については、「 [CWnd:: OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) 」を参照してください `COMPAREITEMSTRUCT` 。

### <a name="remarks"></a>解説

既定では、このメンバー関数は何も行いません。 LBS_SORT スタイルを使用してオーナー描画コンボボックスを作成する場合は、このメンバー関数をオーバーライドして、リストボックスに追加された新しい項目の並べ替えがフレームワークによってサポートされるようにする必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

## <a name="ccomboboxcopy"></a><a name="copy"></a>CComboBox:: コピー

コンボボックスのエディットコントロール内の現在の選択項目を CF_TEXT 形式でクリップボードにコピーします。

```cpp
void Copy();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

## <a name="ccomboboxcreate"></a><a name="create"></a>CComboBox:: Create

コンボボックスを作成し、オブジェクトにアタッチし `CComboBox` ます。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
コンボボックスのスタイルを指定します。 [コンボボックススタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)の任意の組み合わせをボックスに適用します。

*rect*<br/>
コンボボックスの位置とサイズを指します。 には、 [RECT 構造体](/windows/win32/api/windef/ns-windef-rect)またはオブジェクトを指定でき `CRect` ます。

*pParentWnd*<br/>
コンボボックスの親ウィンドウ (通常は) を指定し `CDialog` ます。 NULL にすることはできません。

*nID*<br/>
コンボボックスのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

オブジェクトを構築するには、 `CComboBox` 2 つの手順を実行します。 まず、コンストラクターを呼び出し、次に `Create` を呼び出します。これにより、Windows のコンボボックスが作成され、オブジェクトにアタッチさ `CComboBox` れます。

を実行すると、 `Create` Windows によって[WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)のメッセージがコンボボックスに送信されます。

これらのメッセージは、既定では、基本クラスの[OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)の各メンバー関数によって処理され `CWnd` ます。 既定のメッセージ処理を拡張するには、からクラスを派生させ、 `CComboBox` 新しいクラスにメッセージマップを追加して、前のメッセージハンドラーメンバー関数をオーバーライドします。 `OnCreate`たとえば、新しいクラスに必要な初期化を実行する場合は、をオーバーライドします。

次の[ウィンドウスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)をコンボボックスコントロールに適用します。 :

- 常に WS_CHILD

- WS_VISIBLE 通常

- WS_DISABLED はまれ

- コンボボックスのリストボックスに垂直スクロールを追加する WS_VSCROLL

- コンボボックスのリストボックスに水平スクロールを追加する WS_HSCROLL

- グループコントロールに WS_GROUP

- コンボボックスをタブオーダーに含める WS_TABSTOP

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

## <a name="ccomboboxcut"></a><a name="cut"></a>CComboBox:: Cut

コンボボックスエディットコントロール内の現在の選択項目を削除 (切り取り) し、削除されたテキストを CF_TEXT 形式でクリップボードにコピーします。

```cpp
void Cut();
```

### <a name="remarks"></a>解説

削除されたテキストをクリップボードに配置せずに現在の選択項目を削除するには、 [Clear](#clear)メンバー関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

## <a name="ccomboboxdeleteitem"></a><a name="deleteitem"></a>CComboBox::D eleteItem

ユーザーがオーナー描画オブジェクトから項目を削除したとき、 `CComboBox` またはコンボボックスを破棄したときに、フレームワークによって呼び出されます。

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDeleteItemStruct*<br/>
削除された項目に関する情報を格納している Windows [DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct)構造体への long ポインター。 この構造体の説明については、「 [CWnd:: OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) 」を参照してください。

### <a name="remarks"></a>解説

この関数の既定の実装は、何も行いません。 必要に応じて、この関数をオーバーライドしてコンボボックスを再描画します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

## <a name="ccomboboxdeletestring"></a><a name="deletestring"></a>CComboBox::D eleteString

コンボボックスから、[位置] の*項目を削除*します。

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する文字列へのインデックスを指定します。

### <a name="return-value"></a>戻り値

戻り値が0以上の場合は、リストに残っている文字列の数になります。 *NIndex*がリスト内の項目数より大きいインデックスを指定している場合、戻り値は CB_ERR です。

### <a name="remarks"></a>解説

*これで*、すべての項目が1つ下に移動します。 たとえば、コンボボックスに2つの項目が含まれている場合、最初の項目を削除すると、残りの項目が最初の位置になります。 1番目の位置の項目の場合は、[ *nIndex*] = 0 になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

## <a name="ccomboboxdir"></a><a name="dir"></a>CComboBox::D ir

ファイル名またはドライブの一覧をコンボボックスのリストボックスに追加します。

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>パラメーター

*attr*<br/>
には、 **`enum`** [CFile:: GetStatus](../../mfc/reference/cfile-class.md#getstatus)に記述された値、または次の値の任意の組み合わせを指定できます。

- DDL_READWRITE ファイルの読み取りまたは書き込みを行うことができます。

- DDL_READONLY ファイルは読み取り可能ですが、に書き込むことはできません。

- DDL_HIDDEN ファイルは非表示であり、ディレクトリの一覧に表示されません。

- DDL_SYSTEM ファイルはシステムファイルです。

- *Lpszwildcard*によって指定された名前 DDL_DIRECTORY ディレクトリを指定します。

- DDL_ARCHIVE ファイルはアーカイブされています。

- *Lpszwildcard*によって指定された名前に一致するすべてのドライブを含める DDL_DRIVES ます。

- 排他フラグを DDL_EXCLUSIVE します。 排他フラグが設定されている場合は、指定された種類のファイルだけが表示されます。 それ以外の場合は、指定された種類のファイルが "normal" ファイルに加えて一覧表示されます。

*lpszWildCard*<br/>
ファイル指定文字列を指します。 文字列には、ワイルドカード (たとえば、*.) を含めることができ \* ます。

### <a name="return-value"></a>戻り値

戻り値が0以上の場合は、リストに追加された最後のファイル名の0から始まるインデックスです。 エラーが発生した場合、戻り値は CB_ERR ます。新しい文字列を格納するのに十分な領域がない場合、戻り値は CB_ERRSPACE ます。

### <a name="remarks"></a>解説

この関数は、Windows コントロールではサポートされていません `ComboBoxEx` 。 このコントロールの詳細については、Windows SDK の「 [ComboBoxEx Controls](/windows/win32/Controls/comboboxex-controls) 」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

## <a name="ccomboboxdrawitem"></a><a name="drawitem"></a>CComboBox: rawItem:D

オーナー描画コンボボックスの外観が変化したときにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
必要な描画の種類に関する情報を格納している[DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct)構造体へのポインター。

### <a name="remarks"></a>解説

`itemAction`構造体のメンバーは、 `DRAWITEMSTRUCT` 実行する描画アクションを定義します。 この構造体の説明については、「 [CWnd:: OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) 」を参照してください。

既定では、このメンバー関数は何も行いません。 オーナー描画オブジェクトの描画を実装するには、このメンバー関数をオーバーライドし `CComboBox` ます。 このメンバー関数が終了する前に、アプリケーションは、 *lpDrawItemStruct*で指定された表示コンテキスト用に選択されたすべてのグラフィックスデバイスインターフェイス (GDI) オブジェクトを復元する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

## <a name="ccomboboxfindstring"></a><a name="findstring"></a>CComboBox:: FindString

コンボボックスのリストボックス内の指定したプレフィックスを含む最初の文字列を検索します (選択しません)。

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>パラメーター

*nStartAfter*<br/>
最初に検索される項目の前にある項目の0から始まるインデックスを格納します。 検索がリストボックスの下部に到達すると、リストボックスの一番上から*Nstartafter*によって指定された項目に戻ります。 -1 の場合、リストボックス全体が最初から検索されます。

*lpszString*<br/>
検索するプレフィックスを含む、null で終わる文字列を指します。 検索は大文字と小文字が区別されないため、この文字列には大文字と小文字の任意の組み合わせを含めることができます。

### <a name="return-value"></a>戻り値

戻り値が0以上の場合は、一致する項目の0から始まるインデックスです。 検索に失敗した場合は CB_ERR です。

### <a name="remarks"></a>解説

この関数は、Windows コントロールではサポートされていません `ComboBoxEx` 。 このコントロールの詳細については、Windows SDK の「 [ComboBoxEx Controls](/windows/win32/Controls/comboboxex-controls) 」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

## <a name="ccomboboxfindstringexact"></a><a name="findstringexact"></a>CComboBox:: FindStringExact

メンバー関数を呼び出して、 `FindStringExact` *lpszFind*で指定した文字列と一致する最初のリストボックスの文字列 (コンボボックス内) を検索します。

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>パラメーター

*nIndexStart*<br/>
最初に検索する項目の前にある項目の0から始まるインデックスを指定します。 検索がリストボックスの下部に到達すると、リストボックスの一番上から、 *Nindexstart*によって指定された項目に戻ります。 *Nindexstart*が-1 の場合、リストボックス全体が最初から検索されます。

*lpszFind*<br/>
Null で終わる検索対象の文字列を指します。 この文字列には、拡張子を含む完全なファイル名を含めることができます。 検索では大文字と小文字が区別されないため、この文字列には大文字と小文字の任意の組み合わせを含めることができます。

### <a name="return-value"></a>戻り値

一致する項目の0から始まるインデックス番号。検索に失敗した場合は CB_ERR。

### <a name="remarks"></a>解説

コンボボックスがオーナー描画スタイルを使用して作成され、 [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルが指定されていない場合、は `FindStringExact` *lpszFind*の値に対してダブルワード値を照合しようとします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

## <a name="ccomboboxgetcomboboxinfo"></a><a name="getcomboboxinfo"></a>CComboBox:: GetComboBoxInfo

オブジェクトの情報を取得 `CComboBox` します。

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>パラメーター

*pcbi*<br/>
[COMBOBOXINFO](/windows/win32/api/winuser/ns-winuser-comboboxinfo)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、 [CB_GETCOMBOBOXINFO](/windows/win32/Controls/cb-getcomboboxinfo)メッセージの機能をエミュレートします。

## <a name="ccomboboxgetcount"></a><a name="getcount"></a>CComboBox:: GetCount

コンボボックスのリストボックスの部分に含まれる項目の数を取得するには、このメンバー関数を呼び出します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

項目数。 返されるカウントは、最後の項目のインデックス値よりも1だけ大きくなります (インデックスは0から始まります)。 これは、エラーが発生した場合に CB_ERR ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

## <a name="ccomboboxgetcuebanner"></a><a name="getcuebanner"></a>CComboBox:: GetCueBanner

コンボボックスコントロールに表示されるキューテキストを取得します。

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpszText*|入出力キューバナーテキストを受け取るバッファーへのポインター。|
|*cchText*|から*LpszText*パラメーターが指すバッファーのサイズ。|

### <a name="return-value"></a>戻り値

最初のオーバーロードでは、存在する場合は、キューバナーテキストを含む[CString](../../atl-mfc-shared/using-cstring.md)オブジェクト。それ以外の場合は、 `CString` 長さが0のオブジェクト。

または

2番目のオーバーロードでは、このメソッドが成功した場合は TRUE になります。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

キューテキストは、コンボボックスコントロールの入力領域に表示されるプロンプトです。 ユーザーが入力を提供するまで、キューのテキストが表示されます。

このメソッドは、Windows SDK で説明されている[CB_GETCUEBANNER](/windows/win32/Controls/cb-getcuebanner)メッセージを送信します。

## <a name="ccomboboxgetcursel"></a><a name="getcursel"></a>CComboBox:: GetCurSel

コンボボックス内のどの項目が選択されているかを判断するには、このメンバー関数を呼び出します。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

コンボボックスのリストボックス内で現在選択されている項目の0から始まるインデックス番号。項目が選択されていない場合は CB_ERR。

### <a name="remarks"></a>解説

`GetCurSel`リスト内のインデックスを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

## <a name="ccomboboxgetdroppedcontrolrect"></a><a name="getdroppedcontrolrect"></a>CComboBox:: GetDroppedControlRect

メンバー関数を呼び出して、 `GetDroppedControlRect` ドロップダウンコンボボックスの表示 (ドロップダウン) リストボックスの画面座標を取得します。

```cpp
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>パラメーター

*lprect*<br/>
座標を受け取る[RECT 構造体](/windows/win32/api/windef/ns-windef-rect)をポイントします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

## <a name="ccomboboxgetdroppedstate"></a><a name="getdroppedstate"></a>CComboBox:: GetDroppedState

メンバー関数を呼び出して、 `GetDroppedState` ドロップダウンコンボボックスのリストボックスが表示されている (ドロップダウンされている) かどうかを判断します。

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>戻り値

リストボックスが表示されている場合は0以外の。それ以外の場合は0です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

## <a name="ccomboboxgetdroppedwidth"></a><a name="getdroppedwidth"></a>CComboBox:: GetDroppedWidth

コンボボックスのリストボックスの最小許容幅 (ピクセル単位) を取得するには、この関数を呼び出します。

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>戻り値

成功した場合、許容される最小の幅 (ピクセル単位)。それ以外の場合は、CB_ERR ます。

### <a name="remarks"></a>解説

この関数は、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを持つコンボボックスにのみ適用されます。

既定では、ドロップダウンリストボックスで許容される最小幅は0です。 許容される最小幅は、 [SetDroppedWidth](#setdroppedwidth)を呼び出すことによって設定できます。 コンボボックスのリストボックスの部分が表示されている場合、その幅は、許容される最小幅またはコンボボックスの幅のうち、大きい方になります。

### <a name="example"></a>例

  [SetDroppedWidth](#setdroppedwidth)の例を参照してください。

## <a name="ccomboboxgeteditsel"></a><a name="geteditsel"></a>CComboBox:: GetEditSel

コンボボックスの編集コントロールの現在の選択範囲の開始文字と終了文字の位置を取得します。

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>戻り値

下位ワードの開始位置、および上位ワードの選択範囲の終了後の最初の非表示文字の位置を格納する32ビットの値です。 この関数がエディットコントロールのないコンボボックスで使用されている場合は CB_ERR が返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

## <a name="ccomboboxgetextendedui"></a><a name="getextendedui"></a>CComboBox:: GetExtendedUI

メンバー関数を呼び出して、 `GetExtendedUI` コンボボックスに既定のユーザーインターフェイスまたは拡張ユーザーインターフェイスがあるかどうかを確認します。

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>戻り値

コンボボックスに拡張ユーザーインターフェイスがある場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

拡張ユーザーインターフェイスは、次の方法で識別できます。

- スタティックコントロールをクリックすると、 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルのコンボボックスに対してのみリストボックスが表示されます。

- 下方向キーを押すと、リストボックスが表示されます (F4 は無効になります)。

項目リストが表示されていない場合、静的コントロールのスクロールは無効になります (方向キーは無効になります)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

## <a name="ccomboboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CComboBox:: GetHorizontalExtent

コンボボックスから、コンボボックスのリストボックスの部分を水平方向にスクロールできる幅 (ピクセル単位) を取得します。

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>戻り値

コンボボックスのリストボックスの部分のスクロール可能な幅 (ピクセル単位)。

### <a name="remarks"></a>解説

これは、コンボボックスのリストボックスの部分に水平スクロールバーがある場合にのみ適用されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

## <a name="ccomboboxgetitemdata"></a><a name="getitemdata"></a>CComboBox:: GetItemData

指定したコンボボックス項目に関連付けられている、アプリケーションが提供した32ビット値を取得します。

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
コンボボックスのリストボックス内の項目の0から始まるインデックスを格納します。

### <a name="return-value"></a>戻り値

項目に関連付けられている32ビット値。エラーが発生した場合は CB_ERR。

### <a name="remarks"></a>解説

32ビット値は、 [SetItemData](#setitemdata)メンバー関数呼び出しの*dwItemData*パラメーターを使用して設定できます。 `GetItemDataPtr`取得する32ビット値がポインター () の場合は、メンバー関数を使用し **`void`** <strong>\*</strong> ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

## <a name="ccomboboxgetitemdataptr"></a><a name="getitemdataptr"></a>CComboBox:: GetItemDataPtr

指定したコンボボックス項目に関連付けられた、アプリケーションが提供した32ビット値をポインターとして取得し **`void`** <strong>\*</strong> ます ()。

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
コンボボックスのリストボックス内の項目の0から始まるインデックスを格納します。

### <a name="return-value"></a>戻り値

ポインターを取得します。エラーが発生した場合は-1 を取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

## <a name="ccomboboxgetitemheight"></a><a name="getitemheight"></a>CComboBox:: GetItemHeight

メンバー関数を呼び出して、 `GetItemHeight` コンボボックス内のリスト項目の高さを取得します。

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
高さを取得するコンボボックスのコンポーネントを指定します。 *NIndex*パラメーターが-1 の場合、コンボボックスの編集コントロール (または静的テキスト) 部分の高さが取得されます。 コンボボックスに[CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルが設定されている場合、 *nIndex*は、高さを取得するリスト項目の0から始まるインデックスを指定します。 それ以外の場合は、 *nIndex*を0に設定する必要があります。

### <a name="return-value"></a>戻り値

コンボボックス内の指定した項目の高さ (ピクセル単位)。 エラーが発生した場合は、戻り値は CB_ERR です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

## <a name="ccomboboxgetlbtext"></a><a name="getlbtext"></a>CComboBox:: GetLBText

コンボボックスのリストボックスから文字列を取得します。

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
コピーするリストボックス文字列の0から始まるインデックスを格納します。

*lpszText*<br/>
は、文字列を受け取るバッファーを指します。 バッファーには、文字列と終端の null 文字に十分な領域が必要です。

*rString*<br/>
`CString` への参照。

### <a name="return-value"></a>戻り値

文字列の長さ (バイト単位)。終端の null 文字は除外されます。 *NIndex*で有効なインデックスが指定されていない場合、戻り値は CB_ERR になります。

### <a name="remarks"></a>解説

このメンバー関数の2番目の形式は、 `CString` オブジェクトに項目のテキストを格納します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

## <a name="ccomboboxgetlbtextlen"></a><a name="getlbtextlen"></a>CComboBox:: GetLBTextLen

コンボボックスのリストボックス内の文字列の長さを取得します。

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リストボックスの文字列の0から始まるインデックスを格納します。

### <a name="return-value"></a>戻り値

文字列の長さ (バイト単位) (終端の null 文字は除く)。 *NIndex*で有効なインデックスが指定されていない場合、戻り値は CB_ERR になります。

### <a name="example"></a>例

  「 [CComboBox:: GetLBText](#getlbtext)」の例を参照してください。

## <a name="ccomboboxgetlocale"></a><a name="getlocale"></a>CComboBox:: GetLocale

コンボボックスによって使用されるロケールを取得します。

```
LCID GetLocale() const;
```

### <a name="return-value"></a>戻り値

コンボボックス内の文字列のロケール識別子 (LCID) 値。

### <a name="remarks"></a>解説

たとえば、ロケールは、並べ替えられたコンボボックス内の文字列の並べ替え順序を決定するために使用されます。

### <a name="example"></a>例

  「 [CComboBox:: SetLocale](#setlocale)」の例を参照してください。

## <a name="ccomboboxgetminvisible"></a><a name="getminvisible"></a>CComboBox:: GetMinVisible

現在のコンボボックスコントロールのドロップダウンリストに表示される項目の最小数を取得します。

```
int GetMinVisible() const;
```

### <a name="return-value"></a>戻り値

現在のドロップダウンリストに表示される項目の最小数。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[CB_GETMINVISIBLE](/windows/win32/Controls/cb-setminvisible)メッセージを送信します。

## <a name="ccomboboxgettopindex"></a><a name="gettopindex"></a>CComboBox:: GetTopIndex

コンボボックスのリストボックスの部分に表示されている最初の項目の0から始まるインデックスを取得します。

```
int GetTopIndex() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、コンボボックスのリストボックスの部分に表示されている最初の項目の0から始まるインデックス。それ以外の場合は CB_ERR。

### <a name="remarks"></a>解説

最初は、項目0がリストボックスの一番上にありますが、リストボックスがスクロールされている場合は、別の項目が一番上に表示されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

## <a name="ccomboboxinitstorage"></a><a name="initstorage"></a>CComboBox:: InitStorage

コンボボックスのリストボックスの部分にリストボックス項目を格納するためのメモリを割り当てます。

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>パラメーター

*n 項目*<br/>
追加する項目の数を指定します。

*nBytes*<br/>
項目文字列に割り当てるメモリの量をバイト単位で指定します。

### <a name="return-value"></a>戻り値

成功した場合は、メモリの再割り当てが必要になる前にコンボボックスのリストボックスの部分で格納できる項目の最大数。それ以外の場合は CB_ERRSPACE、十分なメモリが使用できないことを意味します。

### <a name="remarks"></a>解説

のリストボックスの部分に多数の項目を追加する前に、この関数を呼び出し `CComboBox` ます。

Windows 95/98 のみ: *wParam*パラメーターは16ビット値に制限されます。 これは、リストボックスに32767を超える項目を含めることができないことを意味します。 項目の数は制限されていますが、リストボックス内の項目の合計サイズは、使用可能なメモリによってのみ制限されます。

この関数は、多数の項目 (100 を超える) を持つリストボックスの初期化を高速化するのに役立ちます。 事前は、指定された量のメモリを使用して、後続の[Addstring](#addstring)、 [insertstring](#insertstring)、および[Dir](#dir)関数が可能な限り最短の時間を取るようにします。 パラメーターには、推定値を使用できます。 過大評価を使用すると、いくつかの追加メモリが割り当てられます。過小評価を行う場合、通常の割り当ては、事前に割り当てられた量を超える項目に使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

## <a name="ccomboboxinsertstring"></a><a name="insertstring"></a>CComboBox:: InsertString

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

文字列が挿入された位置の 0 から始まるインデックス。 エラーが発生した場合は、戻り値は CB_ERR です。 新しい文字列を保存する空き領域が不足している場合は、戻り値は CB_ERRSPACE です。

### <a name="remarks"></a>解説

[AddString](#addstring) メンバー関数とは異なり、 `InsertString` メンバー関数では、 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) スタイルのリストが並べ替えられることはありません。

> [!NOTE]
> この関数は、Windows コントロールではサポートされていません `ComboBoxEx` 。 このコントロールの詳細については、Windows SDK の「 [ComboBoxEx Controls](/windows/win32/Controls/comboboxex-controls) 」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

## <a name="ccomboboxlimittext"></a><a name="limittext"></a>CComboBox:: LimitText

ユーザーがコンボボックスのエディットコントロールに入力できるテキストの長さをバイト単位で制限します。

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>パラメーター

*nMaxChars*<br/>
ユーザーが入力できるテキストの長さ (バイト単位) を指定します。 このパラメーターが0の場合、テキストの長さは65535バイトに設定されます。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。 スタイル[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)を持つコンボボックスまたはエディットコントロールのないコンボボックスに対して呼び出された場合、戻り値は CB_ERR です。

### <a name="remarks"></a>解説

コンボボックスにスタイル[CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)が指定されていない場合、テキスト制限を編集コントロールのサイズより大きく設定しても効果はありません。

`LimitText`ユーザーが入力できるテキストのみを制限します。 このメソッドは、メッセージの送信時にエディットコントロールに既に存在するテキストには影響しません。また、リストボックス内の文字列が選択されている場合は、エディットコントロールにコピーされるテキストの長さにも影響しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

## <a name="ccomboboxmeasureitem"></a><a name="measureitem"></a>CComboBox:: MeasureItem

オーナー描画スタイルを持つコンボボックスが作成されたときに、フレームワークによって呼び出されます。

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct)構造体への long ポインター。

### <a name="remarks"></a>解説

既定では、このメンバー関数は何も行いません。 このメンバー関数をオーバーライドし、構造体に入力して、 `MEASUREITEMSTRUCT` コンボボックスのリストボックスのサイズをウィンドウに通知します。 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを使用してコンボボックスを作成した場合、フレームワークはリストボックスの各項目に対してこのメンバー関数を呼び出します。 それ以外の場合、このメンバーは1回だけ呼び出されます。

の[SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem)メンバー関数で作成されたオーナー描画コンボボックスで CBS_OWNERDRAWFIXED スタイルを使用する場合は、 `CWnd` さらにプログラミングに関する考慮事項が伴います。 [テクニカルノート 14](../../mfc/tn014-custom-controls.md)の説明を参照してください。

構造の説明については、「 [CWnd:: OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) 」を参照してください `MEASUREITEMSTRUCT` 。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

## <a name="ccomboboxpaste"></a><a name="paste"></a>CComboBox::P aste

クリップボードのデータを、現在のカーソル位置にあるコンボボックスの編集コントロールに挿入します。

```cpp
void Paste();
```

### <a name="remarks"></a>解説

クリップボードに CF_TEXT 形式のデータが含まれている場合にのみ、データが挿入されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

## <a name="ccomboboxresetcontent"></a><a name="resetcontent"></a>CComboBox:: ResetContent

リストボックスからすべての項目を削除し、コンボボックスのコントロールを編集します。

```cpp
void ResetContent();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

## <a name="ccomboboxselectstring"></a><a name="selectstring"></a>CComboBox:: SelectString

コンボボックスのリストボックス内の文字列を検索し、その文字列が見つかった場合は、リストボックス内の文字列を選択して、編集コントロールにコピーします。

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*nStartAfter*<br/>
最初に検索される項目の前にある項目の0から始まるインデックスを格納します。 検索がリストボックスの下部に到達すると、リストボックスの一番上から*Nstartafter*によって指定された項目に戻ります。 -1 の場合、リストボックス全体が最初から検索されます。

*lpszString*<br/>
検索するプレフィックスを含む、null で終わる文字列を指します。 検索は大文字と小文字が区別されないため、この文字列には大文字と小文字の任意の組み合わせを含めることができます。

### <a name="return-value"></a>戻り値

文字列が見つかった場合は、選択された項目の0から始まるインデックス。 検索に失敗した場合、戻り値は CB_ERR、現在の選択内容は変更されません。

### <a name="remarks"></a>解説

文字列が選択されるのは、最初の文字 (開始点から) がプレフィックス文字列内の文字と一致する場合のみです。

`SelectString`メンバー関数と `FindString` メンバー関数はどちらも文字列を検索しますが、 `SelectString` メンバー関数も文字列を選択します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

## <a name="ccomboboxsetcuebanner"></a><a name="setcuebanner"></a>CComboBox:: SetCueBanner

コンボボックスコントロールに表示されるキューテキストを設定します。

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpszText*|からキューテキストを格納している null で終わるバッファーへのポインター。|

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

キューテキストは、コンボボックスコントロールの入力領域に表示されるプロンプトです。 ユーザーが入力を提供するまで、キューのテキストが表示されます。

このメソッドは、Windows SDK で説明されている[CB_SETCUEBANNER](/windows/win32/Controls/cb-setcuebanner)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、コンボボックスコントロールにプログラムでアクセスするために使用される、 *m_combobox*変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>例

次のコード例では、コンボボックスコントロールのキューバナーを設定します。

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsetcursel"></a><a name="setcursel"></a>CComboBox:: SetCurSel

コンボボックスのリストボックスで文字列を選択します。

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>パラメーター

*n*<br/>
選択する文字列の0から始まるインデックスを指定します。 -1 の場合は、リストボックス内の現在の選択内容が削除され、エディットコントロールがクリアされます。

### <a name="return-value"></a>戻り値

メッセージが正常に終了した場合に選択された項目の0から始まるインデックス。 *N*がリスト内の項目数より大きい場合、または*n*が-1 に設定されている場合は、戻り値が CB_ERR ます。これにより、選択がクリアされます。

### <a name="remarks"></a>解説

必要に応じて、リストボックスが表示されるように文字列をスクロールします (リストボックスが表示されている場合)。 コンボボックスのエディットコントロールのテキストが、新しい選択内容を反映するように変更されます。 リストボックス内の以前の選択はすべて削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

## <a name="ccomboboxsetdroppedwidth"></a><a name="setdroppedwidth"></a>CComboBox:: SetDroppedWidth

コンボボックスのリストボックスの最小許容幅 (ピクセル単位) を設定するには、この関数を呼び出します。

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
コンボボックスのリストボックスの部分の許容される最小幅 (ピクセル単位)。

### <a name="return-value"></a>戻り値

成功した場合は、リストボックスの新しい幅。それ以外の場合は CB_ERR。

### <a name="remarks"></a>解説

この関数は、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを持つコンボボックスにのみ適用されます。

既定では、ドロップダウンリストボックスで許容される最小幅は0です。 コンボボックスのリストボックスの部分が表示されている場合、その幅は、許容される最小幅またはコンボボックスの幅のうち、大きい方になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

## <a name="ccomboboxseteditsel"></a><a name="seteditsel"></a>CComboBox:: SetEditSel

コンボボックスの編集コントロールで文字を選択します。

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>パラメーター

*nStartChar*<br/>
開始位置を指定します。 開始位置が-1 に設定されている場合、既存の選択はすべて削除されます。

*nEndChar*<br/>
終了位置を指定します。 終了位置が-1 に設定されている場合、エディットコントロールの開始位置から最後の文字までのすべてのテキストが選択されます。

### <a name="return-value"></a>戻り値

メンバー関数が成功した場合は0以外の。それ以外の場合は0です。 が `CComboBox` [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを持っている場合、またはリストボックスがない場合は CB_ERR です。

### <a name="remarks"></a>解説

位置は0から始まります。 エディットコントロールの最初の文字を選択するには、開始位置として0を指定します。 終了位置は、選択する最後の文字の直後の文字です。 たとえば、エディットコントロールの最初の4文字を選択するには、開始位置0と終了位置4を使用します。

> [!NOTE]
> この関数は、Windows コントロールではサポートされていません `ComboBoxEx` 。 このコントロールの詳細については、Windows SDK の「 [ComboBoxEx Controls](/windows/win32/Controls/comboboxex-controls) 」を参照してください。

### <a name="example"></a>例

  「 [CComboBox:: GetEditSel](#geteditsel)」の例を参照してください。

## <a name="ccomboboxsetextendedui"></a><a name="setextendedui"></a>CComboBox:: SetExtendedUI

メンバー関数を呼び出して、 `SetExtendedUI` 既定のユーザーインターフェイス、または[CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを持つコンボボックスの拡張ユーザーインターフェイスのいずれかを選択します。

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>パラメーター

*bExtended*<br/>
コンボボックスで拡張ユーザーインターフェイスを使用するか、既定のユーザーインターフェイスを使用するかを指定します。 値が TRUE の場合、拡張ユーザーインターフェイスが選択されます。値が FALSE の場合は、標準のユーザーインターフェイスが選択されます。

### <a name="return-value"></a>戻り値

操作が成功した場合は CB_OKAY。エラーが発生した場合は CB_ERR。

### <a name="remarks"></a>解説

拡張ユーザーインターフェイスは、次の方法で識別できます。

- スタティックコントロールをクリックすると、CBS_DROPDOWNLIST スタイルのコンボボックスに対してのみリストボックスが表示されます。

- 下方向キーを押すと、リストボックスが表示されます (F4 は無効になります)。

項目リストが表示されていない場合 (方向キーが無効になっている場合)、静的コントロールのスクロールは無効になります。

### <a name="example"></a>例

  「 [CComboBox:: GetExtendedUI](#getextendedui)」の例を参照してください。

## <a name="ccomboboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CComboBox:: SetHorizontalExtent

コンボボックスのリストボックスの部分を水平方向にスクロールできる幅をピクセル単位で設定します。

```cpp
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>パラメーター

*nExtent*<br/>
コンボボックスのリストボックスの部分を水平方向にスクロールできるピクセル数を指定します。

### <a name="remarks"></a>解説

リストボックスの幅がこの値よりも小さい場合、水平スクロールバーはリストボックス内の項目を水平方向にスクロールします。 リストボックスの幅がこの値以上の場合、水平スクロールバーは非表示になります。コンボボックスに[CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルが設定されている場合は、無効になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

## <a name="ccomboboxsetitemdata"></a><a name="setitemdata"></a>CComboBox:: SetItemData

コンボボックス内の指定した項目に関連付けられている32ビット値を設定します。

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
設定する項目の0から始まるインデックスを格納します。

*dwItemData*<br/>
項目に関連付ける新しい値を格納します。

### <a name="return-value"></a>戻り値

エラーが発生した場合は CB_ERR します。

### <a name="remarks"></a>解説

`SetItemDataPtr`32 ビットの項目がポインターである場合は、メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

## <a name="ccomboboxsetitemdataptr"></a><a name="setitemdataptr"></a>CComboBox:: SetItemDataPtr

コンボボックス内の指定した項目に関連付けられている32ビット値を、指定したポインター () に設定し **`void`** <strong>\*</strong> ます。

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目の0から始まるインデックスを格納します。

*pData*<br/>
項目に関連付けるポインターを格納します。

### <a name="return-value"></a>戻り値

エラーが発生した場合は CB_ERR します。

### <a name="remarks"></a>解説

コンボボックス内の項目の相対位置は、項目が追加または削除されると変化することがありますが、このポインターはコンボボックスの有効期間にわたって有効なままです。 そのため、ボックス内の項目のインデックスは変更される可能性がありますが、ポインターは信頼できる状態のままです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

## <a name="ccomboboxsetitemheight"></a><a name="setitemheight"></a>CComboBox:: SetItemHeight

メンバー関数を呼び出して、コンボボックス `SetItemHeight` 内のリスト項目の高さ、またはコンボボックスの編集コントロール (または静的テキスト) 部分の高さを設定します。

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト項目の高さ、またはコンボボックスの編集コントロール (または静的テキスト) 部分の高さを設定するかどうかを指定します。

コンボボックスに[CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルが設定されている場合、 *nIndex*は、高さを設定するリスト項目の0から始まるインデックスを指定します。それ以外の場合、 *nIndex*は0にする必要があり、すべてのリスト項目の高さが設定されます。

*NIndex*が-1 の場合は、コンボボックスの編集コントロールまたは静的テキスト部分の高さを設定します。

*cyItemHeight*<br/>
*NIndex*によって識別されるコンボボックスコンポーネントの高さ (ピクセル単位) を指定します。

### <a name="return-value"></a>戻り値

インデックスまたは高さが無効である場合に CB_ERR します。それ以外の場合は0です。

### <a name="remarks"></a>解説

コンボボックスの編集コントロール (または静的テキスト) 部分の高さは、リスト項目の高さとは関係なく設定されます。 アプリケーションでは、エディットコントロール (または静的テキスト) 部分の高さが特定のリストボックス項目の高さよりも小さくないことを確認する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

## <a name="ccomboboxsetlocale"></a><a name="setlocale"></a>CComboBox:: SetLocale

このコンボボックスのロケール識別子を設定します。

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>パラメーター

*nNewLocale*<br/>
コンボボックスに設定する新しいロケール識別子 (LCID) 値。

### <a name="return-value"></a>戻り値

このコンボボックスの前のロケール識別子 (LCID) の値。

### <a name="remarks"></a>解説

が呼び出されない場合は、 `SetLocale` 既定のロケールがシステムから取得されます。 このシステムの既定のロケールは、コントロールパネルの地域 (または国際) アプリケーションを使用して変更できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

## <a name="ccomboboxsetminvisibleitems"></a><a name="setminvisibleitems"></a>CComboBox:: SetMinVisibleItems

現在のコンボボックスコントロールのドロップダウンリストに表示される項目の最小数を設定します。

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*非表示*|から表示項目の最小数を指定します。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[CB_SETMINVISIBLE](/windows/win32/Controls/cb-setminvisible)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、コンボボックスコントロールにプログラムでアクセスするために使用される、 *m_combobox*変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>例

次のコード例では、コンボボックスコントロールのドロップダウンリストに20個の項目を挿入します。 次に、ユーザーがドロップダウン矢印をクリックしたときに、10個以上の項目が表示されることを指定します。

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsettopindex"></a><a name="settopindex"></a>CComboBox:: SetTopIndex

コンボボックスのリストボックスの部分に特定の項目が確実に表示されるようにします。

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リストボックス項目の0から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

成功した場合は0。エラーが発生した場合は CB_ERR。

### <a name="remarks"></a>解説

システムは、[ *nIndex* ] で指定された項目がリストボックスの一番上に表示されるか、最大のスクロール範囲に達したときまで、リストボックスをスクロールします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

## <a name="ccomboboxshowdropdown"></a><a name="showdropdown"></a>CComboBox:: ShowDropDown

[CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを持つコンボボックスのリストボックスの表示と非表示を切り替えます。

```cpp
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>パラメーター

*bShowIt*<br/>
ドロップダウンリストボックスを表示するか非表示にするかを指定します。 値が TRUE の場合、リストボックスが表示されます。 値が FALSE の場合は、リストボックスが非表示になります。

### <a name="remarks"></a>解説

既定では、このスタイルのコンボボックスにリストボックスが表示されます。

このメンバー関数は、 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを使用して作成されたコンボボックスには影響しません。

### <a name="example"></a>例

  「 [CComboBox:: GetDroppedState](#getdroppedstate)」の例を参照してください。

## <a name="see-also"></a>関連項目

[MFC のサンプル CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic クラス](../../mfc/reference/cstatic-class.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)
