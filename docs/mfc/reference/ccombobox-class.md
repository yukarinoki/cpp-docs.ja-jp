---
title: Cコンボボックスクラス
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
ms.openlocfilehash: df935bb924c7d8908b1166852dc553a73fc71ff3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369508"
---
# <a name="ccombobox-class"></a>Cコンボボックスクラス

Windows のコンボ ボックスの機能が用意されています。

## <a name="syntax"></a>構文

```
class CComboBox : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コンボボックス::Cコンボボックス](#ccombobox)|`CComboBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComboBox::AddString](#addstring)|コンボ ボックスのリスト ボックスのリスト ボックスの末尾に文字列を追加するか、CBS_SORTスタイルのリスト ボックスの並べ替え位置に文字列を追加します。|
|[コンボボックス::クリア](#clear)|エディット コントロール内の現在の選択項目がある場合は、削除 (クリア) します。|
|[Cコンボボックス::比較アイテム](#compareitem)|並べ替えられたオーナー描画コンボ ボックス内の新しいリスト項目の相対位置を決定するために、フレームワークによって呼び出されます。|
|[Cコンボボックス::コピー](#copy)|現在の選択範囲がある場合は、クリップボードにCF_TEXT形式でコピーします。|
|[コンボボックス::作成](#create)|コンボ ボックスを作成し、オブジェクトに`CComboBox`アタッチします。|
|[Cコンボボックス::カット](#cut)|エディット コントロール内の現在の選択範囲がある場合は、その選択範囲を削除 (カット) し、削除したテキストをCF_TEXT形式でクリップボードにコピーします。|
|[コ:Dコンボボックス::D](#deleteitem)|オーナー描画コンボ ボックスからリスト項目が削除されたときに、フレームワークによって呼び出されます。|
|[:Dコンボボックス:テレテストリング](#deletestring)|コンボ ボックスのリスト ボックスから文字列を削除します。|
|[Cコンボボックス::Dir](#dir)|コンボ ボックスのリスト ボックスにファイル名の一覧を追加します。|
|[:Dローアイテム](#drawitem)|オーナー描画コンボ ボックスの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。|
|[文字列を検索します。](#findstring)|コンボ ボックスのリスト ボックスで、指定したプレフィックスを含む最初の文字列を検索します。|
|[文字列を正確に見つける](#findstringexact)|指定した文字列に一致する最初のリスト ボックス文字列 (コンボ ボックス内) を検索します。|
|[コンボボックス::コンボボックス情報を取得します。](#getcomboboxinfo)|オブジェクトに関する情報`CComboBox`を取得します。|
|[Cコンボボックス::カウントを取得します](#getcount)|コンボ ボックスのリスト ボックス内の項目数を取得します。|
|[Cコンボボックス::ゲットキューバナー](#getcuebanner)|コンボ ボックス コントロールに表示されるキュー テキストを取得します。|
|[Cコンボボックス::ゲットカーセル](#getcursel)|コンボ ボックスのリスト ボックス内に現在選択されている項目がある場合は、そのインデックスを取得します。|
|[コントロールレクトを取得します。](#getdroppedcontrolrect)|ドロップダウン コンボ ボックスの表示されている (ドロップダウンされた) リスト ボックスの画面座標を取得します。|
|[をクリックします。](#getdroppedstate)|ドロップダウン コンボ ボックスのリスト ボックスを表示するかどうかを判断します 。|
|[コンボボックス::ドロップス幅](#getdroppedwidth)|コンボ ボックスのドロップダウン リスト ボックス部分の最小許容幅を取得します。|
|[コンボボックス::ゲットエディットセル](#geteditsel)|コンボ ボックスのエディット コントロールでの現在の選択範囲の開始位置と終了位置を取得します。|
|[コンボボックス::ゲットエクステンデッドUI](#getextendedui)|コンボ ボックスに既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスがあるかどうかを判断します。|
|[Cコンボボックス::ゲス水平範囲](#gethorizontalextent)|コンボ ボックスのリスト ボックス部分を水平方向にスクロールできる幅をピクセル単位で返します。|
|[をクリックします。](#getitemdata)|指定したコンボ ボックス項目に関連付けられているアプリケーション指定の 32 ビット値を取得します。|
|[をクリックします。](#getitemdataptr)|指定したコンボ ボックス項目に関連付けられているアプリケーション指定の 32 ビット ポインターを取得します。|
|[をクリックします。](#getitemheight)|コンボ ボックス内のリスト項目の高さを取得します。|
|[コンボボックス::取得テキスト](#getlbtext)|コンボ ボックスのリスト ボックスから文字列を取得します。|
|[Cコンボボックス::GetLBテキストレン](#getlbtextlen)|コンボ ボックスのリスト ボックス内の文字列の長さを取得します。|
|[コンボボックス::ゲットロケール](#getlocale)|コンボ ボックスのロケール識別子を取得します。|
|[コンボボックス::ゲットミンビジブル](#getminvisible)|現在のコンボ ボックスのドロップダウン リストに表示される項目の最小数を取得します。|
|[コンボボックス::ゲットトップインデックス](#gettopindex)|コンボ ボックスのリスト ボックス部分に表示されている最初の項目のインデックスを返します。|
|[コンボボックス::イニトストレージ](#initstorage)|コンボ ボックスのリスト ボックス部分の項目と文字列のメモリ ブロックを事前に割り当てます。|
|[CComboBox::InsertString](#insertstring)|コンボ ボックスのリスト ボックスに文字列を挿入します。|
|[Cコンボボックス::リミットテキスト](#limittext)|コンボ ボックスのエディット コントロールに入力できるテキストの長さを制限します。|
|[Cコンボボックス::メジャーアイテム](#measureitem)|オーナー描画コンボ ボックスが作成されるときにコンボ ボックスの寸法を決定するために、フレームワークによって呼び出されます。|
|[コンボボックス::Pアステ](#paste)|クリップボードのデータを現在のカーソル位置のエディット コントロールに挿入します。 クリップボードにCF_TEXT形式のデータが含まれている場合にのみ、データが挿入されます。|
|[コンテンツをリセットします。](#resetcontent)|コンボ ボックスのリスト ボックスおよびエディット コントロールからすべての項目を削除します。|
|[コンボボックス::文字列を選択](#selectstring)|コンボ ボックスのリスト ボックス内の文字列を検索し、文字列が見つかった場合は、リスト ボックス内の文字列を選択し、エディット コントロールに文字列をコピーします。|
|[Cコンボボックス::セットキューバナー](#setcuebanner)|コンボ ボックス コントロールに表示されるキュー テキストを設定します。|
|[Cコンボボックス::セットカーセル](#setcursel)|コンボ ボックスのリスト ボックス内の文字列を選択します。|
|[コンボボックス::セットドロップ幅](#setdroppedwidth)|コンボ ボックスのドロップダウン リスト ボックス部分の最小許容幅を設定します。|
|[Cコンボボックス::セットエディットセル](#seteditsel)|コンボ ボックスのエディット コントロールの文字を選択します。|
|[コンボボックス::セットエクステンドUI](#setextendedui)|CBS_DROPDOWNまたはCBS_DROPDOWNLISTスタイルを持つコンボ ボックスの既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスを選択します。|
|[Cコンボボックス::セット水平エクステント](#sethorizontalextent)|コンボ ボックスのリスト ボックス部分を水平方向にスクロールできる幅をピクセル単位で設定します。|
|[を設定します。](#setitemdata)|コンボ ボックス内の指定した項目に関連付けられた 32 ビット値を設定します。|
|[を設定します。](#setitemdataptr)|コンボ ボックス内の指定した項目に関連付けられている 32 ビット ポインターを設定します。|
|[コンボボックス::セットアイテムの高さ](#setitemheight)|コンボ ボックスのリスト項目の高さ、またはコンボ ボックスのエディット コントロール (または静的テキスト) 部分の高さを設定します。|
|[Cコンボボックス::セットロケール](#setlocale)|コンボ ボックスのロケール識別子を設定します。|
|[Cコンボボックス::セットミンビジブルアイテム](#setminvisibleitems)|現在のコンボ ボックスのドロップダウン リストに表示される項目の最小数を設定します。|
|[Cコンボボックス::セットトップインデックス](#settopindex)|コンボ ボックスのリスト ボックス部分に、指定したインデックスを持つ項目を一番上に表示するように指示します。|
|[Cコンボボックス::ショードロップダウン](#showdropdown)|CBS_DROPDOWNまたはCBS_DROPDOWNLISTスタイルを持つコンボ ボックスのリスト ボックスの表示と非表示を切り替えます。|

## <a name="remarks"></a>解説

コンボ ボックスは、リスト ボックスと静的コントロールまたはエディット コントロールの組み合わせで構成されます。 コントロールのリスト ボックス部分は、常に表示される場合も、ユーザーがコントロールの横にあるドロップダウン矢印を選択した場合にのみドロップダウンされます。

リスト ボックスで現在選択されている項目 (存在する場合) は、静的コントロールまたは編集コントロールに表示されます。 さらに、コンボ ボックスにドロップダウン リスト スタイルがある場合、ユーザーはリスト内の項目の 1 つの初期文字を入力でき、リスト ボックスが表示されている場合は、その最初の文字で次の項目が強調表示されます。

次の表は、3 つのコンボ ボックス[スタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)を比較します。

|スタイル|リスト ボックスが表示されている場合|静的コントロールまたは編集コントロール|
|-----------|-------------------------------|-----------------------------|
|シンプル|Always (常に)|[編集]|
|Drop-down|ドロップダウン時|[編集]|
|ドロップダウン リスト|ドロップダウン時|静的|

オブジェクトは、`CComboBox`ダイアログ テンプレートから作成することも、コード内で直接作成することもできます。 どちらの場合も、まずコンストラクタ`CComboBox`を呼び出して`CComboBox`オブジェクトを構築します。次に[、Create](#create)メンバー関数を呼び出してコントロールを作成`CComboBox`し、オブジェクトにアタッチします。

コンボ ボックスから親に送信される Windows 通知メッセージ (通常は派生元のクラス`CDialog`) を処理する場合は、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。

各メッセージ マップ エントリは、次の形式をとります。

**オン\_**_通知_**(** _id_,_メンバFxn_ **)**

通知`id`を送信するコンボ ボックス コントロールの子ウィンドウ ID を指定`memberFxn`します。

親の関数プロトタイプは次のとおりです。

**afx_msg** `void` afx_msg `memberFxn` **( );**

特定の通知が送信される順序は予測できません。 特に、CBN_CLOSEUP通知の前または後にCBN_SELCHANGE通知が発生する場合があります。

メッセージ マップのエントリは次のとおりです。

- ON_CBN_CLOSEUP (ウィンドウズ 3.1 以降)コンボ ボックスのリスト ボックスが閉じられました。 この通知メッセージは[、CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを持つコンボ ボックスには送信されません。

- ON_CBN_DBLCLK コンボ ボックスのリスト ボックス内の文字列をダブルクリックします。 この通知メッセージは、CBS_SIMPLEスタイルのコンボ ボックスに対してのみ送信されます。 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルのコンボ ボックスでは、1 回のクリックでリスト ボックスが非表示になるので、ダブルクリックは実行できません。

- ON_CBN_DROPDOWN コンボ ボックスのリスト ボックスがドロップダウンされます (表示されます)。 この通知メッセージは、CBS_DROPDOWNまたはCBS_DROPDOWNLISTスタイルのコンボ ボックスに対してのみ発生します。

- ON_CBN_EDITCHANGE ユーザーがコンボ ボックスのエディット コントロール部分のテキストを変更した可能性のある操作を行いました。 CBN_EDITUPDATE メッセージとは異なり、このメッセージは Windows が画面を更新した後に送信されます。 コンボ ボックスにCBS_DROPDOWNLISTスタイルがある場合は、この値は送信されません。

- ON_CBN_EDITUPDATEコンボ ボックスのエディット コントロール部分が、変更されたテキストを表示しようとしています。 この通知メッセージは、コントロールがテキストを書式設定した後、テキストを表示する前に送信されます。 コンボ ボックスにCBS_DROPDOWNLISTスタイルがある場合は、この値は送信されません。

- ON_CBN_ERRSPACE コンボ ボックスは、特定の要求を満たすのに十分なメモリを割り当てることができません。

- ON_CBN_SELENDCANCEL (ウィンドウズ 3.1 以降)ユーザーの選択を取り消す必要があることを示します。 ユーザーが項目をクリックし、別のウィンドウまたはコントロールをクリックして、コンボ ボックスのリスト ボックスを非表示にします。 この通知メッセージは、CBN_CLOSEUP通知メッセージの前に送信され、ユーザーの選択を無視することを示します。 CBN_SELENDCANCELまたはCBN_SELENDOK通知メッセージは、CBN_CLOSEUP通知メッセージが送信されない場合でも送信されます (CBS_SIMPLEスタイルのコンボボックスの場合のように)。

- ON_CBN_SELENDOK ユーザーが項目を選択し、Enter キーを押すか、下方向キーをクリックしてコンボ ボックスのリスト ボックスを非表示にします。 この通知メッセージは、CBN_CLOSEUPメッセージの前に送信され、ユーザーの選択が有効であると見なされることを示します。 CBN_SELENDCANCELまたはCBN_SELENDOK通知メッセージは、CBN_CLOSEUP通知メッセージが送信されない場合でも送信されます (CBS_SIMPLEスタイルのコンボボックスの場合のように)。

- ON_CBN_KILLFOCUS コンボ ボックスが入力フォーカスを失っています。

- ON_CBN_SELCHANGEコンボ ボックスのリスト ボックスの選択は、ユーザーがリスト ボックスをクリックするか、方向キーを使用して選択を変更した結果として変更されます。 このメッセージを処理する場合、コンボ ボックスのエディット コントロール内のテキストは、他`GetLBText`の関数または他の類似した関数を使用してのみ取得できます。 `GetWindowText`使用できません。

- ON_CBN_SETFOCUS コンボ ボックスが入力フォーカスを受け取ります。

ダイアログ ボックス内`CComboBox`で (ダイアログ リソースを使用して) オブジェクト`CComboBox`を作成すると、ユーザーがダイアログ ボックスを閉じると、オブジェクトは自動的に破棄されます。

別のウィンドウ`CComboBox`オブジェクト内にオブジェクトを埋め込む場合、破棄する必要はありません。 スタック上にオブジェクト`CComboBox`を作成すると、オブジェクトは自動的に破棄されます。 **新しい**関数を`CComboBox`使用してヒープ上にオブジェクトを作成する場合は、Windows コンボ ボックスが破棄されたときに破棄するには、オブジェクトの**delete**を呼び出す必要があります。

**注**WM_KEYDOWNおよびWM_CHARメッセージを処理する場合は、コンボ ボックスのエディット ボックス コントロールとリスト ボックス コントロールをサブクラス`CEdit`化`CListBox`し、から派生したクラスと から派生したクラスと、それらのメッセージのハンドラーを派生クラスに追加する必要があります。 詳細については[、「CWnd::サブクラス ウィンドウ](../../mfc/reference/cwnd-class.md#subclasswindow)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="ccomboboxaddstring"></a><a name="addstring"></a>コンボボックス::文字列を追加

コンボ ボックスのリスト ボックスに文字列を追加します。

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
追加する null で終わる文字列へのポイント。

### <a name="return-value"></a>戻り値

戻り値が 0 以上の場合は、リスト ボックス内の文字列に対する 0 から始まるインデックスです。 エラーが発生した場合は、戻り値CB_ERR。新しい文字列を格納するために十分な領域がない場合は、戻り値がCB_ERRSPACE。

### <a name="remarks"></a>解説

リスト ボックスが[CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルで作成されなかった場合、文字列はリストの末尾に追加されます。 それ以外の場合は、文字列がリストに挿入され、リストが並べ替えられます。

> [!NOTE]
> この関数は、Windows`ComboBoxEx`コントロールではサポートされていません。 このコントロールの詳細については、Windows SDK[のコンボ ボックスのコントロール](/windows/win32/Controls/comboboxex-controls)を参照してください。

リスト内の特定の位置に文字列を挿入するには[、InsertString](#insertstring)メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

## <a name="ccomboboxccombobox"></a><a name="ccombobox"></a>コンボボックス::Cコンボボックス

`CComboBox` オブジェクトを構築します。

```
CComboBox();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

## <a name="ccomboboxclear"></a><a name="clear"></a>コンボボックス::クリア

コンボ ボックスのエディット コントロールで現在選択されている場合は、その選択を削除します(クリアします)。

```
void Clear();
```

### <a name="remarks"></a>解説

現在の選択範囲を削除し、削除した内容をクリップボードに配置するには、[切り取り](#cut)メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

## <a name="ccomboboxcompareitem"></a><a name="compareitem"></a>Cコンボボックス::比較アイテム

並べ替えられたオーナー描画コンボ ボックスのリスト ボックス部分での新しい項目の相対位置を決定するために、フレームワークによって呼び出されます。

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
[構造体への](/windows/win32/api/winuser/ns-winuser-compareitemstruct)長いポインター。

### <a name="return-value"></a>戻り値

構造体に記述されている 2 つの項目の相対`COMPAREITEMSTRUCT`位置を示します。 次のいずれかの値を指定できます。

|[値]|意味|
|-----------|-------------|
|- 1|項目 1 は、項目 2 の前に並べ替えます。|
|0|項目 1 と項目 2 は同じ並べ替えです。|
|1|項目 1 は、項目 2 の後に並べ替えます。|

の説明については[、CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) `COMPAREITEMSTRUCT`を参照してください。

### <a name="remarks"></a>解説

既定では、このメンバー関数は何も実行しません。 LBS_SORT スタイルを持つオーナー描画コンボ ボックスを作成する場合は、リスト ボックスに追加された新しい項目をフレームワークが並べ替えできるよう、このメンバー関数をオーバーライドする必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

## <a name="ccomboboxcopy"></a><a name="copy"></a>Cコンボボックス::コピー

コンボ ボックスのエディット コントロール内の現在の選択範囲を、CF_TEXT形式でクリップボードにコピーします 。(存在する場合)。

```
void Copy();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

## <a name="ccomboboxcreate"></a><a name="create"></a>コンボボックス::作成

コンボ ボックスを作成し、オブジェクトに`CComboBox`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
コンボ ボックスのスタイルを指定します。 コンボ ボックス[スタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)の任意の組み合わせをボックスに適用します。

*Rect*<br/>
コンボ ボックスの位置とサイズを指します。 [RECT 構造体](/windows/win32/api/windef/ns-windef-rect)またはオブジェクトを指定`CRect`できます。

*pParentWnd*<br/>
コンボ ボックスの親ウィンドウ (通常は`CDialog`a ) を指定します。 NULL にすることはできません。

*nID*<br/>
コンボ ボックスのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

オブジェクトは`CComboBox`2 つの手順で作成します。 まず、コンストラクタを呼び出し`Create`、次にを`CComboBox`呼び出します。

実行時`Create`に、Windows は[WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メッセージをコンボ ボックスに送信します。

これらのメッセージは、`CWnd`既定では、基本クラスの[OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate) [、OnCreate、OnNcCalcSize](../../mfc/reference/cwnd-class.md#oncreate)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数によって処理されます。 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize) 既定のメッセージ処理を拡張するには、 から`CComboBox`クラスを派生し、新しいクラスにメッセージ マップを追加し、上記のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`(たとえば、新しいクラスに必要な初期化を実行する場合)。

コンボ ボックス コントロールに次の[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を適用します。 :

- WS_CHILD常に

- WS_VISIBLE通常

- WS_DISABLEDまれ

- WS_VSCROLL コンボ ボックスのリスト ボックスに垂直スクロールを追加するには

- WS_HSCROLL コンボ ボックスのリスト ボックスに水平スクロールを追加するには

- WS_GROUP グループ コントロールへ

- WS_TABSTOP タブ順序にコンボ ボックスを含めるには

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

## <a name="ccomboboxcut"></a><a name="cut"></a>Cコンボボックス::カット

コンボ ボックス エディット コントロール内の現在の選択項目がある場合は、その選択範囲を削除 (カット) し、削除したテキストをCF_TEXT形式でクリップボードにコピーします。

```
void Cut();
```

### <a name="remarks"></a>解説

削除したテキストをクリップボードに配置せずに現在の選択を削除するには[、Clear](#clear)メンバー関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

## <a name="ccomboboxdeleteitem"></a><a name="deleteitem"></a>コ:Dコンボボックス::D

ユーザーがオーナー描画`CComboBox`オブジェクトから項目を削除するか、コンボ ボックスを破棄したときに、フレームワークによって呼び出されます。

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
削除された項目に関する情報を格納する Windows[の DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct)構造体への長いポインター。 この構造体の説明については[、CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)を参照してください。

### <a name="remarks"></a>解説

この関数の既定の実装は、何も行いません。 必要に応じてコンボ ボックスを再描画するには、この関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

## <a name="ccomboboxdeletestring"></a><a name="deletestring"></a>:Dコンボボックス:テレテストリング

コンボ ボックスから*nIndex*の位置にある項目を削除します。

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する文字列のインデックスを指定します。

### <a name="return-value"></a>戻り値

戻り値が 0 以上の場合は、リストに残っている文字列のカウントになります。 *nIndex*がリスト内の項目数より大きいインデックスを指定する場合、戻り値はCB_ERR。

### <a name="remarks"></a>解説

*nIndex*に続くすべての項目が 1 つ下の位置に移動するようになりました。 たとえば、コンボ ボックスに 2 つの項目が含まれている場合、最初の項目を削除すると、残りの項目が最初の位置になります。 *nIndex*=0 最初の位置の項目。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

## <a name="ccomboboxdir"></a><a name="dir"></a>Cコンボボックス::Dir

コンボ ボックスのリスト ボックスにファイル名またはドライブの一覧を追加します。

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>パラメーター

*Attr*<br/>
[CFile::GetStatus](../../mfc/reference/cfile-class.md#getstatus)で説明されている**列挙**値の任意の組み合わせまたは次の値の任意の組み合わせを指定できます。

- DDL_READWRITE ファイルの読み取りまたは書き込みが可能です。

- DDL_READONLY ファイルは読み取り可能ですが、書き込みできません。

- DDL_HIDDENファイルは非表示で、ディレクトリ一覧には表示されません。

- DDL_SYSTEMファイルはシステムファイルです。

- DDL_DIRECTORY *lpszWildCard*で指定された名前はディレクトリを指定します。

- DDL_ARCHIVEファイルがアーカイブされました。

- DDL_DRIVES *lpszWildCard*で指定された名前に一致するすべてのドライブを含めます。

- DDL_EXCLUSIVE排他的フラグ。 排他フラグが設定されている場合は、指定したタイプのファイルのみがリストされます。 それ以外の場合は、指定された種類のファイルが「通常の」ファイルに加えてリストされます。

*lpszワイルドカード*<br/>
ファイル指定文字列へのポイント。 文字列にはワイルドカードを使用できます (*.\*

### <a name="return-value"></a>戻り値

戻り値が 0 以上の場合は、リストに追加された最後のファイル名の 0 から始まるインデックスです。 エラーが発生した場合は、戻り値CB_ERR。新しい文字列を格納するための十分な領域がない場合は、戻り値がCB_ERRSPACEされます。

### <a name="remarks"></a>解説

この関数は、Windows`ComboBoxEx`コントロールではサポートされていません。 このコントロールの詳細については、Windows SDK[のコンボ ボックスのコントロール](/windows/win32/Controls/comboboxex-controls)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

## <a name="ccomboboxdrawitem"></a><a name="drawitem"></a>:Dローアイテム

オーナー描画コンボ ボックスの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
必要な描画の種類に関する情報を含む[DRAWITEMSTRUCT 構造体](/windows/win32/api/winuser/ns-winuser-drawitemstruct)へのポインター。

### <a name="remarks"></a>解説

構造`itemAction`のメンバーは`DRAWITEMSTRUCT`、実行される描画アクションを定義します。 この構造体の説明については[、CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)を参照してください。

既定では、このメンバー関数は何も実行しません。 オーナー描画`CComboBox`オブジェクトの描画を実装するには、このメンバー関数をオーバーライドします。 このメンバー関数が終了する前に、アプリケーションは*lpDrawItemStruct*で提供される表示コンテキストに対して選択されたすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

## <a name="ccomboboxfindstring"></a><a name="findstring"></a>文字列を検索します。

コンボ ボックスのリスト ボックスで指定したプレフィックスを含む最初の文字列を検索しますが、選択しません。

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>パラメーター

*開始後*<br/>
検索される最初の項目の前の項目の 0 から始まるインデックスが含まれます。 検索がリスト ボックスの一番下に到達すると、リスト ボックスの一番上から*nStartAfter*で指定された項目まで検索が続きます。 1 の場合、リスト ボックス全体が先頭から検索されます。

*文字列*<br/>
検索するプレフィックスを含む null で終わる文字列へのポイント。 検索は大文字と小文字を含むことができるので、大文字と小文字の任意の組み合わせを含めることができます。

### <a name="return-value"></a>戻り値

戻り値が 0 以上の場合は、一致する項目の 0 から始まるインデックスです。 検索が失敗した場合はCB_ERR。

### <a name="remarks"></a>解説

この関数は、Windows`ComboBoxEx`コントロールではサポートされていません。 このコントロールの詳細については、Windows SDK[のコンボ ボックスのコントロール](/windows/win32/Controls/comboboxex-controls)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

## <a name="ccomboboxfindstringexact"></a><a name="findstringexact"></a>文字列を正確に見つける

メンバー関数`FindStringExact`を呼び出して *、 lpszFind*で指定した文字列に一致する最初のリスト ボックス文字列 (コンボ ボックス内) を検索します。

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>パラメーター

*インデックススタート*<br/>
検索する最初の項目の前の項目の 0 から始まるインデックスを指定します。 検索がリスト ボックスの一番下に到達すると、リスト ボックスの一番上から*nIndexStart*で指定された項目まで検索が続きます。 *nIndexStart*が -1 の場合、リスト ボックス全体が先頭から検索されます。

*lpsz検索*<br/>
検索する null で終わる文字列へのポイント。 この文字列には、拡張子を含む完全なファイル名を含めることができます。 検索では大文字と小文字が区別されないので、この文字列には大文字と小文字を組み合わせて指定できます。

### <a name="return-value"></a>戻り値

一致する項目の 0 から始まるインデックス、または検索が失敗した場合CB_ERR。

### <a name="remarks"></a>解説

コンボ ボックスがオーナー描画スタイルで作成されたが[、CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルがない場合は`FindStringExact`、ダブルワード値を*lpszFind*の値と照合しようとします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

## <a name="ccomboboxgetcomboboxinfo"></a><a name="getcomboboxinfo"></a>コンボボックス::コンボボックス情報を取得します。

オブジェクトの情報を`CComboBox`取得します。

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>パラメーター

*pcbi*<br/>
[コンボボックス情報](/windows/win32/api/winuser/ns-winuser-comboboxinfo)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように[、CB_GETCOMBOBOXINFO](/windows/win32/Controls/cb-getcomboboxinfo)メッセージの機能をエミュレートします。

## <a name="ccomboboxgetcount"></a><a name="getcount"></a>Cコンボボックス::カウントを取得します

コンボ ボックスのリスト ボックス部分の項目数を取得します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

項目数。 返されるカウントは、最後の項目のインデックス値より 1 大きい値です (インデックスは 0 から始まります)。 エラーが発生した場合はCB_ERR。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

## <a name="ccomboboxgetcuebanner"></a><a name="getcuebanner"></a>Cコンボボックス::ゲットキューバナー

コンボ ボックス コントロールに表示されるキュー テキストを取得します。

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpszText*|[アウト]キュー バナー テキストを受け取るバッファーへのポインター。|
|*cchText*|[in]*lpszText*パラメーターが指すバッファーのサイズ。|

### <a name="return-value"></a>戻り値

最初のオーバーロードでは、キュー バナー テキストが存在する場合は[CString](../../atl-mfc-shared/using-cstring.md)オブジェクトを格納します。それ以外の`CString`場合は、長さがゼロのオブジェクト。

\- または -

2 番目のオーバーロードでは、このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

キューテキストは、コンボボックスコントロールの入力領域に表示されるプロンプトです。 キューテキストは、ユーザーが入力を入力するまで表示されます。

このメソッドは、Windows SDK に記載されている[CB_GETCUEBANNER](/windows/win32/Controls/cb-getcuebanner)メッセージを送信します。

## <a name="ccomboboxgetcursel"></a><a name="getcursel"></a>Cコンボボックス::ゲットカーセル

コンボ ボックスのどの項目が選択されているかを調べます。

```
int GetCurSel() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックスのリスト ボックスで現在選択されている項目の 0 から始まるインデックス。または項目が選択されていない場合はCB_ERR。

### <a name="remarks"></a>解説

`GetCurSel`はリストにインデックスを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

## <a name="ccomboboxgetdroppedcontrolrect"></a><a name="getdroppedcontrolrect"></a>コントロールレクトを取得します。

ドロップダウン`GetDroppedControlRect`コンボ ボックスの表示されている (ドロップダウンされた) リスト ボックスの画面座標を取得するには、メンバー関数を呼び出します。

```
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
座標を受け取る[RECT 構造体](/windows/win32/api/windef/ns-windef-rect)へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

## <a name="ccomboboxgetdroppedstate"></a><a name="getdroppedstate"></a>をクリックします。

ドロップダウン`GetDroppedState`コンボ ボックスのリスト ボックスが表示されているかどうかを確認するメンバー関数を呼び出します ( ドロップダウン ) します。

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>戻り値

リスト ボックスが表示されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

## <a name="ccomboboxgetdroppedwidth"></a><a name="getdroppedwidth"></a>コンボボックス::ドロップス幅

コンボ ボックスのリスト ボックスの最小許容幅 (ピクセル単位) を取得します。

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、許容される最小の幅 (ピクセル単位)。それ以外の場合は、CB_ERR。

### <a name="remarks"></a>解説

この関数は[、CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルのコンボボックスにのみ適用されます。

既定では、ドロップダウン リスト ボックスの最小許容幅は 0 です。 許容される最小の幅は、 [SetDropWidth](#setdroppedwidth)を呼び出すことによって設定できます。 コンボ ボックスのリスト ボックス部分が表示されるとき、その幅は、最小許容幅またはコンボ ボックスの幅の大きい方になります。

### <a name="example"></a>例

  [「設定値](#setdroppedwidth)幅」の例を参照してください。

## <a name="ccomboboxgeteditsel"></a><a name="geteditsel"></a>コンボボックス::ゲットエディットセル

コンボ ボックスのエディット コントロールでの現在の選択範囲の開始位置と終了位置を取得します。

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>戻り値

下位の単語の開始位置と、上位の単語の選択範囲の終了後の最初の非選択文字の位置を含む 32 ビット値。 エディット コントロールのないコンボ ボックスでこの関数を使用すると、CB_ERRが返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

## <a name="ccomboboxgetextendedui"></a><a name="getextendedui"></a>コンボボックス::ゲットエクステンデッドUI

コンボ`GetExtendedUI`ボックスに既定のユーザー インターフェイスと拡張ユーザー インターフェイスのどちらが含まれているかを調べるには、メンバー関数を呼び出します。

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックスに拡張ユーザー インターフェイスがある場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

拡張ユーザー・インターフェースは、以下の方法で識別できます。

- 静的コントロールをクリックすると[、CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルのコンボ ボックスのリスト ボックスだけが表示されます。

- 下方向キーを押すと、リスト ボックスが表示されます(F4 キーは無効です)。

項目リストが表示されない (矢印キーが無効になっている) 場合、静的コントロールのスクロールは無効になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

## <a name="ccomboboxgethorizontalextent"></a><a name="gethorizontalextent"></a>Cコンボボックス::ゲス水平範囲

コンボ ボックスのリスト ボックス部分を水平方向にスクロールできる幅 (ピクセル単位) をコンボ ボックスから取得します。

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックスのリスト ボックス部分のスクロール可能な幅 (ピクセル単位)。

### <a name="remarks"></a>解説

これは、コンボ ボックスのリスト ボックス部分に水平スクロール バーがある場合にのみ適用されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

## <a name="ccomboboxgetitemdata"></a><a name="getitemdata"></a>をクリックします。

指定したコンボ ボックス項目に関連付けられているアプリケーション指定の 32 ビット値を取得します。

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
コンボ ボックスのリスト ボックス内の項目の 0 から始まるインデックスが含まれます。

### <a name="return-value"></a>戻り値

アイテムに関連付けられている 32 ビット値、またはエラーが発生した場合CB_ERR。

### <a name="remarks"></a>解説

32 ビット値は[、SetItemData](#setitemdata)メンバー関数呼び出しの*dwItemData*パラメーターを使用して設定できます。 取得する`GetItemDataPtr`32 ビット値がポインター (**void** <strong>\*</strong>) の場合は、メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

## <a name="ccomboboxgetitemdataptr"></a><a name="getitemdataptr"></a>をクリックします。

指定されたコンボ ボックス項目に関連付けられているアプリケーション提供の 32 ビット値をポインター (**void** <strong>\*</strong>) として取得します。

```
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
コンボ ボックスのリスト ボックス内の項目の 0 から始まるインデックスが含まれます。

### <a name="return-value"></a>戻り値

ポインターを取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

## <a name="ccomboboxgetitemheight"></a><a name="getitemheight"></a>をクリックします。

コンボ`GetItemHeight`ボックス内のリスト項目の高さを取得するには、メンバー関数を呼び出します。

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
高さを取得するコンボ ボックスのコンポーネントを指定します。 *nIndex*パラメーターが -1 の場合、コンボ ボックスのエディット コントロール (または静的テキスト) 部分の高さが取得されます。 コンボ ボックスに[CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルが設定されている場合 *、nIndex*は、高さを取得するリスト アイテムの 0 から始まるインデックスを指定します。 それ以外の場合は *、nIndex*を 0 に設定する必要があります。

### <a name="return-value"></a>戻り値

コンボ ボックス内の指定した項目の高さ (ピクセル単位)。 エラーが発生した場合は、戻り値は CB_ERR です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

## <a name="ccomboboxgetlbtext"></a><a name="getlbtext"></a>コンボボックス::取得テキスト

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
コピーするリスト ボックス文字列の 0 から始まるインデックスを格納します。

*lpszText*<br/>
文字列を受け取るバッファーへのポイント。 バッファーには、文字列と終端の NULL 文字に十分な領域が必要です。

*文字列*<br/>
`CString` への参照。

### <a name="return-value"></a>戻り値

終端の NULL 文字を除く文字列の長さ (バイト単位)。 *nIndex が*有効なインデックスを指定しない場合、戻り値はCB_ERR。

### <a name="remarks"></a>解説

このメンバー関数の 2 番目の形式`CString`では、オブジェクトに項目のテキストが入力されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

## <a name="ccomboboxgetlbtextlen"></a><a name="getlbtextlen"></a>Cコンボボックス::GetLBテキストレン

コンボ ボックスのリスト ボックス内の文字列の長さを取得します。

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス文字列の 0 から始まるインデックスを格納します。

### <a name="return-value"></a>戻り値

終端の NULL 文字を除く、バイト単位の文字列の長さ。 *nIndex が*有効なインデックスを指定しない場合、戻り値はCB_ERR。

### <a name="example"></a>例

  次の例[を](#getlbtext)参照してください。

## <a name="ccomboboxgetlocale"></a><a name="getlocale"></a>コンボボックス::ゲットロケール

コンボ ボックスで使用されるロケールを取得します。

```
LCID GetLocale() const;
```

### <a name="return-value"></a>戻り値

コンボ ボックス内の文字列のロケール識別子 (LCID) 値。

### <a name="remarks"></a>解説

ロケールは、ソートされたコンボボックス内の文字列のソート順を決定するために使用されます。

### <a name="example"></a>例

  C コンボ[ボックス::セットロケール](#setlocale)の例を参照してください。

## <a name="ccomboboxgetminvisible"></a><a name="getminvisible"></a>コンボボックス::ゲットミンビジブル

現在のコンボ ボックス コントロールのドロップダウン リストに表示される項目の最小数を取得します。

```
int GetMinVisible() const;
```

### <a name="return-value"></a>戻り値

現在のドロップダウン リストに表示される項目の最小数。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[CB_GETMINVISIBLE](/windows/win32/Controls/cb-setminvisible)メッセージを送信します。

## <a name="ccomboboxgettopindex"></a><a name="gettopindex"></a>コンボボックス::ゲットトップインデックス

コンボ ボックスのリスト ボックス部分で最初に表示される項目の 0 から始まるインデックスを取得します。

```
int GetTopIndex() const;
```

### <a name="return-value"></a>戻り値

成功した場合、コンボ ボックスのリスト ボックス部分に表示される最初の項目の 0 から始まるインデックスCB_ERR。.

### <a name="remarks"></a>解説

最初は、項目 0 はリスト ボックスの上部に表示されますが、リスト ボックスがスクロールされている場合は、別の項目が上部に表示されることがあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

## <a name="ccomboboxinitstorage"></a><a name="initstorage"></a>コンボボックス::イニトストレージ

コンボ ボックスのリスト ボックスの部分にリスト ボックス項目を格納するためのメモリを割り当てます。

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

成功した場合、メモリの再割り当てが必要になる前にコンボ ボックスのリスト ボックス部分が格納できる項目の最大数、それ以外の場合はCB_ERRSPACE、メモリが不足していることを意味します。

### <a name="remarks"></a>解説

この関数を呼び出してから、リスト ボックスの一部に多数の項目`CComboBox`を追加します。

Windows 95/98 のみ: *wParam*パラメーターは 16 ビットの値に制限されています。 つまり、リスト ボックスに 32,767 個を超える項目を含めることはできません。 項目数は制限されますが、リスト ボックス内の項目の合計サイズは、使用可能なメモリによってのみ制限されます。

この関数は、項目数が多いリスト ボックス (100 を超える) の初期化を高速化します。 指定されたメモリ量が事前に割り当てられ、後続の[AddString](#addstring) [、InsertString](#insertstring)、[および Dir](#dir)関数は、可能な限り短い時間を取ります。 パラメータの見積を使用できます。 過大評価すると、余分なメモリが割り当てられます。過小評価すると、事前割当量を超える品目に対して通常の割り当てが使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

## <a name="ccomboboxinsertstring"></a><a name="insertstring"></a>文字列を挿入します。

コンボ ボックスのリスト ボックスに文字列を挿入します。

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
文字列を受け取るリスト ボックス内の位置を示す 0 から始まるインデックスです。 このパラメーターが -1 の場合、文字列はリストの末尾に追加されます。

*文字列*<br/>
挿入される null で終わる文字列を指します。

### <a name="return-value"></a>戻り値

文字列が挿入された位置の 0 から始まるインデックス。 エラーが発生した場合は、戻り値は CB_ERR です。 新しい文字列を保存する空き領域が不足している場合は、戻り値は CB_ERRSPACE です。

### <a name="remarks"></a>解説

[AddString](#addstring) メンバー関数とは異なり、 `InsertString` メンバー関数では、 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) スタイルのリストが並べ替えられることはありません。

> [!NOTE]
> この関数は、Windows`ComboBoxEx`コントロールではサポートされていません。 このコントロールの詳細については、Windows SDK[のコンボ ボックスのコントロール](/windows/win32/Controls/comboboxex-controls)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

## <a name="ccomboboxlimittext"></a><a name="limittext"></a>Cコンボボックス::リミットテキスト

コンボ ボックスのエディット コントロールに入力できるテキストの長さをバイト単位で制限します。

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>パラメーター

*nMaxChars*<br/>
ユーザーが入力できるテキストの長さ (バイト単位) を指定します。 このパラメーターが 0 の場合、テキストの長さは 65,535 バイトに設定されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。 スタイルが指定されたコンボ ボックス[CBS_DROPDOWNLIST、](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)またはエディット コントロールを持たないコンボ ボックスに対して呼び出された場合、戻り値はCB_ERR。

### <a name="remarks"></a>解説

コンボ ボックスにスタイル[CBS_AUTOHSCROLLが](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)含まれていない場合は、テキストの制限値をエディット コントロールのサイズより大きく設定しても効果はありません。

`LimitText`ユーザーが入力できるテキストを制限するだけです。 この値は、メッセージの送信時にエディット コントロールに既に存在するテキストには影響を与えません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

## <a name="ccomboboxmeasureitem"></a><a name="measureitem"></a>Cコンボボックス::メジャーアイテム

オーナー描画スタイルを持つコンボ ボックスが作成されるときに、フレームワークによって呼び出されます。

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
[構造体への](/windows/win32/api/winuser/ns-winuser-measureitemstruct)長いポインター。

### <a name="remarks"></a>解説

既定では、このメンバー関数は何も実行しません。 このメンバー関数を`MEASUREITEMSTRUCT`オーバーライドし、コンボ ボックスのリスト ボックスのディメンションを Windows に通知する構造体を入力します。 コンボ ボックスが[CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルで作成された場合、フレームワークはリスト ボックス内の各項目に対してこのメンバー関数を呼び出します。 それ以外の場合、このメンバーは 1 回だけ呼び出されます。

[SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem)メンバー関数で作成されたオーナー描画コンボボックスでCBS_OWNERDRAWFIXEDスタイルを使用すると`CWnd`、さらにプログラミングに関する考慮事項が必要になります。 テクニカル ノート[14](../../mfc/tn014-custom-controls.md)の説明を参照してください。

構造体の説明については[、CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT`を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

## <a name="ccomboboxpaste"></a><a name="paste"></a>コンボボックス::Pアステ

クリップボードのデータをコンボ ボックスの現在のカーソル位置のエディット コントロールに挿入します。

```
void Paste();
```

### <a name="remarks"></a>解説

クリップボードにCF_TEXT形式のデータが含まれている場合にのみ、データが挿入されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

## <a name="ccomboboxresetcontent"></a><a name="resetcontent"></a>コンテンツをリセットします。

コンボ ボックスのリスト ボックスおよびエディット コントロールからすべての項目を削除します。

```
void ResetContent();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

## <a name="ccomboboxselectstring"></a><a name="selectstring"></a>コンボボックス::文字列を選択

コンボ ボックスのリスト ボックス内で文字列を検索し、文字列が見つかった場合は、リスト ボックス内の文字列を選択してエディット コントロールにコピーします。

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*開始後*<br/>
検索される最初の項目の前の項目の 0 から始まるインデックスが含まれます。 検索がリスト ボックスの一番下に到達すると、リスト ボックスの一番上から*nStartAfter*で指定された項目まで検索が続きます。 1 の場合、リスト ボックス全体が先頭から検索されます。

*文字列*<br/>
検索するプレフィックスを含む null で終わる文字列へのポイント。 検索は大文字と小文字を含むことができるので、大文字と小文字の任意の組み合わせを含めることができます。

### <a name="return-value"></a>戻り値

文字列が見つかった場合は、選択した項目の 0 から始まるインデックス。 検索が失敗した場合、戻り値はCB_ERRされ、現在の選択は変更されません。

### <a name="remarks"></a>解説

文字列は、先頭の文字 (開始位置から) がプレフィックス文字列の文字と一致する場合にのみ選択されます。

と メンバー`SelectString``FindString`関数はどちらも文字列を検索しますが、`SelectString`メンバー関数も文字列を選択します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

## <a name="ccomboboxsetcuebanner"></a><a name="setcuebanner"></a>Cコンボボックス::セットキューバナー

コンボ ボックス コントロールに表示されるキュー テキストを設定します。

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpszText*|[in]キュー テキストを格納する NULL で終わるバッファーへのポインター。|

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

キューテキストは、コンボボックスコントロールの入力領域に表示されるプロンプトです。 キューテキストは、ユーザーが入力を入力するまで表示されます。

このメソッドは、Windows SDK に記載されている[CB_SETCUEBANNER](/windows/win32/Controls/cb-setcuebanner)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、コンボ ボックス コントロールにプログラムでアクセスするために使用される変数*m_combobox*を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>例

コンボ ボックス コントロールのキュー バナーを設定するコード例を次に示します。

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsetcursel"></a><a name="setcursel"></a>Cコンボボックス::セットカーセル

コンボ ボックスのリスト ボックス内の文字列を選択します。

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>パラメーター

*n選択*<br/>
選択する文字列の 0 から始まるインデックスを指定します。 1 の場合、リスト ボックス内の現在の選択項目はすべて削除され、エディット コントロールはクリアされます。

### <a name="return-value"></a>戻り値

メッセージが正常に実行された場合に選択された項目の 0 から始まるインデックス。 *nSelect*がリスト内の項目数より大きい場合、または*nSelect*が -1 に設定されている場合は、選択をクリアする場合は、戻り値がCB_ERRされます。

### <a name="remarks"></a>解説

必要に応じて、リスト ボックスが表示されるように文字列をスクロールします (リスト ボックスが表示されている場合)。 コンボ ボックスのエディット コントロールのテキストが、新しい選択内容を反映するように変更されます。 リスト ボックス内の以前の選択は削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

## <a name="ccomboboxsetdroppedwidth"></a><a name="setdroppedwidth"></a>コンボボックス::セットドロップ幅

コンボ ボックスのリスト ボックスの最小許容幅 (ピクセル単位) を設定します。

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>パラメーター

*n幅*<br/>
コンボ ボックスのリスト ボックス部分の最小許容幅 (ピクセル単位)。

### <a name="return-value"></a>戻り値

成功した場合は、リスト ボックスの新しい幅がCB_ERR。

### <a name="remarks"></a>解説

この関数は[、CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルのコンボボックスにのみ適用されます。

既定では、ドロップダウン リスト ボックスの最小許容幅は 0 です。 コンボ ボックスのリスト ボックス部分が表示されるとき、その幅は、最小許容幅またはコンボ ボックスの幅の大きい方になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

## <a name="ccomboboxseteditsel"></a><a name="seteditsel"></a>Cコンボボックス::セットエディットセル

コンボ ボックスのエディット コントロールの文字を選択します。

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>パラメーター

*nStartChar*<br/>
開始位置を指定します。 開始位置が -1 に設定されている場合、既存の選択は削除されます。

*エンドチャー*<br/>
終了位置を指定します。 終了位置が -1 に設定されている場合、エディット コントロールの開始位置から最後の文字までのすべてのテキストが選択されます。

### <a name="return-value"></a>戻り値

メンバー関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0。 CBS_DROPDOWNLISTスタイルを持`CComboBox`っているか、[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)リスト ボックスがない場合は、CB_ERRされます。

### <a name="remarks"></a>解説

位置はゼロから始まります。 エディット コントロールの最初の文字を選択するには、開始位置を 0 に指定します。 終了位置は、最後に選択した文字の直後の文字の位置です。 たとえば、エディット コントロールの最初の 4 文字を選択するには、開始位置 0、終了位置 4 を使用します。

> [!NOTE]
> この関数は、Windows`ComboBoxEx`コントロールではサポートされていません。 このコントロールの詳細については、Windows SDK[のコンボ ボックスのコントロール](/windows/win32/Controls/comboboxex-controls)を参照してください。

### <a name="example"></a>例

  [C コンボボックス](#geteditsel)の例を参照してください。

## <a name="ccomboboxsetextendedui"></a><a name="setextendedui"></a>コンボボックス::セットエクステンドUI

CBS_DROPDOWNまたは`SetExtendedUI`[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを持つコンボ ボックスの既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスを選択[CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)するには、メンバー関数を呼び出します。

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>パラメーター

*b拡張*<br/>
コンボ ボックスで拡張ユーザー インターフェイスを使用するか、既定のユーザー インターフェイスを使用するかを指定します。 値が TRUE の場合は、拡張ユーザー インターフェイスが選択されます。値が FALSE の場合は、標準ユーザー インターフェイスが選択されます。

### <a name="return-value"></a>戻り値

操作が成功した場合にCB_OKAYするか、エラーが発生した場合CB_ERR。

### <a name="remarks"></a>解説

拡張ユーザー・インターフェースは、以下の方法で識別できます。

- 静的コントロールをクリックすると、CBS_DROPDOWNLISTスタイルのコンボ ボックスのリスト ボックスだけが表示されます。

- 下方向キーを押すと、リスト ボックスが表示されます(F4 キーは無効です)。

項目リストが表示されない (矢印キーが無効になっている) 場合、静的コントロールのスクロールは無効になります。

### <a name="example"></a>例

  C コンボ ボックスの例を参照してください[。:GetExtendedUI](#getextendedui).

## <a name="ccomboboxsethorizontalextent"></a><a name="sethorizontalextent"></a>Cコンボボックス::セット水平エクステント

コンボ ボックスのリスト ボックス部分を水平方向にスクロールできる幅をピクセル単位で設定します。

```
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>パラメーター

*nエクステント*<br/>
コンボ ボックスのリスト ボックス部分を水平方向にスクロールできるピクセル数を指定します。

### <a name="remarks"></a>解説

リスト ボックスの幅がこの値より小さい場合、水平スクロール バーはリスト ボックス内の項目を水平方向にスクロールします。 リスト ボックスの幅がこの値以上の場合、水平スクロール バーは非表示になり、コンボ ボックスの[CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルが無効になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

## <a name="ccomboboxsetitemdata"></a><a name="setitemdata"></a>を設定します。

コンボ ボックス内の指定した項目に関連付けられた 32 ビット値を設定します。

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
設定する項目のインデックスが 0 から始まる。

*データ*<br/>
アイテムに関連付ける新しい値を格納します。

### <a name="return-value"></a>戻り値

エラーが発生した場合にCB_ERRします。

### <a name="remarks"></a>解説

32`SetItemDataPtr`ビット項目をポインターにする場合は、メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

## <a name="ccomboboxsetitemdataptr"></a><a name="setitemdataptr"></a>を設定します。

コンボ ボックス内の指定された項目に関連付けられた 32 ビット値を、指定したポインタ (**void** <strong>\*</strong>) に設定します。

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目に対する 0 から始まるインデックスを格納します。

*Pdata*<br/>
項目に関連付けるポインターを含みます。

### <a name="return-value"></a>戻り値

エラーが発生した場合にCB_ERRします。

### <a name="remarks"></a>解説

このポインターは、コンボ ボックス内の項目の相対位置が項目の追加または削除に応じて変更される場合でも、コンボ ボックスの有効期間に有効です。 したがって、ボックス内の項目のインデックスは変更できますが、ポインタは信頼できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

## <a name="ccomboboxsetitemheight"></a><a name="setitemheight"></a>コンボボックス::セットアイテムの高さ

コンボ`SetItemHeight`ボックスのリスト項目の高さ、またはコンボ ボックスのエディット コントロール (または静的テキスト) 部分の高さを設定するには、メンバー関数を呼び出します。

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
コンボ ボックスのリスト項目の高さまたはエディット コントロール (または静的テキスト) 部分の高さを設定するかどうかを指定します。

コンボ ボックスに[CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルが設定されている場合 *、nIndex*は高さを設定するリスト項目の 0 から始まるインデックスを指定します。それ以外の場合は *、nIndex*を 0 にする必要があり、すべてのリスト項目の高さが設定されます。

*nIndex*が -1 の場合、コンボ ボックスのエディット コントロール部分または静的テキスト部分の高さが設定されます。

*アイテムの高さ*<br/>
*nIndex*で識別されるコンボ ボックス コンポーネントの高さをピクセル単位で指定します。

### <a name="return-value"></a>戻り値

インデックスまたは高さが無効な場合はCB_ERR。それ以外の場合は 0。

### <a name="remarks"></a>解説

コンボ ボックスのエディット コントロール (または静的テキスト) 部分の高さは、リスト項目の高さとは別に設定されます。 アプリケーションでは、エディット コントロール (または静的テキスト) 部分の高さが、特定のリスト ボックス項目の高さよりも小さくならないようにする必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

## <a name="ccomboboxsetlocale"></a><a name="setlocale"></a>Cコンボボックス::セットロケール

このコンボ ボックスのロケール識別子を設定します。

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>パラメーター

*n新しいロケール*<br/>
コンボ ボックスに設定する新しいロケール識別子 (LCID) 値。

### <a name="return-value"></a>戻り値

このコンボ ボックスの以前のロケール識別子 (LCID) 値。

### <a name="remarks"></a>解説

呼`SetLocale`び出されない場合、デフォルトのロケールはシステムから取得されます。 このシステムの既定のロケールは、コントロール パネルの地域 (または国際) アプリケーションを使用して変更できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

## <a name="ccomboboxsetminvisibleitems"></a><a name="setminvisibleitems"></a>Cコンボボックス::セットミンビジブルアイテム

現在のコンボ ボックス コントロールのドロップダウン リストに表示される項目の最小数を設定します。

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*iMinVisible*|[in]表示可能な項目の最小数を指定します。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[CB_SETMINVISIBLE](/windows/win32/Controls/cb-setminvisible)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、コンボ ボックス コントロールにプログラムでアクセスするために使用される変数*m_combobox*を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>例

コンボ ボックス コントロールのドロップダウン リストに 20 個の項目を挿入するコード例を次に示します。 次に、ユーザーがドロップダウン矢印を押したときに、最低 10 個の項目が表示されるように指定します。

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsettopindex"></a><a name="settopindex"></a>Cコンボボックス::セットトップインデックス

コンボ ボックスのリスト ボックスの部分に特定の項目が表示されるようにします。

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

成功した場合は 0 を返し、エラーが発生した場合はCB_ERR。

### <a name="remarks"></a>解説

nIndex で指定された項目がリスト ボックスの先頭*nIndex*に表示されるか、最大スクロール範囲に達するまで、リスト ボックスがスクロールされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

## <a name="ccomboboxshowdropdown"></a><a name="showdropdown"></a>Cコンボボックス::ショードロップダウン

[CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを持つコンボ ボックスのリスト ボックスの表示と非表示を切り替えます。

```
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>パラメーター

*bショーイット*<br/>
ドロップダウン リスト ボックスを表示するか非表示にするかを指定します。 TRUE の値はリスト ボックスを示します。 値が FALSE の場合、リスト ボックスは非表示になります。

### <a name="remarks"></a>解説

既定では、このスタイルのコンボ ボックスにはリスト ボックスが表示されます。

このメンバー関数は[、CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルで作成されたコンボ ボックスには影響しません。

### <a name="example"></a>例

  [次](#getdroppedstate)の例を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル CTRL バー](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic クラス](../../mfc/reference/cstatic-class.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)
