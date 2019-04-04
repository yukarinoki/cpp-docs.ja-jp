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
ms.openlocfilehash: 3ab276e83e8642aa5de2fd96305cb6d7b648fc40
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781238"
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
|[CEditView::CEditView](#ceditview)|`CEditView` 型のオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CEditView::FindText](#findtext)|テキスト内の文字列を検索します。|
|[CEditView::GetBufferLength](#getbufferlength)|文字バッファーの長さを取得します。|
|[CEditView::GetEditCtrl](#geteditctrl)|アクセスできるように、`CEdit`の部分を`CEditView`(、Windows コントロールの編集) オブジェクト。|
|[CEditView::GetPrinterFont](#getprinterfont)|現在のプリンター フォントを取得します。|
|[CEditView::GetSelectedText](#getselectedtext)|選択されているテキストを取得します。|
|[CEditView::LockBuffer](#lockbuffer)|バッファーをロックします。|
|[CEditView::PrintInsideRect](#printinsiderect)|指定した四角形内のテキストをレンダリングします。|
|[CEditView::SerializeRaw](#serializeraw)|シリアル化、`CEditView`未加工のテキストとしてディスクにオブジェクト。|
|[CEditView::SetPrinterFont](#setprinterfont)|新しいプリンター フォントを設定します。|
|[CEditView::SetTabStops](#settabstops)|タブの画面表示と印刷の両方の位置を設定します。|
|[CEditView::UnlockBuffer](#unlockbuffer)|バッファーのロックを解除します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CEditView::OnFindNext](#onfindnext)|テキスト文字列の次の出現箇所を検索します。|
|[CEditView::OnReplaceAll](#onreplaceall)|指定された文字列のすべての出現箇所を新しい文字列に置き換えます。|
|[CEditView::OnReplaceSel](#onreplacesel)|現在の選択範囲を置き換えます。|
|[CEditView::OnTextNotFound](#ontextnotfound)|さらに、テキストを照合する検索操作が失敗したときに呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CEditView::dwStyleDefault](#dwstyledefault)|既定の型のオブジェクトのスタイル`CEditView`します。|

## <a name="remarks"></a>Remarks

`CEditView`クラスには、次の追加機能が用意されています。

- 印刷します。

- 検索し、置換します。

クラス`CEditView`クラスの派生クラスは、 `CView`、クラスのオブジェクト`CEditView`ドキュメントおよびドキュメント テンプレートで使用できます。

各`CEditView`コントロールのテキストは独自のグローバル メモリ オブジェクトに保持されます。 アプリケーションは、任意の数を持つことができます`CEditView`オブジェクト。

型のオブジェクトを作成する`CEditView`上の一覧に追加された機能を備えた編集ウィンドウをする場合、または単純なテキスト エディター機能を使用する場合。 A`CEditView`オブジェクトは、ウィンドウの全体のクライアント領域を占有できます。 独自のクラスを派生`CEditView`、基本機能を追加するか、ドキュメント テンプレートに追加できるクラスを宣言します。

クラスの既定の実装`CEditView`次のコマンドを処理します。ID_EDIT_SELECT_ALL、ID_EDIT_FIND、ID_EDIT_REPLACE、ID_EDIT_REPEAT、および ID_FILE_PRINT します。

既定の文字制限`CEditView`は (1024 \* 1024-1 = 1048575)。 これは、基になるエディット コントロールの EM_LIMITTEXT 関数を呼び出すことによって変更できます。 ただし、制限は、オペレーティング システムによって異なりますの種類の編集コントロール (1 つまたは複数行)。 これらの制限に関する詳細については、[EM_LIMITTEXT](/windows/desktop/Controls/em-limittext)を参照してください。

コントロールでは、この制限を変更する、`OnCreate()`関数を`CEditView`クラスし、次のコード行を挿入します。

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

型のオブジェクト`CEditView`(またはから派生した型の`CEditView`)、次の制限があります。

- `CEditView` true を実装していない表示内容は、取得 (WYSIWYG) を編集します。 選択肢では、画面上の読みやすさと、印刷出力`CEditView`opts 画面読みやすくするためです。

- `CEditView` 1 つのフォントだけにテキストを表示できます。 特殊文字が書式設定はサポートされません。 クラスを参照してください。 [CRichEditView](../../mfc/reference/cricheditview-class.md)の優れた機能です。

- テキストの量、`CEditView`含めることができますが制限されています。 制限は同じである、`CEdit`コントロール。

詳細については`CEditView`を参照してください[派生ビュー クラスで使用できる MFC](../../mfc/derived-view-classes-available-in-mfc.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

##  <a name="ceditview"></a>  CEditView::CEditView

`CEditView` 型のオブジェクトを構築します。

```
CEditView();
```

### <a name="remarks"></a>Remarks

オブジェクトを構築後に呼び出す必要がある、 [cwnd::create](../../mfc/reference/cwnd-class.md#create)エディット コントロールを使用する前に機能します。 クラスを派生させる場合`CEditView`しを使用して、テンプレートに追加する`CWinApp::AddDocTemplate`、フレームワークがこの両方のコンス トラクターを呼び出すと、`Create`関数。

##  <a name="dwstyledefault"></a>  CEditView::dwStyleDefault

既定のスタイルが含まれています、`CEditView`オブジェクト。

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>Remarks

この静的メンバーとして渡す、 *dwStyle*のパラメーター、`Create`の既定のスタイルを取得する関数、`CEditView`オブジェクト。

##  <a name="findtext"></a>  CEditView::FindText

呼び出す、`FindText`を検索する関数、`CEditView`オブジェクトのテキスト バッファー。

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszFind*<br/>
検索するテキスト。

*bNext*<br/>
検索の方向を指定します。 TRUE の場合、検索の方向は、バッファーの末尾方向です。 FALSE の場合、検索の方向は、バッファーの先頭方向です。

*置き換えた*<br/>
検索は大文字小文字を区別するかどうかを指定します。 TRUE の場合、検索は大文字小文字が区別されます。 FALSE の場合は、検索は大文字小文字が区別されません。

### <a name="return-value"></a>戻り値

検索テキストが見つかった場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数で指定されたテキストのバッファー内のテキストの検索*されて*を開始位置で指定された方向で現在の選択として*bNext*で指定された大文字小文字の区別を使用して*置き換えた*します。 テキストが見つかった場合は、見つかったテキストを選択範囲を設定し、0 以外の値を返します。 テキストが見つからない場合は、0 を返します。

通常必要はありませんを呼び出す、`FindText`関数をオーバーライドする場合を除き、 `OnFindNext`、呼び出す`FindText`します。

##  <a name="getbufferlength"></a>  CEditView::GetBufferLength

Null 終端文字を含まない、編集コントロールのバッファーの現在の文字数を取得するには、このメンバー関数を呼び出します。

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>戻り値

バッファー内の文字列の長さ。

##  <a name="geteditctrl"></a>  CEditView::GetEditCtrl

呼び出す`GetEditCtrl`編集ビューで使用される編集コントロールへの参照を取得します。

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>戻り値

`CEdit` オブジェクトへの参照。

### <a name="remarks"></a>Remarks

このコントロールは、型の[CEdit](../../mfc/reference/cedit-class.md)を使用して直接 Windows エディット コントロールを操作するため、`CEdit`メンバー関数。

> [!CAUTION]
>  使用して、`CEdit`オブジェクトの編集コントロールを基になる Windows の状態を変更できます。 使用してタブの設定を変更するはいないなど、 [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops)ために機能`CEditView`エディット コントロールと印刷の両方に使用するため、これらの設定をキャッシュします。 代わりに、 [CEditView::SetTabStops](#settabstops)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

##  <a name="getprinterfont"></a>  CEditView::GetPrinterFont

呼び出す`GetPrinterFont`へのポインターを取得する、 [CFont](../../mfc/reference/cfont-class.md)の現在のプリンター フォントを表すオブジェクト。

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>戻り値

ポインター、`CFont`現在のプリンターのフォントを指定するオブジェクトプリンターのフォントが設定されていない場合は NULL です。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。

### <a name="remarks"></a>Remarks

プリンターのフォントが設定されていないかどうか、既定の動作の印刷、`CEditView`クラスは、同じ表示に使用されるフォントを使用して印刷します。

現在のプリンター フォントを決定するのにには、この関数を使用します。 使用して、目的のプリンターのフォントでない場合は場合、[なかったとき](#setprinterfont)を変更します。

##  <a name="getselectedtext"></a>  CEditView::GetSelectedText

呼び出す`GetSelectedText`に選択したテキストをコピーする、`CString`選択または選択範囲の先頭のキャリッジ リターン文字の直前の文字の末尾までのオブジェクト。

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>パラメーター

*strResult*<br/>
参照、`CString`選択したテキストを受信するオブジェクト。

##  <a name="lockbuffer"></a>  CEditView::LockBuffer

バッファーへのポインターを取得するには、このメンバー関数を呼び出します。 バッファーは変更しないでください。

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>戻り値

編集コントロールのバッファーへのポインター。

##  <a name="onfindnext"></a>  CEditView::OnFindNext

指定したテキスト バッファーのテキストを検索*されて*で指定された方向で*bNext*で指定された大文字小文字を区別*置き換えた*します。

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>パラメーター

*lpszFind*<br/>
検索するテキスト。

*bNext*<br/>
検索の方向を指定します。 TRUE の場合、検索の方向は、バッファーの末尾方向です。 FALSE の場合、検索の方向は、バッファーの先頭方向です。

*置き換えた*<br/>
検索は大文字小文字を区別するかどうかを指定します。 TRUE の場合、検索は大文字小文字が区別されます。 FALSE の場合は、検索は大文字小文字が区別されません。

### <a name="remarks"></a>Remarks

検索は、現在の選択範囲の先頭に開始されへの呼び出しによって行われます[FindText](#findtext)します。 既定の実装で`OnFindNext`呼び出し[見つからなかったとき](#ontextnotfound)テキストが見つからない場合。

オーバーライド`OnFindNext`方法を変更する、 `CEditView`-派生オブジェクトがテキストを検索します。 `CEditView` 呼び出し`OnFindNext`ユーザーが標準の検索 ダイアログ ボックスで、次を検索 ボタンを選択したときにします。

##  <a name="onreplaceall"></a>  CEditView::OnReplaceAll

`CEditView` 呼び出し`OnReplaceAll`ユーザーが標準の置換 ダイアログ ボックスで、すべて置換 ボタンを選択するとします。

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>パラメーター

*lpszFind*<br/>
検索するテキスト。

*lpszReplace*<br/>
検索テキストを置換するテキスト。

*置き換えた*<br/>
検索は大文字小文字を区別するかどうかを指定します。 TRUE の場合、検索は大文字小文字が区別されます。 FALSE の場合は、検索は大文字小文字が区別されません。

### <a name="remarks"></a>Remarks

`OnReplaceAll` 指定したテキスト バッファーのテキストを検索*されて*で指定された大文字小文字の区別を*置き換えた*します。 現在の選択範囲の先頭に検索を開始します。 毎回検索テキストが見つかると、この関数で指定されたテキストでその出現するテキストを置換する*見つかる*します。 呼び出しによって、検索が行われます[FindText](#findtext)します。 既定の実装で[見つからなかったとき](#ontextnotfound)テキストが見つからない場合に呼び出されます。

現在の選択範囲が一致しない場合*されて*、選択範囲が更新され、最初に見つかった指定した文字列の*されて*置換が実行されていません。 これにより、ユーザーに選択範囲が置き換えられるテキストと一致しない場合に実行するにはこれを確認できます。

オーバーライド`OnReplaceAll`方法を変更する、 `CEditView`-派生オブジェクトには、テキストが置き換えられます。

##  <a name="onreplacesel"></a>  CEditView::OnReplaceSel

`CEditView` 呼び出し`OnReplaceSel`ユーザーが標準の置換 ダイアログ ボックスで、置換 ボタンを選択するとします。

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>パラメーター

*lpszFind*<br/>
検索するテキスト。

*bNext*<br/>
検索の方向を指定します。 TRUE の場合、検索の方向は、バッファーの末尾方向です。 FALSE の場合、検索の方向は、バッファーの先頭方向です。

*置き換えた*<br/>
検索は大文字小文字を区別するかどうかを指定します。 TRUE の場合、検索は大文字小文字が区別されます。 FALSE の場合は、検索は大文字小文字が区別されません。

*lpszReplace*<br/>
見つかったテキストを置換するテキスト。

### <a name="remarks"></a>Remarks

選択範囲を交換した後この関数は、バッファーで指定されたテキストの次に出現する位置のテキストを検索*されて*で指定された方向で*bNext*、大文字と小文字の区別指定された*置き換えた*します。 呼び出しによって、検索が行われます[FindText](#findtext)します。 テキストが見つからない場合[見つからなかったとき](#ontextnotfound)が呼び出されます。

オーバーライド`OnReplaceSel`方法を変更する、 `CEditView`-派生オブジェクトには、選択したテキストが置き換えられます。

##  <a name="ontextnotfound"></a>  CEditView::OnTextNotFound

この Windows 関数を呼び出す既定の実装を変更するには、この関数をオーバーライド`MessageBeep`します。

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>パラメーター

*lpszFind*<br/>
検索するテキスト。

##  <a name="printinsiderect"></a>  CEditView::PrintInsideRect

呼び出す`PrintInsideRect`で指定された四角形内のテキストを印刷する*rectLayout*します。

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンター デバイス コンテキストへのポインター。

*rectLayout*<br/>
参照を[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](/windows/desktop/api/windef/ns-windef-tagrect)テキストが表示される四角形を指定します。

*nIndexStart*<br/>
表示する最初の文字のバッファー内のインデックスします。

*nIndexStop*<br/>
表示する最後の文字を次の文字のバッファー内のインデックスします。

### <a name="return-value"></a>戻り値

印刷するのには、次の文字のインデックス (最後の文字が表示される文字)。

### <a name="remarks"></a>Remarks

場合、`CEditView`コントロールにスタイル ES_AUTOHSCROLL がない、テキストがレンダリングする四角形内にラップされます。 コントロールにスタイル ES_AUTOHSCROLL がある場合は、四角形の右端にテキストが切り取られます。

`rect.bottom`の要素、 *rectLayout*オブジェクトを変更すると、四角形のサイズ、テキストによって使用されている元の四角形の部分を定義するようにします。

##  <a name="serializeraw"></a>  CEditView::SerializeRaw

呼び出す`SerializeRaw`が、`CArchive`オブジェクトの読み取りまたはテキストを作成、`CEditView`オブジェクトをテキスト ファイル。

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
参照、`CArchive`シリアル化されたテキストを格納するオブジェクトです。

### <a name="remarks"></a>Remarks

`SerializeRaw` 異なる`CEditView`の内部実装の`Serialize`を読み取ってオブジェクトの説明のデータの先頭テキストのみを書き込みます。

##  <a name="setprinterfont"></a>  CEditView::SetPrinterFont

呼び出す`SetPrinterFont`プリンター フォントを指定しているフォントに設定する*pFont*します。

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
型のオブジェクトへのポインター`CFont`します。 NULL の場合は、印刷に使用されるフォントを表示フォントに基づきます。

### <a name="remarks"></a>Remarks

呼び出しを常に特定のフォントを印刷に使用する、表示する場合は、含める`SetPrinterFont`クラスの`OnPreparePrinting`関数。 フォントは、変更、ビューの内容が印刷される前に、印刷が行われる前にこの仮想関数が呼び出されます。

##  <a name="settabstops"></a>  CEditView::SetTabStops

表示および印刷のために使用するタブ ストップを設定するには、この関数を呼び出します。

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>パラメーター

*nTabStops*<br/>
ダイアログ単位で、それぞれのタブ ストップの幅。

### <a name="remarks"></a>Remarks

1 つのタブ ストップ幅のみがサポートされています。 (`CEdit`オブジェクトは、複数のタブ幅をサポートします)。幅は、印刷または表示時に使用するフォントの平均文字幅 (大文字と小文字のアルファベット文字のみに基づく) の 4 分の 1 と同じダイアログ単位。 使用しないようにする`CEdit::SetTabStops`ため`CEditView`タブ ストップの値をキャッシュする必要があります。

この関数は、呼び出されたオブジェクトのタブのみを変更します。 タブを変更する各停止`CEditView`オブジェクトのアプリケーションで、各オブジェクトの`SetTabStops`関数。

### <a name="example"></a>例

このコード フラグメントは、コントロールが使用するフォントを慎重に測定することで、4 文字ごとに、コントロールのタブ ストップを設定します。

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

##  <a name="unlockbuffer"></a>  CEditView::UnlockBuffer

バッファーのロックを解除するには、このメンバー関数を呼び出します。

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>Remarks

呼び出す`UnlockBuffer`によって返されたポインターを使用して完了後[LockBuffer](#lockbuffer)します。

## <a name="see-also"></a>関連項目

[MFC サンプル SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView クラス](../../mfc/reference/cricheditview-class.md)
