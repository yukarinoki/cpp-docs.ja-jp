---
title: CEditView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b15d604670ec1c458c6ca8db5b3b4eab51fb8f65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371544"
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
|[CEditView::FindText](#findtext)|テキスト内で文字列を検索します。|  
|[CEditView::GetBufferLength](#getbufferlength)|文字バッファーの長さを取得します。|  
|[CEditView::GetEditCtrl](#geteditctrl)|アクセスできるように、`CEdit`の部分、 `CEditView` (、Windows のエディット コントロール) オブジェクト。|  
|[CEditView::GetPrinterFont](#getprinterfont)|現在のプリンター フォントを取得します。|  
|[CEditView::GetSelectedText](#getselectedtext)|現在のテキスト選択範囲を取得します。|  
|[CEditView::LockBuffer](#lockbuffer)|バッファーをロックします。|  
|[CEditView::PrintInsideRect](#printinsiderect)|指定した四角形内のテキストを表示します。|  
|[CEditView::SerializeRaw](#serializeraw)|シリアル化、`CEditView`未加工のテキストとしてディスクにオブジェクト。|  
|[なかったとき](#setprinterfont)|新しいプリンター フォントを設定します。|  
|[CEditView::SetTabStops](#settabstops)|タブの画面表示と印刷の両方の位置を設定します。|  
|[CEditView::UnlockBuffer](#unlockbuffer)|バッファーのロックを解除します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CEditView::OnFindNext](#onfindnext)|テキスト文字列の次の出現箇所を検索します。|  
|[CEditView::OnReplaceAll](#onreplaceall)|すべての出現する指定された文字列を新しい文字列に置き換えます。|  
|[CEditView::OnReplaceSel](#onreplacesel)|現在の選択項目を置換します。|  
|[CEditView::OnTextNotFound](#ontextnotfound)|さらに、テキストを照合する検索操作が失敗したときに呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CEditView::dwStyleDefault](#dwstyledefault)|既定の型のオブジェクトのスタイル**CEditView です。**|  
  
## <a name="remarks"></a>コメント  
 `CEditView`クラスには、次の追加機能が用意されています。  
  
-   印刷します。  
  
-   検索し、置換します。  
  
 クラス`CEditView`クラスから派生したは`CView`、クラスのオブジェクト`CEditView`ドキュメントおよびドキュメント テンプレートで使用できます。  
  
 各`CEditView`コントロールのテキストを独自のグローバル メモリ オブジェクトに保持します。 アプリケーションは、任意の数を持つことができます`CEditView`オブジェクト。  
  
 型のオブジェクトを作成する`CEditView`編集ウィンドウを上に示した機能機能を追加する場合、または単純なテキスト エディター機能を使用する場合。 A`CEditView`オブジェクトがウィンドウの全体のクライアント領域を占めることができます。 独自のクラスを派生`CEditView`、基本機能を追加するか、ドキュメント テンプレートに追加できるクラスを宣言します。  
  
 クラスの既定の実装`CEditView`次のコマンドを処理します**ID_EDIT_SELECT_ALL**、 **ID_EDIT_FIND**、 **ID_EDIT_REPLACE**、 **。ID_EDIT_REPEAT**、および**ID_FILE_PRINT**です。  
  
 既定の文字制限`CEditView`は (1024 \* 1024-1 = 1048575)。 これを呼び出すことにより変更することができます、 **EM_LIMITTEXT**基になる関数でコントロールを編集します。 ただし、制限は、オペレーティング システムによって異なります、エディット コントロール (1 つまたは複数行) の種類。 これらの制限の詳細については、次を参照してください。 [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607)です。  
  
 コントロールでは、この制限を変更するには、上書き、`OnCreate()`関数を`CEditView`クラスし、次のコード行を挿入します。  
  
 [!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]  
  
 型のオブジェクト`CEditView`(またはから派生した型の`CEditView`)、次の制限があります。  
  
- `CEditView` true を実装していません表示内容は、取得 (WYSIWYG) を編集します。 選択肢では、画面上の読みやすさと、印刷出力`CEditView`画面の読みやすさを選択します。  
  
- `CEditView` 1 つのフォントのみにテキストを表示できます。 特殊文字が書式設定はサポートされません。 クラスを参照して[CRichEditView](../../mfc/reference/cricheditview-class.md)の大きい機能します。  
  
-   テキストの量、`CEditView`含めることができる制限されます。 制限は同じであるとは、`CEdit`コントロール。  
  
 詳細については`CEditView`を参照してください[派生ビュー クラスで使用できる MFC](../../mfc/derived-view-classes-available-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CEditView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="ceditview"></a>  CEditView::CEditView  
 `CEditView` 型のオブジェクトを構築します。  
  
```  
CEditView();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを構築するには、後に呼び出す必要があります、 [cwnd::create](../../mfc/reference/cwnd-class.md#create)エディット コントロールを使用する前に機能します。 クラスを派生する場合`CEditView`しを使用してテンプレートに追加する`CWinApp::AddDocTemplate`、フレームワークが両方このコンス トラクターを呼び出すと**作成**関数。  
  
##  <a name="dwstyledefault"></a>  CEditView::dwStyleDefault  
 既定のスタイルが含まれています、`CEditView`オブジェクト。  
  
```  
static const DWORD dwStyleDefault;  
```  
  
### <a name="remarks"></a>コメント  
 この静的メンバーとして渡す、`dwStyle`のパラメーター、**作成**の既定のスタイルを取得する関数、`CEditView`オブジェクト。  
  
##  <a name="findtext"></a>  CEditView::FindText  
 呼び出す、`FindText`を検索する関数、`CEditView`オブジェクトのテキスト バッファー。  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bNext = TRUE,  
    BOOL bCase = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索するテキストです。  
  
 `bNext`  
 検索の方向を指定します。 場合**TRUE**バッファーの末尾方向検索の方向です。 場合**FALSE**バッファーの先頭方向検索の方向です。  
  
 `bCase`  
 検索では、大文字小文字を区別するかどうかを指定します。 場合**TRUE**検索では、大文字小文字を区別します。 場合**FALSE**検索では、大文字と小文字が区別されません。  
  
### <a name="return-value"></a>戻り値  
 検索テキストが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、指定した文字列のバッファーにテキストを検索`lpszFind`を開始位置で指定した方向で、現在の選択として`bNext`で指定された大文字小文字の区別を使用して`bCase`です。 テキストが見つかった場合は、見つかったテキストを選択範囲を設定し、0 以外の値を返します。 テキストが見つからなかった場合は、0 を返します。  
  
 通常必要はありませんを呼び出して、`FindText`関数をオーバーライドする場合を除き、 `OnFindNext`、どの呼び出し`FindText`です。  
  
##  <a name="getbufferlength"></a>  CEditView::GetBufferLength  
 現在エディット コントロールのバッファーで、null 終端文字を除いた文字数を取得するには、このメンバー関数を呼び出します。  
  
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
  
### <a name="remarks"></a>コメント  
 このコントロールの種類は[CEdit](../../mfc/reference/cedit-class.md)を直接使用して Windows のエディット コントロールを操作できるように、`CEdit`メンバー関数。  
  
> [!CAUTION]
>  使用して、`CEdit`オブジェクトの基になるウィンドウの状態の変更は、コントロールを編集できます。 たとえば、する必要がありますいない設定を変更するタブを使用して、 [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops)ために機能`CEditView`エディット コントロールと印刷の両方に使用するため、これらの設定をキャッシュします。 代わりに、 [CEditView::SetTabStops](#settabstops)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]  
  
##  <a name="getprinterfont"></a>  CEditView::GetPrinterFont  
 呼び出す`GetPrinterFont`へのポインターを取得する、 [CFont](../../mfc/reference/cfont-class.md)を現在のプリンター フォントを記述するオブジェクト。  
  
```  
CFont* GetPrinterFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `CFont` ; 現在のプリンター フォントを指定するオブジェクト**NULL**プリンター フォントが設定されていない場合。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 プリンター フォントが設定されていないかどうか、既定の印刷の動作、`CEditView`クラスは、表示に使用される同じフォントを使用して印刷します。  
  
 現在プリンター フォントを判断するのにには、この関数を使用します。 場合はそうでない、目的のプリンター フォントを使用して[なかったとき](#setprinterfont)を変更します。  
  
##  <a name="getselectedtext"></a>  CEditView::GetSelectedText  
 呼び出す`GetSelectedText`に選択したテキストをコピーする、`CString`選択または選択範囲の最初のキャリッジ リターン文字の直前の文字の末尾までのオブジェクト。  
  
```  
void GetSelectedText(CString& strResult) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strResult`  
 参照、`CString`を選択したテキストを受け取るオブジェクト。  
  
##  <a name="lockbuffer"></a>  CEditView::LockBuffer  
 バッファーへのポインターを取得するには、このメンバー関数を呼び出します。 バッファーは変更できません。  
  
```  
LPCTSTR LockBuffer() const;  
```  
  
### <a name="return-value"></a>戻り値  
 エディット コントロールのバッファーへのポインター。  
  
##  <a name="onfindnext"></a>  CEditView::OnFindNext  
 指定した文字列のバッファーにテキストを検索`lpszFind`で指定された方向に`bNext`で指定された大文字と小文字の区別`bCase`です。  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索するテキストです。  
  
 `bNext`  
 検索の方向を指定します。 場合**TRUE**バッファーの末尾方向検索の方向です。 場合**FALSE**バッファーの先頭方向検索の方向です。  
  
 `bCase`  
 検索では、大文字小文字を区別するかどうかを指定します。 場合**TRUE**検索では、大文字小文字を区別します。 場合**FALSE**検索では、大文字と小文字が区別されません。  
  
### <a name="remarks"></a>コメント  
 検索は、現在の選択範囲の先頭から開始されへの呼び出しによって行われます[FindText](#findtext)です。 既定の実装で`OnFindNext`呼び出し[見つからなかったとき](#ontextnotfound)テキストが見つからなかった場合です。  
  
 オーバーライド`OnFindNext`方法を変更する、 `CEditView`-派生オブジェクトは、テキストを検索します。 `CEditView` 呼び出し`OnFindNext`ユーザーが標準の検索 ダイアログ ボックスで、次を検索 ボタンを選択するとします。  
  
##  <a name="onreplaceall"></a>  CEditView::OnReplaceAll  
 `CEditView` 呼び出し`OnReplaceAll`ユーザーが標準の置換 ダイアログ ボックスで、すべて置換 ボタンを選択するとします。  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索するテキストです。  
  
 `lpszReplace`  
 検索テキストを置換するテキストです。  
  
 `bCase`  
 検索では、大文字小文字を区別するかどうかを指定します。 場合**TRUE**検索では、大文字小文字を区別します。 場合**FALSE**検索では、大文字と小文字が区別されません。  
  
### <a name="remarks"></a>コメント  
 `OnReplaceAll` 指定した文字列のバッファーにテキストを検索`lpszFind`で指定された大文字と小文字の区別`bCase`です。 検索は、現在の選択範囲の先頭から開始します。 指定されたテキストで、検索テキストが見つかるたびこの関数の置換テキストの出現`lpszReplace`です。 呼び出すことによって、検索を行う[FindText](#findtext)です。 既定の実装で[見つからなかったとき](#ontextnotfound)は、テキストが見つからなかった場合に呼び出されます。  
  
 現在の選択範囲が一致しない場合`lpszFind`、選択範囲が指定した文字列の最初に出現する更新`lpszFind`置換は実行されません。 これにより、ユーザーに選択範囲が置き換えられるテキストと一致しない場合の対処の必要なは、このことを確認できます。  
  
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
 `lpszFind`  
 検索するテキストです。  
  
 `bNext`  
 検索の方向を指定します。 場合**TRUE**バッファーの末尾方向検索の方向です。 場合**FALSE**バッファーの先頭方向検索の方向です。  
  
 `bCase`  
 検索では、大文字小文字を区別するかどうかを指定します。 場合**TRUE**検索では、大文字小文字を区別します。 場合**FALSE**検索では、大文字と小文字が区別されません。  
  
 `lpszReplace`  
 見つかったテキストを置換するテキストです。  
  
### <a name="remarks"></a>コメント  
 この関数がで指定されたテキストの次の出現箇所のバッファーにテキストを検索、選択範囲を交換した後`lpszFind`で指定された方向に`bNext`で指定された大文字と小文字の区別`bCase`です。 呼び出すことによって、検索を行う[FindText](#findtext)です。 テキストが見つからなかった場合[見つからなかったとき](#ontextnotfound)と呼びます。  
  
 オーバーライド`OnReplaceSel`方法を変更する、 `CEditView`-派生オブジェクトには、選択したテキストが置き換えられます。  
  
##  <a name="ontextnotfound"></a>  CEditView::OnTextNotFound  
 既定の実装では、Windows 関数を変更するには、この関数をオーバーライド**MessageBeep**です。  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索するテキストです。  
  
##  <a name="printinsiderect"></a>  CEditView::PrintInsideRect  
 呼び出す`PrintInsideRect`によって指定される四角形内のテキストを印刷する*rectLayout*です。  
  
```  
UINT PrintInsideRect(
    CDC *pDC,  
    RECT& rectLayout,  
    UINT nIndexStart,  
    UINT nIndexStop);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストへのポインター。  
  
 *rectLayout*  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)テキストが表示される四角形を指定します。  
  
 `nIndexStart`  
 表示される最初の文字のバッファー内にあるインデックスを作成します。  
  
 `nIndexStop`  
 表示する最後の文字を次の文字のバッファー内にあるインデックスを作成します。  
  
### <a name="return-value"></a>戻り値  
 印刷するのには、次の文字のインデックス (つまり、表示される最後の文字文字)。  
  
### <a name="remarks"></a>コメント  
 場合、`CEditView`コントロールにスタイルがない**ES_AUTOHSCROLL**レンダリングの四角形内でテキストをラップします。 コントロールにスタイルがある場合**ES_AUTOHSCROLL**テキストは四角形の右端にクリップします。  
  
 **に**の要素、 *rectLayout*オブジェクトが変更されたため、四角形の寸法がテキストで使用されている元の四角形の部分を定義します。  
  
##  <a name="serializeraw"></a>  CEditView::SerializeRaw  
 呼び出す`SerializeRaw`が、`CArchive`テキストの書き込みまたは読み取りをオブジェクト、`CEditView`オブジェクトをテキスト ファイルにします。  
  
```  
void SerializeRaw(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 参照、`CArchive`オブジェクトをシリアル化されたテキストを格納します。  
  
### <a name="remarks"></a>コメント  
 `SerializeRaw` 異なる`CEditView`の内部実装`Serialize`ことで読み取りし、オブジェクトの説明のデータの前せず、テキストのみを書き込みます。  
  
##  <a name="setprinterfont"></a>  なかったとき  
 呼び出す`SetPrinterFont`で指定されたフォントにプリンター フォントを設定する`pFont`です。  
  
```  
void SetPrinterFont(CFont* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 型のオブジェクトへのポインター`CFont`です。 場合**NULL**印刷に使用するフォントは表示フォントに基づいています。  
  
### <a name="remarks"></a>コメント  
 ビューを常に特定のフォントを印刷に使用する場合への呼び出しを含める`SetPrinterFont`クラスの`OnPreparePrinting`関数。 ビューの内容が印刷される前に、フォントの変更が発生するように印刷が行われる前にこの仮想関数が呼び出されます。  
  
##  <a name="settabstops"></a>  CEditView::SetTabStops  
 表示と印刷に使用されるタブ ストップを設定するには、この関数を呼び出します。  
  
```  
void SetTabStops(int nTabStops);
```  
  
### <a name="parameters"></a>パラメーター  
 `nTabStops`  
 ダイアログ単位で、それぞれのタブ ストップの幅。  
  
### <a name="remarks"></a>コメント  
 1 つのタブ ストップ幅のみがサポートされています。 (`CEdit`オブジェクトは複数のタブ幅をサポートします)。幅は、ダイアログ単位は、印刷または表示するのに使用するフォントの平均の文字幅 (大文字と小文字のアルファベット文字のみに基づく) の 4 分の 1 と同じです。 使用しないで`CEdit::SetTabStops`ため`CEditView`タブ ストップ値をキャッシュする必要があります。  
  
 この関数は、呼び出されたオブジェクトのタブのみを変更します。 タブを変更する各停止`CEditView`オブジェクトのアプリケーションで、各オブジェクトの`SetTabStops`関数。  
  
### <a name="example"></a>例  
 上記のコードは、コントロールを使用するフォントを慎重に測定することによって、4 文字ごとに、コントロールのタブ ストップを設定します。  
  
 [!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]  
  
##  <a name="unlockbuffer"></a>  CEditView::UnlockBuffer  
 バッファーのロックを解除するには、このメンバー関数を呼び出します。  
  
```  
void UnlockBuffer() const;  
```  
  
### <a name="remarks"></a>コメント  
 呼び出す`UnlockBuffer`によって返されたポインターを使用して完了したら[LockBuffer](#lockbuffer)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル SUPERPAD](../../visual-cpp-samples.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)
