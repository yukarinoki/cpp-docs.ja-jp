---
title: Cビュークラス
ms.date: 11/04/2016
f1_keywords:
- CView
- AFXWIN/CView
- AFXWIN/CView::CView
- AFXWIN/CView::DoPreparePrinting
- AFXWIN/CView::GetDocument
- AFXWIN/CView::IsSelected
- AFXWIN/CView::OnDragEnter
- AFXWIN/CView::OnDragLeave
- AFXWIN/CView::OnDragOver
- AFXWIN/CView::OnDragScroll
- AFXWIN/CView::OnDrop
- AFXWIN/CView::OnDropEx
- AFXWIN/CView::OnInitialUpdate
- AFXWIN/CView::OnPrepareDC
- AFXWIN/CView::OnScroll
- AFXWIN/CView::OnScrollBy
- AFXWIN/CView::OnActivateFrame
- AFXWIN/CView::OnActivateView
- AFXWIN/CView::OnBeginPrinting
- AFXWIN/CView::OnDraw
- AFXWIN/CView::OnEndPrinting
- AFXWIN/CView::OnEndPrintPreview
- AFXWIN/CView::OnPreparePrinting
- AFXWIN/CView::OnPrint
- AFXWIN/CView::OnUpdate
helpviewer_keywords:
- CView [MFC], CView
- CView [MFC], DoPreparePrinting
- CView [MFC], GetDocument
- CView [MFC], IsSelected
- CView [MFC], OnDragEnter
- CView [MFC], OnDragLeave
- CView [MFC], OnDragOver
- CView [MFC], OnDragScroll
- CView [MFC], OnDrop
- CView [MFC], OnDropEx
- CView [MFC], OnInitialUpdate
- CView [MFC], OnPrepareDC
- CView [MFC], OnScroll
- CView [MFC], OnScrollBy
- CView [MFC], OnActivateFrame
- CView [MFC], OnActivateView
- CView [MFC], OnBeginPrinting
- CView [MFC], OnDraw
- CView [MFC], OnEndPrinting
- CView [MFC], OnEndPrintPreview
- CView [MFC], OnPreparePrinting
- CView [MFC], OnPrint
- CView [MFC], OnUpdate
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
ms.openlocfilehash: 763e36b0736ce588e7e2aded25e50347f9e0ca70
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373204"
---
# <a name="cview-class"></a>Cビュークラス

