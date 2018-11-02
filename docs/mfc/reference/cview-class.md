---
title: CView クラス
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
ms.openlocfilehash: f325423c940df46940d7074c599eb8e502e90586
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50669080"
---
# <a name="cview-class"></a>CView クラス

ユーザーが定義するビュークラスの基本機能が用意されています。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CView : public CWnd
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CView::CView](#cview)|`CView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[しません](#doprepareprinting)|印刷 ダイアログ ボックスを表示し、プリンター デバイス コンテキストを作成します。オーバーライドするときに呼び出す、`OnPreparePrinting`メンバー関数。|
|[CView::GetDocument](#getdocument)|ビューに関連付けられているドキュメントを返します。|
|[CView::IsSelected](#isselected)|ドキュメント項目が選択されているかどうかをテストします。 OLE のサポートが必要です。|
|[CView::OnDragEnter](#ondragenter)|項目が最初に、ビューのドラッグ アンド ドロップ領域にドラッグされたときに呼び出されます。|
|[CView::OnDragLeave](#ondragleave)|ドラッグした項目がビューのドラッグ アンド ドロップ領域を離れると呼び出されます。|
|[直前](#ondragover)|項目がビューのドラッグ アンド ドロップ領域にドラッグされるときに呼び出されます。|
|[CView::OnDragScroll](#ondragscroll)|カーソルがウィンドウのスクロール領域にドラッグされるかどうかを判断するには、呼び出されます。|
|[この関数](#ondrop)|項目がビュー、既定のハンドラーのドラッグ アンド ドロップ領域にドロップされたときに呼び出されます。|
|[CView::OnDropEx](#ondropex)|項目がビュー、プライマリのハンドラーのドラッグ アンド ドロップ領域にドロップされたときに呼び出されます。|
|[:Oninitialupdate](#oninitialupdate)|ビューがドキュメントに最初にアタッチされた後に呼び出されます。|
|[付け](#onpreparedc)|前に呼び出される、`OnDraw`画面表示のメンバー関数を呼び出す、または`OnPrint`印刷または印刷プレビューのメンバー関数が呼び出されます。|
|[CView::OnScroll](#onscroll)|OLE アイテムは、ビューの境界を越えるドラッグされたときに呼び出されます。|
|[CView::OnScrollBy](#onscrollby)|アクティブなインプレース OLE 項目を含むビューがスクロールされたときに呼び出されます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CView::OnActivateFrame](#onactivateframe)|ビューを含むフレーム ウィンドウがアクティブ化または非アクティブ化されたときに呼び出されます。|
|[CView::OnActivateView](#onactivateview)|ビューがアクティブ化されるときに呼び出されます。|
|[値](#onbeginprinting)|印刷ジョブが開始したときに呼び出されますグラフィックス デバイス インターフェイス (GDI) のリソースの割り当てをオーバーライドします。|
|[詳細](#ondraw)|画面の表示、印刷、または印刷プレビューのドキュメントのイメージを表示するために呼び出されます。 必要な実装です。|
|[CView::OnEndPrinting](#onendprinting)|印刷ジョブの終了時に呼び出されますGDI リソースの割り当てを解除するオーバーライドです。|
|[CView::OnEndPrintPreview](#onendprintpreview)|プレビュー モードが終了したときに呼び出されます。|
|[関数](#onprepareprinting)|ドキュメントが印刷またはプレビューされる前に呼び出されます[印刷] ダイアログ ボックスを初期化するためにオーバーライドします。|
|[のみ](#onprint)|印刷またはプレビューのドキュメントのページと呼ばれます。|
|[CView::OnUpdate](#onupdate)|そのドキュメントが表示されているビューに通知するという変更します。|

## <a name="remarks"></a>Remarks

ビューがドキュメントにアタッチされているし、ドキュメントとユーザーの間の仲介役として機能します。 ビューは、画面またはプリンターにドキュメントのイメージを表示しますし、ユーザー入力をドキュメントに操作として解釈します。

ビューは、フレーム ウィンドウの子です。 複数のビューには、分割ウィンドウの場合と同様のフレーム ウィンドウを共有できます。 ビュー クラス、フレーム ウィンドウ クラス、およびドキュメント クラス間の関係を確立、`CDocTemplate`オブジェクト。 ユーザーが新しいウィンドウを開きますか、既存の分割 1 フレームワーク新しいビューを構築し、ドキュメントにアタッチします。

ビューは、1 つだけのドキュメントにアタッチできますが、ドキュメントは、接続して一度に複数のビューを持つことができます: たとえば、分割ウィンドウで、またはマルチ ドキュメント インターフェイス (MDI) アプリケーションで複数の子ウィンドウで、ドキュメントが表示されます。 アプリケーションは、特定のドキュメント型であるに対するさまざまな種類のビューをサポートすることができます。たとえば、ワード プロセッシング プログラムでは、ドキュメントの完全なテキスト ビューとセクションの見出しのみを表示するアウトライン ビューの両方を指定可能性があります。 これらのさまざまな種類のビューの配置できます個別のフレーム ウィンドウで、または 1 つのフレーム ウィンドウの別のウィンドウでスプリッター ウィンドウを使用する場合。

ビューは、さまざまなキーボード入力やマウス入力コマンドと同様に、ドラッグ アンド ドロップを使用してメニューのツールバー、またはスクロール バーからの入力などの入力を処理する可能性があります。 ビューは、そのフレーム ウィンドウによって転送されたコマンドを受信します。 ビューが特定のコマンドを処理しない場合は、関連付けられたドキュメントにコマンドを転送します。 すべてのコマンド ターゲットのようには、ビューは、メッセージ マップを通じてメッセージを処理します。

ビューは、格納することではなく表示やドキュメントのデータを変更します。 ドキュメントでは、そのデータに関する必要な詳細ビューを提供します。 メンバー関数を呼び出すビュー クラスのクラスのドキュメントを提供できます、ドキュメントのデータ メンバーを直接またはアクセス許可の表示することができます。

ドキュメントのデータが変更されたときに、変更、ビューを呼び出す通常、 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews)関数を呼び出すことによって、その他のすべてのビューに通知すると、ドキュメント、`OnUpdate`のメンバー関数各します。 既定の実装`OnUpdate`ビューのクライアント領域全体を無効になります。 ドキュメントの変更後の部分に割り当てられたクライアント領域の領域のみを無効にする上書きすることができます。

使用する`CView`、そこから派生クラスを作成および実装、`OnDraw`画面表示を実行するメンバー関数。 使用することも`OnDraw`印刷と印刷プレビューを実行します。 フレームワークは、印刷とドキュメントのプレビュー、印刷のループを処理します。

ビューのスクロール バーのメッセージを処理する、 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[ために](../../mfc/reference/cwnd-class.md#onvscroll)メンバー関数。 スクロール バーのメッセージが、これらの関数で処理を実装するか、使用することができます、`CView`クラスを派生[CScrollView](../../mfc/reference/cscrollview-class.md)スクロールを処理します。

それに`CScrollView`から派生したその他の 9 つのクラスを提供する、Microsoft Foundation Class ライブラリ`CView`:

- [CCtrlView](../../mfc/reference/cctrlview-class.md)ドキュメント/ビュー アーキテクチャでは、ツリー、一覧、および豊富な編集コントロールを使用できるビュー。

- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)、ダイアログ ボックス コントロールでのデータベース レコードを表示するビュー。

- [CEditView](../../mfc/reference/ceditview-class.md)、単純な複数行のテキスト エディターを提供するビュー。 使用することができます、 `CEditView`  ダイアログ ボックスと、ドキュメントのビュー内のコントロールとしてのオブジェクト。

- [CFormView](../../mfc/reference/cformview-class.md)、スクロール可能なビューをダイアログ ボックス コントロールを含み、ダイアログ テンプレート リソースに基づきます。

- [CListView](../../mfc/reference/clistview-class.md)、ドキュメント/ビュー アーキテクチャのリスト コントロールを利用できるビュー。

- [CRecordView](../../mfc/reference/crecordview-class.md)、ダイアログ ボックス コントロールでのデータベース レコードを表示するビュー。

- [CRichEditView](../../mfc/reference/cricheditview-class.md)ドキュメント/ビュー アーキテクチャ リッチ エディット コントロールを使用できるビュー。

- [CScrollView](../../mfc/reference/cscrollview-class.md)、自動的にスクロールのサポートを提供するビュー。

- [CTreeView](../../mfc/reference/ctreeview-class.md)、ドキュメント/ビュー アーキテクチャのツリー コントロールを利用できるビュー。

`CView`クラスという名前の派生実装クラスにもあります`CPreviewView`、印刷プレビューを実行するために、フレームワークによって使用されます。 このクラスは、印刷プレビュー ウィンドウのツールバーで、単一または二重ページのプレビューなどに固有の機能のサポートを提供し、ズーム、プレビュー イメージを拡大する、します。 呼び出すか、オーバーライドする必要はありません`CPreviewView`のメンバー関数 (たとえば、印刷プレビュー モードで編集をサポートする) 場合は、印刷プレビューの独自のインターフェイスを実装する場合を除き、します。 使用しての詳細については`CView`を参照してください[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)と[印刷](../../mfc/printing.md)します。 さらを参照してください[テクニカル ノート 30:](../../mfc/tn030-customizing-printing-and-print-preview.md)印刷プレビューのカスタマイズの詳細についてはします。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cview"></a>  CView::CView

`CView` オブジェクトを構築します。

```
CView();
```

### <a name="remarks"></a>Remarks

フレームワークは、新しいフレーム ウィンドウが作成されるか、ウィンドウを分割時に、コンス トラクターを呼び出します。 上書き、 [OnInitialUpdate](#oninitialupdate)メンバー関数は、ドキュメントがアタッチされた後に、ビューを初期化します。

##  <a name="doprepareprinting"></a>  しません

この関数のオーバーライドから呼び出す[OnPreparePrinting](#onprepareprinting)を印刷 ダイアログ ボックスを起動し、プリンター デバイス コンテキストを作成します。

```
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*pInfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

### <a name="return-value"></a>戻り値

印刷または印刷プレビューが開始できる場合は 0 以外操作が取り消された場合は 0。

### <a name="remarks"></a>Remarks

この関数の動作は、印刷または印刷プレビューの呼び出されたかどうかによって異なります (で指定された、`m_bPreview`のメンバー、 *pInfo*パラメーター)。 ファイルが印刷される場合、この関数の値を使用して [印刷] ダイアログ ボックスを呼び出します、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)構造体*pInfo* ; を指す関数を作成、ユーザーがダイアログ ボックスを閉じた後、プリンター デバイス コンテキスト ダイアログ ボックスで指定されたユーザーの設定に基づくしを使ってデバイス コンテキストを返します、 *pInfo*パラメーター。 このデバイス コンテキストは、ドキュメントの印刷に使用されます。

この関数は現在、プリンターの設定を使用してプリンター デバイス コンテキストを作成、ファイルがプレビューされている場合このデバイス コンテキストは、プレビュー期間中にプリンターをシミュレートするために使用されます。

##  <a name="getdocument"></a>  CView::GetDocument

ビューのドキュメントへのポインターを取得するには、この関数を呼び出します。

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>戻り値

ポインター、 [CDocument](../../mfc/reference/cdocument-class.md)ビューに関連付けられているオブジェクト。 ビューがドキュメントにアタッチされていない場合は NULL です。

### <a name="remarks"></a>Remarks

これは、ドキュメントのメンバー関数を呼び出すことができます。

##  <a name="isselected"></a>  CView::IsSelected

指定されたドキュメントの項目が選択されているかどうか確認するためにフレームワークによって呼び出されます。

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>パラメーター

*pDocItem*<br/>
テスト対象のドキュメント アイテムへのポインター。

### <a name="return-value"></a>戻り値

指定されたドキュメントの項目がオンの場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数の既定の実装では、FALSE を返します。 選択範囲を使用して実装する場合は、この関数をオーバーライド[CDocItem](../../mfc/reference/cdocitem-class.md)オブジェクト。 ビューには、OLE アイテムが含まれている場合は、この関数をオーバーライドする必要があります。

##  <a name="onactivateframe"></a>  CView::OnActivateFrame

ビューを含むフレーム ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。

```
virtual void OnActivateFrame(
    UINT nState,
    CFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>パラメーター

*状態*<br/>
フレーム ウィンドウがされているかどうかを指定します。 アクティブ化または非アクティブ化します。 次の値のいずれかを指定できます。

- WA_INACTIVE フレーム ウィンドウが非アクティブにします。

- WA_ACTIVE フレーム ウィンドウがマウス以外のいくつかの方法でアクティブ化は、(たとえば、ウィンドウを選択するキーボード インターフェイスの使用) をクリックします。

- マウスのクリックが WA_CLICKACTIVE フレーム ウィンドウをアクティブにします。

*pFrameWnd*<br/>
アクティブ化するのには、フレーム ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

ビューに関連付けられたフレーム ウィンドウがアクティブ化または非アクティブ化されたときに、特別な処理を実行する場合は、このメンバー関数をオーバーライドします。 たとえば、 [CFormView](../../mfc/reference/cformview-class.md)の保存およびフォーカスのあるコントロールを復元するときに、この上書きを実行します。

##  <a name="onactivateview"></a>  CView::OnActivateView

ビューがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。

```
virtual void OnActivateView(
    BOOL bActivate,
    CView* pActivateView,
    CView* pDeactiveView);
```

### <a name="parameters"></a>パラメーター

*bActivate*<br/>
表示されているかどうかを示しますがアクティブまたは非アクティブ化します。

*pActivateView*<br/>
アクティブにされているビュー オブジェクトを指します。

*pDeactiveView*<br/>
非アクティブになるビュー オブジェクトを指します。

### <a name="remarks"></a>Remarks

この関数の既定の実装では、アクティブ化されているビューにフォーカスを設定します。 ビューがアクティブまたは非アクティブ化されたときに、特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、非アクティブなビューから、アクティブなビューを識別する特別な視覚的手掛かりを提供する場合を確認する、 *bActivate*パラメーターとビューの外観を適宜更新します。

*PActivateView*と*pDeactiveView*パラメーターは、アプリケーションのメイン フレーム ウィンドウがアクティブに作業中のビューを変更しない場合、同じビュー をポイント — たとえば、フォーカスされている場合MDI 子ウィンドウの間で切り替えるときに、アプリケーション内で 1 つのビュー間ではなく、他のアプリケーションからを転送します。 これにより、必要な場合のパレットを再現すると表示されます。

これらのパラメーターが異なるとき[CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview)ものとは異なるビューを使用して呼び出した[CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview)を返します。 これは、分割ウィンドウで最もよく発生します。

##  <a name="onbeginprinting"></a>  値

`OnPreparePrinting` が呼び出された後で、印刷または印刷プレビュー ジョブの開始時にフレームワークによって呼び出されます。

```
virtual void OnBeginPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンター デバイス コンテキストを指し示します。

*pInfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

### <a name="remarks"></a>Remarks

この関数の既定の実装は、何も行いません。 この関数をオーバーライドして、特に印刷のために必要な GDI リソース (ペン、フォントなど) を割り当てます。 [OnPrint](#onprint) メンバー関数内から、デバイス コンテキストの GDI オブジェクトを、それらを使用する各ページ用に選択します。 同じビュー オブジェクトを使用して画面の表示と印刷の両方を実行している場合は、各表示に必要な GDI リソースに別個の変数を使用します。これにより、印刷時に画面を更新することができます。

さらに、この関数を使用して、プリンター デバイス コンテキストのプロパティに依存する初期化を実行することもできます。 たとえば、ドキュメントを印刷するために必要なページ数は、印刷ダイアログ ボックスでユーザーが指定した設定 (たとえば、ページの長さ) によって異なる可能性があります。 そのような場合は、通常行うように [OnPreparePrinting](#onprepareprinting) メンバー関数にドキュメントの長さを指定することはできません。ダイアログ ボックスの設定に基づいてプリンター デバイス コンテキストが作成されるまで待機する必要があります。 [OnBeginPrinting](#onbeginprinting) は、プリンター デバイス コンテキストを表す [CDC](../../mfc/reference/cdc-class.md) オブジェクトにアクセスできる初めてのオーバーライド可能な関数です。したがって、この関数からドキュメントの長さを設定することができます。 この時点でドキュメントの長さを指定しない場合、印刷プレビュー時にスクロール バーは表示されません。

##  <a name="ondragenter"></a>  CView::OnDragEnter

マウスがドロップ ターゲット ウィンドウの非スクロール領域を最初に入ったときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*pDataObject*<br/>
指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ビューのドロップ領域にドラッグしています。

*ドロップ*<br/>
修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせ: MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、および MK_RBUTTON します。

*ポイント*<br/>
ビューのクライアント領域を基準と現在のマウスの位置。

### <a name="return-value"></a>戻り値

DROPEFFECT からの値の列挙型で、ユーザーがこの位置にあるオブジェクトを削除する場合に発生するドロップダウンの種類を示します。 ドロップの種類は、通常で示される現在のキーの状態に依存*ドロップ*します。 Keystates DROPEFFECT 値の標準的なマッピングは次のとおりです。

- このウィンドウで、せず、データ オブジェクトを削除できません。

- MK_CONTROL の DROPEFFECT_LINK &#124; MK_SHIFT オブジェクトとそのサーバーの間のリンケージを作成します。

- DROPEFFECT_COPY MK_CONTROL のでは、削除されたオブジェクトのコピーを作成します。

- 行った MK_ALT は、ドロップされたオブジェクトと削除は元のオブジェクトのコピーを作成します。 ビューは、このデータ オブジェクトを受け入れることができるは通常、既定のドロップ効果になります。

詳細については、MFC Advanced Concepts サンプルを参照してください。 [OCLIENT](../../visual-cpp-samples.md)します。

### <a name="remarks"></a>Remarks

既定の実装では、何もせずにします。

今後の呼び出しを準備するには、この関数をオーバーライド、 [OnDragOver](#ondragover)メンバー関数。 この時点で後で使用できるデータ オブジェクトから必要なすべてのデータを取得する必要が、`OnDragOver`メンバー関数。 ビューは、ユーザーの視覚的フィードバックを提供するには、この時点でも更新する必要があります。 詳細については、この記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../../mfc/drag-and-drop-implementing-a-drop-target.md)します。

##  <a name="ondragleave"></a>  CView::OnDragLeave

そのウィンドウの有効なドロップ領域から、マウスを移動すると、ドラッグ操作中にフレームワークが呼び出します。

```
virtual void OnDragLeave();
```

### <a name="remarks"></a>Remarks

現在のビューは、中に行った操作をクリーンアップする必要がある場合は、この関数をオーバーライド[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)オブジェクトがドラッグ アンド ドロップ中に、ビジュアル ユーザー フィードバックを削除するなどの呼び出し.

##  <a name="ondragover"></a>  直前

マウスがドロップ ターゲット ウィンドウに移動するドラッグ操作中に、フレームワークが呼び出します。

```
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*pDataObject*<br/>
指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ドロップ ターゲット上にドラッグします。

*ドロップ*<br/>
修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせ: MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、および MK_RBUTTON します。

*ポイント*<br/>
ビューのクライアント領域を基準と現在のマウスの位置。

### <a name="return-value"></a>戻り値

DROPEFFECT からの値の列挙型で、ユーザーがこの位置にあるオブジェクトを削除する場合に発生するドロップダウンの種類を示します。 型多くの場合に依存キーの現在の状態で示されている*ドロップ*します。 Keystates DROPEFFECT 値の標準的なマッピングは次のとおりです。

- このウィンドウで、せず、データ オブジェクトを削除できません。

- MK_CONTROL の DROPEFFECT_LINK &#124; MK_SHIFT オブジェクトとそのサーバーの間のリンケージを作成します。

- DROPEFFECT_COPY MK_CONTROL のでは、削除されたオブジェクトのコピーを作成します。

- 行った MK_ALT は、ドロップされたオブジェクトと削除は元のオブジェクトのコピーを作成します。 ビューは、データ オブジェクトを受け入れることができるは通常、既定のドロップ効果になります。

詳細については、MFC Advanced Concepts サンプルを参照してください。 [OCLIENT](../../visual-cpp-samples.md)します。

### <a name="remarks"></a>Remarks

既定の実装では、何もせずにします。

ドラッグ操作中にユーザーの視覚的フィードバックを提供するには、この関数をオーバーライドします。 この関数は継続的に呼び出される、のでそれに含まれる任意のコードを可能な限り最適化してください。 詳細については、この記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../../mfc/drag-and-drop-implementing-a-drop-target.md)します。

##  <a name="ondragscroll"></a>  CView::OnDragScroll

呼び出しの前にフレームワークによって呼び出されます[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)ポイントがスクロール可能な領域にかどうかを調べます。

```
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*ドロップ*<br/>
修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせ: MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、および MK_RBUTTON します。

*ポイント*<br/>
画面を基準 (ピクセル単位)、カーソルの位置が含まれています。

### <a name="return-value"></a>戻り値

DROPEFFECT からの値の列挙型で、ユーザーがこの位置にあるオブジェクトを削除する場合に発生するドロップダウンの種類を示します。 ドロップの種類は、通常で示される現在のキーの状態に依存*ドロップ*します。 Keystates DROPEFFECT 値の標準的なマッピングは次のとおりです。

- このウィンドウで、せず、データ オブジェクトを削除できません。

- MK_CONTROL の DROPEFFECT_LINK &#124; MK_SHIFT オブジェクトとそのサーバーの間のリンケージを作成します。

- DROPEFFECT_COPY MK_CONTROL のでは、削除されたオブジェクトのコピーを作成します。

- 行った MK_ALT は、ドロップされたオブジェクトと削除は元のオブジェクトのコピーを作成します。

- DROPEFFECT_SCROLL を使用して、ドラッグのスクロール操作が実行されるときに、または対象のビューで発生していることを示します。

詳細については、MFC Advanced Concepts サンプルを参照してください。 [OCLIENT](../../visual-cpp-samples.md)します。

### <a name="remarks"></a>Remarks

このイベントの特別な動作を提供したい場合は、この関数をオーバーライドします。 既定の実装では、カーソルが各ウィンドウの枠線内で、既定のスクロール領域にドラッグされるときに windows が自動的にスクロールします。詳細については、この記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../../mfc/drag-and-drop-implementing-a-drop-target.md)します。

##  <a name="ondraw"></a>  詳細

ドキュメントのイメージをレンダリングするためにフレームワークによって呼び出されます。

```
virtual void OnDraw(CDC* pDC) = 0;
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
ドキュメントのイメージの描画に使用するデバイス コンテキストへのポインター。

### <a name="remarks"></a>Remarks

フレームワークは、画面の表示、印刷、および印刷プレビューを実行するには、この関数を呼び出すし、事例ごとに別のデバイス コンテキストを渡します。 既定の実装はありません。

ドキュメントのビューを表示するには、この関数をオーバーライドする必要があります。 使用してグラフィック デバイス インターフェイス (GDI) 呼び出しを行うことができます、 [CDC](../../mfc/reference/cdc-class.md)指すオブジェクト、 *pDC*パラメーター。 描画前にデバイス コンテキストにペンやフォントなどの GDI リソースを選択し、し、その後で選択を解除できます。 多くの場合、描画のコードがデバイスに依存しない; を指定できます。つまり、デバイスの種類が、イメージを表示する方法については必要ありません。

描画を最適化するために呼び出す、[ため](../../mfc/reference/cdc-class.md#rectvisible)指定の四角形を描画するかどうかを確認するデバイス コンテキストのメンバー関数。 通常の画面表示と印刷を区別する必要がある場合は、呼び出し、 [IsPrinting](../../mfc/reference/cdc-class.md#isprinting)デバイス コンテキストのメンバー関数。

##  <a name="ondrop"></a>  この関数

ユーザーが有効なドロップ ターゲット上でデータ オブジェクトを離したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnDrop(
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

' pDataObject * へのポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ですが、ドロップ先にドロップします。

*dropEffect*<br/>
ユーザーが要求したドロップ効果。

- DROPEFFECT_COPY では、削除されているデータ オブジェクトのコピーを作成します。

- 行ったは、データ オブジェクトを現在のマウスの位置に移動します。

- DROPEFFECT_LINK は、データ オブジェクトとサーバー間のリンクを作成します。

*ポイント*<br/>
ビューのクライアント領域を基準と現在のマウスの位置。

### <a name="return-value"></a>戻り値

ドロップが成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

既定の実装では、何も実行し、FALSE を返します。

ビューのクライアント領域に OLE ドロップの効果を実装するには、この関数をオーバーライドします。 データ オブジェクトを使用して調べることができます*pDataObject*クリップボード データ形式とデータ削除指定したポイントにします。

> [!NOTE]
>  に対するオーバーライドがある場合、フレームワークはこの関数を呼び出しません[OnDropEx](#ondropex)このビュー クラスにします。

##  <a name="ondropex"></a>  CView::OnDropEx

ユーザーが有効なドロップ ターゲット上でデータ オブジェクトを離したときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*pDataObject*<br/>
指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ですが、ドロップ先にドロップします。

*dropDefault*<br/>
現在のキーの状態に基づいて既定のドロップ操作に対して、ユーザーが選択した結果。 せずがある可能性があります。 ドロップ効果は、「解説」で説明します。

*ドロップダウン リスト*<br/>
ドロップ ソースがサポートしているドロップ効果の一覧。 ビットごとの OR を使用して、ドロップ効果の値を結合することができます ( **&#124;**) 操作。 ドロップ効果は、「解説」で説明します。

*ポイント*<br/>
ビューのクライアント領域を基準と現在のマウスの位置。

### <a name="return-value"></a>戻り値

によって指定された場所にドロップしようとしたときの原因となったドロップ効果*ポイント*します。 によって示される値の 1 つあります*dropEffectList*します。 ドロップ効果は、「解説」で説明します。

### <a name="remarks"></a>Remarks

既定の実装が何もしないし、フレームワークを呼び出す必要がありますを示すダミー値 (-1) を返すには、 [OnDrop](#ondrop)ハンドラー。

マウスの右ボタンのドラッグ アンド ドロップの効果を実装するには、この関数をオーバーライドします。 マウスの右ボタンのドラッグ アンド ドロップ、マウスの右ボタンが離さ通常選択肢のメニューを表示します。

オーバーライド`OnDropEx`マウスの右ボタンのクエリを実行する必要があります。 呼び出すことができます[GetKeyState](https://msdn.microsoft.com/library/windows/desktop/ms646301)からマウスの右ボタンの状態を保存したり、 [OnDragEnter](#ondragenter)ハンドラー。

- マウスの右ボタンがダウンしている場合は、オーバーライドはドロップ ソースがドロップ効果のサポートを提供するポップアップ メニューを表示する必要があります。

   - 調べる*ドロップダウン リスト ボックスから*ドロップ ソースでサポートされているドロップ効果を確認します。 ポップアップ メニューにこれらのアクションのみを有効にします。

   - 使用[SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem)に基づいて既定のアクションを設定する*dropDefault*します。

   - 最後に、ポップアップ メニューからユーザーの選択によって示される操作を行います。

- マウスの右ボタンが押されていない場合、上書きとして処理、標準の削除要求。 指定されたドロップ効果を使用して、 *dropDefault*します。 代わりに、オーバーライドできることを示すダミー値 (-1) を返す`OnDrop`このドロップ操作を処理します。

使用*pDataObject*を調べる、`COleDataObject`クリップボード データ形式とデータ削除指定したポイントにします。

ドロップ効果には、drop 操作に関連付けられたアクションについて説明します。 次のドロップ効果の一覧を参照してください。

- せずドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- 行った移動操作が実行されます。

- 元のデータをドロップしたデータから DROPEFFECT_LINK A リンクが確立されます。

- DROPEFFECT_SCROLL を使用して、ドラッグのスクロール操作が実行されるときに、またはターゲットで発生していることを示します。

既定のメニュー コマンドの設定の詳細については、次を参照してください。 [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem) Windows sdk と[CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu)このボリュームにします。

##  <a name="onendprinting"></a>  CView::OnEndPrinting

ドキュメントが印刷またはプレビューされた後に、フレームワークによって呼び出されます。

```
virtual void OnEndPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンター デバイス コンテキストを指し示します。

*pInfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

### <a name="remarks"></a>Remarks

この関数の既定の実装は、何も行いません。 割り当てられているすべての GDI リソースを解放するには、この関数をオーバーライド、 [OnBeginPrinting](#onbeginprinting)メンバー関数。

##  <a name="onendprintpreview"></a>  CView::OnEndPrintPreview

ユーザーが印刷プレビュー モードを終了するときに、フレームワークによって呼び出されます。

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

*pInfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

*ポイント*<br/>
プレビュー モードで最後に表示されたページで、ポイントを指定します。

*pView*<br/>
プレビュー用に使用するビュー オブジェクトを指します。

### <a name="remarks"></a>Remarks

この関数の既定の実装、 [OnEndPrinting](#onendprinting)印刷プレビュー前に、の状態をメイン フレーム ウィンドウの開始メンバー関数を復元します。 プレビュー モードが終了したときに、特別な処理を実行するには、この関数をオーバーライドします。 たとえば、プレビュー モードから通常の表示モードに切り替える場合は、ドキュメント内のユーザーの位置を維持する場合は、スクロールするにはによって説明されている位置、*ポイント*パラメーターおよび`m_nCurPage`のメンバー`CPrintInfo`構造体、 *pInfo*パラメーターを指します。

基底クラスのバージョンを常に呼び出す`OnEndPrintPreview`関数の末尾には通常、オーバーライドします。

##  <a name="oninitialupdate"></a>  :Oninitialupdate

ビューが最初に、ドキュメントに接続されているが、ビューが最初に表示される前に、フレームワークによって呼び出されます。

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Remarks

この関数の既定の実装、 [OnUpdate](#onupdate)ヒント情報なしでメンバー関数 (つまり、0 の既定値を使用して、 *lHint*パラメーターとの場合は NULL、 *pHint*パラメーター)。 ドキュメントに関する情報を必要とする任意の one-time initialization を実行するには、この関数をオーバーライドします。 たとえば、アプリケーションは、固定サイズのドキュメントに、ドキュメントのサイズに基づくビューのスクロール範囲を初期化するためにこの関数を使用できます。 アプリケーションでは、可変サイズのドキュメントをサポートする場合は、使用[OnUpdate](#onupdate)スクロールを更新する時間を制限すべてドキュメントの変更。

##  <a name="onpreparedc"></a>  付け

前にフレームワークによって呼び出されます、 [OnDraw](#ondraw)画面表示とする前に、メンバー関数が呼び出されます、 [OnPrint](#onprint)印刷または印刷のプレビュー期間中の各ページのメンバー関数が呼び出されます。

```
virtual void OnPrepareDC(
    CDC* pDC,
    CPrintInfo* pInfo = NULL);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
ドキュメントのイメージの描画に使用するデバイス コンテキストへのポインター。

*pInfo*<br/>
指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)場合は、現在の印刷ジョブを記述する構造体`OnPrepareDC`印刷または印刷プレビューでは、呼び出された、`m_nCurPage`メンバーを印刷するページを指定します。 場合、このパラメーターが NULL`OnPrepareDC`画面表示の場合は。

### <a name="remarks"></a>Remarks

この関数の既定の実装は画面表示の場合、関数が呼び出された場合に、何も行われません。 ただし、この関数は、派生クラスでオーバーライドなど[CScrollView](../../mfc/reference/cscrollview-class.md)のデバイス コンテキストの属性を調整するには、オーバーライドの先頭に基本クラスの実装を呼び出すことは常にその結果、します。

印刷関数が呼び出された場合、既定の実装に格納されているページの情報を調べて、 *pInfo*パラメーター。 ドキュメントの長さが指定されていない場合`OnPrepareDC`を 1 ページの長いドキュメントを前提し、して 1 つのページを印刷した後、印刷のループを停止します。 関数に設定して印刷ループを終了、`m_bContinuePrinting`を FALSE に構造体のメンバー。

オーバーライド`OnPrepareDC`は次の理由のいずれかの。

- 指定したページに必要なデバイス コンテキストの属性を調整します。 たとえば、マッピング モードまたは、デバイス コンテキストの他の特性を設定する必要がある場合はこの関数でします。

- 印刷時の改ページ調整を実行します。 使用して、印刷の開始時に、ドキュメントの長さを指定する通常の[OnPreparePrinting](#onprepareprinting)メンバー関数。 ただし、事前にどれくらいの時間のドキュメントが (たとえば、印刷時に、未確定の数のレコードをデータベースから) がわからない場合、オーバーライド`OnPrepareDC`を印刷するドキュメントの終わりをテストするのにします。 印刷するドキュメントの以上ない場合は、設定、`m_bContinuePrinting`のメンバー、`CPrintInfo`構造体を FALSE にします。

- エスケープ コードをページごとにプリンターに送信します。 エスケープ コードを送信する`OnPrepareDC`を呼び出し、`Escape`のメンバー関数、 *pDC*パラメーター。

基本クラスを呼び出して`OnPrepareDC`オーバーライドの先頭にします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]

##  <a name="onprepareprinting"></a>  関数

ドキュメントを印刷またはプレビュー前に、フレームワークによって呼び出されます。

```
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*pInfo*<br/>
現在の印刷ジョブを表す [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 構造体を指し示します。

### <a name="return-value"></a>戻り値

印刷を開始する 0 以外の場合印刷ジョブが取り消された場合は 0 を返します。

### <a name="remarks"></a>Remarks

既定の実装では、何も行われません。

印刷と印刷プレビューを有効にするには、この関数をオーバーライドする必要があります。 呼び出す、 [DoPreparePrinting](#doprepareprinting)メンバー関数を渡す、 *pInfo*パラメーター、戻り値を返します`DoPreparePrinting`印刷 ダイアログ ボックスを表示し、プリンター デバイス コンテキストを作成します。 既定値以外の値を持つ印刷 ダイアログ ボックスを初期化する場合は、メンバーに値を割り当てる*pInfo*します。 たとえば、ドキュメントの長さがわかっている場合に値を渡す、 [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage)のメンバー関数*pInfo*呼び出す前に`DoPreparePrinting`します。 この値にするには表示されます: 範囲 の 印刷 ダイアログ ボックスのボックスです。

`DoPreparePrinting` プレビュー ジョブの印刷 ダイアログ ボックスは表示されません。 印刷ジョブの印刷 ダイアログ ボックスをバイパスする場合は、ことを確認、`m_bPreview`のメンバー *pInfo*に渡す前に TRUE に設定が FALSE で、 `DoPreparePrinting`。 後で FALSE にリセットします。

アクセスを必要とする初期化を実行する必要があるかどうか、 `CDC` (たとえば、ドキュメントの長さを指定する前に、ページ サイズを把握する必要がある場合)、プリンター デバイス コンテキストを表すオブジェクトの上書き、`OnBeginPrinting`メンバー関数。

値を設定する場合、`m_nNumPreviewPages`または`m_strPageDesc`のメンバー、 *pInfo*パラメーターを呼び出した後に行う`DoPreparePrinting`します。 `DoPreparePrinting`メンバー関数のセット`m_nNumPreviewPages`アプリケーションの値にします。INI ファイル設定と`m_strPageDesc`既定値にします。

### <a name="example"></a>例

  オーバーライド`OnPreparePrinting`を呼び出すと`DoPreparePrinting`オーバーライドから、フレームワークは、[印刷] ダイアログ ボックスを表示し、プリンター DC を作成してようにします。

[!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]

ドキュメントが含まれるページ数がわかっている場合は、最大のページを設定`OnPreparePrinting`呼び出す前に`DoPreparePrinting`します。 フレームワークで、[印刷] ダイアログ ボックスの"to"ボックス ページの最大数が表示されます。

[!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]

##  <a name="onprint"></a>  のみ

印刷または印刷ドキュメントのページをプレビューするためにフレームワークによって呼び出されます。

```
virtual void OnPrint(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
プリンター デバイス コンテキストを指し示します。

*pInfo*<br/>
指す、`CPrintInfo`現在の印刷ジョブを記述する構造体。

### <a name="remarks"></a>Remarks

印刷されるページごとに、フレームワークが呼び出した後すぐにこの関数を呼び出す、 [OnPrepareDC](#onpreparedc)メンバー関数。 印刷されるページがで指定された、`m_nCurPage`のメンバー、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)構造体*pInfo*を指します。 既定の実装、 [OnDraw](#ondraw)メンバー関数は、プリンター デバイス コンテキストを渡します。

次の理由により、この関数をオーバーライドします。

- マルチページ ドキュメントの印刷できるようにします。 現在印刷中のページに対応するドキュメントの部分のみを表示します。 使用している場合`OnDraw`レンダリングを実行するドキュメントの適切な部分だけが出力されるよう、ビューポートの原点を調整できます。

- (つまり、アプリケーションは WYSIWYG ではない) 場合、画面イメージとは異なる、印刷されたイメージにします。 プリンター デバイス コンテキストを渡す代わりに`OnDraw`画面に表示されない属性を使用してイメージを表示するために、デバイス コンテキストを使用します。

   GDI リソースを必要な画面表示を使用しない印刷描画前にデバイス コンテキストに選択し、後で選択を解除します。 これらの GDI リソースを割り当てる必要がある[OnBeginPrinting](#onbeginprinting)でリリースされた[OnEndPrinting](#onendprinting)します。

- ヘッダーまたはフッターを実装します。 使用することもできます`OnDraw`で印刷できる領域を制限することで、レンダリングを行う。

なお、`m_rectDraw`のメンバー、 *pInfo*パラメーターには、論理ユニットのページの印刷可能領域がについて説明します。

呼び出さないでください`OnPrepareDC`のオーバーライドで`OnPrint`、フレームワークによって`OnPrepareDC`呼び出す前に自動的に`OnPrint`します。

### <a name="example"></a>例

次に、オーバーライドするための雛形`OnPrint`関数。

[!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]

別の例では、次を参照してください。 [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect)します。

##  <a name="onscroll"></a>  CView::OnScroll

スクロールするかどうかを判断するためにフレームワークによって呼び出されることができます。

```
virtual BOOL OnScroll(
    UINT nScrollCode,
    UINT nPos,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*nScrollCode*<br/>
スクロール バーのコードをユーザーを示すには、要求のスクロールします。 このパラメーターは 2 つの部分で構成されます。 下位バイト、水平方向にスクロール発生の種類を決定すると、上位バイト、垂直方向にスクロール発生の種類を決定します。

- SB_BOTTOM まで下にスクロールします。

- 1 行下 SB_LINEDOWN までスクロールします。

- 1 行上に SB_LINEUP までスクロールします。

- 1 つ page down SB_PAGEDOWN までスクロールします。

- 1 つ page up SB_PAGEUP までスクロールします。

- SB_THUMBTRACK 障壁は、指定した位置にボックスをスクロールします。 現在の位置を指定*nPos*します。

- ページのトップへ SB_TOP にスクロールします。

*nPos*<br/>
現在のスクロール ボックスの位置が含まれる場合、スクロール バーのコードは SB_THUMBTRACK;それ以外の場合は使用されません。 初期のスクロールの範囲に応じて*nPos*が負の数およびにキャストする必要があります、 **int**必要な場合。

*bDoScroll*<br/>
指定したスクロール動作を実際に行うかどうかを判断します。 TRUE の場合、スクロールしを実行します。FALSE の場合、スクロールは発生しません。

### <a name="return-value"></a>戻り値

場合*bDoScroll*戻りますは 0 以外。 それ以外の場合、TRUE であり、ビューのスクロールが実際には 0。 場合*bDoScroll*が FALSE の場合、戻り値の場合に返さがする値*bDoScroll*スクロールを実際にはない場合でも、TRUE が。

### <a name="remarks"></a>Remarks

1 つのケースでこの関数にフレームワークによって呼び出さ*bDoScroll*ビューがスクロール バーのメッセージを受信すると、TRUE に設定します。 この場合、ビューを実際にスクロールする必要があります。 その他の場合は、この関数を呼び出すと*bDoScroll* OLE 項目はスクロール実際に行われる前に、最初に自動スクロールのドロップ ターゲットの領域にドラッグすると、FALSE に設定します。 この場合、する必要がありますいない実際にスクロールするビュー。

##  <a name="onscrollby"></a>  CView::OnScrollBy

ユーザーが存在するドキュメント、ビューの現在の境界に対して OLE 項目をドラッグするか、垂直方向または水平方向のスクロール バーを操作することでいずれかのビューを超える領域を表示するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnScrollBy(
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>パラメーター

*sizeScroll*<br/>
ピクセルの数は、水平および垂直にスクロールします。

*bDoScroll*<br/>
ビューのスクロールがかどうかを判断します。 TRUE の場合、場所は、スクロールし、します。FALSE の場合、スクロールは発生しません。

### <a name="return-value"></a>戻り値

ビューがスクロールできる場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

派生クラスでは、このメソッドは、ビューは、ユーザーが要求され、必要に応じて、新しいリージョンを更新し、方向にスクロールできるかどうかを確認します。 この関数は自動的に呼び出されます[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[ために](../../mfc/reference/cwnd-class.md#onvscroll)スクロールの実際の要求を実行します。

このメソッドの既定の実装では、ビューは変更されませんが、ビューがではスクロールが呼び出されない場合、 `CScrollView`-クラスを派生します。

ドキュメントの幅または高さ 32767 ピクセルを超えると、過去の 32767 スクロールためには失敗`OnScrollBy`、無効なを使用して呼び出した*sizeScroll*引数。

##  <a name="onupdate"></a>  CView::OnUpdate

ビューのドキュメントが変更された後に、フレームワークによって呼び出されますこの関数を呼び出して[CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews)でき、これらの変更を反映するように、その表示を更新するビュー。

```
virtual void OnUpdate(
    CView* pSender,
    LPARAM lHint,
    CObject* pHint);
```

### <a name="parameters"></a>パラメーター

*pSender*<br/>
ドキュメントを変更するビューを指すすべてのビューを更新するか場合は null です。

*lHint*<br/>
変更についての情報が含まれています。

*pHint*<br/>
変更についての情報を格納するオブジェクトを指します。

### <a name="remarks"></a>Remarks

メソッドの既定の実装によって呼び出されますも[OnInitialUpdate](#oninitialupdate)します。 既定の実装は、全体のクライアント領域で、[次へ] の WM_PAINT メッセージが受信したときに塗りつぶすのためにマークを無効にします。 ドキュメントの変更後の部分に割り当てられた領域のみを更新する場合は、この関数をオーバーライドします。 これを行うには、ヒントのパラメーターを使用して変更についての情報を渡す必要があります。

使用する*lHint*ビットマスクまたは列挙型では、通常、特別なヒントの値を定義し、ドキュメントをこれらの値のいずれかを渡します。 使用する*pHint*、ヒントからクラスを派生[CObject](../../mfc/reference/cobject-class.md)ドキュメントをオーバーライドする場合、ヒントにポインターを渡す`OnUpdate`を使用して、[使うため](../../mfc/reference/cobject-class.md#iskindof)ヒント オブジェクトの実行時の型を決定するメンバー関数。

通常実行するいずれかから直接描画`OnUpdate`します。 代わりに、デバイス座標で、更新が必要な領域を示す四角形を決定します。この四角形を渡す[エディット](../../mfc/reference/cwnd-class.md#invalidaterect)します。 これを次に行うことが原因で、 [WM_PAINT](/windows/desktop/gdi/wm-paint)メッセージを受信します。

場合*lHint*は 0 と*pHint*が null の場合、ドキュメントが汎用的な更新プログラムの通知を送信します。 ビューは、汎用的な更新の通知を受信した場合、または、ヒントをデコードできない場合は、クライアント領域全体を無効にします。

## <a name="see-also"></a>関連項目

[MFC のサンプルは](../../visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)
