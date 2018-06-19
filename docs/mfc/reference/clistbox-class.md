---
title: CListBox クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1101e4115efa3c5c822d0d64b767cdee379a0e0b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377837"
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
|[CListBox::CharToItem](#chartoitem)|ユーザー設定を提供する上書き`WM_CHAR`文字列を持たないオーナー描画リスト ボックスの処理です。|  
|[CListBox::CompareItem](#compareitem)|新しい項目の並べ替えられたオーナー描画リスト ボックス内の位置を決定するためにフレームワークによって呼び出されます。|  
|[CListBox::Create](#create)|Windows のリスト ボックスを作成しにアタッチ、`CListBox`オブジェクト。|  
|[CListBox::DeleteItem](#deleteitem)|ユーザーがオーナー描画リスト ボックスから項目を削除するときに、フレームワークによって呼び出されます。|  
|[CListBox::DeleteString](#deletestring)|リスト ボックスから文字列を削除します。|  
|[CListBox::Dir](#dir)|リスト ボックスに、ファイル名、ドライブ、またはその両方、現在のディレクトリからを追加します。|  
|[CListBox::DrawItem](#drawitem)|オーナー描画リスト ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。|  
|[CListBox::FindString](#findstring)|リスト ボックスに文字列を検索します。|  
|[CListBox::FindStringExact](#findstringexact)|指定した文字列と一致する最初のボックスの一覧で文字列を検索します。|  
|[CListBox::GetAnchorIndex](#getanchorindex)|リスト ボックス内の現在のアンカー項目の 0 から始まるインデックスを取得します。|  
|[CListBox::GetCaretIndex](#getcaretindex)|複数選択のリスト ボックスにフォーカス四角形を持つ項目のインデックスを決定します。|  
|[CListBox::GetCount](#getcount)|リスト ボックスに文字列の数を返します。|  
|[CListBox::GetCurSel](#getcursel)|リスト ボックスで現在選択されている文字列の 0 から始まるインデックスを返します。|  
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|リスト ボックスを水平方向にスクロールできることをピクセル単位の幅を返します。|  
|[CListBox::GetItemData](#getitemdata)|リスト ボックスの項目に関連付けられている 32 ビット値を返します。|  
|[CListBox::GetItemDataPtr](#getitemdataptr)|リスト ボックスの項目へのポインターを返します。|  
|[CListBox::GetItemHeight](#getitemheight)|リスト ボックス内の項目の高さを決定します。|  
|[CListBox::GetItemRect](#getitemrect)|現在表示されて、リスト ボックス項目の外接する四角形を返します。|  
|[CListBox::GetListBoxInfo](#getlistboxinfo)|各列の項目の数を取得します。|  
|[CListBox::GetLocale](#getlocale)|リスト ボックスのロケール識別子を取得します。|  
|[CListBox::GetSel](#getsel)|リスト ボックス項目の選択状態を返します。|  
|[CListBox::GetSelCount](#getselcount)|複数選択のリスト ボックスで現在選択されている文字列の数を返します。|  
|[CListBox::GetSelItems](#getselitems)|リスト ボックスで現在選択されている文字列のインデックスを返します。|  
|[CListBox::GetText](#gettext)|バッファーには、リスト ボックス項目をコピーします。|  
|[CListBox::GetTextLen](#gettextlen)|リスト ボックス項目のバイト単位の長さを返します。|  
|[CListBox::GetTopIndex](#gettopindex)|リスト ボックスに表示される文字列の最初のインデックスを返します。|  
|[CListBox::InitStorage](#initstorage)|リスト ボックス項目と文字列のメモリのブロックに事前に割り当てます。|  
|[CListBox::InsertString](#insertstring)|リスト ボックス内の特定の場所に文字列を挿入します。|  
|[CListBox::ItemFromPoint](#itemfrompoint)|点に最も近いボックスの一覧で項目のインデックスを返します。|  
|[CListBox::MeasureItem](#measureitem)|オーナー描画リスト ボックスがリスト ボックスのサイズを調べるために作成されるときに、フレームワークによって呼び出されます。|  
|[中](#resetcontent)|リスト ボックスからのすべてのエントリをクリアします。|  
|[CListBox::SelectString](#selectstring)|検索し、単一選択のリスト ボックスの文字列を選択します。|  
|[CListBox::SelItemRange](#selitemrange)|選択または複数選択のリスト ボックス内の文字列の範囲の選択を解除します。|  
|[CListBox::SetAnchorIndex](#setanchorindex)|拡張の選択を開始するための複数選択のリスト ボックスで、アンカーを設定します。|  
|[CListBox::SetCaretIndex](#setcaretindex)|指定したインデックス位置にある項目を複数選択のリスト ボックスにフォーカス四角形を設定します。|  
|[CListBox::SetColumnWidth](#setcolumnwidth)|複数列のリスト ボックスの列の幅を設定します。|  
|[CListBox::SetCurSel](#setcursel)|リスト ボックスの文字列を選択します。|  
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|リスト ボックスを水平方向にスクロールできることをピクセル単位の幅を設定します。|  
|[CListBox::SetItemData](#setitemdata)|リスト ボックスの項目に関連付けられている 32 ビット値を設定します。|  
|[CListBox::SetItemDataPtr](#setitemdataptr)|リスト ボックスの項目へのポインターを設定します。|  
|[CListBox::SetItemHeight](#setitemheight)|リスト ボックス内のアイテムの高さを設定します。|  
|[CListBox::SetLocale](#setlocale)|リスト ボックスのロケール識別子を設定します。|  
|[CListBox::SetSel](#setsel)|選択または複数選択のリスト ボックスで、ボックスの一覧で項目の選択を解除します。|  
|[CListBox::SetTabStops](#settabstops)|リスト ボックスのタブ ストップの位置を設定します。|  
|[CListBox::SetTopIndex](#settopindex)|リスト ボックスに表示される文字列の最初の 0 から始まるインデックスを設定します。|  
|[CListBox::VKeyToItem](#vkeytoitem)|ユーザー設定を提供する上書き`WM_KEYDOWN`とリスト ボックスの処理、 **LBS_WANTKEYBOARDINPUT**セットのスタイルを設定します。|  
  
## <a name="remarks"></a>コメント  
 リスト ボックスには、ユーザーが表示して選択し、ファイル名などのアイテムの一覧が表示されます。  
  
 単一選択のリスト ボックスでは、ユーザーは、1 つだけの項目を選択できます。 複数選択のリスト ボックスでは、項目の範囲を選択することができます。 ユーザーは、項目を選択してが強調表示されて、リスト ボックスは、親ウィンドウへ通知メッセージが送信されます。  
  
 リスト ボックスは、ダイアログ テンプレートから、またはコードで直接作成できます。 直接作成するには、構築、`CListBox`オブジェクト、し、呼び出し、[作成](#create)Windows リスト ボックス コントロールを作成し、アタッチにメンバー関数、`CListBox`オブジェクト。 ダイアログ テンプレートでリスト ボックスを使用するのには、ダイアログ ボックス クラスでボックスの一覧で変数を宣言しを使用して`DDX_Control` ダイアログ ボックス クラスで`DoDataExchange`コントロールにメンバー変数を接続する関数。 (これを自動的に、ダイアログ ボックス クラスをコントロール変数を追加するとします。)  
  
 派生したクラスで、1 つプロセスは、構築`CListBox`です。 呼び出しと派生クラスのコンス トラクターを記述**作成**から、コンス トラクター内で。  
  
 リスト ボックスからその親に送信される Windows の通知メッセージを処理する場合 (通常から派生したクラス[CDialog](../../mfc/reference/cdialog-class.md))、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。  
  
 各メッセージ マップ エントリは次の形式になります。  
  
 `ON_Notification( id, memberFxn )`  
  
 ここで`id`通知を送信するリスト ボックス コントロールの子ウィンドウ ID を指定し、`memberFxn`通知の処理を記述した親メンバー関数の名前を指定します。  
  
 親の関数プロトタイプは次のとおりです。  
  
 `afx_msg void memberFxn( );`  
  
 潜在的なメッセージ マップ エントリと親に送信する場合の説明の一覧を次に示します。  
  
- **ON_LBN_DBLCLK**ユーザーがリスト ボックスに文字列をダブルクリックします。 リスト ボックスにのみ、 [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルがこの通知メッセージを送信します。  
  
- **ON_LBN_ERRSPACE**リスト ボックスは、要求を満たすために十分なメモリを割り当てることができません。  
  
- **ON_LBN_KILLFOCUS**リスト ボックスが入力フォーカスを失います。  
  
- **ON_LBN_SELCANCEL**現在のリスト ボックスの選択が取り消されました。 リスト ボックスがある場合にのみ、このメッセージが送信、 **LBS_NOTIFY**スタイル。  
  
- **ON_LBN_SELCHANGE**リスト ボックス内の選択が変更されました。 によって、選択が変更された場合、この通知は送信されません、 [CListBox::SetCurSel](#setcursel)メンバー関数。 この通知があるリスト ボックスにのみ適用されます、 **LBS_NOTIFY**スタイル。 **LBN_SELCHANGE**通知メッセージが送信される複数選択のリスト ボックスのユーザーが、方向キーを押したときに選択範囲が変更されていない場合でもです。  
  
- **ON_LBN_SETFOCUS**リスト ボックスが入力フォーカスを受信します。  
  
- **ON_WM_CHARTOITEM**文字列がないオーナー描画リスト ボックスの受信、`WM_CHAR`メッセージ。  
  
- **ON_WM_VKEYTOITEM**でリスト ボックス、 **LBS_WANTKEYBOARDINPUT**スタイルを受け取る、`WM_KEYDOWN`メッセージ。  
  
 作成する場合、 `CListBox` (ダイアログ リソースを使って)、ダイアログ ボックス内のオブジェクト、 `CListBox`  ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CListBox`オブジェクトを破棄する必要があります、ウィンドウ内で、`CListBox`オブジェクト。 作成する場合、`CListBox`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CListBox`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**をユーザーが、親ウィンドウを閉じるときに破棄するオブジェクト。  
  
 メモリを割り当てる場合、`CListBox`オブジェクト、オーバーライド、`CListBox`デストラクターが、割り当てを破棄します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="addstring"></a>  CListBox::AddString  
 リスト ボックスに文字列を追加します。  
  
```  
int AddString(LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszItem`  
 追加するのには、null で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の文字列の 0 から始まるインデックス。 戻り値は**返します**エラーが発生した場合、戻り値は**返します**新しい文字列を保存する十分な空き領域がある場合。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスで作成されなかった場合、 [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル、文字列は、リストの末尾に追加されます。 それ以外の場合、リストに、文字列が挿入され、一覧が並べ替えられます。 リスト ボックスの作成時の**LBS_SORT**スタイルを設定しない場合は、 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル、フレームワーク リストを並べ替えます、1 つまたは複数の呼び出しで、`CompareItem`メンバー関数。  
  
 使用して[InsertString](#insertstring)リスト ボックス内の指定位置に文字列を挿入します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]  
  
##  <a name="chartoitem"></a>  CListBox::CharToItem  
 リスト ボックスの親ウィンドウがときに、フレームワークによって呼び出されます、`WM_CHARTOITEM`リスト ボックスからのメッセージ。  
  
```  
virtual int CharToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nKey`  
 ユーザーが入力した文字の ANSI コード。  
  
 `nIndex`  
 ボックスの一覧でのキャレットの現在の位置。  
  
### <a name="return-value"></a>戻り値  
 返します - 1 または 2 の操作はこれ以上またはキーストロークの既定のアクションを実行する対象のリスト ボックス項目のインデックスを指定する負でない数値。 既定の実装では 1 を返します。  
  
### <a name="remarks"></a>コメント  
 `WM_CHARTOITEM`を受信すると、リスト ボックスによってメッセージが送信される、`WM_CHAR`のみ場合、リスト ボックスをすべて満たしているこれらの条件が、メッセージ。  
  
-   オーナー描画リスト ボックスがあります。  
  
-   [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)セットのスタイルを設定します。  
  
-   少なくとも 1 つの項目があります。  
  
 必要がありますしないこの関数を呼び出す自分でします。 キーボード メッセージの独自のカスタム処理を指定するには、この関数をオーバーライドします。  
  
 オーバーライドの中では、フレームワークに知らせますを実行したアクション値を返す必要があります。 戻り値 1 または 2 を示す項目の選択のすべての側面を処理し、リスト ボックスで、これ以上操作は必要ありません。 -を返す前に 1 または 2、またはすることが選択範囲を設定、カレットを移動します。 選択範囲を設定するには、使用[SetCurSel](#setcursel)または[SetSel](#setsel)です。 カレットを移動するには使用[には](#setcaretindex)します。  
  
 0 以上の戻り値は、リスト ボックスで、項目のインデックスを指定し、リスト ボックスがで指定したアイテムのキーストロークの既定のアクションを実行する必要がありますを示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]  
  
##  <a name="clistbox"></a>  CListBox::CListBox  
 `CListBox` オブジェクトを構築します。  
  
```  
CListBox();
```  
  
### <a name="remarks"></a>コメント  
 構築する、 `CListBox` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出す**ClistBox**し**作成**、Windows のリスト ボックスを初期化しにアタッチする、`CListBox`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]  
  
##  <a name="compareitem"></a>  CListBox::CompareItem  
 並べ替えられたオーナー描画リスト ボックスに新しい項目の相対位置を決定するためにフレームワークによって呼び出されます。  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCompareItemStruct`  
 Long ポインター、`COMPAREITEMSTRUCT`構造体。  
  
### <a name="return-value"></a>戻り値  
 説明されている 2 つの項目の相対位置を示す、 [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md)構造体。 次の値のいずれかがある可能性があります。  
  
|[値]|説明|  
|-----------|-------------|  
|-1|項目 1 は項目 2 の前に並べ替えます。|  
|0|アイテム 1 と 2 のアイテムは、同じを並べ替えます。|  
|1|項目 1 は項目 2 の後に並べ替えられます。|  
  
 参照してください[CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)の詳細については、`COMPAREITEMSTRUCT`構造体。  
  
### <a name="remarks"></a>コメント  
 既定では、このメンバー関数では何も行いません。 オーナー描画リスト ボックスを作成するかどうか、 **LBS_SORT**スタイル、リスト ボックスに追加された新しい項目の並べ替え中に、フレームワークを支援するためにこのメンバー関数をオーバーライドする必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]  
  
##  <a name="create"></a>  CListBox::Create  
 Windows のリスト ボックスを作成しにアタッチ、`CListBox`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 リスト ボックスのスタイルを指定します。 任意の組み合わせを適用[リスト ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)をボックスにします。  
  
 `rect`  
 リスト ボックスのサイズと位置を指定します。 いずれかになります、`CRect`オブジェクトまたは`RECT`構造体。  
  
 `pParentWnd`  
 リスト ボックスの親ウィンドウを指定します (通常、`CDialog`オブジェクト)。 なければなりません**NULL**です。  
  
 `nID`  
 リスト ボックスのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CListBox` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出す**作成**、Windows のリスト ボックスを初期化しにアタッチする、`CListBox`オブジェクト。  
  
 ときに**作成**を実行する Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[wm _ で始まるGETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)リスト ボックス コントロールへのメッセージ。  
  
 既定では、これらのメッセージが処理されます、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数`CWnd`基本クラスです。 既定のメッセージ処理を拡張するには、派生クラスを`CListBox`メッセージ マップを新しいクラスに追加し、前のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)をリスト ボックス コントロールです。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_VSCROLL**垂直スクロール バーを追加するには  
  
- **WS_HSCROLL**水平スクロール バーを追加するには  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**コントロールのタブ オーダーを許可するには  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]  
  
##  <a name="deleteitem"></a>  CListBox::DeleteItem  
 ユーザーがオーナー描画から項目を削除したときに、フレームワークによって呼び出されます`CListBox`オブジェクト、またはリスト ボックスを破棄します。  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDeleteItemStruct`  
 Windows への long ポインター [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md)削除された項目に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 必要に応じてのオーナー描画リスト ボックスを再描画するには、この関数をオーバーライドします。  
  
 参照してください[構造体](../../mfc/reference/cwnd-class.md#ondeleteitem)の詳細については、`DELETEITEMSTRUCT`構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]  
  
##  <a name="deletestring"></a>  CListBox::DeleteString  
 位置に項目を削除します`nIndex`リスト ボックスからです。  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除する文字列の 0 から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 一覧に残っている文字列の数。 戻り値は**返します**場合`nIndex`リスト内の項目数より大きいインデックスを指定します。  
  
### <a name="remarks"></a>コメント  
 次のすべての項目`nIndex`で 1 つ下に移動します。 たとえば、リスト ボックスに 2 つの項目が含まれている場合の最初の項目を削除できるようになります、残りの項目に最初の位置になります。 `nIndex`最初の位置の項目の 0 を = です。  
  
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
 `attr`  
 任意の組み合わせにでき、`enum`で説明されている値**CFile::GetStatu**[s](../../mfc/reference/cfile-class.md#getstatus)、または、次の値の任意の組み合わせ。  
  
|[値]|説明|  
|-----------|-------------|  
|0x0000|ファイルからの読み取りまたはに書き込まれることができます。|  
|0x0001|ファイルからの読み取りに書き込まれないことができます。|  
|0x0002|ファイルは、非表示には、ディレクトリの一覧に表示されません。|  
|0x0004|ファイルは、システム ファイルです。|  
|0x0010|指定した名前`lpszWildCard`ディレクトリを指定します。|  
|0x0020|ファイルがアーカイブされています。|  
|0x4000|指定された名前と一致するすべてのドライブに含める`lpszWildCard`です。|  
|0x8000|排他フラグ。 排他フラグが設定されている場合は、指定した種類のファイルのみが一覧表示されます。 それ以外の場合、「通常」のファイルだけでなく、指定した種類のファイルが一覧表示されます。|  
  
 `lpszWildCard`  
 ファイルの仕様の文字列を指します。 文字列は、ワイルドカードを含めることができます (たとえば、*.\*)。  
  
### <a name="return-value"></a>戻り値  
 一覧に追加された最後のファイル名の 0 から始まるインデックス。 戻り値は**返します**エラーが発生した場合、戻り値は**返します**十分な空き領域がある新しい文字列を格納する場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]  
  
##  <a name="drawitem"></a>  CListBox::DrawItem  
 オーナー描画リスト ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 Long ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**と**itemState**のメンバー、`DRAWITEMSTRUCT`構造体は、実行するのには、描画の動作を定義します。  
  
 既定では、このメンバー関数では何も行いません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CListBox`オブジェクト。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`関数はこのメンバーの前に終了します。  
  
 参照してください[体](../../mfc/reference/cwnd-class.md#ondrawitem)の詳細については、`DRAWITEMSTRUCT`構造体。  
  
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
 `nStartAfter`  
 最初の項目を検索する前に、の項目の 0 から始まるインデックスが含まれています。 指定した項目に、リスト ボックスの上部から続行検索では、リスト ボックスの下部に達すると、`nStartAfter`です。 場合`nStartAfter`-1 で、リスト ボックス全体が先頭から検索します。  
  
 `lpszItem`  
 検索対象のプレフィックスを表す null で終わる文字列へのポインター。 検索では独立しており、ケース、ため、この文字列は、任意の大文字と小文字を含めることができます。  
  
### <a name="return-value"></a>戻り値  
 一致する項目の 0 から始まるインデックス、または**返します**検索が成功した場合。  
  
### <a name="remarks"></a>コメント  
 使用して、 [SelectString](#selectstring)メンバー関数を検索して、文字列を選択します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]  
  
##  <a name="findstringexact"></a>  CListBox::FindStringExact  
 指定した文字列に一致する最初のボックスの一覧で文字列を検索`lpszFind`です。  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndexStart`  
 最初の項目を検索する前に、の項目の 0 から始まるインデックスを指定します。 指定した項目に、リスト ボックスの上部から続行検索では、リスト ボックスの下部に達すると、`nIndexStart`です。 場合`nIndexStart`-1 で、リスト ボックス全体が先頭から検索します。  
  
 `lpszFind`  
 検索する null で終わる文字列へのポインター。 この文字列は、拡張子を含む、完全なファイル名を含めることができます。 検索では、文字列は、任意の大文字と小文字を含めることができますので、大文字と小文字が区別されません。  
  
### <a name="return-value"></a>戻り値  
 一致する項目のインデックスまたは**返します**検索が成功した場合。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスがオーナー描画スタイルで作成された場合、 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル、`FindStringExact`メンバー関数の値に対してダブルワード値を一致させようとしています。`lpszFind`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]  
  
##  <a name="getanchorindex"></a>  CListBox::GetAnchorIndex  
 リスト ボックスで、現在のアンカー項目の 0 から始まるインデックスを取得します。  
  
```  
int GetAnchorIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は現在のアンカー項目のインデックスそれ以外の場合**返します**です。  
  
### <a name="remarks"></a>コメント  
 複数選択のリスト ボックスでは、アンカー項目は、最初または最アイテム連続した選択した項目のブロックです。  
  
### <a name="example"></a>例  
  例を参照して[CListBox::SetAnchorIndex](#setanchorindex)です。  
  
##  <a name="getcaretindex"></a>  CListBox::GetCaretIndex  
 複数選択のリスト ボックスにフォーカス四角形を持つ項目のインデックスを決定します。  
  
```  
int GetCaretIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスにフォーカス四角形をされている項目の 0 から始まるインデックス。 単一選択のリスト ボックスをリスト ボックスには、存在する場合、戻り値は、選択されている項目のインデックスです。  
  
### <a name="remarks"></a>コメント  
 項目は、可能性があります。 または選択されていない可能性があります。  
  
### <a name="example"></a>例  
  例を参照して[CListBox::SetCaretIndex](#setcaretindex)です。  
  
##  <a name="getcount"></a>  CListBox::GetCount  
 リスト ボックス内の項目の数を取得します。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の項目の数または**返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 返される数は、1 (インデックスは 0 から始まる) の最後の項目のインデックス値より大きい値です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]  
  
##  <a name="getcursel"></a>  CListBox::GetCurSel  
 単一選択のリスト ボックスで、存在する場合は、現在選択されている項目の 0 から始まるインデックスを取得します。  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 単一選択のリスト ボックスである場合は、現在選択されている項目の 0 から始まるインデックス。 `LB_ERR`項目が選択されていない場合。  
  
 複数選択のリスト ボックスでは、フォーカスがある項目のインデックス。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要はありません`GetCurSel`複数選択のリスト ボックス。 使用して[CListBox::GetSelItems](#getselitems)代わりにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]  
  
##  <a name="gethorizontalextent"></a>  CListBox::GetHorizontalExtent  
 リスト ボックスから、スクロール可能水平方向にピクセル幅の値を取得します。  
  
```  
int GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スクロール可能な (ピクセル単位)、リスト ボックスの幅。  
  
### <a name="remarks"></a>コメント  
 これは、リスト ボックスに水平スクロール バーがある場合にのみ適用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]  
  
##  <a name="getitemdata"></a>  CListBox::GetItemData  
 指定したリスト ボックスの項目に関連付けられているアプリケーションによって提供されるダブルワード値を取得します。  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスで、項目の 0 から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 アイテムに関連付けられている 32 ビット値または**返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 ダブルワード値は、`dwItemData`のパラメーター、 [SetItemData](#setitemdata)呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]  
  
##  <a name="getitemdataptr"></a>  CListBox::GetItemDataPtr  
 ポインターとして指定したリスト ボックスの項目に関連付けられたアプリケーションによって提供される 32 ビット値を取得します ( **void\***)。  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
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
 `nIndex`  
 リスト ボックスで、項目の 0 から始まるインデックスを指定します。 リスト ボックスがある場合にのみ、このパラメーターは使用、 **LBS_OWNERDRAWVARIABLE**スタイルです。 それ以外の場合、0 に設定する必要がありますします。  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の項目のピクセル単位の高さ。 リスト ボックスがある場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル、戻り値で指定した項目の高さ`nIndex`です。 エラーが発生する場合、戻り値は**返します**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]  
  
##  <a name="getitemrect"></a>  CListBox::GetItemRect  
 リスト ボックス ウィンドウに現在表示されている、その境界ボックスの一覧の項目の四角形の寸法を取得します。  
  
```  
int GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 項目の 0 から始まるインデックスを指定します。  
  
 `lpRect`  
 Long ポインターを指定します、 [RECT 構造体](../../mfc/reference/rect-structure1.md)項目のリスト ボックスのクライアント座標を受け取る。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]  
  
##  <a name="getlistboxinfo"></a>  CListBox::GetListBoxInfo  
 各列の項目の数を取得します。  
  
```  
DWORD GetListBoxInfo() const;  
```  
  
### <a name="return-value"></a>戻り値  
 各列の項目の数、`CListBox`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LB_GETLISTBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775208)メッセージ、Windows SDK で説明します。  
  
##  <a name="getlocale"></a>  CListBox::GetLocale  
 リスト ボックスで使用されるロケールを取得します。  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックス内の文字列のロケール識別子 (LCID) 値。  
  
### <a name="remarks"></a>コメント  
 ロケールが使用、たとえば、並べ替えられたリスト ボックス内の文字列の並べ替え順序を決定します。  
  
### <a name="example"></a>例  
  例を参照して[CListBox::SetLocale](#setlocale)です。  
  
##  <a name="getsel"></a>  CListBox::GetSel  
 項目の選択状態を取得します。  
  
```  
int GetSel(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 項目の 0 から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 正の数値を使用している場合は、指定した項目が選択されています。それ以外の場合は 0 です。 戻り値は`LB_ERR`場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、両方単一および複数選択のリスト ボックスで動作します。  
  
 使用して、現在選択されているリスト ボックス項目のインデックスを取得する[CListBox::GetCurSel](#getcursel)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]  
  
##  <a name="getselcount"></a>  CListBox::GetSelCount  
 複数選択のリスト ボックスで選択したアイテムの合計数を取得します。  
  
```  
int GetSelCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスで選択した項目の数。 戻り値は、リスト ボックスが単一選択のリスト ボックスの場合は、**返します**です。  
  
### <a name="example"></a>例  
  例を参照して[CListBox::GetSelItems](#getselitems)です。  
  
##  <a name="getselitems"></a>  CListBox::GetSelItems  
 複数選択のリスト ボックスで選択した項目の項目番号を指定する整数の配列をバッファーに設定します。  
  
```  
int GetSelItems(
    int nMaxItems,  
    LPINT rgIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMaxItems`  
 項目番号が、バッファーに配置するのには、選択した項目の最大数を指定します。  
  
 `rgIndex`  
 指定された整数の数に対して十分な大きさのバッファーを指すポインター`nMaxItems`です。  
  
### <a name="return-value"></a>戻り値  
 実際のアイテムの数は、バッファーに格納します。 戻り値は、リスト ボックスが単一選択のリスト ボックスの場合は、`LB_ERR`です。  
  
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
 `nIndex`  
 取得する文字列の 0 から始まるインデックスを指定します。  
  
 `lpszBuffer`  
 文字列を受け取るバッファーへのポインター。 バッファーには、文字列、終端の null 文字に十分な空き領域が必要です。 呼び出して前もって文字列のサイズを特定できる、`GetTextLen`メンバー関数。  
  
 `rString`  
 `CString` オブジェクトへの参照。  
  
### <a name="return-value"></a>戻り値  
 終端の null 文字を除いた文字列の長さをバイト単位で。 場合`nIndex`有効なインデックスが指定されていません、戻り値は**返します**です。  
  
### <a name="remarks"></a>コメント  
 このメンバーの 2 番目の形式の関数がいっぱいになった、`CString`文字列のテキストを持つオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]  
  
##  <a name="gettextlen"></a>  CListBox::GetTextLen  
 リスト ボックス項目内の文字列の長さを取得します。  
  
```  
int GetTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 文字列の 0 から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 文字列の終端の null 文字を除く、文字の長さ。 場合`nIndex`有効なインデックスが指定されていません、戻り値は**返します**です。  
  
### <a name="example"></a>例  
  例を参照して[CListBox::GetText](#gettext)です。  
  
##  <a name="gettopindex"></a>  CListBox::GetTopIndex  
 リスト ボックスで、最初に表示される項目の 0 から始まるインデックスを取得します。  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、リスト ボックスに表示される最初の項目の 0 から始まるインデックス**返します**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 最初に、リスト ボックスの上部にある項目の 0 が上部にある別のアイテムがありますが、リスト ボックスをスクロールすると場合、。  
  
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
 `nItems`  
 追加する項目の数を指定します。  
  
 `nBytes`  
 割り当てるバイト数、項目の文字列では、メモリの量を指定します。  
  
### <a name="return-value"></a>戻り値  
 かどうか、成功、項目の最大数をメモリを再割り当てが必要とせずに、それ以外の場合に格納できるリスト ボックス**返します**、十分なメモリの意味があります。  
  
### <a name="remarks"></a>コメント  
 多数の項目を追加する前にこの関数を呼び出して、`CListBox`です。  
  
 この関数は、多数のアイテム (100 より大きい) を持つリスト ボックスの初期化を高速化に役立ちます。 指定されたため、その後のメモリ量を事前に割り当てます[AddString](#addstring)、 [InsertString](#insertstring)、および[Dir](#dir)関数は、最短時間を取得します。 パラメーターの見積もりを行うこともできます。 過大評価していない、余分なメモリが割り当てられます。過小を評価するには、事前に割り当てられた量を超えているアイテムの通常の割り当てが使用されます。  
  
 Windows 95/98 のみ:`nItems`パラメーターは 16 ビット値に制限されます。 つまり、リスト ボックスは、32,767 を超える項目を含めることはできません。 項目の数が制限されているが、リスト ボックス内の項目の合計サイズが使用可能なメモリによってのみ制限されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]  
  
##  <a name="insertstring"></a>  CListBox::InsertString  
 リスト ボックスに文字列を挿入します。  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 文字列を挿入する位置の 0 から始まるインデックスを指定します。 このパラメーターが-1 の場合、文字列はリストの末尾に追加されます。  
  
 `lpszItem`  
 挿入される null で終わる文字列を指します。  
  
### <a name="return-value"></a>戻り値  
 文字列が挿入された位置の 0 から始まるインデックス。 戻り値は**返します**エラーが発生した場合、戻り値は**返します**新しい文字列を保存する十分な空き領域がある場合。  
  
### <a name="remarks"></a>コメント  
 異なり、 [AddString](#addstring)メンバー関数は、`InsertString`と一覧は行われません、 [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)並べ替えスタイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]  
  
##  <a name="itemfrompoint"></a>  CListBox::ItemFromPoint  
 指定した位置に最も近いリスト ボックス項目を決定`pt`です。  
  
```  
UINT ItemFromPoint(
    CPoint pt,  
    BOOL& bOutside) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 リスト ボックスのクライアント領域の左上隅に対して相対的に指定された、最も近い項目を検索する対象のポイント。  
  
 `bOutside`  
 参照、`BOOL`変数に設定されますを`TRUE`場合`pt`が、最も近いリスト ボックス項目のクライアント領域の範囲外`FALSE`場合`pt`は最も近いリスト ボックス項目のクライアント領域の内側です。  
  
### <a name="return-value"></a>戻り値  
 指定した位置に最も近い項目のインデックス`pt`です。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して、上にマウス カーソルが移動リスト ボックス項目を特定します。  
  
### <a name="example"></a>例  
  例を参照して[CListBox::SetAnchorIndex](#setanchorindex)です。  
  
##  <a name="measureitem"></a>  CListBox::MeasureItem  
 オーナー描画スタイルをリスト ボックスが作成されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMeasureItemStruct`  
 Long ポインター、 [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 既定では、このメンバー関数では何も行いません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`構造体、リスト ボックスのサイズの Windows に通知します。 リスト ボックスが作成された場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)リスト ボックス内の各項目のスタイル、フレームワークからこのメンバー関数。 それ以外の場合、このメンバーは、1 回だけ呼び出されます。  
  
 使用しての詳細については、 [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルで作成されたオーナー描画リスト ボックスで、`SubclassDlgItem`のメンバー関数`CWnd`の説明を参照[テクニカル ノート 14: カスタム](../../mfc/tn014-custom-controls.md).  
  
 参照してください[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)の詳細については、`MEASUREITEMSTRUCT`構造**です。**  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]  
  
##  <a name="resetcontent"></a>  中  
 リスト ボックスからすべての項目を削除します。  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]  
  
##  <a name="selectstring"></a>  CListBox::SelectString  
 検索ボックスの一覧で項目の指定した文字列に一致して、一致する項目が見つかった場合、その項目を選択します。  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStartAfter`  
 最初の項目を検索する前に、の項目の 0 から始まるインデックスが含まれています。 指定した項目に、リスト ボックスの上部から続行検索では、リスト ボックスの下部に達すると、`nStartAfter`です。 場合`nStartAfter`-1 で、リスト ボックス全体が先頭から検索します。  
  
 `lpszItem`  
 検索対象のプレフィックスを表す null で終わる文字列へのポインター。 検索では独立しており、ケース、ため、この文字列は、任意の大文字と小文字を含めることができます。  
  
### <a name="return-value"></a>戻り値  
 検索が成功した場合は、選択した項目のインデックス。 検索が成功しなかった場合、戻り値は**返します**現在の選択は変更されません。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスをスクロールすると、必要に応じて、選択した項目を表示します。  
  
 リスト ボックスで、このメンバー関数は使用できません、 [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル。  
  
 項目を選択すると、その文字列の開始点) で指定された文字列内の文字を一致する場合にのみ`lpszItem`です。  
  
 使用して、`FindString`項目を選択せずに文字列を検索するメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]  
  
##  <a name="selitemrange"></a>  CListBox::SelItemRange  
 複数選択のリスト ボックス内の複数の連続した項目を選択します。  
  
```  
int SelItemRange(
    BOOL bSelect,  
    int nFirstItem,  
    int nLastItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `bSelect`  
 選択範囲を設定する方法を指定します。 場合`bSelect`は**TRUE**、文字列が選択され強調表示される場合**FALSE**、強調表示が削除され、文字列が選択されていません。  
  
 `nFirstItem`  
 設定する最初の項目の 0 から始まるインデックスを指定します。  
  
 `nLastItem`  
 設定する最後の項目の 0 から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を複数選択のリスト ボックスでのみ使用します。 複数選択のリスト ボックスで 1 つの項目を選択する必要がある場合などは場合、`nFirstItem`と等しい`nLastItem`— を呼び出す、 [SetSel](#setsel)メンバー関数を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]  
  
##  <a name="setanchorindex"></a>  CListBox::SetAnchorIndex  
 拡張の選択を開始するための複数選択のリスト ボックスで、アンカーを設定します。  
  
```  
void SetAnchorIndex(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 アンカーとなるリスト ボックス項目の 0 から始まるインデックスを指定します。  
  
### <a name="remarks"></a>コメント  
 複数選択のリスト ボックスでは、アンカー項目は、最初または最アイテム連続した選択した項目のブロックです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]  
  
##  <a name="setcaretindex"></a>  CListBox::SetCaretIndex  
 指定したインデックス位置にある項目を複数選択のリスト ボックスにフォーカス四角形を設定します。  
  
```  
int SetCaretIndex(
    int nIndex,  
    BOOL bScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスにフォーカス四角形を表示する項目の 0 から始まるインデックスを指定します。  
  
 *bScroll*  
 この値が 0 の場合は、完全に表示されるまで、その項目がスクロールします。 この値がない場合 0 の場合、項目がスクロールが部分的に表示されるには、少なくともになるまでです。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 項目が表示されていない場合は、スクロールして表示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]  
  
##  <a name="setcolumnwidth"></a>  CListBox::SetColumnWidth  
 複数列のリスト ボックス内のすべての列のピクセル単位の幅を設定 (で作成された、 [LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル)。  
  
```  
void SetColumnWidth(int cxWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 `cxWidth`  
 すべての列のピクセル単位の幅を指定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]  
  
##  <a name="setcursel"></a>  CListBox::SetCurSel  
 文字列を選択し、必要な場合は、ビューにスクロールします。  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSelect`  
 選択する文字列の 0 から始まるインデックスを指定します。 場合`nSelect`-1 で、選択範囲がないように、リスト ボックスを設定します。  
  
### <a name="return-value"></a>戻り値  
 `LB_ERR` 場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 新しい文字列を選択すると、リスト ボックスは選択されていた文字列から強調表示を削除します。  
  
 このメンバー関数は、単一選択のリスト ボックスでのみ使用します。  
  
 を設定または複数選択のリスト ボックスで、選択範囲を削除するには使用[CListBox::SetSel](#setsel)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]  
  
##  <a name="sethorizontalextent"></a>  CListBox::SetHorizontalExtent  
 (ピクセル単位) をリスト ボックスを水平にスクロールすることができます、幅を設定します。  
  
```  
void SetHorizontalExtent(int cxExtent);
```  
  
### <a name="parameters"></a>パラメーター  
 *cxExtent*  
 これによって、リスト ボックスを水平にスクロールすることができますのピクセル数を指定します。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスのサイズがこの値よりも小さい場合は、水平スクロール バーはリスト ボックス内の項目を水平にスクロールします。 リスト ボックスは、大規模なまたはこの値より大きいと、水平スクロール バーが表示されます。  
  
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
 `nIndex`  
 項目の 0 から始まるインデックスを指定します。  
  
 `dwItemData`  
 項目に関連付けられる値を指定します。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]  
  
##  <a name="setitemdataptr"></a>  CListBox::SetItemDataPtr  
 指定したポインターであるリスト ボックスで指定した項目に関連付けられている 32 ビット値の設定 ( **void\***)。  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 項目の 0 から始まるインデックスを指定します。  
  
 `pData`  
 アイテムに関連付けられるへのポインターを指定します。  
  
### <a name="return-value"></a>戻り値  
 **返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 このポインターは項目が追加または削除されるリスト ボックス内の項目の相対位置を変更する可能性がある場合でも、リスト ボックスの有効期間有効です。 そのため、ボックス内の項目のインデックスを変更することができますが、ポインターの信頼性を維持します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]  
  
##  <a name="setitemheight"></a>  CListBox::SetItemHeight  
 リスト ボックス内のアイテムの高さを設定します。  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスで、項目の 0 から始まるインデックスを指定します。 リスト ボックスがある場合にのみ、このパラメーターは使用、 **LBS_OWNERDRAWVARIABLE**スタイルです。 それ以外の場合、0 に設定する必要がありますします。  
  
 `cyItemHeight`  
 (ピクセル単位)、項目の高さを指定します。  
  
### <a name="return-value"></a>戻り値  
 **返します**インデックスまたは高さが有効でない場合。  
  
### <a name="remarks"></a>コメント  
 リスト ボックスがある場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル、この関数は設定で指定した項目の高さ`nIndex`です。 それ以外の場合、この関数は、リスト ボックスですべてのアイテムの高さを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]  
  
##  <a name="setlocale"></a>  CListBox::SetLocale  
 このリスト ボックスのロケール識別子を設定します。  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewLocale`  
 リスト ボックスに設定する新しい値のロケール識別子 (LCID)。  
  
### <a name="return-value"></a>戻り値  
 このリスト ボックスの以前のロケール識別子 (LCID) 値です。  
  
### <a name="remarks"></a>コメント  
 場合**setlocale、_wsetlocale**は呼び出されません、既定のロケールは、システムから取得します。 コントロール パネルを使用してこのシステムの既定のロケールを変更できる地域 (または国際) アプリケーションです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]  
  
##  <a name="setsel"></a>  CListBox::SetSel  
 複数選択のリスト ボックスの文字列を選択します。  
  
```  
int SetSel(
    int nIndex,  
    BOOL bSelect = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 設定する文字列の 0 から始まるインデックスが含まれています。 かどうかは-1 で、選択範囲が追加または削除の値に応じて、すべての文字列から`bSelect`です。  
  
 `bSelect`  
 選択範囲を設定する方法を指定します。 場合`bSelect`は`TRUE`、文字列が選択され強調表示される場合`FALSE`、強調表示が削除され、文字列が選択されていません。 指定した文字列が選択され、既定で強調表示されます。  
  
### <a name="return-value"></a>戻り値  
 `LB_ERR` 場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を複数選択のリスト ボックスでのみ使用します。  
  
 単一選択のリスト ボックスから項目を選択するには[CListBox::SetCurSel](#setcursel)です。  
  
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
 `cxEachStop`  
 タブ ストップはすべて`cxEachStop`ダイアログ単位です。 参照してください*rgTabStops*ダイアログ ユニットの詳細についてはします。  
  
 `nTabStops`  
 リスト ボックスのタブ ストップの数を指定します。  
  
 `rgTabStops`  
 ダイアログ単位でのタブ ストップの位置を表す、整数の配列の最初のメンバーへのポインター。 ダイアログ単位は、水平または垂直距離です。 1 つの水平方向のダイアログ単位は、現在のダイアログ ベースの幅の単位の 4 分の 1 に等しいと 1 つの垂直方向のダイアログ単位は、現在のダイアログ ベースの高さユニットの 8 分の 1 に等しい。 ダイアログの基本単位は、現在のシステム フォントの幅と高さに基づいて計算されます。 **GetDialogBaseUnits** Windows の機能はピクセル単位で現在のダイアログ ボックスの基本単位を返します。 タブ ストップは; 昇順に並べ替える必要があります。バック タブを指定することはできません。  
  
### <a name="return-value"></a>戻り値  
 すべてのタブが設定された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 タブ ストップを 2 つのダイアログ単位の既定のサイズに設定するには、このメンバー関数のパラメーターなしのバージョンを呼び出します。 タブ ストップを 2 以外のサイズを設定するとバージョンを呼び出す、`cxEachStop`引数。  
  
 サイズの配列をタブ ストップを設定するには、バージョンを使用、`rgTabStops`と`nTabStops`引数。 タブ ストップを内の各値の設定は`rgTabStops`で指定された数まで`nTabStops`です。  
  
 呼び出しに応答する、`SetTabStops`メンバー関数の場合、リスト ボックス必要がありますで作成されている、 [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]  
  
##  <a name="settopindex"></a>  CListBox::SetTopIndex  
 特定のリスト ボックス項目が表示されていることを確認します。  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックス項目の 0 から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、0 または**返します**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 システムによって指定された項目まで、リスト ボックスをスクロールする`nIndex`が表示されます、一覧の上部にあるボックスまたは最大スクロールの範囲に達しています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]  
  
##  <a name="vkeytoitem"></a>  CListBox::VKeyToItem  
 リスト ボックスの親ウィンドウがときに、フレームワークによって呼び出されます、`WM_VKEYTOITEM`リスト ボックスからのメッセージ。  
  
```  
virtual int VKeyToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nKey`  
 ユーザーが押されたキーの仮想キー コード。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nIndex`  
 ボックスの一覧でのキャレットの現在の位置。  
  
### <a name="return-value"></a>戻り値  
 返します - 2 以上のアクションを既定のアクションの場合は 1 またはキーストロークの既定のアクションを実行する対象のリスト ボックス項目のインデックスを指定する負でない数値。  
  
### <a name="remarks"></a>コメント  
 `WM_VKEYTOITEM`を受信すると、リスト ボックスによってメッセージが送信される、`WM_KEYDOWN`のみ、リスト ボックス満たしている場合、次の両方が、メッセージ。  
  
-   [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)セットのスタイルを設定します。  
  
-   少なくとも 1 つの項目があります。  
  
 必要がありますしないこの関数を呼び出す自分でします。 キーボード メッセージの独自のカスタム処理を指定するには、この関数をオーバーライドします。  
  
 フレームワークのオーバーライドが実行されるアクションを通知する値を返す必要があります。 戻り値 - 2 は、アプリケーションは、項目の選択のすべての側面を処理し、リスト ボックスで、これ以上操作は必要ありませんを示します。 -2 を返す前に、選択範囲を設定またはカレットを移動することができます。 選択範囲を設定するには、使用[SetCurSel](#setcursel)または[SetSel](#setsel)です。 カレットを移動するには使用[には](#setcaretindex)します。  
  
 戻り値 1 は、キー操作への応答に、リスト ボックスが既定のアクションを実行するかを示します。既定の実装では 1 を返します。  
  
 0 以上の戻り値は、リスト ボックスで、項目のインデックスを指定し、リスト ボックスがで指定したアイテムのキーストロークの既定のアクションを実行する必要がありますを示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLTEST](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [関数クラス](../../mfc/reference/cscrollbar-class.md)   
 [CStatic クラス](../../mfc/reference/cstatic-class.md)