ユーザーが定義するビュークラスの基本機能が用意されています。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CView : public CWnd
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[Cビュー::Cビュー](#cview)|`CView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CView::Do準備印刷](#doprepareprinting)|[印刷] ダイアログ ボックスを表示し、プリンター デバイス コンテキストを作成します。`OnPreparePrinting`メンバー関数をオーバーライドするときに呼び出します。|
|[CView::ドキュメントを取得します。](#getdocument)|ビューに関連付けられているドキュメントを返します。|
|[Cビュー::選択済み](#isselected)|ドキュメント アイテムが選択されているかどうかをテストします。 OLE サポートに必要です。|
|[Cビュー:オンドラグエンター](#ondragenter)|項目がビューのドラッグ アンド ドロップ領域に最初にドラッグされたときに呼び出されます。|
|[CView::オンドラグリーブ](#ondragleave)|ドラッグされた項目がビューのドラッグ アンド ドロップ領域から離れたときに呼び出されます。|
|[Cビュー::オンドラッグオーバー](#ondragover)|項目がビューのドラッグ アンド ドロップ領域上にドラッグされたときに呼び出されます。|
|[::オンドラッグスクロール](#ondragscroll)|カーソルがウィンドウのスクロール領域にドラッグされているかどうかを調べます。|
|[Cビュー::オンドロップ](#ondrop)|項目がビューのドラッグ アンド ドロップ領域にドロップされたときに呼び出されます。|
|[CView::オンドロップエックス](#ondropex)|項目がビューのドラッグ アンド ドロップ領域にドロップされたときに呼び出されます。|
|[Cビュー::オンイニシャルアップデート](#oninitialupdate)|ビューが最初にドキュメントにアタッチされた後に呼び出されます。|
|[Cビュー::オン準備DC](#onpreparedc)|画面表示用`OnDraw`にメンバー関数が呼び出される前`OnPrint`に呼び出されるか、または印刷プレビュー用にメンバー関数が呼び出されます。|
|[Cビュー::オンスクロール](#onscroll)|OLE アイテムがビューの境界を越えてドラッグされたときに呼び出されます。|
|[Cビュー::オンスクロールバイ](#onscrollby)|アクティブなインプレース OLE アイテムを含むビューがスクロールされるときに呼び出されます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[Cビュー::オンアクティブフレーム](#onactivateframe)|ビューを含むフレーム ウィンドウがアクティブまたは非アクティブになったときに呼び出されます。|
|[Cビュー::オンアクティブビュー](#onactivateview)|ビューがアクティブになったときに呼び出されます。|
|[CView::OnBeginPrinting](#onbeginprinting)|印刷ジョブの開始時に呼び出されます。をオーバーライドして、グラフィックス デバイス インターフェイス (GDI) リソースを割り当てます。|
|[Cビュー::オンドロー](#ondraw)|画面表示、印刷、または印刷プレビュー用にドキュメントのイメージをレンダリングするために呼び出されます。 実装が必要です。|
|[Cビュー::オンエンドプリント](#onendprinting)|印刷ジョブが終了したときに呼び出されます。GDI リソースの割り当てを解除する場合にオーバーライドします。|
|[プレビュー::オンエンドプリントプレビュー](#onendprintpreview)|プレビュー モードが終了したときに呼び出されます。|
|[Cビュー::準備印刷中](#onprepareprinting)|ドキュメントを印刷またはプレビューする前に呼び出されます。[印刷] ダイアログ ボックスを初期化するためにオーバーライドします。|
|[Cビュー::オンプリント](#onprint)|ドキュメントのページを印刷またはプレビューするために呼び出されます。|
|[Cビュー::オンアップデート](#onupdate)|ドキュメントが変更されたことをビューに通知するために呼び出されます。|

## <a name="remarks"></a>解説

ビューはドキュメントに添付され、ドキュメントとユーザーの間の仲介として機能します: ビューは、画面またはプリンター上のドキュメントのイメージをレンダリングし、ユーザー入力をドキュメントに対する操作として解釈します。

ビューは、フレーム ウィンドウの子です。 分割ウィンドウの場合と同様に、複数のビューでフレーム ウィンドウを共有できます。 ビュー クラス、フレーム ウィンドウ クラス、およびドキュメント クラスの間のリレーションシップは、`CDocTemplate`オブジェクトによって確立されます。 ユーザーが新しいウィンドウを開くか、既存のウィンドウを分割すると、フレームワークは新しいビューを作成し、ドキュメントにアタッチします。

ビューは 1 つのドキュメントにのみアタッチできますが、ドキュメントに複数のビューを一度にアタッチできます 。 アプリケーションでは、特定のドキュメントタイプに対して異なるタイプのビューをサポートできます。たとえば、文書のテキスト表示全体と、セクション見出しのみを表示するアウトライン 表示の両方を、ワード プロセッシング プログラムで提供できます。 分割ウィンドウを使用する場合、これらの異なる種類のビューを別々のフレーム ウィンドウに配置したり、単一フレーム ウィンドウの別のウィンドウに配置したりできます。

ビューは、キーボード入力、マウス入力、ドラッグアンドドロップによる入力、メニュー、ツールバー、スクロールバーからのコマンドなど、いくつかの異なるタイプの入力を処理する役割を担う場合があります。 ビューは、フレーム ウィンドウによって転送されるコマンドを受け取ります。 ビューが特定のコマンドを処理しない場合、そのビューは関連付けられたドキュメントにコマンドを転送します。 すべてのコマンド ターゲットと同様に、ビューはメッセージ マップを介してメッセージを処理します。

ビューは、ドキュメントのデータの表示と変更を行いますが、保存は行いません。 ドキュメントは、そのデータに関する必要な詳細をビューに提供します。 ビューは、ドキュメントのデータ メンバーに直接アクセスできるようにしたり、ビュー クラスを呼び出すためにドキュメント クラスにメンバー関数を提供したりできます。

ドキュメントのデータが変更されると、通常、変更の原因となるビューは、ドキュメントの[CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews)関数を呼び出し、各ドキュメントのメンバー関数`OnUpdate`を呼び出すことによって他のすべてのビューに通知します。 の既定の`OnUpdate`実装では、ビューのクライアント領域全体が無効になります。 ドキュメントの変更された部分にマップされているクライアント領域の領域のみを無効にするように、この値をオーバーライドできます。

を使用`CView`するには、クラスを派生させ、画面表示`OnDraw`を実行するメンバー関数を実装します。 印刷および印刷プレビュー`OnDraw`を実行することもできます。 フレームワークは、ドキュメントの印刷とプレビューの印刷ループを処理します。

ビューは[、CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)メンバー関数を使用してスクロール バー メッセージを処理します。 これらの関数でスクロール バー メッセージ処理を実装するか、派生クラス`CView`[CScrollView](../../mfc/reference/cscrollview-class.md)を使用してスクロールを処理できます。

また`CScrollView`、Microsoft Foundation クラス ライブラリには、 から`CView`派生した 9 つのクラスが用意されています。

- [CCtrlView](../../mfc/reference/cctrlview-class.md)、ドキュメントの使用を可能にするビュー - ツリー、リスト、およびリッチエディットコントロールを持つビューアーキテクチャ。

- [ダイアログ](../../mfc/reference/cdaorecordview-class.md)ボックス コントロールにデータベース レコードを表示するビューです。

- [CEditView](../../mfc/reference/ceditview-class.md)は、単純な複数行テキスト エディターを提供するビューです。 オブジェクトは`CEditView`、ダイアログ ボックスのコントロールとして、またドキュメントのビューとして使用できます。

- [CFormView](../../mfc/reference/cformview-class.md)は、ダイアログ ボックス コントロールを含み、ダイアログ テンプレート リソースに基づくスクロール可能なビューです。

- [CListView](../../mfc/reference/clistview-class.md)、リスト コントロールを使用してドキュメント - ビュー アーキテクチャの使用を可能にするビューです。

- [ダイアログ](../../mfc/reference/crecordview-class.md)ボックス コントロールにデータベース レコードを表示するビューです。

- [リッチ エディット](../../mfc/reference/cricheditview-class.md)コントロールを使用したドキュメント ビュー アーキテクチャの使用を可能にするビューです。

- [スクロール](../../mfc/reference/cscrollview-class.md)のサポートを自動的に提供するビューです。

- [CTreeView](../../mfc/reference/ctreeview-class.md)、ツリーコントロールを使用してドキュメントのビューアーキテクチャの使用を可能にするビュー。

この`CView`クラスには、印刷プレビューを実行するために`CPreviewView`フレームワークで使用される という派生実装クラスもあります。 このクラスは、ツール バー、単一ページまたは 2 ページのプレビュー、ズーム、つまりプレビューイメージの拡大など、印刷プレビュー ウィンドウに固有の機能をサポートします。 印刷プレビュー用に独自の`CPreviewView`インターフェイスを実装する場合 (たとえば、印刷プレビュー モードでの編集をサポートする場合) を除き、メンバー関数を呼び出したりオーバーライドしたりする必要はありません。 の使用`CView`の詳細については、「[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)と[印刷](../../mfc/printing.md)」を参照してください。 さらに、印刷プレビューのカスタマイズの詳細については、[テクニカル ノート 30](../../mfc/tn030-customizing-printing-and-print-preview.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cviewcview"></a><a name="cview"></a>Cビュー::Cビュー

`CView` オブジェクトを構築します。

```
CView();
```

### <a name="remarks"></a>解説

フレームワークは、新しいフレーム ウィンドウが作成されたとき、またはウィンドウが分割されるときに、コンストラクターを呼び出します。 ドキュメントがアタッチされた後にビューを初期化するには[、OnInitialUpdate](#oninitialupdate)メンバー関数をオーバーライドします。

## <a name="cviewdoprepareprinting"></a><a name="doprepareprinting"></a>CView::Do準備印刷

[OnPreparePrinting](#onprepareprinting)のオーバーライドからこの関数を呼び出して、[印刷] ダイアログ ボックスを呼び出し、プリンター デバイス コンテキストを作成します。

```
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*Pinfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

### <a name="return-value"></a>戻り値

印刷プレビューまたは印刷プレビューを開始できる場合は 0 以外の値を返します。操作がキャンセルされた場合は 0。

### <a name="remarks"></a>解説

この関数の動作は、印刷用または印刷プレビュー `m_bPreview` *(pInfo*パラメーターのメンバーによって指定) のどちらが呼び出されているかによって異なります。 ファイルを印刷する場合、この関数は *、pInfo*が指す[CPrintInfo](../../mfc/reference/cprintinfo-structure.md)構造体の値を使用して[印刷]ダイアログ ボックスを呼び出します。ユーザーがダイアログ ボックスを閉じた後、この関数は、ダイアログ ボックスで指定された設定に基づいてプリンター デバイス コンテキストを作成し *、pInfo*パラメーターを使用してこのデバイス コンテキストを返します。 このデバイス コンテキストは、ドキュメントを印刷するために使用されます。

ファイルをプレビューする場合、この関数は現在のプリンター設定を使用してプリンターデバイスコンテキストを作成します。このデバイス コンテキストは、プレビュー中にプリンターをシミュレートするために使用されます。

## <a name="cviewgetdocument"></a><a name="getdocument"></a>CView::ドキュメントを取得します。

ビューのドキュメントへのポインターを取得します。

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>戻り値

ビューに関連付けられた[CDocument](../../mfc/reference/cdocument-class.md)オブジェクトへのポインター。 ビューがドキュメントに添付されていない場合は NULL。

### <a name="remarks"></a>解説

これにより、ドキュメントのメンバー関数を呼び出すことができます。

## <a name="cviewisselected"></a><a name="isselected"></a>Cビュー::選択済み

指定されたドキュメント アイテムが選択されているかどうかを確認するために、フレームワークによって呼び出されます。

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
テスト対象のドキュメント アイテムへのポイント。

### <a name="return-value"></a>戻り値

指定されたドキュメント アイテムが選択されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数の既定の実装では FALSE が返されます。 [CDocItem](../../mfc/reference/cdocitem-class.md)オブジェクトを使用して選択を実装する場合は、この関数をオーバーライドします。 ビューに OLE アイテムが含まれている場合は、この関数をオーバーライドする必要があります。

## <a name="cviewonactivateframe"></a><a name="onactivateframe"></a>Cビュー::オンアクティブフレーム

ビューを含むフレーム ウィンドウがアクティブまたは非アクティブになったときに、フレームワークによって呼び出されます。

```
virtual void OnActivateFrame(
    UINT nState,
    CFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>パラメーター

*nステート*<br/>
フレーム ウィンドウをアクティブにするか、非アクティブにするかを指定します。 次のいずれかの値を指定できます。

- WA_INACTIVE フレーム ウィンドウを非アクティブ化しています。

- WA_ACTIVE フレーム ウィンドウは、マウス クリック以外の方法でアクティブ化されています (たとえば、キーボード インターフェイスを使用してウィンドウを選択するなど)。

- WA_CLICKACTIVE フレーム ウィンドウがマウスクリックでアクティブ化されている

*をクリックします。*<br/>
アクティブ化するフレーム ウィンドウへのポインター。

### <a name="remarks"></a>解説

ビューに関連付けられているフレーム ウィンドウがアクティブまたは非アクティブになったときに特別な処理を実行する場合は、このメンバー関数をオーバーライドします。 たとえば[、CFormView](../../mfc/reference/cformview-class.md)は、フォーカスを持つコントロールを保存および復元するときに、このオーバーライドを実行します。

## <a name="cviewonactivateview"></a><a name="onactivateview"></a>Cビュー::オンアクティブビュー

ビューがアクティブまたは非アクティブ化されたときに、フレームワークによって呼び出されます。

```
virtual void OnActivateView(
    BOOL bActivate,
    CView* pActivateView,
    CView* pDeactiveView);
```

### <a name="parameters"></a>パラメーター

*bアクティブ化*<br/>
ビューがアクティブ化されているか非アクティブ化されているかを示します。

*ビューをアクティブにする*<br/>
アクティブ化されているビュー オブジェクトへのポインター。

*ビュー*<br/>
非アクティブ化されているビュー オブジェクトへのポイント。

### <a name="remarks"></a>解説

この関数の既定の実装では、アクティブ化するビューにフォーカスが設定されます。 ビューがアクティブまたは非アクティブ化されたときに特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、アクティブなビューと非アクティブなビューを区別する特別なビジュアル キューを提供する場合は *、bActivate*パラメーターを調べて、それに応じてビューの外観を更新します。

*pActivateView*と*pDeactiveView*パラメーターは、アプリケーションのメイン フレーム ウィンドウがアクティブなビューで変更なしでアクティブ化されている場合 (たとえば、フォーカスがアプリケーション内のビューから別のビューに転送される場合や、MDI 子ウィンドウ間で切り替える場合など) に同じビューを指します。 これにより、必要に応じてビューがパレットを再認識できるようになります。

これらのパラメーターは[、CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview)が[CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview)が返すものとは異なるビューで呼び出される場合に異なります。 これは、ほとんどの場合、分割ウィンドウで発生します。

## <a name="cviewonbeginprinting"></a><a name="onbeginprinting"></a>Cビュー::オンビギンプリント

`OnPreparePrinting` が呼び出された後で、印刷または印刷プレビュー ジョブの開始時にフレームワークによって呼び出されます。

```
virtual void OnBeginPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンター デバイス コンテキストを指し示します。

*Pinfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

### <a name="remarks"></a>解説

この関数の既定の実装は、何も行いません。 この関数をオーバーライドして、特に印刷のために必要な GDI リソース (ペン、フォントなど) を割り当てます。 [OnPrint](#onprint) メンバー関数内から、デバイス コンテキストの GDI オブジェクトを、それらを使用する各ページ用に選択します。 同じビュー オブジェクトを使用して画面の表示と印刷の両方を実行している場合は、各表示に必要な GDI リソースに別個の変数を使用します。これにより、印刷時に画面を更新することができます。

さらに、この関数を使用して、プリンター デバイス コンテキストのプロパティに依存する初期化を実行することもできます。 たとえば、ドキュメントを印刷するために必要なページ数は、印刷ダイアログ ボックスでユーザーが指定した設定 (たとえば、ページの長さ) によって異なる可能性があります。 そのような場合は、通常行うように [OnPreparePrinting](#onprepareprinting) メンバー関数にドキュメントの長さを指定することはできません。ダイアログ ボックスの設定に基づいてプリンター デバイス コンテキストが作成されるまで待機する必要があります。 [OnBeginPrinting](#onbeginprinting) は、プリンター デバイス コンテキストを表す [CDC](../../mfc/reference/cdc-class.md) オブジェクトにアクセスできる初めてのオーバーライド可能な関数です。したがって、この関数からドキュメントの長さを設定することができます。 この時点でドキュメントの長さを指定しない場合、印刷プレビュー時にスクロール バーは表示されません。

## <a name="cviewondragenter"></a><a name="ondragenter"></a>Cビュー:オンドラグエンター

マウスが最初にドロップターゲットウィンドウの非スクロール領域に入ったときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*オブジェクト*<br/>
ビューのドロップ エリアにドラッグされる[COleDataObject](../../mfc/reference/coledataobject-class.md)へのポイント。

*州*<br/>
修飾子キーの状態を格納します。 これは、MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、およびMK_RBUTTONの任意の数の組み合わせです。

*ポイント*<br/>
ビューのクライアント領域を基準とした現在のマウス位置。

### <a name="return-value"></a>戻り値

ユーザーがこの位置でオブジェクトを削除した場合に発生するドロップの種類を示す、DROPEFFECT 列挙型の値。 ドロップの種類は通常、 *dwKeyState*で示される現在のキー状態によって異なります。 キーステートと DROPEFFECT 値の標準マッピングは次のとおりです。

- DROPEFFECT_NONE このウィンドウでデータ オブジェクトを削除できません。

- MK_CONTROL &#124; MK_SHIFTのDROPEFFECT_LINK オブジェクトとそのサーバー間のリンケージを作成します。

- MK_CONTROLのDROPEFFECT_COPYドロップされたオブジェクトのコピーを作成します。

- MK_ALTのDROPEFFECT_MOVE削除されたオブジェクトのコピーを作成し、元のオブジェクトを削除します。 通常、これは、ビューがこのデータ オブジェクトを受け入れ可能な場合の既定のドロップ効果です。

詳細については、MFC の高度な概念のサンプル[OCLIENT](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="remarks"></a>解説

デフォルトの実装では、何も行わないし、DROPEFFECT_NONE返します。

この関数をオーバーライドして[、OnDragOver](#ondragover)メンバー関数への今後の呼び出しを準備します。 後でメンバー関数で使用するために、データ オブジェクトから必要なデータは、この時点`OnDragOver`で取得する必要があります。 この時点でビューを更新して、ユーザーに視覚的なフィードバックを提供する必要もあります。 詳細については[、「OLE ドラッグ アンド ドロップ: ドロップ ターゲットを実装する](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)」を参照してください。

## <a name="cviewondragleave"></a><a name="ondragleave"></a>CView::オンドラグリーブ

ドラッグ操作中に、マウスがそのウィンドウの有効なドロップ エリアから移動したときに、フレームワークによって呼び出されます。

```
virtual void OnDragLeave();
```

### <a name="remarks"></a>解説

現在のビューで、オブジェクトのドラッグアンドドロップ中に視覚的なユーザーフィードバックを削除するなど[、OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)の呼び出し中に実行されたアクションをクリーンアップする必要がある場合は、この関数をオーバーライドします。

## <a name="cviewondragover"></a><a name="ondragover"></a>Cビュー::オンドラッグオーバー

ドラッグ操作中に、ドロップ ターゲット ウィンドウ上でマウスを移動したときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*オブジェクト*<br/>
ドロップ ターゲット上でドラッグされる[COleDataObject](../../mfc/reference/coledataobject-class.md)へのポイント。

*州*<br/>
修飾子キーの状態を格納します。 これは、MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、およびMK_RBUTTONの任意の数の組み合わせです。

*ポイント*<br/>
ビュー クライアント領域を基準とした現在のマウス位置。

### <a name="return-value"></a>戻り値

ユーザーがこの位置でオブジェクトを削除した場合に発生するドロップの種類を示す、DROPEFFECT 列挙型の値。 ドロップの種類は *、dwKeyState*で示される現在のキーの状態によって異なります。 キーステートと DROPEFFECT 値の標準マッピングは次のとおりです。

- DROPEFFECT_NONE このウィンドウでデータ オブジェクトを削除できません。

- MK_CONTROL &#124; MK_SHIFTのDROPEFFECT_LINK オブジェクトとそのサーバー間のリンケージを作成します。

- MK_CONTROLのDROPEFFECT_COPYドロップされたオブジェクトのコピーを作成します。

- MK_ALTのDROPEFFECT_MOVE削除されたオブジェクトのコピーを作成し、元のオブジェクトを削除します。 通常、これは、ビューがデータ オブジェクトを受け入れ可能な場合の既定のドロップ効果です。

詳細については、MFC の高度な概念のサンプル[OCLIENT](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="remarks"></a>解説

既定の実装では、何も行わないし、DROPEFFECT_NONE返します。

ドラッグ操作中にユーザーに視覚的なフィードバックを与える場合は、この関数をオーバーライドします。 この関数は連続的に呼び出されるため、その関数に含まれるコードは可能な限り最適化する必要があります。 詳細については[、「OLE ドラッグ アンド ドロップ: ドロップ ターゲットを実装する](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)」を参照してください。

## <a name="cviewondragscroll"></a><a name="ondragscroll"></a>::オンドラッグスクロール

[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)を呼び出す前に、スクロール領域内のポイントがあるかどうかを判断する前に、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*州*<br/>
修飾子キーの状態を格納します。 これは、MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、およびMK_RBUTTONの任意の数の組み合わせです。

*ポイント*<br/>
画面を基準としたカーソルの位置をピクセル単位で指定します。

### <a name="return-value"></a>戻り値

ユーザーがこの位置でオブジェクトを削除した場合に発生するドロップの種類を示す、DROPEFFECT 列挙型の値。 ドロップの種類は通常、 *dwKeyState*で示される現在のキー状態によって異なります。 キーステートと DROPEFFECT 値の標準マッピングは次のとおりです。

- DROPEFFECT_NONE このウィンドウでデータ オブジェクトを削除できません。

- MK_CONTROL &#124; MK_SHIFTのDROPEFFECT_LINK オブジェクトとそのサーバー間のリンケージを作成します。

- MK_CONTROLのDROPEFFECT_COPYドロップされたオブジェクトのコピーを作成します。

- MK_ALTのDROPEFFECT_MOVE削除されたオブジェクトのコピーを作成し、元のオブジェクトを削除します。

- DROPEFFECT_SCROLLドラッグ スクロール操作が発生しようとしているか、ターゲット ビューで発生していることを示します。

詳細については、MFC の高度な概念のサンプル[OCLIENT](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="remarks"></a>解説

このイベントに対して特別な動作を指定する場合は、この関数をオーバーライドします。 既定の実装では、カーソルが各ウィンドウの境界線内の既定のスクロール領域にドラッグされると、ウィンドウが自動的にスクロールされます。 詳細については[、「OLE ドラッグ アンド ドロップ: ドロップ ターゲットを実装する](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)」を参照してください。

## <a name="cviewondraw"></a><a name="ondraw"></a>Cビュー::オンドロー

ドキュメントのイメージをレンダリングするために、フレームワークによって呼び出されます。

```
virtual void OnDraw(CDC* pDC) = 0;
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
ドキュメントのイメージをレンダリングするために使用するデバイス コンテキストへのポイント。

### <a name="remarks"></a>解説

フレームワークは、画面表示、印刷、および印刷プレビューを実行するためにこの関数を呼び出し、それぞれの場合に異なるデバイス コンテキストを渡します。 既定の実装はありません。

ドキュメントのビューを表示するには、この関数をオーバーライドする必要があります。 *pDC*パラメーターで指定された[CDC](../../mfc/reference/cdc-class.md)オブジェクトを使用して、グラフィック デバイス インターフェイス (GDI) 呼び出しを行うことができます。 描画する前に、ペンやフォントなどの GDI リソースをデバイス コンテキストで選択し、その後、それらを選択解除することができます。 描画コードはデバイスに依存しない場合があります。つまり、画像を表示しているデバイスの種類に関する情報は必要ありません。

描画を最適化するには、デバイス コンテキストの[RectVisible](../../mfc/reference/cdc-class.md#rectvisible)メンバー関数を呼び出して、指定された四角形が描画されるかどうかを確認します。 通常の画面表示と印刷を区別する必要がある場合は、デバイス コンテキストの[IsPrinting](../../mfc/reference/cdc-class.md#isprinting)メンバー関数を呼び出します。

## <a name="cviewondrop"></a><a name="ondrop"></a>Cビュー::オンドロップ

ユーザーが有効なドロップ ターゲット上でデータ オブジェクトを解放するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnDrop(
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

'pDataObject* ドロップ ターゲットにドロップされる[COleDataObject](../../mfc/reference/coledataobject-class.md)を指します。

*ドロップエフェクト*<br/>
ユーザーが要求したドロップ効果。

- DROPEFFECT_COPY 削除するデータ オブジェクトのコピーを作成します。

- DROPEFFECT_MOVE データ オブジェクトを現在のマウス位置に移動します。

- DROPEFFECT_LINK データ オブジェクトとそのサーバー間のリンクを作成します。

*ポイント*<br/>
ビュー クライアント領域を基準とした現在のマウス位置。

### <a name="return-value"></a>戻り値

ドロップが成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

既定の実装では何も行われなくて、FALSE が返されます。

ビューのクライアント領域に OLE ドロップの効果を実装するには、この関数をオーバーライドします。 データ オブジェクトは *、pDataObject*を使用して、クリップボードのデータ形式と、指定したポイントで削除されたデータを調べることができます。

> [!NOTE]
> フレームワークは、このビュー クラスで[OnDropEx](#ondropex)にオーバーライドがある場合、この関数を呼び出しません。

## <a name="cviewondropex"></a><a name="ondropex"></a>CView::オンドロップエックス

ユーザーが有効なドロップ ターゲット上でデータ オブジェクトを解放するときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*オブジェクト*<br/>
ドロップ ターゲットにドロップされる[COleDataObject](../../mfc/reference/coledataobject-class.md)へのポイント。

*ドロップデフォルト*<br/>
現在のキーの状態に基づいて、既定のドロップ操作に対してユーザーが選択した効果。 DROPEFFECT_NONEかもしれません。 ドロップ効果については、「解説」で説明します。

*ドロップリスト*<br/>
ドロップ ソースがサポートするドロップ効果のリスト。 ドロップ効果の値は、ビットごとの OR ( **&#124;**) 演算を使用して組み合わせることができます。 ドロップ効果については、「解説」で説明します。

*ポイント*<br/>
ビュー クライアント領域を基準とした現在のマウス位置。

### <a name="return-value"></a>戻り値

*point*で指定された位置でのドロップ試行から生じたドロップ効果。 これは *、dropEffectList*で示される値の 1 つでなければなりません。 ドロップ効果については、「解説」で説明します。

### <a name="remarks"></a>解説

既定の実装では、何も行わないし、ダミー値 ( -1 ) を返すフレームワークが呼び出す必要があることを示す、 [OnDrop](#ondrop)ハンドラーです。

マウスの右ボタンドラッグ アンド ドロップの効果を実装するには、この関数をオーバーライドします。 通常、マウスの右ボタンのドラッグ アンド ドロップは、マウスの右ボタンが離されたときに選択メニューを表示します。

の上書`OnDropEx`きは、マウスの右ボタンを照会する必要があります。 [呼](/windows/win32/api/winuser/nf-winuser-getkeystate)び出すか[、OnDragEnter](#ondragenter)ハンドラーからマウスの右ボタンの状態を格納できます。

- マウスの右ボタンが押されている場合、上書きはドロップソースによるドロップエフェクトのサポートを提供するポップアップメニューを表示するはずです。

  - ドロップ ソースでサポートされているドロップ効果を判断するには *、dropList*を調べます。 ポップアップメニューでこれらのアクションのみを有効にします。

  - [既定のアクションを設定するには、既定](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem)の*アクションを設定*します。

  - 最後に、ポップアップメニューからユーザーの選択によって示されるアクションを実行します。

- マウスの右ボタンがダウンしていない場合、オーバーライドはこれを標準のドロップ要求として処理する必要があります。 で指定したドロップ効果*を使用します*。 または、オーバーライドはダミー値 ( -1 ) を返して`OnDrop`、このドロップ操作を処理することを示します。

*pDataObject を*使用して`COleDataObject`、クリップボードのデータ形式と、指定したポイントでドロップされたデータを調べます。

ドロップ効果は、ドロップ操作に関連付けられたアクションを表します。 ドロップ効果の次のリストを参照してください。

- DROPEFFECT_NONE ドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- DROPEFFECT_MOVE 移動操作が実行されます。

- DROPEFFECT_LINK ドロップされたデータから元のデータへのリンクが確立されます。

- DROPEFFECT_SCROLLドラッグ スクロール操作が発生しようとしているか、ターゲットで発生していることを示します。

既定のメニュー コマンドの設定の詳細については、このボリュームの Windows SDK および[CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu)を参照してください。 [SetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem)

## <a name="cviewonendprinting"></a><a name="onendprinting"></a>Cビュー::オンエンドプリント

ドキュメントの印刷またはプレビュー後に、フレームワークによって呼び出されます。

```
virtual void OnEndPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンター デバイス コンテキストを指し示します。

*Pinfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

### <a name="remarks"></a>解説

この関数の既定の実装は、何も行いません。 この関数をオーバーライドして[、OnBeginPrinting](#onbeginprinting)メンバー関数で割り当てた GDI リソースを解放します。

## <a name="cviewonendprintpreview"></a><a name="onendprintpreview"></a>プレビュー::オンエンドプリントプレビュー

ユーザーが印刷プレビュー モードを終了したときに、フレームワークによって呼び出されます。

```
virtual void OnEndPrintPreview(
    CDC* pDC,
    CPrintInfo* pInfo,
    POINT point,
    CPreviewView* pView);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンター デバイス コンテキストを指し示します。

*Pinfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

*ポイント*<br/>
プレビュー モードで最後に表示されたページ上のポイントを指定します。

*pビュー*<br/>
プレビューに使用するビュー オブジェクトへのポイント。

### <a name="remarks"></a>解説

この関数の既定の実装では[、OnEndPrinting](#onendprinting)メンバー関数を呼び出し、メイン フレーム ウィンドウを印刷プレビューが開始する前の状態に戻します。 プレビューモードが終了したときに特別な処理を実行するには、この関数をオーバーライドします。 たとえば、プレビュー モードから通常の表示モードに切り替えたときにドキュメント内でユーザーの位置を維持する場合は、*ポイント*パラメーターと *、pInfo*パラメーターが指`m_nCurPage`す`CPrintInfo`構造体のメンバーで記述されている位置までスクロールできます。

オーバーライド`OnEndPrintPreview`から常に基本クラスバージョンを呼び出します ( 通常は関数の最後に) 。

## <a name="cviewoninitialupdate"></a><a name="oninitialupdate"></a>Cビュー::オンイニシャルアップデート

ビューが最初にドキュメントにアタッチされた後、ビューが最初に表示される前に、フレームワークによって呼び出されます。

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>解説

この関数の既定の実装では、ヒント情報を含まず[に OnUpdate](#onupdate)メンバー関数を呼び出します (つまり *、lHint*パラメーターに*0、pHint*パラメーターに NULL という既定値を使用します)。 ドキュメントに関する情報を必要とする 1 回限りの初期化を実行するには、この関数をオーバーライドします。 たとえば、アプリケーションに固定サイズのドキュメントがある場合、この関数を使用して、ドキュメントサイズに基づいてビューのスクロール制限を初期化できます。 アプリケーションが可変サイズのドキュメントをサポートしている場合は、ドキュメントが変更されるたびに[OnUpdate](#onupdate)を使用してスクロール制限を更新します。

## <a name="cviewonpreparedc"></a><a name="onpreparedc"></a>Cビュー::オン準備DC

[OnDraw](#ondraw)メンバー関数が画面表示用に呼び出される前、および印刷または印刷プレビュー中に[OnPrint](#onprint)メンバー関数が各ページに呼び出される前に、フレームワークによって呼び出されます。

```
virtual void OnPrepareDC(
    CDC* pDC,
    CPrintInfo* pInfo = NULL);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
ドキュメントのイメージをレンダリングするために使用するデバイス コンテキストへのポイント。

*Pinfo*<br/>
印刷または印刷プレビューを呼び出す場合`OnPrepareDC`は、現在の印刷ジョブを記述する[CPrintInfo](../../mfc/reference/cprintinfo-structure.md)構造体を指します。メンバー`m_nCurPage`は、印刷するページを指定します。 画面表示用に呼`OnPrepareDC`び出されている場合、このパラメーターは NULL です。

### <a name="remarks"></a>解説

この関数のデフォルトの実装は、画面表示用に関数が呼び出された場合は何も行いません。 ただし、この関数は、デバイス コンテキストの属性を調整するために[CScrollView](../../mfc/reference/cscrollview-class.md)などの派生クラスでオーバーライドされます。したがって、オーバーライドの先頭に常に基本クラスの実装を呼び出す必要があります。

この関数が印刷用に呼び出された場合、既定の実装では *、pInfo*パラメーターに格納されているページ情報が調べられます。 ドキュメントの長さが指定されていない場合は、ドキュメントの`OnPrepareDC`長さが 1 ページであると見なされ、1 ページ印刷後に印刷ループが停止します。 この関数は、構造体のメンバーを`m_bContinuePrinting`FALSE に設定することで、印刷ループを停止します。

以下`OnPrepareDC`のいずれかの理由でオーバーライドします。

- 指定したページに必要なデバイス コンテキストの属性を調整します。 たとえば、デバイス コンテキストのマッピング モードやその他の特性を設定する必要がある場合は、この関数で設定します。

- 印刷時間のページネーションを実行します。 通常は、印刷の開始時に[、OnPreparePrinting](#onprepareprinting)メンバー関数を使用してドキュメントの長さを指定します。 ただし、ドキュメントの長さ (たとえば、データベースから不確定な数のレコードを印刷する場合) がわからない場合は、ドキュメントの印刷`OnPrepareDC`中にドキュメントの末尾をテストするように上書きします。 印刷するドキュメントがなくなったら、`m_bContinuePrinting``CPrintInfo`構造体のメンバーを FALSE に設定します。

- ページ単位でプリンタにエスケープ コードを送信する。 から`OnPrepareDC`エスケープ コードを送信するには`Escape`*、pDC*パラメータのメンバー関数を呼び出します。

オーバーライドの先頭での`OnPrepareDC`基本クラス バージョンを呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]

## <a name="cviewonprepareprinting"></a><a name="onprepareprinting"></a>Cビュー::準備印刷中

ドキュメントを印刷またはプレビューする前に、フレームワークによって呼び出されます。

```
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*Pinfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

### <a name="return-value"></a>戻り値

印刷を開始するには 0 以外の値を指定します。印刷ジョブが取り消された場合は 0。

### <a name="remarks"></a>解説

既定の実装では、何も行われません。

印刷プレビューと印刷プレビューを有効にするには、この機能をオーバーライドする必要があります。 [メンバー](#doprepareprinting)関数を呼び出して*pInfo*パラメーターを渡し、戻り値を返します。`DoPreparePrinting`をクリックすると、[印刷] ダイアログ ボックスが表示され、プリンター デバイス コンテキストが作成されます。 [印刷] ダイアログ ボックスを既定値以外の値で初期化する場合は *、pInfo*のメンバに値を割り当てます。 たとえば、ドキュメントの長さがわかっている場合は、呼び出す`DoPreparePrinting`前に*pInfo*の[SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage)メンバー関数に値を渡します。 この値は、[印刷] ダイアログ ボックスの [範囲] ボックスに表示されます。

`DoPreparePrinting`では、プレビュー ジョブの [印刷] ダイアログ ボックスは表示されません。 印刷ジョブの印刷ダイアログ ボックスを省略する場合は *、pInfo*の`m_bPreview`メンバーが FALSE であることを確認し、それを TRUE に設定してから`DoPreparePrinting`、 に渡します。後で FALSE にリセットします。

プリンターのデバイス コンテキストを表す`CDC`オブジェクトへのアクセスを必要とする初期化を実行する必要がある場合 (たとえば、ドキュメントの長さを指定する前にページ サイズを知る必要がある場合`OnBeginPrinting`) は、メンバー関数をオーバーライドします。

*pInfo*パラメータの値または`DoPreparePrinting``m_strPageDesc`メンバー`m_nNumPreviewPages`を設定する場合は、 を呼び出した後で設定します。 この`DoPreparePrinting`メンバー関数`m_nNumPreviewPages`は、アプリケーションの .INI ファイルを`m_strPageDesc`使用し、デフォルト値に設定します。

### <a name="example"></a>例

  オーバーライド`OnPreparePrinting`と呼`DoPreparePrinting`び出しをオーバーライドして、フレームワークが [印刷] ダイアログ ボックスを表示し、プリンター DC を作成します。

[!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]

ドキュメントに含まれるページ数がわかっている場合は、 を呼び`OnPreparePrinting`出す`DoPreparePrinting`前に ページの最大数を設定します。 フレームワークは、[印刷] ダイアログ ボックスの [印刷] ボックスに最大ページ番号を表示します。

[!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]

## <a name="cviewonprint"></a><a name="onprint"></a>Cビュー::オンプリント

ドキュメントのページを印刷またはプレビューするために、フレームワークによって呼び出されます。

```
virtual void OnPrint(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンター デバイス コンテキストを指し示します。

*Pinfo*<br/>
現在の`CPrintInfo`印刷ジョブを記述する構造体へのポイント。

### <a name="remarks"></a>解説

印刷される各ページについて、フレームワークは[OnPrepareDC](#onpreparedc)メンバー関数を呼び出した直後にこの関数を呼び出します。 印刷されるページは *、pInfo* `m_nCurPage`が指す[CPrintInfo](../../mfc/reference/cprintinfo-structure.md)構造体のメンバーによって指定されます。 既定の実装では[、OnDraw](#ondraw)メンバー関数を呼び出し、プリンターのデバイス コンテキストを渡します。

次のいずれかの理由でこの関数をオーバーライドします。

- 複数ページのドキュメントの印刷を許可する。 現在印刷中のページに対応する部分のみを表示します。 レンダリングの実行に使用`OnDraw`している場合は、ドキュメントの適切な部分だけが印刷されるようにビューポートの原点を調整できます。

- 印刷イメージを画面イメージと異なるようにする (つまり、アプリケーションが WYSIWYG でない場合)。 プリンターデバイスコンテキストをに`OnDraw`渡す代わりに、デバイスコンテキストを使用して、画面に表示されていない属性を使用してイメージをレンダリングします。

   画面表示に使用しない印刷用の GDI リソースが必要な場合は、描画する前にデバイス コンテキストで GDI リソースを選択し、その後で選択を解除します。 これらの GDI リソースは[OnBeginPrinting](#onbeginprinting)で割り当てられ[、OnEndPrinting](#onendprinting)で解放される必要があります。

- ヘッダーまたはフッターを実装します。 印刷できる領域を`OnDraw`制限することで、レンダリングを行うために使用できます。

*pInfo* `m_rectDraw`パラメーターのメンバーは、ページの印刷可能領域を論理単位で記述していることに注意してください。

のオーバーライドを`OnPrepareDC`呼び出さない`OnPrint`で下に。フレームワークは、`OnPrepareDC`を呼`OnPrint`び出す前に自動的に呼び出します。

### <a name="example"></a>例

オーバーライドされた`OnPrint`関数のスケルトンを次に示します。

[!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]

別の例については[、「CRichEditView::PrintInsideRect」](../../mfc/reference/cricheditview-class.md#printinsiderect)を参照してください。

## <a name="cviewonscroll"></a><a name="onscroll"></a>Cビュー::オンスクロール

スクロールが可能かどうかを判断するために、フレームワークによって呼び出されます。

```
virtual BOOL OnScroll(
    UINT nScrollCode,
    UINT nPos,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*スクロールコード*<br/>
ユーザーのスクロール要求を示すスクロール バー コード。 このパラメーターは、水平に行われるスクロールのタイプを決定する下位バイトと、垂直に発生するスクロールのタイプを決定する高次バイトの 2 つの部分で構成されます。

- SB_BOTTOM 下にスクロールします。

- SB_LINEDOWN 1 行下にスクロールします。

- SB_LINEUP 1 行上にスクロールします。

- SB_PAGEDOWN 1 ページ下にスクロールします。

- SB_PAGEUP 1 ページ上にスクロールします。

- SB_THUMBTRACKスクロールボックスを指定した位置にドラッグします。 現在の位置は*nPos*で指定されます。

- SB_TOP上にスクロールします。

*Npo*<br/>
スクロール バー コードがSB_THUMBTRACK場合は、現在のスクロール ボックス位置を格納します。それ以外の場合は使用されません。 最初のスクロール範囲によっては *、nPos*は負の値になる可能性があり、必要に応じて**int**にキャストする必要があります。

*スクロール*<br/>
指定されたスクロール操作を実際に実行するかどうかを決定します。 TRUE の場合、スクロールが行われます。FALSE の場合、スクロールは行われません。

### <a name="return-value"></a>戻り値

*bDoScroll*が TRUE で、ビューが実際にスクロールされた場合は、0 以外を返します。それ以外の場合は 0。 *bDoScroll*が FALSE の場合は、実際にはスクロールを行っていないにもかかわらず *、bDoScroll*が TRUE の場合に返される値を返します。

### <a name="remarks"></a>解説

ある場合、ビューがスクロールバーメッセージを受信すると、この関数は*bDoScroll*をTRUEに設定したフレームワークによって呼び出されます。 この場合は、実際にビューをスクロールする必要があります。 もう一方の場合、この関数は、実際にスクロールが行われる前に、OLE アイテムがドロップ ターゲットの自動スクロール領域に最初にドラッグされたときに *、bDoScroll*を FALSE に設定して呼び出されます。 この場合、実際にビューをスクロールしないでください。

## <a name="cviewonscrollby"></a><a name="onscrollby"></a>Cビュー::オンスクロールバイ

OLE アイテムをビューの現在の境界線にドラッグするか、垂直スクロール バーまたは水平スクロール バーを操作して、ユーザーがドキュメントの現在のビューの外にある領域を表示するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnScrollBy(
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*サイズスクロール*<br/>
水平方向と垂直方向にスクロールされたピクセル数。

*スクロール*<br/>
ビューのスクロールが発生するかどうかを決定します。 TRUE の場合はスクロールが行われます。FALSE の場合、スクロールは行われません。

### <a name="return-value"></a>戻り値

ビューをスクロールできる場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

派生クラスでは、このメソッドは、ビューがユーザーが要求した方向にスクロール可能かどうかを確認し、必要に応じて新しい領域を更新します。 この関数は、実際のスクロール要求を実行するために[、CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)によって自動的に呼び出されます。

このメソッドの既定の実装ではビューは変更されませんが、呼び出されない場合、ビューは`CScrollView`-derived クラスでスクロールしません。

ドキュメントの幅または高さが 32767 ピクセルを超える場合、32767 を`OnScrollBy`超えるスクロールは、無効な*sizeScroll*引数で呼び出されるため、失敗します。

## <a name="cviewonupdate"></a><a name="onupdate"></a>Cビュー::オンアップデート

ビューのドキュメントが変更された後にフレームワークによって呼び出されます。この関数は[CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews)によって呼び出され、ビューがそれらの変更を反映するように表示を更新できるようにします。

```
virtual void OnUpdate(
    CView* pSender,
    LPARAM lHint,
    CObject* pHint);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ドキュメントを変更したビューへのポイント、またはすべてのビューを更新する場合は NULL を指定します。

*lヒント*<br/>
変更に関する情報が含まれます。

*ヒント*<br/>
変更に関する情報を格納するオブジェクトへのポイント。

### <a name="remarks"></a>解説

これは[、OnInitialUpdate](#oninitialupdate)の既定の実装によっても呼び出されます。 既定の実装では、クライアント領域全体が無効となり、次のWM_PAINTメッセージが受信されたときに、その領域を描画用にマークします。 ドキュメントの変更された部分にマップされている領域だけを更新する場合は、この関数をオーバーライドします。 これを行うには、ヒントパラメーターを使用して変更に関する情報を渡す必要があります。

*lHint*を使用するには、特殊なヒント値 (通常はビットマスクまたは列挙型) を定義し、ドキュメントにこれらの値のいずれかを渡します。 *pHint*を使用するには[、CObject](../../mfc/reference/cobject-class.md)からヒント クラスを派生させ、ドキュメントにヒント オブジェクトへのポインタを渡します。オーバーライドする`OnUpdate`場合は[、CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)メンバー関数を使用して、ヒント オブジェクトの実行時の型を確認します。

通常は、 から`OnUpdate`直接描画を実行しないでください。 代わりに、デバイス座標で更新が必要な領域を記述する四角形を決定します。この四角形を[CWnd::InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect)に渡します。 これにより、次に[WM_PAINT](/windows/win32/gdi/wm-paint)メッセージを受信したときに描画が発生します。

*lHint*が 0 で *、pHint*が NULL の場合、ドキュメントは汎用更新通知を送信しました。 ビューが汎用更新通知を受信した場合、またはヒントをデコードできない場合は、そのビューのクライアント領域全体を無効にする必要があります。

## <a name="see-also"></a>関連項目

[サンプル MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[クラスを分割する](../../mfc/reference/csplitterwnd-class.md)<br/>
[CDCクラス](../../mfc/reference/cdc-class.md)<br/>
[クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)
