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
ms.openlocfilehash: 05ad60855cd03115cf88ab2b51e56e6a26822035
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352443"
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
|[ボタン::CButton](#cbutton)|`CButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CButton::作成](#create)|Windows ボタン コントロールを作成し、オブジェクトに`CButton`アタッチします。|
|[ボタン::Dローアイテム](#drawitem)|オーナー描画`CButton`オブジェクトを描画する場合にオーバーライドします。|
|[ボタン::ビットマップを取得します。](#getbitmap)|前に[SetBitmap](#setbitmap)で設定したビットマップのハンドルを取得します。|
|[ボタン::ゲットボタンスタイル](#getbuttonstyle)|ボタン コントロールスタイルに関する情報を取得します。|
|[ボタン::ゲットチェック](#getcheck)|ボタン コントロールのチェック状態を取得します。|
|[ボタン::ゲットカーソル](#getcursor)|[SetCursor](#setcursor)で以前に設定したカーソル イメージのハンドルを取得します。|
|[ボタン::ゲットアイコン](#geticon)|前に[SetIcon](#seticon)で設定したアイコンのハンドルを取得します。|
|[ボタン::ゲットイデアルサイズ](#getidealsize)|ボタン コントロールの最適なサイズを取得します。|
|[ボタン::イメージリスト](#getimagelist)|ボタン コントロールのイメージ リストを取得します。|
|[ボタン::ゲットノート](#getnote)|現在のコマンド リンク コントロールのノート コンポーネントを取得します。|
|[ボタン::ゲットノート長](#getnotelength)|現在のコマンド リンク コントロールのノート テキストの長さを取得します。|
|[ボタン::取得スプリットグリフ](#getsplitglyph)|現在の分割ボタン コントロールに関連付けられているグリフを取得します。|
|[ボタン::取得スプリットイメージリスト](#getsplitimagelist)|現在の分割ボタン コントロールのイメージ リストを取得します。|
|[ボタン::ゲットスプリットインフォ](#getsplitinfo)|現在の分割ボタン コントロールを定義する情報を取得します。|
|[ボタン::ゲットスプリットサイズ](#getsplitsize)|現在の分割ボタン コントロールのドロップダウン コンポーネントの外接する四角形を取得します。|
|[ボタン::ゲットスプリットスタイル](#getsplitstyle)|現在の分割ボタン コントロールを定義する分割ボタン スタイルを取得します。|
|[ボタン::ゲットステート](#getstate)|ボタン コントロールのチェック状態、強調表示状態、およびフォーカス状態を取得します。|
|[ボタン::テキストマージンを取得します。](#gettextmargin)|ボタン コントロールのテキストマージンを取得します。|
|[ボタン::ビットマップを設定します。](#setbitmap)|ボタンに表示するビットマップを指定します。|
|[ボタン::セットボタンスタイル](#setbuttonstyle)|ボタンのスタイルを変更します。|
|[ボタン::セットチェック](#setcheck)|ボタン コントロールのチェック状態を設定します。|
|[ボタン::セットカーソル](#setcursor)|ボタンに表示するカーソル イメージを指定します。|
|[ボタン::セットドロップダウン状態](#setdropdownstate)|現在の分割ボタン コントロールのドロップダウン状態を設定します。|
|[ボタン::セットアイコン](#seticon)|ボタンに表示するアイコンを指定します。|
|[ボタン::セットイメージリスト](#setimagelist)|ボタン コントロールのイメージ リストを設定します。|
|[ボタン::セットノート](#setnote)|現在のコマンド リンク コントロールのメモを設定します。|
|[ボタン::セットスプリットグリフ](#setsplitglyph)|指定したグリフを現在の分割ボタン コントロールに関連付けます。|
|[ボタン::セットスプリットイメージリスト](#setsplitimagelist)|イメージ リストを現在の分割ボタン コントロールに関連付けます。|
|[ボタン::セットスプリットインフォ](#setsplitinfo)|現在の分割ボタン コントロールを定義する情報を指定します。|
|[ボタン::セットスプリットサイズ](#setsplitsize)|現在の分割ボタン コントロールのドロップダウン コンポーネントの外接する四角形を設定します。|
|[ボタン::セットスプリットスタイル](#setsplitstyle)|現在の分割ボタン コントロールのスタイルを設定します。|
|[ボタン::セットステート](#setstate)|ボタン コントロールの強調表示状態を設定します。|
|[ボタン::テキストマージンを設定します。](#settextmargin)|ボタン コントロールのテキストの余白を設定します。|

## <a name="remarks"></a>解説

ボタン コントロールは、クリックとオフを切り替えることができる小さな四角形の子ウィンドウです。 ボタンは単独でもグループでも使用でき、ラベル付けしたりテキストなしで表示したりできます。 ボタンは通常、ユーザーがボタンをクリックすると外観を変更します。

一般的なボタンは、チェック ボックス、ラジオ ボタン、およびプッシュ ボタンです。 Create メンバー関数によって初期化時に指定された[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)に従って、オブジェクトはこれらのいずれかになることができます。 [Create](#create) `CButton`

また、派生`CButton`した[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)クラスは、テキストではなくビットマップ イメージでラベル付けされたボタン コントロールの作成をサポートします。 ボタン`CBitmapButton`の上下、フォーカス、および無効の状態に対して、個別のビットマップを使用できます。

ボタン コントロールは、ダイアログ テンプレートから作成することも、コード内で直接作成することもできます。 どちらの場合も、まずコンストラクタ`CButton`を呼び出して`CButton`オブジェクトを構築します。次に、`Create`メンバー関数を呼び出して Windows ボタン コントロール`CButton`を作成し、オブジェクトにアタッチします。

構築は、 から`CButton`派生したクラスの 1 段階のプロセスです。 派生クラスのコンストラクターを記述し、コンストラクター`Create`内から呼び出します。

ボタン コントロールから親コントロールに送信される Windows 通知メッセージ (通常[は CDialog](../../mfc/reference/cdialog-class.md)から派生したクラス) を処理する場合は、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。

各メッセージ マップ エントリは、次の形式をとります。

**オン\_**_通知_**(** _id_,_メンバFxn_ **)**

ここで *、id*は通知を送信するコントロールの子ウィンドウ ID を指定し *、memberFxn*は通知を処理するために記述した親メンバー関数の名前です。

親の関数プロトタイプは次のとおりです。

`afx_msg void memberFxn();`

メッセージ マップのエントリは次のとおりです。

|マップエントリ|親に送信されます。|
|---------------|----------------------------|
|ON_BN_CLICKED|ユーザーがボタンをクリックします。|
|ON_BN_DOUBLECLICKED|ユーザーがボタンをダブルクリックします。|

ダイアログ リソースから`CButton`オブジェクトを作成すると、ユーザーが`CButton`ダイアログ ボックスを閉じるとオブジェクトは自動的に破棄されます。

ウィンドウ内にオブジェクト`CButton`を作成する場合は、オブジェクトを破棄する必要があります。 **新しい**関数を`CButton`使用してヒープ上にオブジェクトを作成する場合は、ユーザーが Windows ボタン コントロールを閉じたときに破棄するには、オブジェクトの**delete**を呼び出す必要があります。 スタック上にオブジェクト`CButton`を作成した場合、または親ダイアログ オブジェクトに埋め込まれている場合は、自動的に破棄されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CButton`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cbuttoncbutton"></a><a name="cbutton"></a>ボタン::CButton

`CButton` オブジェクトを構築します。

```
CButton();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]

## <a name="cbuttoncreate"></a><a name="create"></a>CButton::作成

Windows ボタン コントロールを作成し、オブジェクトに`CButton`アタッチします。

```
virtual BOOL Create(
    LPCTSTR lpszCaption,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*一方、一時おくもみ*<br/>
ボタン コントロールのテキストを指定します。

*Dwstyle*<br/>
ボタン コントロールのスタイルを指定します。 [ボタンスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)の任意の組み合わせをボタンに適用します。

*Rect*<br/>
ボタン コントロールのサイズと位置を指定します。 `CRect`オブジェクトまたは`RECT`構造体のいずれかです。

*pParentWnd*<br/>
ボタン コントロールの親ウィンドウを指定`CDialog`します。 NULL にすることはできません。

*nID*<br/>
ボタン コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

オブジェクトは`CButton`2 つの手順で作成します。 まず、コンストラクタを呼び出し`Create`、次に呼び出しを行い、Windows`CButton`ボタン コントロールを作成してオブジェクトにアタッチします。

WS_VISIBLEスタイルが指定されている場合、Windows はボタン コントロールをアクティブにしてボタンを表示するために必要なすべてのメッセージを送信します。

ボタン コントロールに次の[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を適用します。

- WS_CHILD常に

- WS_VISIBLE通常

- WS_DISABLEDまれ

- WS_GROUP グループ コントロールへ

- WS_TABSTOP タブ順序にボタンを含めるには

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]

## <a name="cbuttondrawitem"></a><a name="drawitem"></a>ボタン::Dローアイテム

オーナー描画ボタンの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
[構造体への](/windows/win32/api/winuser/ns-winuser-drawitemstruct)長いポインター。 構造には、描画する項目と必要な図面のタイプに関する情報が含まれています。

### <a name="remarks"></a>解説

オーナー描画ボタンには、BS_OWNERDRAWスタイルセットがあります。 オーナー描画`CButton`オブジェクトの描画を実装するには、このメンバー関数をオーバーライドします。 アプリケーションは、メンバー関数が終了する前に *、lpDrawItemStruct*で提供される表示コンテキストに選択されているすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります。

BS_[スタイル値](../../mfc/reference/styles-used-by-mfc.md#button-styles)も参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]

## <a name="cbuttongetbitmap"></a><a name="getbitmap"></a>ボタン::ビットマップを取得します。

このメンバー関数を呼び出して、ボタンに関連付けられている[SetBitmap](#setbitmap)で以前に設定されたビットマップのハンドルを取得します。

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>戻り値

ビットマップへのハンドル。 ビットマップが以前に指定されていない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttongetbuttonstyle"></a><a name="getbuttonstyle"></a>ボタン::ゲットボタンスタイル

ボタン コントロールスタイルに関する情報を取得します。

```
UINT GetButtonStyle() const;
```

### <a name="return-value"></a>戻り値

この`CButton`オブジェクトのボタン スタイルを返します。 この関数は[、BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles)スタイル値のみを返し、他のウィンドウスタイルは返しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttongetcheck"></a><a name="getcheck"></a>ボタン::ゲットチェック

オプション ボタンまたはチェック ボックスのチェック状態を取得します。

```
int GetCheck() const;
```

### <a name="return-value"></a>戻り値

BS_AUTOCHECKBOX、BS_AUTORADIOBUTTON、BS_AUTO3STATE、BS_CHECKBOX、BS_RADIOBUTTON、またはBS_3STATEスタイルで作成されたボタン コントロールからの戻り値は、次のいずれかの値です。

|[値]|意味|
|-----------|-------------|
|BST_UNCHECKED|ボタンの状態がオフになっています。|
|BST_CHECKED|ボタンの状態がチェックされます。|
|BST_INDETERMINATE|ボタンの状態は不確定です (ボタンにBS_3STATEまたはBS_AUTO3STATEスタイルがある場合にのみ適用されます)。|

ボタンに他のスタイルがある場合、戻り値はBST_UNCHECKED。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttongetcursor"></a><a name="getcursor"></a>ボタン::ゲットカーソル

このメンバー関数を呼び出して、以前に[SetCursor](#setcursor)で設定された、ボタンに関連付けられているカーソルのハンドルを取得します。

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>戻り値

カーソル イメージへのハンドル。 カーソルが以前に指定されていない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttongeticon"></a><a name="geticon"></a>ボタン::ゲットアイコン

このメンバー関数を呼び出して、以前に[SetIcon](#seticon)で設定されたボタンに関連付けられているアイコンのハンドルを取得します。

```
HICON GetIcon() const;
```

### <a name="return-value"></a>戻り値

アイコンにへのハンドル。 アイコンが指定されていない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttongetidealsize"></a><a name="getidealsize"></a>ボタン::ゲットイデアルサイズ

ボタン コントロールに最適なサイズを取得します。

```
BOOL GetIdealSize(SIZE* psize);
```

### <a name="parameters"></a>パラメーター

*Psize*<br/>
ボタンの現在のサイズへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK の[「ボタン](/windows/win32/controls/buttons)」セクションで説明されているように、BCM_GETIDEALSIZE メッセージの機能をエミュレートします。

## <a name="cbuttongetimagelist"></a><a name="getimagelist"></a>ボタン::イメージリスト

ボタン コントロールからイメージ リストを取得します。

```
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>パラメーター

*ボタンイメージリスト*<br/>
`CButton`オブジェクトのイメージ リストへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK の[「ボタン](/windows/win32/controls/buttons)」セクションで説明されているように、BCM_GETIMAGELIST メッセージの機能をエミュレートします。

## <a name="cbuttongetnote"></a><a name="getnote"></a>ボタン::ゲットノート

現在のコマンド リンク コントロールに関連付けられているノート テキストを取得します。

```
CString GetNote() const;

BOOL GetNote(
    LPTSTR lpszNote,
    UINT* cchNote) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpsz注*|[アウト]バッファーへのポインター。 戻り値が TRUE の場合、バッファーには、現在のコマンド リンク コントロールに関連付けられているノート テキストが含まれます。それ以外の場合、バッファーは変更されません。|
|*cchNote*|[イン、アウト]符号なし整数変数へのポインター。<br /><br /> このメソッドが呼び出されると、変数には *、lpszNote*パラメーターで指定されたバッファーのサイズが含まれます。<br /><br /> このメソッドが返されるときに、戻り値が TRUE の場合、変数には、現在のコマンド リンク コントロールに関連付けられているノートのサイズが格納されます。 戻り値が FALSE の場合、変数には、メモを格納するために必要なバッファー サイズが含まれます。|

### <a name="return-value"></a>戻り値

最初のオーバーロードでは、現在のコマンド リンク コントロールに関連付けられているノート テキストを含む[CString](../../atl-mfc-shared/using-cstring.md)オブジェクト。

\- または -

2 番目のオーバーロードでは、このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_COMMANDLINKまたはBS_DEFCOMMANDLINKのコントロールでのみ使用します。

このメソッドは、Windows SDK に記載されている[BCM_GETNOTE](/windows/win32/Controls/bcm-getnote)メッセージを送信します。

## <a name="cbuttongetnotelength"></a><a name="getnotelength"></a>ボタン::ゲットノート長

現在のコマンド リンク コントロールのノート テキストの長さを取得します。

```
UINT GetNoteLength() const;
```

### <a name="return-value"></a>戻り値

現在のコマンド リンク コントロールの 16 ビット Unicode 文字で表されるノート テキストの長さ。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_COMMANDLINKまたはBS_DEFCOMMANDLINKのコントロールでのみ使用します。

このメソッドは、Windows SDK に記載されている[BCM_GETNOTELENGTH](/windows/win32/Controls/bcm-getnotelength)メッセージを送信します。

## <a name="cbuttongetsplitglyph"></a><a name="getsplitglyph"></a>ボタン::取得スプリットグリフ

現在の分割ボタン コントロールに関連付けられているグリフを取得します。

```
TCHAR GetSplitGlyph() const;
```

### <a name="return-value"></a>戻り値

現在の分割ボタン コントロールに関連付けられているグリフ文字。

### <a name="remarks"></a>解説

グリフとは、特定のフォントの文字を物理的に表現したものです。 たとえば、分割ボタン コントロールは Unicode チェック マーク文字 (U+2713) のグリフで修飾できます。

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

このメソッドは、BCSIF_GLYPH`mask`フラグを使用して[BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体のメンバーを初期化し、Windows SDK で説明されている[BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo)メッセージでその構造体を送信します。 message 関数が返されるときに、このメソッドは構造体のメンバーから`himlGlyph`グリフを取得します。

## <a name="cbuttongetsplitimagelist"></a><a name="getsplitimagelist"></a>ボタン::取得スプリットイメージリスト

現在の分割ボタン コントロールの[イメージ リスト](../../mfc/reference/cimagelist-class.md)を取得します。

```
CImageList* GetSplitImageList() const;
```

### <a name="return-value"></a>戻り値

[オブジェクト](../../mfc/reference/cimagelist-class.md)へのポインター。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

このメソッドは`mask`[、BCSIF_IMAGE](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)フラグを使用してBUTTON_SPLITINFO構造体のメンバーを初期化し、Windows SDK で説明されている[BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo)メッセージでその構造体を送信します。 message 関数が返されるときに、構造体のメンバーからイメージ リストを`himlGlyph`取得します。

## <a name="cbuttongetsplitinfo"></a><a name="getsplitinfo"></a>ボタン::ゲットスプリットインフォ

Windows が現在の分割ボタン コントロールを描画する方法を決定するパラメーターを取得します。

```
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Pinfo*|[アウト]現在の分割ボタン コントロールに関する情報を受け取る[BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体へのポインター。 呼び出し元は構造体の割り当てを担当します。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

このメソッドは、Windows SDK で説明されている[BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo)メッセージを送信します。

## <a name="cbuttongetsplitsize"></a><a name="getsplitsize"></a>ボタン::ゲットスプリットサイズ

現在の分割ボタン コントロールのドロップダウン コンポーネントの外接する四角形を取得します。

```
BOOL GetSplitSize(LPSIZE pSize) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Psize*|[アウト]四角形の説明を受け取る[SIZE](/windows/win32/api/windef/ns-windef-size)構造体へのポインター。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

分割ボタン コントロールを展開すると、リスト コントロールやページャー コントロールなどのドロップダウン コンポーネントを表示できます。 このメソッドは、ドロップダウン コンポーネントを含む外接する四角形を取得します。

このメソッドは、BCSIF_SIZE`mask`フラグを使用して[BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体のメンバーを初期化し、Windows SDK で説明されている[BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo)メッセージでその構造体を送信します。 message 関数が返されるときに、このメソッドは構造体のメンバーから外接`size`する四角形を取得します。

## <a name="cbuttongetsplitstyle"></a><a name="getsplitstyle"></a>ボタン::ゲットスプリットスタイル

現在の分割ボタン コントロールを定義する分割ボタン スタイルを取得します。

```
UINT GetSplitStyle() const;
```

### <a name="return-value"></a>戻り値

分割ボタン スタイルのビットごとの組み合わせ。 詳細については[、BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体の`uSplitStyle`メンバーを参照してください。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

分割ボタンのスタイルは、Windows が分割ボタン アイコンを描画する場合の配置、縦横比、およびグラフィック形式を指定します。

このメソッドは、BCSIF_STYLE`mask`フラグを使用して[BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体のメンバーを初期化し、Windows SDK で説明されている[BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo)メッセージでその構造体を送信します。 message 関数が返されるときに、このメソッドは構造体の`uSplitStyle`メンバーから分割ボタン スタイルを取得します。

## <a name="cbuttongetstate"></a><a name="getstate"></a>ボタン::ゲットステート

ボタン コントロールの状態を取得します。

```
UINT GetState() const;
```

### <a name="return-value"></a>戻り値

ボタン コントロールの現在の状態を示す値の組み合わせを格納するビット フィールド。 次の表に、使用できる値を示します。

|ボタンの状態|[値]|説明|
|------------------|-----------|-----------------|
|BST_UNCHECKED|0x0000|初期状態。|
|BST_CHECKED|0x0001|ボタン コントロールがオンになります。|
|BST_INDETERMINATE|0x0002|状態は不確定です (ボタン コントロールに 3 つの状態がある場合にのみ可能)。|
|BST_PUSHED|0x0004|ボタン コントロールが押されました。|
|BST_FOCUS|0x0008|ボタン コントロールにフォーカスがあります。|

### <a name="remarks"></a>解説

BS_3STATEまたはBS_AUTO3STATEボタン スタイルのボタン コントロールは、不確定状態と呼ばれる 3 番目の状態を持つチェック ボックスを作成します。 不確定状態は、チェック ボックスがオンでもオフでもないことを示します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttongettextmargin"></a><a name="gettextmargin"></a>ボタン::テキストマージンを取得します。

`CButton`オブジェクトのテキストマージンを取得します。

```
BOOL GetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>パラメーター

*マージン*<br/>
`CButton`オブジェクトのテキストマージンへのポインター。

### <a name="return-value"></a>戻り値

テキストの余白を返します。

### <a name="remarks"></a>解説

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK の[ボタン](/windows/win32/controls/buttons)セクションで説明されているように、BCM_GETTEXTMARGIN メッセージの機能をエミュレートします。

## <a name="cbuttonsetbitmap"></a><a name="setbitmap"></a>ボタン::ビットマップを設定します。

新しいビットマップをボタンに関連付けるには、このメンバー関数を呼び出します。

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>パラメーター

*hビットマップ*<br/>
ビットマップのハンドル。

### <a name="return-value"></a>戻り値

ボタンに以前関連付けられたビットマップのハンドル。

### <a name="remarks"></a>解説

ビットマップは、既定でボタンの面の中央に自動的に配置されます。 ビットマップがボタンに対して大きすぎる場合は、どちらかの側でクリップされます。 次のような他の配置オプションを選択できます。

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)ボタンごとに 4 つのビットマップを使用`SetBitmap`するのとは異なり、ボタンごとに 1 つのビットマップしか使用できません。 ボタンを押すと、ビットマップが右下にシフトするように見えます。

ビットマップを使用し終わったら、そのビットマップを解放する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttonsetbuttonstyle"></a><a name="setbuttonstyle"></a>ボタン::セットボタンスタイル

ボタンのスタイルを変更します。

```
void SetButtonStyle(
    UINT nStyle,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*nStyle*<br/>
ボタンの[スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)を指定します。

*引き出し*<br/>
ボタンを再描画するかどうかを指定します。 0 以外の値は、ボタンを再描画します。 0 の値を指定しても、ボタンは再描画されません。 ボタンはデフォルトで再描画されます。

### <a name="remarks"></a>解説

メンバー関数`GetButtonStyle`を使用して、ボタン スタイルを取得します。 完全なボタン スタイルの下位ワードは、ボタン固有のスタイルです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttonsetcheck"></a><a name="setcheck"></a>ボタン::セットチェック

ラジオ ボタンまたはチェック ボックスのチェック状態を設定またはリセットします。

```
void SetCheck(int nCheck);
```

### <a name="parameters"></a>パラメーター

*nチェック*<br/>
チェック状態を指定します。 このパラメーターには、次のいずれかを指定できます。

|[値]|意味|
|-----------|-------------|
|BST_UNCHECKED|ボタンの状態をオフに設定します。|
|BST_CHECKED|ボタンの状態をチェック済みに設定します。|
|BST_INDETERMINATE|ボタンの状態を不確定に設定します。 この値は、ボタンにBS_3STATEまたはBS_AUTO3STATEスタイルがある場合にのみ使用できます。|

### <a name="remarks"></a>解説

このメンバー関数は押ボタンには影響しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttonsetcursor"></a><a name="setcursor"></a>ボタン::セットカーソル

新しいカーソルをボタンに関連付けるには、このメンバー関数を呼び出します。

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>パラメーター

*カーソル*<br/>
カーソルのハンドル。

### <a name="return-value"></a>戻り値

ボタンに以前関連付けられたカーソルのハンドル。

### <a name="remarks"></a>解説

カーソルは、デフォルトでボタンの面の中央に自動的に配置されます。 カーソルがボタンに対して大きすぎる場合は、どちらかの側で切り取られる。 次のような他の配置オプションを選択できます。

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)は、ボタンごとに 4 つのビットマップ`SetCursor`を使用するのとは異なり、ボタンごとに 1 つのカーソルのみを使用します。 ボタンを押すと、カーソルが右下にシフトするように見えます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttonsetdropdownstate"></a><a name="setdropdownstate"></a>ボタン::セットドロップダウン状態

現在の分割ボタン コントロールのドロップダウン状態を設定します。

```
BOOL SetDropDownState(BOOL fDropDown);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ドロップダウン*|[in]状態を設定する場合は TRUEBST_DROPDOWNPUSHED。それ以外の場合は FALSE。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

分割ボタン コントロールには、BS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのスタイルがあり、右側にボタンとドロップダウン矢印が表示されます。 詳細については、「ボタン[スタイル](/windows/win32/Controls/button-styles)」を参照してください。 通常、ドロップダウン状態は、ユーザーがドロップダウン矢印をクリックしたときに設定されます。 このメソッドは、コントロールのドロップダウン状態をプログラムで設定するために使います。 ドロップダウン矢印は、状態を示すためにシェーディングされて描画されます。

このメソッドは、Windows SDK で説明されている[BCM_SETDROPDOWNSTATE](/windows/win32/Controls/bcm-setdropdownstate)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、プログラムによって分割ボタン コントロールにアクセスするために使用される変数*m_splitButton*を定義します。 この変数は、次の例で使用されます。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

次のコード例では、分割ボタン コントロールの状態を、ドロップダウン矢印が押されたことを示すように設定します。

[!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]

## <a name="cbuttonsetelevationrequired"></a><a name="setelevationrequired"></a>CButton::設定標高が必要です

現在のボタン コントロールの状態を`elevation required`に設定します。

```
BOOL SetElevationRequired(BOOL fElevationRequired);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*必要な標高*|[in]状態を設定`elevation required`する場合は TRUE。それ以外の場合は FALSE。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ボタンまたはコマンド リンク コントロールで、高いレベルのセキュリティ アクセス許可を必要とする`elevation required`場合は、コントロールを状態に設定します。 その後、Windows はコントロール上のユーザー アカウント制御 (UAC) シールド アイコンを表示します。 詳細については[、MSDN](https://go.microsoft.com/fwlink/p/?linkid=18507)の「ユーザー アカウント制御」を参照してください。

このメソッドは、Windows SDK で説明されている[BCM_SETSHIELD](/windows/win32/Controls/bcm-setshield)メッセージを送信します。

## <a name="cbuttonseticon"></a><a name="seticon"></a>ボタン::セットアイコン

新しいアイコンをボタンに関連付けるには、このメンバー関数を呼び出します。

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*Hicon*<br/>
アイコンのハンドル。

### <a name="return-value"></a>戻り値

ボタンに以前関連付けられたアイコンのハンドル。

### <a name="remarks"></a>解説

アイコンは、既定でボタンの面の中央に自動的に配置されます。 アイコンがボタンに対して大きすぎる場合は、いずれかの側でクリップされます。 次のような他の配置オプションを選択できます。

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

[CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)ボタンごとに 4 つのビットマップを使用`SetIcon`するのとは異なり、ボタンごとに 1 つのアイコンしか使用できません。 ボタンを押すと、アイコンが右下にシフトして表示されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttonsetimagelist"></a><a name="setimagelist"></a>ボタン::セットイメージリスト

`CButton`オブジェクトのイメージ リストを設定します。

```
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>パラメーター

*ボタンイメージリスト*<br/>
新しいイメージ リストへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK の[ボタン](/windows/win32/controls/buttons)セクションで説明されているように、BCM_SETIMAGELIST メッセージの機能をエミュレートします。

## <a name="cbuttonsetnote"></a><a name="setnote"></a>ボタン::セットノート

現在のコマンド リンク コントロールの注記テキストを設定します。

```
BOOL SetNote(LPCTSTR lpszNote);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpsz注*|[in]コマンド リンク コントロールのメモ テキストとして設定される Unicode 文字列へのポインター。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_COMMANDLINKまたはBS_DEFCOMMANDLINKのコントロールでのみ使用します。

このメソッドは、Windows SDK に記載されている[BCM_SETNOTE](/windows/win32/Controls/bcm-setnote)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、コマンド リンク コントロールにプログラムでアクセスするために使用される変数*m_cmdLink*を定義します。 この変数は、次の例で使用されます。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

コマンド リンク コントロールのノート テキストを設定するコード例を次に示します。

[!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]

## <a name="cbuttonsetsplitglyph"></a><a name="setsplitglyph"></a>ボタン::セットスプリットグリフ

指定したグリフを現在の分割ボタン コントロールに関連付けます。

```
BOOL SetSplitGlyph(TCHAR chGlyph);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*chグリフ*|[in]分割ボタンのドロップダウン矢印として使用するグリフを指定する文字。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

グリフとは、特定のフォントの文字を物理的に表現したものです。 *chGlyph*パラメーターはグリフとして使用されず、システム定義のグリフのセットからグリフを選択するために使用されます。 既定のドロップダウン矢印グリフは文字 '6' で指定され、Unicode 文字のブラック ダウン ポインティング トライアングル (U+25BC) に似ています。

このメソッドは、BCSIF_GLYPH`mask`フラグを使用して[BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体の`himlGlyph`メンバーを初期化し *、chGlyph*パラメーターを持つメンバーを初期化し、Windows SDK で説明されている[BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo)メッセージでその構造体を送信します。

## <a name="cbuttonsetsplitimagelist"></a><a name="setsplitimagelist"></a>ボタン::セットスプリットイメージリスト

[イメージ リスト](../../mfc/reference/cimagelist-class.md)を現在の分割ボタン コントロールに関連付けます。

```
BOOL SetSplitImageList(CImageList* pSplitImageList);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*イメージリスト*|[in]現在の分割ボタン コントロールに割り当てる[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトへのポインター。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

このメソッドは、BUTTON_SPLITINFO`mask`[構造体の](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)メンバーを BCSIF_IMAGE フラグを使用して`himlGlyph`、メンバーを*pSplitImageList*パラメーターで初期化し、Windows SDK で説明されている[BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo)メッセージでその構造体を送信します。

## <a name="cbuttonsetsplitinfo"></a><a name="setsplitinfo"></a>ボタン::セットスプリットインフォ

Windows が現在の分割ボタン コントロールを描画する方法を決定するパラメーターを指定します。

```
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Pinfo*|[in]現在の分割ボタン コントロールを定義する[BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体へのポインター。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

このメソッドは、Windows SDK で説明されている[BCM_SETSPLITINFO](/windows/win32/Controls/bcm-setsplitinfo)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_splitButton`プログラムによって分割ボタン コントロールにアクセスするために使用される変数 を定義します。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

次のコード例では、分割ボタンのドロップダウン矢印に使用されるグリフを変更します。 この例では、アップポイントの三角形グリフをデフォルトの下向き三角形のグリフに置き換えます。 表示されるグリフは、`himlGlyph``BUTTON_SPLITINFO`構造体のメンバーに指定する文字によって異なります。 下向きの三角形グリフは文字 '6' で指定され、上向きの三角形グリフは文字 '5' で指定されます。 比較については、便利な[メソッドを参照](#setsplitglyph)してください。

[!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]

## <a name="cbuttonsetsplitsize"></a><a name="setsplitsize"></a>ボタン::セットスプリットサイズ

現在の分割ボタン コントロールのドロップダウン コンポーネントの外接する四角形を設定します。

```
BOOL SetSplitSize(LPSIZE pSize);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Psize*|[in]外接する四角形を記述する[SIZE](/windows/win32/api/windef/ns-windef-size)構造体へのポインター。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

分割ボタン コントロールを展開すると、リスト コントロールやページャー コントロールなどのドロップダウン コンポーネントを表示できます。 このメソッドは、ドロップダウン コンポーネントを含む外接する四角形のサイズを指定します。

このメソッドは、BCSIF_SIZE`mask`フラグを使用して[BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体の`size`メンバーを初期化し *、pSize*パラメーターを持つメンバーを初期化し、Windows SDK で説明されている[BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo)メッセージでその構造体を送信します。

### <a name="example"></a>例

次のコード例では、`m_splitButton`プログラムによって分割ボタン コントロールにアクセスするために使用される変数 を定義します。 この変数は、次の例で使用されます。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

次のコード例では、分割ボタンのドロップダウン矢印のサイズを 2 倍にします。

[!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]

## <a name="cbuttonsetsplitstyle"></a><a name="setsplitstyle"></a>ボタン::セットスプリットスタイル

現在の分割ボタン コントロールのスタイルを設定します。

```
BOOL SetSplitStyle(UINT uSplitStyle);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*スプリットスタイル*|[in]分割ボタン スタイルのビットごとの組み合わせ。 詳細については[、BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体の`uSplitStyle`メンバーを参照してください。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ボタン スタイルがBS_SPLITBUTTONまたはBS_DEFSPLITBUTTONのコントロールでのみ使用します。

分割ボタンのスタイルは、Windows が分割ボタン アイコンを描画する場合の配置、縦横比、およびグラフィック形式を指定します。 詳細については[、BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体の`uSplitStyle`メンバーを参照してください。

このメソッドは、BCSIF_STYLE`mask`フラグを使用して[BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo)構造体の`uSplitStyle`メンバーを初期化し、メンバーを*uSplitStyle*パラメーターで、Windows SDK で説明されている[BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo)メッセージ内の構造体を送信します。

### <a name="example"></a>例

次のコード例では、`m_splitButton`プログラムによって分割ボタン コントロールにアクセスするために使用される変数 を定義します。

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>例

次のコード例では、分割ボタンのドロップダウン矢印のスタイルを設定します。 BCSS_ALIGNLEFTスタイルではボタンの左側に矢印が表示され、ボタンのサイズを変更してもBCSS_STRETCHスタイルはドロップダウン矢印の縦横比を保持します。

[!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]

## <a name="cbuttonsetstate"></a><a name="setstate"></a>ボタン::セットステート

ボタン コントロールを強調表示するかどうかを設定します。

```
void SetState(BOOL bHighlight);
```

### <a name="parameters"></a>パラメーター

*bハイライト*<br/>
ボタンを強調表示するかどうかを指定します。 0 以外の値はボタンを強調表示します。値を 0 にすると、ハイライトが削除されます。

### <a name="remarks"></a>解説

強調表示は、ボタン コントロールの外側に影響します。 ラジオ ボタンまたはチェック ボックスのチェック状態には影響しません。

ボタン コントロールは、ユーザーがマウスの左ボタンをクリックして押したままにすると、自動的に強調表示されます。 ユーザーがマウス ボタンを離すと、強調表示が削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttonsettextmargin"></a><a name="settextmargin"></a>ボタン::テキストマージンを設定します。

`CButton`オブジェクトのテキストマージンを設定します。

```
BOOL SetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>パラメーター

*マージン*<br/>
新しいテキスト余白へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK の[「ボタン](/windows/win32/controls/buttons)」セクションで説明されているように、BCM_SETTEXTMARGIN メッセージの機能をエミュレートします。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[Cコンボボックスクラス](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic クラス](../../mfc/reference/cstatic-class.md)<br/>
[クラス](../../mfc/reference/cbitmapbutton-class.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)
