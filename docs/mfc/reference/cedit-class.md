---
title: CEdit クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CEdit
- AFXWIN/CEdit
- AFXWIN/CEdit::CEdit
- AFXWIN/CEdit::CanUndo
- AFXWIN/CEdit::CharFromPos
- AFXWIN/CEdit::Clear
- AFXWIN/CEdit::Copy
- AFXWIN/CEdit::Create
- AFXWIN/CEdit::Cut
- AFXWIN/CEdit::EmptyUndoBuffer
- AFXWIN/CEdit::FmtLines
- AFXWIN/CEdit::GetCueBanner
- AFXWIN/CEdit::GetFirstVisibleLine
- AFXWIN/CEdit::GetHandle
- AFXWIN/CEdit::GetHighlight
- AFXWIN/CEdit::GetLimitText
- AFXWIN/CEdit::GetLine
- AFXWIN/CEdit::GetLineCount
- AFXWIN/CEdit::GetMargins
- AFXWIN/CEdit::GetModify
- AFXWIN/CEdit::GetPasswordChar
- AFXWIN/CEdit::GetRect
- AFXWIN/CEdit::GetSel
- AFXWIN/CEdit::HideBalloonTip
- AFXWIN/CEdit::LimitText
- AFXWIN/CEdit::LineFromChar
- AFXWIN/CEdit::LineIndex
- AFXWIN/CEdit::LineLength
- AFXWIN/CEdit::LineScroll
- AFXWIN/CEdit::Paste
- AFXWIN/CEdit::PosFromChar
- AFXWIN/CEdit::ReplaceSel
- AFXWIN/CEdit::SetCueBanner
- AFXWIN/CEdit::SetHandle
- AFXWIN/CEdit::SetHighlight
- AFXWIN/CEdit::SetLimitText
- AFXWIN/CEdit::SetMargins
- AFXWIN/CEdit::SetModify
- AFXWIN/CEdit::SetPasswordChar
- AFXWIN/CEdit::SetReadOnly
- AFXWIN/CEdit::SetRect
- AFXWIN/CEdit::SetRectNP
- AFXWIN/CEdit::SetSel
- AFXWIN/CEdit::SetTabStops
- AFXWIN/CEdit::ShowBalloonTip
- AFXWIN/CEdit::Undo
dev_langs:
- C++
helpviewer_keywords:
- CEdit [MFC], CEdit
- CEdit [MFC], CanUndo
- CEdit [MFC], CharFromPos
- CEdit [MFC], Clear
- CEdit [MFC], Copy
- CEdit [MFC], Create
- CEdit [MFC], Cut
- CEdit [MFC], EmptyUndoBuffer
- CEdit [MFC], FmtLines
- CEdit [MFC], GetCueBanner
- CEdit [MFC], GetFirstVisibleLine
- CEdit [MFC], GetHandle
- CEdit [MFC], GetHighlight
- CEdit [MFC], GetLimitText
- CEdit [MFC], GetLine
- CEdit [MFC], GetLineCount
- CEdit [MFC], GetMargins
- CEdit [MFC], GetModify
- CEdit [MFC], GetPasswordChar
- CEdit [MFC], GetRect
- CEdit [MFC], GetSel
- CEdit [MFC], HideBalloonTip
- CEdit [MFC], LimitText
- CEdit [MFC], LineFromChar
- CEdit [MFC], LineIndex
- CEdit [MFC], LineLength
- CEdit [MFC], LineScroll
- CEdit [MFC], Paste
- CEdit [MFC], PosFromChar
- CEdit [MFC], ReplaceSel
- CEdit [MFC], SetCueBanner
- CEdit [MFC], SetHandle
- CEdit [MFC], SetHighlight
- CEdit [MFC], SetLimitText
- CEdit [MFC], SetMargins
- CEdit [MFC], SetModify
- CEdit [MFC], SetPasswordChar
- CEdit [MFC], SetReadOnly
- CEdit [MFC], SetRect
- CEdit [MFC], SetRectNP
- CEdit [MFC], SetSel
- CEdit [MFC], SetTabStops
- CEdit [MFC], ShowBalloonTip
- CEdit [MFC], Undo
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98410fb8b62eb160e21803b60a14ce731ffc8c23
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957456"
---
# <a name="cedit-class"></a>CEdit Class
Windows のエディット コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CEdit : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CEdit::CEdit](#cedit)|構築、`CEdit`コントロール オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CEdit::CanUndo](#canundo)|エディット コントロールの操作が完了できるかどうかを判断します。|  
|[CEdit::CharFromPos](#charfrompos)|指定した位置に最も近い文字の行や文字のインデックスを取得します。|  
|[CEdit::Clear](#clear)|削除 (クリア) 編集の現在の選択 (存在する場合) を制御します。|  
|[CEdit::Copy](#copy)|現在の選択 (もしあれば) エディット コントロールでクリップボードにコピーで**エディット**形式です。|  
|[CEdit::Create](#create)|Windows のエディット コントロールを作成しにアタッチ、`CEdit`オブジェクト。|  
|[CEdit::Cut](#cut)|削除 (切り取り) 編集の現在の選択 (存在する場合) を制御し、削除したテキストでクリップボードにコピー**エディット**形式。|  
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|(クリア) 編集の取り消しのフラグのコントロールをリセットします。|  
|[CEdit::FmtLines](#fmtlines)|複数行エディット コントロール内のソフト改行文字を含めること、オンまたはオフを設定します。|  
|[CEdit::GetCueBanner](#getcuebanner)|ヒントのテキスト、またはコントロールが空で、フォーカスされていないときに、エディット コントロールでのヒントとして表示されるテキストを取得します。|  
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|エディット コントロールに表示されている最上位の行を決定します。|  
|[CEdit::GetHandle](#gethandle)|複数行のエディット コントロールの現在割り当てられているメモリへのハンドルを取得します。|  
|[CEdit::GetHighlight](#gethighlight)|開始と終了値、現在の編集コントロールで強調表示されているテキストの範囲内の文字のインデックスを取得します。|  
|[CEdit::GetLimitText](#getlimittext)|このテキストの最大量を取得`CEdit`含めることができます。|  
|[CEdit::GetLine](#getline)|エディット コントロールから行のテキストを取得します。|  
|[CEdit::GetLineCount](#getlinecount)|複数行エディット コントロールで行の数を取得します。|  
|[CEdit::GetMargins](#getmargins)|このため、左右の余白を取得`CEdit`です。|  
|[CEdit::GetModify](#getmodify)|エディット コントロールの内容が変更されたかどうかを判断します。|  
|[CEdit::GetPasswordChar](#getpasswordchar)|テキストを入力したときに、エディット コントロールに表示されるパスワード文字を取得します。|  
|[CEdit::GetRect](#getrect)|エディット コントロールの書式設定、四角形を取得します。|  
|[CEdit::GetSel](#getsel)|エディット コントロールで現在の選択範囲の最初と最後の文字位置を取得します。|  
|[CEdit::HideBalloonTip](#hideballoontip)|現在の編集コントロールに関連付けられているバルーン ヒントを非表示にします。|  
|[CEdit::LimitText](#limittext)|ユーザーがエディット コントロールに入力できるテキストの長さを制限します。|  
|[CEdit::LineFromChar](#linefromchar)|指定した文字のインデックスを含む行の行番号を取得します。|  
|[CEdit::LineIndex](#lineindex)|複数行のエディット コントロール内の行の文字インデックスを取得します。|  
|[CEdit::LineLength](#linelength)|編集コントロール内の行の長さを取得します。|  
|[CEdit::LineScroll](#linescroll)|複数行のエディット コントロールのテキストをスクロールします。|  
|[CEdit::Paste](#paste)|エディット コントロールの現在のカーソル位置にクリップボードからデータを挿入します。 クリップボードのデータを格納する場合にのみ、データが挿入される**エディット**形式です。|  
|[CEdit::PosFromChar](#posfromchar)|指定された文字のインデックスの左上隅の座標を取得します。|  
|[CEdit::ReplaceSel](#replacesel)|エディット コントロールの現在の選択を指定したテキストに置き換えます。|  
|[CEdit::SetCueBanner](#setcuebanner)|ヒントのテキスト、またはコントロールが空で、フォーカスされていないときに、エディット コントロールでのヒントとして表示されるテキストを設定します。|  
|[CEdit::SetHandle](#sethandle)|複数行エディット コントロールで使用されるローカル メモリへのハンドルを設定します。|  
|[CEdit::SetHighlight](#sethighlight)|強調表示に現在表示されているテキストの範囲は、コントロールを編集します。|  
|[CEdit::SetLimitText](#setlimittext)|この文字列の最大時間を設定`CEdit`含めることができます。|  
|[CEdit::SetMargins](#setmargins)|左と右の余白を設定してこの`CEdit`です。|  
|[CEdit::SetModify](#setmodify)|設定または編集コントロールの変更のフラグをクリアします。|  
|[CEdit::SetPasswordChar](#setpasswordchar)|設定またはテキストを入力したときに、エディット コントロールに表示されるパスワード文字を削除します。|  
|[CEdit::SetReadOnly](#setreadonly)|エディット コントロールの読み取り専用の状態を設定します。|  
|[CEdit::SetRect](#setrect)|複数行エディット コントロールの書式設定の四角形を設定し、コントロールを更新します。|  
|[CEdit::SetRectNP](#setrectnp)|コントロール ウィンドウを再描画せず、複数行エディット コントロールの書式設定、四角形を設定します。|  
|[CEdit::SetSel](#setsel)|エディット コントロールの文字の範囲を選択します。|  
|[CEdit::SetTabStops](#settabstops)|エディット コントロールを複数行にタブを設定します。|  
|[CEdit::ShowBalloonTip](#showballoontip)|現在の編集コントロールに関連付けられているバルーン ヒントを表示します。|  
|[CEdit::Undo](#undo)|最後のエディット コントロールの操作を反転させます。|  
  
## <a name="remarks"></a>Remarks  
 エディット コントロールは、ユーザーがテキストを入力できる長方形の子ウィンドウです。  
  
 ダイアログ テンプレートから、またはコードで直接編集コントロールを作成できます。 どちらの場合、コンス トラクターを呼び出して最初`CEdit`構築するために、`CEdit`オブジェクト、し、呼び出し、[作成](#create)、ウィンドウを作成するメンバー関数は、コントロールを編集し、添付、`CEdit`オブジェクト。  
  
 派生したクラスで、1 つプロセスは、構築`CEdit`です。 呼び出しと派生クラスのコンス トラクターを記述`Create`から、コンス トラクター内で。  
  
 `CEdit` 重要な機能からの継承`CWnd`です。 設定してからテキストを取得する、`CEdit`オブジェクトを使用して、`CWnd`メンバー関数[SetWindowText](cwnd-class.md#setwindowtext)と[GetWindowText](cwnd-class.md#getwindowtext)編集の内容全体を制御する設定または取得場合でも、その複数行にわたるコントロールです。 複数行のコントロールでテキスト行は、'\r\n' 文字のシーケンスで区切られます。 また、エディット コントロールが複数行の場合は、取得し、呼び出すことによって、コントロールのテキストの一部を設定、`CEdit`メンバー関数[GetLine](#getline)、 [SetSel](#setsel)、 [GetSel](#getsel)、および[ReplaceSel](#replacesel)です。  
  
 Windows のエディット コントロールからその親に送信される通知メッセージを処理する場合 (通常から派生したクラス`CDialog`)、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。  
  
 各メッセージ マップ エントリは次の形式になります。  
  
  **On _**_通知_**(** _id_**、** _memberFxn_ **)**
  
 ここで`id`、通知を送信するエディット コントロールの子ウィンドウ ID を指定し、`memberFxn`通知の処理を記述した親メンバー関数の名前を指定します。  
  
 親の関数プロトタイプは次のとおりです。  
  
 **afx_msg** void memberFxn **( );**  
  
 潜在的なメッセージ マップ エントリと親に送信する場合の説明の一覧を次に示します。  
  
- **ON_EN_CHANGE**ユーザーがエディット コントロールでテキストを変更可能性があるアクションを取得します。 異なり、 **EN_UPDATE**通知メッセージを Windows の表示が更新後にこの通知メッセージが送信されます。  
  
- **ON_EN_ERRSPACE**エディット コントロールは、特定の要求を満たすのに十分なメモリを割り当てることができません。  
  
- **ON_EN_HSCROLL**エディット コントロールの水平スクロール バーをクリックします。 画面が更新される前に、親ウィンドウに通知されます。  
  
- **ON_EN_KILLFOCUS**エディット コントロールが入力フォーカスを失った。  
  
- **ON_EN_MAXTEXT**エディット コントロールの文字の指定した数を超えましたの現在の挿入およびが切り捨てられました。 編集コントロールがあるないときにも送信、 **ES_AUTOHSCROLL**がエディット コントロールの幅に収まりきらないスタイルおよび挿入する文字の数。 編集コントロールがあるないときにも送信、 **ES_AUTOVSCROLL**スタイルおよびテキストの挿入される行の合計数は、エディット コントロールの高さを超えてしまいます。  
  
- **ON_EN_SETFOCUS**エディット コントロールが入力フォーカスを受け取るときに送信します。  
  
- **ON_EN_UPDATE**エディット コントロールが変更されたテキストを表示しようとしています。 コントロールがテキストを書式設定後、そのテキストを表示できるように、ウィンドウのサイズを変更することができます、必要に応じて前に送信されます。  
  
- **ON_EN_VSCROLL**エディット コントロールの垂直スクロール バーをクリックします。 画面が更新される前に、親ウィンドウに通知されます。  
  
 作成する場合、`CEdit`ダイアログ ボックスでは、内のオブジェクト、 `CEdit`  ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CEdit`ダイアログ エディターを使用して、ダイアログ リソースからのオブジェクト、 `CEdit`  ダイアログ ボックスを閉じたときに、オブジェクトが自動的に破棄されます。  
  
 作成する場合、`CEdit`ウィンドウ内でオブジェクトを破棄しても必要があります。 作成する場合、`CEdit`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CEdit`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**オブジェクトを破棄して、ユーザーが、Windows が終了するときにコントロールを編集します。 メモリを割り当てる場合、`CEdit`オブジェクト、オーバーライド、`CEdit`デストラクターが、割り当てを破棄します。  
  
 エディット コントロールでの特定のスタイルを変更する (など**ES_READONLY**) を使用する代わりに、コントロールに特定のメッセージを送信する必要があります[は](cwnd-class.md#modifystyle)します。 参照してください[コントロールのスタイルを編集](http://msdn.microsoft.com/library/windows/desktop/bb775464)Windows SDK にします。  
  
 `CEdit` の詳細については、次を参照してください。  
  
- [コントロール](../../mfc/controls-mfc.md)  
  
-   サポート技術情報の記事 Q259949: 情報: SetCaretPos() が適切ではない CEdit または CRichEditCtrl コントロール  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CEdit`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="canundo"></a>  CEdit::CanUndo  
 この関数では、最後の編集操作を元に戻すことができるかどうかを判断します。  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>戻り値  
 呼び出しによってに最後の編集操作を元に戻すことができる場合は 0 以外、`Undo`メンバー関数は元に戻すことができない場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::Undo](#undo)です。  
  
##  <a name="cedit"></a>  CEdit::CEdit  
 `CEdit` オブジェクトを構築します。  
  
```  
CEdit();
```  
  
### <a name="remarks"></a>Remarks  
 使用して[作成](#create)構築するために、Windows のエディット コントロール。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]  
  
##  <a name="charfrompos"></a>  CEdit::CharFromPos  
 0 から始まる行およびこれで、指定したポイントに最も近い文字の文字インデックスを取得するには、この関数を呼び出す`CEdit`コントロール  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pt*  
 これのクライアント領域内のポイントの座標`CEdit`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 低位の文字インデックス**WORD**、上位の行インデックス**WORD**です。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]  
  
##  <a name="clear"></a>  CEdit::Clear  
 削除する (オフ) 現在の選択 (存在する場合)、編集コントロールでは、この関数を呼び出します。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarks  
 による削除`Clear`で元に戻すことができます、[を元に戻す](#undo)メンバー関数。  
  
 現在の選択範囲を削除し、削除された内容に配置し、クリップボード、[切り取り](#cut)メンバー関数。  
  
 詳細については、次を参照してください。 [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]  
  
##  <a name="copy"></a>  CEdit::Copy  
 関数を呼び出してこのコピーを現在の選択 (存在する場合) でクリップボードにエディット コントロールで**エディット**形式です。  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]  
  
##  <a name="create"></a>  CEdit::Create  
 Windows のエディット コントロールを作成しにアタッチ、`CEdit`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 エディット コントロールのスタイルを指定します。 任意の組み合わせを適用[エディット スタイル](styles-used-by-mfc.md#edit-styles)コントロールにします。  
  
 *rect*  
 エディット コントロールのサイズと位置を指定します。 指定できます、`CRect`オブジェクトまたは`RECT`構造体。  
  
 *pParentWnd*  
 エディット コントロールの親ウィンドウを指定します (通常、 `CDialog`)。 なければなりません**NULL**です。  
  
 *nID*  
 エディット コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、 `CEdit` 2 つのステップ内のオブジェクト。 まずを呼び出して、`CEdit`コンス トラクターと、呼び出し`Create`、Windows のエディット コントロールを作成しにアタッチする、`CEdit`オブジェクト。  
  
 ときに`Create`を実行する Windows の送信、 [WM_NCCREATE](http://msdn.microsoft.com/library/windows/desktop/ms632635)、 [WM_NCCALCSIZE](http://msdn.microsoft.com/library/windows/desktop/ms632634)、 [WM_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619)、および[WM_GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626)エディット コントロールするメッセージです。  
  
 既定では、これらのメッセージが処理されます、 [OnNcCreate](cwnd-class.md#onnccreate)、 [OnNcCalcSize](cwnd-class.md#onnccalcsize)、 [OnCreate](cwnd-class.md#oncreate)、および[OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo)メンバー関数`CWnd`基本クラスです。 既定のメッセージ処理を拡張するには、派生クラスを`CEdit`メッセージ マップを新しいクラスに追加し、上記のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 次の適用[ウィンドウ スタイル](styles-used-by-mfc.md#window-styles)エディット コントロールにします。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**タブ移動順序に編集コントロールを含める  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]  
  
##  <a name="cut"></a>  CEdit::Cut  
 エディット コントロールで (存在する場合) は、現在の選択 (カット) を削除するには、この関数を呼び出すし、削除したテキストでクリップボードにコピー**エディット**形式です。  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Remarks  
 による削除`Cut`で元に戻すことができます、[を元に戻す](#undo)メンバー関数。  
  
 削除したテキストをクリップボードに配置することがなく、現在の選択範囲を削除する呼び出し、[クリア](#clear)メンバー関数。  
  
 詳細については、次を参照してください。 [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]  
  
##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer  
 エディット コントロールの取り消しのフラグをリセット (消去) するには、この関数を呼び出します。  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Remarks  
 エディット コントロールようになりましたことはできません、最後の操作を取り消します。 エディット コントロール内の操作が取り消せるされるたびに、元に戻すフラグが設定されています。  
  
 取り消しのフラグが自動的に消去されるたびに、 [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)または[SetHandle](#sethandle) `CWnd`メンバー関数が呼び出されます。  
  
 詳細については、次を参照してください。 [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]  
  
##  <a name="fmtlines"></a>  CEdit::FmtLines  
 この関数では、複数行エディット コントロール内でソフト改行文字を含めることをオンまたはオフに設定します。  
  
```  
BOOL FmtLines(BOOL bAddEOL);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAddEOL*  
 ソフト改行文字が挿入されるかどうかを指定します。 値**TRUE**文字は; を挿入します。 値の**FALSE**それらを削除します。  
  
### <a name="return-value"></a>戻り値  
 存在する場合、0 以外の値の書式設定が発生します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 ソフト改行は、次の 2 つのキャリッジ リターンとテキストの折り返しにより分割された行の末尾に挿入ラインフィードで構成されます。 ハード改行は、1 つの復帰と改行で構成されます。 ハード改行が付いている行には影響ありません`FmtLines`です。  
  
 Windows は、場合にのみ応答、`CEdit`オブジェクトは、複数行エディット コントロール。  
  
 `FmtLines` によって返されるバッファーにのみ影響[GetHandle](#gethandle)とによって返されるテキスト[WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627)です。 エディット コントロール内のテキストの表示に影響を与えません。  
  
 詳細については、次を参照してください。 [EM_FMTLINES](http://msdn.microsoft.com/library/windows/desktop/bb761570) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]  
  
##  <a name="getcuebanner"></a>  CEdit::GetCueBanner  
 ヒントのテキスト、またはコントロールが空の場合、エディット コントロールでのヒントとして表示されるテキストを取得します。  
  
```  
BOOL GetCueBanner(
    LPWSTR lpszText,  
    int cchText) const;  
  
CString GetCueBanner() const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*lpszText*  
 ヒントのテキストを表す文字列へのポインター。  
  
 [in]*cchText*  
 受信できる文字数。 この番号には、終端が含まれています。`NULL`文字です。  
  
### <a name="return-value"></a>戻り値  
 最初のオーバー ロードの`true`メソッドが成功しなかった場合は場合`false`です。  
  
 2 番目のオーバー ロードのため、 [CString](../../atl-mfc-shared/using-cstring.md)メソッドが成功した、それ以外の場合は、ヒントのテキストを含む空の文字列 ("") です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [EM_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761572) Windows SDK で説明するメッセージ。 詳細については、次を参照してください。、 [Edit_GetCueBannerText](http://msdn.microsoft.com/library/windows/desktop/bb761695)マクロです。  
  
##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine  
 エディット コントロールに表示されている最上位の行を判断するには、この関数を呼び出します。  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最上位に表示されている行の 0 から始まるインデックス。 単一行エディット コントロールでは、戻り値は 0 です。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]  
  
##  <a name="gethandle"></a>  CEdit::GetHandle  
 現在、複数行エディット コントロールに割り当てられたメモリへのハンドルを取得するには、この関数を呼び出します。  
  
```  
HLOCAL GetHandle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 エディット コントロールの内容を保持するバッファーを識別するローカル メモリのハンドル。 単一行エディット コントロールにメッセージを送信するなどのエラーが発生した場合、戻り値は 0 です。  
  
### <a name="remarks"></a>Remarks  
 ハンドルは、ローカル メモリ ハンドルがありのいずれかで使用できる、**ローカル**をローカル メモリを受け取る Windows メモリ関数をパラメーターとして処理します。  
  
 **GetHandle**複数行のエディット コントロールでのみ処理します。  
  
 呼び出す**GetHandle**  ダイアログ ボックスがで作成された場合にのみ、ダイアログ ボックス内の複数行のエディット コントロールの**DS_LOCALEDIT**スタイル フラグを設定します。 場合、 **DS_LOCALEDIT**スタイルが設定されていない、0 以外の戻り値が表示されますが、返される値を使用することはできません。  
  
> [!NOTE]
> **GetHandle** Windows 95/98 では動作しません。 呼び出す場合**GetHandle** Windows 95/98 では返します**NULL**です。 **GetHandle**は、Windows NT version 3.51 以降で説明されているように動作します。  
  
 詳細については、次を参照してください。 [EM_GETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761576) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]  
  
##  <a name="gethighlight"></a>  CEdit::GetHighlight  
 現在の編集コントロールで強調表示されているテキストの範囲内の最初と最後の文字のインデックスを取得します。  
  
```  
BOOL GetHighlight(
    int* pichStart,   
    int* pichEnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[out]*pichStart*|強調表示されているテキストの範囲の最初の文字の 0 から始まるインデックス。|  
|[out]*pichEnd*|強調表示されているテキストの範囲の最後の文字の 0 から始まるインデックス。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [EM_GETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761578) Windows SDK で説明するメッセージ。  
  
##  <a name="getlimittext"></a>  CEdit::GetLimitText  
 このテキストの制限値を取得するには、このメンバー関数を呼び出す`CEdit`オブジェクト。  
  
```  
UINT GetLimitText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のテキストの制限、(バイト単位) でこの`CEdit`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 テキストの制限は、(バイト単位) がエディット コントロールが受け入れることができる、テキストの最大量です。  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]  
  
##  <a name="getline"></a>  CEdit::GetLine  
 エディット コントロールから行のテキストを取得するには、この関数を呼び出すし、配置で*lpszBuffer*です。  
  
```  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer) const;  
  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer,  
    int nMaxLength) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 編集コントロールの複数行から取得する行番号を指定します。 行番号は 0 から始まります。値 0 は、最初の行を指定します。 このパラメーターは、単一行エディット コントロールを無視します。  
  
 *lpszBuffer*  
 行のコピーを受け取るバッファーへのポインター。 バッファーの最初の単語は、バッファーにコピーする文字の最大数を指定する必要があります。  
  
 *格納*  
 バッファーにコピーするバイトの最大数を指定します。 `GetLine` 最初の単語にこの値を配置*lpszBuffer* Windows への呼び出しを行う前にします。  
  
### <a name="return-value"></a>戻り値  
 実際にコピーされたバイト数。 行番号がで指定された場合、戻り値は 0 *nIndex*エディット コントロール内の行の数よりも大きいです。  
  
### <a name="remarks"></a>Remarks  
 コピーした行に null 終端文字が含まれていません。  
  
 詳細については、次を参照してください。 [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::GetLineCount](#getlinecount)です。  
  
##  <a name="getlinecount"></a>  CEdit::GetLineCount  
 複数行エディット コントロールで行の数を取得するには、この関数を呼び出します。  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 複数行にある行の数を表す整数では、コントロールを編集します。 エディット コントロールにテキストが入力されていない場合、戻り値は 1 です。  
  
### <a name="remarks"></a>Remarks  
 `GetLineCount` 複数行エディット コントロールでのみ処理されます。  
  
 詳細については、次を参照してください。 [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]  
  
##  <a name="getmargins"></a>  CEdit::GetMargins  
 この編集コントロールの左と右余白を取得するには、このメンバー関数を呼び出します。  
  
```  
DWORD GetMargins() const;  
```  
  
### <a name="return-value"></a>戻り値  
 低位の左余白の幅**WORD**と高い順序で右余白の幅**WORD**です。  
  
### <a name="remarks"></a>Remarks  
 余白はピクセル単位で測定されます。  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_GETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761590) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)です。  
  
##  <a name="getmodify"></a>  CEdit::GetModify  
 エディット コントロールの内容が変更されたかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>戻り値  
 編集コントロールの内容が変更された場合は 0 以外。0 のままである場合は変更されません。  
  
### <a name="remarks"></a>Remarks  
 Windows では、エディット コントロールの内容が変更されているかどうかを示す内部フラグを保持します。 このフラグをクリアすると、編集コントロールが最初に作成を呼び出してもクリア可能性があります、 [SetModify](#setmodify)メンバー関数。  
  
 詳細については、次を参照してください。 [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]  
  
##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar  
 この関数では、テキストを入力したときに、エディット コントロールに表示されるパスワードの文字を取得します。  
  
```  
TCHAR GetPasswordChar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが入力した文字の代わりに表示する文字を指定します。 戻り値は`NULL`パスワード文字が存在しない場合。  
  
### <a name="remarks"></a>Remarks  
 編集コントロールを作成する場合、 **ES_PASSWORD**スタイル、コントロールをサポートする DLL は、既定のパスワードの文字を決定します。 マニフェストまたは[InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697)メソッド決定 DLL をサポートするエディット コントロール。 User32.dll エディット コントロールをサポートしている場合、既定のパスワード文字はアスタリスク ('* '、U +002)。 Comctl32.dll version 6 は、エディット コントロールをサポートする場合、既定の文字は、黒の丸 ('●' で、U +0 25CF)。 詳細については、DLL とバージョンがサポートするコモン コントロールを参照してください[シェルと共通のコントロール バージョン](http://msdn.microsoft.com/library/windows/desktop/bb776779)します。  
  
 このメソッドは、送信、 [EM_GETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761594) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]  
  
##  <a name="getrect"></a>  CEdit::GetRect  
 エディット コントロールの書式設定、四角形を取得するには、この関数を呼び出します。  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRect*  
 指す、`RECT`書式の四角形を受け取る構造体。  
  
### <a name="remarks"></a>Remarks  
 書式設定の四角形は、これは、エディット コントロール ウィンドウのサイズの独立したテキストの外接する四角形です。  
  
 によって複数行エディット コントロールの書式設定、四角形を変更することができます、 [SetRect](#setrect)と[角形](#setrectnp)メンバー関数。  
  
 詳細については、次を参照してください。 [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::LimitText](#limittext)です。  
  
##  <a name="getsel"></a>  CEdit::GetSel  
 開始と終了値、戻り値またはパラメーターを使用して、編集コントロールの現在の選択 (存在する場合) の文字位置を取得するには、この関数を呼び出します。  
  
```  
DWORD GetSel() const;  
  
void GetSel(
    int& nStartChar,  
    int& nEndChar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nStartChar*  
 現在の選択範囲の最初の文字の位置を受信する整数への参照。  
  
 *nEndChar*  
 現在の選択範囲の末尾を越えたダブルワードの位置を受信する整数への参照。  
  
### <a name="return-value"></a>戻り値  
 バージョンを返す、`DWORD`上位ワードに選択範囲の終了後に下位ワードの開始位置と最初に選択されていない文字の位置を表す値を返します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [EM_GETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761598) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]  
  
##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip  
 現在の編集コントロールに関連付けられているバルーン ヒントを非表示にします。  
  
```  
BOOL HideBalloonTip();
```  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 この関数は、 [EM_HIDEBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761604) Windows SDK で説明するメッセージ。  
  
##  <a name="limittext"></a>  CEdit::LimitText  
 ユーザーがエディット コントロールに入力するテキストの長さを制限するには、この関数を呼び出します。  
  
```  
void LimitText(int nChars = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *文字数*  
 ユーザーが入力できるテキストの長さ (単位: バイト) を指定します。 このパラメーターが 0 の場合は、テキストの長さに設定されている**UINT_MAX**バイトです。 これが既定の動作です。  
  
### <a name="remarks"></a>Remarks  
 テキストの制限を変更すると、ユーザーが入力できるテキストのみが制限されます。 影響を与えません任意のテキストで既に編集コントロールにも、によって、編集コントロールにコピーされたテキストの長さに影響は、 [SetWindowText](cwnd-class.md#setwindowtext)メンバー関数内`CWnd`です。 アプリケーションで使用する場合、`SetWindowText`関数への呼び出しで指定されているよりエディット コントロールにテキストを配置する`LimitText`ユーザーがエディット コントロール内のテキストのいずれかを削除します。 ただし、テキストの制限は、ユーザーが新しいテキストに、既存のテキストを置換できないように、現在の選択範囲を削除しない限り、により、テキストは、テキストの制限値未満になってしまいます。  
  
> [!NOTE]
>  Win32 (Windows NT と Windows 95/98)、 [SetLimitText](#setlimittext)この関数を置き換えます。  
  
 詳細については、次を参照してください。 [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]  
  
##  <a name="linefromchar"></a>  CEdit::LineFromChar  
 指定した文字のインデックスを含む行の行番号を取得するには、この関数を呼び出します。  
  
```  
int LineFromChar(int nIndex = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 エディット コントロールのテキストに必要な文字の 0 から始まるインデックス値が含まれるか、-1 を含んでいます。 場合*nIndex* -1 で、現在の行では、カーソルがある行を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定された文字のインデックスを含む行の 0 から始まる行番号*nIndex*です。 場合*nIndex* -1 で、選択範囲の最初の文字を含む行の数が返されます。 選択されていない場合は、現在の行番号が返されます。  
  
### <a name="remarks"></a>Remarks  
 文字のインデックスは、エディット コントロールの先頭からの文字の数です。  
  
 このメンバー関数は、複数行エディット コントロールでのみ使用します。  
  
 詳細については、次を参照してください。 [EM_LINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761609) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]  
  
##  <a name="lineindex"></a>  CEdit::LineIndex  
 この関数では、複数行エディット コントロール内の行の文字インデックスを取得します。  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nLine*  
 エディット コントロールのテキストで目的の行のインデックス値が含まれていますか、-1 を含んでいます。 場合*nLine* -1 で、現在の行では、カーソルがある行を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定した行の文字インデックス*nLine*または指定した行番号がエディット コントロール内の行の数より大きい場合は-1。  
  
### <a name="remarks"></a>Remarks  
 文字インデックスは、指定した行エディット コントロールの先頭から文字の数です。  
  
 このメンバー関数は、複数行エディット コントロールでのみ処理されます。  
  
 詳細については、次を参照してください。 [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]  
  
##  <a name="linelength"></a>  CEdit::LineLength  
 編集コントロール内の行の長さを取得します。  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nLine*  
 長さを取得する行の文字の 0 から始まるインデックス。 既定値は -1 です。  
  
### <a name="return-value"></a>戻り値  
 単一行エディット コントロールで、戻り値は、長さ`TCHAR`s、エディット コントロール内のテキスト。  
  
 複数行エディット コントロールで、戻り値は、長さ`TCHAR`で指定された行の s、 *nLine*パラメーター。 [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)]テキスト、長さは行のバイト数の場合 Unicode テキスト、長さは行の文字の数。 長さには、行の最後にキャリッジ リターン文字は含まれません。  
  
 場合、 *nLine*パラメーターは、コントロール内の文字数よりも多い、戻り値は 0 です。  
  
 場合、 *nLine*パラメーターが-1、戻り値が選択されている文字を含む行で選択されていない文字の数。 たとえば、次の行の末尾から 8 番目の文字を 1 つの行の 4 番目の文字から選択範囲の場合、戻り値は 10 です。 つまり、3 つは、最初の行で、次の 7 個の文字です。  
  
 詳細については、`TCHAR`を入力しを参照してください、`TCHAR`テーブルの行に[Windows Data Types](http://msdn.microsoft.com/library/windows/desktop/aa383751)です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドはサポート、 [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) Windows SDK に説明されているメッセージです。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::LineIndex](#lineindex)です。  
  
##  <a name="linescroll"></a>  CEdit::LineScroll  
 複数行エディット コントロールのテキストをスクロールするには、この関数を呼び出します。  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *nLines*  
 垂直方向にスクロールする行数を指定します。  
  
 *文字数*  
 水平方向にスクロールする文字位置の数を指定します。 編集コントロールにいずれかがある場合、この値は無視されます、 **ES_RIGHT**または**ES_CENTER**スタイル。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、複数行エディット コントロールでのみ処理されます。  
  
 エディット コントロールは、過去のエディット コントロールでテキストの最後の行は垂直方向にスクロールされません。 指定された行の数と現在の行かどうか*nLines*エディット コントロールで行の合計数を超える場合、値がエディット コントロールの最後の行がエディット コントロール ウィンドウの一番上にスクロールされる基準を調整します。  
  
 `LineScroll` 過去の任意の行の最後の文字、水平方向にスクロールするために使用します。  
  
 詳細については、次を参照してください。 [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::GetFirstVisibleLine](#getfirstvisibleline)です。  
  
##  <a name="paste"></a>  CEdit::Paste  
 クリップボードからデータを挿入するには、この関数を呼び出して、`CEdit`のカーソル位置にします。  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Remarks  
 クリップボードのデータを格納する場合にのみ、データが挿入される**エディット**形式です。  
  
 詳細については、次を参照してください。 [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]  
  
##  <a name="posfromchar"></a>  CEdit::PosFromChar  
 内で指定された文字の位置 (左上隅) を取得するには、この関数を呼び出す`CEdit`オブジェクト。  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nChar*  
 指定した文字の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定された文字の左上隅の座標*nChar*です。  
  
### <a name="remarks"></a>Remarks  
 文字を指定するには、0 から始まるインデックス値を提供します。 場合*nChar*がのこの最後の文字のインデックスよりも大きい`CEdit`オブジェクトの戻り値は、この最後の文字の直後の文字の位置の座標を指定`CEdit`オブジェクト。  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::LineFromChar](#linefromchar)です。  
  
##  <a name="replacesel"></a>  CEdit::ReplaceSel  
 指定されたテキスト編集コントロールの現在の選択を置き換えるには、この関数を呼び出す*されている*です。  
  
```  
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *されています。*  
 置換テキストを含む null で終わる文字列へのポインター。  
  
 *bCanUndo*  
 この関数が完了できることを指定するには、このパラメーターの値を設定**TRUE**です。 既定値は**FALSE**です。  
  
### <a name="remarks"></a>Remarks  
 エディット コントロール内のテキストの一部だけを置換します。 すべてのテキストを置換する場合は、使用、[とき](cwnd-class.md#setwindowtext)メンバー関数。  
  
 現在選択されていない、置換テキストは、現在のカーソル位置に挿入されます。  
  
 詳細については、次を参照してください。 [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::LineIndex](#lineindex)です。  
  
##  <a name="setcuebanner"></a>  CEdit::SetCueBanner  
 ヒントのテキストとして表示されるか、ヒントは、エディット コントロールが空の場合を制御するテキストを設定します。  
  
```  
BOOL SetCueBanner(LPCWSTR lpszText);

 
BOOL SetCueBanner(
    LPCWSTR lpszText,   
    BOOL fDrawWhenFocused = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszText*  
 エディット コントロールに表示されるヒントを含む文字列へのポインター。  
  
 [in]*fDrawWhenFocused*  
 場合`false`ユーザーがエディット コントロールでクリックするし、フォーカスを制御キュー バナーは描画されません。  
  
 場合`true`コントロールにフォーカスがある場合でも、キュー バナーを描画します。 キュー バナーには、ユーザーがコントロールに入力を開始すると表示されなくなります。  
  
 既定値は `false` です。  
  
### <a name="return-value"></a>戻り値  
 `true` メソッドが成功した場合それ以外の場合`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [EM_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761639) Windows SDK で説明するメッセージ。 詳細については、次を参照してください。、 [Edit_SetCueBannerTextFocused](http://msdn.microsoft.com/library/windows/desktop/bb761703)マクロです。  
  
### <a name="example"></a>例  
 次の例で、 [CEdit::SetCueBanner](#setcuebanner)メソッドです。  
  
 [!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]  
  
##  <a name="sethandle"></a>  CEdit::SetHandle  
 複数行エディット コントロールで使用されるローカル メモリへのハンドルを設定するには、この関数を呼び出します。  
  
```  
void SetHandle(HLOCAL hBuffer);
```  
  
### <a name="parameters"></a>パラメーター  
 *hBuffer*  
 ローカル メモリへのハンドルが含まれています。 このハンドルを前回呼び出したときに作成する必要があります、 [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) Windows 関数を使用して、**あらかじめ**フラグ。 メモリは、null で終わる文字列を格納すると見なされます。 場合はそうでない場合は、割り当てられたメモリの最初のバイトが 0 に設定する必要があります。  
  
### <a name="remarks"></a>Remarks  
 独自のバッファーを割り当てる代わりに現在表示されているテキストを格納するのに、このバッファーをエディット コントロールで使用されます。  
  
 このメンバー関数は、複数行エディット コントロールでのみ処理されます。  
  
 使用するアプリケーションでは、新しいメモリ ハンドルを設定、前に、 [GetHandle](#gethandle)を現在のメモリ バッファーへのハンドルを取得し、空きメモリを使用してそのメンバー関数、 **LocalFree** Windows の機能です。  
  
 `SetHandle` 元に戻すバッファーをクリア (、 [CanUndo](#canundo)メンバー関数は、0 を返します) と内部変更フラグ (、[この](#getmodify)メンバー関数は、0 を返します)。 エディット コントロール ウィンドウが再描画されます。  
  
 ダイアログ ボックスを作成する場合にのみ、ダイアログ ボックスで複数行エディット コントロールでは、このメンバー関数を使用することができます、 **DS_LOCALEDIT**スタイル フラグを設定します。  
  
> [!NOTE]
> **GetHandle** Windows 95/98 では動作しません。 呼び出す場合**GetHandle** Windows 95/98 では返します**NULL**です。 **GetHandle**は、Windows NT version 3.51 以降で説明されているように動作します。  
  
 詳細については、次を参照してください。 [EM_SETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761641)、 [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723)、および[LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]  
  
##  <a name="sethighlight"></a>  CEdit::SetHighlight  
 強調表示に現在表示されているテキストの範囲は、コントロールを編集します。  
  
```  
void SetHighlight(
    int ichStart,   
    int ichEnd);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*ichStart*|強調表示するテキストの範囲の最初の文字の 0 から始まるインデックス。|  
|[in]*ichEnd*|強調表示するテキストの範囲の最後の文字の 0 から始まるインデックス。|  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [EM_SETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761643) Windows SDK で説明するメッセージ。  
  
##  <a name="setlimittext"></a>  CEdit::SetLimitText  
 このテキストの制限を設定するには、このメンバー関数を呼び出す`CEdit`オブジェクト。  
  
```  
void SetLimitText(UINT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMax*  
 文字で、新しいテキスト制限。  
  
### <a name="remarks"></a>Remarks  
 テキストの制限は、エディット コントロールが受け入れることができる文字のテキストの最大量です。  
  
 テキストの制限を変更すると、ユーザーが入力できるテキストのみが制限されます。 影響を与えません任意のテキストで既に編集コントロールにも、によって、編集コントロールにコピーされたテキストの長さに影響は、 [SetWindowText](cwnd-class.md#setwindowtext)メンバー関数内`CWnd`です。 アプリケーションで使用する場合、`SetWindowText`関数への呼び出しで指定されているよりエディット コントロールにテキストを配置する`LimitText`ユーザーがエディット コントロール内のテキストのいずれかを削除します。 ただし、テキストの制限は、ユーザーが新しいテキストに、既存のテキストを置換できないように、現在の選択範囲を削除しない限り、により、テキストは、テキストの制限値未満になってしまいます。  
  
 この関数は[LimitText](#limittext) Win32 でします。  
  
 詳細については、次を参照してください。 [EM_SETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761647) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)です。  
  
##  <a name="setmargins"></a>  CEdit::SetMargins  
 この編集コントロールの左と右余白を設定するには、このメソッドを呼び出します。  
  
```  
void SetMargins(
    UINT nLeft,  
    UINT nRight);
```  
  
### <a name="parameters"></a>パラメーター  
 *nLeft*  
 ピクセル単位で、新しいの左余白の幅。  
  
 *nRight*  
 ピクセル単位で、新しい右余白の幅。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  このメンバー関数は、Windows 95 および Windows NT 4.0 から使用可能です。  
  
 詳細については、次を参照してください。 [EM_SETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761649) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)です。  
  
##  <a name="setmodify"></a>  CEdit::SetModify  
 設定または編集コントロールの変更されたフラグをオフにするには、この関数を呼び出します。  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bModified*  
 値**TRUE**テキストが変更されたことを示す、値を**FALSE**修正されていないことを示します。 既定では、変更されたフラグは設定されます。  
  
### <a name="remarks"></a>Remarks  
 変更されたフラグは、エディット コントロール内のテキストが変更されたかどうかを示します。 ユーザーがテキストを変更するたびに自動的に設定されます。 その値を取得することがあります、[この](#getmodify)メンバー関数。  
  
 詳細については、次を参照してください。 [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::GetModify](#getmodify)です。  
  
##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar  
 設定するか、ユーザーがテキストを入力したときに、エディット コントロールに表示されるパスワード文字を削除するには、この関数を呼び出します。  
  
```  
void SetPasswordChar(TCHAR ch);
```  
  
### <a name="parameters"></a>パラメーター  
 *ch*  
 ユーザーが入力文字の代わりに表示する文字を指定します。 場合*ch*が 0 の場合、ユーザーによって入力された実際の文字が表示されます。  
  
### <a name="remarks"></a>Remarks  
 パスワードの文字を設定すると、各文字をユーザーの種類の文字が表示されます。  
  
 このメンバー関数には、エディット コントロールの複数行に影響はありません。  
  
 ときに、`SetPasswordChar`メンバー関数が呼び出されると、`CEdit`で指定された文字を使用してすべて表示可能な文字を再描画*ch*です。  
  
 編集コントロールが作成された場合、 [ES_PASSWORD](styles-used-by-mfc.md#edit-styles)スタイル、既定のパスワードの文字に設定には、アスタリスク ( **\***)。 このスタイルは`SetPasswordChar`で呼び出された*ch*を 0 に設定します。  
  
 詳細については、次を参照してください。 [EM_SETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761653) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]  
  
##  <a name="setreadonly"></a>  CEdit::SetReadOnly  
 エディット コントロールの読み取り専用の状態を設定するには、この関数を呼び出します。  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bReadOnly*  
 設定するか、編集コントロールの読み取り専用の状態を削除するかどうかを指定します。 値**TRUE**状態を設定する読み取り専用です。 値の**FALSE**を読み取り/書き込みの状態を設定します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、操作が成功、または 0 の場合、エラーが発生します。  
  
### <a name="remarks"></a>Remarks  
 テストすることによって、現在の設定が見つかりません、 [ES_READONLY](styles-used-by-mfc.md#edit-styles)の戻り値のフラグ[状態](cwnd-class.md#getstyle)です。  
  
 詳細については、次を参照してください。 [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]  
  
##  <a name="setrect"></a>  CEdit::SetRect  
 指定された座標を使用して、四角形の寸法を設定するには、この関数を呼び出します。  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRect*  
 指す、`RECT`構造または`CRect`新しい書式設定の四角形の寸法を指定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメンバーは、複数行エディット コントロールでのみ処理されます。  
  
 使用して`SetRect`複数行の四角形は、書式を設定するコントロールを編集します。 書式設定の四角形は、これは、エディット コントロール ウィンドウのサイズの独立したテキストの外接する四角形です。 エディット コントロールが最初に作成されるときに書式設定の四角形は、エディット コントロール ウィンドウのクライアント領域と同じです。 使用して、`SetRect`メンバー関数は、アプリケーションと、書式の四角形エディット コントロール ウィンドウより大きいか小さいです。  
  
 スクロール バーがエディット コントロールがない場合は、テキストは、クリップされます、ラップされません書式の四角形のウィンドウよりも大きいが行われた場合。 エディット コントロールに境界線が含まれている場合は、境界線のサイズによって書式設定の四角形が少なくなります。 によって返される四角形を調整する場合は、`GetRect`メンバー関数は、四角形に渡す前に境界線のサイズを削除する必要があります`SetRect`です。  
  
 ときに`SetRect`が呼び出されると、エディット コントロールのテキストも再フォーマットし、再表示されます。  
  
 詳細については、次を参照してください。 [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]  
  
##  <a name="setrectnp"></a>  CEdit::SetRectNP  
 この関数では、複数行エディット コントロールの書式設定の四角形を設定します。  
  
```  
void SetRectNP(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRect*  
 指す、`RECT`構造または`CRect`新しい四角形の寸法を指定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 書式設定の四角形は、これは、エディット コントロール ウィンドウのサイズの独立したテキストの外接する四角形です。  
  
 `SetRectNP` 同じですが、`SetRect`のメンバー関数が、編集コントロールのウィンドウが再描画されません。  
  
 エディット コントロールが最初に作成されるときに書式設定の四角形は、エディット コントロール ウィンドウのクライアント領域と同じです。 呼び出して、`SetRectNP`メンバー関数は、アプリケーションと、書式の四角形エディット コントロール ウィンドウより大きいか小さいです。  
  
 スクロール バーがエディット コントロールがない場合は、テキストは、クリップされます、ラップされません書式の四角形のウィンドウよりも大きいが行われた場合。  
  
 このメンバーは、複数行エディット コントロールでのみ処理されます。  
  
 詳細については、次を参照してください。 [EM_SETRECTNP](http://msdn.microsoft.com/library/windows/desktop/bb761659) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::SetRect](#setrect)です。  
  
##  <a name="setsel"></a>  CEdit::SetSel  
 エディット コントロール内の文字の範囲を選択するには、この関数を呼び出します。  
  
```  
void SetSel(
    DWORD dwSelection,  
    BOOL bNoScroll = FALSE);

 
void SetSel(
    int nStartChar,  
    int nEndChar,  
    BOOL bNoScroll = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwSelection*  
 下位ワード内の開始位置と高位の単語の終了位置を指定します。 下位ワードが 0 で、上位ワードが-1 の場合、エディット コントロール内のすべてのテキストが選択されます。 下位ワードが-1 の場合は、現在の選択項目が削除されます。  
  
 *bNoScroll*  
 カレットをスクロールして表示するかどうかを示します。 場合**FALSE**キャレットをスクロールして表示します。 場合**TRUE**カーソルがスクロール表示されません。  
  
 *nStartChar*  
 開始位置を指定します。 場合*nStartChar*は 0 と*nEndChar* -1 で、編集コントロール内のテキストが選択されています。 場合*nStartChar* -1 で、現在の選択項目を削除します。  
  
 *nEndChar*  
 終了位置を指定します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [EM_SETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761661) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEdit::GetSel](#getsel)です。  
  
##  <a name="settabstops"></a>  CEdit::SetTabStops  
 この関数では、複数行エディット コントロールでタブ位置を設定します。  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>パラメーター  
 *cxEachStop*  
 タブ ストップに設定することを指定すべて*cxEachStop*ダイアログ単位です。  
  
 *nTabStops*  
 含まれているタブの数を指定*rgTabStops*です。 この番号は、1 より大きくなければなりません。  
  
 *rgTabStops*  
 ダイアログ単位で、タブを指定する符号なし整数の配列へのポインターを停止します。 ダイアログ単位は、水平または垂直距離です。 1 つの水平方向のダイアログ単位は、現在のダイアログ ベースの幅の単位の 4 分の 1 に等しいと 1 の垂直方向のダイアログ単位は、現在のダイアログ ベースの高さユニットの 8 分の 1 に等しい。 ダイアログの基本単位は、現在のシステム フォントの幅と高さに基づいて計算されます。 **GetDialogBaseUnits** Windows の機能はピクセル単位で現在のダイアログ ボックスの基本単位を返します。  
  
### <a name="return-value"></a>戻り値  
 タブが設定された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 複数行エディット コントロールにテキストをコピーしたら、テキスト内の任意のタブ文字を次のタブ ストップまで生成される領域となります。  
  
 タブ ストップを 32 ダイアログ単位の既定のサイズに設定するには、このメンバー関数のパラメーターなしのバージョンを呼び出します。 タブ ストップを 32 以外のサイズを設定するとバージョンを呼び出す、 *cxEachStop*パラメーター。 サイズの配列をタブ ストップを設定するには、2 つのパラメーターでバージョンを使用します。  
  
 このメンバー関数は、複数行エディット コントロールでのみ処理されます。  
  
 `SetTabStops` 自動的に再描画されない、編集ウィンドウです。 テキスト編集コントロールのタブ ストップを変更する場合を呼び出す[エディット](cwnd-class.md#invalidaterect)編集ウィンドウが再描画します。  
  
 詳細については、次を参照してください。 [EM_SETTABSTOPS](http://msdn.microsoft.com/library/windows/desktop/bb761663)と[GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CEditView::SetTabStops](ceditview-class.md#settabstops)です。  
  
##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip  
 現在の編集コントロールに関連付けられているバルーン ヒントを表示します。  
  
```  
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

 
BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,   
    LPCWSTR lpszText,   
    INT ttiIcon = TTI_NONE);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*pEditBalloonTip*|ポインター、 [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466)バルーン ヒントを記述する構造体。|  
|[in]*lpszTitle*|バルーン ヒントのタイトルを含む Unicode 文字列へのポインター。|  
|[in]*lpszText*|バルーン ヒントのテキストを含む Unicode 文字列へのポインター。|  
|[in]*ttiIcon*|**INT**バルーン ヒントに関連付けるアイコンの種類を指定します。 既定値は `TTI_NONE` です。 詳細については、次を参照してください。、`ttiIcon`のメンバー、 [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466)構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 この関数は、 [EM_SHOWBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761668) Windows SDK で説明するメッセージ。 詳細については、次を参照してください。、 [Edit_ShowBalloonTip](http://msdn.microsoft.com/library/windows/desktop/bb761707)マクロです。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_cedit`、つまり現在の編集コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]  
  
### <a name="example"></a>例  
 次のコード例では、エディット コントロールのバルーン ヒントを表示します。 [CEdit::ShowBalloonTip](#showballoontip)メソッドは、タイトルとバルーンのヒント テキストを指定します。  
  
 [!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]  
  
##  <a name="undo"></a>  CEdit::Undo  
 最後のエディット コントロールの操作を元に戻すには、この関数を呼び出します。  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>戻り値  
 単一行エディット コントロールでは、戻り値は 0 以外では常にします。 複数行エディット コントロールでは、戻り値は元に戻す操作が成功した場合は 0 以外、または元に戻す操作が失敗した場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 元に戻す操作が元に戻すことができますもあります。 たとえば、最初の呼び出し、削除した文字列を戻すことができます`Undo`です。 2 番目の呼び出しを使用してテキストを削除するには中間の編集操作がない限り、`Undo`です。  
  
 詳細については、次を参照してください。 [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CALCDRIV](../../visual-cpp-samples.md)   
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](cwnd-class.md)   
 [CButton クラス](cbutton-class.md)   
 [CComboBox クラス](ccombobox-class.md)   
 [CListBox クラス](clistbox-class.md)   
 [関数クラス](cscrollbar-class.md)   
 [CStatic クラス](cstatic-class.md)   
 [CDialog クラス](cdialog-class.md)
