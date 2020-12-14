---
description: '詳細情報: CEditView クラス'
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
ms.openlocfilehash: b83b83b90fe530d2615a507d80e2af771397d286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184713"
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
|[CEditView:: CEditView](#ceditview)|`CEditView` 型のオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CEditView:: FindText](#findtext)|テキスト内の文字列を検索します。|
|[CEditView:: GetBufferLength](#getbufferlength)|文字バッファーの長さを取得します。|
|[CEditView:: GetEditCtrl](#geteditctrl)|`CEdit`オブジェクトの部分 `CEditView` (Windows のエディットコントロール) へのアクセスを提供します。|
|[CEditView:: GetPrinterFont](#getprinterfont)|現在のプリンターのフォントを取得します。|
|[CEditView:: GetSelectedText](#getselectedtext)|現在のテキスト選択を取得します。|
|[CEditView:: LockBuffer](#lockbuffer)|バッファーをロックします。|
|[CEditView::P rintInsideRect](#printinsiderect)|指定された四角形の内部にテキストを表示します。|
|[CEditView:: SerializeRaw](#serializeraw)|オブジェクトを `CEditView` 生のテキストとしてディスクにシリアル化します。|
|[CEditView:: SetPrinterFont](#setprinterfont)|新しいプリンターフォントを設定します。|
|[CEditView:: SetTabStops](#settabstops)|画面の表示と印刷の両方に対してタブストップを設定します。|
|[CEditView:: UnlockBuffer](#unlockbuffer)|バッファーのロックを解除します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CEditView:: OnFindNext](#onfindnext)|次に出現するテキスト文字列を検索します。|
|[CEditView:: OnReplaceAll](#onreplaceall)|指定した文字列のすべての出現箇所を新しい文字列に置換します。|
|[CEditView:: OnReplaceSel](#onreplacesel)|現在の選択項目を置き換えます。|
|[CEditView:: OnTextNotFound](#ontextnotfound)|検索操作がそれ以上のテキストと一致しない場合に呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CEditView::d Wスタイルの既定値](#dwstyledefault)|型のオブジェクトの既定のスタイル `CEditView` 。|

## <a name="remarks"></a>解説

クラスには `CEditView` 、次の追加の関数が用意されています。

- 印刷。

- [検索と置換]。

クラス `CEditView` はクラスの派生クラスであるため `CView` 、クラスのオブジェクトは `CEditView` ドキュメントとドキュメントテンプレートで使用できます。

各 `CEditView` コントロールのテキストは、独自のグローバルメモリオブジェクトに保持されます。 アプリケーションには、任意の数のオブジェクトを含めることができ `CEditView` ます。

`CEditView`上に一覧表示されている機能を持つ編集ウィンドウが必要な場合、または単純なテキストエディター機能が必要な場合は、型のオブジェクトを作成します。 オブジェクトは、 `CEditView` ウィンドウのクライアント領域全体を占めることができます。 から独自のクラスを派生させて `CEditView` 、基本機能を追加または変更するか、ドキュメントテンプレートに追加できるクラスを宣言します。

クラスの既定の実装では、 `CEditView` ID_EDIT_SELECT_ALL、ID_EDIT_FIND、ID_EDIT_REPLACE、ID_EDIT_REPEAT、および ID_FILE_PRINT の各コマンドが処理されます。

の既定の文字制限 `CEditView` は、(1024 \* 1024-1 = 1048575) です。 これは、基になるエディットコントロールの EM_LIMITTEXT 関数を呼び出すことによって変更できます。 ただし、制限は、オペレーティングシステムと編集コントロールの種類 (単一または複数行) によって異なります。 これらの制限の詳細については、「 [EM_LIMITTEXT](/windows/win32/Controls/em-limittext)」を参照してください。

コントロールでこの制限を変更するには、 `OnCreate()` クラスの関数をオーバーライド `CEditView` し、次のコード行を挿入します。

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

型 `CEditView` (またはから派生した型) のオブジェクトには `CEditView` 、次の制限があります。

- `CEditView` 実際には、表示される内容 (WYSIWYG) を実際には実装していません。 画面上の読みやすさと印刷出力の一致を選択できる場合は、 `CEditView` 画面の読みやすさを選択します。

- `CEditView` テキストを1つのフォントでのみ表示できます。 特殊文字の書式設定はサポートされていません。 機能の詳細については、「クラス [CRichEditView](../../mfc/reference/cricheditview-class.md) 」を参照してください。

- に含めることができるテキストの量 `CEditView` は制限されています。 制限は、コントロールの場合と同じ `CEdit` です。

の詳細につい `CEditView` ては、「 [MFC で使用できる派生ビュークラス](../../mfc/derived-view-classes-available-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

## <a name="ceditviewceditview"></a><a name="ceditview"></a> CEditView:: CEditView

`CEditView` 型のオブジェクトを構築します。

```
CEditView();
```

### <a name="remarks"></a>解説

オブジェクトを構築した後は、エディットコントロールを使用する前に [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) 関数を呼び出す必要があります。 からクラスを派生させ、 `CEditView` を使用してテンプレートに追加した場合 `CWinApp::AddDocTemplate` 、フレームワークは、このコンストラクターと関数の両方を呼び出し `Create` ます。

## <a name="ceditviewdwstyledefault"></a><a name="dwstyledefault"></a> CEditView::d Wスタイルの既定値

オブジェクトの既定のスタイルを格納 `CEditView` します。

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>解説

オブジェクトの既定のスタイルを取得するには、この静的メンバーを関数の *dwStyle* パラメーターとして渡し `Create` `CEditView` ます。

## <a name="ceditviewfindtext"></a><a name="findtext"></a> CEditView:: FindText

関数を呼び出して、 `FindText` `CEditView` オブジェクトのテキストバッファーを検索します。

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

この関数は、バッファー内のテキストで、 *lpszFind* で指定されたテキストを検索します。このとき、現在の選択範囲から、 *bnext* で指定した方向に、 *bnext* で大文字小文字の区別を指定します。 テキストが見つかった場合は、選択範囲を検出されたテキストに設定し、0以外の値を返します。 テキストが見つからない場合、この関数は0を返します。

`FindText`を呼び出すをオーバーライドしない限り、通常は関数を呼び出す必要はありません `OnFindNext` `FindText` 。

## <a name="ceditviewgetbufferlength"></a><a name="getbufferlength"></a> CEditView:: GetBufferLength

このメンバー関数を呼び出して、エディットコントロールのバッファーに現在格納されている文字数を取得します (null 終端文字は含まれません)。

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>戻り値

バッファー内の文字列の長さ。

## <a name="ceditviewgeteditctrl"></a><a name="geteditctrl"></a> CEditView:: GetEditCtrl

`GetEditCtrl`を呼び出して、edit ビューで使用される編集コントロールへの参照を取得します。

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>戻り値

`CEdit` オブジェクトへの参照です。

### <a name="remarks"></a>解説

このコントロール [の型は](../../mfc/reference/cedit-class.md)、メンバー関数を使用して、Windows のエディットコントロールを直接操作できるようにし `CEdit` ます。

> [!CAUTION]
> オブジェクトを使用すると、 `CEdit` 基になる Windows エディットコントロールの状態を変更できます。 たとえば、では、これらの設定を編集コントロールと印刷の両方で使用できるようにするため、この関数を使用してタブ設定を変更しないように [します](../../mfc/reference/cedit-class.md#settabstops) `CEditView` 。 代わりに、 [CEditView:: SetTabStops](#settabstops)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

## <a name="ceditviewgetprinterfont"></a><a name="getprinterfont"></a> CEditView:: GetPrinterFont

を呼び出して、 `GetPrinterFont` 現在のプリンターのフォントを説明する [CFont](../../mfc/reference/cfont-class.md) オブジェクトへのポインターを取得します。

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>戻り値

`CFont`現在のプリンターのフォントを指定するオブジェクトへのポインター。プリンターフォントが設定されていない場合は NULL です。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。

### <a name="remarks"></a>解説

プリンターフォントが設定されていない場合、クラスの既定の印刷動作 `CEditView` は、表示に使用されるフォントと同じフォントを使用して印刷されます。

現在のプリンターのフォントを確認するには、この関数を使用します。 必要なプリンタフォントでない場合は、 [CEditView:: SetPrinterFont](#setprinterfont) を使用して変更します。

## <a name="ceditviewgetselectedtext"></a><a name="getselectedtext"></a> CEditView:: GetSelectedText

を呼び出して、選択し `GetSelectedText` たテキストを選択 `CString` 範囲の最後まで、または選択範囲内の最初のキャリッジリターン文字の前の文字の前にあるオブジェクトにコピーします。

```cpp
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>パラメーター

*strResult*<br/>
選択された `CString` テキストを受け取るオブジェクトへの参照。

## <a name="ceditviewlockbuffer"></a><a name="lockbuffer"></a> CEditView:: LockBuffer

このメンバー関数を呼び出して、バッファーへのポインターを取得します。 バッファーを変更することはできません。

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>戻り値

エディットコントロールのバッファーへのポインター。

## <a name="ceditviewonfindnext"></a><a name="onfindnext"></a> CEditView:: OnFindNext

*LpszFind**によって* 指定された方向に、 *bnext* で大文字と小文字の区別を指定して、バッファー内のテキスト内で指定したテキストを検索します。

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

検索は、現在の選択範囲の先頭から開始され、 [FindText](#findtext)の呼び出しによって行われます。 既定の実装では、 `OnFindNext` テキストが見つからない場合、は [OnTextNotFound](#ontextnotfound) を呼び出します。

をオーバーライドし `OnFindNext` て、派生オブジェクトがテキストを検索する方法を変更し `CEditView` ます。 `CEditView``OnFindNext`ユーザーが標準の [検索] ダイアログボックスで [次を検索] ボタンを選択したときに、を呼び出します。

## <a name="ceditviewonreplaceall"></a><a name="onreplaceall"></a> CEditView:: OnReplaceAll

`CEditView``OnReplaceAll`ユーザーが標準の [置換] ダイアログボックスの [すべて置換] ボタンを選択したときに、を呼び出します。

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

`OnReplaceAll`*lpszFind* によって指定されたテキストについて、バッファー内のテキストを検索します。 *bcase* では大文字と小文字が区別されます。 検索は、現在の選択範囲の先頭から開始されます。 検索テキストが見つかるたびに、この関数は、テキストの出現箇所を *Lpszreplace* によって指定されたテキストに置き換えます。 検索は、 [FindText](#findtext)を呼び出すことによって行われます。 既定の実装では、テキストが見つからない場合に [OnTextNotFound](#ontextnotfound) が呼び出されます。

現在の選択範囲が *lpszFind* と一致しない場合、選択は *lpszFind* によって指定されたテキストが最初に出現する位置に更新され、置換は実行されません。 これにより、ユーザーは、選択範囲が置換対象のテキストと一致しない場合に実行しようとしていることを確認できます。

をオーバーライドし `OnReplaceAll` て、派生オブジェクトがテキストを置き換える方法を変更し `CEditView` ます。

## <a name="ceditviewonreplacesel"></a><a name="onreplacesel"></a> CEditView:: OnReplaceSel

`CEditView``OnReplaceSel`ユーザーが標準の [置換] ダイアログボックスで [置換] ボタンを選択したときに、を呼び出します。

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

選択範囲を置換した後、この関数は、 *lpszFind* によって指定されたテキストが次に出現する位置を、 *bnext* によって指定された方向で検索します。 *bnext* では大文字と小文字を区別します。 検索は、 [FindText](#findtext)を呼び出すことによって行われます。 テキストが見つからない場合は、 [OnTextNotFound](#ontextnotfound) が呼び出されます。

をオーバーライドして、選択した `OnReplaceSel` `CEditView` テキストを派生オブジェクトで置き換える方法を変更します。

## <a name="ceditviewontextnotfound"></a><a name="ontextnotfound"></a> CEditView:: OnTextNotFound

Windows 関数を呼び出す既定の実装を変更するには、この関数をオーバーライドし `MessageBeep` ます。

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>パラメーター

*lpszFind*<br/>
検索するテキスト。

## <a name="ceditviewprintinsiderect"></a><a name="printinsiderect"></a> CEditView::P rintInsideRect

`PrintInsideRect` *RectLayout* で指定された四角形のテキストを印刷するには、を呼び出します。

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
テキストが表示される四角形を指定する、 [CRect](../../atl-mfc-shared/reference/crect-class.md) オブジェクトまたは [RECT 構造体](/windows/win32/api/windef/ns-windef-rect) への参照。

*nIndexStart*<br/>
表示される最初の文字のバッファー内のインデックス。

*nIndexStop*<br/>
レンダリングされる最後の文字の後に続く文字のバッファー内のインデックス。

### <a name="return-value"></a>戻り値

印刷される次の文字のインデックス (つまり、最後に描画された文字の後の文字)。

### <a name="remarks"></a>解説

コントロールに `CEditView` スタイル ES_AUTOHSCROLL が指定されていない場合、テキストは描画四角形内に折り返されます。 コントロールのスタイルが ES_AUTOHSCROLL の場合、テキストは四角形の右端でクリップされます。

`rect.bottom` *RectLayout* オブジェクトの要素が変更され、四角形のディメンションで、テキストによって占有されている元の四角形の部分が定義されます。

## <a name="ceditviewserializeraw"></a><a name="serializeraw"></a> CEditView:: SerializeRaw

を呼び出して、オブジェクトのテキスト `SerializeRaw` `CArchive` を読み取りまたは `CEditView` テキストファイルに書き込みます。

```cpp
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
シリアル化された `CArchive` テキストを格納するオブジェクトへの参照。

### <a name="remarks"></a>解説

`SerializeRaw` は、 `CEditView` の内部実装とは異なり `Serialize` ます。これは、オブジェクトの説明データを前に記述するのではなく、テキストのみを読み書きします。

## <a name="ceditviewsetprinterfont"></a><a name="setprinterfont"></a> CEditView:: SetPrinterFont

`SetPrinterFont`を呼び出して、プリンターフォントを *pfont* によって指定されたフォントに設定します。

```cpp
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
型のオブジェクトへのポインター `CFont` 。 NULL の場合、印刷に使用されるフォントは、表示フォントに基づいています。

### <a name="remarks"></a>解説

ビューで常に特定のフォントを印刷に使用する場合は、の呼び出しを `SetPrinterFont` クラスの関数に含め `OnPreparePrinting` ます。 この仮想関数は印刷が行われる前に呼び出されるため、フォントの変更はビューの内容が印刷される前に行われます。

## <a name="ceditviewsettabstops"></a><a name="settabstops"></a> CEditView:: SetTabStops

この関数を呼び出して、表示と印刷に使用するタブストップを設定します。

```cpp
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>パラメーター

*nTabStops*<br/>
各タブストップの幅 (ダイアログ単位)。

### <a name="remarks"></a>解説

タブストップの幅は1つしかサポートされていません。 ( `CEdit` オブジェクトは、複数のタブ幅をサポートしています)。幅はダイアログ単位です。これは、印刷時または表示時に使用されるフォントの平均的な文字幅の 1 ~ 4 (大文字と小文字のアルファベット文字に基づく) に相当します。 では、 `CEdit::SetTabStops` `CEditView` タブストップの値をキャッシュする必要があるため、を使用しないでください。

この関数は、呼び出されたオブジェクトのタブのみを変更します。 アプリケーション内の各オブジェクトのタブストップを変更するには `CEditView` 、各オブジェクトの関数を呼び出し `SetTabStops` ます。

### <a name="example"></a>例

このコード片では、コントロールが使用するフォントを慎重に測定することで、コントロールのタブストップを4番目のすべての文字に設定します。

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

## <a name="ceditviewunlockbuffer"></a><a name="unlockbuffer"></a> CEditView:: UnlockBuffer

バッファーのロックを解除するには、このメンバー関数を呼び出します。

```cpp
void UnlockBuffer() const;
```

### <a name="remarks"></a>解説

`UnlockBuffer` [Lockbuffer](#lockbuffer)によって返されたポインターの使用が完了したら、を呼び出します。

## <a name="see-also"></a>関連項目

[MFC サンプル SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView クラス](../../mfc/reference/cricheditview-class.md)
