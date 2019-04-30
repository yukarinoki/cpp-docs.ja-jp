---
title: CButton クラス
ms.date: 11/04/2016
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
ms.openlocfilehash: b1a02d995594f5e079359151167ac970a3d1ab37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348693"
---
# <a name="cbutton-class"></a>CButton クラス

Windows のボタン コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CButton : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CButton::CButton](#cbutton)|`CButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CButton::Create](#create)|Windows ボタン コントロールを作成しにアタッチします、`CButton`オブジェクト。|
|[CButton::DrawItem](#drawitem)|オーナー描画を描画するためにオーバーライド`CButton`オブジェクト。|
|[CButton::GetBitmap](#getbitmap)|以前のビットマップのハンドルを取得[SetBitmap](#setbitmap)します。|
|[CButton::GetButtonStyle](#getbuttonstyle)|ボタン コントロールのスタイルに関する情報を取得します。|
|[CButton::GetCheck](#getcheck)|ボタン コントロールのチェックの状態を取得します。|
|[CButton::GetCursor](#getcursor)|カーソルのイメージのハンドルが以前に設定と取得[以前](#setcursor)します。|
|[CButton::GetIcon](#geticon)|以前の設定アイコンのハンドルを取得[SetIcon](#seticon)します。|
|[CButton::GetIdealSize](#getidealsize)|ボタン コントロールの適切なサイズを取得します。|
|[CButton::GetImageList](#getimagelist)|ボタン コントロールのイメージ リストを取得します。|
|[CButton::GetNote](#getnote)|現在のコマンド リンク コントロールの注コンポーネントを取得します。|
|[CButton::GetNoteLength](#getnotelength)|現在のコマンド リンク コントロールのメモのテキストの長さを取得します。|
|[CButton::GetSplitGlyph](#getsplitglyph)|現在の分割ボタン コントロールに関連付けられたグリフを取得します。|
|[CButton::GetSplitImageList](#getsplitimagelist)|現在の分割ボタン コントロールのイメージ リストを取得します。|
|[CButton::GetSplitInfo](#getsplitinfo)|現在の分割ボタン コントロールを定義する情報を取得します。|
|[CButton::GetSplitSize](#getsplitsize)|現在の分割ボタン コントロールのドロップダウン リストのコンポーネントの外接する四角形を取得します。|
|[CButton::GetSplitStyle](#getsplitstyle)|現在の分割ボタン コントロールを定義する分割ボタンのスタイルを取得します。|
|[CButton::GetState](#getstate)|状態の確認、強調表示状態、およびボタン コントロールのフォーカスの状態を取得します。|
|[CButton::GetTextMargin](#gettextmargin)|ボタン コントロールのテキストの余白を取得します。|
|[CButton::SetBitmap](#setbitmap)|ボタンに表示されるビットマップを指定します。|
|[CButton::SetButtonStyle](#setbuttonstyle)|ボタンのスタイルを変更します。|
|[CButton::SetCheck](#setcheck)|ボタン コントロールのチェックの状態を設定します。|
|[CButton::SetCursor](#setcursor)|ボタンに表示されるカーソルのイメージを指定します。|
|[CButton::SetDropDownState](#setdropdownstate)|現在の分割ボタン コントロールのドロップダウン リストの状態を設定します。|
|[CButton::SetIcon](#seticon)|ボタンに表示されるアイコンを指定します。|
|[CButton::SetImageList](#setimagelist)|ボタン コントロールのイメージ リストを設定します。|
|[CButton::SetNote](#setnote)|現在のコマンド リンク コントロールのメモを設定します。|
|[CButton::SetSplitGlyph](#setsplitglyph)|指定されたグリフを現在の分割ボタン コントロールに関連付けます。|
|[CButton::SetSplitImageList](#setsplitimagelist)|イメージ リストを現在の分割ボタン コントロールに関連付けます。|
|[CButton::SetSplitInfo](#setsplitinfo)|現在の分割ボタン コントロールを定義する情報を指定します。|
|[CButton::SetSplitSize](#setsplitsize)|現在の分割ボタン コントロールのドロップダウン リストのコンポーネントの外接する四角形を設定します。|
|[CButton::SetSplitStyle](#setsplitstyle)|現在の分割ボタン コントロールのスタイルを設定します。|
|[CButton::SetState](#setstate)|ボタン コントロールの強調表示の状態を設定します。|
|[CButton::SetTextMargin](#settextmargin)|ボタン コントロールのテキストの余白を設定します。|

## <a name="remarks"></a>Remarks

ボタン コントロールは、オンとオフをクリックして可能な小さな四角形の子ウィンドウです。 ボタンは、1 人またはグループに使用することができますとラベルを付けることができますか、またはテキストなしで表示されます。 ユーザーがクリックしたとき、ボタンは通常の外観を変更します。

一般的なボタンは、チェック ボックス、ラジオ ボタン、およびプッシュ ボタンには。 A`CButton`オブジェクトは、これらのいずれかになることができますに従い、[ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)によって初期化時に指定された、[作成](#create)メンバー関数。

さらに、 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)クラスから派生した`CButton`テキストではなくビットマップ イメージ ラベルが付いたボタン コントロールの作成をサポートします。 A`CBitmapButton`ボタンの下、重点を置いて、および状態を無効になっているは、別のビットマップを持つことができます。

ダイアログ テンプレートから、またはコードで直接、ボタン コントロールを作成できます。 どちらの場合も、コンス トラクターを呼び出す最初`CButton`を構築する、`CButton`オブジェクト; を呼び出して、`Create`メンバー関数は、Windows を作成するボタン コントロールと、アタッチ先、`CButton`オブジェクト。

派生したクラスの 1 ステップのプロセスは、構築`CButton`します。 呼び出しと派生クラスのコンス トラクターを記述`Create`からコンス トラクター内。

ボタン コントロールからその親に送信される Windows 通知メッセージを処理する場合 (通常はから派生したクラス[CDialog](../../mfc/reference/cdialog-class.md))、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。

各メッセージ マップ エントリは、次の形式をとります。

**ON\_**_Notification_ **(** _id_, _memberFxn_ **)**

場所*id*通知を送信するコントロールの子ウィンドウ ID を指定および*memberFxn*通知を処理するために記述した親メンバー関数の名前を指定します。

親の関数のプロトタイプは次のとおりです。

`afx_msg void memberFxn();`

潜在的なメッセージ マップ エントリは次のとおりです。

|マップ エントリ|ときに親に送信しています.|
|---------------|----------------------------|
|ON_BN_CLICKED|ユーザーがボタンをクリックします。|
|ON_BN_DOUBLECLICKED|ユーザーがボタンをダブルクリックします。|

作成する場合、`CButton`ダイアログ リソースからのオブジェクト、 `CButton`  ダイアログ ボックスを閉じると、オブジェクトが自動的に破棄されます。

作成する場合、`CButton`オブジェクト、ウィンドウ内にそれを破棄する必要があります。 作成する場合、`CButton`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**ボタン コントロールをユーザーが、Windows を閉じるときに破棄するオブジェクト。 作成する場合、`CButton`またはスタック上のオブジェクトが親ダイアログ オブジェクトに埋め込まれた、自動的に破棄します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CButton`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cbutton"></a>  CButton::CButton

`CButton` オブジェクトを構築します。

```
CButton();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]

##  <a name="create"></a>  CButton::Create

Windows ボタン コントロールを作成しにアタッチします、`CButton`オブジェクト。

```
virtual BOOL Create(
    LPCTSTR lpszCaption,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*lpszCaption*<br/>
ボタン コントロールのテキストを指定します。

*dwStyle*<br/>
ボタン コントロールのスタイルを指定します。 任意の組み合わせを適用[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)ボタン。

*rect*<br/>
ボタン コントロールのサイズと位置を指定します。 いずれかのことができます、`CRect`オブジェクトまたは`RECT`構造体。

*pParentWnd*<br/>
通常、ボタン コントロールの親ウィンドウを指定します、`CDialog`します。 NULL は指定できません。

*nID*<br/>
ボタン コントロールの ID を指定します

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

構築する、 `CButton` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出して`Create`、Windows ボタン コントロールを作成しにアタッチする`CButton`オブジェクト。

WS_VISIBLE スタイルを指定すると、Windows はアクティブ化し、ボタンを表示するために必要なすべてのメッセージをボタン コントロールに送信します。

次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)ボタン コントロールに。

- WS_CHILD 常に

- WS_VISIBLE 通常

- WS_DISABLED ことはほとんどありません。

- WS_GROUP コントロールをグループ化

- WS_TABSTOP をタブ移動順序で、ボタンを含める

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]

##  <a name="drawitem"></a>  CButton::DrawItem

オーナー描画ボタンの外観が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
Long ポインター、 [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)構造体。 構造体には、描画される項目および必要な図面の種類に関する情報が含まれています。

### <a name="remarks"></a>Remarks

BS_OWNERDRAW スタイルを設定しています、オーナー描画ボタン オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CButton`オブジェクト。 アプリケーションで提供されるディスプレイ コンテキスト用に選択したすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*メンバーの前に、関数が終了します。

参照してください、[うち](../../mfc/reference/styles-used-by-mfc.md#button-styles)値のスタイルを設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]

##  <a name="getbitmap"></a>  CButton::GetBitmap

以前、ビットマップのハンドルを取得するには、このメンバー関数を呼び出す[SetBitmap](#setbitmap)、つまり、ボタンに関連付けられています。

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>戻り値

ビットマップへのハンドル。 以前にビットマップが指定されていない場合は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

##  <a name="getbuttonstyle"></a>  CButton::GetButtonStyle

ボタン コントロールのスタイルに関する情報を取得します。

```
UINT GetButtonStyle() const;
```

### <a name="return-value"></a>戻り値

このボタンのスタイルを返します`CButton`オブジェクト。 この関数のみを返します、[うち](../../mfc/reference/styles-used-by-mfc.md#button-styles)スタイルが値の他のウィンドウ スタイル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

##  <a name="getcheck"></a>  CButton::GetCheck

オプション ボタンやチェック ボックスのチェックの状態を取得します。

```
int GetCheck() const;
```

### <a name="return-value"></a>戻り値

BS_AUTOCHECKBOX、BS_AUTORADIOBUTTON、BS_AUTO3STATE BS_CHECKBOX、BS_RADIOBUTTON、作成したボタン コントロールからの戻り値または BS_3STATE スタイルは、次の値のいずれか。

|[値]|説明|
|-----------|-------------|
|設定されています。|ボタンの状態がオフになっています。|
|BST_CHECKED|ボタンの状態がチェックされます。|
|BST_INDETERMINATE|ボタンの状態が不定になります (ボタンに BS_3STATE または BS_AUTO3STATE スタイルがある場合にのみ適用されます)。|

その他のスタイルをボタンには、戻り値が設定されています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

##  <a name="getcursor"></a>  CButton::GetCursor

以前、カーソルのハンドルを取得するには、このメンバー関数を呼び出す[以前](#setcursor)、つまり、ボタンに関連付けられています。

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>戻り値

カーソル イメージへのハンドル。 以前にカーソルが指定されていない場合は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

##  <a name="geticon"></a>  CButton::GetIcon

以前、アイコンのハンドルを取得するには、このメンバー関数を呼び出す[SetIcon](#seticon)、つまり、ボタンに関連付けられています。

```
HICON GetIcon() const;
```

### <a name="return-value"></a>戻り値

アイコンにへのハンドル。 以前にアイコンが指定されていない場合は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

##  <a name="getidealsize"></a>  CButton::GetIdealSize

ボタン コントロールの適切なサイズを取得します。

```
BOOL GetIdealSize(SIZE* psize);
```

### <a name="parameters"></a>パラメーター

*psize*<br/>
ボタンの現在のサイズへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は」の説明に従って、BCM_GETIDEALSIZE メッセージの機能をエミュレート、[ボタン](/windows/desktop/controls/buttons)Windows SDK の「します。

##  <a name="getimagelist"></a>  CButton::GetImageList

ボタン コントロールからのイメージ リストを取得するには、このメソッドを呼び出します。

```
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>パラメーター

*pbuttonImagelist*<br/>
イメージ リストへのポインター、`CButton`オブジェクト。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は」の説明に従って、BCM_GETIMAGELIST メッセージの機能をエミュレート、[ボタン](/windows/desktop/controls/buttons)Windows SDK の「します。

##  <a name="getnote"></a>  CButton::GetNote

現在のコマンド リンク コントロールに関連付けられたメモのテキストを取得します。

```
CString GetNote() const;

BOOL GetNote(
    LPTSTR lpszNote,
    UINT* cchNote) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpszNote*|[out]呼び出し元が割り当てと解放を担当する、バッファーへのポインター。 バッファーに現在のコマンド リンク コントロールに関連付けられているメモのテキストが含まれています、戻り値が TRUE の場合それ以外の場合、バッファーは変更されません。|
|*cchNote*|[入力、出力]符号なし整数型の変数へのポインター。<br /><br /> 変数にはこのメソッドが呼び出されるで指定したバッファーのサイズが含まれています、 *lpszNote*パラメーター。<br /><br /> ときにこのメソッドから戻り値が TRUE、変数の場合に、現在のコマンド リンク コントロールに関連付けられている注釈のサイズが含まれています。 戻り値が FALSE の場合、変数には、メモの格納に必要なバッファー サイズが含まれています。|

### <a name="return-value"></a>戻り値

最初のオーバー ロードで、 [CString](../../atl-mfc-shared/using-cstring.md)を現在のコマンド リンク コントロールに関連付けられたメモのテキストを含むオブジェクト。

- または -

2 番目のオーバー ロードでは、このメソッドが成功した場合は TRUE します。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_COMMANDLINK または BS_DEFCOMMANDLINK コントロールでのみ、このメソッドを使用します。

このメソッドは、送信、 [BCM_GETNOTE](/windows/desktop/Controls/bcm-getnote)メッセージは、Windows SDK で説明します。

##  <a name="getnotelength"></a>  CButton::GetNoteLength

現在のコマンド リンク コントロールのメモのテキストの長さを取得します。

```
UINT GetNoteLength() const;
```

### <a name="return-value"></a>戻り値

現在のコマンド リンク コントロールの 16 ビット Unicode 文字で、メモのテキストの長さ。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_COMMANDLINK または BS_DEFCOMMANDLINK コントロールでのみ、このメソッドを使用します。

このメソッドは、送信、 [BCM_GETNOTELENGTH](/windows/desktop/Controls/bcm-getnotelength)メッセージは、Windows SDK で説明します。

##  <a name="getsplitglyph"></a>  CButton::GetSplitGlyph

現在の分割ボタン コントロールに関連付けられたグリフを取得します。

```
TCHAR GetSplitGlyph() const;
```

### <a name="return-value"></a>戻り値

現在の分割ボタン コントロールに関連付けられたグリフ文字。

### <a name="remarks"></a>Remarks

グリフは、特定のフォントの文字の物理表現です。 たとえば、分割ボタン コントロールをチェック マークの Unicode 文字のグリフで装飾可能性があります (U + 2713)。

ボタン スタイルは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON コントロールでのみ、このメソッドを使用します。

このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_GLYPH フラグ、および、構造体の送信を含む構造体、[したり](/windows/desktop/Controls/bcm-getsplitinfo)メッセージに記載されている、Windows SDK。 このメソッドがからグリフを取得するメッセージの関数が戻るとき、`himlGlyph`構造体のメンバー。

##  <a name="getsplitimagelist"></a>  CButton::GetSplitImageList

取得、[イメージ リスト](../../mfc/reference/cimagelist-class.md)の現在の分割ボタン コントロール。

```
CImageList* GetSplitImageList() const;
```

### <a name="return-value"></a>戻り値

ポインターを[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON コントロールでのみ、このメソッドを使用します。

このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_IMAGE フラグ、および、構造体の送信を含む構造体、[したり](/windows/desktop/Controls/bcm-getsplitinfo)メッセージに記載されている、Windows SDK。 このメソッドは、イメージの一覧から取得メッセージ関数が戻るとき、`himlGlyph`構造体のメンバー。

##  <a name="getsplitinfo"></a>  CButton::GetSplitInfo

Windows が現在の分割ボタン コントロールを描画する方法を決定するパラメーターを取得します。

```
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pInfo*|[out]ポインターを[BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo)現在の分割ボタン コントロールに関する情報を受け取る構造体。 呼び出し元が、構造体を割り当てる責任を負います。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON コントロールでのみ、このメソッドを使用します。

このメソッドは、送信、[したり](/windows/desktop/Controls/bcm-getsplitinfo)メッセージは、Windows SDK で説明します。

##  <a name="getsplitsize"></a>  CButton::GetSplitSize

現在の分割ボタン コントロールのドロップダウン リストのコンポーネントの外接する四角形を取得します。

```
BOOL GetSplitSize(LPSIZE pSize) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pSize*|[out]ポインターを[サイズ](/windows/desktop/api/windef/ns-windef-tagsize)四角形の説明を受け取る。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON コントロールでのみ、このメソッドを使用します。

分割ボタン コントロールが展開されている場合は、リスト コントロールのページャー コントロールなどのドロップダウン リストのコンポーネントを表示できます。 このメソッドは、ドロップダウン リストのコンポーネントを含んでいる外接する四角形を取得します。

このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_SIZE フラグ、および、構造体の送信を含む構造体、[したり](/windows/desktop/Controls/bcm-getsplitinfo)メッセージに記載されている、Windows SDK。 このメソッドは、外接する四角形から取得メッセージ関数が戻るとき、`size`構造体のメンバー。

##  <a name="getsplitstyle"></a>  CButton::GetSplitStyle

現在の分割ボタン コントロールを定義する分割ボタンのスタイルを取得します。

```
UINT GetSplitStyle() const;
```

### <a name="return-value"></a>戻り値

分割ボタンのスタイルのビットごとの組み合わせ。 詳細については、次を参照してください。、`uSplitStyle`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo)構造体。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON コントロールでのみ、このメソッドを使用します。

分割ボタンのスタイルは、配置、縦横比、および Windows 分割ボタンのアイコンを描画するため、グラフィカルな形式を指定します。

このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_STYLE フラグ、および、構造体の送信を含む構造体、[したり](/windows/desktop/Controls/bcm-getsplitinfo)メッセージに記載されている、Windows SDK。 このメソッドがから分割ボタンのスタイルを取得するメッセージの関数が戻るとき、`uSplitStyle`構造体のメンバー。

##  <a name="getstate"></a>  CButton::GetState

ボタン コントロールの状態を取得します。

```
UINT GetState() const;
```

### <a name="return-value"></a>戻り値

ボタン コントロールの現在の状態を示す値の組み合わせを含むビット フィールド。 次の表では、使用可能な値を示します。

|ボタンの状態|[値]|説明|
|------------------|-----------|-----------------|
|設定されています。|0x0000|初期状態です。|
|BST_CHECKED|0x0001|ボタン コントロールがチェックされます。|
|BST_INDETERMINATE|0x0002|状態は、中間 (のみ可能なボタン コントロールに 3 つの状態がある場合) です。|
|BST_PUSHED|0x0004|ボタン コントロールが押されました。|
|BST_FOCUS|0x0008|ボタン コントロールにフォーカスが移動するとします。|

### <a name="remarks"></a>Remarks

BS_3STATE または BS_AUTO3STATE ボタン スタイルをボタン コントロールは、中間の状態は、という 3 つ目の状態にあるチェック ボックスを作成します。 中間の状態は、チェック ボックスがオンでもオフでもないことを示します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

##  <a name="gettextmargin"></a>  CButton::GetTextMargin

テキストの余白を取得するには、このメソッドを呼び出して、`CButton`オブジェクト。

```
BOOL GetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>パラメーター

*pmargin*<br/>
テキストの右側部分へのポインター、`CButton`オブジェクト。

### <a name="return-value"></a>戻り値

テキストの余白を返します。

### <a name="remarks"></a>Remarks

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は」の説明に従って、BCM_GETTEXTMARGIN メッセージの機能をエミュレート、[ボタン](/windows/desktop/controls/buttons)Windows SDK の「します。

##  <a name="setbitmap"></a>  CButton::SetBitmap

新しいビットマップをボタンに関連付けるには、このメンバー関数を呼び出します。

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>パラメーター

*hBitmap*<br/>
ビットマップのハンドル。

### <a name="return-value"></a>戻り値

以前は、ボタンに関連付けられたビットマップのハンドル。

### <a name="remarks"></a>Remarks

ビットマップは既定で中央揃え ボタンの表面に自動的に配置されます。 ビットマップが大きすぎてボタンのいずれかの側クリップされます。 次のように、他の配置オプションを選択できます。

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

異なり[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)、ボタン、4 つのビットマップを使用する`SetBitmap`ボタンごとの 1 つだけのビットマップを使用します。 ボタンが押されたときに移行し、右下に、ビットマップが表示されます。

それが済んだら、ビットマップを解放します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

##  <a name="setbuttonstyle"></a>  CButton::SetButtonStyle

ボタンのスタイルを変更します。

```
void SetButtonStyle(
    UINT nStyle,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*nStyle*<br/>
指定します、[ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)します。

*bRedraw*<br/>
ボタンを再描画するかどうかを指定します。 0 以外の値は、ボタンを再描画します。 値 0 は、ボタンを再描画されません。 既定では、ボタンが再描画されます。

### <a name="remarks"></a>Remarks

使用して、`GetButtonStyle`ボタン スタイルを取得します。 完了ボタン スタイルの下位ワードは、特定のボタンのスタイルです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

##  <a name="setcheck"></a>  CButton::SetCheck

設定またはラジオ ボタンまたはチェック ボックスのチェックの状態をリセットします。

```
void SetCheck(int nCheck);
```

### <a name="parameters"></a>パラメーター

*確認してください。*<br/>
チェックの状態を指定します。 このパラメーターには、次のいずれかを指定できます。

|[値]|説明|
|-----------|-------------|
|設定されています。|ボタンの状態をオフに設定します。|
|BST_CHECKED|チェック ボタンの状態を設定します。|
|BST_INDETERMINATE|中間には、ボタンの状態を設定します。 この値は、ボタンに BS_3STATE または BS_AUTO3STATE スタイルがある場合にのみ使用できます。|

### <a name="remarks"></a>Remarks

このメンバー関数は、プッシュ ボタンに影響を与えません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

##  <a name="setcursor"></a>  CButton::SetCursor

新しいカーソルをボタンに関連付けるには、このメンバー関数を呼び出します。

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>パラメーター

*hCursor*<br/>
カーソルのハンドル。

### <a name="return-value"></a>戻り値

以前、ボタンに関連付けられているカーソルのハンドル。

### <a name="remarks"></a>Remarks

カーソルは既定で中央揃え ボタンの表面に自動的に配置されます。 カーソルが大きすぎてボタンのいずれかの側クリップされます。 次のように、他の配置オプションを選択できます。

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

異なり[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)、ボタン、4 つのビットマップを使用する`SetCursor`ボタンごとに 1 つだけのカーソルを使用します。 ボタンが押されたときに移行し、右下にカーソルが表示されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

##  <a name="setdropdownstate"></a>  CButton::SetDropDownState

現在の分割ボタン コントロールのドロップダウン リストの状態を設定します。

```
BOOL SetDropDownState(BOOL fDropDown);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*fDropDown*|[in]BST_DROPDOWNPUSHED の状態を設定する場合は TRUEそれ以外の場合、FALSE です。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

分割ボタン コントロールは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON のスタイルを備え、ボタンと右側の下矢印で構成されます。 詳細については、次を参照してください。[ボタンのスタイル](/windows/desktop/Controls/button-styles)します。 通常は、ドロップダウン状態は、ユーザーがドロップダウンの矢印をクリックしたときに設定されます。 コントロールのドロップダウン リストの状態をプログラムで設定するのにには、このメソッドを使用します。 ドロップダウン矢印が、状態を示す影を描画します。

このメソッドは、送信、 [BCM_SETDROPDOWNSTATE](/windows/desktop/Controls/bcm-setdropdownstate)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 *m_splitButton*が分割ボタン コントロールをプログラムでアクセスするために使用します。 この変数は、次の例で使用されます。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

次のコード例では、ドロップダウン矢印がプッシュされたことを示す分割ボタン コントロールの状態を設定します。

[!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]

##  <a name="setelevationrequired"></a>  CButton::SetElevationRequired

ボタン コントロールを現在の状態を設定`elevation required`、管理者特権でのセキュリティ アイコンを表示するコントロールに必要な。

```
BOOL SetElevationRequired(BOOL fElevationRequired);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*fElevationRequired*|[in]設定する場合は True`elevation required`状態、それ以外は FALSE。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタンまたはコマンド リンク コントロールは、操作を実行する管理者特権でのセキュリティ アクセス許可を必要とする場合は、コントロールを設定`elevation required`状態。 その後、Windows では、コントロールのユーザー アカウント制御 (UAC) 盾のアイコンが表示されます。 詳細についてを参照してください「ユーザー アカウント制御」 [MSDN](http://go.microsoft.com/fwlink/p/?linkid=18507)します。

このメソッドは、送信、 [BCM_SETSHIELD](/windows/desktop/Controls/bcm-setshield)メッセージは、Windows SDK で説明します。

##  <a name="seticon"></a>  CButton::SetIcon

新しいアイコンをボタンに関連付けるには、このメンバー関数を呼び出します。

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*hIcon*<br/>
アイコンのハンドル。

### <a name="return-value"></a>戻り値

以前、ボタンに関連付けられているアイコンのハンドル。

### <a name="remarks"></a>Remarks

アイコンは、既定で中央揃え ボタンの表面に自動的に配置されます。 ボタンのアイコンが大きすぎて、右辺でも左辺でもクリップされます。 次のように、他の配置オプションを選択できます。

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

異なり[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)、ボタン、4 つのビットマップを使用する`SetIcon`ボタンごとの 1 つだけのアイコンが使用されます。 ボタンが押されたときに、シフトし、右下に、アイコンが表示されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

##  <a name="setimagelist"></a>  CButton::SetImageList

イメージ リストを設定するには、このメソッドを呼び出して、`CButton`オブジェクト。

```
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>パラメーター

*pbuttonImagelist*<br/>
新しいイメージ リストへのポインター。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は」の説明に従って、BCM_SETIMAGELIST メッセージの機能をエミュレート、[ボタン](/windows/desktop/controls/buttons)Windows SDK の「します。

##  <a name="setnote"></a>  CButton::SetNote

現在のコマンド リンク コントロールのメモのテキストを設定します。

```
BOOL SetNote(LPCTSTR lpszNote);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpszNote*|[in]コマンド リンク コントロールのメモのテキストとして設定されている Unicode 文字列へのポインター。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_COMMANDLINK または BS_DEFCOMMANDLINK コントロールでのみ、このメソッドを使用します。

このメソッドは、送信、 [BCM_SETNOTE](/windows/desktop/Controls/bcm-setnote)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 *m_cmdLink*、つまりコマンド リンク コントロールをプログラムでアクセスするために使用します。 この変数は、次の例で使用されます。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

次のコード例では、コマンド リンク コントロールのメモのテキストを設定します。

[!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]

##  <a name="setsplitglyph"></a>  CButton::SetSplitGlyph

指定されたグリフを現在の分割ボタン コントロールに関連付けます。

```
BOOL SetSplitGlyph(TCHAR chGlyph);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*chGlyph*|[in]分割ボタンのドロップダウン矢印として使用するグリフを指定する文字。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

BS_SPLITBUTTON または BS_DEFSPLITBUTTON ボタン スタイルのコントロールでのみ、このメソッドを使用します。

グリフは、特定のフォントの文字の物理表現です。 *ChGlyph*パラメーターは、グリフとしては使用されませんが、システム定義のグリフのセットからグリフを選択するために使用します。 既定のドロップダウン矢印グリフ文字 '6' で指定された Unicode 文字 (U + 25BC) 黒いダウン右向き三角形に類似しています。

このメソッドを初期化します、`mask`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_GLYPH フラグを含む構造体と`himlGlyph`を持つメンバー、 *chGlyph*パラメーター、し、送信します。構造体、[したり](/windows/desktop/Controls/bcm-getsplitinfo)Windows SDK で説明されているメッセージ。

##  <a name="setsplitimagelist"></a>  CButton::SetSplitImageList

関連付けます、[イメージ リスト](../../mfc/reference/cimagelist-class.md)現在の分割ボタン コントロールを使用します。

```
BOOL SetSplitImageList(CImageList* pSplitImageList);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pSplitImageList*|[in]ポインターを[CImageList](../../mfc/reference/cimagelist-class.md)を現在の分割ボタン コントロールに割り当てるオブジェクト。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON コントロールでのみ、このメソッドを使用します。

このメソッドは、初期化、`mask`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_IMAGE フラグを含む構造体と`himlGlyph`を持つメンバー、 *pSplitImageList*パラメーターを作成して送信し、その構造体、[したり](/windows/desktop/Controls/bcm-getsplitinfo)Windows SDK で説明されているメッセージ。

##  <a name="setsplitinfo"></a>  CButton::SetSplitInfo

Windows が現在の分割ボタン コントロールを描画する方法を決定するパラメーターを指定します。

```
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pInfo*|[in]ポインターを[BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo)現在の分割ボタン コントロールを定義する構造体。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON コントロールでのみ、このメソッドを使用します。

このメソッドは、送信、 [BCM_SETSPLITINFO](/windows/desktop/Controls/bcm-setsplitinfo)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。`m_splitButton`が分割ボタン コントロールをプログラムでアクセスするために使用します。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

次のコード例では、分割ボタンのドロップダウン矢印用に使用されるグリフを変更します。 例では、上向き三角形グリフ既定下向きの三角形のグリフの置換されます。 指定した文字に表示されるグリフの依存、`himlGlyph`のメンバー、`BUTTON_SPLITINFO`構造体。 下向きの三角形のグリフが ' 6 文字で指定された '、' 5 文字で、上向き三角形のグリフが指定された '。 比較については、便利なメソッドを参照してください。 [CButton::SetSplitGlyph](#setsplitglyph)します。

[!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]

##  <a name="setsplitsize"></a>  CButton::SetSplitSize

現在の分割ボタン コントロールのドロップダウン リストのコンポーネントの外接する四角形を設定します。

```
BOOL SetSplitSize(LPSIZE pSize);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pSize*|[in]ポインターを[サイズ](/windows/desktop/api/windef/ns-windef-tagsize)外接する四角形を記述する構造体。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON コントロールでのみ、このメソッドを使用します。

分割ボタン コントロールが展開されている場合は、リスト コントロールのページャー コントロールなどのドロップダウン リストのコンポーネントを表示できます。 このメソッドは、ドロップダウン リストのコンポーネントを含んでいる外接する四角形のサイズを指定します。

このメソッドを初期化します、`mask`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_SIZE フラグを含む構造体と`size`を持つメンバー、 *pSize*パラメーターとし、構造体の送信[したり](/windows/desktop/Controls/bcm-getsplitinfo)Windows SDK で説明されているメッセージ。

### <a name="example"></a>例

次のコード例は、変数を定義します。`m_splitButton`が分割ボタン コントロールをプログラムでアクセスするために使用します。 この変数は、次の例で使用されます。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

次のコード例には、分割ボタンのドロップダウン矢印のサイズが 2 倍にします。

[!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]

##  <a name="setsplitstyle"></a>  CButton::SetSplitStyle

現在の分割ボタン コントロールのスタイルを設定します。

```
BOOL SetSplitStyle(UINT uSplitStyle);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*uSplitStyle*|[in]分割ボタンのスタイルのビットごとの組み合わせ。 詳細については、次を参照してください。、`uSplitStyle`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo)構造体。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ボタン スタイルは、BS_SPLITBUTTON または BS_DEFSPLITBUTTON コントロールでのみ、このメソッドを使用します。

分割ボタンのスタイルは、配置、縦横比、および Windows 分割ボタンのアイコンを描画するため、グラフィカルな形式を指定します。 詳細については、次を参照してください。、`uSplitStyle`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo)構造体。

このメソッドを初期化します、`mask`のメンバー、 [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_STYLE フラグを含む構造体と`uSplitStyle`を持つメンバー、 *uSplitStyle*パラメーター、し、送信します。構造体、[したり](/windows/desktop/Controls/bcm-getsplitinfo)Windows SDK で説明されているメッセージ。

### <a name="example"></a>例

次のコード例は、変数を定義します。`m_splitButton`が分割ボタン コントロールをプログラムでアクセスするために使用します。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

次のコード例では、分割ボタンのドロップダウン矢印のスタイルを設定します。 BCSS_ALIGNLEFT スタイルが、ボタンの左側にある矢印を表示し、BCSS_STRETCH スタイルは、ボタンのサイズを変更するときにドロップダウン矢印の比率を保持します。

[!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]

##  <a name="setstate"></a>  CButton::SetState

かどうか、ボタン コントロールが強調表示されているかどうかを設定します。

```
void SetState(BOOL bHighlight);
```

### <a name="parameters"></a>パラメーター

*bHighlight*<br/>
ボタンが強調表示されるかどうかを指定します。 0 以外の値には、ボタンが強調表示されます。値 0 は、任意の強調表示を削除します。

### <a name="remarks"></a>Remarks

強調表示ボタン コントロールの外観に影響を与えます。 オプション ボタンやチェック ボックスのチェックの状態に影響を与えません。

ボタン コントロールは、ユーザーをクリックし、マウスの左ボタンを保持しているときに自動的に強調表示されます。 ユーザーがマウス ボタンを離したときに、強調表示は削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

##  <a name="settextmargin"></a>  CButton::SetTextMargin

テキストの余白を設定するには、このメソッドを呼び出して、`CButton`オブジェクト。

```
BOOL SetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>パラメーター

*pmargin*<br/>
新しいテキスト余白へのポインター。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は」の説明に従って、BCM_SETTEXTMARGIN メッセージの機能をエミュレート、[ボタン](/windows/desktop/controls/buttons)Windows SDK の「します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic クラス](../../mfc/reference/cstatic-class.md)<br/>
[CBitmapButton クラス](../../mfc/reference/cbitmapbutton-class.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)
