---
title: CEditView クラス
ms.date: 11/04/2016
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
ms.openlocfilehash: 8fbb2dc569e675ecff4ce04758a4eced40505bf6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373967"
---
# <a name="ceditview-class"></a>CEditView クラス

Windows のエディット コントロールの機能を提供するビュー クラスの一種であり、シンプルなテキスト編集エディターを実装できます。

## <a name="syntax"></a>構文

```
class CEditView : public CCtrlView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[編集ビュー::CEditビュー](#ceditview)|`CEditView` 型のオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[テキストを見つける](#findtext)|テキスト内の文字列を検索します。|
|[を表示::バッファリングの長さを取得します。](#getbufferlength)|文字バッファーの長さを取得します。|
|[ビュー::取得エディットCtrl](#geteditctrl)|`CEditView`オブジェクト (Windows`CEdit`エディット コントロール) の部分へのアクセスを提供します。|
|[ビュー::取得プリンターフォント](#getprinterfont)|現在のプリンター フォントを取得します。|
|[ビュー::選択されたテキストを取得します。](#getselectedtext)|現在のテキスト選択を取得します。|
|[コントロールビュー::ロックバッファ](#lockbuffer)|バッファーをロックします。|
|[:Pリントインサイドレック](#printinsiderect)|指定された四角形の内部にテキストをレンダリングします。|
|[ビュー::シリアライズロー](#serializeraw)|オブジェクトを`CEditView`ディスクに未加工のテキストとしてシリアル化します。|
|[ビュー::セットプリンターフォント](#setprinterfont)|新しいプリンタフォントを設定します。|
|[ビュー::セットタブストップ](#settabstops)|画面表示と印刷の両方のタブ位置を設定します。|
|[ビュー::ロック解除バッファ](#unlockbuffer)|バッファのロックを解除します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[次の画面を表示します。](#onfindnext)|次に出現するテキスト文字列を検索します。|
|[::すべて置換](#onreplaceall)|指定した文字列のすべての出現箇所を新しい文字列で置き換えます。|
|[::オンコセプセル](#onreplacesel)|現在の選択を置き換えます。|
|[テキストビュー::テキストが見つかりません](#ontextnotfound)|検索操作がそれ以降のテキストと一致しない場合に呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ビュー::dスタイルの既定値](#dwstyledefault)|型`CEditView`のオブジェクトの既定のスタイル。|

## <a name="remarks"></a>解説

この`CEditView`クラスには、次の追加機能が用意されています。

- 印刷。

- 検索して置き換えます。

クラス`CEditView`は派生クラス`CView`であるため、クラス`CEditView`のオブジェクトはドキュメントとドキュメントテンプレートで使用できます。

各`CEditView`コントロールのテキストは、独自のグローバル メモリ オブジェクトに保持されます。 アプリケーションには、任意の数の`CEditView`オブジェクトを含めることができます。

上記の追加機能`CEditView`を持つ編集ウィンドウが必要な場合、またはテキストエディタの簡単な機能を使用する場合は、型のオブジェクトを作成します。 オブジェクト`CEditView`は、ウィンドウのクライアント領域全体を占有できます。 基本機能を追加または`CEditView`変更したり、ドキュメント テンプレートに追加できるクラスを宣言したりするには、独自のクラスを派生させます。

クラス`CEditView`の既定の実装では、ID_EDIT_SELECT_ALL、ID_EDIT_FIND、ID_EDIT_REPLACE、ID_EDIT_REPEAT、およびID_FILE_PRINTのコマンドを処理します。

デフォルトの`CEditView`文字数制限は (1024 \* 1024 - 1 = 1048575) です。 これは、基になるエディット コントロールのEM_LIMITTEXT関数を呼び出すことで変更できます。 ただし、制限はオペレーティング システムと編集コントロールの種類 (単一行または複数行) によって異なります。 これらの制限の詳細については[、「EM_LIMITTEXT」](/windows/win32/Controls/em-limittext)を参照してください。

コントロールでこの制限を変更するには、クラスの関数`OnCreate()`を`CEditView`オーバーライドし、次のコード行を挿入します。

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

型`CEditView`(または から`CEditView`派生した型のオブジェクト) には、次の制限があります。

- `CEditView`あなたが見るものが何を得る(WYSIWYG)編集である真を実装していません。 画面上の読みやすさと一致する印刷出力の間で選択がある`CEditView`場合は、画面の読みやすさを選択します。

- `CEditView`1 つのフォントでテキストを表示できます。 特殊文字の書式設定はサポートされていません。 より大きな機能については、クラス[CRichEditView](../../mfc/reference/cricheditview-class.md)を参照してください。

- a に`CEditView`含めることができるテキストの量は制限されます。 制限は`CEdit`、コントロールの場合と同じです。

詳細については、「 MFC で[使用できる派生ビュー クラス](../../mfc/derived-view-classes-available-in-mfc.md)」を参照してください。 `CEditView`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="ceditviewceditview"></a><a name="ceditview"></a>編集ビュー::CEditビュー

`CEditView` 型のオブジェクトを構築します。

```
CEditView();
```

### <a name="remarks"></a>解説

オブジェクトを構築した後、編集コントロールを使用する前に[CWnd::Create](../../mfc/reference/cwnd-class.md#create)関数を呼び出す必要があります。 から`CEditView`クラスを派生し、それをテンプレートに追加`CWinApp::AddDocTemplate`する場合、フレームワークはこのコンストラクターと関数の両方を`Create`呼び出します。

## <a name="ceditviewdwstyledefault"></a><a name="dwstyledefault"></a>ビュー::dスタイルの既定値

オブジェクトの既定のスタイルを`CEditView`格納します。

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>解説

この静的メンバーを`Create`関数の*dwStyle*パラメーターとして渡して、オブジェクトの既定の`CEditView`スタイルを取得します。

## <a name="ceditviewfindtext"></a><a name="findtext"></a>テキストを見つける

オブジェクトの`FindText`テキスト バッファーを`CEditView`検索する関数を呼び出します。

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
検索するテキスト。

*Bnext*<br/>
検索の方向を指定します。 TRUE の場合、検索方向はバッファーの末尾に向かっています。 FALSE の場合、検索方向はバッファーの先頭に向かっています。

*bCase*<br/>
検索で大文字と小文字を区別するかどうかを指定します。 TRUE の場合、検索では大文字と小文字が区別されます。 FALSE の場合、検索では大文字と小文字が区別されません。

### <a name="return-value"></a>戻り値

検索テキストが見つかった場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、バッファ内のテキストを検索し、現在の選択から始めて *、bNext*で指定された方向に、および*bCase*で指定された大文字と小文字の区別を使用して*lpszFind*で指定されたテキストを検索します。 テキストが見つかった場合は、選択対象を見つかったテキストに設定し、0 以外の値を返します。 テキストが見つからない場合、関数は 0 を返します。

通常は、`FindText``OnFindNext`をオーバーライドしない限り、関数を呼び出す`FindText`必要はありません。

## <a name="ceditviewgetbufferlength"></a><a name="getbufferlength"></a>を表示::バッファリングの長さを取得します。

このメンバー関数を呼び出して、現在エディット コントロールのバッファーに含まれる文字数を取得します。

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>戻り値

バッファー内の文字列の長さ。

## <a name="ceditviewgeteditctrl"></a><a name="geteditctrl"></a>ビュー::取得エディットCtrl

エディ`GetEditCtrl`ット ビューで使用されるエディット コントロールへの参照を取得するために呼び出します。

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>戻り値

`CEdit` オブジェクトへの参照です。

### <a name="remarks"></a>解説

このコントロールは[CEdit](../../mfc/reference/cedit-class.md)型なので、メンバー関数を使用して Windows エディ`CEdit`ット コントロールを直接操作できます。

> [!CAUTION]
> オブジェクトを`CEdit`使用すると、基になる Windows エディット コントロールの状態を変更できます。 たとえば[、CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops)関数`CEditView`を使用してタブ設定を変更しないでください。 代わりに[、CEditView::セットタブストップ](#settabstops)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

## <a name="ceditviewgetprinterfont"></a><a name="getprinterfont"></a>ビュー::取得プリンターフォント

現在`GetPrinterFont`のプリンター フォントを記述する[CFont](../../mfc/reference/cfont-class.md)オブジェクトへのポインターを取得する呼び出し。

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>戻り値

現在のプリンター`CFont`フォントを指定するオブジェクトへのポインター。プリンター・フォントが設定されていない場合は NULL。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。

### <a name="remarks"></a>解説

プリンタフォントが設定されていない場合、`CEditView`クラスのデフォルトの印刷動作は、表示に使用したのと同じフォントを使用して印刷することです。

この関数を使用して、現在のプリンタ フォントを確認します。 目的のプリンター フォントでない場合は[、CEditView::SetPrinterFont](#setprinterfont)を使用してフォントを変更します。

## <a name="ceditviewgetselectedtext"></a><a name="getselectedtext"></a>ビュー::選択されたテキストを取得します。

選択`GetSelectedText`したテキストを`CString`オブジェクトにコピーする場合に、選択範囲の先頭の改行文字の前にある文字を呼び出します。

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>パラメーター

*結果*<br/>
選択したテキストを`CString`受け取るオブジェクトへの参照。

## <a name="ceditviewlockbuffer"></a><a name="lockbuffer"></a>コントロールビュー::ロックバッファ

バッファーへのポインターを取得します。 バッファは変更しないでください。

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>戻り値

エディット コントロールのバッファーへのポインター。

## <a name="ceditviewonfindnext"></a><a name="onfindnext"></a>次の画面を表示します。

bNext で指定された方向に *、バッファー*内のテキストを検索し、 *bNext*で指定された方向に*bCase*で指定します。

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
検索するテキスト。

*Bnext*<br/>
検索の方向を指定します。 TRUE の場合、検索方向はバッファーの末尾に向かっています。 FALSE の場合、検索方向はバッファーの先頭に向かっています。

*bCase*<br/>
検索で大文字と小文字を区別するかどうかを指定します。 TRUE の場合、検索では大文字と小文字が区別されます。 FALSE の場合、検索では大文字と小文字が区別されません。

### <a name="remarks"></a>解説

検索は現在の選択範囲の先頭から開始され[、FindText](#findtext)の呼び出しによって実行されます。 既定の実装では、`OnFindNext`テキストが見つからない場合[に OnTextNotFound](#ontextnotfound)を呼び出します。

派生`OnFindNext`オブジェクトがテキストを検索`CEditView`する方法を変更するには、オーバーライドします。 `CEditView`ユーザー`OnFindNext`が標準の [検索] ダイアログ ボックスの [次を検索] ボタンをクリックすると、呼び出されます。

## <a name="ceditviewonreplaceall"></a><a name="onreplaceall"></a>::すべて置換

`CEditView`ユーザー`OnReplaceAll`が標準の [置換] ダイアログ ボックスの [すべて置換] ボタンを選択すると、呼び出されます。

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
検索するテキスト。

*置き換え*<br/>
検索テキストを置き換えるテキスト。

*bCase*<br/>
検索で大文字と小文字を区別するかどうかを指定します。 TRUE の場合、検索では大文字と小文字が区別されます。 FALSE の場合、検索では大文字と小文字が区別されません。

### <a name="remarks"></a>解説

`OnReplaceAll`バッファ内のテキストを検索し、 *bCase*で大文字と小文字を区別して*lpszFind*で指定されたテキストを検索します。 検索は、現在の選択範囲の先頭から開始されます。 検索テキストが見つかるたびに、この関数は、そのテキストの出現を*lpszReplace*で指定されたテキストに置き換えます。 検索は[、FindText](#findtext)への呼び出しを通じて実行されます。 既定の実装では、テキストが見つからない場合に[OnTextNotFound](#ontextnotfound)が呼び出されます。

現在の選択内容が*lpszFind*と一致しない場合、選択内容は*lpszFind*で指定されたテキストの最初の出現箇所に更新され、置換は実行されません。 これにより、置換するテキストと選択が一致しない場合に、これが必要な操作であることをユーザーが確認できます。

派生`OnReplaceAll`オブジェクトがテキストを`CEditView`置き換える方法を変更するには、オーバーライドします。

## <a name="ceditviewonreplacesel"></a><a name="onreplacesel"></a>::オンコセプセル

`CEditView`ユーザー`OnReplaceSel`が標準の [置換] ダイアログ ボックスの [置換] ボタンを選択すると、呼び出されます。

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
検索するテキスト。

*Bnext*<br/>
検索の方向を指定します。 TRUE の場合、検索方向はバッファーの末尾に向かっています。 FALSE の場合、検索方向はバッファーの先頭に向かっています。

*bCase*<br/>
検索で大文字と小文字を区別するかどうかを指定します。 TRUE の場合、検索では大文字と小文字が区別されます。 FALSE の場合、検索では大文字と小文字が区別されません。

*置き換え*<br/>
見つかったテキストを置き換えるテキスト。

### <a name="remarks"></a>解説

選択範囲を置き換えると、この関数は、bNext で指定された方向に *、バッファ*内のテキストを検索し、次に指定されたテキストを*bNext*で指定した*bCase*方向に検索します。 検索は[、FindText](#findtext)への呼び出しを通じて実行されます。 テキストが見つからない場合は[、OnTextNotFound](#ontextnotfound)が呼び出されます。

選択`OnReplaceSel`したテキストを派生オブジェクト`CEditView`で置き換える方法を変更するには、オーバーライドします。

## <a name="ceditviewontextnotfound"></a><a name="ontextnotfound"></a>テキストビュー::テキストが見つかりません

Windows 関数を呼び出す既定の実装を変更するには`MessageBeep`、この関数をオーバーライドします。

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
検索するテキスト。

## <a name="ceditviewprintinsiderect"></a><a name="printinsiderect"></a>:Pリントインサイドレック

`PrintInsideRect` *rectLayout*で指定された四角形内のテキストを印刷する呼び出し。

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンターデバイス コンテキストへのポインター。

*レクトレイアウト*<br/>
テキストを描画する四角形を指定する[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](/windows/win32/api/windef/ns-windef-rect)への参照。

*インデックススタート*<br/>
レンダリングされる最初の文字のバッファー内のインデックス。

*インデックスストップ*<br/>
最後にレンダリングされる文字の後に続く文字のバッファー内のインデックス。

### <a name="return-value"></a>戻り値

次に印刷される文字のインデックス (つまり、最後に表示された文字の後の文字)。

### <a name="remarks"></a>解説

コントロールに`CEditView`スタイル ES_AUTOHSCROLLがない場合、テキストはレンダリング用の四角形内で折り返されます。 コントロールにスタイルがES_AUTOHSCROLLされている場合、テキストは四角形の右端でクリップされます。

`rect.bottom` *rectLayout*オブジェクトの要素が変更され、テキストが占める元の四角形の一部が四角形の寸法によって定義されます。

## <a name="ceditviewserializeraw"></a><a name="serializeraw"></a>ビュー::シリアライズロー

オブジェクト`SerializeRaw`を読み`CArchive`取るか、テキスト ファイルに書`CEditView`き込むオブジェクトを呼び出します。

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
シリアル化された`CArchive`テキストを格納するオブジェクトへの参照。

### <a name="remarks"></a>解説

`SerializeRaw`の内部実装`CEditView``Serialize`とは異なり、オブジェクト記述データの前に書き込みせずにテキストのみを読み書きするという点で異なります。

## <a name="ceditviewsetprinterfont"></a><a name="setprinterfont"></a>ビュー::セットプリンターフォント

`SetPrinterFont` *pFont*で指定されたフォントにプリンタフォントを設定する呼び出し。

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
型`CFont`のオブジェクトへのポインター。 NULL の場合、印刷に使用されるフォントは表示フォントに基づいています。

### <a name="remarks"></a>解説

ビューで常に特定のフォントを使用して印刷する場合は、クラスの`SetPrinterFont``OnPreparePrinting`関数に呼び出しを含めます。 この仮想関数は印刷前に呼び出されるため、ビューの内容が印刷される前にフォントの変更が行われます。

## <a name="ceditviewsettabstops"></a><a name="settabstops"></a>ビュー::セットタブストップ

表示と印刷に使用するタブ ストップを設定します。

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>パラメーター

*nタブストップ*<br/>
各タブストップの幅 (ダイアログ単位)。

### <a name="remarks"></a>解説

タブストップ幅は 1 つだけです。 (`CEdit`オブジェクトは複数のタブ幅をサポートします)。幅はダイアログ単位で、印刷時または表示時に使用されるフォントの平均文字幅の 4 分の 1 に相当します (大文字と小文字の英字のみに基づきます)。 タブストップ値を`CEdit::SetTabStops`キャッシュ`CEditView`する必要があるため、使用しないでください。

この関数は、呼び出されるオブジェクトのタブのみを変更します。 アプリケーションの各`CEditView`オブジェクトのタブストップを変更するには、各オブジェクトの`SetTabStops`関数を呼び出します。

### <a name="example"></a>例

このコードは、コントロールで使用されるフォントを注意深く測定することで、コントロール内のタブ ストップを 4 文字ごとに設定します。

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

## <a name="ceditviewunlockbuffer"></a><a name="unlockbuffer"></a>ビュー::ロック解除バッファ

バッファーのロックを解除するには、このメンバー関数を呼び出します。

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>解説

`UnlockBuffer` [LockBuffer](#lockbuffer)によって返されるポインターを使用して終了した後に呼び出します。

## <a name="see-also"></a>関連項目

[MFC サンプル スーパーパッド](../../overview/visual-cpp-samples.md)<br/>
[クラスを表示します。](../../mfc/reference/cctrlview-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[クラスを表示します。](../../mfc/reference/cctrlview-class.md)<br/>
[クラスを表示します。](../../mfc/reference/cricheditview-class.md)
