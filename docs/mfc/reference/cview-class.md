---
title: CView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ca94e9d1f870fe028faec413a79f13d8a3b8eaa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[しません](#doprepareprinting)|印刷 ダイアログ ボックスを表示し、プリンター デバイス コンテキスト; を作成しますオーバーライドするときに呼び出す、`OnPreparePrinting`メンバー関数。|  
|[CView::GetDocument](#getdocument)|ビューに関連付けられているドキュメントを返します。|  
|[CView::IsSelected](#isselected)|ドキュメント項目が選択されているかどうかをテストします。 OLE のサポートが必要です。|  
|[CView::OnDragEnter](#ondragenter)|項目が最初に、ビューのドラッグ アンド ドロップ領域にドラッグされたときに呼び出されます。|  
|[CView::OnDragLeave](#ondragleave)|ドラッグした項目がビューのドラッグ アンド ドロップ領域を離れるときに呼び出されます。|  
|[直前](#ondragover)|項目がビューのドラッグ アンド ドロップ領域にドラッグされたときに呼び出されます。|  
|[CView::OnDragScroll](#ondragscroll)|カーソルがウィンドウのスクロール領域にドラッグされるかどうかを決定するには、呼び出されます。|  
|[この関数](#ondrop)|項目が、ビューでは、既定のハンドラーのドラッグ アンド ドロップ領域にドロップされたときに呼び出されます。|  
|[CView::OnDropEx](#ondropex)|項目がビュー、プライマリのハンドラーのドラッグ アンド ドロップ領域にドロップされたときに呼び出されます。|  
|[:Oninitialupdate](#oninitialupdate)|ビューは最初のドキュメントにアタッチされている後に呼び出されます。|  
|[付け](#onpreparedc)|前に呼び出される、`OnDraw`画面表示のメンバー関数が呼び出される、または`OnPrint`印刷または印刷プレビューのメンバー関数が呼び出されます。|  
|[CView::OnScroll](#onscroll)|OLE 項目がビューの境界を越えてドラッグされると呼び出されます。|  
|[CView::OnScrollBy](#onscrollby)|アクティブなインプレース OLE 項目を含むビューをスクロールするときに呼び出されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CView::OnActivateFrame](#onactivateframe)|ビューを含むフレーム ウィンドウがアクティブまたは非アクティブ化されたときに呼び出されます。|  
|[CView::OnActivateView](#onactivateview)|ビューがアクティブになったときに呼び出されます。|  
|[値](#onbeginprinting)|印刷ジョブが開始すると呼び出されますグラフィックス デバイス インターフェイス (GDI) のリソースに割り当てるオーバーライドします。|  
|[詳細](#ondraw)|画面の表示、印刷、または印刷プレビューのドキュメントのイメージを表示するために呼び出されます。 必要な実装です。|  
|[CView::OnEndPrinting](#onendprinting)|印刷ジョブの終了時に呼び出されますGDI リソースの解放をオーバーライドします。|  
|[CView::OnEndPrintPreview](#onendprintpreview)|プレビュー モードが終了したときに呼び出されます。|  
|[関数](#onprepareprinting)|ドキュメントが印刷またはプレビューされる前に呼び出されます[印刷] ダイアログ ボックスを初期化するためにオーバーライドします。|  
|[のみ](#onprint)|印刷または印刷ドキュメントのページをプレビューするには、呼び出されます。|  
|[CView::OnUpdate](#onupdate)|そのドキュメントがされているビューを通知するために呼び出されますを変更します。|  
  
## <a name="remarks"></a>コメント  
 ビューがドキュメントにアタッチし、ドキュメントとユーザー間の媒介として機能します。 ビューは、画面またはプリンター上のドキュメントのイメージを表示しますと、ユーザー入力をドキュメントに操作として解釈します。  
  
 ビューは、フレーム ウィンドウの子です。 複数のビューには、分割ウィンドウの場合と同様に、フレーム ウィンドウを共有できます。 ビュー クラス、フレーム ウィンドウ クラス、およびドキュメント クラス間の関係を確立、`CDocTemplate`オブジェクト。 ユーザーが新しいウィンドウを開きます。 または、既存の分割、1 つ、framework 新しいビューを構築してドキュメントにアタッチします。  
  
 ビューは、1 つだけのドキュメントにアタッチできますが、ドキュメントは、接続して、一度に複数のビューを持つことができます: たとえば、分割ウィンドウで、またはマルチ ドキュメント インターフェイス (MDI) アプリケーションで複数の子ウィンドウで、ドキュメントが表示されます。 アプリケーションはの特定のドキュメントの種類です。 さまざまな種類のビューをサポートすることができます。たとえば、ワード プロセッシング プログラムでは、ドキュメントの完全なテキスト ビューとセクションの見出しだけを表示するためのアウトライン ビューの両方を指定可能性があります。 さまざまな種類のビューまたは配置できます個別のフレーム ウィンドウで、1 つのフレーム ウィンドウの別のペインで分割ウィンドウを使用する場合。  
  
 ビューは、さまざまなキーボード入力やマウス入力のメニュー、ツールバー、またはスクロール バーのコマンドと同様に、ドラッグ アンド ドロップによる入力などの入力を処理する可能性があります。 ビューは、そのフレーム ウィンドウによって転送されたコマンドを受信します。 ビューが指定されたコマンドを処理しない場合は、関連付けられたドキュメントにコマンドを転送します。 すべてのコマンド ターゲットのようには、ビューは、メッセージ マップを通じてメッセージを処理します。  
  
 ビューは、表示すると、ドキュメントのデータを変更するのではなく保存することです。 ドキュメントは、そのデータに関する必要な詳細ビューを提供します。 呼び出すビュー クラスのドキュメント クラスのメンバー関数を提供できます、ドキュメントのデータ メンバーと直接、またはアクセス許可の表示ができます。  
  
 変更を担当するビューを呼び出す通常ドキュメントのデータが変更されたときに、 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews)関数を呼び出すことによって他のすべてのビューをユーザーに通知すると、ドキュメント、`OnUpdate`のメンバー関数各します。 既定の実装`OnUpdate`ビューのクライアント領域全体を無効にします。 ドキュメントの変更後の部分に割り当てられたクライアント領域の領域のみを無効化するメソッドをオーバーライドすることができます。  
  
 使用する`CView`、クラスの派生、および実装、`OnDraw`画面表示を実行するメンバー関数。 使用することも`OnDraw`印刷と印刷プレビューを実行します。 フレームワークは、印刷とドキュメントのプレビューの印刷ループを処理します。  
  
 ビューにスクロール バーのメッセージを処理する、 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[ために](../../mfc/reference/cwnd-class.md#onvscroll)メンバー関数。 スクロール バーでメッセージの処理、これらの関数を実装するか、使用して、`CView`クラスを派生[CScrollView](../../mfc/reference/cscrollview-class.md)スクロールを処理します。  
  
 それに`CScrollView`、Microsoft Foundation Class ライブラリから派生したその他の 9 つのクラスを提供する`CView`:  
  
- [CCtrlView](../../mfc/reference/cctrlview-class.md)、により、ドキュメント/ビュー アーキテクチャ ツリー、一覧、およびリッチ エディット コントロールの使用状況を表示します。  
  
- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)、ダイアログ ボックス コントロールにデータベース レコードを表示するビュー。  
  
- [CEditView](../../mfc/reference/ceditview-class.md)、単純な複数行のテキスト エディターを含むビュー。 使用することができます、 `CEditView`  ダイアログ ボックスだけでなく、ドキュメントのビュー コントロールとしてオブジェクト。  
  
- [CFormView](../../mfc/reference/cformview-class.md)、スクロール可能なビューをダイアログ ボックス コントロールを格納し、ダイアログ テンプレート リソースに基づきます。  
  
- [CListView](../../mfc/reference/clistview-class.md)、ドキュメント/ビュー アーキテクチャのリスト コントロールを利用できるビュー。  
  
- [CRecordView](../../mfc/reference/crecordview-class.md)、ダイアログ ボックス コントロールにデータベース レコードを表示するビュー。  
  
- [CRichEditView](../../mfc/reference/cricheditview-class.md)、により、ドキュメント/ビュー アーキテクチャをリッチ エディット コントロールの使用状況を表示します。  
  
- [CScrollView](../../mfc/reference/cscrollview-class.md)、自動的にスクロールをサポートするビュー。  
  
- [CTreeView](../../mfc/reference/ctreeview-class.md)、ドキュメント/ビュー アーキテクチャのツリー コントロールを利用できるビュー。  
  
 `CView`クラスという名前の実装の派生クラスにもあります**CPreviewView**、ありの印刷プレビューを実行するために、フレームワークによって使用されます。 このクラスは、ツールバーでは、単一または二重ページ プレビューなどの印刷プレビュー ウィンドウに固有の機能のサポートを提供し、ズーム、プレビュー イメージを拡大する、します。 呼び出しまたはのいずれかをオーバーライドする必要はありません**CPreviewView**のメンバー関数 (たとえば、印刷プレビュー モードで編集をサポートする) 場合は、印刷プレビューの独自のインターフェイスを実装する場合を除き、します。 使用する方法についての`CView`を参照してください[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)と[印刷](../../mfc/printing.md)です。 さらを参照してください[テクニカル ノート 30:](../../mfc/tn030-customizing-printing-and-print-preview.md)印刷プレビューのカスタマイズの詳細についてはします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cview"></a>  CView::CView  
 `CView` オブジェクトを構築します。  
  
```  
CView();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、新しいフレーム ウィンドウが作成されるか、ウィンドウを分割時に、コンス トラクターを呼び出します。 上書き、[フィルターと並べ替え順序](#oninitialupdate)ドキュメントをアタッチした後に、ビューを初期化するためにメンバー関数。  
  
##  <a name="doprepareprinting"></a>  しません  
 この関数のオーバーライドから呼び出す[OnPreparePrinting](#onprepareprinting)を印刷 ダイアログ ボックスを起動し、プリンター デバイス コンテキストを作成します。  
  
```  
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
### <a name="return-value"></a>戻り値  
 印刷または印刷のプレビューが開始できる場合は 0 以外。操作が取り消された場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の動作は、印刷または印刷プレビューの呼び出されたかどうかによって異なります (によって指定された、**されます**のメンバー、`pInfo`パラメーター)。 この関数が、印刷 ダイアログ ボックスで値を使用してを起動して、ファイルを印刷する場合、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)構造体`pInfo`指す; ユーザーがダイアログ ボックスを閉じた後、この関数はプリンター デバイス コンテキストを作成ダイアログ ボックスで指定されたユーザーの設定に基づくしを使ってデバイス コンテキストを返します、`pInfo`パラメーター。 このデバイス コンテキストは、ドキュメントの印刷に使用されます。  
  
 この関数は、現在のプリンターの設定を使用してプリンター デバイス コンテキストを作成、ファイルがプレビューされている場合このデバイス コンテキストはプレビュー期間中は、プリンターをシミュレートするために使用されます。  
  
##  <a name="getdocument"></a>  CView::GetDocument  
 ビューのドキュメントへのポインターを取得するには、この関数を呼び出します。  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CDocument](../../mfc/reference/cdocument-class.md)ビューに関連付けられているオブジェクト。 **NULL**ビューがドキュメントにアタッチされていない場合。  
  
### <a name="remarks"></a>コメント  
 これにより、ドキュメントのメンバー関数を呼び出すことができます。  
  
##  <a name="isselected"></a>  CView::IsSelected  
 指定したドキュメント項目が選択されているかどうかを確認するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDocItem`  
 テスト対象のドキュメント アイテムへのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定したドキュメント項目がオンの場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装を返します**FALSE**です。 選択範囲を使用して実装する場合は、この関数をオーバーライド[CDocItem](../../mfc/reference/cdocitem-class.md)オブジェクト。 ビューには、OLE アイテムが含まれている場合は、この関数をオーバーライドする必要があります。  
  
##  <a name="onactivateframe"></a>  CView::OnActivateFrame  
 ビューを含むフレーム ウィンドウがアクティブまたは非アクティブ化されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnActivateFrame(
    UINT nState,  
    CFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `nState`  
 フレーム ウィンドウがされているかどうかを指定します。 アクティブ化または非アクティブにします。 次の値のいずれかを指定できます。  
  
- **WA_INACTIVE**フレーム ウィンドウを非アクティブ化します。  
  
- **WA_ACTIVE**フレーム ウィンドウがアクティブ化されているいくつかの方法で (たとえば、ウィンドウを選択するキーボード インターフェイスの使用) して、マウスのクリックしてではないです。  
  
- **WA_CLICKACTIVE**フレーム ウィンドウをマウスのクリックによってアクティブ化  
  
 `pFrameWnd`  
 アクティブ化するのには、フレーム ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 ビューに関連付けられているフレーム ウィンドウがアクティブまたは非アクティブ化されたときに、特別な処理を実行する場合は、このメンバー関数をオーバーライドします。 たとえば、 [CFormView](../../mfc/reference/cformview-class.md)を保存し、フォーカスがあるコントロールを復元するときに、この上書きを実行します。  
  
##  <a name="onactivateview"></a>  CView::OnActivateView  
 ビューがアクティブまたは非アクティブ化されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnActivateView(
    BOOL bActivate,  
    CView* pActivateView,  
    CView* pDeactiveView);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActivate`  
 表示されているかどうかを示しますがアクティブまたは非アクティブ化します。  
  
 `pActivateView`  
 アクティブ化されたビュー オブジェクトへのポインター。  
  
 `pDeactiveView`  
 非アクティブになるビュー オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装では、アクティブ化されているビューにフォーカスを設定します。 ビューがアクティブまたは非アクティブ化されたときに特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、非アクティブなビューと、アクティブなビューを区別する特殊なビジュアル キューを提供する場合とを確認する、`bActivate`パラメーターと、ビューの外観を適宜更新します。  
  
 `pActivateView`と`pDeactiveView`パラメーターは、アプリケーションのメイン フレーム ウィンドウがアクティブなビューで変更が行われていないアクティブな場合、同じビューを指す — たとえば、次のいずれかからではなく、このいずれかに、別のアプリケーションからフォーカスが転送されます。表示別にアプリケーション内、または MDI 子ウィンドウの間で切り替えるときにします。 これにより、必要な場合は、そのパレットを再現するためのビューです。  
  
 これらのパラメーターが異なるとき[CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview)新機能とは異なるビューで呼び出された[CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview)を返します。 これは、分割ウィンドウでよく発生します。  
  
##  <a name="onbeginprinting"></a>  値  
 `OnPreparePrinting` が呼び出された後で、印刷または印刷プレビュー ジョブの開始時にフレームワークによって呼び出されます。  
  
```  
virtual void OnBeginPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストを指し示します。  
  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 この関数をオーバーライドして、特に印刷のために必要な GDI リソース (ペン、フォントなど) を割り当てます。 内からデバイス コンテキストに GDI オブジェクトを選択、 [OnPrint](#onprint)それらを使用する各ページのメンバー関数。 同じビュー オブジェクトを使用して画面の表示と印刷の両方を実行している場合は、各表示に必要な GDI リソースに別個の変数を使用します。これにより、印刷時に画面を更新することができます。  
  
 さらに、この関数を使用して、プリンター デバイス コンテキストのプロパティに依存する初期化を実行することもできます。 たとえば、ドキュメントを印刷するために必要なページ数は、印刷ダイアログ ボックスでユーザーが指定した設定 (たとえば、ページの長さ) によって異なる可能性があります。 このような状況で、ドキュメントの長さを指定することはできません、 [OnPreparePrinting](#onprepareprinting)メンバー関数の場合、通常行うようにする場所です ダイアログ ボックスの設定に基づいてプリンター デバイス コンテキストが作成されるまでに待機する必要があります。 [OnBeginPrinting](#onbeginprinting)への最初のオーバーライド可能な関数を提供するアクセスは、 [CDC](../../mfc/reference/cdc-class.md)のため、この関数からドキュメントの長さを設定することができます、プリンター デバイス コンテキストを表すオブジェクト。 この時点でドキュメントの長さを指定しない場合、印刷プレビュー時にスクロール バーは表示されません。  
  
##  <a name="ondragenter"></a>  CView::OnDragEnter  
 マウスがドロップ ターゲットのウィンドウの非スクロール領域を最初に入ったときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ビューのドロップ領域にドラッグしています。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**です。  
  
 `point`  
 ビューのクライアント領域と相対的現在のマウスの位置。  
  
### <a name="return-value"></a>戻り値  
 値、`DROPEFFECT`列挙型、ユーザーがこの位置にあるオブジェクトを削除する場合に発生するドロップダウンの型を示します。 Drop の種類は、によって示される現在のキーの状態に通常依存`dwKeyState`です。 Keystates の標準的なマッピング`DROPEFFECT`値は。  
  
- `DROPEFFECT_NONE` このウィンドウで、データ オブジェクトを削除できません。  
  
- `DROPEFFECT_LINK` **MK_CONTROL &#124; MK_SHIFT** 、オブジェクトとサーバー間のリンケージを作成します。  
  
- `DROPEFFECT_COPY` **MK_CONTROL**ドロップされたオブジェクトのコピーを作成します。  
  
- `DROPEFFECT_MOVE` **MK_ALT**ドロップされたオブジェクトのコピーを作成し、元のオブジェクトを削除します。 これは、通常既定ドロップ操作の結果、ビューは、このデータ オブジェクトを受け取ることができます。  
  
 詳細については、MFC Advanced Concepts サンプルを参照してください。 [OCLIENT](../../visual-cpp-samples.md)です。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も返す`DROPEFFECT_NONE`です。  
  
 将来の呼び出しを準備するには、この関数をオーバーライド、 [OnDragOver](#ondragover)メンバー関数。 この時点で後で使用できるデータ オブジェクトから必要なすべてのデータを取得する必要があります、`OnDragOver`メンバー関数。 ビューは、ユーザーの視覚的フィードバックを提供するには、この時点でも更新する必要があります。 詳細については、記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../../mfc/drag-and-drop-implementing-a-drop-target.md)です。  
  
##  <a name="ondragleave"></a>  CView::OnDragLeave  
 そのウィンドウで、有効なドロップ領域不足、マウスを移動すると、ドラッグ操作中に、フレームワークによって呼び出されます  
  
```  
virtual void OnDragLeave();
```  
  
### <a name="remarks"></a>コメント  
 現在のビューは、中に行った操作をクリーンアップする必要がある場合は、この関数をオーバーライド[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)オブジェクトがドラッグ アンド ドロップ中に、ビジュアル ユーザー フィードバックを削除するなどの呼び出し.  
  
##  <a name="ondragover"></a>  直前  
 マウスをドロップ ターゲットのウィンドウに移動するドラッグ操作中に、フレームワークによって呼び出されます  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ドロップ ターゲット上にドラッグします。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**です。  
  
 `point`  
 ビューのクライアント領域の基準とした現在のマウスの位置。  
  
### <a name="return-value"></a>戻り値  
 値、`DROPEFFECT`列挙型、ユーザーがこの位置にあるオブジェクトを削除する場合に発生するドロップダウンの型を示します。 種類ドロップの多くの場合、異なりますキーの現在の状態によって示される`dwKeyState`です。 Keystates の標準的なマッピング`DROPEFFECT`値は。  
  
- `DROPEFFECT_NONE` このウィンドウで、データ オブジェクトを削除できません。  
  
- `DROPEFFECT_LINK` **MK_CONTROL &#124; MK_SHIFT** 、オブジェクトとサーバー間のリンケージを作成します。  
  
- `DROPEFFECT_COPY` **MK_CONTROL**ドロップされたオブジェクトのコピーを作成します。  
  
- `DROPEFFECT_MOVE` **MK_ALT**ドロップされたオブジェクトのコピーを作成し、元のオブジェクトを削除します。 これは、通常既定ドロップ操作の結果、ビューは、データ オブジェクトを受け取ることができます。  
  
 詳細については、MFC Advanced Concepts サンプルを参照してください。 [OCLIENT](../../visual-cpp-samples.md)です。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、何も返す`DROPEFFECT_NONE`です。  
  
 ドラッグ操作中にユーザーに視覚的フィードバックを提供するには、この関数をオーバーライドします。 以降、この関数は継続的に呼び出されると、それに含まれるすべてのコードをできるだけ最適化してください。 詳細については、記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../../mfc/drag-and-drop-implementing-a-drop-target.md)です。  
  
##  <a name="ondragscroll"></a>  CView::OnDragScroll  
 呼び出しの前にフレームワークによって呼び出されます[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)ポイントがスクロール可能な領域があるかどうかを決定します。  
  
```  
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**です。  
  
 `point`  
 画面に対して相対的ピクセル単位で、カーソルの位置が含まれています。  
  
### <a name="return-value"></a>戻り値  
 値、`DROPEFFECT`列挙型、ユーザーがこの位置にあるオブジェクトを削除する場合に発生するドロップダウンの型を示します。 Drop の種類は、によって示される現在のキーの状態に通常依存`dwKeyState`です。 Keystates の標準的なマッピング`DROPEFFECT`値は。  
  
- `DROPEFFECT_NONE` このウィンドウで、データ オブジェクトを削除できません。  
  
- `DROPEFFECT_LINK` **MK_CONTROL &#124; MK_SHIFT** 、オブジェクトとサーバー間のリンケージを作成します。  
  
- `DROPEFFECT_COPY` **MK_CONTROL**ドロップされたオブジェクトのコピーを作成します。  
  
- `DROPEFFECT_MOVE` **MK_ALT**ドロップされたオブジェクトのコピーを作成し、元のオブジェクトを削除します。  
  
- `DROPEFFECT_SCROLL` ドラッグ スクロール操作が発生するか、対象のビューで発生していることを示します。  
  
 詳細については、MFC Advanced Concepts サンプルを参照してください。 [OCLIENT](../../visual-cpp-samples.md)です。  
  
### <a name="remarks"></a>コメント  
 このイベントの特別な動作を提供する場合は、この関数をオーバーライドします。 既定の実装では、カーソルが各ウィンドウの枠線内の既定のスクロール領域にドラッグされると、windows が自動的にスクロールします。詳細については、記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../../mfc/drag-and-drop-implementing-a-drop-target.md)です。  
  
##  <a name="ondraw"></a>  詳細  
 ドキュメントのイメージをレンダリングするためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(CDC* pDC) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ドキュメントのイメージの描画に使用するデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 各ケースで別のデバイス コンテキストを渡すし、画面表示、印刷、および印刷プレビューを実行するには、この関数呼び出し、します。 既定の実装はありません。  
  
 ドキュメントのビューを表示するには、この関数をオーバーライドする必要があります。 使用してグラフィック デバイス インターフェイス (GDI) 呼び出しを行うことができます、 [CDC](../../mfc/reference/cdc-class.md)によって指されるオブジェクト、`pDC`パラメーター。 描画前にデバイス コンテキストにペン、フォントなどの GDI リソースを選択し、後に選択解除できます。 多くの場合、描画コードをできるデバイスに依存しません。つまり、デバイスの種類が、イメージを表示する方法についての情報をする必要がないです。  
  
 描画を最適化する呼び出し、[ため](../../mfc/reference/cdc-class.md#rectvisible)を指定した四角形を描画するかどうかを調べるには、デバイス コンテキストのメンバー関数。 通常の画面表示と印刷を区別する必要がある場合は、呼び出し、 [IsPrinting](../../mfc/reference/cdc-class.md#isprinting)デバイス コンテキストのメンバー関数。  
  
##  <a name="ondrop"></a>  この関数  
 ユーザーは、有効なドロップ ターゲット上でデータ オブジェクトを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrop(
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)がドロップ ターゲットにドロップします。  
  
 `dropEffect`  
 ユーザーが要求しているドロップ効果。  
  
- `DROPEFFECT_COPY` 削除されるデータ オブジェクトのコピーを作成します。  
  
- `DROPEFFECT_MOVE` データ オブジェクトを現在のマウスの位置に移動します。  
  
- `DROPEFFECT_LINK` データ オブジェクトとサーバー間のリンクを作成します。  
  
 `point`  
 ビューのクライアント領域の基準とした現在のマウスの位置。  
  
### <a name="return-value"></a>戻り値  
 ドロップダウンが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装は何もしませんし、返します**FALSE**です。  
  
 ビューのクライアント領域に OLE ドロップの効果を実装するには、この関数をオーバーライドします。 使用して、データ オブジェクトを調べることができます`pDataObject`クリップボード データ形式とデータ削除指定した位置にします。  
  
> [!NOTE]
>  オーバーライドがある場合、フレームワークはこの関数を呼び出しません[OnDropEx](#ondropex)このビュー クラスにします。  
  
##  <a name="ondropex"></a>  CView::OnDropEx  
 ユーザーは、有効なドロップ ターゲット上でデータ オブジェクトを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)がドロップ ターゲットにドロップします。  
  
 `dropDefault`  
 現在のキーの状態に基づく既定のドロップ操作のユーザーが選択した結果。 可能性がある`DROPEFFECT_NONE`です。 ドロップ効果は、「解説」セクションで説明します。  
  
 `dropList`  
 ドロップ ソースでサポートされる、ドロップ効果の一覧。 ビットごとの OR を使用して、ドロップ効果の値を結合することができます ( **&#124;**) 操作です。 ドロップ効果は、「解説」セクションで説明します。  
  
 `point`  
 ビューのクライアント領域の基準とした現在のマウスの位置。  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップしようとしたときの原因となったドロップ効果`point`です。 によって示される値のいずれかがこのあります*dropEffectList*です。 ドロップ効果は、「解説」セクションで説明します。  
  
### <a name="remarks"></a>コメント  
 既定の実装が何もしないし、フレームワークを呼び出す必要がありますを示すためにダミーの値 (-1) を返すには、 [OnDrop](#ondrop)ハンドラー。  
  
 マウスの右ボタンのドラッグ アンド ドロップの効果を実装するには、この関数をオーバーライドします。 マウスの右ボタンのドラッグ アンド ドロップ、マウスの右ボタンが離されると、メニュー項目を通常表示します。  
  
 オーバーライド`OnDropEx`マウスの右ボタンのクエリを実行する必要があります。 呼び出すことができます[GetKeyState](http://msdn.microsoft.com/library/windows/desktop/ms646301)からマウスの右ボタンの状態を保存、 [OnDragEnter](#ondragenter)ハンドラー。  
  
-   マウスの右ボタンがダウンしている場合、上書きにはドロップ ソースが、ドロップ効果のサポートを提供するポップアップ メニューが表示されます。  
  
    -   調べる`dropList`をドロップ ソースがサポートされているドロップ効果を判断します。 ポップアップ メニューにこれらのアクションのみを有効にします。  
  
    -   使用して[SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996)に基づいて既定のアクションを設定する`dropDefault`です。  
  
    -   最後に、対処をポップアップ メニューからユーザーの選択によって示されます。  
  
-   マウスの右ボタンが押されていない場合、オーバーライドする必要があります。 この処理標準ドロップ要求として。 指定されたドロップ効果を使用して`dropDefault`です。 代わりに、オーバーライドできることを示すためにダミーの値 (-1) を返す`OnDrop`このドロップ操作を処理します。  
  
 使用して`pDataObject`を調べる、`COleDataObject`クリップボード データ形式とデータ削除指定した位置にします。  
  
 ドロップ効果には、drop 操作に関連付けられたアクションがについて説明します。 次のようなドロップ効果の一覧を参照してください。  
  
- `DROPEFFECT_NONE` ドロップは許可されていません。  
  
- `DROPEFFECT_COPY` コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE` 移動操作が実行されます。  
  
- `DROPEFFECT_LINK` ドロップされたデータから、元のデータへのリンクが確立できません。  
  
- `DROPEFFECT_SCROLL` ドラッグ スクロール操作が発生するか、ターゲットで発生していることを示します。  
  
 既定のメニュー コマンドの設定の詳細については、次を参照してください。 [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) Windows sdk と[CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu)このボリュームにします。  
  
##  <a name="onendprinting"></a>  CView::OnEndPrinting  
 ドキュメントが印刷またはプレビューされた後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnEndPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストを指し示します。  
  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 割り当てられている GDI リソースを解放するには、この関数をオーバーライドします[OnBeginPrinting](#onbeginprinting)メンバー関数。  
  
##  <a name="onendprintpreview"></a>  CView::OnEndPrintPreview  
 印刷プレビュー モードを終了するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnEndPrintPreview(
    CDC* pDC,  
    CPrintInfo* pInfo,  
    POINT point,  
    CPreviewView* pView);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストを指し示します。  
  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
 `point`  
 プレビュー モードで最後に表示されたページで、ポイントを指定します。  
  
 `pView`  
 プレビューに使用するビュー オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装、 [OnEndPrinting](#onendprinting)印刷プレビューの前に、の状態をメイン フレーム ウィンドウが開始されたメンバー関数を復元します。 プレビュー モードが終了した場合に、特別な処理を実行するには、この関数をオーバーライドします。 たとえば、プレビュー モードから通常の表示モードに切り替える際に、ドキュメント内のユーザーの位置を維持する場合は、スクロールできますで説明されている位置に、`point`パラメーターおよび`m_nCurPage`のメンバー、`CPrintInfo`構造体`pInfo`パラメーターをポイントします。  
  
 常に、基本クラスのバージョンを呼び出す`OnEndPrintPreview`関数の末尾には通常、オーバーライドします。  
  
##  <a name="oninitialupdate"></a>  :Oninitialupdate  
 ビューが最初に表示される前に、ビューが最初に、ドキュメントにアタッチされている後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装、 [OnUpdate](#onupdate)ヒント情報なしのメンバー関数 (つまり、0 を既定値を使用して、`lHint`パラメーターと**NULL** の`pHint`パラメーター)。 ドキュメントに関する情報を必要とする任意の 1 回だけ初期化を実行するには、この関数をオーバーライドします。 たとえば、アプリケーションに固定サイズのドキュメントがある場合は、ドキュメントのサイズに基づくビューのスクロールの範囲を初期化するためにこの関数を使用できます。 アプリケーションでは、可変サイズのドキュメントをサポートする場合を使用して[OnUpdate](#onupdate)スクロールを更新する制限たびにドキュメントの変更。  
  
##  <a name="onpreparedc"></a>  付け  
 前にフレームワークによって呼び出されます、 [OnDraw](#ondraw)画面表示とする前に、メンバー関数が呼び出される、 [OnPrint](#onprint)印刷または印刷のプレビュー期間中の各ページのメンバー関数が呼び出されます。  
  
```  
virtual void OnPrepareDC(
    CDC* pDC,  
    CPrintInfo* pInfo = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ドキュメントのイメージの描画に使用するデバイス コンテキストへのポインター。  
  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)場合は、現在の印刷ジョブを記述する構造体`OnPrepareDC`印刷または印刷プレビューで呼び出されたが、`m_nCurPage`メンバーを印刷するページを指定します。 このパラメーターは**NULL**場合`OnPrepareDC`画面に対して呼び出されます。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は画面表示のため、関数が呼び出された場合に、何も行いません。 ただし、この関数は、派生クラスでオーバーライドなど[CScrollView](../../mfc/reference/cscrollview-class.md)のデバイス コンテキストの属性を調整するには、オーバーライドした関数の先頭に基本クラス実装を呼び出すは常にその結果、します。  
  
 印刷の関数が呼び出されると場合、既定の実装に格納されているページの情報を調べて、`pInfo`パラメーター。 ドキュメントの長さが指定されていない場合`OnPrepareDC`1 ページにあるドキュメントを前提としていて、1 つのページが印刷された後に印刷ループを停止します。 関数を設定して印刷ループを停止する、`m_bContinuePrinting`に構造体のメンバー **FALSE**です。  
  
 オーバーライド`OnPrepareDC`の原因は次のいずれか。  
  
-   指定されたページの必要に応じて、デバイス コンテキストの属性を調整します。 たとえば、マップ モードまたはデバイス コンテキストの他の特性を設定する必要がある場合ではこの関数。  
  
-   印刷時の改ページを実行します。 使用して、印刷の開始時にドキュメントの長さを指定する通常、 [OnPreparePrinting](#onprepareprinting)メンバー関数。 ただし、理解していない場合、事前にどのくらいの時間のドキュメント (たとえば、印刷時に、何らかの数のレコードをデータベースから) は、オーバーライド`OnPrepareDC`が出力されているときに、ドキュメントの末尾をテストします。 ある場合、ドキュメントを印刷するはこれ以上、設定、`m_bContinuePrinting`のメンバー、`CPrintInfo`構造の**FALSE**です。  
  
-   エスケープ コードをページ単位ごとにプリンターに送信します。 エスケープ コードを送信する`OnPrepareDC`を呼び出して、**エスケープ**のメンバー関数、`pDC`パラメーター。  
  
 基本クラスを呼び出して`OnPrepareDC`オーバーライドの先頭にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]  
  
##  <a name="onprepareprinting"></a>  関数  
 ドキュメントが印刷またはプレビューされる前に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
### <a name="return-value"></a>戻り値  
 印刷が開始する 0 以外の値印刷ジョブが取り消された場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。  
  
 印刷と印刷プレビューを有効にするには、この関数をオーバーライドする必要があります。 呼び出す、 [DoPreparePrinting](#doprepareprinting)を引数としてメンバー関数の場合、`pInfo`パラメーター、その戻り値を返す`DoPreparePrinting`印刷 ダイアログ ボックスを表示し、プリンター デバイス コンテキストを作成します。 既定以外の値を持つ [印刷] ダイアログ ボックスを初期化する場合は、メンバーに値を割り当てる`pInfo`です。 たとえば、ドキュメントの長さがわかっている場合に値を渡す、 [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage)のメンバー関数`pInfo`呼び出す前に`DoPreparePrinting`です。 この値が表示されます。 範囲 の 印刷 ダイアログ ボックスのボックスです。  
  
 `DoPreparePrinting` プレビュー ジョブの印刷 ダイアログ ボックスは表示されません。 印刷ジョブの印刷 ダイアログ ボックスをバイパスする場合は、ことを確認、**されます**のメンバー`pInfo`は**FALSE**に設定および**TRUE**に渡す前に`DoPreparePrinting`; にリセット**FALSE**後です。  
  
 アクセスを必要とする初期化を実行する必要があるかどうか、 `CDC` (たとえば、ドキュメントの長さを指定する前に、ページ サイズを知る必要がある場合)、プリンター デバイス コンテキストを表すオブジェクトを上書き、`OnBeginPrinting`メンバー関数。  
  
 値を設定する場合、 **m_nNumPreviewPages**または**関数**のメンバー、`pInfo`パラメーターで呼び出した後に行う`DoPreparePrinting`です。 `DoPreparePrinting`メンバー関数のセットを**m_nNumPreviewPages**アプリケーションの値にします。INI ファイル設定と**関数**を既定値にします。  
  
### <a name="example"></a>例  
  オーバーライド`OnPreparePrinting`を呼び出すと`DoPreparePrinting`オーバーライドからフレームワークは、[印刷] ダイアログ ボックスを表示し、プリンター DC を作成してようにします。  
  
 [!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]  
  
 ドキュメントが含まれるページ数がわかっている場合は、最大のページを設定`OnPreparePrinting`呼び出す前に`DoPreparePrinting`です。 フレームワークで、"to"、印刷ダイアログ ボックスの ページの最大数が表示されます。  
  
 [!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]  
  
##  <a name="onprint"></a>  のみ  
 印刷または印刷ドキュメントのページをプレビューするためにフレームワークによって呼び出されます。  
  
```  
virtual void OnPrint(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストを指し示します。  
  
 `pInfo`  
 指す、`CPrintInfo`現在の印刷ジョブを記述する構造体。  
  
### <a name="remarks"></a>コメント  
 印刷されるページごとに、フレームワークを呼び出し、この関数呼び出し直後後、 [OnPrepareDC](#onpreparedc)メンバー関数。 印刷されるページが指定された、`m_nCurPage`のメンバー、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)構造体`pInfo`を指します。 既定の実装、 [OnDraw](#ondraw)メンバー関数はプリンター デバイス コンテキストを渡します。  
  
 次の理由のいずれかに対してこの関数をオーバーライドします。  
  
-   マルチページ ドキュメントの印刷を許可するには 現在印刷中のページに対応するドキュメントの部分のみを表示します。 使用する場合`OnDraw`レンダリングを実行するドキュメントの適切な部分だけが印刷されるよう、ビューポートの原点を調整できます。  
  
-   異なる外観画面イメージ (つまり、アプリケーションは WYSIWYG ではない) 場合、印刷されたイメージを確認します。 プリンター デバイス コンテキストを渡す代わりに`OnDraw`画面に表示されない属性を使用してイメージを表示するために、デバイス コンテキストを使用します。  
  
     画面の表示を使用しない印刷に GDI リソースが必要な場合は、描画前にデバイス コンテキストに選択し、後に選択解除します。 これらの GDI リソースを割り当てる必要がある[OnBeginPrinting](#onbeginprinting)およびでリリースされる[OnEndPrinting](#onendprinting)です。  
  
-   ヘッダーまたはフッターを実装します。 使用することもできます`OnDraw`で印刷できる領域を制限することで、表示を行う。  
  
 なお、 **m_rectDraw**のメンバー、`pInfo`パラメーターは、論理ユニットのページの印刷可能領域をについて説明します。  
  
 呼び出す必要はありません`OnPrepareDC`のオーバーライドで`OnPrint`以外の場合は、フレームワークによって`OnPrepareDC`呼び出す前に自動的に`OnPrint`です。  
  
### <a name="example"></a>例  
 次に、オーバーライドされるのスケルトン`OnPrint`関数。  
  
 [!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]  
  
 別の例では、次を参照してください。 [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect)です。  
  
##  <a name="onscroll"></a>  CView::OnScroll  
 考えられるがスクロールするかどうかを判断するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnScroll(
    UINT nScrollCode,  
    UINT nPos,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nScrollCode`  
 スクロール バーのコードをユーザーを示すには、要求のスクロールします。 このパラメーターは 2 つの部分で構成されます: を水平方向にスクロール発生の種類を決定するには、下位バイトおよび高位バイトのことで、垂直方向にスクロール発生の種類を決定します。  
  
- **SB_BOTTOM**一番下までスクロールします。  
  
- **SB_LINEDOWN**が 1 行下へスクロールします。  
  
- **SB_LINEUP**を 1 つの行にスクロールします。  
  
- **SB_PAGEDOWN**が 1 ページ下へスクロールします。  
  
- **SB_PAGEUP**を 1 つのページをスクロールします。  
  
- **SB_THUMBTRACK**指定した位置にスクロール ボックスをドラッグします。 現在の位置を指定`nPos`です。  
  
- **SB_TOP**上部までスクロールします。  
  
 `nPos`  
 スクロール バーのコードがある場合、現在のスクロール ボックスの位置を含む**SB_THUMBTRACK**です。 それ以外の場合は使用されません。 初期のスクロールの範囲に応じて`nPos`が負の数およびにキャストする必要があります、`int`必要な場合です。  
  
 `bDoScroll`  
 指定されたスクロール動作を実際に行うかどうかを判断します。 場合**true の場合、**スクロールを行う; 場合、 **FALSE**、スクロールする必要がありますが実行されません。  
  
### <a name="return-value"></a>戻り値  
 場合`bDoScroll`は**TRUE**とビューをスクロール実際には、戻りますは 0 以外。 それ以外の場合 0 です。 場合`bDoScroll`は**FALSE**、するが返される場合、値を返す`bDoScroll`された**TRUE**場合でも、実際には、スクロールを行わないと、します。  
  
### <a name="remarks"></a>コメント  
 1 つのケースで、この関数がフレームワークによって呼び出されます`bDoScroll`'éý' **TRUE**ビューがスクロール バーのメッセージを受信するとします。 この場合、ビューを実際にスクロールする必要があります。 その他の場合は、この関数が呼び出されます`bDoScroll`'éý' **FALSE** OLE 項目が最初にドロップときのドロップ ターゲットの自動スクロール領域にスクロール実際に行われる前にします。 ここでは、する必要がありますいない実際にビューをスクロールします。  
  
##  <a name="onscrollby"></a>  CView::OnScrollBy  
 ユーザーがビューの現在の罫線に対して OLE 項目をドラッグして、または垂直方向または水平方向のスクロール バーを操作することで、ドキュメントの存在のビューを超える領域を表示するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnScrollBy(
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `sizeScroll`  
 ピクセル数は、水平方向および垂直方向にスクロールします。  
  
 `bDoScroll`  
 ビューのスクロールするかどうかを判断します。 場合**true の場合、**場合; スクロールの受け取りを配置し、 **FALSE**、スクロールは発生しません。  
  
### <a name="return-value"></a>戻り値  
 ビューがこの方向にスクロールするできた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドは、ビューは、ユーザーが要求され、必要に応じて、新しい領域を更新し、方向にスクロールできるかどうかを確認します。 この関数は自動的に呼び出されます[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[ために](../../mfc/reference/cwnd-class.md#onvscroll)を実際のスクロールの要求を実行します。  
  
 このメソッドの既定の実装には、ビューは変わりませんが呼び出されない場合、ビューをスクロールするのには`CScrollView`-クラスを派生します。  
  
 ドキュメントの幅または高さが 32767 ピクセルを超えると、過去の 32767 スクロールのため失敗します`OnScrollBy`が正しくないと呼びます`sizeScroll`引数。  
  
##  <a name="onupdate"></a>  CView::OnUpdate  
 ビューのドキュメントが変更された後に、フレームワークによって呼び出されますこの関数は[CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews)と、それらの変更を反映するように表示を更新します。  
  
```  
virtual void OnUpdate(
    CView* pSender,  
    LPARAM lHint,  
    CObject* pHint);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSender`  
 ドキュメントを変更するビューへのポインターまたは**NULL**場合、すべてのビューを更新します。  
  
 `lHint`  
 変更についての情報が含まれています。  
  
 `pHint`  
 変更についての情報を格納するオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装によって呼び出されますも[フィルターと並べ替え順序](#oninitialupdate)です。 既定の実装がクライアント領域全体、ときに描画するためにマークを無効になります次`WM_PAINT`メッセージを受信します。 ドキュメントの変更後の部分に割り当てられた領域のみを更新する場合は、この関数をオーバーライドします。 これを行うには、ヒントのパラメーターを使用して変更についての情報を渡す必要があります。  
  
 使用する`lHint`ビットマスクまたは列挙型では、通常、特別なヒントの値を定義、およびドキュメントをこれらの値のいずれかを渡します。 使用する`pHint`からヒント クラスを派生[CObject](../../mfc/reference/cobject-class.md)ドキュメントをオーバーライドする場合のヒントにポインターを渡す`OnUpdate`を使用して、[使うため](../../mfc/reference/cobject-class.md#iskindof)するメンバー関数ヒント オブジェクトの実行時の型を決定します。  
  
 通常実行するいずれかから直接描画`OnUpdate`です。 代わりに、デバイスの座標で、更新; が必要な領域を示す四角形を決定します。この四角形を渡す[エディット](../../mfc/reference/cwnd-class.md#invalidaterect)です。 これを次に行うことが原因で、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージを受信します。  
  
 場合`lHint`は 0 と`pHint`は**NULL**ドキュメントが汎用的な更新の通知を送信します。 ビューは、汎用的な更新プログラムの通知を受信した場合、または、ヒントをデコードできない場合は、そのクライアント領域全体を無効にします。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルは](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)
