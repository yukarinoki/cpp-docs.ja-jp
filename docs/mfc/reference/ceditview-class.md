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
ms.openlocfilehash: e9b7dea980e607c776e2d50c679042c765080fdb
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424423"
---
# <a name="ceditview-class"></a>CEditView クラス

Windows のエディット コントロールの機能を提供するビュー クラスの一種であり、シンプルなテキスト編集エディターを実装できます。

## <a name="syntax"></a>構文

```
class CEditView : public CCtrlView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CEditView:: CEditView](#ceditview)|`CEditView` 型のオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CEditView:: FindText](#findtext)|テキスト内の文字列を検索します。|
|[CEditView:: GetBufferLength](#getbufferlength)|文字バッファーの長さを取得します。|
|[CEditView:: GetEditCtrl](#geteditctrl)|`CEditView` オブジェクト (Windows のエディットコントロール) の `CEdit` 部分へのアクセスを提供します。|
|[CEditView:: GetPrinterFont](#getprinterfont)|現在のプリンターのフォントを取得します。|
|[CEditView:: GetSelectedText](#getselectedtext)|現在のテキスト選択を取得します。|
|[CEditView:: LockBuffer](#lockbuffer)|バッファーをロックします。|
|[CEditView::P rintInsideRect](#printinsiderect)|指定された四角形の内部にテキストを表示します。|
|[CEditView:: SerializeRaw](#serializeraw)|`CEditView` オブジェクトを生のテキストとしてディスクにシリアル化します。|
|[CEditView:: SetPrinterFont](#setprinterfont)|新しいプリンターフォントを設定します。|
|[CEditView:: SetTabStops](#settabstops)|画面の表示と印刷の両方に対してタブストップを設定します。|
|[CEditView:: UnlockBuffer](#unlockbuffer)|バッファーのロックを解除します。|

### <a name="protected-methods"></a>プロテクト メソッド

|Name|Description|
|----------|-----------------|
|[CEditView:: OnFindNext](#onfindnext)|次に出現するテキスト文字列を検索します。|
|[CEditView:: OnReplaceAll](#onreplaceall)|指定した文字列のすべての出現箇所を新しい文字列に置換します。|
|[CEditView:: OnReplaceSel](#onreplacesel)|現在の選択項目を置き換えます。|
|[CEditView:: OnTextNotFound](#ontextnotfound)|検索操作がそれ以上のテキストと一致しない場合に呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|Description|
|----------|-----------------|
|[CEditView::d Wスタイルの既定値](#dwstyledefault)|`CEditView`型のオブジェクトの既定のスタイル。|

## <a name="remarks"></a>解説

`CEditView` クラスには、次のような追加の関数が用意されています。

- 印刷。

- [検索と置換]。

クラス `CEditView` はクラス `CView`の派生クラスであるため、クラス `CEditView` のオブジェクトはドキュメントおよびドキュメントテンプレートと共に使用できます。

各 `CEditView` コントロールのテキストは、独自のグローバルメモリオブジェクトに保持されます。 アプリケーションには、任意の数の `CEditView` オブジェクトを含めることができます。

上に一覧表示されている機能を含む編集ウィンドウが必要な場合、または単純なテキストエディター機能が必要な場合は、`CEditView` 型のオブジェクトを作成します。 `CEditView` オブジェクトは、ウィンドウのクライアント領域全体を占めることができます。 `CEditView` から独自のクラスを派生させて、基本機能を追加または変更したり、ドキュメントテンプレートに追加できるクラスを宣言したりします。

クラス `CEditView` の既定の実装では、ID_EDIT_SELECT_ALL、ID_EDIT_FIND、ID_EDIT_REPLACE、ID_EDIT_REPEAT、および ID_FILE_PRINT の各コマンドが処理されます。

`CEditView` の既定の文字数の制限は、(1024 \* 1024-1 = 1048575) です。 これは、基になるエディットコントロールの EM_LIMITTEXT 関数を呼び出すことによって変更できます。 ただし、制限は、オペレーティングシステムと編集コントロールの種類 (単一または複数行) によって異なります。 これらの制限の詳細については、「 [EM_LIMITTEXT](/windows/win32/Controls/em-limittext)」を参照してください。

コントロールでこの制限を変更するには、`CEditView` クラスの `OnCreate()` 関数をオーバーライドし、次のコード行を挿入します。

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

`CEditView` 型のオブジェクト (または `CEditView`から派生した型) には、次の制限があります。

- 実際には、表示される内容 (WYSIWYG) を実装していない `CEditView` ます。 画面上で読みやすさと印刷出力を一致させるかどうかを選択できます。 `CEditView` は、画面の読みやすさを選択します。

- `CEditView` は、1つのフォントでのみテキストを表示できます。 特殊文字の書式設定はサポートされていません。 機能の詳細については、「クラス[CRichEditView](../../mfc/reference/cricheditview-class.md) 」を参照してください。

- `CEditView` に含めることができるテキストの量は制限されています。 制限は、`CEdit` コントロールと同じです。

`CEditView`の詳細については、「 [MFC で使用できる派生ビュークラス](../../mfc/derived-view-classes-available-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

##  <a name="ceditview"></a>CEditView:: CEditView

`CEditView` 型のオブジェクトを構築します。

```
CEditView();
```

### <a name="remarks"></a>解説

オブジェクトを構築した後は、エディットコントロールを使用する前に[CWnd:: Create](../../mfc/reference/cwnd-class.md#create)関数を呼び出す必要があります。 `CEditView` からクラスを派生させ、`CWinApp::AddDocTemplate`を使用してテンプレートに追加した場合、フレームワークは、このコンストラクターと `Create` 関数の両方を呼び出します。

##  <a name="dwstyledefault"></a>CEditView::d Wスタイルの既定値

`CEditView` オブジェクトの既定のスタイルを格納します。

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>解説

この静的メンバーを `Create` 関数の*dwStyle*パラメーターとして渡して、`CEditView` オブジェクトの既定のスタイルを取得します。

##  <a name="findtext"></a>CEditView:: FindText

`FindText` 関数を呼び出して、`CEditView` オブジェクトのテキストバッファーを検索します。

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
検索の方向を指定します。 TRUE の場合、検索方向はバッファーの末尾に向かっています。 FALSE の場合、検索方向はバッファーの先頭に向かっています。

*bCase*<br/>
検索で大文字と小文字を区別するかどうかを指定します。 TRUE の場合、検索では大文字と小文字が区別されます。 FALSE の場合、検索では大文字と小文字が区別されません。

### <a name="return-value"></a>戻り値

検索テキストが見つかった場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、バッファー内のテキストで、 *lpszFind*で指定されたテキストを検索します。このとき、現在の選択範囲から、 *bnext*で指定した方向に、 *bnext*で大文字小文字の区別を指定します。 テキストが見つかった場合は、選択範囲を検出されたテキストに設定し、0以外の値を返します。 テキストが見つからない場合、この関数は0を返します。

`FindText`を呼び出す `OnFindNext`をオーバーライドしない限り、通常は `FindText` 関数を呼び出す必要はありません。

##  <a name="getbufferlength"></a>CEditView:: GetBufferLength

このメンバー関数を呼び出して、エディットコントロールのバッファーに現在格納されている文字数を取得します (null 終端文字は含まれません)。

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>戻り値

バッファー内の文字列の長さ。

##  <a name="geteditctrl"></a>CEditView:: GetEditCtrl

`GetEditCtrl` を呼び出して、edit ビューで使用される編集コントロールへの参照を取得します。

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>戻り値

`CEdit` オブジェクトへの参照です。

### <a name="remarks"></a>解説

このコントロールの型は[CEdit](../../mfc/reference/cedit-class.md)であるため、`CEdit` メンバー関数を使用して、Windows のエディットコントロールを直接操作できます。

> [!CAUTION]
>  `CEdit` オブジェクトを使用すると、基になる Windows エディットコントロールの状態を変更できます。 たとえば、エディットコントロールと印刷の両方で使用するためにこれらの設定を `CEditView` キャッシュするため、では、 [CEdit:: SetTabStops](../../mfc/reference/cedit-class.md#settabstops)関数を使用してタブ設定を変更しないようにする必要があります。 代わりに、 [CEditView:: SetTabStops](#settabstops)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

##  <a name="getprinterfont"></a>CEditView:: GetPrinterFont

`GetPrinterFont` を呼び出して、現在のプリンターのフォントを説明する[CFont](../../mfc/reference/cfont-class.md)オブジェクトへのポインターを取得します。

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>戻り値

現在のプリンターのフォントを指定する `CFont` オブジェクトへのポインター。プリンターフォントが設定されていない場合は NULL です。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。

### <a name="remarks"></a>解説

プリンターフォントが設定されていない場合、`CEditView` クラスの既定の印刷動作は、表示に使用されるフォントと同じフォントを使用して印刷されます。

現在のプリンターのフォントを確認するには、この関数を使用します。 必要なプリンタフォントでない場合は、 [CEditView:: SetPrinterFont](#setprinterfont)を使用して変更します。

##  <a name="getselectedtext"></a>CEditView:: GetSelectedText

選択したテキストを選択範囲の末尾まで、または選択範囲内の最初のキャリッジリターン文字の前にある文字を `CString` オブジェクトにコピーするには、`GetSelectedText` を呼び出します。

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>パラメーター

*strResult*<br/>
選択されたテキストを受け取る `CString` オブジェクトへの参照。

##  <a name="lockbuffer"></a>CEditView:: LockBuffer

このメンバー関数を呼び出して、バッファーへのポインターを取得します。 バッファーを変更することはできません。

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>戻り値

エディットコントロールのバッファーへのポインター。

##  <a name="onfindnext"></a>CEditView:: OnFindNext

*LpszFind* *によって*指定された方向に、 *bnext*で大文字と小文字の区別を指定して、バッファー内のテキスト内で指定したテキストを検索します。

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
検索の方向を指定します。 TRUE の場合、検索方向はバッファーの末尾に向かっています。 FALSE の場合、検索方向はバッファーの先頭に向かっています。

*bCase*<br/>
検索で大文字と小文字を区別するかどうかを指定します。 TRUE の場合、検索では大文字と小文字が区別されます。 FALSE の場合、検索では大文字と小文字が区別されません。

### <a name="remarks"></a>解説

検索は、現在の選択範囲の先頭から開始され、 [FindText](#findtext)の呼び出しによって行われます。 既定の実装では、テキストが見つからない場合、`OnFindNext` は[OnTextNotFound](#ontextnotfound)を呼び出します。

`OnFindNext` をオーバーライドして、`CEditView`派生オブジェクトがテキストを検索する方法を変更します。 `CEditView` は、ユーザーが標準の [検索] ダイアログボックスで [次を検索] ボタンを選択したときに `OnFindNext` を呼び出します。

##  <a name="onreplaceall"></a>CEditView:: OnReplaceAll

`CEditView` は、ユーザーが標準の [置換] ダイアログボックスの [すべて置換] ボタンを選択したときに `OnReplaceAll` を呼び出します。

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
検索テキストを置き換えるテキスト。

*bCase*<br/>
検索で大文字と小文字を区別するかどうかを指定します。 TRUE の場合、検索では大文字と小文字が区別されます。 FALSE の場合、検索では大文字と小文字が区別されません。

### <a name="remarks"></a>解説

`OnReplaceAll` は、 *lpszFind*で指定されたテキストのバッファー内のテキストを検索します。 *bcase*では大文字と小文字が区別されます。 検索は、現在の選択範囲の先頭から開始されます。 検索テキストが見つかるたびに、この関数は、テキストの出現箇所を*Lpszreplace*によって指定されたテキストに置き換えます。 検索は、 [FindText](#findtext)を呼び出すことによって行われます。 既定の実装では、テキストが見つからない場合に[OnTextNotFound](#ontextnotfound)が呼び出されます。

現在の選択範囲が*lpszFind*と一致しない場合、選択は*lpszFind*によって指定されたテキストが最初に出現する位置に更新され、置換は実行されません。 これにより、ユーザーは、選択範囲が置換対象のテキストと一致しない場合に実行しようとしていることを確認できます。

`OnReplaceAll` をオーバーライドして、`CEditView`派生オブジェクトによるテキストの置換方法を変更します。

##  <a name="onreplacesel"></a>CEditView:: OnReplaceSel

`CEditView` は、ユーザーが標準の [置換] ダイアログボックスで [置換] ボタンを選択したときに `OnReplaceSel` を呼び出します。

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
検索の方向を指定します。 TRUE の場合、検索方向はバッファーの末尾に向かっています。 FALSE の場合、検索方向はバッファーの先頭に向かっています。

*bCase*<br/>
検索で大文字と小文字を区別するかどうかを指定します。 TRUE の場合、検索では大文字と小文字が区別されます。 FALSE の場合、検索では大文字と小文字が区別されません。

*lpszReplace*<br/>
見つかったテキストを置き換えるテキスト。

### <a name="remarks"></a>解説

選択範囲を置換した後、この関数は、 *lpszFind*によって指定されたテキストが次に出現する位置を、 *bnext*によって指定された方向で検索します。 *bnext*では大文字と小文字を区別します。 検索は、 [FindText](#findtext)を呼び出すことによって行われます。 テキストが見つからない場合は、 [OnTextNotFound](#ontextnotfound)が呼び出されます。

`OnReplaceSel` をオーバーライドして、選択したテキストを `CEditView`派生オブジェクトで置き換える方法を変更します。

##  <a name="ontextnotfound"></a>CEditView:: OnTextNotFound

Windows 関数 `MessageBeep`を呼び出す既定の実装を変更するには、この関数をオーバーライドします。

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>パラメーター

*lpszFind*<br/>
検索するテキスト。

##  <a name="printinsiderect"></a>CEditView::P rintInsideRect

*RectLayout*で指定された四角形のテキストを印刷するには、`PrintInsideRect` を呼び出します。

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンターデバイスコンテキストへのポインター。

*rectLayout*<br/>
テキストが表示される四角形を指定する、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](/windows/win32/api/windef/ns-windef-rect)への参照。

*nIndexStart*<br/>
表示される最初の文字のバッファー内のインデックス。

*nIndexStop*<br/>
レンダリングされる最後の文字の後に続く文字のバッファー内のインデックス。

### <a name="return-value"></a>戻り値

印刷される次の文字のインデックス (つまり、最後に描画された文字の後の文字)。

### <a name="remarks"></a>解説

`CEditView` コントロールにスタイル ES_AUTOHSCROLL がない場合、テキストはレンダリング四角形内に折り返されます。 コントロールのスタイルが ES_AUTOHSCROLL の場合、テキストは四角形の右端でクリップされます。

*RectLayout*オブジェクトの `rect.bottom` 要素が変更され、四角形のディメンションで、テキストによって占有されている元の四角形の部分が定義されます。

##  <a name="serializeraw"></a>CEditView:: SerializeRaw

`SerializeRaw` を呼び出して、`CArchive` オブジェクトが `CEditView` オブジェクト内のテキストをテキストファイルに読み取りまたは書き込みます。

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*金*<br/>
シリアル化されたテキストを格納する `CArchive` オブジェクトへの参照。

### <a name="remarks"></a>解説

`SerializeRaw` は `CEditView`の内部 `Serialize` 実装とは異なります。これは、オブジェクトの説明データを前に記述することなく、テキストのみを読み書きすることです。

##  <a name="setprinterfont"></a>CEditView:: SetPrinterFont

`SetPrinterFont` を呼び出して、プリンターフォントを*Pfont*によって指定されたフォントに設定します。

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
`CFont`型のオブジェクトへのポインター。 NULL の場合、印刷に使用されるフォントは、表示フォントに基づいています。

### <a name="remarks"></a>解説

ビューで常に特定のフォントを印刷に使用する場合は、クラスの `OnPreparePrinting` 関数に `SetPrinterFont` の呼び出しを含めます。 この仮想関数は印刷が行われる前に呼び出されるため、フォントの変更はビューの内容が印刷される前に行われます。

##  <a name="settabstops"></a>CEditView:: SetTabStops

この関数を呼び出して、表示と印刷に使用するタブストップを設定します。

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>パラメーター

*nTabStops*<br/>
各タブストップの幅 (ダイアログ単位)。

### <a name="remarks"></a>解説

タブストップの幅は1つしかサポートされていません。 (`CEdit` オブジェクトは、複数のタブ幅をサポートしています)。幅はダイアログ単位です。これは、印刷時または表示時に使用されるフォントの平均的な文字幅の 1 ~ 4 (大文字と小文字のアルファベット文字に基づく) に相当します。 `CEditView` はタブストップの値をキャッシュする必要があるため、`CEdit::SetTabStops` は使用しないでください。

この関数は、呼び出されたオブジェクトのタブのみを変更します。 アプリケーション内の各 `CEditView` オブジェクトのタブストップを変更するには、各オブジェクトの `SetTabStops` 関数を呼び出します。

### <a name="example"></a>例

このコード片では、コントロールが使用するフォントを慎重に測定することで、コントロールのタブストップを4番目のすべての文字に設定します。

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

##  <a name="unlockbuffer"></a>CEditView:: UnlockBuffer

バッファーのロックを解除するには、このメンバー関数を呼び出します。

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>解説

[Lockbuffer](#lockbuffer)によって返されたポインターの使用が完了したら、`UnlockBuffer` を呼び出します。

## <a name="see-also"></a>参照

[MFC サンプル SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView クラス](../../mfc/reference/cricheditview-class.md)
