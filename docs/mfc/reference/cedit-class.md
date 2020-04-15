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
ms.openlocfilehash: 3ca2fe4486ae0751f37d046ef28ed11e60e776ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373982"
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
|[エディット::CEdit](#cedit)|コントロール オブジェクト`CEdit`を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[編集::カンドゥンド](#canundo)|エディット コントロール操作を元に戻すことができるかどうかを決定します。|
|[エディット::シャアフロズポス](#charfrompos)|指定した位置に最も近い文字の行と文字のインデックスを取得します。|
|[エディット::クリア](#clear)|エディット コントロール内の現在の選択範囲 (存在する場合) を削除します (クリアします)。|
|[編集::コピー](#copy)|エディット コントロールの現在の選択範囲 (存在する場合) を、CF_TEXT形式でクリップボードにコピーします。|
|[編集::作成](#create)|Windows エディット コントロールを作成し、オブジェクト`CEdit`にアタッチします。|
|[エディット::カット](#cut)|エディット コントロール内の現在の選択範囲 (存在する場合) を削除 (カット) し、削除したテキストをCF_TEXT形式でクリップボードにコピーします。|
|[::空のUndoバッファ](#emptyundobuffer)|エディット コントロールの元に戻すフラグをリセット (クリア) します。|
|[エディット::FmtLines](#fmtlines)|複数行エディット コントロール内でソフト 改行文字を含めるかどうか設定します。|
|[エディット::ゲットキューバナー](#getcuebanner)|コントロールが空でフォーカスがない場合に、エディット コントロールにテキスト キューまたはヒントとして表示されるテキストを取得します。|
|[エディット::ゲットファーストビジブルライン](#getfirstvisibleline)|エディット コントロール内の一番上に表示される行を指定します。|
|[エディット::ゲットハンドル](#gethandle)|複数行エディット コントロールに現在割り当てられているメモリへのハンドルを取得します。|
|[編集::ゲットハイライト](#gethighlight)|現在のエディット コントロールで強調表示されているテキストの範囲内の開始文字と終了文字のインデックスを取得します。|
|[テキストを取得します。](#getlimittext)|このテキストに含めることができる最大量`CEdit`のテキストを取得します。|
|[エディット::ゲットライン](#getline)|エディット コントロールからテキスト行を取得します。|
|[エディット::ゲットラインカウント](#getlinecount)|複数行エディット コントロールの行数を取得します。|
|[編集::ゲットマージン](#getmargins)|この`CEdit`余白の左右の余白を取得します。|
|[編集::ゲット修正](#getmodify)|エディット コントロールの内容が変更されたかどうかを判断します。|
|[エディット::ゲットパスワードシャール](#getpasswordchar)|ユーザーがテキストを入力したときに、エディット コントロールに表示されるパスワード文字を取得します。|
|[エディット::ゲットレック](#getrect)|エディット コントロールの書式設定四角形を取得します。|
|[エディット::ゲットセル](#getsel)|エディット コントロール内の現在の選択範囲の先頭と最後の文字位置を取得します。|
|[編集::バルーンチップを非表示にする](#hideballoontip)|現在のエディット コントロールに関連付けられているバルーン ヒントを非表示にします。|
|[編集::リミットテキスト](#limittext)|ユーザーがエディット コントロールに入力できるテキストの長さを制限します。|
|[エディット::ラインフロルチャリング](#linefromchar)|指定した文字インデックスを含む行の行番号を取得します。|
|[編集::ラインインデックス](#lineindex)|複数行エディット コントロール内の行の文字インデックスを取得します。|
|[編集::ラインレングス](#linelength)|エディット コントロールの行の長さを取得します。|
|[::ラインスクロール](#linescroll)|複数行のエディット コントロールのテキストをスクロールします。|
|[エディット::Pアステ](#paste)|クリップボードのデータを現在のカーソル位置のエディット コントロールに挿入します。 クリップボードにCF_TEXT形式のデータが含まれている場合にのみ、データが挿入されます。|
|[エディット::PosFromChar](#posfromchar)|指定した文字インデックスの左上隅の座標を取得します。|
|[エディット::セルを交換](#replacesel)|エディット コントロール内の現在の選択範囲を指定したテキストに置き換えます。|
|[エディット::セットキューバナー](#setcuebanner)|コントロールが空でフォーカスがない場合に、エディット コントロールにテキスト キューまたはヒントとして表示されるテキストを設定します。|
|[編集::セットハンドル](#sethandle)|複数行エディット コントロールで使用されるローカル メモリへのハンドルを設定します。|
|[編集::セットハイライト](#sethighlight)|現在のエディット コントロールに表示されているテキストの範囲を強調表示します。|
|[テキストを編集します。](#setlimittext)|このテキストに含めることができる最大量`CEdit`のテキストを設定します。|
|[編集::セットマージン](#setmargins)|この`CEdit`余白の左右の余白を設定します。|
|[編集::セット修正](#setmodify)|エディット コントロールの変更フラグを設定またはクリアします。|
|[エディット::セットパスワード文字](#setpasswordchar)|ユーザーがテキストを入力したときに、エディット コントロールに表示されるパスワード文字を設定または削除します。|
|[編集::セットリードオンリック](#setreadonly)|エディット コントロールの読み取り専用の状態を設定します。|
|[エディット::セットレック](#setrect)|複数行エディット コントロールの書式設定四角形を設定し、コントロールを更新します。|
|[エディット::セットレクトNP](#setrectnp)|コントロール ウィンドウを再描画せずに、複数行エディット コントロールの書式設定四角形を設定します。|
|[エディット::セットセル](#setsel)|エディット コントロール内の文字の範囲を選択します。|
|[編集::セットタブストップ](#settabstops)|複数行のエディット コントロールでタブ位置を設定します。|
|[エディット::バルーンチップを表示](#showballoontip)|現在のエディット コントロールに関連付けられているバルーン ヒントが表示されます。|
|[編集::元に戻す](#undo)|最後のエディット コントロール操作を元に戻します。|

## <a name="remarks"></a>解説

エディット コントロールは、ユーザーがテキストを入力できる四角形の子ウィンドウです。

編集コントロールは、ダイアログ テンプレートから作成することも、コード内で直接作成することもできます。 どちらの場合も、まず`CEdit`コンストラクタを呼び出して`CEdit`オブジェクトを構築し、次に[Create](#create)メンバー関数を呼び出して Windows`CEdit`エディット コントロールを作成し、オブジェクトにアタッチします。

構築は、 から`CEdit`派生したクラスの 1 段階のプロセスです。 派生クラスのコンストラクターを記述し、コンストラクター`Create`内から呼び出します。

`CEdit`から重要な機能を`CWnd`継承します。 `CEdit`オブジェクトのテキストを設定および取得するには、`CWnd`メンバー関数[SetWindowText](cwnd-class.md#setwindowtext)および[GetWindowText](cwnd-class.md#getwindowtext)を使用します。 複数行コントロールのテキスト行は、'\r\n' 文字シーケンスで区切られます。 また、`CEdit`エディット コントロールが複数行の場合は、メンバー関数[GetLine](#getline) [、SetSel 、GetSel](#setsel)、および[ReplaceSel](#replacesel)を呼び出して、コントロールのテキストの一部を取得および設定します。 [GetSel](#getsel)

エディット コントロールから親に送信される Windows 通知メッセージ (通常は派生元のクラス`CDialog`) を処理する場合は、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。

各メッセージ マップ エントリは、次の形式をとります。

  **ON_**_通知_**(** _id_**,** _メンバFxn_ **)**

通知`id`を送信するエディット コントロールの子ウィンドウ ID を`memberFxn`指定し、通知を処理するために記述した親メンバー関数の名前を指定します。

親の関数プロトタイプは次のとおりです。

**afx_msg**ボイドメンバーFxn **( );**

次に、メッセージ マップエントリの候補と、それらが親に送信されるケースの説明を示します。

- ON_EN_CHANGE ユーザーが編集コントロール内のテキストを変更した可能性のある操作を実行しました。 EN_UPDATE通知メッセージとは異なり、この通知メッセージは、Windows が表示を更新した後に送信されます。

- ON_EN_ERRSPACE エディット コントロールは、特定の要求を満たすのに十分なメモリを割り当てることができません。

- ON_EN_HSCROLL ユーザーがエディット コントロールの水平スクロール バーをクリックします。 画面が更新される前に、親ウィンドウに通知されます。

- ON_EN_KILLFOCUS エディット コントロールが入力フォーカスを失います。

- ON_EN_MAXTEXT 現在の挿入がエディット コントロールに指定された文字数を超え、切り捨てられました。 また、エディット コントロールにES_AUTOHSCROLLスタイルが設定されておらず、挿入する文字数がエディット コントロールの幅を超えた場合にも送信されます。 また、エディット コントロールにES_AUTOVSCROLLスタイルが設定されておらず、テキストの挿入によって生じる行の総数がエディット コントロールの高さを超えた場合にも送信されます。

- ON_EN_SETFOCUS エディット コントロールが入力フォーカスを受け取ったときに送信されます。

- ON_EN_UPDATE エディット コントロールが変更されたテキストを表示しようとしています。 コントロールがテキストを書式設定した後、必要に応じてウィンドウサイズを変更できるようにテキストをスクリーン表示する前に送信されます。

- ON_EN_VSCROLL ユーザーがエディット コントロールの垂直スクロール バーをクリックします。 画面が更新される前に、親ウィンドウに通知されます。

ダイアログ ボックス内`CEdit`にオブジェクトを作成すると、ユーザー`CEdit`がダイアログ ボックスを閉じると、オブジェクトは自動的に破棄されます。

ダイアログ エディターを`CEdit`使用してダイアログ リソースからオブジェクトを作成すると、`CEdit`ユーザーがダイアログ ボックスを閉じると、オブジェクトは自動的に破棄されます。

ウィンドウ内にオブジェクト`CEdit`を作成する場合は、オブジェクトを破棄する必要もあります。 スタック上にオブジェクト`CEdit`を作成すると、オブジェクトは自動的に破棄されます。 **新しい**関数を`CEdit`使用してヒープ上にオブジェクトを作成する場合は、ユーザーが Windows エディット コントロールを終了したときに破棄するために、オブジェクトの**delete**を呼び出す必要があります。 オブジェクトにメモリを`CEdit`割り当てる場合は、`CEdit`デストラクタをオーバーライドして割り当てを破棄します。

編集コントロールの特定のスタイル (ES_READONLYなど) を変更するには[、ModifyStyle](cwnd-class.md#modifystyle)を使用する代わりに、コントロールに特定のメッセージを送信する必要があります。 Windows SDK[の「コントロール スタイルの編集](/windows/win32/Controls/edit-control-styles)」を参照してください。

`CEdit`の詳細については、「[コントロール](../../mfc/controls-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="ceditcanundo"></a><a name="canundo"></a>編集::カンドゥンド

最後の編集操作を元に戻すことができるかどうかを調べます。

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>戻り値

`Undo`最後の編集操作をメンバー関数の呼び出しで元に戻すことができる場合は 0 以外。取り消すことができない場合は 0。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[EM_CANUNDO](/windows/win32/Controls/em-canundo)を参照してください。

### <a name="example"></a>例

  [「CEdit::元に戻す](#undo)」の例を参照してください。

## <a name="ceditcedit"></a><a name="cedit"></a>エディット::CEdit

`CEdit` オブジェクトを構築します。

```
CEdit();
```

### <a name="remarks"></a>解説

[作成](#create)を使用して、Windows エディット コントロールを構築します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

## <a name="ceditcharfrompos"></a><a name="charfrompos"></a>エディット::シャアフロズポス

この`CEdit`コントロール内の指定した位置に最も近い文字の 0 から始まる行と文字インデックスを取得します。

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
この`CEdit`オブジェクトのクライアント領域内のポイントの座標。

### <a name="return-value"></a>戻り値

下位の WORD の文字インデックス、および高次の WORD の行インデックス。

### <a name="remarks"></a>解説

> [!NOTE]
> このメンバー関数は、Windows 95 および Windows NT 4.0 以降で使用できます。

詳細については、Windows SDK の[EM_CHARFROMPOS](/windows/win32/Controls/em-charfrompos)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

## <a name="ceditclear"></a><a name="clear"></a>エディット::クリア

エディット コントロールの現在の選択項目 (存在する場合) を削除 (クリア) します。

```
void Clear();
```

### <a name="remarks"></a>解説

によって実行された`Clear`削除は[、元に戻す](#undo)メンバー関数を呼び出すことによって元に戻すことができます。

現在の選択範囲を削除し、削除した内容をクリップボードに配置するには[、Cut](#cut)メンバー関数を呼び出します。

詳細については、Windows SDK の[WM_CLEAR](/windows/win32/dataxchg/wm-clear)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

## <a name="ceditcopy"></a><a name="copy"></a>編集::コピー

エディット コントロールの現在の選択範囲 (存在する場合) をクリップボードにCF_TEXT形式で貼り付けます。

```
void Copy();
```

### <a name="remarks"></a>解説

詳細については、「Windows SDK の[WM_COPY」](/windows/win32/dataxchg/wm-copy)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

## <a name="ceditcreate"></a><a name="create"></a>編集::作成

Windows エディット コントロールを作成し、オブジェクト`CEdit`にアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
エディット コントロールのスタイルを指定します。 [編集スタイル](styles-used-by-mfc.md#edit-styles)の任意の組み合わせをコントロールに適用します。

*Rect*<br/>
エディット コントロールのサイズと位置を指定します。 オブジェクトまたは`RECT`構造体`CRect`を指定できます。

*pParentWnd*<br/>
エディット コントロールの親ウィンドウ (通常は`CDialog`a ) を指定します。 NULL にすることはできません。

*nID*<br/>
エディット コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

オブジェクトは`CEdit`2 つの手順で作成します。 まず、コンストラクタを`CEdit`呼び出し`Create`、次にを`CEdit`呼び出します。

Windows`Create`が実行されると[、WM_NCCREATE](/windows/win32/winmsg/wm-nccreate)、 [WM_NCCALCSIZE](/windows/win32/winmsg/wm-nccalcsize)、 [WM_CREATE](/windows/win32/winmsg/wm-create)、および[WM_GETMINMAXINFO](/windows/win32/winmsg/wm-getminmaxinfo)メッセージがエディット コントロールに送信されます。

これらのメッセージは、`CWnd`既定では、基本クラスの[OnNcCreate、OnNcCalcSize、OnCreate](cwnd-class.md#onnccreate)、および[OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo)メンバー関数によって処理されます。 [OnNcCalcSize](cwnd-class.md#onnccalcsize) [OnCreate](cwnd-class.md#oncreate) 既定のメッセージ処理を拡張するには、 から`CEdit`クラスを派生し、新しいクラスにメッセージ マップを追加し、上記のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`(たとえば、新しいクラスに必要な初期化を実行する場合)。

エディット コントロールに次の[ウィンドウ スタイル](styles-used-by-mfc.md#window-styles)を適用します。

- WS_CHILD常に

- WS_VISIBLE通常

- WS_DISABLEDまれ

- WS_GROUP グループ コントロールへ

- WS_TABSTOP タブ順序にエディット コントロールを含めるには

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

## <a name="ceditcut"></a><a name="cut"></a>エディット::カット

エディット コントロールの現在の選択項目 (存在する場合) を削除 (切り取る) し、削除されたテキストをCF_TEXT形式でクリップボードにコピーします。

```
void Cut();
```

### <a name="remarks"></a>解説

によって実行された`Cut`削除は[、元に戻す](#undo)メンバー関数を呼び出すことによって元に戻すことができます。

削除したテキストをクリップボードに入れずに現在の選択を削除するには[、Clear](#clear)メンバー関数を呼び出します。

詳細については、Windows SDK の[WM_CUT](/windows/win32/dataxchg/wm-cut)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

## <a name="ceditemptyundobuffer"></a><a name="emptyundobuffer"></a>::空のUndoバッファ

エディット コントロールの元に戻すフラグをリセット (クリア) します。

```
void EmptyUndoBuffer();
```

### <a name="remarks"></a>解説

エディット コントロールは、直前の操作を元に戻すことができなくなります。 エディット コントロール内の操作を元に戻すことができる場合は、必ず undo フラグが設定されます。

戻すフラグは[、SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)または[SetHandle](#sethandle)`CWnd`メンバー関数が呼び出されるたびに自動的にクリアされます。

詳細については、「Windows SDK の[EM_EMPTYUNDOBUFFER」](/windows/win32/Controls/em-emptyundobuffer)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

## <a name="ceditfmtlines"></a><a name="fmtlines"></a>エディット::FmtLines

複数行エディット コントロール内でソフト 改行文字の挿入を設定します。

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>パラメーター

*ブアドエオール*<br/>
ソフト改行文字を挿入するかどうかを指定します。 TRUE の値は文字を挿入します。値が FALSE の場合は、それらを削除します。

### <a name="return-value"></a>戻り値

書式が発生した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ソフト改行は、2 つの改行と、ワード ラップのために破られた行の末尾に挿入される改行で構成されます。 ハード改行は、1 つのキャリッジ リターンと 1 つの改行で構成されます。 ハード改行で終わる行は、 によって影響を`FmtLines`受けません。

Windows は、オブジェクトが`CEdit`複数行のエディット コントロールである場合にのみ応答します。

`FmtLines`[GetHandle](#gethandle)によって返されるバッファーと[、WM_GETTEXT](/windows/win32/winmsg/wm-gettext)によって返されるテキストにのみ影響します。 エディット コントロール内のテキストの表示には影響しません。

詳細については、「Windows SDK の[EM_FMTLINES」](/windows/win32/Controls/em-fmtlines)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

## <a name="ceditgetcuebanner"></a><a name="getcuebanner"></a>エディット::ゲットキューバナー

コントロールが空の場合に、エディット コントロールにテキスト キューまたはヒントとして表示されるテキストを取得します。

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[アウト]キュー テキストを含む文字列へのポインター。

*cchText*<br/>
[in]受信できる文字数。 この数値には、終端の NULL 文字が含まれます。

### <a name="return-value"></a>戻り値

最初のオーバーロードでは、メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

2 番目のオーバーロードでは、メソッドが成功した場合にキュー テキストを格納する[CString。](../../atl-mfc-shared/using-cstring.md)それ以外の場合は、空の文字列 ("") を返します。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[EM_GETCUEBANNER](/windows/win32/Controls/em-getcuebanner)メッセージを送信します。 詳細については[、Edit_GetCueBannerText](/windows/win32/api/commctrl/nf-commctrl-edit_getcuebannertext)マクロを参照してください。

## <a name="ceditgetfirstvisibleline"></a><a name="getfirstvisibleline"></a>エディット::ゲットファーストビジブルライン

エディット コントロール内の一番上の可視行を調べます。

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>戻り値

表示される一番上の行の 0 から始まるインデックス。 単一行エディット コントロールの場合、戻り値は 0 です。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[EM_GETFIRSTVISIBLELINE](/windows/win32/Controls/em-getfirstvisibleline)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

## <a name="ceditgethandle"></a><a name="gethandle"></a>エディット::ゲットハンドル

複数行エディット コントロールに現在割り当てられているメモリへのハンドルを取得します。

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>戻り値

エディット コントロールの内容を保持しているバッファを識別するローカル メモリ ハンドル。 単一行のエディット コントロールにメッセージを送信するなどのエラーが発生した場合、戻り値は 0 です。

### <a name="remarks"></a>解説

ハンドルはローカル メモリ ハンドルであり、ローカル メモリ ハンドルをパラメータとして受け取る**任意のローカル**Windows メモリ関数で使用できます。

`GetHandle`は、複数行のエディット コントロールによってのみ処理されます。

ダイアログ`GetHandle`ボックスがDS_LOCALEDITスタイル フラグを設定して作成された場合にのみ、ダイアログ ボックスで複数行エディット コントロールを呼び出します。 DS_LOCALEDITスタイルが設定されていない場合でも、0 以外の戻り値は取得されますが、戻り値は使用できません。

> [!NOTE]
> `GetHandle`Windows 95/98 では動作しません。 Windows 95/98 で呼び出`GetHandle`すと、NULL が返されます。 `GetHandle`Windows NT バージョン 3.51 以降で説明されているように動作します。

詳細については、「Windows SDK の[EM_GETHANDLE」](/windows/win32/Controls/em-gethandle)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

## <a name="ceditgethighlight"></a><a name="gethighlight"></a>編集::ゲットハイライト

現在のエディット コントロールで強調表示されているテキスト範囲の最初と最後の文字のインデックスを取得します。

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ピッチスタート*|[アウト]強調表示されたテキスト範囲の最初の文字の 0 から始まるインデックス。|
|*ピクエンド*|[アウト]強調表示されたテキスト範囲の最後の文字の 0 から始まるインデックス。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[EM_GETHILITE](/windows/win32/Controls/em-gethilite)メッセージを送信します。 両方`SetHighlight`とも`GetHighlight`、現在 UNICODE ビルドでのみ有効になっています。

## <a name="ceditgetlimittext"></a><a name="getlimittext"></a>テキストを取得します。

この`CEdit`オブジェクトのテキスト制限を取得します。

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>戻り値

この`CEdit`オブジェクトの現在のテキスト制限 (TCHARs)。

### <a name="remarks"></a>解説

テキスト制限は、編集コントロールが受け入れることのできるテキストの最大量 (TCHAR) です。

> [!NOTE]
> このメンバー関数は、Windows 95 および Windows NT 4.0 以降で使用できます。

詳細については、Windows SDK の[EM_GETLIMITTEXT](/windows/win32/Controls/em-getlimittext)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

## <a name="ceditgetline"></a><a name="getline"></a>エディット::ゲットライン

エディット コントロールからテキスト行を取得し *、lpszBuffer*に配置します。

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
複数行エディット コントロールから取得する行番号を指定します。 行番号は 0 から始まります。値 0 は最初の行を指定します。 このパラメーターは、単一行のエディット コントロールでは無視されます。

*バッファ*<br/>
行のコピーを受け取るバッファーへのポイント。 バッファーの最初のワードは、バッファーにコピーできる TCHARs の最大数を指定する必要があります。

*長さ*<br/>
バッファーにコピーできる TCHAR 文字の最大数を指定します。 `GetLine`この値は、Windows への呼び出しを行う前に *、lpszBuffer*の最初の単語に置きます。

### <a name="return-value"></a>戻り値

実際にコピーされた文字数。 *nIndex*で指定された行番号がエディット コントロールの行数より大きい場合、戻り値は 0 になります。

### <a name="remarks"></a>解説

コピーされた行に、ヌル終了文字が含まれていません。

詳細については、「Windows SDK の[EM_GETLINE」](/windows/win32/Controls/em-getline)を参照してください。

### <a name="example"></a>例

  次の例を参照[してください](#getlinecount)。

## <a name="ceditgetlinecount"></a><a name="getlinecount"></a>エディット::ゲットラインカウント

複数行エディット コントロールの行数を取得します。

```
int GetLineCount() const;
```

### <a name="return-value"></a>戻り値

複数行エディット コントロールの行数を含む整数。 エディット コントロールにテキストが入力されていない場合、戻り値は 1 です。

### <a name="remarks"></a>解説

`GetLineCount`は複数行のエディット コントロールによってのみ処理されます。

詳細については、「Windows SDK の[EM_GETLINECOUNT」](/windows/win32/Controls/em-getlinecount)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

## <a name="ceditgetmargins"></a><a name="getmargins"></a>編集::ゲットマージン

このエディット コントロールの左右の余白を取得します。

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>戻り値

下位の WORD の左余白の幅、および高次 WORD の右余白の幅。

### <a name="remarks"></a>解説

余白はピクセル単位で測定されます。

> [!NOTE]
> このメンバー関数は、Windows 95 および Windows NT 4.0 以降で使用できます。

詳細については、Windows SDK の[EM_GETMARGINS](/windows/win32/Controls/em-getmargins)を参照してください。

### <a name="example"></a>例

  [次](ceditview-class.md#geteditctrl)の例を参照してください。

## <a name="ceditgetmodify"></a><a name="getmodify"></a>編集::ゲット修正

エディット コントロールの内容が変更されたかどうかを調べます。

```
BOOL GetModify() const;
```

### <a name="return-value"></a>戻り値

エディット コントロールの内容が変更されている場合は 0 以外の値を返します。0 を変更しない場合。

### <a name="remarks"></a>解説

Windows では、エディット コントロールの内容が変更されたかどうかを示す内部フラグが保持されます。 このフラグは、エディット コントロールが最初に作成されたときにクリアされ[、SetModify](#setmodify)メンバー関数を呼び出すことによってもクリアされます。

詳細については、「Windows SDK の[EM_GETMODIFY」](/windows/win32/Controls/em-getmodify)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

## <a name="ceditgetpasswordchar"></a><a name="getpasswordchar"></a>エディット::ゲットパスワードシャール

ユーザーがテキストを入力したときに編集コントロールに表示されるパスワード文字を取得します。

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>戻り値

ユーザーが入力した文字の代わりに表示する文字を指定します。 パスワード文字が存在しない場合、戻り値は NULL です。

### <a name="remarks"></a>解説

ES_PASSWORD スタイルを使用してエディット コントロールを作成すると、そのコントロールをサポートする DLL によって既定のパスワード文字が決まります。 マニフェストまたは[InitCommonControlsEx](/windows/win32/api/commctrl/nf-commctrl-initcommoncontrolsex)メソッドは、エディット コントロールをサポートする DLL を決定します。 user32.dll が編集コントロールをサポートしている場合、デフォルトのパスワード文字はアスタリスク ('*', U+002A) です。 comctl32.dll バージョン 6 が編集コントロールをサポートしている場合、デフォルトの文字は黒丸 ('●',U+25CF) です。 共通コントロールをサポートする DLL とバージョンの詳細については、「[シェルとコモン コントロールのバージョン](/previous-versions/windows/desktop/legacy/bb776779\(v=vs.85\))」を参照してください。

このメソッドは、Windows SDK で説明されている[EM_GETPASSWORDCHAR](/windows/win32/Controls/em-getpasswordchar)メッセージを送信します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

## <a name="ceditgetrect"></a><a name="getrect"></a>エディット::ゲットレック

エディット コントロールの書式設定四角形を取得します。

```
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
書式設定された四`RECT`角形を受け取る構造体へのポインター。

### <a name="remarks"></a>解説

書式設定の四角形は、エディット コントロール ウィンドウのサイズに依存しないテキストの制限四角形です。

複数行エディット コントロールの書式設定四角形は[、SetRect](#setrect)および[SetRectNP](#setrectnp)メンバー関数によって変更できます。

詳細については、Windows SDK の[EM_GETRECT](/windows/win32/Controls/em-getrect)を参照してください。

### <a name="example"></a>例

  [次](#limittext)の例を参照してください。

## <a name="ceditgetsel"></a><a name="getsel"></a>エディット::ゲットセル

エディット コントロール内の現在の選択範囲 (存在する場合) の開始位置と終了文字位置を、戻り値またはパラメーターを使用して取得します。

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>パラメーター

*nStartChar*<br/>
現在の選択範囲の先頭文字の位置を受け取る整数への参照。

*エンドチャー*<br/>
現在の選択範囲の末尾を越えて、最初に選択されていない文字の位置を受け取る整数への参照。

### <a name="return-value"></a>戻り値

DWORD を返すバージョンは、下位の単語の開始位置と上位の単語の選択範囲の末尾の後の最初の非選択文字の位置を含む値を返します。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[EM_GETSEL](/windows/win32/Controls/em-getsel)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

## <a name="cedithideballoontip"></a><a name="hideballoontip"></a>編集::バルーンチップを非表示にする

現在のエディット コントロールに関連付けられているバルーン ヒントを非表示にします。

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数は、Windows SDK に記載されている[EM_HIDEBALLOONTIP](/windows/win32/Controls/em-hideballoontip)メッセージを送信します。

## <a name="ceditlimittext"></a><a name="limittext"></a>編集::リミットテキスト

ユーザーがエディット コントロールに入力できるテキストの長さを制限します。

```
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>パラメーター

*nChars*<br/>
ユーザーが入力できるテキストの長さを TCHARs で指定します。 このパラメーターが 0 の場合、テキストの長さは UINT_MAX バイトに設定されます。 これは既定の動作です。

### <a name="remarks"></a>解説

テキスト制限を変更すると、ユーザーが入力できるテキストのみが制限されます。 エディット コントロールに既に含まれるテキストには影響しません。 [SetWindowText](cwnd-class.md#setwindowtext) `CWnd` アプリケーションが、この関数`SetWindowText`を使用して、 の`LimitText`呼び出しで指定されているテキストよりも多くのテキストをエディット コントロールに配置する場合、ユーザーはエディット コントロール内の任意のテキストを削除できます。 ただし、テキスト制限を使用すると、現在の選択項目を削除するとテキストがテキストの制限を下回らない限り、既存のテキストを新しいテキストに置き換えることはできません。

> [!NOTE]
> Win32 (Windows NT および Windows 95/98) では、この関数を[置](#setlimittext)き換えます。

詳細については、Windows SDK の[EM_LIMITTEXT](/windows/win32/Controls/em-limittext)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

## <a name="ceditlinefromchar"></a><a name="linefromchar"></a>エディット::ラインフロルチャリング

指定した文字インデックスを含む行の行番号を取得します。

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
エディット コントロールのテキスト内の目的の文字のインデックス値を 0 から始まる値で指定します。 *nIndex*が -1 の場合、現在の行、つまりキャレットを含む行を指定します。

### <a name="return-value"></a>戻り値

*nIndex*で指定された文字インデックスを含む行の 0 から始まる行番号。 *nIndex が*-1 の場合、選択範囲の最初の文字を含む行の番号が返されます。 選択項目がない場合は、現在の行番号が返されます。

### <a name="remarks"></a>解説

文字インデックスは、エディット コントロールの先頭からの文字数です。

このメンバー関数は、複数行のエディット コントロールでのみ使用されます。

詳細については、「Windows SDK の[EM_LINEFROMCHAR」](/windows/win32/Controls/em-linefromchar)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

## <a name="ceditlineindex"></a><a name="lineindex"></a>編集::ラインインデックス

複数行エディット コントロール内の行の文字インデックスを取得します。

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>パラメーター

*nライン*<br/>
エディット コントロールのテキスト内の目的の行のインデックス値を含むか、-1 を含みます。 *nLine*が -1 の場合、現在の行、つまりキャレットを含む行を指定します。

### <a name="return-value"></a>戻り値

*nLine*または -1 で指定された行の文字インデックス (指定した行番号がエディット コントロールの行数より大きい場合)。

### <a name="remarks"></a>解説

文字インデックスは、エディット コントロールの先頭から指定した行までの文字数です。

このメンバー関数は、複数行のエディット コントロールによってのみ処理されます。

詳細については、Windows SDK の[EM_LINEINDEX](/windows/win32/controls/em-lineindex)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

## <a name="ceditlinelength"></a><a name="linelength"></a>編集::ラインレングス

エディット コントロールの行の長さを取得します。

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>パラメーター

*nライン*<br/>
長さを取得する行の文字の 0 から始まるインデックス。 既定値は -1 です。

### <a name="return-value"></a>戻り値

単一行エディット コントロールの場合、戻り値は編集コントロール内のテキストの長さ (TCHAR) です。

複数行エディット コントロールの場合、戻り値は*nLine*パラメーターで指定された行の TCHARs 単位の長さになります。 ANSI テキストの場合、長さは行のバイト数です。Unicode テキストの場合、長さは行内の文字数です。 長さには、行の末尾にキャリッジ リターン文字は含まれません。

*nLine*パラメーターがコントロール内の文字数を超える場合、戻り値は 0 になります。

*nLine*パラメーターが -1 の場合、戻り値は選択した文字を含む行内の未選択の文字の数です。 たとえば、選択範囲が 1 行の 4 番目の文字から次の行の末尾から 8 番目の文字まで続く場合、戻り値は 10 になります。 つまり、最初の行に 3 文字、次の行に 7 文字です。

TCHAR 型の詳細については[、Windows データ型](/windows/win32/WinProg/windows-data-types)の表の TCHAR 行を参照してください。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[EM_LINELENGTH](/windows/win32/Controls/em-linelength)メッセージでサポートされています。

### <a name="example"></a>例

  [次](#lineindex)の例を参照してください。

## <a name="ceditlinescroll"></a><a name="linescroll"></a>::ラインスクロール

複数行エディット コントロールのテキストをスクロールします。

```
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>パラメーター

*nライン*<br/>
垂直方向にスクロールする行数を指定します。

*nChars*<br/>
水平方向にスクロールする文字の位置の数を指定します。 エディット コントロールにES_RIGHTまたはES_CENTERスタイルが設定されている場合、この値は無視されます。

### <a name="remarks"></a>解説

このメンバー関数は、複数行のエディット コントロールによってのみ処理されます。

エディット コントロールの最後の行のテキストを縦方向にスクロールしません。 現在の行に*nLines*で指定された行数を加えた値がエディット コントロールの行の合計数を超えた場合、エディット コントロールの最後の行がエディット コントロール ウィンドウの先頭までスクロールされるように値が調整されます。

`LineScroll`を使用して、行の最後の文字を横方向にスクロールできます。

詳細については、Windows SDK の[EM_LINESCROLL](/windows/win32/Controls/em-linescroll)を参照してください。

### <a name="example"></a>例

  [次](#getfirstvisibleline)の例を参照してください。

## <a name="ceditpaste"></a><a name="paste"></a>エディット::Pアステ

クリップボード`CEdit`のデータをカーソル位置に挿入します。

```
void Paste();
```

### <a name="remarks"></a>解説

クリップボードにCF_TEXT形式のデータが含まれている場合にのみ、データが挿入されます。

詳細については、Windows SDK の[WM_PASTE](/windows/win32/dataxchg/wm-paste)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

## <a name="ceditposfromchar"></a><a name="posfromchar"></a>エディット::PosFromChar

この`CEdit`オブジェクト内の特定の文字の位置 (左上隅) を取得します。

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>パラメーター

*Nchar*<br/>
指定した文字の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

*nChar*で指定された文字の左上隅の座標。

### <a name="remarks"></a>解説

文字は、0 から始まるインデックス値を指定して指定します。 *nChar*がこの`CEdit`オブジェクトの最後の文字のインデックスより大きい場合、戻り値はこの`CEdit`オブジェクトの最後の文字を過ぎた文字位置の座標を指定します。

> [!NOTE]
> このメンバー関数は、Windows 95 および Windows NT 4.0 以降で使用できます。

詳細については、Windows SDK の[EM_POSFROMCHAR](/windows/win32/Controls/em-posfromchar)を参照してください。

### <a name="example"></a>例

  [「CEdit::ラインフロルチャー](#linefromchar)」の例を参照してください。

## <a name="ceditreplacesel"></a><a name="replacesel"></a>エディット::セルを交換

編集コントロール内の現在の選択範囲を *、lpszNewText*で指定されたテキストに置き換えます。

```
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>パラメーター

*テキスト*<br/>
置換テキストを含む null で終わる文字列へのポイント。

*b元に戻す*<br/>
この関数を元に戻すことができるように指定するには、このパラメータの値を TRUE に設定します。 既定値は FALSE です。

### <a name="remarks"></a>解説

エディット コントロール内のテキストの一部だけを置換します。 すべてのテキストを置き換える場合は[、CWnd::SetWindowText](cwnd-class.md#setwindowtext)メンバー関数を使用します。

現在の選択がない場合、置換テキストは現在のカーソル位置に挿入されます。

詳細については、Windows SDK の[EM_REPLACESEL](/windows/win32/Controls/em-replacesel)を参照してください。

### <a name="example"></a>例

  [次](#lineindex)の例を参照してください。

## <a name="ceditsetcuebanner"></a><a name="setcuebanner"></a>エディット::セットキューバナー

コントロールが空の場合に、エディット コントロールにテキスト キューまたはヒントとして表示されるテキストを設定します。

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
[in]エディット コントロールに表示するキューを含む文字列へのポインター。

*フォーカスを合わせる*<br/>
[in]FALSE の場合、ユーザーがエディット コントロールをクリックしてフォーカスを与えたときに、キュー バナーは描画されません。

TRUE の場合、コントロールにフォーカスがある場合でも、キュー バナーが描画されます。 ユーザーがコントロールの入力を開始すると、キュー バナーが消えます。

既定値は FALSE です。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[EM_SETCUEBANNER](/windows/win32/Controls/em-setcuebanner)メッセージを送信します。 詳細については[、Edit_SetCueBannerTextFocused](/windows/win32/api/commctrl/nf-commctrl-edit_setcuebannertextfocused)マクロを参照してください。

### <a name="example"></a>例

次の例は、[メソッド](#setcuebanner)を示しています。

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

## <a name="ceditsethandle"></a><a name="sethandle"></a>編集::セットハンドル

複数行エディット コントロールで使用されるローカル メモリへのハンドルを設定します。

```
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>パラメーター

*バッファ*<br/>
ローカル メモリへのハンドルを格納します。 このハンドルは、LMEM_MOVEABLE フラグを使用して[、以前に LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc) Windows 関数を呼び出して作成されている必要があります。 メモリには、null で終わる文字列が含まれているものと見なされます。 この場合、割り当てられたメモリの最初のバイトを 0 に設定する必要があります。

### <a name="remarks"></a>解説

エディット コントロールは、このバッファーを使用して、自身のバッファーを割り当てるのではなく、現在表示されているテキストを格納します。

このメンバー関数は、複数行のエディット コントロールによってのみ処理されます。

アプリケーションは、新しいメモリ ハンドルを設定する前に[、GetHandle](#gethandle)メンバー関数を使用して、現在のメモリ バッファーへのハンドルを取得`LocalFree`し、Windows 関数を使用してそのメモリを解放する必要があります。

`SetHandle`元に戻すバッファー [(CanUndo](#canundo)メンバー関数は 0 を返します) をクリアし、内部変更フラグ[(GetModify](#getmodify)メンバー関数は 0 を返します)。 エディット コントロール ウィンドウが再描画されます。

このメンバー関数は、ダイアログ ボックスの複数行エディット コントロールで使用できるのは、DS_LOCALEDIT スタイル フラグが設定されたダイアログ ボックスを作成した場合だけです。

> [!NOTE]
> `GetHandle`Windows 95/98 では動作しません。 Windows 95/98 で呼び出`GetHandle`すと、NULL が返されます。 `GetHandle`Windows NT バージョン 3.51 以降で説明されているように動作します。

詳細については、Windows SDK[のEM_SETHANDLE](/windows/win32/Controls/em-sethandle)、[ローカルオロック](/windows/win32/api/winbase/nf-winbase-localalloc)、[およびローカルフリー](/windows/win32/api/winbase/nf-winbase-localfree)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

## <a name="ceditsethighlight"></a><a name="sethighlight"></a>編集::セットハイライト

現在のエディット コントロールに表示されているテキストの範囲を強調表示します。

```
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*イッチスタート*|[in]強調表示するテキスト範囲の最初の文字の 0 から始まるインデックス。|
|*イクエンド*|[in]強調表示するテキスト範囲の最後の文字の 0 から始まるインデックス。|

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[EM_SETHILITE](/windows/win32/Controls/em-sethilite)メッセージを送信します。  このメソッドは、Windows SDK で説明されている[EM_SETHILITE](/windows/win32/Controls/em-sethilite)メッセージを送信します。 両方`SetHighlight`とも`GetHighlight`、UNICODE ビルドでのみ有効です。

## <a name="ceditsetlimittext"></a><a name="setlimittext"></a>テキストを編集します。

この`CEdit`オブジェクトのテキスト制限を設定します。

```
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>パラメーター

*nMax*<br/>
新しいテキストの制限 (文字数)。

### <a name="remarks"></a>解説

テキスト制限は、エディット コントロールが受け入れることのできるテキストの最大量です。

テキスト制限を変更すると、ユーザーが入力できるテキストのみが制限されます。 エディット コントロールに既に含まれるテキストには影響しません。 [SetWindowText](cwnd-class.md#setwindowtext) `CWnd` アプリケーションが、この関数`SetWindowText`を使用して、 の`LimitText`呼び出しで指定されているテキストよりも多くのテキストをエディット コントロールに配置する場合、ユーザーはエディット コントロール内の任意のテキストを削除できます。 ただし、テキスト制限を使用すると、現在の選択項目を削除するとテキストがテキストの制限を下回らない限り、既存のテキストを新しいテキストに置き換えることはできません。

この関数は、Win32[の LimitText](#limittext)を置き換えます。

詳細については、Windows SDK の[EM_SETLIMITTEXT](/windows/win32/Controls/em-setlimittext)を参照してください。

### <a name="example"></a>例

  [次](ceditview-class.md#geteditctrl)の例を参照してください。

## <a name="ceditsetmargins"></a><a name="setmargins"></a>編集::セットマージン

このエディット コントロールの左右の余白を設定します。

```
void SetMargins(
    UINT nLeft,
    UINT nRight);
```

### <a name="parameters"></a>パラメーター

*n左*<br/>
新しい左余白の幅 (ピクセル単位)。

*n右*<br/>
新しい右余白の幅 (ピクセル単位)。

### <a name="remarks"></a>解説

> [!NOTE]
> このメンバー関数は、Windows 95 および Windows NT 4.0 以降で使用できます。

詳細については、Windows SDK の[EM_SETMARGINS](/windows/win32/Controls/em-setmargins)を参照してください。

### <a name="example"></a>例

  [次](ceditview-class.md#geteditctrl)の例を参照してください。

## <a name="ceditsetmodify"></a><a name="setmodify"></a>編集::セット修正

エディット コントロールの変更フラグを設定またはクリアします。

```
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>パラメーター

*bModified*<br/>
TRUE の値は、テキストが変更されたことを示し、FALSE の値は、それが変更されていないことを示します。 デフォルトでは、変更されたフラグが設定されます。

### <a name="remarks"></a>解説

変更されたフラグは、エディット コントロール内のテキストが変更されたかどうかを示します。 ユーザーがテキストを変更するたびに自動的に設定されます。 その値は[、GetModify](#getmodify)メンバー関数を使用して取得できます。

詳細については、「Windows SDK の[EM_SETMODIFY」](/windows/win32/Controls/em-setmodify)を参照してください。

### <a name="example"></a>例

  [CEdit::GetModify](#getmodify)の例を参照してください。

## <a name="ceditsetpasswordchar"></a><a name="setpasswordchar"></a>エディット::セットパスワード文字

ユーザーがテキストを入力するときに、エディット コントロールに表示されるパスワード文字を設定または削除します。

```
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>パラメーター

*Ch*<br/>
ユーザーが入力した文字の代わりに表示する文字を指定します。 *ch が*0 の場合、ユーザーが入力した実際の文字が表示されます。

### <a name="remarks"></a>解説

パスワード文字を設定すると、ユーザーが入力した文字ごとにその文字が表示されます。

このメンバー関数は、複数行のエディット コントロールには影響しません。

メンバー関数`SetPasswordChar`が呼び出されると`CEdit`、 *ch*で指定された文字を使用して、表示されているすべての文字が再描画されます。

[ES_PASSWORD](styles-used-by-mfc.md#edit-styles)スタイルでエディット コントロールを作成する場合、デフォルトのパスワード文字はアスタリスク ( <strong>\*</strong>) に設定されます。 ch を 0`SetPasswordChar`に設定*ch*して呼び出された場合、このスタイルは削除されます。

詳細については、Windows SDK の[EM_SETPASSWORDCHAR](/windows/win32/Controls/em-setpasswordchar)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

## <a name="ceditsetreadonly"></a><a name="setreadonly"></a>編集::セットリードオンリック

エディット コントロールの読み取り専用状態を設定します。

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>パラメーター

*読み取り専用*<br/>
エディット コントロールの読み取り専用状態を設定するか削除するかを指定します。 TRUE の値は、状態を読み取り専用に設定します。FALSE の値は、読み取り/書き込み状態を設定します。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外、エラーが発生した場合は 0 以外。

### <a name="remarks"></a>解説

現在の設定は[、CWnd::GetStyle](cwnd-class.md#getstyle)の戻り値で[ES_READONLY](styles-used-by-mfc.md#edit-styles)フラグをテストすることによって見つけることができます。

詳細については、Windows SDK の[EM_SETREADONLY](/windows/win32/Controls/em-setreadonly)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

## <a name="ceditsetrect"></a><a name="setrect"></a>エディット::セットレック

指定した座標を使用して四角形のサイズを設定します。

```
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
書式設定された四`RECT`角形の`CRect`新しい寸法を指定する構造体またはオブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバーは、複数行のエディット コントロールによってのみ処理されます。

複数`SetRect`行エディット コントロールの書式設定四角形を設定するために使用します。 書式設定の四角形は、エディット コントロール ウィンドウのサイズに依存しないテキストの制限四角形です。 エディット コントロールが最初に作成されるとき、書式設定の四角形はエディット コントロール ウィンドウのクライアント領域と同じです。 アプリケーションは、`SetRect`メンバー関数を使用して、書式設定用の四角形をエディット コントロール ウィンドウよりも大きくまたは小さくすることができます。

エディット コントロールにスクロール バーがない場合、書式設定された四角形がウィンドウより大きくなると、テキストは折り返されずにクリップされます。 エディット コントロールに枠線が含まれている場合、書式設定用の四角形は枠線のサイズに縮小されます。 メンバー関数によって返される四角形を`GetRect`調整する場合は、四角形を に渡す前に境界線のサイズ`SetRect`を削除する必要があります。

呼`SetRect`び出されると、エディット コントロールのテキストも再フォーマットされ、再表示されます。

詳細については、Windows SDK の[EM_SETRECT](/windows/win32/Controls/em-setrect)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

## <a name="ceditsetrectnp"></a><a name="setrectnp"></a>エディット::セットレクトNP

複数行エディット コントロールの書式設定四角形を設定します。

```
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
四角形の`RECT`新しい`CRect`寸法を指定する構造体またはオブジェクトへのポインター。

### <a name="remarks"></a>解説

書式設定の四角形は、エディット コントロール ウィンドウのサイズに依存しないテキストの制限四角形です。

`SetRectNP`は、エディット`SetRect`コントロール ウィンドウが再描画されないことを除いて、メンバー関数と同じです。

エディット コントロールが最初に作成されるとき、書式設定の四角形はエディット コントロール ウィンドウのクライアント領域と同じです。 アプリケーションは、`SetRectNP`メンバー関数を呼び出すことで、書式設定用の四角形をエディット コントロール ウィンドウよりも大きくまたは小さくすることができます。

エディット コントロールにスクロール バーがない場合、書式設定された四角形がウィンドウより大きくなると、テキストは折り返されずにクリップされます。

このメンバーは、複数行のエディット コントロールによってのみ処理されます。

詳細については、Windows SDK の[EM_SETRECTNP](/windows/win32/Controls/em-setrectnp)を参照してください。

### <a name="example"></a>例

  [CEdit::SetRect](#setrect)の例を参照してください。

## <a name="ceditsetsel"></a><a name="setsel"></a>エディット::セットセル

エディット コントロール内の文字の範囲を選択します。

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

*dw選択*<br/>
下位の単語の開始位置と上位ワードの終了位置を指定します。 下位ワードが 0 で、上位ワードが -1 の場合、エディット コントロール内のすべてのテキストが選択されます。 下位ワードが -1 の場合、現在の選択はすべて削除されます。

*をスクロールします。*<br/>
キャレットをスクロールして表示するかどうかを示します。 FALSE の場合、キャレットはビューにスクロールされます。 TRUE の場合、キャレットはビューにスクロールされません。

*nStartChar*<br/>
開始位置を指定します。 *nStartChar*が 0 で*nEndChar*が -1 の場合、エディット コントロール内のすべてのテキストが選択されます。 *nStartChar*が -1 の場合、現在の選択項目はすべて削除されます。

*エンドチャー*<br/>
終了位置を指定します。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[EM_SETSEL](/windows/win32/Controls/em-setsel)を参照してください。

### <a name="example"></a>例

  [CEdit::GetSel](#getsel)の例を参照してください。

## <a name="ceditsettabstops"></a><a name="settabstops"></a>編集::セットタブストップ

複数行のエディット コントロールでタブストップを設定します。

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>パラメーター

*お互いの停止*<br/>
タブストップを*すべてのcxEachStop*ダイアログユニットで設定することを指定します。

*nタブストップ*<br/>
*rgTabStops*に含まれるタブ ストップの数を指定します。 この数値は 1 より大きくなければなりません。

*rgタブストップ*<br/>
タブストップをダイアログ単位で指定する符号なし整数の配列へのポイント。 ダイアログ単位は、水平または垂直の距離です。 1 つの水平ダイアログ単位は現在のダイアログ ベースの幅単位の 4 分の 1 に等しく、1 つの垂直ダイアログ単位は現在のダイアログ ベースの高さの単位の 8 分の 1 に等しくなります。 ダイアログベースの単位は、現在のシステムフォントの高さと幅に基づいて計算されます。 Windows`GetDialogBaseUnits`関数は、現在のダイアログベースの単位をピクセル単位で返します。

### <a name="return-value"></a>戻り値

タブが設定されている場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

複数行のエディット コントロールにテキストをコピーすると、テキスト内の任意のタブ文字が次のタブ位置までスペースを生成します。

タブストップを既定のサイズである 32 ダイアログ ユニットに設定するには、このメンバー関数のパラメーターなしのバージョンを呼び出します。 タブストップを 32 以外のサイズに設定するには *、cxEachStop*パラメーターを使用してバージョンを呼び出します。 タブストップをサイズの配列に設定するには、2 つのパラメーターを持つバージョンを使用します。

このメンバー関数は、複数行のエディット コントロールによってのみ処理されます。

`SetTabStops`では、編集ウィンドウが自動的に再描画されることはありません。 エディット コントロールに既に存在するテキストのタブ ストップを変更した場合は[、CWnd::InvalidateRect](cwnd-class.md#invalidaterect)を呼び出して編集ウィンドウを再描画します。

詳細については、windows SDK の[EM_SETTABSTOPS](/windows/win32/Controls/em-settabstops)と[GetDialogBaseUnits](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits)を参照してください。

### <a name="example"></a>例

  「[テキストビュー::セットタブストップ](ceditview-class.md#settabstops)」の例を参照してください。

## <a name="ceditshowballoontip"></a><a name="showballoontip"></a>エディット::バルーンチップを表示

現在のエディット コントロールに関連付けられているバルーン ヒントが表示されます。

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
|*バルーンヒントを編集します。*|[in]バルーン ヒントを記述する[EDITBALLOONTIP](/windows/win32/api/commctrl/ns-commctrl-editballoontip)構造体へのポインター。|
|*lpszタイトル*|[in]バルーン ヒントのタイトルを含む Unicode 文字列へのポインター。|
|*lpszText*|[in]バルーン ヒント テキストを含む Unicode 文字列へのポインター。|
|*ティアイコン*|[in]バルーン ヒントに関連付けるアイコンの種類を指定する**INT。** 既定値は TTI_NONE です。 詳細については`ttiIcon`[、EDITBALLOONTIP](/windows/win32/api/commctrl/ns-commctrl-editballoontip)構造体のメンバーを参照してください。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数は、Windows SDK に記載されている[EM_SHOWBALLOONTIP](/windows/win32/Controls/em-showballoontip)メッセージを送信します。 詳細については[、Edit_ShowBalloonTip](/windows/win32/api/commctrl/nf-commctrl-edit_showballoontip)マクロを参照してください。

### <a name="example"></a>例

次のコード例では、`m_cedit`現在のエディット コントロールにアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>例

エディット コントロールのバルーン ヒントを表示するコード例を次に示します。 [CEdit::ShowBalloonTip](#showballoontip)メソッドは、タイトルとバルーン ヒントテキストを指定します。

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

## <a name="ceditundo"></a><a name="undo"></a>編集::元に戻す

最後のエディット コントロール操作を元に戻します。

```
BOOL Undo();
```

### <a name="return-value"></a>戻り値

単一行エディット コントロールの場合、戻り値は常に 0 以外です。 複数行エディット コントロールの場合、元に戻す操作が成功した場合は 0 以外の値を返し、元に戻す操作が失敗した場合は 0 を返します。

### <a name="remarks"></a>解説

元に戻す操作を元に戻すこともできます。 たとえば、削除したテキストを復元するには、 を最初に呼`Undo`び出します。 間に編集操作がない限り、2 回目の呼び出しでテキストを削除できます`Undo`。

詳細については、Windows SDK の[EM_UNDO](/windows/win32/Controls/em-undo)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[サンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](cwnd-class.md)<br/>
[CButton クラス](cbutton-class.md)<br/>
[Cコンボボックスクラス](ccombobox-class.md)<br/>
[CListBox クラス](clistbox-class.md)<br/>
[CScrollBar クラス](cscrollbar-class.md)<br/>
[CStatic クラス](cstatic-class.md)<br/>
[クラス](cdialog-class.md)
