---
title: CEdit Class
ms.date: 09/12/2018
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
ms.openlocfilehash: 45c03d142c34186660aa2715081ffb0f45e85ccc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773750"
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
|[CEdit::CEdit](#cedit)|構築、`CEdit`コントロール オブジェクト。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CEdit::CanUndo](#canundo)|エディット コントロールの操作が完了できるかどうかを判断します。|
|[CEdit::CharFromPos](#charfrompos)|指定した位置に最も近い文字の行や文字のインデックスを取得します。|
|[CEdit::Clear](#clear)|編集の現在の選択 (存在する場合) を制御する (クリア) を削除します。|
|[CEdit::Copy](#copy)|現在の選択 (あれば) エディット コントロールでクリップボードにコピーされているテキスト形式でします。|
|[CEdit::Create](#create)|Windows のエディット コントロールを作成しにアタッチします、`CEdit`オブジェクト。|
|[CEdit::Cut](#cut)|(切り取り) の編集で現在の選択 (存在する場合) を制御し、コピーされているテキストでクリップボードに削除されたテキストの書式設定します。|
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|(クリア) の編集を元に戻すフラグ コントロールをリセットします。|
|[CEdit::FmtLines](#fmtlines)|複数行のエディット コントロール内のソフトの改行文字を含めることオンまたはオフを設定します。|
|[CEdit::GetCueBanner](#getcuebanner)|ヒントのテキストまたはコントロールが空で、フォーカスがないときに、エディット コントロールでのヒントとして表示されるテキストを取得します。|
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|エディット コントロールに表示されている最上位の行を決定します。|
|[CEdit::GetHandle](#gethandle)|複数行のエディット コントロールに現在割り当てられているメモリを識別するハンドルを取得します。|
|[CEdit::GetHighlight](#gethighlight)|開始日と終了、現在の編集コントロールで強調表示されているテキストの範囲内の文字のインデックスを取得します。|
|[CEdit::GetLimitText](#getlimittext)|このテキストの最大量を取得します。`CEdit`含めることができます。|
|[CEdit::GetLine](#getline)|エディット コントロールから行のテキストを取得します。|
|[CEdit::GetLineCount](#getlinecount)|複数行のエディット コントロールで行の数を取得します。|
|[CEdit::GetMargins](#getmargins)|これは、左右の余白を取得します。`CEdit`します。|
|[CEdit::GetModify](#getmodify)|エディット コントロールの内容が変更されたかどうかを判断します。|
|[CEdit::GetPasswordChar](#getpasswordchar)|テキストを入力したときに、エディット コントロールに表示されるパスワードの文字を取得します。|
|[CEdit::GetRect](#getrect)|エディット コントロールの書式設定の四角形を取得します。|
|[CEdit::GetSel](#getsel)|エディット コントロールで現在の選択範囲の最初と最後の文字位置を取得します。|
|[CEdit::HideBalloonTip](#hideballoontip)|現在の編集コントロールに関連付けられているバルーン ヒントを非表示にします。|
|[CEdit::LimitText](#limittext)|ユーザーがエディット コントロールに入力できるテキストの長さを制限します。|
|[CEdit::LineFromChar](#linefromchar)|指定された文字インデックスを含む行の行番号を取得します。|
|[CEdit::LineIndex](#lineindex)|複数行のエディット コントロール内の行の文字インデックスを取得します。|
|[CEdit::LineLength](#linelength)|編集コントロール内の行の長さを取得します。|
|[CEdit::LineScroll](#linescroll)|複数行のエディット コントロールのテキストをスクロールします。|
|[CEdit::Paste](#paste)|クリップボードから現在のカーソル位置にある編集コントロールにデータを挿入します。 クリップボードにされているテキスト形式のデータが含まれている場合にのみデータが挿入されます。|
|[CEdit::PosFromChar](#posfromchar)|指定された文字インデックスの左上隅の座標を取得します。|
|[CEdit::ReplaceSel](#replacesel)|エディット コントロールの現在の選択を指定したテキストに置き換えます。|
|[CEdit::SetCueBanner](#setcuebanner)|ヒントのテキストまたはコントロールが空で、フォーカスがないときに、エディット コントロールでのヒントとして表示されるテキストを設定します。|
|[CEdit::SetHandle](#sethandle)|ハンドルは、複数行のエディット コントロールで使用されるローカル メモリを設定します。|
|[CEdit::SetHighlight](#sethighlight)|強調表示、現在の表示されるテキストの範囲は、コントロールを編集します。|
|[CEdit::SetLimitText](#setlimittext)|このテキストの最大サイズを設定`CEdit`含めることができます。|
|[CEdit::SetMargins](#setmargins)|左と右の余白を設定します。`CEdit`します。|
|[CEdit::SetModify](#setmodify)|設定または編集コントロールの変更フラグをクリアします。|
|[CEdit::SetPasswordChar](#setpasswordchar)|設定またはテキストを入力したときに、エディット コントロールに表示されるパスワード文字を削除します。|
|[CEdit::SetReadOnly](#setreadonly)|エディット コントロールの読み取り専用の状態を設定します。|
|[CEdit::SetRect](#setrect)|複数行のエディット コントロールの書式設定の四角形を設定し、コントロールを更新します。|
|[CEdit::SetRectNP](#setrectnp)|コントロール ウィンドウを再描画せずには、複数行のエディット コントロールの書式設定の四角形を設定します。|
|[CEdit::SetSel](#setsel)|エディット コントロール内の文字の範囲を選択します。|
|[CEdit::SetTabStops](#settabstops)|コントロールの編集では、複数行のタブ ストップを設定します。|
|[CEdit::ShowBalloonTip](#showballoontip)|現在の編集コントロールに関連付けられているバルーン ヒントが表示されます。|
|[CEdit::Undo](#undo)|最後の編集コントロールの操作を反転させます。|

## <a name="remarks"></a>Remarks

編集コントロールは、ユーザーがテキストを入力できる四角形の子ウィンドウです。

ダイアログ テンプレートから、またはコードで直接編集コントロールを作成できます。 どちらの場合も、コンス トラクターを呼び出す最初`CEdit`を構築する、`CEdit`オブジェクトを呼び出して、[作成](#create)メンバー関数は、Windows を作成するコントロールを編集し、アタッチ先、`CEdit`オブジェクト。

派生したクラスの 1 ステップのプロセスは、構築`CEdit`します。 呼び出しと派生クラスのコンス トラクターを記述`Create`からコンス トラクター内。

`CEdit` 重要な機能を継承`CWnd`します。 設定してからテキストを取得する、`CEdit`オブジェクトを使用して、`CWnd`メンバー関数[SetWindowText](cwnd-class.md#setwindowtext)と[GetWindowText](cwnd-class.md#getwindowtext)編集の内容全体を制御する設定または取得の場合でも、その複数行のコントロール。 複数行のコントロールでテキストの行は、"\r\n"文字のシーケンスで区切られます。 また、エディット コントロールが複数行の場合は、取得し、呼び出すことによって、コントロールのテキストの一部を設定、`CEdit`メンバー関数[GetLine](#getline)、 [SetSel](#setsel)、 [GetSel](#getsel)、および[ReplaceSel](#replacesel)します。

エディット コントロールからその親に送信される Windows 通知メッセージを処理する場合 (通常はから派生したクラス`CDialog`)、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。

各メッセージ マップ エントリは、次の形式をとります。

  **ON_**_NOTIFICATION_**(** _id_**,** _memberFxn_ **)**

場所`id`、通知を送信するエディット コントロールの子ウィンドウ ID を指定し、`memberFxn`通知を処理するために記述した親メンバー関数の名前を指定します。

親の関数のプロトタイプは次のとおりです。

**afx_msg** void memberFxn **( );**

次は、潜在的なメッセージ マップ エントリと親に送信するケースの説明の一覧に示します。

- ON_EN_CHANGE、ユーザーがエディット コントロールでテキストを変更可能性があるアクションをしました。 EN_UPDATE 通知メッセージとは異なりこの通知メッセージは、Windows の更新が、表示後に送信されます。

- ON_EN_ERRSPACE エディット コントロールでは、特定の要求を満たすために十分なメモリを割り当てることができません。

- ON_EN_HSCROLL、ユーザーは、編集コントロールの水平スクロール バーをクリックします。 画面が更新される前に、親ウィンドウに通知されます。

- ON_EN_KILLFOCUS エディット コントロールには、入力フォーカスが失われます。

- ON_EN_MAXTEXT 現在のカーソルでは、エディット コントロールの文字の指定した数を超えました、切り詰められました。 エディット コントロールに ES_AUTOHSCROLL スタイルが含まれておらず、エディット コントロールの幅を挿入する文字数を超えるときにも送信されます。 エディット コントロールに ES_AUTOVSCROLL スタイルがないし、編集コントロールの高さを超える結果のテキストの挿入行の合計数も送信されます。

- ON_EN_SETFOCUS は、エディット コントロールが入力フォーカスを受け取るときに送信されます。

- ON_EN_UPDATE テキスト表示の変更の詳細については、エディット コントロール。 コントロールがテキストを書式設定後、そのテキストを表示するため、ウィンドウのサイズを変更することができます、必要に応じて前に送信されます。

- ON_EN_VSCROLL、ユーザーは、編集コントロールの垂直スクロール バーをクリックします。 画面が更新される前に、親ウィンドウに通知されます。

作成する場合、 `CEdit`  ダイアログ ボックスでは、内のオブジェクト、 `CEdit`  ダイアログ ボックスを閉じると、オブジェクトが自動的に破棄されます。

作成する場合、`CEdit`ダイアログ エディターを使用して、ダイアログ リソースからのオブジェクト、 `CEdit`  ダイアログ ボックスを閉じると、オブジェクトが自動的に破棄されます。

作成する場合、`CEdit`を破棄する必要がありますも、ウィンドウ内でオブジェクトします。 作成する場合、`CEdit`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CEdit`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**オブジェクトを破棄して、ユーザー、Windows の終了時にコントロールを編集します。 メモリを割り当てることがある場合、`CEdit`オブジェクト、オーバーライド、`CEdit`デストラクターの割り当てを破棄します。

編集コントロール (ES_READONLY) などの特定のスタイルを変更するコントロールを使用する代わりに特定のメッセージを送信する必要があります[は](cwnd-class.md#modifystyle)します。 参照してください[コントロールのスタイルを編集](/windows/desktop/Controls/edit-control-styles)Windows SDK にします。

詳細については`CEdit`を参照してください[コントロール](../../mfc/controls-mfc.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="canundo"></a>  CEdit::CanUndo

最後の編集操作を元に戻すことができるかどうかを判断するには、この関数を呼び出します。

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>戻り値

呼び出しで最後の編集操作を取り消すことができる場合、0 以外の場合、`Undo`メンバー関数は元に戻すことができない場合は 0。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [EM_CANUNDO](/windows/desktop/Controls/em-canundo) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEdit::Undo](#undo)します。

##  <a name="cedit"></a>  CEdit::CEdit

`CEdit` オブジェクトを構築します。

```
CEdit();
```

### <a name="remarks"></a>Remarks

使用[作成](#create)Windows のエディット コントロールを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

##  <a name="charfrompos"></a>  CEdit::CharFromPos

これで、指定したポイントに最も近い文字の文字のインデックスおよび 0 から始まる行を取得するには、この関数を呼び出す`CEdit`コントロール

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
これのクライアント領域内のポイントの座標`CEdit`オブジェクト。

### <a name="return-value"></a>戻り値

下位の WORD で文字のインデックスと上位の単語の行インデックス。

### <a name="remarks"></a>Remarks

> [!NOTE]
>  このメンバー関数は、Windows 95 と Windows NT 4.0 以降を使用できます。

詳細については、次を参照してください。 [EM_CHARFROMPOS](/windows/desktop/Controls/em-charfrompos) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

##  <a name="clear"></a>  CEdit::Clear

編集コントロールに現在の選択 (ある場合) 削除、(オフ) するには、この関数を呼び出します。

```
void Clear();
```

### <a name="remarks"></a>Remarks

によって実行された削除`Clear`呼び出すことによって、元に戻すことができます、[を元に戻す](#undo)メンバー関数。

現在の選択範囲を削除し、削除された内容をクリップボードに配置、電話、[切り取り](#cut)メンバー関数。

詳細については、次を参照してください。 [WM_CLEAR](/windows/desktop/dataxchg/wm-clear) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

##  <a name="copy"></a>  CEdit::Copy

この関数を呼び出してコピー現在の選択 (あれば) されているテキスト形式でクリップボードに編集コントロールにします。

```
void Copy();
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [WM_COPY](/windows/desktop/dataxchg/wm-copy) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

##  <a name="create"></a>  CEdit::Create

Windows のエディット コントロールを作成しにアタッチします、`CEdit`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
編集コントロールのスタイルを指定します。 任意の組み合わせを適用[エディット スタイル](styles-used-by-mfc.md#edit-styles)コントロールにします。

*rect*<br/>
編集コントロールのサイズと位置を指定します。 `CRect`オブジェクトまたは`RECT`構造体。

*pParentWnd*<br/>
編集コントロールの親ウィンドウを指定します (通常、 `CDialog`)。 NULL は指定できません。

*nID*<br/>
編集コントロールの ID を指定します

### <a name="return-value"></a>戻り値

初期化が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

構築する、 `CEdit` 2 つのステップ内のオブジェクト。 最初に、呼び出し、`CEdit`コンス トラクターと、呼び出し`Create`、Windows のエディット コントロールを作成しにアタッチする`CEdit`オブジェクト。

ときに`Create`実行されると、Windows の送信、 [WM_NCCREATE](/windows/desktop/winmsg/wm-nccreate)、 [WM_NCCALCSIZE](/windows/desktop/winmsg/wm-nccalcsize)、 [WM_CREATE](/windows/desktop/winmsg/wm-create)、および[WM_GETMINMAXINFO](/windows/desktop/winmsg/wm-getminmaxinfo)編集コントロールにメッセージです。

既定でこれらのメッセージが処理されます、 [OnNcCreate](cwnd-class.md#onnccreate)、 [OnNcCalcSize](cwnd-class.md#onnccalcsize)、 [OnCreate](cwnd-class.md#oncreate)、および[OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo)メンバー関数`CWnd`基本クラス。 既定のメッセージ処理を拡張するには、派生クラスを`CEdit`メッセージ マップを新しいクラスに追加し、上記のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`、たとえば、新しいクラスに必要な初期化を実行します。

次の適用[ウィンドウ スタイル](styles-used-by-mfc.md#window-styles)エディット コントロールにします。

- WS_CHILD 常に

- WS_VISIBLE 通常

- WS_DISABLED ことはほとんどありません。

- WS_GROUP コントロールをグループ化

- 編集コントロールをタブの順に含める WS_TABSTOP

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

##  <a name="cut"></a>  CEdit::Cut

エディット コントロールで現在の選択 (ある場合) (切り取り) を削除するには、この関数を呼び出すし、削除されたテキストをされているテキスト形式でクリップボードにコピーします。

```
void Cut();
```

### <a name="remarks"></a>Remarks

によって実行された削除`Cut`呼び出すことによって、元に戻すことができます、[を元に戻す](#undo)メンバー関数。

削除されたテキストをクリップボードに配置することがなく現在の選択範囲を削除する、[クリア](#clear)メンバー関数。

詳細については、次を参照してください。 [WM_CUT](/windows/desktop/dataxchg/wm-cut) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer

エディット コントロールの元に戻すフラグ (クリア) をリセットするには、この関数を呼び出します。

```
void EmptyUndoBuffer();
```

### <a name="remarks"></a>Remarks

エディット コントロールが、最後の操作を元に戻すことは今すぐします。 編集コントロール内の操作は完了できないときに、元に戻すフラグが設定されます。

元に戻すフラグは、自動的にクリアされるたびに、 [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)または[SetHandle](#sethandle) `CWnd`メンバー関数が呼び出されます。

詳細については、次を参照してください。 [EM_EMPTYUNDOBUFFER](/windows/desktop/Controls/em-emptyundobuffer) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

##  <a name="fmtlines"></a>  CEdit::FmtLines

複数行のエディット コントロール内のソフトの改行文字を含めることをオンまたはオフに設定するには、この関数を呼び出します。

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>パラメーター

*bAddEOL*<br/>
ソフトの改行文字が挿入されるかどうかを指定します。 値が TRUE の文字は; を挿入しますFALSE の値は、それらを削除します。

### <a name="return-value"></a>戻り値

存在する場合、0 以外の値の書式設定が発生します。それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

論理的な改行は、2 つのキャリッジ リターンとラインフィード ワード ラップにより分割された行の末尾に挿入で構成されます。 ハード改行は、1 つのキャリッジ リターンとラインフィードで構成されます。 ハード改行で終了する行の影響を受けない`FmtLines`します。

Windows は、場合にのみ応答、`CEdit`オブジェクトが複数行のエディット コントロール。

`FmtLines` によって返されるバッファーにのみ影響[GetHandle](#gethandle)とによって返されるテキスト[WM_GETTEXT](/windows/desktop/winmsg/wm-gettext)します。 編集コントロール内のテキストの表示に影響を与えません。

詳細については、次を参照してください。 [EM_FMTLINES](/windows/desktop/Controls/em-fmtlines) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

##  <a name="getcuebanner"></a>  CEdit::GetCueBanner

ヒントのテキストまたはコントロールが空の場合、エディット コントロールでのヒントとして表示されるテキストを取得します。

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[out]ヒントのテキストを含む文字列へのポインター。

*cchText*<br/>
[in]受信できる文字数。 この数値には、終端の NULL 文字が含まれます。

### <a name="return-value"></a>戻り値

最初のオーバー ロードのメソッドが成功した場合は TRUE します。それ以外の場合は FALSE です。

2 番目のオーバー ロードを[CString](../../atl-mfc-shared/using-cstring.md)メソッドが成功した。 それ以外の場合は、キュー テキストを含む空の文字列 ("")。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [EM_GETCUEBANNER](/windows/desktop/Controls/em-getcuebanner)メッセージは、Windows SDK で説明します。 詳細については、次を参照してください。、 [Edit_GetCueBannerText](/windows/desktop/api/commctrl/nf-commctrl-edit_getcuebannertext)マクロ。

##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine

エディット コントロールに表示されている最上位の行を判断するには、この関数を呼び出します。

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>戻り値

最上位に表示されている行の 0 から始まるインデックス。 単一行のエディット コントロールでは、戻り値は 0 です。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [EM_GETFIRSTVISIBLELINE](/windows/desktop/Controls/em-getfirstvisibleline) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

##  <a name="gethandle"></a>  CEdit::GetHandle

複数行のエディット コントロールに現在割り当てられているメモリを識別するハンドルを取得するには、この関数を呼び出します。

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>戻り値

編集コントロールの内容を保持するバッファーを識別するローカル メモリ ハンドルを指定します。 単一行のエディット コントロールにメッセージを送信するなどのエラーが発生した場合、戻り値は 0 です。

### <a name="remarks"></a>Remarks

ハンドルは、ローカル メモリ ハンドルしのいずれかで使用できる、**ローカル**ローカル メモリを確認する Windows メモリ関数をパラメーターとして処理します。

`GetHandle` 複数行のエディット コントロールでのみ処理されます。

呼び出す`GetHandle`DS_LOCALEDIT スタイルのフラグ設定 ダイアログ ボックスが作成された場合にのみ、ダイアログ ボックスで複数行のエディット コントロール。 DS_LOCALEDIT スタイルが設定されていない場合は、0 以外の戻り値が表示が、返された値を使用することはできません。

> [!NOTE]
> `GetHandle` Windows 95/98 では機能しません。 呼び出す場合`GetHandle`Windows 95/98 では NULL を返します。 `GetHandle` Windows NT version 3.51 以降の下に記載されているが機能します。

詳細については、次を参照してください。 [EM_GETHANDLE](/windows/desktop/Controls/em-gethandle) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

##  <a name="gethighlight"></a>  CEdit::GetHighlight

現在の編集コントロールで強調表示されているテキストの範囲内には、最初と最後の文字のインデックスを取得します。

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pichStart*|[out]強調表示されているテキストの範囲の最初の文字の 0 から始まるインデックス。|
|*pichEnd*|[out]強調表示されているテキストの範囲の最後の文字の 0 から始まるインデックス。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [EM_GETHILITE](/windows/desktop/Controls/em-gethilite)メッセージは、Windows SDK で説明します。 両方`SetHighlight`と`GetHighlight`UNICODE ビルドのみの場合、現在有効になっています。

##  <a name="getlimittext"></a>  CEdit::GetLimitText

このテキストの上限を取得するには、このメンバー関数を呼び出す`CEdit`オブジェクト。

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>戻り値

現在のテキストの制限、Tchar でこの`CEdit`オブジェクト。

### <a name="remarks"></a>Remarks

テキストの上限は、エディット コントロールが受け入れることができる、Tchar 内のテキストの最大量です。

> [!NOTE]
>  このメンバー関数は、Windows 95 と Windows NT 4.0 以降を使用できます。

詳細については、次を参照してください。 [EM_GETLIMITTEXT](/windows/desktop/Controls/em-getlimittext) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

##  <a name="getline"></a>  CEdit::GetLine

エディット コントロールから行のテキストを取得するには、この関数を呼び出すし、配置で*lpszBuffer*します。

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

*nIndex*<br/>
コントロールの編集から複数行を取得する行番号を指定します。 行番号は 0 から始まります。値 0 は、最初の行を指定します。 単一行のエディット コントロールでは、このパラメーターは無視されます。

*lpszBuffer*<br/>
行のコピーを受け取るバッファーへのポインター。 バッファーの最初の単語は、バッファーにコピーする Tchar の最大数を指定する必要があります。

*nMaxLength*<br/>
バッファーにコピーする TCHAR 文字の最大数を指定します。 `GetLine` 最初の単語でこの値を配置*lpszBuffer* Windows への呼び出しを行う前にします。

### <a name="return-value"></a>戻り値

実際にコピーされた文字数。 行番号が指定された場合、戻り値は 0 *nIndex*がエディット コントロールで行の数より大きい。

### <a name="remarks"></a>Remarks

コピーした行に null 終端文字が含まれていません。

詳細については、次を参照してください。 [EM_GETLINE](/windows/desktop/Controls/em-getline) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEdit::GetLineCount](#getlinecount)します。

##  <a name="getlinecount"></a>  CEdit::GetLineCount

複数行のエディット コントロールで行の数を取得するには、この関数を呼び出します。

```
int GetLineCount() const;
```

### <a name="return-value"></a>戻り値

編集コントロールの複数行の行の数を表す整数。 エディット コントロールにテキストが入力されていない場合、戻り値は 1 です。

### <a name="remarks"></a>Remarks

`GetLineCount` 複数行のエディット コントロールでのみ処理されます。

詳細については、次を参照してください。 [EM_GETLINECOUNT](/windows/desktop/Controls/em-getlinecount) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

##  <a name="getmargins"></a>  CEdit::GetMargins

この編集コントロールの左と右の余白を取得するには、このメンバー関数を呼び出します。

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>戻り値

下位ワードと上位の単語の右余白の幅で左余白の幅。

### <a name="remarks"></a>Remarks

余白は、ピクセル単位で測定されます。

> [!NOTE]
>  このメンバー関数は、Windows 95 と Windows NT 4.0 以降を使用できます。

詳細については、次を参照してください。 [EM_GETMARGINS](/windows/desktop/Controls/em-getmargins) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)します。

##  <a name="getmodify"></a>  CEdit::GetModify

エディット コントロールの内容が変更されたかどうかを判断するには、この関数を呼び出します。

```
BOOL GetModify() const;
```

### <a name="return-value"></a>戻り値

編集コントロールの内容が変更された場合は 0 以外0 のままである場合は変更されません。

### <a name="remarks"></a>Remarks

Windows では、エディット コントロールの内容が変更されたかどうかを示す内部フラグを保持します。 このフラグをクリア エディット コントロールが最初に作成し、呼び出すことによってもクリアすることがあります、 [SetModify](#setmodify)メンバー関数。

詳細については、次を参照してください。 [EM_GETMODIFY](/windows/desktop/Controls/em-getmodify) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar

テキストを入力したときに、エディット コントロールに表示されるパスワードの文字を取得するには、この関数を呼び出します。

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>戻り値

ユーザーが入力した文字の代わりに表示する文字を指定します。 パスワードの文字が存在しない場合、戻り値は NULL です。

### <a name="remarks"></a>Remarks

ES_PASSWORD スタイルを使用して、編集コントロールを作成する場合、コントロールをサポートする DLL は、既定のパスワード文字を決定します。 マニフェストまたは[InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) DLL をサポートするメソッドを判断しますエディット コントロール。 既定のパスワード文字はアスタリスク、user32.dll、編集コントロールをサポートする場合 ('* '、U +002)。 Comctl32.dll バージョン 6 では、エディット コントロールをサポートする場合、既定の文字は、黒の丸 ('●'、U + 25CF) は。 DLL およびバージョン サポートの詳細については、一般的なコントロールを参照してください[シェルと共通コントロール バージョン](https://msdn.microsoft.com/library/windows/desktop/bb776779)します。

このメソッドは、送信、 [EM_GETPASSWORDCHAR](/windows/desktop/Controls/em-getpasswordchar)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

##  <a name="getrect"></a>  CEdit::GetRect

エディット コントロールの書式設定の四角形を取得するには、この関数を呼び出します。

```
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
指す、`RECT`書式設定の四角形を受け取る構造体。

### <a name="remarks"></a>Remarks

書式設定の四角形は、編集コントロール ウィンドウのサイズに依存しませんが、テキストの外接する四角形です。

によって複数行のエディット コントロールの書式設定の四角形を変更することができます、 [SetRect](#setrect)と[角形](#setrectnp)メンバー関数。

詳細については、次を参照してください。 [EM_GETRECT](/windows/desktop/Controls/em-getrect) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEdit::LimitText](#limittext)します。

##  <a name="getsel"></a>  CEdit::GetSel

開始と終了文字位置の戻り値またはパラメーターを使用して、編集コントロールの現在の選択 (ある場合) を取得するには、この関数を呼び出します。

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>パラメーター

*nStartChar*<br/>
現在選択されている最初の文字の位置を受信する整数への参照。

*nEndChar*<br/>
現在の選択範囲の末尾を越えた最初の選択されていない文字の位置を受信する整数への参照。

### <a name="return-value"></a>戻り値

Dword バージョンでは、上位の単語の選択範囲の終了後の下位ワード内の開始位置と選択されていない最初の文字の位置を格納している値を返します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [EM_GETSEL](/windows/desktop/Controls/em-getsel) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip

現在の編集コントロールに関連付けられているバルーン ヒントを非表示にします。

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

この関数は送信、 [EM_HIDEBALLOONTIP](/windows/desktop/Controls/em-hideballoontip)メッセージは、Windows SDK で説明します。

##  <a name="limittext"></a>  CEdit::LimitText

ユーザーがエディット コントロールに入力されるテキストの長さを制限するには、この関数を呼び出します。

```
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>パラメーター

*文字数*<br/>
(Tchar) で、ユーザーが入力できるテキストの長さを指定します。 このパラメーターが 0 の場合は、テキストの長さが UINT_MAX バイトに設定されます。 これが既定の動作です。

### <a name="remarks"></a>Remarks

テキストの上限を変更するには、ユーザーが入力できるテキストのみが制限されます。 影響を与えません任意のテキストで既に編集コントロールにもコピーして編集コントロールにテキストの長さに影響は、 [SetWindowText](cwnd-class.md#setwindowtext)メンバー関数で`CWnd`します。 アプリケーションで使用する場合、`SetWindowText`関数への呼び出しで指定されているよりエディット コントロールにテキストを配置する`LimitText`ユーザーがエディット コントロール内のテキストのいずれかを削除できます。 ただし、テキストの上限は、既存のテキストを新しいテキストに置き換えてから、ユーザーを防ぐ、により、テキストの制限を下回る、テキストの現在の選択範囲を削除しない限り。

> [!NOTE]
>  Win32 の (Windows NT および Windows 95/98) [SetLimitText](#setlimittext)この関数に置き換えられます。

詳細については、次を参照してください。 [EM_LIMITTEXT](/windows/desktop/Controls/em-limittext) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

##  <a name="linefromchar"></a>  CEdit::LineFromChar

指定された文字インデックスを含む行の行番号を取得するには、この関数を呼び出します。

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
編集コントロールのテキストで、目的の文字の 0 から始まるインデックス値を格納するか、-1 を含んでいます。 場合*nIndex* -1、カーソルの行は、現在の行を指定します。

### <a name="return-value"></a>戻り値

指定された文字インデックスを含む行の 0 から始まる行番号*nIndex*します。 場合*nIndex* -1 で、選択範囲の最初の文字を含んでいる行の数が返されます。 選択されていない場合は、現在の行番号が返されます。

### <a name="remarks"></a>Remarks

文字のインデックスには、エディット コントロールの先頭からの文字数です。

このメンバー関数は、複数行のエディット コントロールでのみ使用されます。

詳細については、次を参照してください。 [EM_LINEFROMCHAR](/windows/desktop/Controls/em-linefromchar) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

##  <a name="lineindex"></a>  CEdit::LineIndex

複数行のエディット コントロール内の行の文字インデックスを取得するには、この関数を呼び出します。

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>パラメーター

*n 行*<br/>
編集コントロールのテキストで目的の行のインデックス値を格納するか、-1 を含んでいます。 場合*n 行*-1、カーソルの行は、現在の行を指定します。

### <a name="return-value"></a>戻り値

指定された行の文字インデックス*n 行*または指定した行番号が、編集コントロール内の行の数よりも大きい場合は-1。

### <a name="remarks"></a>Remarks

文字のインデックスには、編集コントロールの先頭から指定した行の文字数です。

このメンバー関数は、複数行のエディット コントロールでのみ処理されます。

詳細については、次を参照してください。 [EM_LINEINDEX](https://msdn.microsoft.com/library/windows/desktop/bb761611) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

##  <a name="linelength"></a>  CEdit::LineLength

編集コントロール内の行の長さを取得します。

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>パラメーター

*n 行*<br/>
長さを取得する行の文字の 0 から始まるインデックス。 既定値は -1 です。

### <a name="return-value"></a>戻り値

単一行のエディット コントロールでは、戻り値は、編集コントロール内のテキストの長さ、Tchar が。

複数行のエディット コントロールでは、戻り値で指定された行の長さ、Tchar、 *n 行*パラメーター。 ANSI テキスト、長さは、行のバイト数です。Unicode テキストの長さは、行の文字の数です。 長さでは、行の末尾にあるキャリッジ リターン文字は含まれません。

場合、 *n 行*パラメーターがコントロール内の文字数よりも多い、戻り値は 0。

場合、 *n 行*パラメーターが-1、戻り値が選択されていない文字を選択した文字を含む行の数。 たとえば、次の行の末尾からの 8 番目の文字を 1 つの行の 4 番目の文字から選択範囲の場合、戻り値は 10 です。 つまり、3 つの文字を 1 行目と 7 にします。

TCHAR 型の詳細については、TCHAR 行のテーブルを参照してください。[データ型の Windows](/windows/desktop/WinProg/windows-data-types)します。

### <a name="remarks"></a>Remarks

このメソッドはサポート、 [EM_LINELENGTH](/windows/desktop/Controls/em-linelength)メッセージは、Windows SDK で説明されています。

### <a name="example"></a>例

  例をご覧ください[CEdit::LineIndex](#lineindex)します。

##  <a name="linescroll"></a>  CEdit::LineScroll

複数行のエディット コントロールのテキストをスクロールするには、この関数を呼び出します。

```
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>パラメーター

*nLines*<br/>
垂直方向にスクロールする行数を指定します。

*文字数*<br/>
水平方向にスクロールする文字位置の数を指定します。 この値には、編集コントロールが ES_RIGHT または ES_CENTER のいずれかのスタイルは無視されます。

### <a name="remarks"></a>Remarks

このメンバー関数は、複数行のエディット コントロールでのみ処理されます。

エディット コントロールが過去の最後の行が編集コントロールのテキストの垂直方向にスクロールされません。 かどうか、現在の改行で指定された行の数を足す*nLines*エディット コントロール内の行の合計数を超える場合、エディット コントロールの最後の行が編集コントロール ウィンドウの一番上にスクロールするために値が調整されます。

`LineScroll` 過去の任意の行の最後の文字、水平方向にスクロールするために使用します。

詳細については、次を参照してください。 [EM_LINESCROLL](/windows/desktop/Controls/em-linescroll) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEdit::GetFirstVisibleLine](#getfirstvisibleline)します。

##  <a name="paste"></a>  CEdit::Paste

クリップボードからデータを挿入するには、この関数を呼び出す、`CEdit`カーソルの位置。

```
void Paste();
```

### <a name="remarks"></a>Remarks

クリップボードにされているテキスト形式のデータが含まれている場合にのみデータが挿入されます。

詳細については、次を参照してください。 [WM_PASTE](/windows/desktop/dataxchg/wm-paste) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

##  <a name="posfromchar"></a>  CEdit::PosFromChar

この特定の文字の位置 (左上隅) を取得するには、この関数を呼び出す`CEdit`オブジェクト。

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>パラメーター

*NChar*<br/>
指定した文字の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定された文字の左上隅の座標*nChar*します。

### <a name="remarks"></a>Remarks

文字を指定するには、その 0 から始まるインデックス値を提供します。 場合*nChar*がこの最後の文字のインデックスよりも大きい`CEdit`オブジェクト、戻り値の最後の文字の直後の文字位置の座標を指定しますこの`CEdit`オブジェクト。

> [!NOTE]
>  このメンバー関数は、Windows 95 と Windows NT 4.0 以降を使用できます。

詳細については、次を参照してください。 [EM_POSFROMCHAR](/windows/desktop/Controls/em-posfromchar) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEdit::LineFromChar](#linefromchar)します。

##  <a name="replacesel"></a>  CEdit::ReplaceSel

指定されたテキスト編集コントロールの現在の選択を置換するには、この関数を呼び出す*されている*します。

```
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>パラメーター

*lpszNewText*<br/>
置換テキストを含む null で終わる文字列へのポインター。

*bCanUndo*<br/>
この関数が実行できることを指定するには、このパラメーターの値を TRUE に設定します。 既定値は FALSE です。

### <a name="remarks"></a>Remarks

エディット コントロールでテキストの一部のみが置き換えられます。 すべてのテキストを置換する場合を使用して、[とき](cwnd-class.md#setwindowtext)メンバー関数。

現在の選択項目がない場合、置換テキストは、現在のカーソル位置に挿入されます。

詳細については、次を参照してください。 [EM_REPLACESEL](/windows/desktop/Controls/em-replacesel) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEdit::LineIndex](#lineindex)します。

##  <a name="setcuebanner"></a>  CEdit::SetCueBanner

または、ヒントのテキストとして表示されるヒントは、エディット コントロールとコントロールが空のテキストを設定します。

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[in]エディット コントロールに表示されるヒントを含む文字列へのポインター。

*fDrawWhenFocused*<br/>
[in]FALSE の場合、ユーザーがエディット コントロールでクリックするし、コントロール、フォーカス キュー バナーは描画されません。

TRUE の場合、コントロールにフォーカスがある場合でも、キュー バナーを描画します。 キュー バナーは、ユーザーがコントロールに入力を開始すると表示されなくなります。

既定値は FALSE です。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [EM_SETCUEBANNER](/windows/desktop/Controls/em-setcuebanner)メッセージは、Windows SDK で説明します。 詳細については、次を参照してください。、 [Edit_SetCueBannerTextFocused](/windows/desktop/api/commctrl/nf-commctrl-edit_setcuebannertextfocused)マクロ。

### <a name="example"></a>例

次の例で、 [CEdit::SetCueBanner](#setcuebanner)メソッド。

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

##  <a name="sethandle"></a>  CEdit::SetHandle

複数行のエディット コントロールで使用されるローカル メモリへのハンドルを設定するには、この関数を呼び出します。

```
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>パラメーター

*hBuffer*<br/>
ローカル メモリを識別するハンドルが含まれています。 このハンドルを以前の呼び出しで作成する必要があります、 [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc) Windows 関数が、あらかじめフラグを使用します。 メモリは、null で終わる文字列を格納すると見なされます。 場合はサポートしていない場合は、割り当てられたメモリの最初のバイトが 0 に設定する必要があります。

### <a name="remarks"></a>Remarks

エディット コントロール自体のバッファーを割り当てる代わりに現在表示されているテキストを格納するのにバッファーが使用されます。

このメンバー関数は、複数行のエディット コントロールでのみ処理されます。

使用するアプリケーションでは、新しいメモリ ハンドルを設定、前に、 [GetHandle](#gethandle)メンバー関数を現在のメモリ バッファーへのハンドルを取得し、空きメモリを使用して、 `LocalFree` Windows 関数。

`SetHandle` 元に戻すバッファーをクリアします (、 [CanUndo](#canundo)メンバー関数は、0 を返します) と内部の変更フラグ (、[この](#getmodify)メンバー関数は、0 を返します)。 編集コントロールのウィンドウが再描画されます。

DS_LOCALEDIT スタイルのフラグ設定 ダイアログ ボックスを作成した場合にのみ、ダイアログ ボックスで、複数行のエディット コントロールでは、このメンバー関数を使用できます。

> [!NOTE]
> `GetHandle` Windows 95/98 では機能しません。 呼び出す場合`GetHandle`Windows 95/98 では NULL を返します。 `GetHandle` Windows NT version 3.51 以降の下に記載されているが機能します。

詳細については、次を参照してください。 [EM_SETHANDLE](/windows/desktop/Controls/em-sethandle)、 [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc)、および[LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

##  <a name="sethighlight"></a>  CEdit::SetHighlight

強調表示、現在の表示されるテキストの範囲は、コントロールを編集します。

```
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ichStart*|[in]強調表示するテキストの範囲の最初の文字の 0 から始まるインデックス。|
|*ichEnd*|[in]強調表示するテキストの範囲の最後の文字の 0 から始まるインデックス。|

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [EM_SETHILITE](/windows/desktop/Controls/em-sethilite)メッセージは、Windows SDK で説明します。  このメソッドは、送信、 [EM_SETHILITE](/windows/desktop/Controls/em-sethilite)メッセージは、Windows SDK で説明します。 両方`SetHighlight`と`GetHighlight`の UNICODE ビルドでのみ有効になっています。

##  <a name="setlimittext"></a>  CEdit::SetLimitText

このテキストの上限を設定するには、このメンバー関数を呼び出す`CEdit`オブジェクト。

```
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>パラメーター

*nMax*<br/>
文字で、新しいテキスト制限。

### <a name="remarks"></a>Remarks

テキストの上限は、エディット コントロールが受け入れることができる文字数のテキストの最大量です。

テキストの上限を変更するには、ユーザーが入力できるテキストのみが制限されます。 影響を与えません任意のテキストで既に編集コントロールにもコピーして編集コントロールにテキストの長さに影響は、 [SetWindowText](cwnd-class.md#setwindowtext)メンバー関数で`CWnd`します。 アプリケーションで使用する場合、`SetWindowText`関数への呼び出しで指定されているよりエディット コントロールにテキストを配置する`LimitText`ユーザーがエディット コントロール内のテキストのいずれかを削除できます。 ただし、テキストの上限は、既存のテキストを新しいテキストに置き換えてから、ユーザーを防ぐ、により、テキストの制限を下回る、テキストの現在の選択範囲を削除しない限り。

この関数に置き換えられます[LimitText](#limittext) Win32 でします。

詳細については、次を参照してください。 [EM_SETLIMITTEXT](/windows/desktop/Controls/em-setlimittext) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)します。

##  <a name="setmargins"></a>  CEdit::SetMargins

この編集コントロールの左と右の余白を設定するには、このメソッドを呼び出します。

```
void SetMargins(
    UINT nLeft,
    UINT nRight);
```

### <a name="parameters"></a>パラメーター

*nLeft*<br/>
ピクセル単位では、新しい左余白の幅。

*nRight*<br/>
ピクセル単位では、新しい右余白の幅。

### <a name="remarks"></a>Remarks

> [!NOTE]
>  このメンバー関数は、Windows 95 と Windows NT 4.0 以降を使用できます。

詳細については、次を参照してください。 [EM_SETMARGINS](/windows/desktop/Controls/em-setmargins) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)します。

##  <a name="setmodify"></a>  CEdit::SetModify

設定または編集コントロールの変更フラグをオフにするには、この関数を呼び出します。

```
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>パラメーター

*bModified*<br/>
値が TRUE のことを示し、テキストを変更すると、FALSE の値は変更されませんをことを示します。 既定では、変更のフラグが設定されます。

### <a name="remarks"></a>Remarks

変更されたフラグは、編集コントロール内のテキストが変更されたかどうかを示します。 ユーザーがテキストを変更するたびに自動的に設定されます。 その値を取得することがあります、[この](#getmodify)メンバー関数。

詳細については、次を参照してください。 [EM_SETMODIFY](/windows/desktop/Controls/em-setmodify) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEdit::GetModify](#getmodify)します。

##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar

設定またはユーザーがテキストを入力すると、エディット コントロールに表示されるパスワード文字を削除するには、この関数を呼び出します。

```
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
ユーザーが入力文字の代わりに表示する文字を指定します。 場合*ch*が 0 の場合、ユーザーによって入力された実際の文字が表示されます。

### <a name="remarks"></a>Remarks

パスワードの文字が設定されている場合は、各文字をユーザーがその文字が表示されます。

このメンバー関数は、編集コントロールの複数行に影響を与えません。

ときに、`SetPasswordChar`メンバー関数が呼び出されると、`CEdit`で指定された文字を使用してすべての表示の文字を再描画*ch*します。

編集コントロールが作成された場合、 [ES_PASSWORD](styles-used-by-mfc.md#edit-styles)スタイル、既定のパスワード文字はアスタリスクを設定 ( <strong>\*</strong>)。 このスタイルは`SetPasswordChar`を使用して呼び出した*ch*を 0 に設定します。

詳細については、次を参照してください。 [EM_SETPASSWORDCHAR](/windows/desktop/Controls/em-setpasswordchar) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

##  <a name="setreadonly"></a>  CEdit::SetReadOnly

エディット コントロールの読み取り専用の状態を設定するには、この関数を呼び出します。

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>パラメーター

*bReadOnly*<br/>
設定または編集コントロールの読み取り専用の状態を削除するかどうかを指定します。 TRUE の値を読み取り専用状態を設定します。FALSE の値は、読み取り/書き込み状態を設定します。

### <a name="return-value"></a>戻り値

以外の場合は、操作が成功するか、エラーが 0 の場合に発生します。

### <a name="remarks"></a>Remarks

現在の設定をテストして、存在、 [ES_READONLY](styles-used-by-mfc.md#edit-styles)の戻り値のフラグ[状態](cwnd-class.md#getstyle)します。

詳細については、次を参照してください。 [EM_SETREADONLY](/windows/desktop/Controls/em-setreadonly) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

##  <a name="setrect"></a>  CEdit::SetRect

指定した座標を使用して四角形の寸法を設定するには、この関数を呼び出します。

```
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
指す、`RECT`構造または`CRect`新しい書式設定の四角形の寸法を指定するオブジェクト。

### <a name="remarks"></a>Remarks

このメンバーは、複数行のエディット コントロールでのみ処理されます。

使用`SetRect`複数行の四角形は、書式を設定するコントロールを編集します。 書式設定の四角形は、編集コントロール ウィンドウのサイズに依存しませんが、テキストの外接する四角形です。 編集コントロールが作成されると、書式設定の四角形は、エディット コントロール ウィンドウのクライアント領域の場合と同じです。 使用して、`SetRect`メンバー関数は、アプリケーションと、書式設定の四角形エディット コントロールのウィンドウより大きいか小さい。

スクロール バーがエディット コントロールがない場合は、テキストが切り取られるでラップされていない場合、書式設定の四角形のウィンドウよりも大きいが行われた場合。 エディット コントロールに境界線が含まれている場合、境界線のサイズによって、書式設定の四角形が減少します。 によって返される四角形を調整する場合は、`GetRect`メンバー関数は、対象の四角形を渡す前に、境界線のサイズを削除する必要があります`SetRect`します。

ときに`SetRect`を呼び出すと、編集コントロールのテキストも再フォーマットし、再表示されます。

詳細については、次を参照してください。 [EM_SETRECT](/windows/desktop/Controls/em-setrect) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

##  <a name="setrectnp"></a>  CEdit::SetRectNP

複数行のエディット コントロールの書式設定の四角形を設定するには、この関数を呼び出します。

```
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
指す、`RECT`構造または`CRect`新しい四角形の寸法を指定するオブジェクト。

### <a name="remarks"></a>Remarks

書式設定の四角形は、編集コントロール ウィンドウのサイズに依存しませんが、テキストの外接する四角形です。

`SetRectNP` 同じですが、`SetRect`のメンバー関数が、編集コントロールのウィンドウが再描画されません。

編集コントロールが作成されると、書式設定の四角形は、エディット コントロール ウィンドウのクライアント領域の場合と同じです。 呼び出すことによって、`SetRectNP`メンバー関数は、アプリケーションと、書式設定の四角形エディット コントロールのウィンドウより大きいか小さい。

スクロール バーがエディット コントロールがない場合は、テキストが切り取られるでラップされていない場合、書式設定の四角形のウィンドウよりも大きいが行われた場合。

このメンバーは、複数行のエディット コントロールでのみ処理されます。

詳細については、次を参照してください。 [EM_SETRECTNP](/windows/desktop/Controls/em-setrectnp) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEdit::SetRect](#setrect)します。

##  <a name="setsel"></a>  CEdit::SetSel

エディット コントロールでの文字の範囲を選択するには、この関数を呼び出します。

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

*dwSelection*<br/>
下位ワード内の開始位置と終了位置の上位ワードを指定します。 下位ワードが 0 で、上位の単語が-1 の場合、編集コントロール内のすべてのテキストが選択されます。 下位ワードが-1 の場合は、現在の選択項目が削除されます。

*bNoScroll*<br/>
カレットをスクロールして表示するかどうかを示します。 FALSE の場合、カーソルをスクロールして表示します。 TRUE の場合、カーソルはスクロールして表示できません。

*nStartChar*<br/>
開始位置を指定します。 場合*nStartChar*は 0 と*nEndChar* -1 で、編集コントロール内のテキストが選択されているすべて。 場合*nStartChar* -1 で、現在の選択項目を削除します。

*nEndChar*<br/>
終了位置を指定します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [EM_SETSEL](/windows/desktop/Controls/em-setsel) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEdit::GetSel](#getsel)します。

##  <a name="settabstops"></a>  CEdit::SetTabStops

複数行のエディット コントロールにタブ ストップを設定するには、この関数を呼び出します。

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>パラメーター

*cxEachStop*<br/>
タブ ストップがある、設定することを指定しますすべて*cxEachStop*ダイアログ単位。

*nTabStops*<br/>
含まれているタブ ストップの数を指定*rgTabStops*します。 この数は、1 より大きくなければなりません。

*rgTabStops*<br/>
ダイアログ単位で、タブを指定する符号なし整数の配列へのポインターを停止します。 ダイアログ単位は、水平方向または垂直方向の距離です。 1 つの水平ダイアログ単位は現在のダイアログ ベースの幅の単位の 4 分の 1 と等しくと 1 の垂直方向のダイアログ単位が現在のダイアログ ベースの高さの単位の 8 分の 1 と等しい。 ダイアログの基本単位は、高さと幅の現在のシステム フォントに基づいて計算されます。 `GetDialogBaseUnits` Windows 関数はピクセル単位で現在のダイアログ ボックスにベース ユニットの数を返します。

### <a name="return-value"></a>戻り値

タブが設定された場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

複数行のエディット コントロールにテキストをコピー、テキスト内の任意のタブ文字は最大で次のタブ ストップが生成される領域になります。

タブ ストップを 32 ダイアログ単位の既定のサイズを設定するには、このメンバー関数のパラメーターなしのバージョンを呼び出します。 タブ ストップを 32 以外のサイズを設定するとバージョンを呼び出す、 *cxEachStop*パラメーター。 サイズの配列にタブ ストップを設定するには、2 つのパラメーター バージョンを使用します。

このメンバー関数は、複数行のエディット コントロールでのみ処理されます。

`SetTabStops` 自動的に再描画されない編集ウィンドウ。 テキスト編集コントロールのタブ ストップを変更する場合は、呼び出す[エディット](cwnd-class.md#invalidaterect)編集ウィンドウを再描画します。

詳細については、次を参照してください。 [EM_SETTABSTOPS](/windows/desktop/Controls/em-settabstops)と[GetDialogBaseUnits](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CEditView::SetTabStops](ceditview-class.md#settabstops)します。

##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip

現在の編集コントロールに関連付けられているバルーン ヒントが表示されます。

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
|*pEditBalloonTip*|[in]ポインター、 [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip)バルーン ヒントを記述する構造体。|
|*lpszTitle*|[in]バルーン ヒントのタイトルを含む Unicode 文字列へのポインター。|
|*lpszText*|[in]バルーン ヒントのテキストを含む Unicode 文字列へのポインター。|
|*ttiIcon*|[in]**INT**バルーン ヒントに関連付けるアイコンの種類を指定します。 既定値は、TTI_NONE です。 詳細については、次を参照してください。、`ttiIcon`のメンバー、 [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip)構造体。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

この関数は送信、 [EM_SHOWBALLOONTIP](/windows/desktop/Controls/em-showballoontip)メッセージは、Windows SDK で説明します。 詳細については、次を参照してください。、 [Edit_ShowBalloonTip](/windows/desktop/api/commctrl/nf-commctrl-edit_showballoontip)マクロ。

### <a name="example"></a>例

次のコード例は、変数を定義`m_cedit`、つまり現在の編集コントロールにアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>例

次のコード例では、エディット コントロールのバルーン ヒントが表示されます。 [CEdit::ShowBalloonTip](#showballoontip)メソッドは、タイトルとバルーンのヒント テキストを指定します。

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

##  <a name="undo"></a>  CEdit::Undo

最後の編集コントロールの操作を元に戻すには、この関数を呼び出します。

```
BOOL Undo();
```

### <a name="return-value"></a>戻り値

単一行のエディット コントロールでは、戻り値は 0 以外では常にします。 複数行のエディット コントロールには、戻り値は元に戻す操作が成功した場合、0 以外の場合、元に戻す操作が失敗した場合は 0。

### <a name="remarks"></a>Remarks

元に戻す操作が元に戻すことができますもあります。 たとえば、最初の呼び出しで削除されたテキストを復元できます`Undo`します。 2 番目の呼び出しを使用してテキストを削除するには中間の編集操作がない限り、`Undo`します。

詳細については、次を参照してください。 [EM_UNDO](/windows/desktop/Controls/em-undo) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](cwnd-class.md)<br/>
[CButton クラス](cbutton-class.md)<br/>
[CComboBox クラス](ccombobox-class.md)<br/>
[CListBox クラス](clistbox-class.md)<br/>
[CScrollBar クラス](cscrollbar-class.md)<br/>
[CStatic クラス](cstatic-class.md)<br/>
[CDialog クラス](cdialog-class.md)
