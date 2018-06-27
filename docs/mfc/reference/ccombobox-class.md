---
title: CComboBox クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb514531e600243fe02f8b5a6a9cd91a30c14542
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952581"
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
|[Ccombobox::addstring](#addstring)|コンボ ボックスまたはリスト ボックスでの並べ替えの位置にあるリスト ボックスの一覧の末尾に文字列を追加、 **CBS_SORT**スタイル。|  
|[CComboBox::Clear](#clear)|削除 (クリア) 現在の選択範囲の編集コントロールに存在する場合。|  
|[CComboBox::CompareItem](#compareitem)|並べ替えられたオーナー描画コンボ ボックスで新しいリスト アイテムの相対位置を決定するためにフレームワークによって呼び出されます。|  
|[CComboBox::Copy](#copy)|現在の選択範囲の場合、いずれかでクリップボードにコピー**エディット**形式です。|  
|[CComboBox::Create](#create)|コンボ ボックスを作成しにアタッチ、`CComboBox`オブジェクト。|  
|[CComboBox::Cut](#cut)|(切り取り)、現在選択中のいずれかの編集を制御し、削除されたテキストでクリップボードにコピー**エディット**形式です。|  
|[CComboBox::DeleteItem](#deleteitem)|リスト項目がオーナー描画コンボ ボックスから削除されたときに、フレームワークによって呼び出されます。|  
|[オーナー](#deletestring)|コンボ ボックスのリスト ボックスから文字列を削除します。|  
|[CComboBox::Dir](#dir)|コンボ ボックスのリスト ボックスにファイル名の一覧を追加します。|  
|[CComboBox::DrawItem](#drawitem)|オーナー描画コンボ ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。|  
|[CComboBox::FindString](#findstring)|コンボ ボックスの一覧ボックスで指定されたプレフィックスを含む最初の文字列を検索します。|  
|[CComboBox::FindStringExact](#findstringexact)|ボックスの一覧の最初の文字列 (コンボ ボックスの場合)、指定した文字列に一致するを検索します。|  
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|に関する情報を取得、`CComboBox`オブジェクト。|  
|[CComboBox::GetCount](#getcount)|コンボ ボックスのリスト ボックス内の項目の数を取得します。|  
|[CComboBox::GetCueBanner](#getcuebanner)|コンボ ボックス コントロールの表示されるヒントのテキストを取得します。|  
|[CComboBox::GetCurSel](#getcursel)|コンボ ボックスの一覧ボックスで、存在する場合は、現在選択されている項目のインデックスを取得します。|  
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|ドロップダウン コンボ ボックスの表示 (ドロップ ダウン) リスト ボックスの画面座標を取得します。|  
|[CComboBox::GetDroppedState](#getdroppedstate)|かどうか、ドロップダウン コンボ ボックスの一覧ボックスが表示 (ドロップダウン) を決定します。|  
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|最小のコンボ ボックスのドロップダウン リスト ボックスの部分の幅を取得します。|  
|[CComboBox::GetEditSel](#geteditsel)|コンボ ボックスの編集コントロールに現在の選択範囲の開始と終了文字位置を取得します。|  
|[CComboBox::GetExtendedUI](#getextendedui)|コンボ ボックスが既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスがあるかどうかを判断します。|  
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|コンボ ボックスのリスト ボックスの部分が水平方向にスクロールできることをピクセル単位の幅を返します。|  
|[CComboBox::GetItemData](#getitemdata)|コンボ ボックス内の指定した項目に関連付けられたアプリケーションによって提供される 32 ビット値を取得します。|  
|[CComboBox::GetItemDataPtr](#getitemdataptr)|コンボ ボックス内の指定した項目に関連付けられているアプリケーションによって提供される 32 ビット ポインターを取得します。|  
|[CComboBox::GetItemHeight](#getitemheight)|コンボ ボックスのリスト項目の高さを取得します。|  
|[CComboBox::GetLBText](#getlbtext)|コンボ ボックスのリスト ボックスから文字列を取得します。|  
|[CComboBox::GetLBTextLen](#getlbtextlen)|コンボ ボックスの一覧ボックスで、文字列の長さを取得します。|  
|[CComboBox::GetLocale](#getlocale)|コンボ ボックスのロケール識別子を取得します。|  
|[CComboBox::GetMinVisible](#getminvisible)|現在のコンボ ボックスのドロップダウン リストに表示される項目の最小数を取得します。|  
|[CComboBox::GetTopIndex](#gettopindex)|コンボ ボックスのリスト ボックスの部分で、最初に表示される項目のインデックスを返します。|  
|[CComboBox::InitStorage](#initstorage)|アイテムと、リスト ボックス、コンボ ボックスの部分で文字列用のメモリ ブロックに事前に割り当てます。|  
|[CComboBox::InsertString](#insertstring)|コンボ ボックスのリスト ボックスに文字列を挿入します。|  
|[CComboBox::LimitText](#limittext)|ユーザーがコンボ ボックスの編集コントロールに入力できるテキストの長さを制限します。|  
|[CComboBox::MeasureItem](#measureitem)|オーナー描画コンボ ボックスが作成されるときに、コンボ ボックスのサイズを調べるためにフレームワークによって呼び出されます。|  
|[CComboBox::Paste](#paste)|エディット コントロールの現在のカーソル位置にクリップボードからデータを挿入します。 クリップボードのデータを格納する場合にのみ、データが挿入される**エディット**形式です。|  
|[CComboBox::ResetContent](#resetcontent)|一覧からすべての項目 ボックス、コンボ ボックスのコントロールを編集を削除します。|  
|[CComboBox::SelectString](#selectstring)|コンボ ボックスのリスト ボックス内の文字列を検索し、文字列が見つかった場合、リスト ボックスで、文字列を選択し、編集コントロールに文字列をコピーします。|  
|[CComboBox::SetCueBanner](#setcuebanner)|コンボ ボックス コントロールに表示されるヒントのテキストを設定します。|  
|[CComboBox::SetCurSel](#setcursel)|コンボ ボックスのリスト ボックスに文字列を選択します。|  
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|最小のコンボ ボックスのドロップダウン リスト ボックスの部分の幅を設定します。|  
|[CComboBox::SetEditSel](#seteditsel)|コンボ ボックスの編集コントロールの文字を選択します。|  
|[CComboBox::SetExtendedUI](#setextendedui)|既定のユーザー インターフェイスまたはがコンボ ボックスの拡張ユーザー インターフェイスのいずれかを選択、 **CBS_DROPDOWN**または**CBS_DROPDOWNLIST**スタイル。|  
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|コンボ ボックスのリスト ボックスの部分が水平方向にスクロールできることをピクセル単位の幅を設定します。|  
|[CComboBox::SetItemData](#setitemdata)|コンボ ボックスで指定した項目に関連付けられている 32 ビット値を設定します。|  
|[CComboBox::SetItemDataPtr](#setitemdataptr)|コンボ ボックスで指定した項目に関連付けられている 32 ビット ポインターを設定します。|  
|[CComboBox::SetItemHeight](#setitemheight)|コンボ ボックスまたはコンボ ボックスの編集コントロール (または静的なテキスト) の部分の高さのリスト項目の高さを設定します。|  
|[CComboBox::SetLocale](#setlocale)|コンボ ボックスのロケール識別子を設定します。|  
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|現在のコンボ ボックスのドロップダウン リストに表示される項目の最小数を設定します。|  
|[CComboBox::SetTopIndex](#settopindex)|上部にある指定したインデックスを持つ項目を表示するコンボ ボックスのリスト ボックスの部分に指示します。|  
|[CComboBox::ShowDropDown](#showdropdown)|表示またはがコンボ ボックスのリスト ボックスを非表示、 **CBS_DROPDOWN**または**CBS_DROPDOWNLIST**スタイル。|  
  
## <a name="remarks"></a>Remarks  
 コンボ ボックスは、スタティック コントロールまたは編集コントロールのいずれかと組み合わせるリスト ボックスで構成されます。 コントロールのリスト ボックスの部分常に表示される可能性があります。 または可能性がありますのみドロップダウン コントロールの横にあるドロップダウン矢印を選択するとします。  
  
 リスト ボックスで現在選択されているアイテム (存在する場合) は、静的に表示されるまたはコントロールを編集します。 さらに、コンボ ボックスがドロップダウン リストのスタイルは、ユーザーは一覧で、項目のいずれかの最初の文字を入力することができ、ボックスの一覧表示されていればでその最初の文字を次のアイテムは強調表示します。  
  
 次の表に、次の 3 つのコンボ ボックス[スタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)です。  
  
|スタイル|ときにボックスの一覧を表示|コントロールの種類|  
|-----------|-------------------------------|-----------------------------|  
|[シンプル]|Always|編集|  
|Drop-down|下へドロップされたときに|編集|  
|ドロップダウン リスト|下へドロップされたときに|スタティック|  
  
 作成することができます、`CComboBox`ダイアログ テンプレートから、またはコードで直接オブジェクト。 どちらの場合、コンス トラクターを呼び出して最初`CComboBox`構築するために、`CComboBox`オブジェクトです。 まず、[作成](#create)コントロールを作成し、アタッチにメンバー関数、`CComboBox`オブジェクト。  
  
 Windows のコンボ ボックスからその親に送信される通知メッセージを処理する場合 (通常から派生したクラス`CDialog`)、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。  
  
 各メッセージ マップ エントリは次の形式になります。  
  
 **On _** 通知 **(**`id`**、**`memberFxn`**)**  
  
 ここで`id`通知を送信するコンボ ボックス コントロールの子ウィンドウ ID を指定および`memberFxn`通知の処理を記述した親メンバー関数の名前を指定します。  
  
 親の関数プロトタイプは次のとおりです。  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 特定の通知が送信される順序を予測することはできません。 具体的には、 **CBN_SELCHANGE**前に、または後に、通知が発生する可能性があります、 **CBN_CLOSEUP**通知します。  
  
 潜在的なメッセージ マップ エントリは次のとおりです。  
  
- **ON_CBN_CLOSEUP** (Windows 3.1 以降)コンボ ボックスの一覧ボックスが閉じられます。 コンボ ボックスのこの通知メッセージは送信されません、 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。  
  
- **ON_CBN_DBLCLK**コンボ ボックスのリスト ボックス内の文字列をダブルクリックします。 コンボ ボックスにこの通知メッセージが送信されたのみ、 **CBS_SIMPLE**スタイル。 コンボ ボックスの[CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルをダブルクリックを実行できないため、1 回のクリックは、リスト ボックスを非表示にします。  
  
- **ON_CBN_DROPDOWN**コンボ ボックスのリスト ボックスがドロップダウンしようとしていますが (表示可能にする)。 この通知メッセージのみ発生することで、コンボ ボックス、 **CBS_DROPDOWN**または**CBS_DROPDOWNLIST**スタイル。  
  
- **ON_CBN_EDITCHANGE**ユーザーがコンボ ボックスの編集コントロール部分のテキストが変更される可能性があるアクションを取得します。 異なり、 **CBN_EDITUPDATE**メッセージ、Windows が画面を更新した後、このメッセージを送信はします。 コンボ ボックスがある場合は送信されません、 **CBS_DROPDOWNLIST**スタイル。  
  
- **ON_CBN_EDITUPDATE**コンボ ボックスの編集コントロール部分が変更されたテキストを表示しようとしています。 コントロールがテキストを書式設定後、そのテキストを表示する前に、この通知メッセージが送信されます。 コンボ ボックスがある場合は送信されません、 **CBS_DROPDOWNLIST**スタイル。  
  
- **ON_CBN_ERRSPACE**コンボ ボックスは、特定の要求を満たすのに十分なメモリを割り当てることができません。  
  
- **ON_CBN_SELENDCANCEL** (Windows 3.1 以降)ユーザーの選択を取り消す必要があることを示します。 ユーザーは、項目をクリックして、別のウィンドウまたはコンボ ボックスのリスト ボックスを非表示にするコントロールをクリックします。 前にこの通知メッセージが送信される、 **CBN_CLOSEUP**通知メッセージをユーザーの選択を無視することを示します。 **CBN_SELENDCANCEL**または**CBN_SELENDOK**通知メッセージが送信される場合でも、 **CBN_CLOSEUP**通知メッセージは送信されません (コンボ ボックスの場合と、**CBS_SIMPLE**スタイル)。  
  
- **ON_CBN_SELENDOK**ユーザー項目を選択してし、ENTER キーを押したまたはコンボ ボックスのリスト ボックスを非表示に、下方向キーをクリックします。 この通知メッセージの送信前に、 **CBN_CLOSEUP**こと、ユーザーの選択が有効と見なされるかを示すメッセージ。 **CBN_SELENDCANCEL**または**CBN_SELENDOK**通知メッセージが送信される場合でも、 **CBN_CLOSEUP**通知メッセージは送信されません (コンボ ボックスの場合と、**CBS_SIMPLE**スタイル)。  
  
- **ON_CBN_KILLFOCUS**コンボ ボックスが入力フォーカスを失います。  
  
- **ON_CBN_SELCHANGE**コンボ ボックスのリスト ボックスの選択内容を方向キーを使用して、選択を変更するか、リスト ボックス内をクリックすると、ユーザーの結果として変更します。 このメッセージを処理するときに、コンボ ボックスの編集コントロール内のテキストのみを取得できます`GetLBText`または別のような関数です。 `GetWindowText` 使用できません。  
  
- **ON_CBN_SETFOCUS**コンボ ボックスが入力フォーカスを受け取る。  
  
 作成する場合、 `CComboBox` (ダイアログ リソースを使って)、ダイアログ ボックス内のオブジェクト、 `CComboBox`  ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 埋め込む場合、`CComboBox`別のウィンドウ内のオブジェクトがオブジェクトを破棄する必要はありません。 作成する場合、`CComboBox`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CComboBox`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を Windows のコンボ ボックスが破棄されるときに破棄するオブジェクト。  
  
 **注**WM_KEYDOWN と WM_CHAR メッセージを処理する場合があるサブクラスをコンボ ボックスの編集とリスト ボックス コントロールからクラスを派生`CEdit`と`CListBox`、し、派生クラスに含まれるメッセージのハンドラーを追加します。 詳細については、次を参照してください。 [ http://support.microsoft.com/default.aspxscid=kb; en-ご心配なく。Q174667](http://support.microsoft.com/default.aspxscid=kb;en-us;q174667)と[CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="addstring"></a>  Ccombobox::addstring  
 コンボ ボックスのリスト ボックスに文字列を追加します。  
  
```  
int AddString(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszString*  
 追加するのには、null で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値が 0 以上の場合は、リスト ボックス内の文字列の 0 から始まるインデックスであります。 戻り値は**CB_ERR**エラーが発生した場合、戻り値は**CB_ERRSPACE**新しい文字列を保存する十分な空き領域がある場合。  
  
### <a name="remarks"></a>Remarks  
 リスト ボックスで作成されなかった場合、 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、文字列は、リストの末尾に追加されます。 それ以外の場合、リストに、文字列が挿入され、一覧が並べ替えられます。  
  
> [!NOTE]
>  この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)Windows SDK に含まれています。  
  
 リスト内の指定位置に文字列を挿入するには、使用、 [InsertString](#insertstring)メンバー関数。  
  
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
 削除 (クリア) 現在の選択、コンボ ボックスのエディット コントロールである場合。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarks  
 を現在の選択範囲を削除してから削除された内容をクリップボードに配置するには、[切り取り](#cut)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]  
  
##  <a name="compareitem"></a>  CComboBox::CompareItem  
 並べ替えられたオーナー描画コンボ ボックスのリスト ボックスの部分で新しい項目の相対位置を決定するためにフレームワークによって呼び出されます。  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpCompareItemStruct*  
 Long ポインター、 [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md)構造体。  
  
### <a name="return-value"></a>戻り値  
 説明されている 2 つの項目の相対位置を示す、`COMPAREITEMSTRUCT`構造体。 次の値のいずれかを指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|- 1|項目 1 は項目 2 の前に並べ替えます。|  
|0|アイテム 1 と 2 のアイテムは、同じを並べ替えます。|  
|1|項目 1 は項目 2 の後に並べ替えられます。|  
  
 参照してください[CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)の詳細については`COMPAREITEMSTRUCT`します。  
  
### <a name="remarks"></a>Remarks  
 既定では、このメンバー関数では何も行いません。 オーナー描画コンボ ボックスを作成するかどうか、 **LBS_SORT**スタイル、リスト ボックスに追加された新しい項目の並べ替え中に、フレームワークを支援するためにこのメンバー関数をオーバーライドする必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]  
  
##  <a name="copy"></a>  CComboBox::Copy  
 いずれかでクリップボードにコンボ ボックスの編集コントロールにする場合は、現在の選択範囲をコピー**エディット**形式です。  
  
```  
void Copy();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]  
  
##  <a name="create"></a>  CComboBox::Create  
 コンボ ボックスを作成しにアタッチ、`CComboBox`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 コンボ ボックスのスタイルを指定します。 任意の組み合わせを適用[コンボ ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)をボックスにします。  
  
 *rect*  
 コンボ ボックスのサイズと位置を指します。 指定できます、 [RECT 構造体](../../mfc/reference/rect-structure1.md)または`CRect`オブジェクト。  
  
 *pParentWnd*  
 コンボ ボックスの親ウィンドウを指定します (通常、 `CDialog`)。 なければなりません**NULL**です。  
  
 *nID*  
 コンボ ボックスのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CComboBox` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出す`Create`、Windows のコンボ ボックスを作成およびにアタッチする、`CComboBox`オブジェクト。  
  
 ときに`Create`を実行する Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)コンボ ボックスにメッセージです。  
  
 既定では、これらのメッセージが処理されます、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数`CWnd`基本クラスです。 既定のメッセージ処理を拡張するには、派生クラスを`CComboBox`メッセージ マップを新しいクラスに追加し、前のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)コンボ ボックス コントロールにします。 :  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_VSCROLL**コンボ ボックスで、リスト ボックスに垂直スクロール機能を追加するには  
  
- **WS_HSCROLL**コンボ ボックスにあるリスト ボックスの横方向のスクロール機能を追加するには  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**タブ移動順序に、コンボ ボックスを含める  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]  
  
##  <a name="cut"></a>  CComboBox::Cut  
 削除 (切り取り) コンボ ボックスで編集する場合、現在の選択を制御、および削除されたテキストでクリップボードにコピー**エディット**形式です。  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Remarks  
 削除されたテキストをクリップボードに組み込まずに現在の選択範囲を削除する呼び出し、[クリア](#clear)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]  
  
##  <a name="deleteitem"></a>  CComboBox::DeleteItem  
 ユーザーがオーナー描画から項目を削除したときに、フレームワークによって呼び出されます`CComboBox`オブジェクトまたはコンボ ボックスを破棄します。  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDeleteItemStruct*  
 Windows への long ポインター [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md)削除された項目に関する情報を格納する構造体。 参照してください[構造体](../../mfc/reference/cwnd-class.md#ondeleteitem)この構造体の詳細についてはします。  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装は、何も行いません。 必要に応じて、コンボ ボックスを描画するには、この関数をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]  
  
##  <a name="deletestring"></a>  オーナー  
 位置に項目を削除します*nIndex*コンボ ボックスからです。  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 インデックスを削除するのには、文字列を指定します。  
  
### <a name="return-value"></a>戻り値  
 戻り値が 0 以上の場合は、一覧に残っている文字列の数です。 戻り値は**CB_ERR**場合*nIndex*リスト内の項目数より大きいインデックスを指定します。  
  
### <a name="remarks"></a>Remarks  
 次のすべての項目*nIndex*で 1 つ下に移動します。 たとえば、コンボ ボックスに 2 つの項目が含まれている場合の最初の項目を削除できるようになります、残りの項目に最初の位置になります。 *nIndex*最初の位置の項目の 0 を = です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]  
  
##  <a name="dir"></a>  CComboBox::Dir  
 コンボ ボックスのリスト ボックスにファイル名またはドライブの一覧を追加します。  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>パラメーター  
 *attr*  
 組み合わせにすることができます、 **enum**の値で説明[cfile::getstatus](../../mfc/reference/cfile-class.md#getstatus)または、次の値の任意の組み合わせ。  
  
- **DDL_READWRITE**ファイルの読み取りまたはに書き込まれることができます。  
  
- **DDL_READONLY**ファイルをから読み取ることができますには書き込まれません。  
  
- **DDL_HIDDEN**ファイルを非表示に、ディレクトリの一覧が表示されません。  
  
- **DDL_SYSTEM**ファイルは、システム ファイルです。  
  
- **DDL_DIRECTORY**によって指定された名前*lpszWildCard*ディレクトリを指定します。  
  
- **DDL_ARCHIVE**ファイルがアーカイブされています。  
  
- **含んだ**で指定された名前と一致するすべてのドライブに含める*lpszWildCard*です。  
  
- **DDL_EXCLUSIVE**排他フラグ。 排他フラグが設定されている場合は、指定した種類のファイルのみが一覧表示されます。 それ以外の場合、「通常」のファイルだけでなく、指定した種類のファイルが一覧表示されます。  
  
 *lpszWildCard*  
 ファイルの仕様の文字列を指します。 文字列は、ワイルドカードを含めることができます (たとえば、*.\*)。  
  
### <a name="return-value"></a>戻り値  
 戻り値が 0 以上の場合は、一覧に追加された最後のファイル名の 0 から始まるインデックスであります。 戻り値は**CB_ERR**エラーが発生した場合、戻り値は**CB_ERRSPACE**十分な空き領域がある新しい文字列を格納する場合。  
  
### <a name="remarks"></a>Remarks  
 この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]  
  
##  <a name="drawitem"></a>  CComboBox::DrawItem  
 オーナー描画コンボ ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDrawItemStruct*  
 ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>Remarks  
 **ItemAction**のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。 参照してください[体](../../mfc/reference/cwnd-class.md#ondrawitem)この構造体の詳細についてはします。  
  
 既定では、このメンバー関数では何も行いません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CComboBox`オブジェクト。 このメンバー関数が終了すると、前に、アプリケーションがで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]  
  
##  <a name="findstring"></a>  CComboBox::FindString  
 見つかるが、コンボ ボックスの一覧ボックスで指定されたプレフィックスを含む最初の文字列を選択しません。  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszString) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nStartAfter*  
 最初の項目を検索する前に、の項目の 0 から始まるインデックスが含まれています。 指定した項目に、リスト ボックスの上部から続行検索では、リスト ボックスの下部に達すると、 *nStartAfter*です。 -1 の場合、リスト ボックス全体が先頭から検索されます。  
  
 *lpszString*  
 検索対象のプレフィックスを表す null で終わる文字列へのポインター。 検索では独立しており、ケースを指定するため、この文字列は、任意の大文字と小文字を含めることができます。  
  
### <a name="return-value"></a>戻り値  
 戻り値が 0 以上の場合は、一致する項目の 0 から始まるインデックスであります。 **CB_ERR**検索が成功した場合。  
  
### <a name="remarks"></a>Remarks  
 この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]  
  
##  <a name="findstringexact"></a>  CComboBox::FindStringExact  
 呼び出す、`FindStringExact`検索ボックスの一覧の最初の文字列 (コンボ ボックスで指定した文字列に一致するメンバー関数*されて*です。  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndexStart*  
 最初の項目を検索する前に、の項目の 0 から始まるインデックスを指定します。 指定した項目に、リスト ボックスの上部から続行検索では、リスト ボックスの下部に達すると、 *nIndexStart*です。 場合*nIndexStart* -1 で、リスト ボックス全体が先頭から検索します。  
  
 *されています。*  
 検索する null で終わる文字列へのポインター。 この文字列は、拡張子を含む、完全なファイル名を含めることができます。 検索は大文字と小文字はないため、この文字列は、任意の大文字と小文字を含めることができます。  
  
### <a name="return-value"></a>戻り値  
 一致する項目の 0 から始まるインデックス、または**CB_ERR**検索が成功した場合。  
  
### <a name="remarks"></a>Remarks  
 コンボ ボックスがオーナー描画スタイルで作成された場合、 [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、`FindStringExact`ダブルワード値の値と比較を一致させようと*されて*です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]  
  
##  <a name="getcomboboxinfo"></a>  CComboBox::GetComboBoxInfo  
 情報を取得、`CComboBox`オブジェクト。  
  
```  
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pcbi*  
 ポインター、 [COMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775798)構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数の機能をエミュレートする、 [CB_GETCOMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775839)メッセージ、Windows SDK で説明します。  
  
##  <a name="getcount"></a>  CComboBox::GetCount  
 コンボ ボックスのリスト ボックスの部分内の項目数を取得するには、このメンバー関数を呼び出します。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目の数。 返される数は、1 (インデックスは 0 から始まる) の最後の項目のインデックス値より大きい値です。 **CB_ERR**場合は、エラーが発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]  
  
##  <a name="getcuebanner"></a>  CComboBox::GetCueBanner  
 コンボ ボックス コントロールの表示されるヒントのテキストを取得します。  
  
```  
CString GetCueBanner() const;  
  
BOOL GetCueBanner(
    LPTSTR lpszText,   
    int cchText) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[out]*lpszText*|キュー バナー テキストを受け取るバッファーへのポインター。|  
|[in]*cchText*|バッファーのサイズを*lpszText*パラメーターをポイントします。|  
  
### <a name="return-value"></a>戻り値  
 最初のオーバー ロード、 [CString](../../atl-mfc-shared/using-cstring.md) ; 存在する場合は、キュー バナー テキストを格納しているオブジェクトそれ以外の場合、`CString`長さがゼロを持つオブジェクトです。  
  
 - または -  
  
 2 番目のオーバー ロードで`true`このメソッドが成功した、それ以外の場合`false`です。  
  
### <a name="remarks"></a>Remarks  
 ヒントのテキストは、コンボ ボックス コントロールの入力領域に表示されるプロンプトです。 ユーザーが入力されるまで、ヒントのテキストが表示されます。  
  
 このメソッドは、送信、 [CB_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775843) Windows SDK で説明するメッセージ。  
  
##  <a name="getcursel"></a>  CComboBox::GetCurSel  
 コンボ ボックスでどの項目が選択されているかを判断するには、このメンバー関数を呼び出します。  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックスの一覧ボックスで現在選択されている項目の 0 から始まるインデックス、または**CB_ERR**項目が選択されていない場合。  
  
### <a name="remarks"></a>Remarks  
 `GetCurSel` リストにインデックスを返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]  
  
##  <a name="getdroppedcontrolrect"></a>  CComboBox::GetDroppedControlRect  
 呼び出す、`GetDroppedControlRect`ドロップダウン コンボ ボックスの表示 (削除) の一覧ボックスの画面座標を取得します。  
  
```  
void GetDroppedControlRect(LPRECT lprect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lprect*  
 指す、 [RECT 構造体](../../mfc/reference/rect-structure1.md)座標を受け取ることができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]  
  
##  <a name="getdroppedstate"></a>  CComboBox::GetDroppedState  
 呼び出す、`GetDroppedState`メンバー関数かどうか、ドロップダウン コンボ ボックスの一覧ボックスが表示されるか (ドロップダウン) をします。  
  
```  
BOOL GetDroppedState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスを表示する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]  
  
##  <a name="getdroppedwidth"></a>  CComboBox::GetDroppedWidth  
 幅の最小許容値、コンボ ボックスのリスト ボックスのピクセル単位を取得するには、この関数を呼び出します。  
  
```  
int GetDroppedWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、最小の許容される幅 (ピクセル単位) です。それ以外の場合、 **CB_ERR**です。  
  
### <a name="remarks"></a>Remarks  
 この関数は、コンボ ボックスにのみ適用されます、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。  
  
 既定では、ドロップダウン リスト ボックスの許容される最小の幅は 0 です。 設定できる最小幅を呼び出すことによって設定できる[SetDroppedWidth](#setdroppedwidth)です。 コンボ ボックスのリスト ボックスの部分が表示されたら、幅は許容される幅の最小値またはコンボ ボックスの幅のうち、大きい方です。  
  
### <a name="example"></a>例  
  例を参照して[SetDroppedWidth](#setdroppedwidth)です。  
  
##  <a name="geteditsel"></a>  CComboBox::GetEditSel  
 コンボ ボックスの編集コントロールに現在の選択範囲の開始と終了文字位置を取得します。  
  
```  
DWORD GetEditSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 高位の単語の選択範囲の終了後に下位ワードの開始位置と最初に選択されていない文字の位置を表す 32 ビット値。 この関数は、コンボ ボックスは、編集コントロールを使用する場合**CB_ERR**が返されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]  
  
##  <a name="getextendedui"></a>  CComboBox::GetExtendedUI  
 呼び出す、`GetExtendedUI`コンボ ボックスが既定のユーザー インターフェイスまたは拡張ユーザー インターフェイスがあるかどうかを調べます。  
  
```  
BOOL GetExtendedUI() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックスに、拡張ユーザー インターフェイスがある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 拡張ユーザー インターフェイスは、次の方法で識別できます。  
  
-   静的コントロールをクリックして、コンボ ボックスの場合のみ、リスト ボックスを表示、 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。  
  
-   下方向キーを押すと、(f4 キーは無効)、リスト ボックスが表示されます。  
  
 項目の一覧が表示される (矢印キーは無効になります) ではない場合に、スタティック コントロールのスクロールは無効になります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]  
  
##  <a name="gethorizontalextent"></a>  CComboBox::GetHorizontalExtent  
 コンボ ボックスから、これによって、リスト ボックス、コンボ ボックスの部分を水平にスクロールすることができます (ピクセル単位) の幅を取得します。  
  
```  
UINT GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセルのコンボ ボックス、リスト ボックスの部分のスクロール可能な幅です。  
  
### <a name="remarks"></a>Remarks  
 これは、リスト ボックス、コンボ ボックスの部分が水平スクロール バーを持つ場合にのみ適用されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]  
  
##  <a name="getitemdata"></a>  CComboBox::GetItemData  
 コンボ ボックス内の指定した項目に関連付けられたアプリケーションによって提供される 32 ビット値を取得します。  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 コンボ ボックスのリスト ボックス内の項目の 0 から始まるインデックスが含まれています。  
  
### <a name="return-value"></a>戻り値  
 アイテムに関連付けられている 32 ビット値または**CB_ERR**場合は、エラーが発生します。  
  
### <a name="remarks"></a>Remarks  
 32 ビット値を設定することができます、 *dwItemData*のパラメーター、 [SetItemData](#setitemdata)メンバー関数の呼び出しです。 使用して、`GetItemDataPtr`メンバー関数を取得する 32 ビット値がポインターの場合 ( **void\***)。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]  
  
##  <a name="getitemdataptr"></a>  CComboBox::GetItemDataPtr  
 ポインターとして指定されたコンボ ボックスの項目に関連付けられたアプリケーションによって提供される 32 ビット値を取得します ( **void\***)。  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
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
 *nIndex*  
 高さを取得するコンボ ボックスのコンポーネントを指定します。 場合、 *nIndex*パラメーターが-1、コンボ ボックスの編集コントロール (または静的なテキスト) の部分の高さを取得します。 コンボ ボックスがある場合、 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、 *nIndex*の高さを取得するリスト項目の 0 から始まるインデックスを指定します。 それ以外の場合、 *nIndex*を 0 に設定する必要があります。  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックスで指定した項目のピクセル単位の高さ。 エラーが発生した場合は、戻り値は **CB_ERR** です。  
  
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
 *nIndex*  
 コピーするリスト ボックスの文字列の 0 から始まるインデックスが含まれています。  
  
 *lpszText*  
 文字列を受け取るバッファーへのポインター。 バッファーには、文字列、終端の null 文字に十分な空き領域が必要です。  
  
 *rString*  
 参照、`CString`です。  
  
### <a name="return-value"></a>戻り値  
 終端の null 文字を除いた文字列の長さをバイト単位で。 場合*nIndex*有効なインデックスが指定されていません、戻り値は**CB_ERR**です。  
  
### <a name="remarks"></a>Remarks  
 このメンバーの 2 番目の形式の関数がいっぱいになった、`CString`項目のテキストを持つオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]  
  
##  <a name="getlbtextlen"></a>  CComboBox::GetLBTextLen  
 コンボ ボックスの一覧ボックスで、文字列の長さを取得します。  
  
```  
int GetLBTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 リスト ボックスの文字列の 0 から始まるインデックスが含まれています。  
  
### <a name="return-value"></a>戻り値  
 (バイト単位)、終端の null 文字を除く文字列の長さ。 場合*nIndex*有効なインデックスが指定されていません、戻り値は**CB_ERR**です。  
  
### <a name="example"></a>例  
  例を参照して[CComboBox::GetLBText](#getlbtext)です。  
  
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
  例を参照して[CComboBox::SetLocale](#setlocale)です。  
  
##  <a name="getminvisible"></a>  CComboBox::GetMinVisible  
 現在のコンボ ボックス コントロールのドロップダウン リストに表示される項目の最小数を取得します。  
  
```  
int GetMinVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のドロップダウン リストに表示される項目の最小数。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [CB_GETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) Windows SDK で説明するメッセージ。  
  
##  <a name="gettopindex"></a>  CComboBox::GetTopIndex  
 コンボ ボックスのリスト ボックスの部分で最初に表示される項目の 0 から始まるインデックスを取得します。  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、コンボ ボックスのリスト ボックスの部分で最初に表示される項目の 0 から始まるインデックス**CB_ERR**それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 最初に、リスト ボックスの上部にある項目の 0 が上部にある別のアイテムがありますが、リスト ボックスをスクロールすると場合、。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]  
  
##  <a name="initstorage"></a>  CComboBox::InitStorage  
 コンボ ボックスのリスト ボックスの部分でリスト ボックス項目を格納するためにメモリを割り当てます。  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 *nItems*  
 追加する項目の数を指定します。  
  
 *nBytes*  
 割り当てるバイト数、項目の文字列では、メモリの量を指定します。  
  
### <a name="return-value"></a>戻り値  
 かどうか、成功、項目の最大数をメモリを再割り当てが必要とせずに、それ以外の場合、リスト ボックス、コンボ ボックスの部分を格納できます**CB_ERRSPACE**、十分なメモリの意味があります。  
  
### <a name="remarks"></a>Remarks  
 リスト ボックスの部分に多数のアイテムを追加する前にこの関数を呼び出して、`CComboBox`です。  
  
 Windows 95/98 のみ: *wParam*パラメーターは 16 ビット値に制限されます。 つまり、リスト ボックスは、32,767 を超える項目を含めることはできません。 項目の数が制限されているが、リスト ボックス内の項目の合計サイズが使用可能なメモリによってのみ制限されます。  
  
 この関数は、多数のアイテム (100 より大きい) を持つリスト ボックスの初期化を高速化に役立ちます。 指定されたため、その後のメモリ量を事前に割り当てます[AddString](#addstring)、 [InsertString](#insertstring)、および[Dir](#dir)関数は、最短時間を取得します。 パラメーターの見積もりを行うこともできます。 過大評価していない、余分なメモリが割り当てられます。過小を評価するには、事前に割り当てられた量を超えているアイテムの通常の割り当てが使用されます。  
  
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
 *nIndex*  
 文字列を受け取るリスト ボックス内の位置を示す 0 から始まるインデックスです。 このパラメーターが-1 の場合、文字列はリストの末尾に追加されます。  
  
 *lpszString*  
 挿入される null で終わる文字列を指します。  
  
### <a name="return-value"></a>戻り値  
 文字列が挿入された位置の 0 から始まるインデックス。 エラーが発生した場合は、戻り値は **CB_ERR** です。 新しい文字列を保存する空き領域が不足している場合は、戻り値は **CB_ERRSPACE** です。  
  
### <a name="remarks"></a>Remarks  
 異なり、 [AddString](#addstring)メンバー関数の場合、`InsertString`メンバー関数を使用したリストは発生しません、 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)並べ替えスタイルです。  
  
> [!NOTE]
>  この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]  
  
##  <a name="limittext"></a>  CComboBox::LimitText  
 ユーザーがコンボ ボックスの編集コントロールに入力できるテキストの長さ (バイト単位) を制限します。  
  
```  
BOOL LimitText(int nMaxChars);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMaxChars*  
 ユーザーが入力できるテキストの長さ (単位: バイト) を指定します。 このパラメーターが 0 の場合、テキストの長さは、65,535 バイトに設定されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外。 します。 コンボ ボックス スタイルを使用して呼び出された場合[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)コンボ ボックス編集コントロールを使用しないには、戻り値はまたは**CB_ERR**です。  
  
### <a name="remarks"></a>Remarks  
 コンボ ボックスは、スタイルを持たない場合[CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)、エディット コントロールのサイズよりも大きくするテキストの制限を設定効果はありません。  
  
 `LimitText` ユーザーが入力できるテキストを制限するだけです。 影響を与えません任意のテキストで既に編集コントロールにリスト ボックス内の文字列が選択されているときに、編集コントロールにコピーするテキストの長さに影響は、メッセージを送信するとき。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]  
  
##  <a name="measureitem"></a>  CComboBox::MeasureItem  
 オーナー描画スタイルをコンボ ボックスが作成されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMeasureItemStruct*  
 Long ポインター、 [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md)構造体。  
  
### <a name="remarks"></a>Remarks  
 既定では、このメンバー関数では何も行いません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`コンボ ボックスで、一覧の各次元の Windows がボックスに通知する構造体。 コンボ ボックスが作成された場合、 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)リスト ボックス内の各項目のスタイル、フレームワークからこのメンバー関数。 それ以外の場合、このメンバーは、1 回だけ呼び出されます。  
  
 使用して、 **CBS_OWNERDRAWFIXED**スタイルで作成されたオーナー描画コンボ ボックスで、 [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem)のメンバー関数`CWnd`さらにプログラミングの考慮事項が含まれます。 説明を参照[テクニカル ノート 14: カスタム](../../mfc/tn014-custom-controls.md)です。  
  
 参照してください[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)の詳細については、`MEASUREITEMSTRUCT`構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]  
  
##  <a name="paste"></a>  CComboBox::Paste  
 クリップボードから現在のカーソル位置にあるコンボ ボックスのエディット コントロールにデータを挿入します。  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Remarks  
 クリップボードのデータを格納する場合にのみ、データが挿入される**エディット**形式です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]  
  
##  <a name="resetcontent"></a>  CComboBox::ResetContent  
 一覧からすべての項目 ボックス、コンボ ボックスのコントロールを編集を削除します。  
  
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
 *nStartAfter*  
 最初の項目を検索する前に、の項目の 0 から始まるインデックスが含まれています。 指定した項目に、リスト ボックスの上部から続行検索では、リスト ボックスの下部に達すると、 *nStartAfter*です。 -1 の場合、リスト ボックス全体が先頭から検索されます。  
  
 *lpszString*  
 検索対象のプレフィックスを表す null で終わる文字列へのポインター。 検索では独立しており、ケースを指定するため、この文字列は、任意の大文字と小文字を含めることができます。  
  
### <a name="return-value"></a>戻り値  
 文字列が見つかった場合は、選択した項目の 0 から始まるインデックス。 検索が成功しなかった場合、戻り値は**CB_ERR**現在の選択は変更されません。  
  
### <a name="remarks"></a>Remarks  
 文字列は、(始点) から、先頭の文字がプレフィックス文字列内の文字と一致する場合にのみが選択されます。  
  
 なお、`SelectString`と`FindString`メンバー関数は、文字列を検索ですが、`SelectString`メンバー関数も、文字列を選択します。  
  
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
|[in]*lpszText*|ヒントのテキストを格納する null で終わるバッファーへのポインター。|  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は `true`。それ以外の場合は `false`。  
  
### <a name="remarks"></a>Remarks  
 ヒントのテキストは、コンボ ボックス コントロールの入力領域に表示されるプロンプトです。 ユーザーが入力されるまで、ヒントのテキストが表示されます。  
  
 このメソッドは、送信、 [CB_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775897) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義*m_combobox*、つまり、コンボ ボックス コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
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
 *nSelect*  
 選択する文字列の 0 から始まるインデックスを指定します。 場合は-1 で、リスト ボックスで現在の選択は解除され、編集コントロールがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 メッセージが成功した場合に選択した項目の 0 から始まるインデックス。 戻り値は**CB_ERR**場合*nSelect*リスト内の項目の数よりも大きい場合、または*nSelect*選択を解除を-1 に設定されています。  
  
### <a name="remarks"></a>Remarks  
 必要に応じて、リスト ボックスは (リスト ボックスが表示されている場合)、ビューに、文字列をスクロールします。 コンボ ボックスの編集コントロール内のテキストが新しい選択を反映するように変更します。 リスト ボックスで前の選択内容が削除されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]  
  
##  <a name="setdroppedwidth"></a>  CComboBox::SetDroppedWidth  
 コンボ ボックスのリスト ボックスのピクセル単位で設定できる最小幅を設定するには、この関数を呼び出します。  
  
```  
int SetDroppedWidth(UINT nWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *nWidth*  
 リスト ボックス、コンボ ボックスの部分をピクセル単位で設定できる最小幅。  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、一覧の新しい幅ボックス、それ以外の場合**CB_ERR**です。  
  
### <a name="remarks"></a>Remarks  
 この関数は、コンボ ボックスにのみ適用されます、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。  
  
 既定では、ドロップダウン リスト ボックスの許容される最小の幅は 0 です。 コンボ ボックスのリスト ボックスの部分が表示されたら、幅は許容される幅の最小値またはコンボ ボックスの幅のうち、大きい方です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]  
  
##  <a name="seteditsel"></a>  CComboBox::SetEditSel  
 コンボ ボックスの編集コントロールの文字を選択します。  
  
```  
BOOL SetEditSel(
    int nStartChar,  
    int nEndChar);
```  
  
### <a name="parameters"></a>パラメーター  
 *nStartChar*  
 開始位置を指定します。 開始位置が-1 に設定されている場合は、既存の選択内容が削除されます。  
  
 *nEndChar*  
 終了位置を指定します。 終了位置に設定されている-1 のすべてのテキストの開始位置から最後の編集コントロール内の文字が選択されます。  
  
### <a name="return-value"></a>戻り値  
 このメンバー関数が成功した場合は 0 以外。それ以外の場合 0 を返します。 **CB_ERR**場合`CComboBox`が、 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイルを設定したり、リスト ボックスではありません。  
  
### <a name="remarks"></a>Remarks  
 位置は、0 から始まる。 エディット コントロールの最初の文字を選択するには、0 の開始位置を指定します。 終了の位置を選択する最後の文字の直後後の文字です。 たとえば、エディット コントロールの最初の 4 つの文字を選択する、0 の開始位置と終了位置に 4 を使用するは。  
  
> [!NOTE]
>  この関数は、Windows **ComboBoxEx** コントロールではサポートされていません。 このコントロールの詳細については、次を参照してください。 [ComboBoxEx コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775738)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CComboBox::GetEditSel](#geteditsel)です。  
  
##  <a name="setextendedui"></a>  CComboBox::SetExtendedUI  
 呼び出す、`SetExtendedUI`メンバー関数を既定のユーザー インターフェイスまたはがコンボ ボックスの拡張ユーザー インターフェイスのいずれかを選択する、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。  
  
```  
int SetExtendedUI(BOOL bExtended = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bExtended*  
 拡張ユーザー インターフェイスまたは既定のユーザー インターフェイスに、コンボ ボックスを使用するかどうかを指定します。 値**TRUE**拡張選択ユーザー インターフェイス。 値の**FALSE**標準のユーザー インターフェイスを選択します。  
  
### <a name="return-value"></a>戻り値  
 **正常**操作が成功した場合または**CB_ERR**場合は、エラーが発生します。  
  
### <a name="remarks"></a>Remarks  
 拡張ユーザー インターフェイスは、次の方法で識別できます。  
  
-   静的コントロールをクリックして、コンボ ボックスの場合のみ、リスト ボックスを表示、 **CBS_DROPDOWNLIST**スタイル。  
  
-   下方向キーを押すと、(f4 キーは無効)、リスト ボックスが表示されます。  
  
 項目の一覧が表示されていないときに、スタティック コントロールのスクロールを無効 (方向キーが無効になります)。  
  
### <a name="example"></a>例  
  例を参照して[CComboBox::GetExtendedUI](#getextendedui)です。  
  
##  <a name="sethorizontalextent"></a>  CComboBox::SetHorizontalExtent  
 これによって、リスト ボックス、コンボ ボックスの部分を水平にスクロールすることができます (ピクセル単位) の幅を設定します。  
  
```  
void SetHorizontalExtent(UINT nExtent);
```  
  
### <a name="parameters"></a>パラメーター  
 *nExtent*  
 これによって、リスト ボックス、コンボ ボックスの部分を水平にスクロールすることができますのピクセル数を指定します。  
  
### <a name="remarks"></a>Remarks  
 リスト ボックスの幅がこの値よりも小さい場合は、水平スクロール バーはリスト ボックス内の項目を水平にスクロールします。 水平スクロール バーを非表示に、リスト ボックスの幅がこの値以上の場合は、または、コンボ ボックスがある場合、 [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、無効になっています。  
  
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
 *nIndex*  
 設定する項目の 0 から始まるインデックスが含まれています。  
  
 *dwItemData*  
 項目に関連付ける新しい値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 **CB_ERR**場合は、エラーが発生します。  
  
### <a name="remarks"></a>Remarks  
 使用して、`SetItemDataPtr`メンバー関数は 32 ビット アイテムがポインターである場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]  
  
##  <a name="setitemdataptr"></a>  CComboBox::SetItemDataPtr  
 指定したポインターであるコンボ ボックスで指定した項目に関連付けられている 32 ビット値の設定 ( **void\***)。  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 項目の 0 から始まるインデックスが含まれています。  
  
 *pData*  
 項目に関連付けるへのポインターが含まれています。  
  
### <a name="return-value"></a>戻り値  
 **CB_ERR**場合は、エラーが発生します。  
  
### <a name="remarks"></a>Remarks  
 このポインターは項目の追加または削除、コンボ ボックス内の項目の相対位置を変更する可能性がありますもコンボ ボックスの有効期間は有効です。 そのため、ボックス内の項目のインデックスを変更することができますが、ポインターの信頼性を維持します。  
  
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
 *nIndex*  
 リスト項目の高さまたはコンボ ボックスの編集コントロール (または静的なテキスト) の部分の高さが設定されているかどうかを指定します。  
  
 コンボ ボックスがある場合、 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル、 *nIndex*の高さは、それ以外の設定をリスト項目の 0 から始まるインデックスを指定します*nIndex* 0 でなければなりませんすべてのリスト アイテムの高さが設定されます。  
  
 場合*nIndex* -1 で、編集コントロールの高さまたはコンボ ボックスの静的なテキスト部分を設定します。  
  
 *cyItemHeight*  
 高さを指定します (ピクセル単位) で識別される、コンボ ボックス コンポーネントの*nIndex*です。  
  
### <a name="return-value"></a>戻り値  
 **CB_ERR**インデックスまたは高さが無効です。 それ以外の場合 0 の場合。  
  
### <a name="remarks"></a>Remarks  
 コンボ ボックスの編集コントロール (または静的なテキスト) の部分の高さは、リスト項目の高さとは無関係に設定されます。 アプリケーションする必要がありますいないことを確認、編集コントロール (または静的なテキスト) 部分の高さ、特定のリスト ボックス項目の高さよりも小さいです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]  
  
##  <a name="setlocale"></a>  CComboBox::SetLocale  
 このコンボ ボックスのロケール識別子を設定します。  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>パラメーター  
 *nNewLocale*  
 コンボ ボックスに設定する新しい値のロケール識別子 (LCID)。  
  
### <a name="return-value"></a>戻り値  
 このコンボ ボックスの以前のロケール識別子 (LCID) 値です。  
  
### <a name="remarks"></a>Remarks  
 場合**setlocale、_wsetlocale**は呼び出されません、既定のロケールは、システムから取得します。 コントロール パネルを使用してこのシステムの既定のロケールを変更できる地域 (または国際) アプリケーションです。  
  
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
|[in]*iMinVisible*|表示されている項目の最小数を指定します。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [CB_SETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義*m_combobox*、つまり、コンボ ボックス コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>例  
 次のコード例では、コンボ ボックス コントロールのドロップダウン リストに 20 個のアイテムを挿入します。 ドロップダウン矢印を押すと、少なくとも 10 個のアイテムが表示されることを指定します。  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="settopindex"></a>  CComboBox::SetTopIndex  
 特定のアイテムが、リスト ボックス、コンボ ボックスの部分に表示されていることを確認します。  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 リスト ボックス項目の 0 から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、0 または**CB_ERR**場合は、エラーが発生します。  
  
### <a name="remarks"></a>Remarks  
 システムによって指定された項目まで、リスト ボックスをスクロールする*nIndex*が表示されます、一覧の上部にあるボックスまたは最大スクロールの範囲に達しています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]  
  
##  <a name="showdropdown"></a>  CComboBox::ShowDropDown  
 表示またはがコンボ ボックスのリスト ボックスを非表示、 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)または[CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。  
  
```  
void ShowDropDown(BOOL bShowIt = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShowIt*  
 ドロップダウン リスト ボックスを表示するか非表示にするかどうかを指定します。 値**TRUE**リスト ボックスを表示します。 値**FALSE**リスト ボックスを非表示にします。  
  
### <a name="remarks"></a>Remarks  
 既定では、このスタイルのコンボ ボックスは、リスト ボックスに表示されます。  
  
 このメンバー関数も何も起こりませんで作成されたコンボ ボックスに、 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)スタイル。  
  
### <a name="example"></a>例  
  例を参照して[CComboBox::GetDroppedState](#getdroppedstate)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [関数クラス](../../mfc/reference/cscrollbar-class.md)   
 [CStatic クラス](../../mfc/reference/cstatic-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)
